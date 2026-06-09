# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800d8624`
- end: `0x1800d8774`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d8494`

## callees

- `0x180051524`
- `0x1800d7fa8`
- `0x1800d7ff4`
- `0x1800d8624`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d8704`
- `ntdll!RtlInitUnicodeString` at `0x1800d8704`
- `ntdll!RtlCompareUnicodeString` at `0x1800d8730`
- `ntdll!RtlCompareUnicodeString` at `0x1800d8730`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d867e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d86e0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d867e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800d86e0`
- `ntdll!NtQueryInformationToken` at `0x1800d8661`
- `ntdll!NtQueryInformationToken` at `0x1800d86d4`
- `ntdll!NtQueryInformationToken` at `0x1800d8661`
- `ntdll!NtQueryInformationToken` at `0x1800d86d4`

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
0x1800d8624  mov     rax, rsp
0x1800d8627  mov     [rax+8], rbx
0x1800d862b  mov     [rax+10h], rsi
0x1800d862f  mov     [rax+20h], r9
0x1800d8633  push    rdi
0x1800d8634  push    r14
0x1800d8636  push    r15
0x1800d8638  sub     rsp, 50h
0x1800d863c  xor     r9d, r9d; TokenInformationLength
0x1800d863f  mov     dword ptr [rax+20h], 0
0x1800d8646  mov     r14, r8
0x1800d8649  lea     rax, [rax+20h]
0x1800d864d  mov     r15, rdx
0x1800d8650  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800d8655  xor     r8d, r8d; TokenInformation
0x1800d8658  mov     rdi, rcx
0x1800d865b  lea     esi, [r9+27h]
0x1800d865f  mov     edx, esi; TokenInformationClass
0x1800d8661  call    cs:__imp_NtQueryInformationToken
0x1800d8667  cmp     eax, 0C0000023h
0x1800d866c  jz      short loc_1800D8689
0x1800d866e  test    eax, eax
0x1800d8670  jnz     short loc_1800D867C
0x1800d8672  mov     eax, 54Fh
0x1800d8677  jmp     loc_1800D8760
0x1800d867c  mov     ecx, eax; Status
0x1800d867e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800d8684  jmp     loc_1800D8760
0x1800d8689  mov     ecx, dword ptr [rsp+68h+Size]
0x1800d8690  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800d8695  mov     rbx, rax
0x1800d8698  test    rax, rax
0x1800d869b  jnz     short loc_1800D86A5
0x1800d869d  lea     ebx, [rax+8]
0x1800d86a0  jmp     loc_1800D8746
0x1800d86a5  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800d86ad  xor     edx, edx; Val
0x1800d86af  mov     rcx, rbx; void *
0x1800d86b2  call    memset_0
0x1800d86b7  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800d86bf  lea     rax, [rsp+68h+Size]
0x1800d86c7  mov     r8, rbx; TokenInformation
0x1800d86ca  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800d86cf  mov     edx, esi; TokenInformationClass
0x1800d86d1  mov     rcx, rdi; TokenHandle
0x1800d86d4  call    cs:__imp_NtQueryInformationToken
0x1800d86da  test    eax, eax
0x1800d86dc  jns     short loc_1800D86EA
0x1800d86de  mov     ecx, eax; Status
0x1800d86e0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800d86e6  mov     edi, eax
0x1800d86e8  jmp     short loc_1800D8756
0x1800d86ea  cmp     dword ptr [rbx+4], 0
0x1800d86ee  jbe     short loc_1800D8751
0x1800d86f0  xorps   xmm0, xmm0
0x1800d86f3  lea     rdx, SourceString; "WIN://SYSAPPID"
0x1800d86fa  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800d86ff  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800d8704  call    cs:__imp_RtlInitUnicodeString
0x1800d870a  xorps   xmm0, xmm0
0x1800d870d  xor     edi, edi
0x1800d870f  movups  [rsp+68h+var_28], xmm0
0x1800d8714  cmp     edi, [rbx+4]
0x1800d8717  jnb     short loc_1800D8751
0x1800d8719  mov     rax, [rbx+8]
0x1800d871d  lea     rcx, [rdi+rdi*4]
0x1800d8721  mov     r8b, 1; CaseInsensitive
0x1800d8724  lea     rsi, [rax+rcx*8]
0x1800d8728  mov     rdx, rsi; String2
0x1800d872b  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800d8730  call    cs:__imp_RtlCompareUnicodeString
0x1800d8736  test    eax, eax
0x1800d8738  jz      short loc_1800D873E
0x1800d873a  inc     edi
0x1800d873c  jmp     short loc_1800D8714
0x1800d873e  mov     [r14], rsi
0x1800d8741  mov     [r15], rbx
0x1800d8744  xor     ebx, ebx
0x1800d8746  xor     ecx, ecx; P
0x1800d8748  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800d874d  mov     eax, ebx
0x1800d874f  jmp     short loc_1800D8760
0x1800d8751  mov     edi, 490h
0x1800d8756  mov     rcx, rbx; P
0x1800d8759  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800d875e  mov     eax, edi
0x1800d8760  mov     rbx, [rsp+68h+arg_0]
0x1800d8765  mov     rsi, [rsp+68h+arg_8]
0x1800d876a  add     rsp, 50h
0x1800d876e  pop     r15
0x1800d8770  pop     r14
0x1800d8772  pop     rdi
0x1800d8773  retn
```
