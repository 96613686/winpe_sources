# SmPreWrite

- ea: `0x140001100`
- end: `0x140001175`
- name: `SmPreWrite`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001100`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14000113c`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000113c`
- `FLTMGR!FltReleaseContext` at `0x14000115d`
- `FLTMGR!FltReleaseContext` at `0x14000115d`

## pseudocode

```c
__int64 __fastcall SmPreWrite(__int64 a1, __int64 a2, PFLT_CONTEXT *a3)
{
  __int64 v3; // rax
  char v5; // cl
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  Context = 0;
  v5 = *(_BYTE *)(v3 + 4);
  if ( (v5 == 4 || v5 == 13 && *(_DWORD *)(v3 + 40) == 623208)
    && FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    if ( !*(_DWORD *)Context )
    {
      *a3 = Context;
      return 0;
    }
    FltReleaseContext(Context);
  }
  return 1;
}

```

## disassembly

```asm
0x140001100  push    rbx
0x140001102  sub     rsp, 20h
0x140001106  mov     rax, [rcx+10h]
0x14000110a  mov     rbx, r8
0x14000110d  mov     [rsp+28h+Context], 0
0x140001116  mov     r9, rdx
0x140001119  mov     cl, [rax+4]
0x14000111c  cmp     cl, 4
0x14000111f  jz      short loc_14000112F
0x140001121  cmp     cl, 0Dh
0x140001124  jnz     short loc_140001169
0x140001126  cmp     dword ptr [rax+28h], 98268h
0x14000112d  jnz     short loc_140001169
0x14000112f  mov     rdx, [rdx+20h]; FileObject
0x140001133  lea     r8, [rsp+28h+Context]; Context
0x140001138  mov     rcx, [r9+18h]; Instance
0x14000113c  call    cs:__imp_FltGetStreamHandleContext
0x140001143  nop     dword ptr [rax+rax+00h]
0x140001148  test    eax, eax
0x14000114a  js      short loc_140001169
0x14000114c  mov     rcx, [rsp+28h+Context]; Context
0x140001151  cmp     dword ptr [rcx], 0
0x140001154  jnz     short loc_14000115D
0x140001156  mov     [rbx], rcx
0x140001159  xor     eax, eax
0x14000115b  jmp     short loc_14000116E
0x14000115d  call    cs:__imp_FltReleaseContext
0x140001164  nop     dword ptr [rax+rax+00h]
0x140001169  mov     eax, 1
0x14000116e  add     rsp, 20h
0x140001172  pop     rbx
0x140001173  retn
```
