# CTxtSelection::DeleteCaretBitmap(int)

- ea: `0x180078974`
- end: `0x1800789f1`
- name: `?DeleteCaretBitmap@CTxtSelection@@QEAAHH@Z`
- size: `125`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18004c0e8`
- `0x1800788fc`
- `0x1800792e4`

## callees

- `0x180078974`
- `0x180079c0c`

## import_xrefs

- `ext-ms-win-ntuser-caret-l1-1-0!DestroyCaret` at `0x1800789c1`
- `ext-ms-win-ntuser-caret-l1-1-0!DestroyCaret` at `0x1800789c1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800789ce`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800789ce`

## pseudocode

```c
__int64 __fastcall CTxtSelection::DeleteCaretBitmap(CTxtSelection *this, int a2)
{
  unsigned int v2; // edi
  __int64 v6; // rax
  CTxtEdit *v7; // rcx

  v2 = 0;
  if ( *((_QWORD *)this + 29) )
  {
    v6 = *((_QWORD *)this + 3);
    v2 = 1;
    if ( v6 && (v7 = *(CTxtEdit **)(v6 + 40)) != 0 )
      CTxtEdit::TxDestroyCaret(v7);
    else
      DestroyCaret();
    DeleteObject(*((HGDIOBJ *)this + 29));
    *((_QWORD *)this + 29) = 0;
  }
  if ( a2 )
    *((_DWORD *)this + 60) = 0;
  return v2;
}

```

## disassembly

```asm
0x180078974  mov     [rsp+arg_0], rbx
0x180078979  mov     [rsp+arg_8], rsi
0x18007897e  push    rdi
0x18007897f  sub     rsp, 20h
0x180078983  xor     edi, edi
0x180078985  mov     esi, edx
0x180078987  mov     rbx, rcx
0x18007898a  cmp     [rcx+0E8h], rdi
0x180078991  jnz     short loc_1800789B3
0x180078993  test    esi, esi
0x180078995  jz      short loc_1800789A1
0x180078997  mov     dword ptr [rbx+0F0h], 0
0x1800789a1  mov     rbx, [rsp+28h+arg_0]
0x1800789a6  mov     eax, edi
0x1800789a8  mov     rsi, [rsp+28h+arg_8]
0x1800789ad  add     rsp, 20h
0x1800789b1  pop     rdi
0x1800789b2  retn
0x1800789b3  mov     rax, [rcx+18h]
0x1800789b7  mov     edi, 1
0x1800789bc  test    rax, rax
0x1800789bf  jnz     short loc_1800789E1
0x1800789c1  call    cs:__imp_DestroyCaret
0x1800789c7  mov     rcx, [rbx+0E8h]; ho
0x1800789ce  call    cs:__imp_DeleteObject
0x1800789d4  mov     qword ptr [rbx+0E8h], 0
0x1800789df  jmp     short loc_180078993
0x1800789e1  mov     rcx, [rax+28h]; this
0x1800789e5  test    rcx, rcx
0x1800789e8  jz      short loc_1800789C1
0x1800789ea  call    ?TxDestroyCaret@CTxtEdit@@QEAAXXZ; CTxtEdit::TxDestroyCaret(void)
0x1800789ef  jmp     short loc_1800789C7
```
