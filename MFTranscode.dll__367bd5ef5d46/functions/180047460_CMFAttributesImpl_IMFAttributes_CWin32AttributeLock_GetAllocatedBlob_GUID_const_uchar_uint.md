# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(_GUID const &,uchar * *,uint *)

- ea: `0x180047460`
- end: `0x1800474f9`
- name: `?GetAllocatedBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEAPEAEPEAI@Z`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800076c0`
- `0x180047460`
- `0x1800594bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800474e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004747e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004747e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800474ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800474ae`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::GetAllocatedBlob(
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
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
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
0x180047460  push    rbx
0x180047462  push    rbp
0x180047463  push    rsi
0x180047464  push    rdi
0x180047465  push    r14
0x180047467  sub     rsp, 20h
0x18004746b  lea     rbp, [rcx+8]
0x18004746f  mov     rdi, rcx
0x180047472  mov     rcx, rbp; lpCriticalSection
0x180047475  mov     rsi, r9
0x180047478  mov     r14, r8
0x18004747b  mov     rbx, rdx
0x18004747e  call    cs:__imp_EnterCriticalSection
0x180047484  mov     rdx, rbx
0x180047487  mov     rcx, rdi
0x18004748a  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18004748f  mov     rdi, rax
0x180047492  test    rax, rax
0x180047495  jz      short loc_1800474DE
0x180047497  mov     eax, 1011h
0x18004749c  cmp     [rdi], ax
0x18004749f  jnz     short loc_1800474D7
0x1800474a1  test    rsi, rsi
0x1800474a4  jz      short loc_1800474AB
0x1800474a6  mov     ecx, [rdi+8]
0x1800474a9  mov     [rsi], ecx
0x1800474ab  mov     ecx, [rdi+8]; cb
0x1800474ae  call    cs:__imp_CoTaskMemAlloc
0x1800474b4  mov     [r14], rax
0x1800474b7  test    rax, rax
0x1800474ba  jnz     short loc_1800474C3
0x1800474bc  mov     ebx, 8007000Eh
0x1800474c1  jmp     short loc_1800474E3
0x1800474c3  mov     r8d, [rdi+8]; Size
0x1800474c7  xor     ebx, ebx
0x1800474c9  mov     rdx, [rdi+10h]; Src
0x1800474cd  mov     rcx, rax; void *
0x1800474d0  call    memcpy_0
0x1800474d5  jmp     short loc_1800474E3
0x1800474d7  mov     ebx, 0C00D36BDh
0x1800474dc  jmp     short loc_1800474E3
0x1800474de  mov     ebx, 0C00D36E6h
0x1800474e3  mov     rcx, rbp; lpCriticalSection
0x1800474e6  call    cs:__imp_LeaveCriticalSection
0x1800474ec  mov     eax, ebx
0x1800474ee  add     rsp, 20h
0x1800474f2  pop     r14
0x1800474f4  pop     rdi
0x1800474f5  pop     rsi
0x1800474f6  pop     rbp
0x1800474f7  pop     rbx
0x1800474f8  retn
```
