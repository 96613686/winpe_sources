# CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(_GUID const &,uchar const *,uint)

- ea: `0x1800cd9d0`
- end: `0x1800cda73`
- name: `?SetBlob@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBEI@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800cc868`
- `0x1800cd9d0`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cda5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cda5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd9ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cd9ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cda12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800cda12`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(
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
  Item = CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(a1, a2);
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
0x1800cd9d0  push    rbx
0x1800cd9d2  push    rbp
0x1800cd9d3  push    rsi
0x1800cd9d4  push    rdi
0x1800cd9d5  push    r12
0x1800cd9d7  push    r14
0x1800cd9d9  push    r15
0x1800cd9db  sub     rsp, 20h
0x1800cd9df  mov     rdi, rcx
0x1800cd9e2  mov     r15d, r9d
0x1800cd9e5  add     rcx, 8; lpCriticalSection
0x1800cd9e9  mov     r12, r8
0x1800cd9ec  mov     rbx, rdx
0x1800cd9ef  call    cs:__imp_EnterCriticalSection
0x1800cd9f5  mov     rdx, rbx
0x1800cd9f8  mov     rcx, rdi
0x1800cd9fb  call    ?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CMFCSLock>::CreateItem(_GUID const &)
0x1800cda00  mov     rsi, rax
0x1800cda03  test    rax, rax
0x1800cda06  jnz     short loc_1800CDA0F
0x1800cda08  mov     ebx, 8007000Eh
0x1800cda0d  jmp     short loc_1800CDA58
0x1800cda0f  mov     rcx, r15; cb
0x1800cda12  call    cs:__imp_CoTaskMemAlloc
0x1800cda18  mov     [rsi+10h], rax
0x1800cda1c  test    rax, rax
0x1800cda1f  jnz     short loc_1800CDA38
0x1800cda21  mov     rax, [rdi]
0x1800cda24  mov     rdx, rbx
0x1800cda27  mov     rcx, rdi
0x1800cda2a  mov     rax, [rax+98h]
0x1800cda31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cda36  jmp     short loc_1800CDA08
0x1800cda38  xor     ebx, ebx
0x1800cda3a  mov     r8, r15; Size
0x1800cda3d  mov     rdx, r12; Src
0x1800cda40  mov     rcx, rax; void *
0x1800cda43  call    memcpy_0
0x1800cda48  mov     word ptr [rsi], 1011h
0x1800cda4d  mov     [rsi+8], r15d
0x1800cda51  mov     dword ptr [rdi+40h], 1
0x1800cda58  lea     rcx, [rdi+8]; lpCriticalSection
0x1800cda5c  call    cs:__imp_LeaveCriticalSection
0x1800cda62  mov     eax, ebx
0x1800cda64  add     rsp, 20h
0x1800cda68  pop     r15
0x1800cda6a  pop     r14
0x1800cda6c  pop     r12
0x1800cda6e  pop     rdi
0x1800cda6f  pop     rsi
0x1800cda70  pop     rbp
0x1800cda71  pop     rbx
0x1800cda72  retn
```
