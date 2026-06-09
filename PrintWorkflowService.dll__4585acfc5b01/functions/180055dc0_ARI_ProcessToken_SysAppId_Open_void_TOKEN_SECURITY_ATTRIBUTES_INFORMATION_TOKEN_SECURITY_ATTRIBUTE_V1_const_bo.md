# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180055dc0`
- end: `0x180055f10`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055b7c`

## callees

- `0x18000495c`
- `0x1800557ac`
- `0x18005582c`
- `0x180055dc0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180055ecc`
- `ntdll!RtlCompareUnicodeString` at `0x180055ecc`
- `ntdll!NtQueryInformationToken` at `0x180055dfd`
- `ntdll!NtQueryInformationToken` at `0x180055e70`
- `ntdll!NtQueryInformationToken` at `0x180055dfd`
- `ntdll!NtQueryInformationToken` at `0x180055e70`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180055e1a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180055e7c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180055e1a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180055e7c`
- `ntdll!RtlInitUnicodeString` at `0x180055ea0`
- `ntdll!RtlInitUnicodeString` at `0x180055ea0`

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
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
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
0x180055dc0  mov     rax, rsp
0x180055dc3  mov     [rax+8], rbx
0x180055dc7  mov     [rax+10h], rsi
0x180055dcb  mov     [rax+20h], r9
0x180055dcf  push    rdi
0x180055dd0  push    r14
0x180055dd2  push    r15
0x180055dd4  sub     rsp, 50h
0x180055dd8  xor     r9d, r9d; TokenInformationLength
0x180055ddb  mov     dword ptr [rax+20h], 0
0x180055de2  mov     r14, r8
0x180055de5  lea     rax, [rax+20h]
0x180055de9  mov     r15, rdx
0x180055dec  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180055df1  xor     r8d, r8d; TokenInformation
0x180055df4  mov     rdi, rcx
0x180055df7  lea     esi, [r9+27h]
0x180055dfb  mov     edx, esi; TokenInformationClass
0x180055dfd  call    cs:__imp_NtQueryInformationToken
0x180055e03  cmp     eax, 0C0000023h
0x180055e08  jz      short loc_180055E25
0x180055e0a  test    eax, eax
0x180055e0c  jnz     short loc_180055E18
0x180055e0e  mov     eax, 54Fh
0x180055e13  jmp     loc_180055EFC
0x180055e18  mov     ecx, eax; Status
0x180055e1a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180055e20  jmp     loc_180055EFC
0x180055e25  mov     ecx, dword ptr [rsp+68h+Size]
0x180055e2c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180055e31  mov     rbx, rax
0x180055e34  test    rax, rax
0x180055e37  jnz     short loc_180055E41
0x180055e39  lea     ebx, [rax+8]
0x180055e3c  jmp     loc_180055EE2
0x180055e41  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180055e49  xor     edx, edx; Val
0x180055e4b  mov     rcx, rbx; void *
0x180055e4e  call    memset_0
0x180055e53  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180055e5b  lea     rax, [rsp+68h+Size]
0x180055e63  mov     r8, rbx; TokenInformation
0x180055e66  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180055e6b  mov     edx, esi; TokenInformationClass
0x180055e6d  mov     rcx, rdi; TokenHandle
0x180055e70  call    cs:__imp_NtQueryInformationToken
0x180055e76  test    eax, eax
0x180055e78  jns     short loc_180055E86
0x180055e7a  mov     ecx, eax; Status
0x180055e7c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180055e82  mov     edi, eax
0x180055e84  jmp     short loc_180055EF2
0x180055e86  cmp     dword ptr [rbx+4], 0
0x180055e8a  jbe     short loc_180055EED
0x180055e8c  xorps   xmm0, xmm0
0x180055e8f  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x180055e96  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180055e9b  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180055ea0  call    cs:__imp_RtlInitUnicodeString
0x180055ea6  xorps   xmm0, xmm0
0x180055ea9  xor     edi, edi
0x180055eab  movups  [rsp+68h+var_28], xmm0
0x180055eb0  cmp     edi, [rbx+4]
0x180055eb3  jnb     short loc_180055EED
0x180055eb5  mov     rax, [rbx+8]
0x180055eb9  lea     rcx, [rdi+rdi*4]
0x180055ebd  mov     r8b, 1; CaseInsensitive
0x180055ec0  lea     rsi, [rax+rcx*8]
0x180055ec4  mov     rdx, rsi; String2
0x180055ec7  lea     rcx, [rsp+68h+DestinationString]; String1
0x180055ecc  call    cs:__imp_RtlCompareUnicodeString
0x180055ed2  test    eax, eax
0x180055ed4  jz      short loc_180055EDA
0x180055ed6  inc     edi
0x180055ed8  jmp     short loc_180055EB0
0x180055eda  mov     [r14], rsi
0x180055edd  mov     [r15], rbx
0x180055ee0  xor     ebx, ebx
0x180055ee2  xor     ecx, ecx; P
0x180055ee4  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180055ee9  mov     eax, ebx
0x180055eeb  jmp     short loc_180055EFC
0x180055eed  mov     edi, 490h
0x180055ef2  mov     rcx, rbx; P
0x180055ef5  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180055efa  mov     eax, edi
0x180055efc  mov     rbx, [rsp+68h+arg_0]
0x180055f01  mov     rsi, [rsp+68h+arg_8]
0x180055f06  add     rsp, 50h
0x180055f0a  pop     r15
0x180055f0c  pop     r14
0x180055f0e  pop     rdi
0x180055f0f  retn
```
