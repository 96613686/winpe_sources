# BfSetWriteTrackingEa

- ea: `0x14000f9c4`
- end: `0x14000fa6d`
- name: `BfSetWriteTrackingEa`
- size: `169`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f930`
- `0x1400157a0`

## callees

- `0x14000f9c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fa4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fa4e`
- `ntoskrnl!ExAllocatePool2` at `0x14000f9e9`
- `ntoskrnl!ExAllocatePool2` at `0x14000f9e9`
- `FLTMGR!FltSetEaFile` at `0x14000fa38`
- `FLTMGR!FltSetEaFile` at `0x14000fa38`

## pseudocode

```c
__int64 __fastcall BfSetWriteTrackingEa(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)
{
  _DWORD *Pool2; // rax
  void *v5; // rbx
  unsigned int v6; // edi

  Pool2 = (_DWORD *)ExAllocatePool2(256, 38, 2004108866);
  v5 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = 0;
    Pool2[1] = 71680;
    qmemcpy(Pool2 + 2, "$BINDFLT.WRITTEN.IN.SILO", 24);
    v6 = FltSetEaFile(Instance, FileObject, Pool2, 0x26u);
    ExFreePoolWithTag(v5, 0x77744642u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v6;
}

```

## disassembly

```asm
0x14000f9c4  mov     [rsp+arg_0], rbx
0x14000f9c9  mov     [rsp+arg_8], rsi
0x14000f9ce  push    rdi
0x14000f9cf  sub     rsp, 20h
0x14000f9d3  mov     rdi, rdx
0x14000f9d6  mov     rsi, rcx
0x14000f9d9  mov     edx, 26h ; '&'
0x14000f9de  mov     ecx, 100h
0x14000f9e3  mov     r8d, 77744642h
0x14000f9e9  call    cs:__imp_ExAllocatePool2
0x14000f9f0  nop     dword ptr [rax+rax+00h]
0x14000f9f5  mov     rbx, rax
0x14000f9f8  test    rax, rax
0x14000f9fb  jnz     short loc_14000FA04
0x14000f9fd  mov     edi, 0C000009Ah
0x14000fa02  jmp     short loc_14000FA5A
0x14000fa04  mov     dword ptr [rax], 0
0x14000fa0a  mov     r9d, 26h ; '&'; Length
0x14000fa10  mov     dword ptr [rax+4], 11800h
0x14000fa17  mov     r8, rbx; EaBuffer
0x14000fa1a  movups  xmm0, xmmword ptr cs:aBindfltWritten; "$BINDFLT.WRITTEN.IN.SILO"
0x14000fa21  mov     rdx, rdi; FileObject
0x14000fa24  mov     rcx, rsi; Instance
0x14000fa27  movups  xmmword ptr [rax+8], xmm0
0x14000fa2b  movsd   xmm1, qword ptr cs:aBindfltWritten+10h; ".IN.SILO"
0x14000fa33  movsd   qword ptr [rax+18h], xmm1
0x14000fa38  call    cs:__imp_FltSetEaFile
0x14000fa3f  nop     dword ptr [rax+rax+00h]
0x14000fa44  mov     edi, eax
0x14000fa46  mov     edx, 77744642h; Tag
0x14000fa4b  mov     rcx, rbx; P
0x14000fa4e  call    cs:__imp_ExFreePoolWithTag
0x14000fa55  nop     dword ptr [rax+rax+00h]
0x14000fa5a  mov     rbx, [rsp+28h+arg_0]
0x14000fa5f  mov     eax, edi
0x14000fa61  mov     rsi, [rsp+28h+arg_8]
0x14000fa66  add     rsp, 20h
0x14000fa6a  pop     rdi
0x14000fa6b  retn
```
