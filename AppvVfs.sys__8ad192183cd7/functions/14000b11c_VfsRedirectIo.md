# VfsRedirectIo

- ea: `0x14000b11c`
- end: `0x14000b1c2`
- name: `VfsRedirectIo`
- size: `166`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140006998`
- `0x14000ad70`
- `0x14000ade0`
- `0x14000ae70`
- `0x14000e18c`

## callees

- `0x14000b11c`

## import_xrefs

- `FLTMGR!FltSetCallbackDataDirty` at `0x14000b1a8`
- `FLTMGR!FltSetCallbackDataDirty` at `0x14000b1a8`
- `FLTMGR!FltIsIoRedirectionAllowedForOperation` at `0x14000b16f`
- `FLTMGR!FltIsIoRedirectionAllowedForOperation` at `0x14000b16f`

## pseudocode

```c
__int64 __fastcall VfsRedirectIo(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  __int64 result; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FLT_INSTANCE *v6; // rdx
  unsigned __int8 RedirectionAllowedThisIo; // [rsp+38h] [rbp+10h] BYREF

  if ( (*(_DWORD *)(a2 + 4) & 4) != 0 )
  {
    Data->Iopb->TargetFileObject = *(PFILE_OBJECT *)(a2 + 48);
    Data->Iopb->TargetInstance = *(PFLT_INSTANCE *)(a2 + 40);
  }
  else
  {
    result = *(unsigned int *)(a2 + 32);
    if ( (int)result < 0 )
      return result;
    Iopb = Data->Iopb;
    v6 = *(struct _FLT_INSTANCE **)(a2 + 64);
    RedirectionAllowedThisIo = 0;
    if ( Iopb->TargetInstance != v6
      && (FltIsIoRedirectionAllowedForOperation(Data, v6, &RedirectionAllowedThisIo, 0) < 0 || !RedirectionAllowedThisIo) )
    {
      return 3221225473LL;
    }
    Data->Iopb->TargetFileObject = *(PFILE_OBJECT *)(a2 + 72);
    Data->Iopb->TargetInstance = *(PFLT_INSTANCE *)(a2 + 64);
  }
  FltSetCallbackDataDirty(Data);
  return 0;
}

```

## disassembly

```asm
0x14000b11c  mov     [rsp+arg_0], rbx
0x14000b121  push    rdi
0x14000b122  sub     rsp, 20h
0x14000b126  mov     eax, [rdx+4]
0x14000b129  mov     rbx, rdx
0x14000b12c  mov     rdi, rcx
0x14000b12f  test    al, 4
0x14000b131  jz      short loc_14000B14D
0x14000b133  mov     r8, [rcx+10h]
0x14000b137  mov     rax, [rdx+30h]
0x14000b13b  mov     [r8+8], rax
0x14000b13f  mov     r8, [rcx+10h]
0x14000b143  mov     rax, [rdx+28h]
0x14000b147  mov     [r8+10h], rax
0x14000b14b  jmp     short loc_14000B1A5
0x14000b14d  mov     eax, [rdx+20h]
0x14000b150  test    eax, eax
0x14000b152  js      short loc_14000B1B6
0x14000b154  mov     rax, [rcx+10h]
0x14000b158  mov     rdx, [rdx+40h]; TargetInstance
0x14000b15c  mov     [rsp+28h+RedirectionAllowedThisIo], 0
0x14000b161  cmp     [rax+10h], rdx
0x14000b165  jz      short loc_14000B18D
0x14000b167  xor     r9d, r9d; RedirectionAllowedAllIo
0x14000b16a  lea     r8, [rsp+28h+RedirectionAllowedThisIo]; RedirectionAllowedThisIo
0x14000b16f  call    cs:__imp_FltIsIoRedirectionAllowedForOperation
0x14000b176  nop     dword ptr [rax+rax+00h]
0x14000b17b  test    eax, eax
0x14000b17d  js      short loc_14000B186
0x14000b17f  cmp     [rsp+28h+RedirectionAllowedThisIo], 0
0x14000b184  jnz     short loc_14000B18D
0x14000b186  mov     eax, 0C0000001h
0x14000b18b  jmp     short loc_14000B1B6
0x14000b18d  mov     rcx, [rdi+10h]
0x14000b191  mov     rax, [rbx+48h]
0x14000b195  mov     [rcx+8], rax
0x14000b199  mov     rcx, [rdi+10h]
0x14000b19d  mov     rax, [rbx+40h]
0x14000b1a1  mov     [rcx+10h], rax
0x14000b1a5  mov     rcx, rdi; Data
0x14000b1a8  call    cs:__imp_FltSetCallbackDataDirty
0x14000b1af  nop     dword ptr [rax+rax+00h]
0x14000b1b4  xor     eax, eax
0x14000b1b6  mov     rbx, [rsp+28h+arg_0]
0x14000b1bb  add     rsp, 20h
0x14000b1bf  pop     rdi
0x14000b1c0  retn
```
