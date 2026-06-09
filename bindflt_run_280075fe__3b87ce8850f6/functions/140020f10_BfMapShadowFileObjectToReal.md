# BfMapShadowFileObjectToReal

- ea: `0x140020f10`
- end: `0x140020fea`
- name: `BfMapShadowFileObjectToReal`
- size: `218`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_CONTEXT Context@<r8>, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001740`
- `0x1400060f0`
- `0x1400127a0`
- `0x140024e40`

## callees

- `0x140020f10`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x140020fcc`
- `FLTMGR!FltGetStreamHandleContext` at `0x140020fcc`
- `FLTMGR!FltReleaseContext` at `0x140020f71`
- `FLTMGR!FltReleaseContext` at `0x140020f71`

## pseudocode

```c
char __fastcall BfMapShadowFileObjectToReal(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        _BYTE *Context,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  _WORD *FsContext; // rax
  _BYTE *v8; // rcx
  char v13; // bl
  _QWORD *FsContext2; // rdx
  _QWORD *v15; // rcx
  PFLT_CONTEXT Contexta; // [rsp+38h] [rbp+10h] BYREF

  FsContext = FileObject->FsContext;
  v8 = Context;
  Contexta = Context;
  if ( !FsContext || *FsContext != 25649 )
    return 0;
  if ( !Context )
  {
    if ( FltGetStreamHandleContext(Instance, FileObject, &Contexta) < 0 )
      return 0;
    v8 = Contexta;
  }
  v13 = v8[80] & 1;
  if ( !Context )
    FltReleaseContext(v8);
  if ( !v13 )
    return 0;
  FsContext2 = FileObject->FsContext2;
  *a5 = FsContext2[1];
  v15 = a6;
  *a4 = FsContext2[2];
  if ( v15 )
    *v15 = *FsContext2;
  return 1;
}

```

## disassembly

```asm
0x140020f10  mov     [rsp+arg_10], rsi
0x140020f15  mov     [rsp+arg_18], rdi
0x140020f1a  push    r14
0x140020f1c  sub     rsp, 20h
0x140020f20  mov     rax, [rdx+18h]
0x140020f24  mov     r10, rcx
0x140020f27  mov     rcx, r8; Context
0x140020f2a  mov     r14, r9
0x140020f2d  mov     [rsp+28h+Context], rcx
0x140020f32  mov     rdi, r8
0x140020f35  mov     rsi, rdx
0x140020f38  test    rax, rax
0x140020f3b  jz      short loc_140020F47
0x140020f3d  mov     edx, 6431h
0x140020f42  cmp     [rax], dx
0x140020f45  jz      short loc_140020F5B
0x140020f47  xor     al, al
0x140020f49  mov     rsi, [rsp+28h+arg_10]
0x140020f4e  mov     rdi, [rsp+28h+arg_18]
0x140020f53  add     rsp, 20h
0x140020f57  pop     r14
0x140020f59  retn
0x140020f5b  test    rdi, rdi
0x140020f5e  jz      short loc_140020FC1
0x140020f60  mov     [rsp+28h+arg_0], rbx
0x140020f65  movzx   ebx, byte ptr [rcx+50h]
0x140020f69  and     bl, 1
0x140020f6c  test    rdi, rdi
0x140020f6f  jnz     short loc_140020F7D
0x140020f71  call    cs:__imp_FltReleaseContext
0x140020f78  nop     dword ptr [rax+rax+00h]
0x140020f7d  test    bl, bl
0x140020f7f  mov     rbx, [rsp+28h+arg_0]
0x140020f84  jz      short loc_140020F47
0x140020f86  mov     rdx, [rsi+20h]
0x140020f8a  mov     rax, [rsp+28h+arg_20]
0x140020f8f  mov     rcx, [rdx+8]
0x140020f93  mov     [rax], rcx
0x140020f96  mov     rcx, [rsp+28h+arg_28]
0x140020f9b  mov     rax, [rdx+10h]
0x140020f9f  mov     [r14], rax
0x140020fa2  test    rcx, rcx
0x140020fa5  jz      short loc_140020FAD
0x140020fa7  mov     rax, [rdx]
0x140020faa  mov     [rcx], rax
0x140020fad  mov     rsi, [rsp+28h+arg_10]
0x140020fb2  mov     al, 1
0x140020fb4  mov     rdi, [rsp+28h+arg_18]
0x140020fb9  add     rsp, 20h
0x140020fbd  pop     r14
0x140020fbf  retn
0x140020fc1  lea     r8, [rsp+28h+Context]; Context
0x140020fc6  mov     rdx, rsi; FileObject
0x140020fc9  mov     rcx, r10; Instance
0x140020fcc  call    cs:__imp_FltGetStreamHandleContext
0x140020fd3  nop     dword ptr [rax+rax+00h]
0x140020fd8  test    eax, eax
0x140020fda  js      loc_140020F47
0x140020fe0  mov     rcx, [rsp+28h+Context]
0x140020fe5  jmp     loc_140020F60
```
