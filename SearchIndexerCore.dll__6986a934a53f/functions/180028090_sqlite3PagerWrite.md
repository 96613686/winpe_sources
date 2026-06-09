# sqlite3PagerWrite

- ea: `0x180028090`
- end: `0x1800280fe`
- name: `sqlite3PagerWrite`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `5`
- tags: ``

## callers

- `0x180027660`
- `0x1800364a8`
- `0x180036eb4`
- `0x1800391a0`
- `0x180039ce0`
- `0x18003a0d0`
- `0x18003b900`
- `0x18003d990`
- `0x18003eda4`
- `0x180043f28`
- `0x180044158`
- `0x18004f6a0`
- `0x18005c940`
- `0x18005cec0`
- `0x1800605b8`
- `0x1800608b8`
- `0x180060c4c`
- `0x180063dd4`
- `0x18006f18c`
- `0x180073510`
- `0x1800750b0`
- `0x180075480`
- `0x18007d570`
- `0x18008c7cc`
- `0x1800938d8`
- `0x18009d2c0`

## callees

- `0x180028090`
- `0x180028150`
- `0x180041890`
- `0x18006e0a8`
- `0x180071b54`

## pseudocode

```c
__int64 __fastcall sqlite3PagerWrite(__int64 a1)
{
  _DWORD *v2; // rcx
  __int64 result; // rax

  v2 = *(_DWORD **)(a1 + 40);
  if ( (*(_BYTE *)(a1 + 52) & 4) != 0 && v2[8] >= *(_DWORD *)(a1 + 48) )
  {
    if ( v2[32] && (unsigned int)subjRequiresPage(a1) )
      return subjournalPage(a1);
    else
      return 0;
  }
  else
  {
    result = (unsigned int)v2[12];
    if ( !(_DWORD)result )
    {
      if ( v2[46] > v2[50] )
        return pagerWriteLargeSector(a1);
      else
        return pager_write(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028090  push    rbx
0x180028092  sub     rsp, 20h
0x180028096  mov     rbx, rcx
0x180028099  mov     rcx, [rcx+28h]
0x18002809d  test    byte ptr [rbx+34h], 4
0x1800280a1  jz      short loc_1800280BC
0x1800280a3  mov     eax, [rbx+30h]
0x1800280a6  cmp     [rcx+20h], eax
0x1800280a9  jb      short loc_1800280BC
0x1800280ab  cmp     dword ptr [rcx+80h], 0
0x1800280b2  jnz     short loc_1800280DB
0x1800280b4  xor     eax, eax
0x1800280b6  add     rsp, 20h
0x1800280ba  pop     rbx
0x1800280bb  retn
0x1800280bc  mov     eax, [rcx+30h]
0x1800280bf  test    eax, eax
0x1800280c1  jnz     short loc_1800280B6
0x1800280c3  mov     eax, [rcx+0C8h]
0x1800280c9  cmp     [rcx+0B8h], eax
0x1800280cf  mov     rcx, rbx
0x1800280d2  ja      short loc_1800280F4
0x1800280d4  call    pager_write
0x1800280d9  jmp     short loc_1800280B6
0x1800280db  mov     rcx, rbx
0x1800280de  call    subjRequiresPage
0x1800280e3  test    eax, eax
0x1800280e5  jz      short loc_1800280B4
0x1800280e7  mov     rcx, rbx
0x1800280ea  add     rsp, 20h
0x1800280ee  pop     rbx
0x1800280ef  jmp     subjournalPage
0x1800280f4  add     rsp, 20h
0x1800280f8  pop     rbx
0x1800280f9  jmp     pagerWriteLargeSector
```
