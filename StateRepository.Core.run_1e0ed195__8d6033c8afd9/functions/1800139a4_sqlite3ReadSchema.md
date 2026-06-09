# sqlite3ReadSchema

- ea: `0x1800139a4`
- end: `0x1800139ed`
- name: `sqlite3ReadSchema`
- size: `73`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180003128`
- `0x18000ded0`
- `0x1800137fc`
- `0x180013c28`
- `0x180050420`
- `0x18005c958`
- `0x1800830cc`
- `0x1800832c0`
- `0x1800834e0`
- `0x180085340`
- `0x180086c1c`

## callees

- `0x1800139a4`
- `0x1800151b4`

## pseudocode

```c
__int64 __fastcall sqlite3ReadSchema(__int64 *a1)
{
  __int64 v1; // rdi
  __int64 result; // rax

  v1 = *a1;
  result = 0;
  if ( !*(_BYTE *)(*a1 + 197) )
  {
    result = sqlite3Init(*a1, a1 + 1);
    if ( (_DWORD)result )
    {
      ++*((_DWORD *)a1 + 13);
      *((_DWORD *)a1 + 6) = result;
    }
    else if ( *(_BYTE *)(v1 + 111) )
    {
      *(_DWORD *)(v1 + 44) |= 0x10u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800139a4  mov     [rsp+arg_0], rbx
0x1800139a9  push    rdi
0x1800139aa  sub     rsp, 20h
0x1800139ae  mov     rdi, [rcx]
0x1800139b1  xor     eax, eax
0x1800139b3  mov     rbx, rcx
0x1800139b6  cmp     [rdi+0C5h], al
0x1800139bc  jz      short loc_1800139C9
0x1800139be  mov     rbx, [rsp+28h+arg_0]
0x1800139c3  add     rsp, 20h
0x1800139c7  pop     rdi
0x1800139c8  retn
0x1800139c9  lea     rdx, [rcx+8]
0x1800139cd  mov     rcx, rdi
0x1800139d0  call    sqlite3Init
0x1800139d5  test    eax, eax
0x1800139d7  jz      short loc_1800139E1
0x1800139d9  inc     dword ptr [rbx+34h]
0x1800139dc  mov     [rbx+18h], eax
0x1800139df  jmp     short loc_1800139BE
0x1800139e1  cmp     byte ptr [rdi+6Fh], 0
0x1800139e5  jz      short loc_1800139BE
0x1800139e7  or      dword ptr [rdi+2Ch], 10h
0x1800139eb  jmp     short loc_1800139BE
```
