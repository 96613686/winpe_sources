# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedString(_GUID const &,ushort * *,uint *)

- ea: `0x18006d740`
- end: `0x18006d808`
- name: `?GetAllocatedString@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAGPEAI@Z`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800445e4`
- `0x18006d740`
- `0x18009606c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d7ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006d7ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d760`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006d760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006d7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006d7b8`

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
0x18006d740  push    rbx
0x18006d742  push    rbp
0x18006d743  push    rsi
0x18006d744  push    rdi
0x18006d745  push    r14
0x18006d747  push    r15
0x18006d749  sub     rsp, 28h
0x18006d74d  lea     rbp, [rcx+8]
0x18006d751  mov     rdi, rcx
0x18006d754  mov     rcx, rbp; lpCriticalSection
0x18006d757  mov     r14, r9
0x18006d75a  mov     r15, r8
0x18006d75d  mov     rbx, rdx
0x18006d760  call    cs:__imp_EnterCriticalSection
0x18006d767  nop     dword ptr [rax+rax+00h]
0x18006d76c  mov     rdx, rbx
0x18006d76f  mov     rcx, rdi
0x18006d772  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18006d777  xor     ebx, ebx
0x18006d779  mov     rsi, rax
0x18006d77c  test    rax, rax
0x18006d77f  jz      short loc_18006D7E4
0x18006d781  cmp     word ptr [rax], 1Fh
0x18006d785  jnz     short loc_18006D7DD
0x18006d787  mov     rcx, [rax+8]
0x18006d78b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006d78f  inc     rax
0x18006d792  cmp     [rcx+rax*2], bx
0x18006d796  jnz     short loc_18006D78F
0x18006d798  cmp     rax, 7FFFFFFEh
0x18006d79e  jb      short loc_18006D7A7
0x18006d7a0  mov     ebx, 8007000Eh
0x18006d7a5  jmp     short loc_18006D7E9
0x18006d7a7  test    r14, r14
0x18006d7aa  jz      short loc_18006D7AF
0x18006d7ac  mov     [r14], eax
0x18006d7af  lea     edi, [rax+1]
0x18006d7b2  add     rdi, rdi
0x18006d7b5  mov     rcx, rdi; cb
0x18006d7b8  call    cs:__imp_CoTaskMemAlloc
0x18006d7bf  nop     dword ptr [rax+rax+00h]
0x18006d7c4  mov     [r15], rax
0x18006d7c7  test    rax, rax
0x18006d7ca  jz      short loc_18006D7A0
0x18006d7cc  mov     rdx, [rsi+8]; Src
0x18006d7d0  mov     r8, rdi; Size
0x18006d7d3  mov     rcx, rax; void *
0x18006d7d6  call    memcpy_0
0x18006d7db  jmp     short loc_18006D7E9
0x18006d7dd  mov     ebx, 0C00D36BDh
0x18006d7e2  jmp     short loc_18006D7E9
0x18006d7e4  mov     ebx, 0C00D36E6h
0x18006d7e9  mov     rcx, rbp; lpCriticalSection
0x18006d7ec  call    cs:__imp_LeaveCriticalSection
0x18006d7f3  nop     dword ptr [rax+rax+00h]
0x18006d7f8  mov     eax, ebx
0x18006d7fa  add     rsp, 28h
0x18006d7fe  pop     r15
0x18006d800  pop     r14
0x18006d802  pop     rdi
0x18006d803  pop     rsi
0x18006d804  pop     rbp
0x18006d805  pop     rbx
0x18006d806  retn
```
