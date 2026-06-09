# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18002ae5c`
- end: `0x18002afac`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ac50`
- `0x18005cdb8`

## callees

- `0x18002ae5c`
- `0x18002d1c8`
- `0x18005caa8`
- `0x18005cb90`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002ae99`
- `ntdll!NtQueryInformationToken` at `0x18002af0c`
- `ntdll!NtQueryInformationToken` at `0x18002ae99`
- `ntdll!NtQueryInformationToken` at `0x18002af0c`
- `ntdll!RtlInitUnicodeString` at `0x18002af3c`
- `ntdll!RtlInitUnicodeString` at `0x18002af3c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002aeb6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002af18`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002aeb6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18002af18`
- `ntdll!RtlCompareUnicodeString` at `0x18002af68`
- `ntdll!RtlCompareUnicodeString` at `0x18002af68`

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
0x18002ae5c  mov     rax, rsp
0x18002ae5f  mov     [rax+8], rbx
0x18002ae63  mov     [rax+10h], rsi
0x18002ae67  mov     [rax+20h], r9
0x18002ae6b  push    rdi
0x18002ae6c  push    r14
0x18002ae6e  push    r15
0x18002ae70  sub     rsp, 50h
0x18002ae74  xor     r9d, r9d; TokenInformationLength
0x18002ae77  mov     dword ptr [rax+20h], 0
0x18002ae7e  mov     r14, r8
0x18002ae81  lea     rax, [rax+20h]
0x18002ae85  mov     r15, rdx
0x18002ae88  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002ae8d  xor     r8d, r8d; TokenInformation
0x18002ae90  mov     rdi, rcx
0x18002ae93  lea     esi, [r9+27h]
0x18002ae97  mov     edx, esi; TokenInformationClass
0x18002ae99  call    cs:__imp_NtQueryInformationToken
0x18002ae9f  cmp     eax, 0C0000023h
0x18002aea4  jz      short loc_18002AEC1
0x18002aea6  test    eax, eax
0x18002aea8  jnz     short loc_18002AEB4
0x18002aeaa  mov     eax, 54Fh
0x18002aeaf  jmp     loc_18002AF98
0x18002aeb4  mov     ecx, eax; Status
0x18002aeb6  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18002aebc  jmp     loc_18002AF98
0x18002aec1  mov     ecx, dword ptr [rsp+68h+Size]
0x18002aec8  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18002aecd  mov     rbx, rax
0x18002aed0  test    rax, rax
0x18002aed3  jnz     short loc_18002AEDD
0x18002aed5  lea     ebx, [rax+8]
0x18002aed8  jmp     loc_18002AF7E
0x18002aedd  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18002aee5  xor     edx, edx; Val
0x18002aee7  mov     rcx, rbx; void *
0x18002aeea  call    memset_0
0x18002aeef  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18002aef7  lea     rax, [rsp+68h+Size]
0x18002aeff  mov     r8, rbx; TokenInformation
0x18002af02  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18002af07  mov     edx, esi; TokenInformationClass
0x18002af09  mov     rcx, rdi; TokenHandle
0x18002af0c  call    cs:__imp_NtQueryInformationToken
0x18002af12  test    eax, eax
0x18002af14  jns     short loc_18002AF22
0x18002af16  mov     ecx, eax; Status
0x18002af18  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18002af1e  mov     edi, eax
0x18002af20  jmp     short loc_18002AF8E
0x18002af22  cmp     dword ptr [rbx+4], 0
0x18002af26  jbe     short loc_18002AF89
0x18002af28  xorps   xmm0, xmm0
0x18002af2b  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18002af32  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002af37  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18002af3c  call    cs:__imp_RtlInitUnicodeString
0x18002af42  xorps   xmm0, xmm0
0x18002af45  xor     edi, edi
0x18002af47  movups  [rsp+68h+var_28], xmm0
0x18002af4c  cmp     edi, [rbx+4]
0x18002af4f  jnb     short loc_18002AF89
0x18002af51  mov     rax, [rbx+8]
0x18002af55  lea     rcx, [rdi+rdi*4]
0x18002af59  mov     r8b, 1; CaseInsensitive
0x18002af5c  lea     rsi, [rax+rcx*8]
0x18002af60  mov     rdx, rsi; String2
0x18002af63  lea     rcx, [rsp+68h+DestinationString]; String1
0x18002af68  call    cs:__imp_RtlCompareUnicodeString
0x18002af6e  test    eax, eax
0x18002af70  jz      short loc_18002AF76
0x18002af72  inc     edi
0x18002af74  jmp     short loc_18002AF4C
0x18002af76  mov     [r14], rsi
0x18002af79  mov     [r15], rbx
0x18002af7c  xor     ebx, ebx
0x18002af7e  xor     ecx, ecx; P
0x18002af80  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18002af85  mov     eax, ebx
0x18002af87  jmp     short loc_18002AF98
0x18002af89  mov     edi, 490h
0x18002af8e  mov     rcx, rbx; P
0x18002af91  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18002af96  mov     eax, edi
0x18002af98  mov     rbx, [rsp+68h+arg_0]
0x18002af9d  mov     rsi, [rsp+68h+arg_8]
0x18002afa2  add     rsp, 50h
0x18002afa6  pop     r15
0x18002afa8  pop     r14
0x18002afaa  pop     rdi
0x18002afab  retn
```
