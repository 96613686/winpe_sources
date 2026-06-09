# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180056038`
- end: `0x180056188`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056464`

## callees

- `0x180003cf6`
- `0x180055ebc`
- `0x18005600c`
- `0x180056038`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180056092`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800560f4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180056092`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800560f4`
- `ntdll!RtlInitUnicodeString` at `0x180056118`
- `ntdll!RtlInitUnicodeString` at `0x180056118`
- `ntdll!RtlCompareUnicodeString` at `0x180056144`
- `ntdll!RtlCompareUnicodeString` at `0x180056144`
- `ntdll!NtQueryInformationToken` at `0x180056075`
- `ntdll!NtQueryInformationToken` at `0x1800560e8`
- `ntdll!NtQueryInformationToken` at `0x180056075`
- `ntdll!NtQueryInformationToken` at `0x1800560e8`

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
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
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
0x180056038  mov     rax, rsp
0x18005603b  mov     [rax+8], rbx
0x18005603f  mov     [rax+10h], rsi
0x180056043  mov     [rax+20h], r9
0x180056047  push    rdi
0x180056048  push    r14
0x18005604a  push    r15
0x18005604c  sub     rsp, 50h
0x180056050  xor     r9d, r9d; TokenInformationLength
0x180056053  mov     dword ptr [rax+20h], 0
0x18005605a  mov     r14, r8
0x18005605d  lea     rax, [rax+20h]
0x180056061  mov     r15, rdx
0x180056064  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180056069  xor     r8d, r8d; TokenInformation
0x18005606c  mov     rdi, rcx
0x18005606f  lea     esi, [r9+27h]
0x180056073  mov     edx, esi; TokenInformationClass
0x180056075  call    cs:__imp_NtQueryInformationToken
0x18005607b  cmp     eax, 0C0000023h
0x180056080  jz      short loc_18005609D
0x180056082  test    eax, eax
0x180056084  jnz     short loc_180056090
0x180056086  mov     eax, 54Fh
0x18005608b  jmp     loc_180056174
0x180056090  mov     ecx, eax; Status
0x180056092  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180056098  jmp     loc_180056174
0x18005609d  mov     ecx, dword ptr [rsp+68h+Size]
0x1800560a4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800560a9  mov     rbx, rax
0x1800560ac  test    rax, rax
0x1800560af  jnz     short loc_1800560B9
0x1800560b1  lea     ebx, [rax+8]
0x1800560b4  jmp     loc_18005615A
0x1800560b9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800560c1  xor     edx, edx; Val
0x1800560c3  mov     rcx, rbx; void *
0x1800560c6  call    memset_0
0x1800560cb  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800560d3  lea     rax, [rsp+68h+Size]
0x1800560db  mov     r8, rbx; TokenInformation
0x1800560de  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800560e3  mov     edx, esi; TokenInformationClass
0x1800560e5  mov     rcx, rdi; TokenHandle
0x1800560e8  call    cs:__imp_NtQueryInformationToken
0x1800560ee  test    eax, eax
0x1800560f0  jns     short loc_1800560FE
0x1800560f2  mov     ecx, eax; Status
0x1800560f4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800560fa  mov     edi, eax
0x1800560fc  jmp     short loc_18005616A
0x1800560fe  cmp     dword ptr [rbx+4], 0
0x180056102  jbe     short loc_180056165
0x180056104  xorps   xmm0, xmm0
0x180056107  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18005610e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180056113  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180056118  call    cs:__imp_RtlInitUnicodeString
0x18005611e  xorps   xmm0, xmm0
0x180056121  xor     edi, edi
0x180056123  movups  [rsp+68h+var_28], xmm0
0x180056128  cmp     edi, [rbx+4]
0x18005612b  jnb     short loc_180056165
0x18005612d  mov     rax, [rbx+8]
0x180056131  lea     rcx, [rdi+rdi*4]
0x180056135  mov     r8b, 1; CaseInsensitive
0x180056138  lea     rsi, [rax+rcx*8]
0x18005613c  mov     rdx, rsi; String2
0x18005613f  lea     rcx, [rsp+68h+DestinationString]; String1
0x180056144  call    cs:__imp_RtlCompareUnicodeString
0x18005614a  test    eax, eax
0x18005614c  jz      short loc_180056152
0x18005614e  inc     edi
0x180056150  jmp     short loc_180056128
0x180056152  mov     [r14], rsi
0x180056155  mov     [r15], rbx
0x180056158  xor     ebx, ebx
0x18005615a  xor     ecx, ecx; P
0x18005615c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180056161  mov     eax, ebx
0x180056163  jmp     short loc_180056174
0x180056165  mov     edi, 490h
0x18005616a  mov     rcx, rbx; P
0x18005616d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180056172  mov     eax, edi
0x180056174  mov     rbx, [rsp+68h+arg_0]
0x180056179  mov     rsi, [rsp+68h+arg_8]
0x18005617e  add     rsp, 50h
0x180056182  pop     r15
0x180056184  pop     r14
0x180056186  pop     rdi
0x180056187  retn
```
