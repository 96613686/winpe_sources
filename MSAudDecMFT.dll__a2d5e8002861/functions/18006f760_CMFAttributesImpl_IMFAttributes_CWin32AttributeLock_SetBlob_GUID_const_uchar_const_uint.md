# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18006f760`
- end: `0x18006f817`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e004`

## callees

- `0x18006cf6c`
- `0x18006f760`
- `0x18009606c`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f7f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f7f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f77f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f77f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f7a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006f7a8`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetBlob(
        __int64 a1,
        __int64 a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  __int64 Item; // rsi
  unsigned int v9; // ebx
  void *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = CoTaskMemAlloc(v5);
    *(_QWORD *)(Item + 16) = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy_0(v10, a3, v5);
      *(_WORD *)Item = 4113;
      *(_DWORD *)(Item + 8) = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x18006f760  push    rbx
0x18006f762  push    rbp
0x18006f763  push    rsi
0x18006f764  push    rdi
0x18006f765  push    r12
0x18006f767  push    r14
0x18006f769  push    r15
0x18006f76b  sub     rsp, 20h
0x18006f76f  mov     rdi, rcx
0x18006f772  mov     r15d, r9d
0x18006f775  add     rcx, 8; lpCriticalSection
0x18006f779  mov     r12, r8
0x18006f77c  mov     rbx, rdx
0x18006f77f  call    cs:__imp_EnterCriticalSection
0x18006f786  nop     dword ptr [rax+rax+00h]
0x18006f78b  mov     rdx, rbx
0x18006f78e  mov     rcx, rdi
0x18006f791  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)
0x18006f796  mov     rsi, rax
0x18006f799  test    rax, rax
0x18006f79c  jnz     short loc_18006F7A5
0x18006f79e  mov     ebx, 8007000Eh
0x18006f7a3  jmp     short loc_18006F7F5
0x18006f7a5  mov     rcx, r15; cb
0x18006f7a8  call    cs:__imp_CoTaskMemAlloc
0x18006f7af  nop     dword ptr [rax+rax+00h]
0x18006f7b4  mov     [rsi+10h], rax
0x18006f7b8  test    rax, rax
0x18006f7bb  jnz     short loc_18006F7D5
0x18006f7bd  mov     rax, [rdi]
0x18006f7c0  mov     rdx, rbx
0x18006f7c3  mov     rcx, rdi
0x18006f7c6  mov     rax, [rax+98h]
0x18006f7cd  call    cs:__guard_dispatch_icall_fptr
0x18006f7d3  jmp     short loc_18006F79E
0x18006f7d5  xor     ebx, ebx
0x18006f7d7  mov     r8, r15; Size
0x18006f7da  mov     rdx, r12; Src
0x18006f7dd  mov     rcx, rax; void *
0x18006f7e0  call    memcpy_0
0x18006f7e5  mov     word ptr [rsi], 1011h
0x18006f7ea  mov     [rsi+8], r15d
0x18006f7ee  mov     dword ptr [rdi+40h], 1
0x18006f7f5  lea     rcx, [rdi+8]; lpCriticalSection
0x18006f7f9  call    cs:__imp_LeaveCriticalSection
0x18006f800  nop     dword ptr [rax+rax+00h]
0x18006f805  mov     eax, ebx
0x18006f807  add     rsp, 20h
0x18006f80b  pop     r15
0x18006f80d  pop     r14
0x18006f80f  pop     r12
0x18006f811  pop     rdi
0x18006f812  pop     rsi
0x18006f813  pop     rbp
0x18006f814  pop     rbx
0x18006f815  retn
```
