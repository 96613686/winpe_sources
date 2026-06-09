# ZSTDMT_freeBufferPool

- ea: `0x1800a4550`
- end: `0x1800a4620`
- name: `ZSTDMT_freeBufferPool`
- size: `208`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a3820`
- `0x1800a40c0`
- `0x1800a4630`
- `0x1800a49c0`

## callees

- `0x1800a4550`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a45a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a45e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a4614`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a45a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a45e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800a4614`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a45f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a45f1`

## pseudocode

```c
void __fastcall ZSTDMT_freeBufferPool(struct _RTL_CRITICAL_SECTION *Block)
{
  unsigned int i; // edi
  void *v3; // rcx
  void (__fastcall *LockSemaphore)(ULONG_PTR, void *); // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  void (__fastcall *v6)(ULONG_PTR, PRTL_CRITICAL_SECTION_DEBUG, struct _RTL_CRITICAL_SECTION *); // rax
  void (__fastcall *v7)(ULONG_PTR, struct _RTL_CRITICAL_SECTION *); // rax

  if ( Block )
  {
    if ( Block[2].DebugInfo )
    {
      for ( i = 0; i < Block[1].LockCount; ++i )
      {
        v3 = (void *)*((_QWORD *)&Block[2].DebugInfo->Type + 2 * i);
        if ( v3 )
        {
          LockSemaphore = (void (__fastcall *)(ULONG_PTR, void *))Block[1].LockSemaphore;
          if ( LockSemaphore )
            LockSemaphore(Block[1].SpinCount, v3);
          else
            free(v3);
        }
      }
      DebugInfo = Block[2].DebugInfo;
      if ( DebugInfo )
      {
        v6 = (void (__fastcall *)(ULONG_PTR, PRTL_CRITICAL_SECTION_DEBUG, struct _RTL_CRITICAL_SECTION *))Block[1].LockSemaphore;
        if ( v6 )
          v6(Block[1].SpinCount, DebugInfo, Block);
        else
          free(Block[2].DebugInfo);
      }
    }
    DeleteCriticalSection(Block);
    v7 = (void (__fastcall *)(ULONG_PTR, struct _RTL_CRITICAL_SECTION *))Block[1].LockSemaphore;
    if ( v7 )
      v7(Block[1].SpinCount, Block);
    else
      free(Block);
  }
}

```

## disassembly

```asm
0x1800a4550  test    rcx, rcx
0x1800a4553  jz      locret_1800A461F
0x1800a4559  push    rbx
0x1800a455a  sub     rsp, 20h
0x1800a455e  cmp     qword ptr [rcx+50h], 0
0x1800a4563  mov     rbx, rcx
0x1800a4566  jz      loc_1800A45EE
0x1800a456c  mov     [rsp+28h+arg_0], rdi
0x1800a4571  xor     edi, edi
0x1800a4573  cmp     [rcx+30h], edi
0x1800a4576  jbe     short loc_1800A45B6
0x1800a4578  nop     dword ptr [rax+rax+00000000h]
0x1800a4580  mov     rax, [rbx+50h]
0x1800a4584  mov     ecx, edi
0x1800a4586  add     rcx, rcx
0x1800a4589  mov     rcx, [rax+rcx*8]; Block
0x1800a458d  test    rcx, rcx
0x1800a4590  jz      short loc_1800A45AF
0x1800a4592  mov     rax, [rbx+40h]
0x1800a4596  test    rax, rax
0x1800a4599  jz      short loc_1800A45A9
0x1800a459b  mov     rdx, rcx
0x1800a459e  mov     rcx, [rbx+48h]
0x1800a45a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45a7  jmp     short loc_1800A45AF
0x1800a45a9  call    cs:__imp_free
0x1800a45af  inc     edi
0x1800a45b1  cmp     edi, [rbx+30h]
0x1800a45b4  jb      short loc_1800A4580
0x1800a45b6  mov     rdx, [rbx+50h]
0x1800a45ba  mov     ecx, 48h ; 'H'
0x1800a45bf  mov     rdi, [rsp+28h+arg_0]
0x1800a45c4  mov     eax, 40h ; '@'
0x1800a45c9  mov     r8, rbx
0x1800a45cc  test    rdx, rdx
0x1800a45cf  jz      short loc_1800A45EE
0x1800a45d1  mov     rax, [rax+rbx]
0x1800a45d5  test    rax, rax
0x1800a45d8  jz      short loc_1800A45E5
0x1800a45da  mov     rcx, [rcx+rbx]
0x1800a45de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a45e3  jmp     short loc_1800A45EE
0x1800a45e5  mov     rcx, rdx; Block
0x1800a45e8  call    cs:__imp_free
0x1800a45ee  mov     rcx, rbx; lpCriticalSection
0x1800a45f1  call    cs:__imp_DeleteCriticalSection
0x1800a45f7  mov     rax, [rbx+40h]
0x1800a45fb  test    rax, rax
0x1800a45fe  jz      short loc_1800A4611
0x1800a4600  mov     rcx, [rbx+48h]
0x1800a4604  mov     rdx, rbx
0x1800a4607  add     rsp, 20h
0x1800a460b  pop     rbx
0x1800a460c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4611  mov     rcx, rbx; Block
0x1800a4614  call    cs:__imp_free
0x1800a461a  add     rsp, 20h
0x1800a461e  pop     rbx
0x1800a461f  retn
```
