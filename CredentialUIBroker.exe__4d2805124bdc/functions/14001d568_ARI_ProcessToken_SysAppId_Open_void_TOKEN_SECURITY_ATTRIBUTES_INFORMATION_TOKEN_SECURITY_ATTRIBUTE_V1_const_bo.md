# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x14001d568`
- end: `0x14001d6b8`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d320`

## callees

- `0x1400042c4`
- `0x14001cf5c`
- `0x14001d0b0`
- `0x14001d568`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001d5c2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001d624`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001d5c2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14001d624`
- `ntdll!RtlInitUnicodeString` at `0x14001d648`
- `ntdll!RtlInitUnicodeString` at `0x14001d648`
- `ntdll!NtQueryInformationToken` at `0x14001d5a5`
- `ntdll!NtQueryInformationToken` at `0x14001d618`
- `ntdll!NtQueryInformationToken` at `0x14001d5a5`
- `ntdll!NtQueryInformationToken` at `0x14001d618`
- `ntdll!RtlCompareUnicodeString` at `0x14001d674`
- `ntdll!RtlCompareUnicodeString` at `0x14001d674`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID v9; // rax
  void *v10; // rdx
  PVOID v11; // rbx
  int v12; // ebx
  int v13; // eax
  ULONG v14; // edi
  __int64 v15; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v16; // rsi
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v9 = ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
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
0x14001d568  mov     rax, rsp
0x14001d56b  mov     [rax+8], rbx
0x14001d56f  mov     [rax+10h], rsi
0x14001d573  mov     [rax+20h], r9
0x14001d577  push    rdi
0x14001d578  push    r14
0x14001d57a  push    r15
0x14001d57c  sub     rsp, 50h
0x14001d580  xor     r9d, r9d; TokenInformationLength
0x14001d583  mov     dword ptr [rax+20h], 0
0x14001d58a  mov     r14, r8
0x14001d58d  lea     rax, [rax+20h]
0x14001d591  mov     r15, rdx
0x14001d594  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14001d599  xor     r8d, r8d; TokenInformation
0x14001d59c  mov     rdi, rcx
0x14001d59f  lea     esi, [r9+27h]
0x14001d5a3  mov     edx, esi; TokenInformationClass
0x14001d5a5  call    cs:__imp_NtQueryInformationToken
0x14001d5ab  cmp     eax, 0C0000023h
0x14001d5b0  jz      short loc_14001D5CD
0x14001d5b2  test    eax, eax
0x14001d5b4  jnz     short loc_14001D5C0
0x14001d5b6  mov     eax, 54Fh
0x14001d5bb  jmp     loc_14001D6A4
0x14001d5c0  mov     ecx, eax; Status
0x14001d5c2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001d5c8  jmp     loc_14001D6A4
0x14001d5cd  mov     ecx, dword ptr [rsp+68h+Size]
0x14001d5d4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x14001d5d9  mov     rbx, rax
0x14001d5dc  test    rax, rax
0x14001d5df  jnz     short loc_14001D5E9
0x14001d5e1  lea     ebx, [rax+8]
0x14001d5e4  jmp     loc_14001D68A
0x14001d5e9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x14001d5f1  xor     edx, edx; Val
0x14001d5f3  mov     rcx, rbx; void *
0x14001d5f6  call    memset_0
0x14001d5fb  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x14001d603  lea     rax, [rsp+68h+Size]
0x14001d60b  mov     r8, rbx; TokenInformation
0x14001d60e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14001d613  mov     edx, esi; TokenInformationClass
0x14001d615  mov     rcx, rdi; TokenHandle
0x14001d618  call    cs:__imp_NtQueryInformationToken
0x14001d61e  test    eax, eax
0x14001d620  jns     short loc_14001D62E
0x14001d622  mov     ecx, eax; Status
0x14001d624  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14001d62a  mov     edi, eax
0x14001d62c  jmp     short loc_14001D69A
0x14001d62e  cmp     dword ptr [rbx+4], 0
0x14001d632  jbe     short loc_14001D695
0x14001d634  xorps   xmm0, xmm0
0x14001d637  lea     rdx, SourceString; "WIN://SYSAPPID"
0x14001d63e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001d643  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x14001d648  call    cs:__imp_RtlInitUnicodeString
0x14001d64e  xorps   xmm0, xmm0
0x14001d651  xor     edi, edi
0x14001d653  movups  [rsp+68h+var_28], xmm0
0x14001d658  cmp     edi, [rbx+4]
0x14001d65b  jnb     short loc_14001D695
0x14001d65d  mov     rax, [rbx+8]
0x14001d661  lea     rcx, [rdi+rdi*4]
0x14001d665  mov     r8b, 1; CaseInsensitive
0x14001d668  lea     rsi, [rax+rcx*8]
0x14001d66c  mov     rdx, rsi; String2
0x14001d66f  lea     rcx, [rsp+68h+DestinationString]; String1
0x14001d674  call    cs:__imp_RtlCompareUnicodeString
0x14001d67a  test    eax, eax
0x14001d67c  jz      short loc_14001D682
0x14001d67e  inc     edi
0x14001d680  jmp     short loc_14001D658
0x14001d682  mov     [r14], rsi
0x14001d685  mov     [r15], rbx
0x14001d688  xor     ebx, ebx
0x14001d68a  xor     ecx, ecx; P
0x14001d68c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x14001d691  mov     eax, ebx
0x14001d693  jmp     short loc_14001D6A4
0x14001d695  mov     edi, 490h
0x14001d69a  mov     rcx, rbx; P
0x14001d69d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x14001d6a2  mov     eax, edi
0x14001d6a4  mov     rbx, [rsp+68h+arg_0]
0x14001d6a9  mov     rsi, [rsp+68h+arg_8]
0x14001d6ae  add     rsp, 50h
0x14001d6b2  pop     r15
0x14001d6b4  pop     r14
0x14001d6b6  pop     rdi
0x14001d6b7  retn
```
