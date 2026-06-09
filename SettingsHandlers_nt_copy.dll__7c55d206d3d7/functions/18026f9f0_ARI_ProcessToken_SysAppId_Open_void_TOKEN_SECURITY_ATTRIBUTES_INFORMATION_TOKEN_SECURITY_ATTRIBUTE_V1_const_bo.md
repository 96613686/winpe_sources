# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x18026f9f0`
- end: `0x18026fb65`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18026f854`

## callees

- `0x18000d44c`
- `0x18026f4fc`
- `0x18026f5a8`
- `0x18026f9f0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18026fb1a`
- `ntdll!RtlCompareUnicodeString` at `0x18026fb1a`
- `ntdll!NtQueryInformationToken` at `0x18026fa2d`
- `ntdll!NtQueryInformationToken` at `0x18026faac`
- `ntdll!NtQueryInformationToken` at `0x18026fa2d`
- `ntdll!NtQueryInformationToken` at `0x18026faac`
- `ntdll!RtlInitUnicodeString` at `0x18026fae8`
- `ntdll!RtlInitUnicodeString` at `0x18026fae8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18026fa50`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18026fabe`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18026fa50`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18026fabe`

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
0x18026f9f0  mov     rax, rsp
0x18026f9f3  mov     [rax+8], rbx
0x18026f9f7  mov     [rax+10h], rsi
0x18026f9fb  mov     [rax+20h], r9
0x18026f9ff  push    rdi
0x18026fa00  push    r14
0x18026fa02  push    r15
0x18026fa04  sub     rsp, 50h
0x18026fa08  xor     r9d, r9d; TokenInformationLength
0x18026fa0b  mov     dword ptr [rax+20h], 0
0x18026fa12  mov     r14, r8
0x18026fa15  lea     rax, [rax+20h]
0x18026fa19  mov     r15, rdx
0x18026fa1c  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18026fa21  xor     r8d, r8d; TokenInformation
0x18026fa24  mov     rdi, rcx
0x18026fa27  lea     esi, [r9+27h]
0x18026fa2b  mov     edx, esi; TokenInformationClass
0x18026fa2d  call    cs:__imp_NtQueryInformationToken
0x18026fa34  nop     dword ptr [rax+rax+00h]
0x18026fa39  cmp     eax, 0C0000023h
0x18026fa3e  jz      short loc_18026FA61
0x18026fa40  test    eax, eax
0x18026fa42  jnz     short loc_18026FA4E
0x18026fa44  mov     eax, 54Fh
0x18026fa49  jmp     loc_18026FB50
0x18026fa4e  mov     ecx, eax; Status
0x18026fa50  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18026fa57  nop     dword ptr [rax+rax+00h]
0x18026fa5c  jmp     loc_18026FB50
0x18026fa61  mov     ecx, dword ptr [rsp+68h+Size]
0x18026fa68  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x18026fa6d  mov     rbx, rax
0x18026fa70  test    rax, rax
0x18026fa73  jnz     short loc_18026FA7D
0x18026fa75  lea     ebx, [rax+8]
0x18026fa78  jmp     loc_18026FB36
0x18026fa7d  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x18026fa85  xor     edx, edx; Val
0x18026fa87  mov     rcx, rbx; void *
0x18026fa8a  call    memset_0
0x18026fa8f  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x18026fa97  lea     rax, [rsp+68h+Size]
0x18026fa9f  mov     r8, rbx; TokenInformation
0x18026faa2  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18026faa7  mov     edx, esi; TokenInformationClass
0x18026faa9  mov     rcx, rdi; TokenHandle
0x18026faac  call    cs:__imp_NtQueryInformationToken
0x18026fab3  nop     dword ptr [rax+rax+00h]
0x18026fab8  test    eax, eax
0x18026faba  jns     short loc_18026FACE
0x18026fabc  mov     ecx, eax; Status
0x18026fabe  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18026fac5  nop     dword ptr [rax+rax+00h]
0x18026faca  mov     edi, eax
0x18026facc  jmp     short loc_18026FB46
0x18026face  cmp     dword ptr [rbx+4], 0
0x18026fad2  jbe     short loc_18026FB41
0x18026fad4  xorps   xmm0, xmm0
0x18026fad7  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18026fade  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18026fae3  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18026fae8  call    cs:__imp_RtlInitUnicodeString
0x18026faef  nop     dword ptr [rax+rax+00h]
0x18026faf4  xorps   xmm0, xmm0
0x18026faf7  xor     edi, edi
0x18026faf9  movups  [rsp+68h+var_28], xmm0
0x18026fafe  cmp     edi, [rbx+4]
0x18026fb01  jnb     short loc_18026FB41
0x18026fb03  mov     rax, [rbx+8]
0x18026fb07  lea     rcx, [rdi+rdi*4]
0x18026fb0b  mov     r8b, 1; CaseInsensitive
0x18026fb0e  lea     rsi, [rax+rcx*8]
0x18026fb12  mov     rdx, rsi; String2
0x18026fb15  lea     rcx, [rsp+68h+DestinationString]; String1
0x18026fb1a  call    cs:__imp_RtlCompareUnicodeString
0x18026fb21  nop     dword ptr [rax+rax+00h]
0x18026fb26  test    eax, eax
0x18026fb28  jz      short loc_18026FB2E
0x18026fb2a  inc     edi
0x18026fb2c  jmp     short loc_18026FAFE
0x18026fb2e  mov     [r14], rsi
0x18026fb31  mov     [r15], rbx
0x18026fb34  xor     ebx, ebx
0x18026fb36  xor     ecx, ecx; P
0x18026fb38  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18026fb3d  mov     eax, ebx
0x18026fb3f  jmp     short loc_18026FB50
0x18026fb41  mov     edi, 490h
0x18026fb46  mov     rcx, rbx; P
0x18026fb49  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18026fb4e  mov     eax, edi
0x18026fb50  mov     rbx, [rsp+68h+arg_0]
0x18026fb55  mov     rsi, [rsp+68h+arg_8]
0x18026fb5a  add     rsp, 50h
0x18026fb5e  pop     r15
0x18026fb60  pop     r14
0x18026fb62  pop     rdi
0x18026fb63  retn
```
