# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800a62bc`
- end: `0x1800a640c`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d38c`

## callees

- `0x1800517cc`
- `0x1800a60e0`
- `0x1800a612c`
- `0x1800a62bc`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800a62f9`
- `ntdll!NtQueryInformationToken` at `0x1800a636c`
- `ntdll!NtQueryInformationToken` at `0x1800a62f9`
- `ntdll!NtQueryInformationToken` at `0x1800a636c`
- `ntdll!RtlInitUnicodeString` at `0x1800a639c`
- `ntdll!RtlInitUnicodeString` at `0x1800a639c`
- `ntdll!RtlCompareUnicodeString` at `0x1800a63c8`
- `ntdll!RtlCompareUnicodeString` at `0x1800a63c8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6316`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6378`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6316`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a6378`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  void *v9; // rax
  void *v10; // rdx
  void *v11; // rbx
  int v12; // ebx
  int v13; // eax
  ULONG v14; // edi
  __int64 v15; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v16; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v9 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v11 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, Size);
      v13 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v11, Size, &Size);
      if ( v13 >= 0 )
      {
        if ( *((_DWORD *)v11 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v15 = 0;
          v18 = 0;
          while ( (unsigned int)v15 < *((_DWORD *)v11 + 1) )
          {
            v16 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*((_QWORD *)v11 + 1) + 40 * v15);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v16, 1u) )
            {
              *a3 = v16;
              *a2 = v11;
              v12 = 0;
              goto LABEL_15;
            }
            v15 = (unsigned int)(v15 + 1);
          }
        }
        v14 = 1168;
      }
      else
      {
        v14 = RtlNtStatusToDosErrorNoTeb(v13);
      }
      ARI::Free(v11, v10);
      return v14;
    }
    else
    {
      v12 = 8;
LABEL_15:
      ARI::Free(0, v10);
      return v12;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1800a62bc  mov     rax, rsp
0x1800a62bf  mov     [rax+8], rbx
0x1800a62c3  mov     [rax+10h], rsi
0x1800a62c7  mov     [rax+20h], r9
0x1800a62cb  push    rdi
0x1800a62cc  push    r14
0x1800a62ce  push    r15
0x1800a62d0  sub     rsp, 50h
0x1800a62d4  xor     r9d, r9d; TokenInformationLength
0x1800a62d7  mov     dword ptr [rax+20h], 0
0x1800a62de  mov     r14, r8
0x1800a62e1  lea     rax, [rax+20h]
0x1800a62e5  mov     r15, rdx
0x1800a62e8  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a62ed  xor     r8d, r8d; TokenInformation
0x1800a62f0  mov     rdi, rcx
0x1800a62f3  lea     esi, [r9+27h]
0x1800a62f7  mov     edx, esi; TokenInformationClass
0x1800a62f9  call    cs:__imp_NtQueryInformationToken
0x1800a62ff  cmp     eax, 0C0000023h
0x1800a6304  jz      short loc_1800A6321
0x1800a6306  test    eax, eax
0x1800a6308  jnz     short loc_1800A6314
0x1800a630a  mov     eax, 54Fh
0x1800a630f  jmp     loc_1800A63F8
0x1800a6314  mov     ecx, eax; Status
0x1800a6316  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a631c  jmp     loc_1800A63F8
0x1800a6321  mov     ecx, dword ptr [rsp+68h+Size]
0x1800a6328  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800a632d  mov     rbx, rax
0x1800a6330  test    rax, rax
0x1800a6333  jnz     short loc_1800A633D
0x1800a6335  lea     ebx, [rax+8]
0x1800a6338  jmp     loc_1800A63DE
0x1800a633d  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800a6345  xor     edx, edx; Val
0x1800a6347  mov     rcx, rbx; void *
0x1800a634a  call    memset_0
0x1800a634f  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800a6357  lea     rax, [rsp+68h+Size]
0x1800a635f  mov     r8, rbx; TokenInformation
0x1800a6362  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a6367  mov     edx, esi; TokenInformationClass
0x1800a6369  mov     rcx, rdi; TokenHandle
0x1800a636c  call    cs:__imp_NtQueryInformationToken
0x1800a6372  test    eax, eax
0x1800a6374  jns     short loc_1800A6382
0x1800a6376  mov     ecx, eax; Status
0x1800a6378  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a637e  mov     edi, eax
0x1800a6380  jmp     short loc_1800A63EE
0x1800a6382  cmp     dword ptr [rbx+4], 0
0x1800a6386  jbe     short loc_1800A63E9
0x1800a6388  xorps   xmm0, xmm0
0x1800a638b  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800a6392  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800a6397  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800a639c  call    cs:__imp_RtlInitUnicodeString
0x1800a63a2  xorps   xmm0, xmm0
0x1800a63a5  xor     edi, edi
0x1800a63a7  movups  [rsp+68h+var_28], xmm0
0x1800a63ac  cmp     edi, [rbx+4]
0x1800a63af  jnb     short loc_1800A63E9
0x1800a63b1  mov     rax, [rbx+8]
0x1800a63b5  lea     rcx, [rdi+rdi*4]
0x1800a63b9  mov     r8b, 1; CaseInsensitive
0x1800a63bc  lea     rsi, [rax+rcx*8]
0x1800a63c0  mov     rdx, rsi; String2
0x1800a63c3  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800a63c8  call    cs:__imp_RtlCompareUnicodeString
0x1800a63ce  test    eax, eax
0x1800a63d0  jz      short loc_1800A63D6
0x1800a63d2  inc     edi
0x1800a63d4  jmp     short loc_1800A63AC
0x1800a63d6  mov     [r14], rsi
0x1800a63d9  mov     [r15], rbx
0x1800a63dc  xor     ebx, ebx
0x1800a63de  xor     ecx, ecx; P
0x1800a63e0  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a63e5  mov     eax, ebx
0x1800a63e7  jmp     short loc_1800A63F8
0x1800a63e9  mov     edi, 490h
0x1800a63ee  mov     rcx, rbx; P
0x1800a63f1  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a63f6  mov     eax, edi
0x1800a63f8  mov     rbx, [rsp+68h+arg_0]
0x1800a63fd  mov     rsi, [rsp+68h+arg_8]
0x1800a6402  add     rsp, 50h
0x1800a6406  pop     r15
0x1800a6408  pop     r14
0x1800a640a  pop     rdi
0x1800a640b  retn
```
