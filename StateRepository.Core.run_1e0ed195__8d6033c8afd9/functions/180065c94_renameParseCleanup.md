# renameParseCleanup

- ea: `0x180065c94`
- end: `0x180065d21`
- name: `renameParseCleanup`
- size: `141`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180065620`
- `0x1800659c0`
- `0x18006dff0`
- `0x18007d6a0`
- `0x18007e570`

## callees

- `0x18000a9e0`
- `0x18000c718`
- `0x18004660c`
- `0x180046630`
- `0x18005ba3c`
- `0x18005fa24`
- `0x180065c94`
- `0x18007eb1c`

## pseudocode

```c
__int64 __fastcall renameParseCleanup(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx

  v1 = *a1;
  if ( a1[2] )
    sqlite3VdbeFinalize();
  sqlite3DeleteTable(v1, a1[44]);
  while ( 1 )
  {
    v4 = a1[45];
    if ( !v4 )
      break;
    v3 = a1[45];
    a1[45] = *(_QWORD *)(v4 + 40);
    sqlite3FreeIndex(v1, v3);
  }
  sqlite3DeleteTrigger(v1, a1[46]);
  sqlite3DbFree(v1, a1[1]);
  renameTokenFree(v1, a1[52]);
  return sqlite3ParseObjectReset(a1);
}

```

## disassembly

```asm
0x180065c94  mov     [rsp+arg_0], rbx
0x180065c99  push    rdi
0x180065c9a  sub     rsp, 20h
0x180065c9e  mov     rdi, [rcx]
0x180065ca1  mov     rbx, rcx
0x180065ca4  mov     rcx, [rcx+10h]
0x180065ca8  test    rcx, rcx
0x180065cab  jz      short loc_180065CB2
0x180065cad  call    sqlite3VdbeFinalize
0x180065cb2  mov     rdx, [rbx+160h]
0x180065cb9  mov     rcx, rdi
0x180065cbc  call    sqlite3DeleteTable
0x180065cc1  jmp     short loc_180065CD9
0x180065cc3  mov     rax, [rcx+28h]
0x180065cc7  mov     rdx, rcx
0x180065cca  mov     rcx, rdi
0x180065ccd  mov     [rbx+168h], rax
0x180065cd4  call    sqlite3FreeIndex
0x180065cd9  mov     rcx, [rbx+168h]
0x180065ce0  test    rcx, rcx
0x180065ce3  jnz     short loc_180065CC3
0x180065ce5  mov     rdx, [rbx+170h]
0x180065cec  mov     rcx, rdi
0x180065cef  call    sqlite3DeleteTrigger
0x180065cf4  mov     rdx, [rbx+8]
0x180065cf8  mov     rcx, rdi
0x180065cfb  call    sqlite3DbFree
0x180065d00  mov     rdx, [rbx+1A0h]
0x180065d07  mov     rcx, rdi
0x180065d0a  call    renameTokenFree
0x180065d0f  mov     rcx, rbx
0x180065d12  mov     rbx, [rsp+28h+arg_0]
0x180065d17  add     rsp, 20h
0x180065d1b  pop     rdi
0x180065d1c  jmp     sqlite3ParseObjectReset
```
