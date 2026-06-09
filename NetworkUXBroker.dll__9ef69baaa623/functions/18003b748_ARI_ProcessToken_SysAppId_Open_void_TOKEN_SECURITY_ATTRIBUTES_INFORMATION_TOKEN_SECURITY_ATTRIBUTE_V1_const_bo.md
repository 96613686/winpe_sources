# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18003b748`
- end: `0x18003b898`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b554`

## callees

- `0x1800030a0`
- `0x18003b0c0`
- `0x18003b140`
- `0x18003b748`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003b828`
- `ntdll!RtlInitUnicodeString` at `0x18003b828`
- `ntdll!NtQueryInformationToken` at `0x18003b785`
- `ntdll!NtQueryInformationToken` at `0x18003b7f8`
- `ntdll!NtQueryInformationToken` at `0x18003b785`
- `ntdll!NtQueryInformationToken` at `0x18003b7f8`
- `ntdll!RtlCompareUnicodeString` at `0x18003b854`
- `ntdll!RtlCompareUnicodeString` at `0x18003b854`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b7a2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b804`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b7a2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003b804`

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
0x18003b748  mov     rax, rsp
0x18003b74b  mov     [rax+8], rbx
0x18003b74f  mov     [rax+10h], rsi
0x18003b753  mov     [rax+20h], r9
0x18003b757  push    rdi
0x18003b758  push    r14
0x18003b75a  push    r15
0x18003b75c  sub     rsp, 50h
0x18003b760  xor     r9d, r9d; TokenInformationLength
0x18003b763  mov     dword ptr [rax+20h], 0
0x18003b76a  mov     r14, r8
0x18003b76d  lea     rax, [rax+20h]
0x18003b771  mov     r15, rdx
0x18003b774  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003b779  xor     r8d, r8d; TokenInformation
0x18003b77c  mov     rdi, rcx
0x18003b77f  lea     esi, [r9+27h]
0x18003b783  mov     edx, esi; TokenInformationClass
0x18003b785  call    cs:__imp_NtQueryInformationToken
0x18003b78b  cmp     eax, 0C0000023h
0x18003b790  jz      short loc_18003B7AD
0x18003b792  test    eax, eax
0x18003b794  jnz     short loc_18003B7A0
0x18003b796  mov     eax, 54Fh
0x18003b79b  jmp     loc_18003B884
0x18003b7a0  mov     ecx, eax; Status
0x18003b7a2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003b7a8  jmp     loc_18003B884
0x18003b7ad  mov     ecx, dword ptr [rsp+68h+Size]
0x18003b7b4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18003b7b9  mov     rbx, rax
0x18003b7bc  test    rax, rax
0x18003b7bf  jnz     short loc_18003B7C9
0x18003b7c1  lea     ebx, [rax+8]
0x18003b7c4  jmp     loc_18003B86A
0x18003b7c9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18003b7d1  xor     edx, edx; Val
0x18003b7d3  mov     rcx, rbx; void *
0x18003b7d6  call    memset_0
0x18003b7db  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18003b7e3  lea     rax, [rsp+68h+Size]
0x18003b7eb  mov     r8, rbx; TokenInformation
0x18003b7ee  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003b7f3  mov     edx, esi; TokenInformationClass
0x18003b7f5  mov     rcx, rdi; TokenHandle
0x18003b7f8  call    cs:__imp_NtQueryInformationToken
0x18003b7fe  test    eax, eax
0x18003b800  jns     short loc_18003B80E
0x18003b802  mov     ecx, eax; Status
0x18003b804  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003b80a  mov     edi, eax
0x18003b80c  jmp     short loc_18003B87A
0x18003b80e  cmp     dword ptr [rbx+4], 0
0x18003b812  jbe     short loc_18003B875
0x18003b814  xorps   xmm0, xmm0
0x18003b817  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18003b81e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18003b823  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18003b828  call    cs:__imp_RtlInitUnicodeString
0x18003b82e  xorps   xmm0, xmm0
0x18003b831  xor     edi, edi
0x18003b833  movups  [rsp+68h+var_28], xmm0
0x18003b838  cmp     edi, [rbx+4]
0x18003b83b  jnb     short loc_18003B875
0x18003b83d  mov     rax, [rbx+8]
0x18003b841  lea     rcx, [rdi+rdi*4]
0x18003b845  mov     r8b, 1; CaseInsensitive
0x18003b848  lea     rsi, [rax+rcx*8]
0x18003b84c  mov     rdx, rsi; String2
0x18003b84f  lea     rcx, [rsp+68h+DestinationString]; String1
0x18003b854  call    cs:__imp_RtlCompareUnicodeString
0x18003b85a  test    eax, eax
0x18003b85c  jz      short loc_18003B862
0x18003b85e  inc     edi
0x18003b860  jmp     short loc_18003B838
0x18003b862  mov     [r14], rsi
0x18003b865  mov     [r15], rbx
0x18003b868  xor     ebx, ebx
0x18003b86a  xor     ecx, ecx; P
0x18003b86c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003b871  mov     eax, ebx
0x18003b873  jmp     short loc_18003B884
0x18003b875  mov     edi, 490h
0x18003b87a  mov     rcx, rbx; P
0x18003b87d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003b882  mov     eax, edi
0x18003b884  mov     rbx, [rsp+68h+arg_0]
0x18003b889  mov     rsi, [rsp+68h+arg_8]
0x18003b88e  add     rsp, 50h
0x18003b892  pop     r15
0x18003b894  pop     r14
0x18003b896  pop     rdi
0x18003b897  retn
```
