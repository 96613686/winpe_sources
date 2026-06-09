# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18003c030`
- end: `0x18003c185`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003bc44`

## callees

- `0x18003c030`
- `0x18003c18c`
- `0x18003c1e8`
- `0x1800aa5ac`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18003c06d`
- `ntdll!NtQueryInformationToken` at `0x18003c0c5`
- `ntdll!NtQueryInformationToken` at `0x18003c06d`
- `ntdll!NtQueryInformationToken` at `0x18003c0c5`
- `ntdll!RtlInitUnicodeString` at `0x18003c0ed`
- `ntdll!RtlInitUnicodeString` at `0x18003c0ed`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c166`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c17d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c166`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003c17d`
- `ntdll!RtlCompareUnicodeString` at `0x18003c119`
- `ntdll!RtlCompareUnicodeString` at `0x18003c119`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  void *v8; // rax
  void *v9; // rdx
  void *v10; // rbx
  int v11; // eax
  __int64 v12; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v13; // rsi
  int v14; // ebx
  ULONG v16; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v8 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v10 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 < 0 )
      {
        v16 = RtlNtStatusToDosErrorNoTeb(v11);
      }
      else
      {
        if ( *((_DWORD *)v10 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v12 = 0;
          v18 = 0;
          while ( (unsigned int)v12 < *((_DWORD *)v10 + 1) )
          {
            v13 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*((_QWORD *)v10 + 1) + 40 * v12);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v13, 1u) )
            {
              *a3 = v13;
              *a2 = v10;
              v14 = 0;
              goto LABEL_9;
            }
            v12 = (unsigned int)(v12 + 1);
          }
        }
        v16 = 1168;
      }
      ARI::Free(v10, v9);
      return v16;
    }
    else
    {
      v14 = 8;
LABEL_9:
      ARI::Free(0, v9);
      return v14;
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
0x18003c030  mov     rax, rsp
0x18003c033  mov     [rax+8], rbx
0x18003c037  mov     [rax+10h], rsi
0x18003c03b  mov     [rax+20h], r9
0x18003c03f  push    rdi
0x18003c040  push    r14
0x18003c042  push    r15
0x18003c044  sub     rsp, 50h
0x18003c048  xor     r9d, r9d; TokenInformationLength
0x18003c04b  mov     dword ptr [rax+20h], 0
0x18003c052  mov     r14, r8
0x18003c055  lea     rax, [rax+20h]
0x18003c059  mov     r15, rdx
0x18003c05c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003c061  xor     r8d, r8d; TokenInformation
0x18003c064  mov     rdi, rcx
0x18003c067  lea     esi, [r9+27h]
0x18003c06b  mov     edx, esi; TokenInformationClass
0x18003c06d  call    cs:__imp_NtQueryInformationToken
0x18003c073  cmp     eax, 0C0000023h
0x18003c078  jnz     loc_18003C170
0x18003c07e  mov     ecx, dword ptr [rsp+68h+Size]
0x18003c085  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18003c08a  mov     rbx, rax
0x18003c08d  test    rax, rax
0x18003c090  jz      loc_18003C15D
0x18003c096  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18003c09e  xor     edx, edx; Val
0x18003c0a0  mov     rcx, rax; void *
0x18003c0a3  call    memset_0
0x18003c0a8  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18003c0b0  lea     rax, [rsp+68h+Size]
0x18003c0b8  mov     r8, rbx; TokenInformation
0x18003c0bb  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18003c0c0  mov     edx, esi; TokenInformationClass
0x18003c0c2  mov     rcx, rdi; TokenHandle
0x18003c0c5  call    cs:__imp_NtQueryInformationToken
0x18003c0cb  test    eax, eax
0x18003c0cd  js      loc_18003C164
0x18003c0d3  cmp     dword ptr [rbx+4], 0
0x18003c0d7  jbe     short loc_18003C148
0x18003c0d9  xorps   xmm0, xmm0
0x18003c0dc  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x18003c0e3  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18003c0e8  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18003c0ed  call    cs:__imp_RtlInitUnicodeString
0x18003c0f3  xorps   xmm0, xmm0
0x18003c0f6  xor     edi, edi
0x18003c0f8  movups  [rsp+68h+var_28], xmm0
0x18003c0fd  cmp     edi, [rbx+4]
0x18003c100  jnb     short loc_18003C148
0x18003c102  mov     rax, [rbx+8]
0x18003c106  lea     rcx, [rdi+rdi*4]
0x18003c10a  mov     r8b, 1; CaseInsensitive
0x18003c10d  lea     rsi, [rax+rcx*8]
0x18003c111  mov     rdx, rsi; String2
0x18003c114  lea     rcx, [rsp+68h+DestinationString]; String1
0x18003c119  call    cs:__imp_RtlCompareUnicodeString
0x18003c11f  test    eax, eax
0x18003c121  jnz     short loc_18003C159
0x18003c123  mov     [r14], rsi
0x18003c126  mov     [r15], rbx
0x18003c129  xor     ebx, ebx
0x18003c12b  xor     ecx, ecx; P
0x18003c12d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003c132  mov     eax, ebx
0x18003c134  mov     rbx, [rsp+68h+arg_0]
0x18003c139  mov     rsi, [rsp+68h+arg_8]
0x18003c13e  add     rsp, 50h
0x18003c142  pop     r15
0x18003c144  pop     r14
0x18003c146  pop     rdi
0x18003c147  retn
0x18003c148  mov     edi, 490h
0x18003c14d  mov     rcx, rbx; P
0x18003c150  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18003c155  mov     eax, edi
0x18003c157  jmp     short loc_18003C134
0x18003c159  inc     edi
0x18003c15b  jmp     short loc_18003C0FD
0x18003c15d  mov     ebx, 8
0x18003c162  jmp     short loc_18003C12B
0x18003c164  mov     ecx, eax; Status
0x18003c166  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c16c  mov     edi, eax
0x18003c16e  jmp     short loc_18003C14D
0x18003c170  test    eax, eax
0x18003c172  jnz     short loc_18003C17B
0x18003c174  mov     eax, 54Fh
0x18003c179  jmp     short loc_18003C134
0x18003c17b  mov     ecx, eax; Status
0x18003c17d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18003c183  jmp     short loc_18003C134
```
