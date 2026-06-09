# CMPEG2Controller::~CMPEG2Controller(void)

- ea: `0x18001d5d4`
- end: `0x18001d6bd`
- name: `??1CMPEG2Controller@@UEAA@XZ`
- size: `233`
- prototype: `void __fastcall(CMPEG2Controller *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18001dae0`
- `0x18001db20`
- `0x18001db70`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x18001d5d4`
- `0x18001e740`
- `0x180034010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001d6a2`
- `KERNEL32!HeapFree` at `0x18001d6a2`
- `KERNEL32!DeleteCriticalSection` at `0x18001d642`
- `KERNEL32!DeleteCriticalSection` at `0x18001d642`
- `KERNEL32!DeleteCriticalSection` at `0x18001d6b6`

## pseudocode

```c
void __fastcall CMPEG2Controller::~CMPEG2Controller(CMPEG2Controller *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdi
  volatile signed __int32 *v5; // rdi
  void *v6; // r8

  *(_QWORD *)this = &CMPEG2Controller::`vftable';
  CMPEG2Controller::ClearConfig(this);
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 32LL))(v2, 1);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 8LL))(v3, 1);
  v4 = *((_QWORD *)this + 23);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 40), 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)v4);
      operator delete((void *)v4, 0x30u);
    }
    *((_QWORD *)this + 23) = 0;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 10, 0xFFFFFFFF) == 1 )
    {
      CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v5);
      operator delete((void *)v5, 0x2530u);
    }
    *((_QWORD *)this + 12) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
    HeapFree(*((HANDLE *)this + 5), 0, v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x18001d5d4  mov     [rsp+arg_8], rbx
0x18001d5d9  push    rdi
0x18001d5da  sub     rsp, 20h
0x18001d5de  lea     rax, ??_7CMPEG2Controller@@6B@; const CMPEG2Controller::`vftable'
0x18001d5e5  mov     rbx, rcx
0x18001d5e8  mov     [rcx], rax
0x18001d5eb  call    ?ClearConfig@CMPEG2Controller@@UEAAJXZ; CMPEG2Controller::ClearConfig(void)
0x18001d5f0  mov     rcx, [rbx+88h]
0x18001d5f7  mov     edi, 1
0x18001d5fc  test    rcx, rcx
0x18001d5ff  jz      short loc_18001D60F
0x18001d601  mov     rax, [rcx]
0x18001d604  mov     edx, edi
0x18001d606  mov     rax, [rax+20h]
0x18001d60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d60f  mov     rcx, [rbx+8]
0x18001d613  test    rcx, rcx
0x18001d616  jz      short loc_18001D626
0x18001d618  mov     rax, [rcx]
0x18001d61b  mov     edx, edi
0x18001d61d  mov     rax, [rax+8]
0x18001d621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d626  mov     rdi, [rbx+0B8h]
0x18001d62d  test    rdi, rdi
0x18001d630  jz      short loc_18001D660
0x18001d632  or      eax, 0FFFFFFFFh
0x18001d635  lock xadd [rdi+28h], eax
0x18001d63a  cmp     eax, 1
0x18001d63d  jnz     short loc_18001D655
0x18001d63f  mov     rcx, rdi; lpCriticalSection
0x18001d642  call    cs:__imp_DeleteCriticalSection
0x18001d648  mov     edx, 30h ; '0'; unsigned __int64
0x18001d64d  mov     rcx, rdi; void *
0x18001d650  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d655  mov     qword ptr [rbx+0B8h], 0
0x18001d660  mov     rdi, [rbx+60h]
0x18001d664  test    rdi, rdi
0x18001d667  jz      short loc_18001D693
0x18001d669  or      eax, 0FFFFFFFFh
0x18001d66c  lock xadd [rdi+28h], eax
0x18001d671  cmp     eax, 1
0x18001d674  jnz     short loc_18001D68B
0x18001d676  mov     rcx, rdi; this
0x18001d679  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18001d67e  mov     edx, 2530h; unsigned __int64
0x18001d683  mov     rcx, rdi; void *
0x18001d686  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d68b  mov     qword ptr [rbx+60h], 0
0x18001d693  mov     r8, [rbx+10h]; lpMem
0x18001d697  test    r8, r8
0x18001d69a  jz      short loc_18001D6A8
0x18001d69c  mov     rcx, [rbx+28h]; hHeap
0x18001d6a0  xor     edx, edx; dwFlags
0x18001d6a2  call    cs:__imp_HeapFree
0x18001d6a8  lea     rcx, [rbx+38h]
0x18001d6ac  mov     rbx, [rsp+28h+arg_8]
0x18001d6b1  add     rsp, 20h
0x18001d6b5  pop     rdi
0x18001d6b6  jmp     cs:__imp_DeleteCriticalSection
```
