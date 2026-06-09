# CMFAttributesImpl<IMFActivate,CMFCSLock>::SetGUID(_GUID const &,_GUID const &)

- ea: `0x1800347b0`
- end: `0x180034840`
- name: `?SetGUID@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@0@Z`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180031f1c`
- `0x1800347b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003482d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003482d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800347c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800347c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347ed`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::SetGUID(__int64 a1, __int64 a2, _OWORD *a3)
{
  __int64 Item; // rsi
  unsigned int v7; // ebx
  _OWORD *v8; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(a1, a2);
  if ( Item )
  {
    v8 = CoTaskMemAlloc(0x10u);
    *(_QWORD *)(Item + 8) = v8;
    if ( v8 )
    {
      *(_WORD *)Item = 72;
      v7 = 0;
      *v8 = *a3;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
  }
  v7 = -2147024882;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v7;
}

```

## disassembly

```asm
0x1800347b0  push    rbx
0x1800347b2  push    rbp
0x1800347b3  push    rsi
0x1800347b4  push    rdi
0x1800347b5  push    r14
0x1800347b7  sub     rsp, 20h
0x1800347bb  mov     rdi, rcx
0x1800347be  mov     r14, r8
0x1800347c1  add     rcx, 8; lpCriticalSection
0x1800347c5  mov     rbx, rdx
0x1800347c8  call    cs:__imp_EnterCriticalSection
0x1800347ce  mov     rdx, rbx
0x1800347d1  mov     rcx, rdi
0x1800347d4  call    ?CreateItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(_GUID const &)
0x1800347d9  mov     rsi, rax
0x1800347dc  test    rax, rax
0x1800347df  jnz     short loc_1800347E8
0x1800347e1  mov     ebx, 8007000Eh
0x1800347e6  jmp     short loc_180034829
0x1800347e8  mov     ecx, 10h; cb
0x1800347ed  call    cs:__imp_CoTaskMemAlloc
0x1800347f3  mov     [rsi+8], rax
0x1800347f7  test    rax, rax
0x1800347fa  jnz     short loc_180034813
0x1800347fc  mov     rax, [rdi]
0x1800347ff  mov     rdx, rbx
0x180034802  mov     rcx, rdi
0x180034805  mov     rax, [rax+98h]
0x18003480c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034811  jmp     short loc_1800347E1
0x180034813  mov     word ptr [rsi], 48h ; 'H'
0x180034818  xor     ebx, ebx
0x18003481a  movups  xmm0, xmmword ptr [r14]
0x18003481e  movdqu  xmmword ptr [rax], xmm0
0x180034822  mov     dword ptr [rdi+40h], 1
0x180034829  lea     rcx, [rdi+8]; lpCriticalSection
0x18003482d  call    cs:__imp_LeaveCriticalSection
0x180034833  mov     eax, ebx
0x180034835  add     rsp, 20h
0x180034839  pop     r14
0x18003483b  pop     rdi
0x18003483c  pop     rsi
0x18003483d  pop     rbp
0x18003483e  pop     rbx
0x18003483f  retn
```
