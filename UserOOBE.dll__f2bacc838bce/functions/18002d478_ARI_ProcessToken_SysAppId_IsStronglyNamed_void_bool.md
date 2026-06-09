# ARI::ProcessToken::SysAppId::IsStronglyNamed(void *,bool *)

- ea: `0x18002d478`
- end: `0x18002d5a1`
- name: `?IsStronglyNamed@SysAppId@ProcessToken@ARI@@YAJPEAXPEA_N@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d41c`

## callees

- `0x180004200`
- `0x18002d25c`
- `0x18002d2a8`
- `0x18002d478`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002d54c`
- `ntdll!RtlInitUnicodeString` at `0x18002d54c`
- `ntdll!RtlCompareUnicodeString` at `0x18002d574`
- `ntdll!RtlCompareUnicodeString` at `0x18002d574`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002d4c8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002d528`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002d4c8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002d528`
- `ntdll!NtQueryInformationToken` at `0x18002d4ab`
- `ntdll!NtQueryInformationToken` at `0x18002d51c`
- `ntdll!NtQueryInformationToken` at `0x18002d4ab`
- `ntdll!NtQueryInformationToken` at `0x18002d51c`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::IsStronglyNamed(HANDLE TokenHandle, _BYTE *a2, bool *a3)
{
  NTSTATUS InformationToken; // eax
  void *v7; // rax
  void *v8; // rdx
  void *v9; // rbx
  int v10; // eax
  UNICODE_STRING *v11; // rdx
  ULONG v12; // edi
  __int64 i; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  size_t Size; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(Size) = 0;
  *a2 = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, (PULONG)&Size);
  if ( InformationToken == -1073741789 )
  {
    v7 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>((unsigned int)Size);
    v9 = v7;
    if ( v7 )
    {
      memset_0(v7, 0, (unsigned int)Size);
      v10 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v9, Size, (PULONG)&Size);
      if ( v10 >= 0 )
      {
        if ( *((_DWORD *)v9 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          for ( i = 0; (unsigned int)i < *((_DWORD *)v9 + 1); i = (unsigned int)(i + 1) )
          {
            v11 = (UNICODE_STRING *)(*((_QWORD *)v9 + 1) + 40 * i);
            if ( v11[1].Length == 3 && !RtlCompareUnicodeString(&DestinationString, v11, 1u) )
            {
              *a2 = 1;
              break;
            }
          }
        }
        v12 = 0;
      }
      else
      {
        v12 = RtlNtStatusToDosErrorNoTeb(v10);
      }
      ARI::Free(v9, v11);
      return v12;
    }
    else
    {
      ARI::Free(0, v8);
      return 8;
    }
  }
  else if ( InformationToken )
  {
    return RtlNtStatusToDosErrorNoTeb(InformationToken);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x18002d478  mov     rax, rsp
0x18002d47b  mov     [rax+8], rbx
0x18002d47f  mov     [rax+18h], rsi
0x18002d483  push    rdi
0x18002d484  sub     rsp, 40h
0x18002d488  xor     r9d, r9d; TokenInformationLength
0x18002d48b  mov     dword ptr [rax+10h], 0
0x18002d492  mov     rsi, rdx
0x18002d495  mov     byte ptr [rdx], 0
0x18002d498  lea     rax, [rax+10h]
0x18002d49c  xor     r8d, r8d; TokenInformation
0x18002d49f  mov     rdi, rcx
0x18002d4a2  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002d4a7  lea     edx, [r9+27h]; TokenInformationClass
0x18002d4ab  call    cs:__imp_NtQueryInformationToken
0x18002d4b1  cmp     eax, 0C0000023h
0x18002d4b6  jz      short loc_18002D4D3
0x18002d4b8  test    eax, eax
0x18002d4ba  jnz     short loc_18002D4C6
0x18002d4bc  mov     eax, 54Fh
0x18002d4c1  jmp     loc_18002D591
0x18002d4c6  mov     ecx, eax; Status
0x18002d4c8  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18002d4ce  jmp     loc_18002D591
0x18002d4d3  mov     ecx, dword ptr [rsp+48h+Size]
0x18002d4d7  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18002d4dc  mov     rbx, rax
0x18002d4df  test    rax, rax
0x18002d4e2  jnz     short loc_18002D4F3
0x18002d4e4  xor     ecx, ecx; P
0x18002d4e6  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18002d4eb  lea     eax, [rbx+8]
0x18002d4ee  jmp     loc_18002D591
0x18002d4f3  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x18002d4f8  xor     edx, edx; Val
0x18002d4fa  mov     rcx, rbx; void *
0x18002d4fd  call    memset_0
0x18002d502  mov     r9d, dword ptr [rsp+48h+Size]; TokenInformationLength
0x18002d507  lea     rax, [rsp+48h+Size]
0x18002d50c  mov     r8, rbx; TokenInformation
0x18002d50f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002d514  mov     edx, 27h ; '''; TokenInformationClass
0x18002d519  mov     rcx, rdi; TokenHandle
0x18002d51c  call    cs:__imp_NtQueryInformationToken
0x18002d522  test    eax, eax
0x18002d524  jns     short loc_18002D532
0x18002d526  mov     ecx, eax; Status
0x18002d528  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18002d52e  mov     edi, eax
0x18002d530  jmp     short loc_18002D587
0x18002d532  cmp     dword ptr [rbx+4], 0
0x18002d536  jbe     short loc_18002D585
0x18002d538  xorps   xmm0, xmm0
0x18002d53b  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x18002d542  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18002d547  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18002d54c  call    cs:__imp_RtlInitUnicodeString
0x18002d552  xor     edi, edi
0x18002d554  cmp     edi, [rbx+4]
0x18002d557  jnb     short loc_18002D585
0x18002d559  mov     rax, [rbx+8]
0x18002d55d  lea     rcx, [rdi+rdi*4]
0x18002d561  lea     rdx, [rax+rcx*8]; String2
0x18002d565  cmp     word ptr [rdx+10h], 3
0x18002d56a  jnz     short loc_18002D57E
0x18002d56c  mov     r8b, 1; CaseInsensitive
0x18002d56f  lea     rcx, [rsp+48h+DestinationString]; String1
0x18002d574  call    cs:__imp_RtlCompareUnicodeString
0x18002d57a  test    eax, eax
0x18002d57c  jz      short loc_18002D582
0x18002d57e  inc     edi
0x18002d580  jmp     short loc_18002D554
0x18002d582  mov     byte ptr [rsi], 1
0x18002d585  xor     edi, edi
0x18002d587  mov     rcx, rbx; P
0x18002d58a  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18002d58f  mov     eax, edi
0x18002d591  mov     rbx, [rsp+48h+arg_0]
0x18002d596  mov     rsi, [rsp+48h+arg_10]
0x18002d59b  add     rsp, 40h
0x18002d59f  pop     rdi
0x18002d5a0  retn
```
