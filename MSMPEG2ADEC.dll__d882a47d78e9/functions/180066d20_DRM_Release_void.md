# DRM_Release(void *)

- ea: `0x180066d20`
- end: `0x180066d90`
- name: `?DRM_Release@@YAJPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000aa40`

## callees

- `0x1800013a0`
- `0x180066d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066d6c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066d6c`

## pseudocode

```c
__int64 __fastcall DRM_Release(char *Block)
{
  __int64 i; // rbx

  if ( !Block )
    return 0xFFFFFFFFLL;
  for ( i = 0; i != 64; ++i )
    operator delete(*(void **)(*((_QWORD *)Block + 4) + 8 * i));
  operator delete(*((void **)Block + 4));
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 288));
  operator delete(Block);
  return 0;
}

```

## disassembly

```asm
0x180066d20  push    rdi
0x180066d22  sub     rsp, 20h
0x180066d26  mov     rdi, rcx
0x180066d29  test    rcx, rcx
0x180066d2c  jnz     short loc_180066D3A
0x180066d2e  mov     eax, 0FFFFFFFFh
0x180066d33  add     rsp, 20h
0x180066d37  pop     rdi
0x180066d38  retn
0x180066d3a  mov     [rsp+28h+arg_0], rbx
0x180066d3f  xor     ebx, ebx
0x180066d41  mov     rcx, [rdi+20h]
0x180066d45  mov     rcx, [rcx+rbx*8]; Block
0x180066d49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180066d4e  inc     rbx
0x180066d51  cmp     rbx, 40h ; '@'
0x180066d55  jnz     short loc_180066D41
0x180066d57  mov     rcx, [rdi+20h]; Block
0x180066d5b  mov     rbx, [rsp+28h+arg_0]
0x180066d60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180066d65  lea     rcx, [rdi+120h]; lpCriticalSection
0x180066d6c  call    cs:__imp_DeleteCriticalSection
0x180066d73  nop     dword ptr [rax+rax+00h]
0x180066d78  mov     rcx, rdi; Block
0x180066d7b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180066d80  xor     eax, eax
0x180066d82  add     rsp, 20h
0x180066d86  pop     rdi
0x180066d87  retn
```
