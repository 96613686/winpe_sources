# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180006430`
- end: `0x1800065ba`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `394`
- prototype: `ULONG __fastcall(HANDLE TokenHandle, _QWORD *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005f14`

## callees

- `0x180006430`
- `0x1800065c0`
- `0x1800327f8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180006465`
- `ntdll!NtQueryInformationToken` at `0x1800064ec`
- `ntdll!NtQueryInformationToken` at `0x180006465`
- `ntdll!NtQueryInformationToken` at `0x1800064ec`
- `ntdll!RtlInitUnicodeString` at `0x180006513`
- `ntdll!RtlInitUnicodeString` at `0x180006513`
- `ntdll!RtlAllocateHeap` at `0x1800064a8`
- `ntdll!RtlAllocateHeap` at `0x1800064a8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006580`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800065a1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180006580`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800065a1`
- `ntdll!RtlCompareUnicodeString` at `0x180006541`
- `ntdll!RtlCompareUnicodeString` at `0x180006541`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  unsigned __int128 v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  void *v11; // rdx
  unsigned int v12; // edi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v13; // rsi
  ULONG v15; // edi
  void *v16; // rdx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v8 = Size * (unsigned __int128)0x10uLL;
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (*(_QWORD *)&v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * Size), (v9 = v8) != 0) )
    {
      memset_0((void *)v8, 0, Size);
      v10 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, (PVOID)v9, Size, &Size);
      if ( v10 < 0 )
      {
        v15 = RtlNtStatusToDosErrorNoTeb(v10);
        ARI::Free((PVOID)v9, v16);
        return v15;
      }
      else
      {
        if ( *(_DWORD *)(v9 + 4) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v12 = 0;
          v18 = 0;
          while ( v12 < *(_DWORD *)(v9 + 4) )
          {
            v13 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*(_QWORD *)(v9 + 8) + 40LL * v12);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v13, 1u) )
            {
              *a3 = v13;
              *a2 = v9;
              ARI::Free(0, v11);
              return 0;
            }
            ++v12;
          }
        }
        ARI::Free((PVOID)v9, v11);
        return 1168;
      }
    }
    else
    {
      ARI::Free(0, *((void **)&v8 + 1));
      return 8;
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
0x180006430  mov     rax, rsp
0x180006433  mov     [rax+10h], rsi
0x180006437  mov     [rax+20h], r9
0x18000643b  push    rdi
0x18000643c  push    r14
0x18000643e  push    r15
0x180006440  sub     rsp, 50h
0x180006444  lea     rax, [rax+20h]
0x180006448  mov     r14, r8
0x18000644b  mov     r15, rdx
0x18000644e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180006453  xor     esi, esi
0x180006455  xor     r9d, r9d; TokenInformationLength
0x180006458  mov     [rax], esi
0x18000645a  xor     r8d, r8d; TokenInformation
0x18000645d  mov     edx, 27h ; '''; TokenInformationClass
0x180006462  mov     rdi, rcx
0x180006465  call    cs:__imp_NtQueryInformationToken
0x18000646b  cmp     eax, 0C0000023h
0x180006470  jnz     loc_180006594
0x180006476  mov     ecx, dword ptr [rsp+68h+Size]
0x18000647d  mov     eax, 10h
0x180006482  mul     rcx
0x180006485  mov     [rsp+68h+arg_0], rbx
0x18000648a  mov     qword ptr [rsp+68h+DestinationString.Length], rsi
0x18000648f  test    rdx, rdx
0x180006492  jnz     loc_180006570
0x180006498  mov     rcx, gs:60h
0x1800064a1  mov     r8, rax; Size
0x1800064a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800064a8  call    cs:__imp_RtlAllocateHeap
0x1800064ae  mov     rbx, rax
0x1800064b1  test    rax, rax
0x1800064b4  jz      loc_180006570
0x1800064ba  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800064c2  xor     edx, edx; Val
0x1800064c4  mov     rcx, rax; void *
0x1800064c7  call    memset_0
0x1800064cc  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800064d4  lea     rax, [rsp+68h+Size]
0x1800064dc  mov     r8, rbx; TokenInformation
0x1800064df  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800064e4  mov     edx, 27h ; '''; TokenInformationClass
0x1800064e9  mov     rcx, rdi; TokenHandle
0x1800064ec  call    cs:__imp_NtQueryInformationToken
0x1800064f2  test    eax, eax
0x1800064f4  js      loc_18000657E
0x1800064fa  cmp     [rbx+4], esi
0x1800064fd  jbe     short loc_18000654F
0x1800064ff  xorps   xmm0, xmm0
0x180006502  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180006509  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18000650e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180006513  call    cs:__imp_RtlInitUnicodeString
0x180006519  xorps   xmm0, xmm0
0x18000651c  mov     edi, esi
0x18000651e  movups  [rsp+68h+var_28], xmm0
0x180006523  cmp     edi, [rbx+4]
0x180006526  jnb     short loc_18000654F
0x180006528  mov     eax, edi
0x18000652a  mov     r8b, 1; CaseInsensitive
0x18000652d  lea     rcx, [rax+rax*4]
0x180006531  mov     rax, [rbx+8]
0x180006535  lea     rsi, [rax+rcx*8]
0x180006539  mov     rdx, rsi; String2
0x18000653c  lea     rcx, [rsp+68h+DestinationString]; String1
0x180006541  call    cs:__imp_RtlCompareUnicodeString
0x180006547  test    eax, eax
0x180006549  jz      short loc_1800065A9
0x18000654b  inc     edi
0x18000654d  jmp     short loc_180006523
0x18000654f  mov     rcx, rbx; P
0x180006552  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180006557  mov     eax, 490h
0x18000655c  mov     rbx, [rsp+68h+arg_0]
0x180006561  mov     rsi, [rsp+68h+arg_8]
0x180006566  add     rsp, 50h
0x18000656a  pop     r15
0x18000656c  pop     r14
0x18000656e  pop     rdi
0x18000656f  retn
0x180006570  xor     ecx, ecx; P
0x180006572  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180006577  mov     eax, 8
0x18000657c  jmp     short loc_18000655C
0x18000657e  mov     ecx, eax; Status
0x180006580  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180006586  mov     rcx, rbx; P
0x180006589  mov     edi, eax
0x18000658b  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180006590  mov     eax, edi
0x180006592  jmp     short loc_18000655C
0x180006594  test    eax, eax
0x180006596  jnz     short loc_18000659F
0x180006598  mov     eax, 54Fh
0x18000659d  jmp     short loc_180006561
0x18000659f  mov     ecx, eax; Status
0x1800065a1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800065a7  jmp     short loc_180006561
0x1800065a9  mov     [r14], rsi
0x1800065ac  xor     ecx, ecx; P
0x1800065ae  mov     [r15], rbx
0x1800065b1  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1800065b6  xor     eax, eax
0x1800065b8  jmp     short loc_18000655C
```
