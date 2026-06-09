# CMFAttributesImpl<IMFActivate,CMFCSLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x180032600`
- end: `0x180032699`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800088d0`
- `0x180032600`
- `0x1800594bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003261e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003261e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003264e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003264e`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::GetAllocatedBlob(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 Item; // rdi
  void *v10; // rax
  unsigned int v11; // ebx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(a1, a2);
  if ( Item )
  {
    if ( *(_WORD *)Item == 4113 )
    {
      if ( a4 )
        *a4 = *(_DWORD *)(Item + 8);
      v10 = CoTaskMemAlloc(*(unsigned int *)(Item + 8));
      *a3 = v10;
      if ( v10 )
      {
        v11 = 0;
        memcpy_0(v10, *(const void **)(Item + 16), *(unsigned int *)(Item + 8));
      }
      else
      {
        v11 = -2147024882;
      }
    }
    else
    {
      v11 = -1072875843;
    }
  }
  else
  {
    v11 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v11;
}

```

## disassembly

```asm
0x180032600  push    rbx
0x180032602  push    rbp
0x180032603  push    rsi
0x180032604  push    rdi
0x180032605  push    r14
0x180032607  sub     rsp, 20h
0x18003260b  lea     rbp, [rcx+8]
0x18003260f  mov     rdi, rcx
0x180032612  mov     rcx, rbp; lpCriticalSection
0x180032615  mov     rsi, r9
0x180032618  mov     r14, r8
0x18003261b  mov     rbx, rdx
0x18003261e  call    cs:__imp_EnterCriticalSection
0x180032624  mov     rdx, rbx
0x180032627  mov     rcx, rdi
0x18003262a  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x18003262f  mov     rdi, rax
0x180032632  test    rax, rax
0x180032635  jz      short loc_18003267E
0x180032637  mov     eax, 1011h
0x18003263c  cmp     [rdi], ax
0x18003263f  jnz     short loc_180032677
0x180032641  test    rsi, rsi
0x180032644  jz      short loc_18003264B
0x180032646  mov     ecx, [rdi+8]
0x180032649  mov     [rsi], ecx
0x18003264b  mov     ecx, [rdi+8]; cb
0x18003264e  call    cs:__imp_CoTaskMemAlloc
0x180032654  mov     [r14], rax
0x180032657  test    rax, rax
0x18003265a  jnz     short loc_180032663
0x18003265c  mov     ebx, 8007000Eh
0x180032661  jmp     short loc_180032683
0x180032663  mov     r8d, [rdi+8]; Size
0x180032667  xor     ebx, ebx
0x180032669  mov     rdx, [rdi+10h]; Src
0x18003266d  mov     rcx, rax; void *
0x180032670  call    memcpy_0
0x180032675  jmp     short loc_180032683
0x180032677  mov     ebx, 0C00D36BDh
0x18003267c  jmp     short loc_180032683
0x18003267e  mov     ebx, 0C00D36E6h
0x180032683  mov     rcx, rbp; lpCriticalSection
0x180032686  call    cs:__imp_LeaveCriticalSection
0x18003268c  mov     eax, ebx
0x18003268e  add     rsp, 20h
0x180032692  pop     r14
0x180032694  pop     rdi
0x180032695  pop     rsi
0x180032696  pop     rbp
0x180032697  pop     rbx
0x180032698  retn
```
