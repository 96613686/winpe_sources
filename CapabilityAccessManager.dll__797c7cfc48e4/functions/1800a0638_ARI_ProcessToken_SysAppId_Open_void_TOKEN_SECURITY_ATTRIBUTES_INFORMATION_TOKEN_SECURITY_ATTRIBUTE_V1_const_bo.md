# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800a0638`
- end: `0x1800a0788`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a04b0`

## callees

- `0x18000a0bc`
- `0x180037408`
- `0x1800a01b0`
- `0x1800a0638`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a0692`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a06f4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a0692`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800a06f4`
- `ntdll!RtlCompareUnicodeString` at `0x1800a0744`
- `ntdll!RtlCompareUnicodeString` at `0x1800a0744`
- `ntdll!NtQueryInformationToken` at `0x1800a0675`
- `ntdll!NtQueryInformationToken` at `0x1800a06e8`
- `ntdll!NtQueryInformationToken` at `0x1800a0675`
- `ntdll!NtQueryInformationToken` at `0x1800a06e8`
- `ntdll!RtlInitUnicodeString` at `0x1800a0718`
- `ntdll!RtlInitUnicodeString` at `0x1800a0718`

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
0x1800a0638  mov     rax, rsp
0x1800a063b  mov     [rax+8], rbx
0x1800a063f  mov     [rax+10h], rsi
0x1800a0643  mov     [rax+20h], r9
0x1800a0647  push    rdi
0x1800a0648  push    r14
0x1800a064a  push    r15
0x1800a064c  sub     rsp, 50h
0x1800a0650  xor     r9d, r9d; TokenInformationLength
0x1800a0653  mov     dword ptr [rax+20h], 0
0x1800a065a  mov     r14, r8
0x1800a065d  lea     rax, [rax+20h]
0x1800a0661  mov     r15, rdx
0x1800a0664  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a0669  xor     r8d, r8d; TokenInformation
0x1800a066c  mov     rdi, rcx
0x1800a066f  lea     esi, [r9+27h]
0x1800a0673  mov     edx, esi; TokenInformationClass
0x1800a0675  call    cs:__imp_NtQueryInformationToken
0x1800a067b  cmp     eax, 0C0000023h
0x1800a0680  jz      short loc_1800A069D
0x1800a0682  test    eax, eax
0x1800a0684  jnz     short loc_1800A0690
0x1800a0686  mov     eax, 54Fh
0x1800a068b  jmp     loc_1800A0774
0x1800a0690  mov     ecx, eax; Status
0x1800a0692  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a0698  jmp     loc_1800A0774
0x1800a069d  mov     ecx, dword ptr [rsp+68h+Size]
0x1800a06a4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800a06a9  mov     rbx, rax
0x1800a06ac  test    rax, rax
0x1800a06af  jnz     short loc_1800A06B9
0x1800a06b1  lea     ebx, [rax+8]
0x1800a06b4  jmp     loc_1800A075A
0x1800a06b9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800a06c1  xor     edx, edx; Val
0x1800a06c3  mov     rcx, rbx; void *
0x1800a06c6  call    memset_0
0x1800a06cb  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800a06d3  lea     rax, [rsp+68h+Size]
0x1800a06db  mov     r8, rbx; TokenInformation
0x1800a06de  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800a06e3  mov     edx, esi; TokenInformationClass
0x1800a06e5  mov     rcx, rdi; TokenHandle
0x1800a06e8  call    cs:__imp_NtQueryInformationToken
0x1800a06ee  test    eax, eax
0x1800a06f0  jns     short loc_1800A06FE
0x1800a06f2  mov     ecx, eax; Status
0x1800a06f4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800a06fa  mov     edi, eax
0x1800a06fc  jmp     short loc_1800A076A
0x1800a06fe  cmp     dword ptr [rbx+4], 0
0x1800a0702  jbe     short loc_1800A0765
0x1800a0704  xorps   xmm0, xmm0
0x1800a0707  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800a070e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800a0713  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800a0718  call    cs:__imp_RtlInitUnicodeString
0x1800a071e  xorps   xmm0, xmm0
0x1800a0721  xor     edi, edi
0x1800a0723  movups  [rsp+68h+var_28], xmm0
0x1800a0728  cmp     edi, [rbx+4]
0x1800a072b  jnb     short loc_1800A0765
0x1800a072d  mov     rax, [rbx+8]
0x1800a0731  lea     rcx, [rdi+rdi*4]
0x1800a0735  mov     r8b, 1; CaseInsensitive
0x1800a0738  lea     rsi, [rax+rcx*8]
0x1800a073c  mov     rdx, rsi; String2
0x1800a073f  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800a0744  call    cs:__imp_RtlCompareUnicodeString
0x1800a074a  test    eax, eax
0x1800a074c  jz      short loc_1800A0752
0x1800a074e  inc     edi
0x1800a0750  jmp     short loc_1800A0728
0x1800a0752  mov     [r14], rsi
0x1800a0755  mov     [r15], rbx
0x1800a0758  xor     ebx, ebx
0x1800a075a  xor     ecx, ecx; P
0x1800a075c  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a0761  mov     eax, ebx
0x1800a0763  jmp     short loc_1800A0774
0x1800a0765  mov     edi, 490h
0x1800a076a  mov     rcx, rbx; P
0x1800a076d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800a0772  mov     eax, edi
0x1800a0774  mov     rbx, [rsp+68h+arg_0]
0x1800a0779  mov     rsi, [rsp+68h+arg_8]
0x1800a077e  add     rsp, 50h
0x1800a0782  pop     r15
0x1800a0784  pop     r14
0x1800a0786  pop     rdi
0x1800a0787  retn
```
