# CMFAttributesImpl<IMFActivate,CMFCSLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x180034680`
- end: `0x180034723`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180031f1c`
- `0x180034680`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003470c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003470c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003469f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003469f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800346c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800346c2`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::SetBlob(
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
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(a1, a2);
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
0x180034680  push    rbx
0x180034682  push    rbp
0x180034683  push    rsi
0x180034684  push    rdi
0x180034685  push    r12
0x180034687  push    r14
0x180034689  push    r15
0x18003468b  sub     rsp, 20h
0x18003468f  mov     rdi, rcx
0x180034692  mov     r15d, r9d
0x180034695  add     rcx, 8; lpCriticalSection
0x180034699  mov     r12, r8
0x18003469c  mov     rbx, rdx
0x18003469f  call    cs:__imp_EnterCriticalSection
0x1800346a5  mov     rdx, rbx
0x1800346a8  mov     rcx, rdi
0x1800346ab  call    ?CreateItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(_GUID const &)
0x1800346b0  mov     rsi, rax
0x1800346b3  test    rax, rax
0x1800346b6  jnz     short loc_1800346BF
0x1800346b8  mov     ebx, 8007000Eh
0x1800346bd  jmp     short loc_180034708
0x1800346bf  mov     rcx, r15; cb
0x1800346c2  call    cs:__imp_CoTaskMemAlloc
0x1800346c8  mov     [rsi+10h], rax
0x1800346cc  test    rax, rax
0x1800346cf  jnz     short loc_1800346E8
0x1800346d1  mov     rax, [rdi]
0x1800346d4  mov     rdx, rbx
0x1800346d7  mov     rcx, rdi
0x1800346da  mov     rax, [rax+98h]
0x1800346e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346e6  jmp     short loc_1800346B8
0x1800346e8  xor     ebx, ebx
0x1800346ea  mov     r8, r15; Size
0x1800346ed  mov     rdx, r12; Src
0x1800346f0  mov     rcx, rax; void *
0x1800346f3  call    memcpy_0
0x1800346f8  mov     word ptr [rsi], 1011h
0x1800346fd  mov     [rsi+8], r15d
0x180034701  mov     dword ptr [rdi+40h], 1
0x180034708  lea     rcx, [rdi+8]; lpCriticalSection
0x18003470c  call    cs:__imp_LeaveCriticalSection
0x180034712  mov     eax, ebx
0x180034714  add     rsp, 20h
0x180034718  pop     r15
0x18003471a  pop     r14
0x18003471c  pop     r12
0x18003471e  pop     rdi
0x18003471f  pop     rsi
0x180034720  pop     rbp
0x180034721  pop     rbx
0x180034722  retn
```
