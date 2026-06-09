# moveToChild

- ea: `0x180054468`
- end: `0x18005453d`
- name: `moveToChild`
- size: `213`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800259b0`
- `0x18002616c`
- `0x18005430c`
- `0x180054410`
- `0x1800601e4`
- `0x180067268`

## callees

- `0x180024414`
- `0x180026290`
- `0x180054468`
- `0x180060134`

## pseudocode

```c
__int64 __fastcall moveToChild(__int64 a1, __int64 a2)
{
  __int64 *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  unsigned int inited; // r8d
  __int64 v8; // rcx
  __int64 v10; // rcx

  if ( *(char *)(a1 + 84) >= 19 )
    return sqlite3ReportError(11, 76072, "database corruption");
  *(_BYTE *)(a1 + 1) &= 0xF9u;
  v3 = (__int64 *)(a1 + 136);
  v4 = a1 + 136;
  *(_WORD *)(a1 + 70) = 0;
  *(_WORD *)(a1 + 2LL * *(char *)(a1 + 84) + 88) = *(_WORD *)(a1 + 86);
  *(_QWORD *)(a1 + 8LL * *(char *)(a1 + 84) + 144) = *(_QWORD *)(a1 + 136);
  v5 = *(unsigned __int8 *)(a1 + 2);
  v6 = *(_QWORD *)(a1 + 32);
  ++*(_BYTE *)(a1 + 84);
  *(_WORD *)(a1 + 86) = 0;
  inited = getAndInitPage(v6, a2, v4, v5);
  if ( inited
    || ((v8 = *v3, !*(_WORD *)(*v3 + 24)) || *(_BYTE *)(v8 + 1) != *(_BYTE *)(a1 + 85))
    && (releasePage(v8), (inited = sqlite3ReportError(11, 76086, "database corruption")) != 0) )
  {
    v10 = *(char *)(a1 + 84);
    *(_BYTE *)(a1 + 84) = v10 - 1;
    *v3 = *(_QWORD *)(a1 + 8 * v10 + 136);
  }
  return inited;
}

```

## disassembly

```asm
0x180054468  mov     [rsp+arg_0], rbx
0x18005446d  push    rdi
0x18005446e  sub     rsp, 20h
0x180054472  cmp     byte ptr [rcx+54h], 13h
0x180054476  mov     rbx, rcx
0x180054479  jge     short loc_1800544EB
0x18005447b  and     byte ptr [rcx+1], 0F9h
0x18005447f  lea     rdi, [rbx+88h]
0x180054486  xor     eax, eax
0x180054488  mov     r8, rdi
0x18005448b  mov     [rcx+46h], ax
0x18005448f  movsx   rcx, byte ptr [rcx+54h]
0x180054494  movzx   eax, word ptr [rbx+56h]
0x180054498  mov     [rbx+rcx*2+58h], ax
0x18005449d  movsx   rcx, byte ptr [rbx+54h]
0x1800544a2  mov     rax, [rdi]
0x1800544a5  mov     [rbx+rcx*8+90h], rax
0x1800544ad  xor     eax, eax
0x1800544af  movzx   r9d, byte ptr [rbx+2]
0x1800544b4  mov     rcx, [rbx+20h]
0x1800544b8  inc     byte ptr [rbx+54h]
0x1800544bb  mov     [rbx+56h], ax
0x1800544bf  call    getAndInitPage
0x1800544c4  mov     r8d, eax
0x1800544c7  test    eax, eax
0x1800544c9  jnz     short loc_180054525
0x1800544cb  mov     rcx, [rdi]
0x1800544ce  cmp     word ptr [rcx+18h], 1
0x1800544d3  jb      short loc_180054503
0x1800544d5  mov     dl, [rbx+55h]
0x1800544d8  cmp     [rcx+1], dl
0x1800544db  jnz     short loc_180054503
0x1800544dd  mov     eax, r8d
0x1800544e0  mov     rbx, [rsp+28h+arg_0]
0x1800544e5  add     rsp, 20h
0x1800544e9  pop     rdi
0x1800544ea  retn
0x1800544eb  lea     r8, aDatabaseCorrup; "database corruption"
0x1800544f2  mov     edx, 12928h
0x1800544f7  mov     ecx, 0Bh
0x1800544fc  call    sqlite3ReportError
0x180054501  jmp     short loc_1800544E0
0x180054503  call    releasePage
0x180054508  lea     r8, aDatabaseCorrup; "database corruption"
0x18005450f  mov     edx, 12936h
0x180054514  mov     ecx, 0Bh
0x180054519  call    sqlite3ReportError
0x18005451e  mov     r8d, eax
0x180054521  test    eax, eax
0x180054523  jz      short loc_1800544DD
0x180054525  movsx   rcx, byte ptr [rbx+54h]
0x18005452a  lea     eax, [rcx-1]
0x18005452d  mov     [rbx+54h], al
0x180054530  mov     rcx, [rbx+rcx*8+88h]
0x180054538  mov     [rdi], rcx
0x18005453b  jmp     short loc_1800544DD
```
