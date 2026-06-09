# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18003e100`
- end: `0x18003e250`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003df54`

## callees

- `0x1800030b6`
- `0x18003db14`
- `0x18003dbf8`
- `0x18003e100`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18003e20c`
- `ntdll!RtlCompareUnicodeString` at `0x18003e20c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e15a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e1bc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e15a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003e1bc`
- `ntdll!RtlInitUnicodeString` at `0x18003e1e0`
- `ntdll!RtlInitUnicodeString` at `0x18003e1e0`
- `ntdll!NtQueryInformationToken` at `0x18003e13d`
- `ntdll!NtQueryInformationToken` at `0x18003e1b0`
- `ntdll!NtQueryInformationToken` at `0x18003e13d`
- `ntdll!NtQueryInformationToken` at `0x18003e1b0`

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
0x18003e100  mov     rax, rsp
0x18003e103  mov     [rax+8], rbx
0x18003e107  mov     [rax+10h], rsi
0x18003e10b  mov     [rax+20h], r9
0x18003e10f  push    rdi
0x18003e110  push    r14
0x18003e112  push    r15
0x18003e114  sub     rsp, 50h
0x18003e118  xor     r9d, r9d; TokenInformationLength
0x18003e11b  mov     dword ptr [rax+20h], 0
0x18003e122  mov     r14, r8
0x18003e125  lea     rax, [rax+20h]
0x18003e129  mov     r15, rdx
0x18003e12c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003e131  xor     r8d, r8d; TokenInformation
0x18003e134  mov     rdi, rcx
0x18003e137  lea     esi, [r9+27h]
0x18003e13b  mov     edx, esi; TokenInformationClass
0x18003e13d  call    cs:__imp_NtQueryInformationToken
0x18003e143  cmp     eax, 0C0000023h
0x18003e148  jz      short loc_18003E165
0x18003e14a  test    eax, eax
0x18003e14c  jnz     short loc_18003E158
0x18003e14e  mov     eax, 54Fh
0x18003e153  jmp     loc_18003E23C
0x18003e158  mov     ecx, eax; Status
0x18003e15a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e160  jmp     loc_18003E23C
0x18003e165  mov     ecx, dword ptr [rsp+68h+Size]
0x18003e16c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18003e171  mov     rbx, rax
0x18003e174  test    rax, rax
0x18003e177  jnz     short loc_18003E181
0x18003e179  lea     ebx, [rax+8]
0x18003e17c  jmp     loc_18003E222
0x18003e181  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18003e189  xor     edx, edx; Val
0x18003e18b  mov     rcx, rbx; void *
0x18003e18e  call    memset_0
0x18003e193  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18003e19b  lea     rax, [rsp+68h+Size]
0x18003e1a3  mov     r8, rbx; TokenInformation
0x18003e1a6  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003e1ab  mov     edx, esi; TokenInformationClass
0x18003e1ad  mov     rcx, rdi; TokenHandle
0x18003e1b0  call    cs:__imp_NtQueryInformationToken
0x18003e1b6  test    eax, eax
0x18003e1b8  jns     short loc_18003E1C6
0x18003e1ba  mov     ecx, eax; Status
0x18003e1bc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003e1c2  mov     edi, eax
0x18003e1c4  jmp     short loc_18003E232
0x18003e1c6  cmp     dword ptr [rbx+4], 0
0x18003e1ca  jbe     short loc_18003E22D
0x18003e1cc  xorps   xmm0, xmm0
0x18003e1cf  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18003e1d6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18003e1db  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18003e1e0  call    cs:__imp_RtlInitUnicodeString
0x18003e1e6  xorps   xmm0, xmm0
0x18003e1e9  xor     edi, edi
0x18003e1eb  movups  [rsp+68h+var_28], xmm0
0x18003e1f0  cmp     edi, [rbx+4]
0x18003e1f3  jnb     short loc_18003E22D
0x18003e1f5  mov     rax, [rbx+8]
0x18003e1f9  lea     rcx, [rdi+rdi*4]
0x18003e1fd  mov     r8b, 1; CaseInsensitive
0x18003e200  lea     rsi, [rax+rcx*8]
0x18003e204  mov     rdx, rsi; String2
0x18003e207  lea     rcx, [rsp+68h+DestinationString]; String1
0x18003e20c  call    cs:__imp_RtlCompareUnicodeString
0x18003e212  test    eax, eax
0x18003e214  jz      short loc_18003E21A
0x18003e216  inc     edi
0x18003e218  jmp     short loc_18003E1F0
0x18003e21a  mov     [r14], rsi
0x18003e21d  mov     [r15], rbx
0x18003e220  xor     ebx, ebx
0x18003e222  xor     ecx, ecx; P
0x18003e224  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003e229  mov     eax, ebx
0x18003e22b  jmp     short loc_18003E23C
0x18003e22d  mov     edi, 490h
0x18003e232  mov     rcx, rbx; P
0x18003e235  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003e23a  mov     eax, edi
0x18003e23c  mov     rbx, [rsp+68h+arg_0]
0x18003e241  mov     rsi, [rsp+68h+arg_8]
0x18003e246  add     rsp, 50h
0x18003e24a  pop     r15
0x18003e24c  pop     r14
0x18003e24e  pop     rdi
0x18003e24f  retn
```
