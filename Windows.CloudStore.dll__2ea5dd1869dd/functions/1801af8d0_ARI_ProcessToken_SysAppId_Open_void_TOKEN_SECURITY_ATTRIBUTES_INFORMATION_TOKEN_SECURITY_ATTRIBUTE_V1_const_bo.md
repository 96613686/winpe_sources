# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1801af8d0`
- end: `0x1801afa20`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801af740`

## callees

- `0x180120c94`
- `0x1801af410`
- `0x1801af510`
- `0x1801af8d0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1801af9dc`
- `ntdll!RtlCompareUnicodeString` at `0x1801af9dc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801af92a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801af98c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801af92a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801af98c`
- `ntdll!RtlInitUnicodeString` at `0x1801af9b0`
- `ntdll!RtlInitUnicodeString` at `0x1801af9b0`
- `ntdll!NtQueryInformationToken` at `0x1801af90d`
- `ntdll!NtQueryInformationToken` at `0x1801af980`
- `ntdll!NtQueryInformationToken` at `0x1801af90d`
- `ntdll!NtQueryInformationToken` at `0x1801af980`

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
0x1801af8d0  mov     rax, rsp
0x1801af8d3  mov     [rax+8], rbx
0x1801af8d7  mov     [rax+10h], rsi
0x1801af8db  mov     [rax+20h], r9
0x1801af8df  push    rdi
0x1801af8e0  push    r14
0x1801af8e2  push    r15
0x1801af8e4  sub     rsp, 50h
0x1801af8e8  xor     r9d, r9d; TokenInformationLength
0x1801af8eb  mov     dword ptr [rax+20h], 0
0x1801af8f2  mov     r14, r8
0x1801af8f5  lea     rax, [rax+20h]
0x1801af8f9  mov     r15, rdx
0x1801af8fc  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1801af901  xor     r8d, r8d; TokenInformation
0x1801af904  mov     rdi, rcx
0x1801af907  lea     esi, [r9+27h]
0x1801af90b  mov     edx, esi; TokenInformationClass
0x1801af90d  call    cs:__imp_NtQueryInformationToken
0x1801af913  cmp     eax, 0C0000023h
0x1801af918  jz      short loc_1801AF935
0x1801af91a  test    eax, eax
0x1801af91c  jnz     short loc_1801AF928
0x1801af91e  mov     eax, 54Fh
0x1801af923  jmp     loc_1801AFA0C
0x1801af928  mov     ecx, eax; Status
0x1801af92a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1801af930  jmp     loc_1801AFA0C
0x1801af935  mov     ecx, dword ptr [rsp+68h+Size]
0x1801af93c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1801af941  mov     rbx, rax
0x1801af944  test    rax, rax
0x1801af947  jnz     short loc_1801AF951
0x1801af949  lea     ebx, [rax+8]
0x1801af94c  jmp     loc_1801AF9F2
0x1801af951  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1801af959  xor     edx, edx; Val
0x1801af95b  mov     rcx, rbx; void *
0x1801af95e  call    memset_0
0x1801af963  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1801af96b  lea     rax, [rsp+68h+Size]
0x1801af973  mov     r8, rbx; TokenInformation
0x1801af976  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1801af97b  mov     edx, esi; TokenInformationClass
0x1801af97d  mov     rcx, rdi; TokenHandle
0x1801af980  call    cs:__imp_NtQueryInformationToken
0x1801af986  test    eax, eax
0x1801af988  jns     short loc_1801AF996
0x1801af98a  mov     ecx, eax; Status
0x1801af98c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1801af992  mov     edi, eax
0x1801af994  jmp     short loc_1801AFA02
0x1801af996  cmp     dword ptr [rbx+4], 0
0x1801af99a  jbe     short loc_1801AF9FD
0x1801af99c  xorps   xmm0, xmm0
0x1801af99f  lea     rdx, SourceString; "WIN://SYSAPPID"
0x1801af9a6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1801af9ab  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1801af9b0  call    cs:__imp_RtlInitUnicodeString
0x1801af9b6  xorps   xmm0, xmm0
0x1801af9b9  xor     edi, edi
0x1801af9bb  movups  [rsp+68h+var_28], xmm0
0x1801af9c0  cmp     edi, [rbx+4]
0x1801af9c3  jnb     short loc_1801AF9FD
0x1801af9c5  mov     rax, [rbx+8]
0x1801af9c9  lea     rcx, [rdi+rdi*4]
0x1801af9cd  mov     r8b, 1; CaseInsensitive
0x1801af9d0  lea     rsi, [rax+rcx*8]
0x1801af9d4  mov     rdx, rsi; String2
0x1801af9d7  lea     rcx, [rsp+68h+DestinationString]; String1
0x1801af9dc  call    cs:__imp_RtlCompareUnicodeString
0x1801af9e2  test    eax, eax
0x1801af9e4  jz      short loc_1801AF9EA
0x1801af9e6  inc     edi
0x1801af9e8  jmp     short loc_1801AF9C0
0x1801af9ea  mov     [r14], rsi
0x1801af9ed  mov     [r15], rbx
0x1801af9f0  xor     ebx, ebx
0x1801af9f2  xor     ecx, ecx; P
0x1801af9f4  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1801af9f9  mov     eax, ebx
0x1801af9fb  jmp     short loc_1801AFA0C
0x1801af9fd  mov     edi, 490h
0x1801afa02  mov     rcx, rbx; P
0x1801afa05  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1801afa0a  mov     eax, edi
0x1801afa0c  mov     rbx, [rsp+68h+arg_0]
0x1801afa11  mov     rsi, [rsp+68h+arg_8]
0x1801afa16  add     rsp, 50h
0x1801afa1a  pop     r15
0x1801afa1c  pop     r14
0x1801afa1e  pop     rdi
0x1801afa1f  retn
```
