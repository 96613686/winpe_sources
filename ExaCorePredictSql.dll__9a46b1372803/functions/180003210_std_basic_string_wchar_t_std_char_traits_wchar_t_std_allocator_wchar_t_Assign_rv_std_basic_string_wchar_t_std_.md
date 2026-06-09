# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Assign_rv(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x180003210`
- end: `0x18000329d`
- name: `?_Assign_rv@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX$$QEAV12@@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x180003210`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18000323b`
- `VCRUNTIME140!memmove` at `0x18000323b`

## pseudocode

```c
__int64 __fastcall std::wstring::_Assign_rv(_QWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  bool v5; // cf

  if ( a2[3] >= 8u )
  {
    if ( a1 )
      *a1 = *a2;
    *a2 = 0;
  }
  else if ( a2[2] != -1 )
  {
    memmove(a1, a2, 2 * (a2[2] + 1LL));
  }
  a1[2] = a2[2];
  result = a2[3];
  a1[3] = result;
  a2[3] = 7;
  v5 = a2[3] < 8u;
  a2[2] = 0;
  if ( v5 )
  {
    *(_WORD *)a2 = 0;
  }
  else
  {
    result = *a2;
    *(_WORD *)*a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003210  mov     [rsp+arg_0], rbx
0x180003215  mov     [rsp+arg_8], rsi
0x18000321a  push    rdi
0x18000321b  sub     rsp, 20h
0x18000321f  xor     edi, edi
0x180003221  mov     rbx, rdx
0x180003224  cmp     qword ptr [rdx+18h], 8
0x180003229  mov     rsi, rcx
0x18000322c  jnb     short loc_180003243
0x18000322e  mov     r8, [rdx+10h]
0x180003232  add     r8, 1
0x180003236  jz      short loc_180003251
0x180003238  add     r8, r8; Size
0x18000323b  call    cs:__imp_memmove
0x180003241  jmp     short loc_180003251
0x180003243  test    rsi, rsi
0x180003246  jz      short loc_18000324E
0x180003248  mov     rax, [rdx]
0x18000324b  mov     [rcx], rax
0x18000324e  mov     [rdx], rdi
0x180003251  mov     rax, [rbx+10h]
0x180003255  mov     [rsi+10h], rax
0x180003259  mov     rax, [rbx+18h]
0x18000325d  mov     [rsi+18h], rax
0x180003261  mov     qword ptr [rbx+18h], 7
0x180003269  cmp     qword ptr [rbx+18h], 8
0x18000326e  mov     [rbx+10h], rdi
0x180003272  jb      short loc_18000328A
0x180003274  mov     rax, [rbx]
0x180003277  mov     [rax], di
0x18000327a  mov     rbx, [rsp+28h+arg_0]
0x18000327f  mov     rsi, [rsp+28h+arg_8]
0x180003284  add     rsp, 20h
0x180003288  pop     rdi
0x180003289  retn
0x18000328a  mov     rsi, [rsp+28h+arg_8]
0x18000328f  mov     [rbx], di
0x180003292  mov     rbx, [rsp+28h+arg_0]
0x180003297  add     rsp, 20h
0x18000329b  pop     rdi
0x18000329c  retn
```
