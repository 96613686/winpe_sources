# DragDropPrivate::MultiThunkAtoW(char const *)

- ea: `0x18003dfac`
- end: `0x18003e061`
- name: `?MultiThunkAtoW@DragDropPrivate@@YAPEAGPEBD@Z`
- size: `181`
- prototype: `unsigned __int16 *__fastcall(DragDropPrivate *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18003df00`

## callees

- `0x18003dfac`
- `0x18007a9bc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003e024`
- `KERNEL32!SetLastError` at `0x18003e024`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003e02d`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003e050`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003e02d`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18003e050`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18003dffe`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18003dffe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BasePrivate *__fastcall DragDropPrivate::MultiThunkAtoW(DragDropPrivate *this, const char *a2)
{
  DragDropPrivate *v2; // rsi
  int v3; // eax
  bool v4; // r8
  unsigned __int64 v5; // rdi
  unsigned __int128 v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // rcx
  BasePrivate *v10; // rbx
  void *v11; // rdx
  BasePrivate *v12; // rcx
  __int64 v13; // [rsp+0h] [rbp-48h] BYREF
  int v15; // [rsp+58h] [rbp+10h]
  BasePrivate *v16; // [rsp+60h] [rbp+18h]

  v2 = this;
  v3 = DragDropPrivate::MultiMultiByteToWideChar(this, a2, this, 0, 0);
  v5 = v3;
  v15 = v3;
  if ( v3 <= 0 )
    return 0;
  v7 = (unsigned __int64)v3 * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v5, 2u) )
    *(_QWORD *)&v7 = -1;
  try
  {
    BYTE8(v7) = 1;
    v10 = (BasePrivate *)BasePrivate::New((BasePrivate *)v7, *((unsigned __int64 *)&v7 + 1), v4);
    v16 = v10;
  }
  catch ( ... )
  {
    v8 = &v13;
    v2 = this;
    LODWORD(v5) = v15;
    v10 = v16;
  }
  if ( !v10 )
  {
    SetLastError(0xEu);
    v12 = 0;
LABEL_7:
    BasePrivate::Delete(v12, v11);
    return 0;
  }
  if ( (int)DragDropPrivate::MultiMultiByteToWideChar(v9, v8, v2, v10, v5) <= 0 )
  {
    v12 = v10;
    goto LABEL_7;
  }
  BasePrivate::Delete(0, v11);
  return v10;
}

```

## disassembly

```asm
0x18003dfac  mov     [rsp+arg_0], rcx
0x18003dfb1  push    rbx
0x18003dfb2  push    rsi
0x18003dfb3  push    rdi
0x18003dfb4  sub     rsp, 30h
0x18003dfb8  mov     rsi, rcx
0x18003dfbb  mov     [rsp+48h+var_28], 0
0x18003dfc3  xor     r9d, r9d
0x18003dfc6  mov     r8, rcx
0x18003dfc9  call    DragDropPrivate__MultiMultiByteToWideChar
0x18003dfce  movsxd  rdi, eax
0x18003dfd1  mov     [rsp+48h+arg_8], edi
0x18003dfd5  test    eax, eax
0x18003dfd7  jg      short loc_18003DFDD
0x18003dfd9  xor     eax, eax
0x18003dfdb  jmp     short loc_18003E059
0x18003dfdd  mov     [rsp+48h+arg_10], 0
0x18003dfe6  mov     eax, 2
0x18003dfeb  mul     rdi
0x18003dfee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003dff5  cmovb   rax, rcx
0x18003dff9  mov     dl, 1
0x18003dffb  mov     rcx, rax
0x18003dffe  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18003e004  mov     rbx, rax
0x18003e007  mov     [rsp+48h+arg_10], rax
0x18003e00c  jmp     short loc_18003E01C
0x18003e00e  mov     rsi, [rsp+48h+arg_0]
0x18003e013  mov     edi, [rsp+48h+arg_8]
0x18003e017  mov     rbx, [rsp+48h+arg_10]
0x18003e01c  test    rbx, rbx
0x18003e01f  jnz     short loc_18003E035
0x18003e021  lea     ecx, [rbx+0Eh]; dwErrCode
0x18003e024  call    cs:__imp_SetLastError
0x18003e02a  nop
0x18003e02b  xor     ecx, ecx
0x18003e02d  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18003e033  jmp     short loc_18003DFD9
0x18003e035  mov     [rsp+48h+var_28], edi
0x18003e039  mov     r9, rbx
0x18003e03c  mov     r8, rsi
0x18003e03f  call    DragDropPrivate__MultiMultiByteToWideChar
0x18003e044  nop
0x18003e045  test    eax, eax
0x18003e047  jg      short loc_18003E04E
0x18003e049  mov     rcx, rbx
0x18003e04c  jmp     short loc_18003E02D
0x18003e04e  xor     ecx, ecx
0x18003e050  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18003e056  mov     rax, rbx
0x18003e059  add     rsp, 30h
0x18003e05d  pop     rdi
0x18003e05e  pop     rsi
0x18003e05f  pop     rbx
0x18003e060  retn
```
