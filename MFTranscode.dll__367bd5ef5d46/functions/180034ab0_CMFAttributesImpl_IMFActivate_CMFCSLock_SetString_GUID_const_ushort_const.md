# CMFAttributesImpl<IMFActivate,CMFCSLock>::SetString(_GUID const &,ushort const *)

- ea: `0x180034ab0`
- end: `0x180034b7d`
- name: `?SetString@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEBG@Z`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180031f1c`
- `0x180034ab0`
- `0x1800594bc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034b66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034b66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034acc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b1f`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::SetString(__int64 a1, __int64 a2, _WORD *a3)
{
  __int64 Item; // rax
  __int64 v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  size_t v11; // rbp
  void *v12; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(a1, a2);
  v7 = Item;
  if ( !a3 )
    goto LABEL_2;
  if ( !Item )
  {
LABEL_4:
    v8 = -2147024882;
    goto LABEL_11;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = 2 * v9 + 2;
  if ( v10 < 0xFFFFFFFF )
  {
    v11 = (unsigned int)v10;
    v12 = CoTaskMemAlloc((unsigned int)v10);
    *(_QWORD *)(v7 + 8) = v12;
    if ( v12 )
    {
      v8 = 0;
      memcpy_0(v12, a3, v11);
      *(_WORD *)v7 = 31;
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_11;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 152LL))(a1, a2);
    goto LABEL_4;
  }
LABEL_2:
  v8 = -2147024809;
LABEL_11:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return v8;
}

```

## disassembly

```asm
0x180034ab0  push    rbx
0x180034ab2  push    rbp
0x180034ab3  push    rsi
0x180034ab4  push    rdi
0x180034ab5  push    r12
0x180034ab7  push    r14
0x180034ab9  push    r15
0x180034abb  sub     rsp, 20h
0x180034abf  mov     rdi, rcx
0x180034ac2  mov     r14, r8
0x180034ac5  add     rcx, 8; lpCriticalSection
0x180034ac9  mov     rbx, rdx
0x180034acc  call    cs:__imp_EnterCriticalSection
0x180034ad2  mov     rdx, rbx
0x180034ad5  mov     rcx, rdi
0x180034ad8  call    ?CreateItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::CreateItem(_GUID const &)
0x180034add  xor     r12d, r12d
0x180034ae0  mov     rsi, rax
0x180034ae3  test    r14, r14
0x180034ae6  jnz     short loc_180034AEF
0x180034ae8  mov     ebx, 80070057h
0x180034aed  jmp     short loc_180034B62
0x180034aef  test    rsi, rsi
0x180034af2  jnz     short loc_180034AFB
0x180034af4  mov     ebx, 8007000Eh
0x180034af9  jmp     short loc_180034B62
0x180034afb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034aff  inc     rax
0x180034b02  cmp     [r14+rax*2], r12w
0x180034b07  jnz     short loc_180034AFF
0x180034b09  lea     rax, ds:2[rax*2]
0x180034b11  mov     ecx, 0FFFFFFFFh
0x180034b16  cmp     rax, rcx
0x180034b19  jnb     short loc_180034AE8
0x180034b1b  mov     ecx, eax; cb
0x180034b1d  mov     ebp, eax
0x180034b1f  call    cs:__imp_CoTaskMemAlloc
0x180034b25  mov     [rsi+8], rax
0x180034b29  test    rax, rax
0x180034b2c  jnz     short loc_180034B45
0x180034b2e  mov     rax, [rdi]
0x180034b31  mov     rdx, rbx
0x180034b34  mov     rcx, rdi
0x180034b37  mov     rax, [rax+98h]
0x180034b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b43  jmp     short loc_180034AF4
0x180034b45  mov     r8, rbp; Size
0x180034b48  mov     rdx, r14; Src
0x180034b4b  mov     rcx, rax; void *
0x180034b4e  mov     ebx, r12d
0x180034b51  call    memcpy_0
0x180034b56  mov     word ptr [rsi], 1Fh
0x180034b5b  mov     dword ptr [rdi+40h], 1
0x180034b62  lea     rcx, [rdi+8]; lpCriticalSection
0x180034b66  call    cs:__imp_LeaveCriticalSection
0x180034b6c  mov     eax, ebx
0x180034b6e  add     rsp, 20h
0x180034b72  pop     r15
0x180034b74  pop     r14
0x180034b76  pop     r12
0x180034b78  pop     rdi
0x180034b79  pop     rsi
0x180034b7a  pop     rbp
0x180034b7b  pop     rbx
0x180034b7c  retn
```
