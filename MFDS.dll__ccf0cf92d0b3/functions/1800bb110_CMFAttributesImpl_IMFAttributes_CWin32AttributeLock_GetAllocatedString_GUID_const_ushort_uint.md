# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x1800bb110`
- end: `0x1800bb1d8`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010010`
- `0x180074a12`
- `0x1800bb110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb1bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb1bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb130`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb188`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb188`

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
0x1800bb110  push    rbx
0x1800bb112  push    rbp
0x1800bb113  push    rsi
0x1800bb114  push    rdi
0x1800bb115  push    r14
0x1800bb117  push    r15
0x1800bb119  sub     rsp, 28h
0x1800bb11d  lea     rbp, [rcx+8]
0x1800bb121  mov     rdi, rcx
0x1800bb124  mov     rcx, rbp; lpCriticalSection
0x1800bb127  mov     r14, r9
0x1800bb12a  mov     r15, r8
0x1800bb12d  mov     rbx, rdx
0x1800bb130  call    cs:__imp_EnterCriticalSection
0x1800bb137  nop     dword ptr [rax+rax+00h]
0x1800bb13c  mov     rdx, rbx
0x1800bb13f  mov     rcx, rdi
0x1800bb142  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x1800bb147  xor     ebx, ebx
0x1800bb149  mov     rsi, rax
0x1800bb14c  test    rax, rax
0x1800bb14f  jz      short loc_1800BB1B4
0x1800bb151  cmp     word ptr [rax], 1Fh
0x1800bb155  jnz     short loc_1800BB1AD
0x1800bb157  mov     rcx, [rax+8]
0x1800bb15b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bb15f  inc     rax
0x1800bb162  cmp     [rcx+rax*2], bx
0x1800bb166  jnz     short loc_1800BB15F
0x1800bb168  cmp     rax, 7FFFFFFEh
0x1800bb16e  jb      short loc_1800BB177
0x1800bb170  mov     ebx, 8007000Eh
0x1800bb175  jmp     short loc_1800BB1B9
0x1800bb177  test    r14, r14
0x1800bb17a  jz      short loc_1800BB17F
0x1800bb17c  mov     [r14], eax
0x1800bb17f  lea     edi, [rax+1]
0x1800bb182  add     rdi, rdi
0x1800bb185  mov     rcx, rdi; cb
0x1800bb188  call    cs:__imp_CoTaskMemAlloc
0x1800bb18f  nop     dword ptr [rax+rax+00h]
0x1800bb194  mov     [r15], rax
0x1800bb197  test    rax, rax
0x1800bb19a  jz      short loc_1800BB170
0x1800bb19c  mov     rdx, [rsi+8]; Src
0x1800bb1a0  mov     r8, rdi; Size
0x1800bb1a3  mov     rcx, rax; void *
0x1800bb1a6  call    memcpy_0
0x1800bb1ab  jmp     short loc_1800BB1B9
0x1800bb1ad  mov     ebx, 0C00D36BDh
0x1800bb1b2  jmp     short loc_1800BB1B9
0x1800bb1b4  mov     ebx, 0C00D36E6h
0x1800bb1b9  mov     rcx, rbp; lpCriticalSection
0x1800bb1bc  call    cs:__imp_LeaveCriticalSection
0x1800bb1c3  nop     dword ptr [rax+rax+00h]
0x1800bb1c8  mov     eax, ebx
0x1800bb1ca  add     rsp, 28h
0x1800bb1ce  pop     r15
0x1800bb1d0  pop     r14
0x1800bb1d2  pop     rdi
0x1800bb1d3  pop     rsi
0x1800bb1d4  pop     rbp
0x1800bb1d5  pop     rbx
0x1800bb1d6  retn
```
