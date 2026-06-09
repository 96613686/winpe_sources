# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x180033ef0`
- end: `0x180033f9b`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800085bc`
- `0x180033ef0`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x180033f0d`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x180033f0d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180033f7f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180033f7f`

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
0x180033ef0  push    rbx
0x180033ef2  push    rbp
0x180033ef3  push    rsi
0x180033ef4  push    rdi
0x180033ef5  push    r14
0x180033ef7  push    r15
0x180033ef9  sub     rsp, 28h
0x180033efd  cmp     qword ptr [rcx+68h], 0
0x180033f02  mov     rbx, r8
0x180033f05  mov     rsi, rdx
0x180033f08  mov     rdi, rcx
0x180033f0b  jz      short loc_180033F15
0x180033f0d  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x180033f13  jmp     short loc_180033F8E
0x180033f15  mov     rax, [rcx+40h]
0x180033f19  mov     rbp, rbx
0x180033f1c  mov     r9, [rax]
0x180033f1f  test    r9, r9
0x180033f22  jz      short loc_180033F2C
0x180033f24  mov     rax, [rcx+58h]
0x180033f28  mov     ecx, [rax]
0x180033f2a  jmp     short loc_180033F2E
0x180033f2c  xor     ecx, ecx
0x180033f2e  test    rbx, rbx
0x180033f31  jle     short loc_180033F88
0x180033f33  test    ecx, ecx
0x180033f35  jle     short loc_180033F68
0x180033f37  movsxd  r15, ecx
0x180033f3a  mov     rcx, r9; void *
0x180033f3d  cmp     rbx, r15
0x180033f40  cmovl   r15, rbx
0x180033f44  mov     r8, r15; Size
0x180033f47  call    memcpy_0
0x180033f4c  mov     rax, [rdi+58h]
0x180033f50  sub     rbx, r15
0x180033f53  sub     [rax], r15d
0x180033f56  mov     rcx, [rdi+40h]
0x180033f5a  movsxd  rax, r15d
0x180033f5d  add     [rcx], rax
0x180033f60  test    rbx, rbx
0x180033f63  jle     short loc_180033F88
0x180033f65  add     rsi, r15
0x180033f68  mov     r9, [rdi+80h]
0x180033f6f  test    r9, r9
0x180033f72  jz      short loc_180033F88
0x180033f74  mov     r8, rbx
0x180033f77  mov     edx, 1
0x180033f7c  mov     rcx, rsi
0x180033f7f  call    cs:__imp__o_fwrite
0x180033f85  sub     rbx, rax
0x180033f88  sub     rbp, rbx
0x180033f8b  mov     rax, rbp
0x180033f8e  add     rsp, 28h
0x180033f92  pop     r15
0x180033f94  pop     r14
0x180033f96  pop     rdi
0x180033f97  pop     rsi
0x180033f98  pop     rbp
0x180033f99  pop     rbx
0x180033f9a  retn
```
