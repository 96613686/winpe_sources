# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x180047500`
- end: `0x1800475b5`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800076c0`
- `0x180047500`
- `0x1800594bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800475a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800475a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047520`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047572`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(
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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x180047500  push    rbx
0x180047502  push    rbp
0x180047503  push    rsi
0x180047504  push    rdi
0x180047505  push    r14
0x180047507  push    r15
0x180047509  sub     rsp, 28h
0x18004750d  lea     rbp, [rcx+8]
0x180047511  mov     rdi, rcx
0x180047514  mov     rcx, rbp; lpCriticalSection
0x180047517  mov     r14, r9
0x18004751a  mov     r15, r8
0x18004751d  mov     rbx, rdx
0x180047520  call    cs:__imp_EnterCriticalSection
0x180047526  mov     rdx, rbx
0x180047529  mov     rcx, rdi
0x18004752c  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x180047531  xor     ebx, ebx
0x180047533  mov     rsi, rax
0x180047536  test    rax, rax
0x180047539  jz      short loc_180047598
0x18004753b  cmp     word ptr [rax], 1Fh
0x18004753f  jnz     short loc_180047591
0x180047541  mov     rcx, [rax+8]
0x180047545  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047549  inc     rax
0x18004754c  cmp     [rcx+rax*2], bx
0x180047550  jnz     short loc_180047549
0x180047552  cmp     rax, 7FFFFFFEh
0x180047558  jb      short loc_180047561
0x18004755a  mov     ebx, 8007000Eh
0x18004755f  jmp     short loc_18004759D
0x180047561  test    r14, r14
0x180047564  jz      short loc_180047569
0x180047566  mov     [r14], eax
0x180047569  lea     edi, [rax+1]
0x18004756c  add     rdi, rdi
0x18004756f  mov     rcx, rdi; cb
0x180047572  call    cs:__imp_CoTaskMemAlloc
0x180047578  mov     [r15], rax
0x18004757b  test    rax, rax
0x18004757e  jz      short loc_18004755A
0x180047580  mov     rdx, [rsi+8]; Src
0x180047584  mov     r8, rdi; Size
0x180047587  mov     rcx, rax; void *
0x18004758a  call    memcpy_0
0x18004758f  jmp     short loc_18004759D
0x180047591  mov     ebx, 0C00D36BDh
0x180047596  jmp     short loc_18004759D
0x180047598  mov     ebx, 0C00D36E6h
0x18004759d  mov     rcx, rbp; lpCriticalSection
0x1800475a0  call    cs:__imp_LeaveCriticalSection
0x1800475a6  mov     eax, ebx
0x1800475a8  add     rsp, 28h
0x1800475ac  pop     r15
0x1800475ae  pop     r14
0x1800475b0  pop     rdi
0x1800475b1  pop     rsi
0x1800475b2  pop     rbp
0x1800475b3  pop     rbx
0x1800475b4  retn
```
