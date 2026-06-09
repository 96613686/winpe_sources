# QSTextBox_CreateInstance

- ea: `0x180018510`
- end: `0x1800185b6`
- name: `QSTextBox_CreateInstance`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180018500`
- `0x18001ca38`

## callees

- `0x180017f80`
- `0x1800180d4`
- `0x180018510`
- `0x180018f74`
- `0x18004df30`

## pseudocode

```c
__int64 __fastcall QSTextBox_CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 (__fastcall **v8)(__int64, __int64, _QWORD *); // rax
  int v9; // edi

  if ( !qword_1800DB0E0 )
  {
    v9 = -2147467259;
LABEL_16:
    *a3 = 0;
    return (unsigned int)v9;
  }
  v6 = sub_180018F74(0x220u);
  if ( v6 )
    v7 = sub_1800180D4(v6);
  else
    v7 = 0;
  if ( v7 && (int)sub_180017F80(v7) >= 0 )
  {
    v8 = *(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v7;
    if ( !a1 )
      a1 = v7;
    *(_QWORD *)(v7 + 512) = a1;
    v9 = (*v8)(v7, a2, a3);
  }
  else
  {
    v9 = -2147024882;
  }
  if ( v9 < 0 )
  {
    if ( v7 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v7 + 8) + 776LL))(v7 + 8, 1);
    goto LABEL_16;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018510  mov     [rsp+arg_0], rbx
0x180018515  mov     [rsp+arg_8], rbp
0x18001851a  mov     [rsp+arg_10], rsi
0x18001851f  push    rdi
0x180018520  sub     rsp, 20h
0x180018524  cmp     cs:qword_1800DB0E0, 0
0x18001852c  mov     rsi, r8
0x18001852f  mov     rbp, rdx
0x180018532  mov     rdi, rcx
0x180018535  jz      loc_180052542
0x18001853b  mov     ecx, 220h; Size
0x180018540  call    sub_180018F74
0x180018545  test    rax, rax
0x180018548  jz      short loc_1800185AA
0x18001854a  mov     rcx, rax
0x18001854d  call    sub_1800180D4
0x180018552  mov     rbx, rax
0x180018555  test    rbx, rbx
0x180018558  jz      short loc_1800185AE
0x18001855a  mov     rcx, rbx
0x18001855d  call    sub_180017F80
0x180018562  test    eax, eax
0x180018564  js      short loc_1800185AE
0x180018566  mov     rax, [rbx]
0x180018569  test    rdi, rdi
0x18001856c  mov     r8, rsi
0x18001856f  mov     rdx, rbp
0x180018572  cmovz   rdi, rbx
0x180018576  mov     rcx, rbx
0x180018579  mov     [rbx+200h], rdi
0x180018580  mov     rax, [rax]
0x180018583  call    cs:__guard_dispatch_icall_fptr
0x180018589  mov     edi, eax
0x18001858b  test    edi, edi
0x18001858d  js      loc_180052549
0x180018593  mov     rbx, [rsp+28h+arg_0]
0x180018598  mov     eax, edi
0x18001859a  mov     rbp, [rsp+28h+arg_8]
0x18001859f  mov     rsi, [rsp+28h+arg_10]
0x1800185a4  add     rsp, 20h
0x1800185a8  pop     rdi
0x1800185a9  retn
0x1800185aa  xor     ebx, ebx
0x1800185ac  jmp     short loc_180018555
0x1800185ae  mov     edi, 8007000Eh
0x1800185b3  jmp     short loc_18001858B
0x180052542  mov     edi, 80004005h
0x180052547  jmp     short loc_180052567
0x180052549  test    rbx, rbx
0x18005254c  jz      short loc_180052567
0x18005254e  lea     rcx, [rbx+8]
0x180052552  mov     edx, 1
0x180052557  mov     rax, [rcx]
0x18005255a  mov     rax, [rax+308h]
0x180052561  call    cs:__guard_dispatch_icall_fptr
0x180052567  mov     qword ptr [rsi], 0
0x18005256e  jmp     loc_180018593
```
