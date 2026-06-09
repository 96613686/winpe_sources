# VfsCreateStreamHandleContext

- ea: `0x140001fb4`
- end: `0x140002078`
- name: `VfsCreateStreamHandleContext`
- size: `196`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003f24`

## callees

- `0x140001fb4`
- `0x140014000`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x14000203d`
- `FLTMGR!FltSetStreamHandleContext` at `0x14000203d`
- `FLTMGR!FltAllocateContext` at `0x140001ff1`
- `FLTMGR!FltAllocateContext` at `0x140001ff1`
- `FLTMGR!FltReleaseContext` at `0x140002054`
- `FLTMGR!FltReleaseContext` at `0x140002054`

## pseudocode

```c
NTSTATUS __fastcall VfsCreateStreamHandleContext(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, PFLT_CONTEXT *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
  PFLT_CONTEXT NewContext; // [rsp+78h] [rbp+20h] BYREF

  NewContext = 0;
  result = FltAllocateContext(VfsData, 0x10u, 0x98u, PagedPool, &NewContext);
  if ( result >= 0 )
  {
    memset(NewContext, 0, 0x98u);
    *(_WORD *)NewContext = 5768;
    *((_WORD *)NewContext + 1) = 152;
    v7 = FltSetStreamHandleContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, 0);
    if ( v7 >= 0 )
    {
      *a3 = NewContext;
      return 0;
    }
    else
    {
      FltReleaseContext(NewContext);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001fb4  push    rbx
0x140001fb6  push    rbp
0x140001fb7  push    rsi
0x140001fb8  push    rdi
0x140001fb9  sub     rsp, 38h
0x140001fbd  mov     rbx, rdx
0x140001fc0  mov     [rsp+58h+NewContext], 0
0x140001fc9  mov     edx, 10h; ContextType
0x140001fce  lea     rax, [rsp+58h+NewContext]
0x140001fd3  mov     rdi, r8
0x140001fd6  mov     [rsp+58h+ReturnedContext], rax; ReturnedContext
0x140001fdb  mov     rsi, rcx
0x140001fde  mov     ebp, 98h
0x140001fe3  mov     rcx, cs:VfsData; Filter
0x140001fea  mov     r8d, ebp; ContextSize
0x140001fed  lea     r9d, [rdx-0Fh]; PoolType
0x140001ff1  call    cs:__imp_FltAllocateContext
0x140001ff8  nop     dword ptr [rax+rax+00h]
0x140001ffd  test    eax, eax
0x140001fff  js      short loc_14000206E
0x140002001  mov     rcx, [rsp+58h+NewContext]; void *
0x140002006  mov     r8d, ebp; Size
0x140002009  xor     edx, edx; Val
0x14000200b  call    memset
0x140002010  mov     rax, [rsp+58h+NewContext]
0x140002015  mov     r8d, 1; Operation
0x14000201b  mov     rdx, rbx; FileObject
0x14000201e  mov     [rsp+58h+ReturnedContext], 0; OldContext
0x140002027  mov     rcx, rsi; Instance
0x14000202a  mov     word ptr [rax], 1688h
0x14000202f  mov     rax, [rsp+58h+NewContext]
0x140002034  mov     [rax+2], bp
0x140002038  mov     r9, [rsp+58h+NewContext]; NewContext
0x14000203d  call    cs:__imp_FltSetStreamHandleContext
0x140002044  nop     dword ptr [rax+rax+00h]
0x140002049  mov     ebx, eax
0x14000204b  test    eax, eax
0x14000204d  jns     short loc_140002064
0x14000204f  mov     rcx, [rsp+58h+NewContext]; Context
0x140002054  call    cs:__imp_FltReleaseContext
0x14000205b  nop     dword ptr [rax+rax+00h]
0x140002060  mov     eax, ebx
0x140002062  jmp     short loc_14000206E
0x140002064  mov     rax, [rsp+58h+NewContext]
0x140002069  mov     [rdi], rax
0x14000206c  xor     eax, eax
0x14000206e  add     rsp, 38h
0x140002072  pop     rdi
0x140002073  pop     rsi
0x140002074  pop     rbp
0x140002075  pop     rbx
0x140002076  retn
```
