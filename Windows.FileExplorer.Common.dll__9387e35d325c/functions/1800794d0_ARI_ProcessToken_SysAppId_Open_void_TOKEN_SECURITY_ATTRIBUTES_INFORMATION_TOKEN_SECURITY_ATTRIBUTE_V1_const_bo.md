# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800794d0`
- end: `0x180079620`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180079314`

## callees

- `0x180038708`
- `0x180078f40`
- `0x180078fc0`
- `0x1800794d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800795b0`
- `ntdll!RtlInitUnicodeString` at `0x1800795b0`
- `ntdll!RtlCompareUnicodeString` at `0x1800795dc`
- `ntdll!RtlCompareUnicodeString` at `0x1800795dc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007952a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007958c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007952a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18007958c`
- `ntdll!NtQueryInformationToken` at `0x18007950d`
- `ntdll!NtQueryInformationToken` at `0x180079580`
- `ntdll!NtQueryInformationToken` at `0x18007950d`
- `ntdll!NtQueryInformationToken` at `0x180079580`

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
0x1800794d0  mov     rax, rsp
0x1800794d3  mov     [rax+8], rbx
0x1800794d7  mov     [rax+10h], rsi
0x1800794db  mov     [rax+20h], r9
0x1800794df  push    rdi
0x1800794e0  push    r14
0x1800794e2  push    r15
0x1800794e4  sub     rsp, 50h
0x1800794e8  xor     r9d, r9d; TokenInformationLength
0x1800794eb  mov     dword ptr [rax+20h], 0
0x1800794f2  mov     r14, r8
0x1800794f5  lea     rax, [rax+20h]
0x1800794f9  mov     r15, rdx
0x1800794fc  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180079501  xor     r8d, r8d; TokenInformation
0x180079504  mov     rdi, rcx
0x180079507  lea     esi, [r9+27h]
0x18007950b  mov     edx, esi; TokenInformationClass
0x18007950d  call    cs:__imp_NtQueryInformationToken
0x180079513  cmp     eax, 0C0000023h
0x180079518  jz      short loc_180079535
0x18007951a  test    eax, eax
0x18007951c  jnz     short loc_180079528
0x18007951e  mov     eax, 54Fh
0x180079523  jmp     loc_18007960C
0x180079528  mov     ecx, eax; Status
0x18007952a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180079530  jmp     loc_18007960C
0x180079535  mov     ecx, dword ptr [rsp+68h+Size]
0x18007953c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180079541  mov     rbx, rax
0x180079544  test    rax, rax
0x180079547  jnz     short loc_180079551
0x180079549  lea     ebx, [rax+8]
0x18007954c  jmp     loc_1800795F2
0x180079551  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180079559  xor     edx, edx; Val
0x18007955b  mov     rcx, rbx; void *
0x18007955e  call    memset_0
0x180079563  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18007956b  lea     rax, [rsp+68h+Size]
0x180079573  mov     r8, rbx; TokenInformation
0x180079576  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18007957b  mov     edx, esi; TokenInformationClass
0x18007957d  mov     rcx, rdi; TokenHandle
0x180079580  call    cs:__imp_NtQueryInformationToken
0x180079586  test    eax, eax
0x180079588  jns     short loc_180079596
0x18007958a  mov     ecx, eax; Status
0x18007958c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180079592  mov     edi, eax
0x180079594  jmp     short loc_180079602
0x180079596  cmp     dword ptr [rbx+4], 0
0x18007959a  jbe     short loc_1800795FD
0x18007959c  xorps   xmm0, xmm0
0x18007959f  lea     rdx, SourceString; "WIN://SYSAPPID"
0x1800795a6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800795ab  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800795b0  call    cs:__imp_RtlInitUnicodeString
0x1800795b6  xorps   xmm0, xmm0
0x1800795b9  xor     edi, edi
0x1800795bb  movups  [rsp+68h+var_28], xmm0
0x1800795c0  cmp     edi, [rbx+4]
0x1800795c3  jnb     short loc_1800795FD
0x1800795c5  mov     rax, [rbx+8]
0x1800795c9  lea     rcx, [rdi+rdi*4]
0x1800795cd  mov     r8b, 1; CaseInsensitive
0x1800795d0  lea     rsi, [rax+rcx*8]
0x1800795d4  mov     rdx, rsi; String2
0x1800795d7  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800795dc  call    cs:__imp_RtlCompareUnicodeString
0x1800795e2  test    eax, eax
0x1800795e4  jz      short loc_1800795EA
0x1800795e6  inc     edi
0x1800795e8  jmp     short loc_1800795C0
0x1800795ea  mov     [r14], rsi
0x1800795ed  mov     [r15], rbx
0x1800795f0  xor     ebx, ebx
0x1800795f2  xor     ecx, ecx; P
0x1800795f4  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800795f9  mov     eax, ebx
0x1800795fb  jmp     short loc_18007960C
0x1800795fd  mov     edi, 490h
0x180079602  mov     rcx, rbx; P
0x180079605  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18007960a  mov     eax, edi
0x18007960c  mov     rbx, [rsp+68h+arg_0]
0x180079611  mov     rsi, [rsp+68h+arg_8]
0x180079616  add     rsp, 50h
0x18007961a  pop     r15
0x18007961c  pop     r14
0x18007961e  pop     rdi
0x18007961f  retn
```
