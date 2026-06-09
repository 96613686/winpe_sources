# CMFAttributesImpl<IMFActivate,CMFCSLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x1800326a0`
- end: `0x180032755`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800088d0`
- `0x1800326a0`
- `0x1800594bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032740`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032740`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800326c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032712`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::GetAllocatedString(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _DWORD *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  __int64 Item; // rax
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  SIZE_T v14; // rdi
  void *v15; // rax

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(a1, a2);
  v10 = 0;
  v11 = Item;
  if ( Item )
  {
    if ( *(_WORD *)Item == 31 )
    {
      v12 = *(_QWORD *)(Item + 8);
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      if ( v13 >= 0x7FFFFFFE )
        goto LABEL_6;
      if ( a4 )
        *a4 = v13;
      v14 = 2LL * (unsigned int)(v13 + 1);
      v15 = CoTaskMemAlloc(v14);
      *a3 = v15;
      if ( v15 )
        memcpy_0(v15, *(const void **)(v11 + 8), v14);
      else
LABEL_6:
        v10 = -2147024882;
    }
    else
    {
      v10 = -1072875843;
    }
  }
  else
  {
    v10 = -1072875802;
  }
  LeaveCriticalSection(v4);
  return v10;
}

```

## disassembly

```asm
0x1800326a0  push    rbx
0x1800326a2  push    rbp
0x1800326a3  push    rsi
0x1800326a4  push    rdi
0x1800326a5  push    r14
0x1800326a7  push    r15
0x1800326a9  sub     rsp, 28h
0x1800326ad  lea     rbp, [rcx+8]
0x1800326b1  mov     rdi, rcx
0x1800326b4  mov     rcx, rbp; lpCriticalSection
0x1800326b7  mov     r14, r9
0x1800326ba  mov     r15, r8
0x1800326bd  mov     rbx, rdx
0x1800326c0  call    cs:__imp_EnterCriticalSection
0x1800326c6  mov     rdx, rbx
0x1800326c9  mov     rcx, rdi
0x1800326cc  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x1800326d1  xor     ebx, ebx
0x1800326d3  mov     rsi, rax
0x1800326d6  test    rax, rax
0x1800326d9  jz      short loc_180032738
0x1800326db  cmp     word ptr [rax], 1Fh
0x1800326df  jnz     short loc_180032731
0x1800326e1  mov     rcx, [rax+8]
0x1800326e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800326e9  inc     rax
0x1800326ec  cmp     [rcx+rax*2], bx
0x1800326f0  jnz     short loc_1800326E9
0x1800326f2  cmp     rax, 7FFFFFFEh
0x1800326f8  jb      short loc_180032701
0x1800326fa  mov     ebx, 8007000Eh
0x1800326ff  jmp     short loc_18003273D
0x180032701  test    r14, r14
0x180032704  jz      short loc_180032709
0x180032706  mov     [r14], eax
0x180032709  lea     edi, [rax+1]
0x18003270c  add     rdi, rdi
0x18003270f  mov     rcx, rdi; cb
0x180032712  call    cs:__imp_CoTaskMemAlloc
0x180032718  mov     [r15], rax
0x18003271b  test    rax, rax
0x18003271e  jz      short loc_1800326FA
0x180032720  mov     rdx, [rsi+8]; Src
0x180032724  mov     r8, rdi; Size
0x180032727  mov     rcx, rax; void *
0x18003272a  call    memcpy_0
0x18003272f  jmp     short loc_18003273D
0x180032731  mov     ebx, 0C00D36BDh
0x180032736  jmp     short loc_18003273D
0x180032738  mov     ebx, 0C00D36E6h
0x18003273d  mov     rcx, rbp; lpCriticalSection
0x180032740  call    cs:__imp_LeaveCriticalSection
0x180032746  mov     eax, ebx
0x180032748  add     rsp, 28h
0x18003274c  pop     r15
0x18003274e  pop     r14
0x180032750  pop     rdi
0x180032751  pop     rsi
0x180032752  pop     rbp
0x180032753  pop     rbx
0x180032754  retn
```
