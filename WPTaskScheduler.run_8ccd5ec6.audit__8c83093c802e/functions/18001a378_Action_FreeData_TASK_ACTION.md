# Action::FreeData(_TASK_ACTION *)

- ea: `0x18001a378`
- end: `0x18001a454`
- name: `?FreeData@Action@@SAJPEAU_TASK_ACTION@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct _TASK_ACTION *Block)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x18001a090`
- `0x18001a170`
- `0x18001a250`

## callees

- `0x18001a378`
- `0x180022010`

## import_xrefs

- `msvcrt!free` at `0x18001a3ca`
- `msvcrt!free` at `0x18001a3d3`
- `msvcrt!free` at `0x18001a414`
- `msvcrt!free` at `0x18001a423`
- `msvcrt!free` at `0x18001a42c`
- `msvcrt!free` at `0x18001a43c`
- `msvcrt!free` at `0x18001a3ca`
- `msvcrt!free` at `0x18001a3d3`
- `msvcrt!free` at `0x18001a414`
- `msvcrt!free` at `0x18001a423`
- `msvcrt!free` at `0x18001a42c`
- `msvcrt!free` at `0x18001a43c`

## pseudocode

```c
__int64 __fastcall Action::FreeData(void ***Block)
{
  unsigned int v2; // ebx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  void **v6; // rbx
  void *v7; // rcx
  void **v8; // rsi
  void *v9; // rcx

  if ( Block )
  {
    v3 = *(_DWORD *)Block;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( !v4 )
      {
        v2 = (*((__int64 (__fastcall **)(void ***))ActionExtensionFunctionTable + 3))(Block);
LABEL_23:
        free(Block);
        return v2;
      }
      v5 = v4 - 1;
      if ( v5 )
      {
        if ( v5 == 1 )
        {
          v6 = Block[1];
          if ( v6 )
          {
            v7 = v6[2];
            if ( v7 )
              free(v7);
            free(v6);
          }
          v2 = 0;
        }
        else
        {
          v2 = -2100362984;
        }
        goto LABEL_23;
      }
      v8 = Block[1];
      if ( v8 )
      {
        v2 = 0;
LABEL_19:
        v9 = v8[1];
        if ( v9 )
          free(v9);
        free(v8);
        goto LABEL_23;
      }
    }
    else
    {
      v8 = Block[1];
      if ( v8 )
      {
        v2 = 0;
        if ( *v8 )
          free(*v8);
        goto LABEL_19;
      }
    }
    v2 = -2147467261;
    goto LABEL_23;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x18001a378  mov     [rsp+arg_0], rbx
0x18001a37d  mov     [rsp+arg_8], rsi
0x18001a382  push    rdi
0x18001a383  sub     rsp, 20h
0x18001a387  mov     rdi, rcx
0x18001a38a  test    rcx, rcx
0x18001a38d  jnz     short loc_18001A399
0x18001a38f  mov     ebx, 80004003h
0x18001a394  jmp     loc_18001A442
0x18001a399  mov     ecx, [rcx]
0x18001a39b  test    ecx, ecx
0x18001a39d  jz      short loc_18001A401
0x18001a39f  sub     ecx, 1
0x18001a3a2  jz      short loc_18001A3EA
0x18001a3a4  sub     ecx, 1
0x18001a3a7  jz      short loc_18001A3DD
0x18001a3a9  cmp     ecx, 1
0x18001a3ac  jz      short loc_18001A3B8
0x18001a3ae  mov     ebx, 82CF0118h
0x18001a3b3  jmp     loc_18001A439
0x18001a3b8  mov     rbx, [rdi+8]
0x18001a3bc  test    rbx, rbx
0x18001a3bf  jz      short loc_18001A3D9
0x18001a3c1  mov     rcx, [rbx+10h]; Block
0x18001a3c5  test    rcx, rcx
0x18001a3c8  jz      short loc_18001A3D0
0x18001a3ca  call    cs:__imp_free
0x18001a3d0  mov     rcx, rbx; Block
0x18001a3d3  call    cs:__imp_free
0x18001a3d9  xor     ebx, ebx
0x18001a3db  jmp     short loc_18001A439
0x18001a3dd  mov     rsi, [rdi+8]
0x18001a3e1  test    rsi, rsi
0x18001a3e4  jz      short loc_18001A434
0x18001a3e6  xor     ebx, ebx
0x18001a3e8  jmp     short loc_18001A41A
0x18001a3ea  mov     rax, cs:?ActionExtensionFunctionTable@@3PEAU_ActionExtFunctions@@EA; _ActionExtFunctions * ActionExtensionFunctionTable
0x18001a3f1  mov     rcx, rdi
0x18001a3f4  mov     rax, [rax+18h]
0x18001a3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3fd  mov     ebx, eax
0x18001a3ff  jmp     short loc_18001A439
0x18001a401  mov     rsi, [rdi+8]
0x18001a405  test    rsi, rsi
0x18001a408  jz      short loc_18001A434
0x18001a40a  mov     rcx, [rsi]; Block
0x18001a40d  xor     ebx, ebx
0x18001a40f  test    rcx, rcx
0x18001a412  jz      short loc_18001A41A
0x18001a414  call    cs:__imp_free
0x18001a41a  mov     rcx, [rsi+8]; Block
0x18001a41e  test    rcx, rcx
0x18001a421  jz      short loc_18001A429
0x18001a423  call    cs:__imp_free
0x18001a429  mov     rcx, rsi; Block
0x18001a42c  call    cs:__imp_free
0x18001a432  jmp     short loc_18001A439
0x18001a434  mov     ebx, 80004003h
0x18001a439  mov     rcx, rdi; Block
0x18001a43c  call    cs:__imp_free
0x18001a442  mov     rsi, [rsp+28h+arg_8]
0x18001a447  mov     eax, ebx
0x18001a449  mov     rbx, [rsp+28h+arg_0]
0x18001a44e  add     rsp, 20h
0x18001a452  pop     rdi
0x18001a453  retn
```
