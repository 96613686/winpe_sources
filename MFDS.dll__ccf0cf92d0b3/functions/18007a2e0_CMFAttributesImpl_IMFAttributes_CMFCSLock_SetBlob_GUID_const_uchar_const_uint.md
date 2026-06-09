# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x18007a2e0`
- end: `0x18007a39d`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800781c8`
- `0x18007a2e0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18007a35f`
- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x18007a35f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a37f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a37f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a2ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a2ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a328`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a328`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(
        __int64 a1,
        _DWORD *a2,
        const void *a3,
        unsigned int a4)
{
  SIZE_T v5; // r15
  PROPVARIANT *Item; // rsi
  unsigned int v9; // ebx
  BYTE *v10; // rax

  v5 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v10 = (BYTE *)CoTaskMemAlloc(v5);
    Item->bstrblobVal.pData = v10;
    if ( v10 )
    {
      v9 = 0;
      memcpy(v10, a3, v5);
      Item->vt = 4113;
      Item->lVal = v5;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v9 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v9;
}

```

## disassembly

```asm
0x18007a2e0  push    rbx
0x18007a2e2  push    rbp
0x18007a2e3  push    rsi
0x18007a2e4  push    rdi
0x18007a2e5  push    r12
0x18007a2e7  push    r14
0x18007a2e9  push    r15
0x18007a2eb  sub     rsp, 20h
0x18007a2ef  mov     rdi, rcx
0x18007a2f2  mov     r15d, r9d
0x18007a2f5  add     rcx, 8; lpCriticalSection
0x18007a2f9  mov     r12, r8
0x18007a2fc  mov     rbx, rdx
0x18007a2ff  call    cs:__imp_EnterCriticalSection
0x18007a306  nop     dword ptr [rax+rax+00h]
0x18007a30b  mov     rdx, rbx
0x18007a30e  mov     rcx, rdi
0x18007a311  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x18007a316  mov     rsi, rax
0x18007a319  test    rax, rax
0x18007a31c  jnz     short loc_18007A325
0x18007a31e  mov     ebx, 8007000Eh
0x18007a323  jmp     short loc_18007A37B
0x18007a325  mov     rcx, r15; cb
0x18007a328  call    cs:__imp_CoTaskMemAlloc
0x18007a32f  nop     dword ptr [rax+rax+00h]
0x18007a334  mov     [rsi+10h], rax
0x18007a338  test    rax, rax
0x18007a33b  jnz     short loc_18007A354
0x18007a33d  mov     rax, [rdi]
0x18007a340  mov     rdx, rbx
0x18007a343  mov     rcx, rdi
0x18007a346  mov     rax, [rax+98h]
0x18007a34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a352  jmp     short loc_18007A31E
0x18007a354  xor     ebx, ebx
0x18007a356  mov     r8, r15; Size
0x18007a359  mov     rdx, r12; Src
0x18007a35c  mov     rcx, rax; void *
0x18007a35f  call    cs:__imp_memcpy
0x18007a366  nop     dword ptr [rax+rax+00h]
0x18007a36b  mov     word ptr [rsi], 1011h
0x18007a370  mov     [rsi+8], r15d
0x18007a374  mov     dword ptr [rdi+40h], 1
0x18007a37b  lea     rcx, [rdi+8]; lpCriticalSection
0x18007a37f  call    cs:__imp_LeaveCriticalSection
0x18007a386  nop     dword ptr [rax+rax+00h]
0x18007a38b  mov     eax, ebx
0x18007a38d  add     rsp, 20h
0x18007a391  pop     r15
0x18007a393  pop     r14
0x18007a395  pop     r12
0x18007a397  pop     rdi
0x18007a398  pop     rsi
0x18007a399  pop     rbp
0x18007a39a  pop     rbx
0x18007a39b  retn
```
