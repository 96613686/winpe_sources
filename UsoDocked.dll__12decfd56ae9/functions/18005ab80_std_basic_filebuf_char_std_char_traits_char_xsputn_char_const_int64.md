# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x18005ab80`
- end: `0x18005ac2b`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008554`
- `0x18005ab80`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18005ab9d`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x18005ab9d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005ac0f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005ac0f`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, __int64 a3)
{
  __int64 v3; // rbx
  char *v4; // rsi
  void *v8; // r9
  int v9; // ecx
  size_t v10; // r15
  __int64 v11; // r9

  v3 = a3;
  v4 = a2;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = **(void ***)(a1 + 64);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 88);
  else
    v9 = 0;
  if ( a3 > 0 )
  {
    if ( v9 > 0 )
    {
      v10 = v9;
      if ( a3 < v9 )
        v10 = a3;
      memcpy_0(v8, a2, v10);
      v3 -= v10;
      **(_DWORD **)(a1 + 88) -= v10;
      **(_QWORD **)(a1 + 64) += (int)v10;
      if ( v3 <= 0 )
        return a3 - v3;
      v4 += v10;
    }
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v3 -= _o_fwrite(v4, 1, v3, v11);
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x18005ab80  push    rbx
0x18005ab82  push    rbp
0x18005ab83  push    rsi
0x18005ab84  push    rdi
0x18005ab85  push    r14
0x18005ab87  push    r15
0x18005ab89  sub     rsp, 28h
0x18005ab8d  cmp     qword ptr [rcx+68h], 0
0x18005ab92  mov     rbx, r8
0x18005ab95  mov     rsi, rdx
0x18005ab98  mov     rdi, rcx
0x18005ab9b  jz      short loc_18005ABA5
0x18005ab9d  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x18005aba3  jmp     short loc_18005AC1E
0x18005aba5  mov     rax, [rcx+40h]
0x18005aba9  mov     rbp, rbx
0x18005abac  mov     r9, [rax]
0x18005abaf  test    r9, r9
0x18005abb2  jz      short loc_18005ABBC
0x18005abb4  mov     rax, [rcx+58h]
0x18005abb8  mov     ecx, [rax]
0x18005abba  jmp     short loc_18005ABBE
0x18005abbc  xor     ecx, ecx
0x18005abbe  test    rbx, rbx
0x18005abc1  jle     short loc_18005AC18
0x18005abc3  test    ecx, ecx
0x18005abc5  jle     short loc_18005ABF8
0x18005abc7  movsxd  r15, ecx
0x18005abca  mov     rcx, r9; void *
0x18005abcd  cmp     rbx, r15
0x18005abd0  cmovl   r15, rbx
0x18005abd4  mov     r8, r15; Size
0x18005abd7  call    memcpy_0
0x18005abdc  mov     rax, [rdi+58h]
0x18005abe0  sub     rbx, r15
0x18005abe3  sub     [rax], r15d
0x18005abe6  mov     rcx, [rdi+40h]
0x18005abea  movsxd  rax, r15d
0x18005abed  add     [rcx], rax
0x18005abf0  test    rbx, rbx
0x18005abf3  jle     short loc_18005AC18
0x18005abf5  add     rsi, r15
0x18005abf8  mov     r9, [rdi+80h]
0x18005abff  test    r9, r9
0x18005ac02  jz      short loc_18005AC18
0x18005ac04  mov     r8, rbx
0x18005ac07  mov     edx, 1
0x18005ac0c  mov     rcx, rsi
0x18005ac0f  call    cs:__imp__o_fwrite
0x18005ac15  sub     rbx, rax
0x18005ac18  sub     rbp, rbx
0x18005ac1b  mov     rax, rbp
0x18005ac1e  add     rsp, 28h
0x18005ac22  pop     r15
0x18005ac24  pop     r14
0x18005ac26  pop     rdi
0x18005ac27  pop     rsi
0x18005ac28  pop     rbp
0x18005ac29  pop     rbx
0x18005ac2a  retn
```
