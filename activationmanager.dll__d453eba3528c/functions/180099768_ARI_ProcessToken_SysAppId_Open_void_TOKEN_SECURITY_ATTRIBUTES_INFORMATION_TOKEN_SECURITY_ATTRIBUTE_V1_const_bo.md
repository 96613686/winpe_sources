# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180099768`
- end: `0x1800998b8`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800995dc`

## callees

- `0x18005ba40`
- `0x1800993cc`
- `0x18009944c`
- `0x180099768`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800997a5`
- `ntdll!NtQueryInformationToken` at `0x180099818`
- `ntdll!NtQueryInformationToken` at `0x1800997a5`
- `ntdll!NtQueryInformationToken` at `0x180099818`
- `ntdll!RtlInitUnicodeString` at `0x180099848`
- `ntdll!RtlInitUnicodeString` at `0x180099848`
- `ntdll!RtlCompareUnicodeString` at `0x180099874`
- `ntdll!RtlCompareUnicodeString` at `0x180099874`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800997c2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180099824`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800997c2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180099824`

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
0x180099768  mov     rax, rsp
0x18009976b  mov     [rax+8], rbx
0x18009976f  mov     [rax+10h], rsi
0x180099773  mov     [rax+20h], r9
0x180099777  push    rdi
0x180099778  push    r14
0x18009977a  push    r15
0x18009977c  sub     rsp, 50h
0x180099780  xor     r9d, r9d; TokenInformationLength
0x180099783  mov     dword ptr [rax+20h], 0
0x18009978a  mov     r14, r8
0x18009978d  lea     rax, [rax+20h]
0x180099791  mov     r15, rdx
0x180099794  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180099799  xor     r8d, r8d; TokenInformation
0x18009979c  mov     rdi, rcx
0x18009979f  lea     esi, [r9+27h]
0x1800997a3  mov     edx, esi; TokenInformationClass
0x1800997a5  call    cs:__imp_NtQueryInformationToken
0x1800997ab  cmp     eax, 0C0000023h
0x1800997b0  jz      short loc_1800997CD
0x1800997b2  test    eax, eax
0x1800997b4  jnz     short loc_1800997C0
0x1800997b6  mov     eax, 54Fh
0x1800997bb  jmp     loc_1800998A4
0x1800997c0  mov     ecx, eax; Status
0x1800997c2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800997c8  jmp     loc_1800998A4
0x1800997cd  mov     ecx, dword ptr [rsp+68h+Size]
0x1800997d4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800997d9  mov     rbx, rax
0x1800997dc  test    rax, rax
0x1800997df  jnz     short loc_1800997E9
0x1800997e1  lea     ebx, [rax+8]
0x1800997e4  jmp     loc_18009988A
0x1800997e9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800997f1  xor     edx, edx; Val
0x1800997f3  mov     rcx, rbx; void *
0x1800997f6  call    memset_0
0x1800997fb  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180099803  lea     rax, [rsp+68h+Size]
0x18009980b  mov     r8, rbx; TokenInformation
0x18009980e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180099813  mov     edx, esi; TokenInformationClass
0x180099815  mov     rcx, rdi; TokenHandle
0x180099818  call    cs:__imp_NtQueryInformationToken
0x18009981e  test    eax, eax
0x180099820  jns     short loc_18009982E
0x180099822  mov     ecx, eax; Status
0x180099824  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18009982a  mov     edi, eax
0x18009982c  jmp     short loc_18009989A
0x18009982e  cmp     dword ptr [rbx+4], 0
0x180099832  jbe     short loc_180099895
0x180099834  xorps   xmm0, xmm0
0x180099837  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x18009983e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180099843  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180099848  call    cs:__imp_RtlInitUnicodeString
0x18009984e  xorps   xmm0, xmm0
0x180099851  xor     edi, edi
0x180099853  movups  [rsp+68h+var_28], xmm0
0x180099858  cmp     edi, [rbx+4]
0x18009985b  jnb     short loc_180099895
0x18009985d  mov     rax, [rbx+8]
0x180099861  lea     rcx, [rdi+rdi*4]
0x180099865  mov     r8b, 1; CaseInsensitive
0x180099868  lea     rsi, [rax+rcx*8]
0x18009986c  mov     rdx, rsi; String2
0x18009986f  lea     rcx, [rsp+68h+DestinationString]; String1
0x180099874  call    cs:__imp_RtlCompareUnicodeString
0x18009987a  test    eax, eax
0x18009987c  jz      short loc_180099882
0x18009987e  inc     edi
0x180099880  jmp     short loc_180099858
0x180099882  mov     [r14], rsi
0x180099885  mov     [r15], rbx
0x180099888  xor     ebx, ebx
0x18009988a  xor     ecx, ecx; P
0x18009988c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180099891  mov     eax, ebx
0x180099893  jmp     short loc_1800998A4
0x180099895  mov     edi, 490h
0x18009989a  mov     rcx, rbx; P
0x18009989d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800998a2  mov     eax, edi
0x1800998a4  mov     rbx, [rsp+68h+arg_0]
0x1800998a9  mov     rsi, [rsp+68h+arg_8]
0x1800998ae  add     rsp, 50h
0x1800998b2  pop     r15
0x1800998b4  pop     r14
0x1800998b6  pop     rdi
0x1800998b7  retn
```
