# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x1400217e0`
- end: `0x14002188b`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004a60`
- `0x1400217e0`

## import_xrefs

- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1400217fd`
- `msvcp_win!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x1400217fd`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14002186f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14002186f`

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
0x1400217e0  push    rbx
0x1400217e2  push    rbp
0x1400217e3  push    rsi
0x1400217e4  push    rdi
0x1400217e5  push    r14
0x1400217e7  push    r15
0x1400217e9  sub     rsp, 28h
0x1400217ed  cmp     qword ptr [rcx+68h], 0
0x1400217f2  mov     rbx, r8
0x1400217f5  mov     rsi, rdx
0x1400217f8  mov     rdi, rcx
0x1400217fb  jz      short loc_140021805
0x1400217fd  call    cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x140021803  jmp     short loc_14002187E
0x140021805  mov     rax, [rcx+40h]
0x140021809  mov     rbp, rbx
0x14002180c  mov     r9, [rax]
0x14002180f  test    r9, r9
0x140021812  jz      short loc_14002181C
0x140021814  mov     rax, [rcx+58h]
0x140021818  mov     ecx, [rax]
0x14002181a  jmp     short loc_14002181E
0x14002181c  xor     ecx, ecx
0x14002181e  test    rbx, rbx
0x140021821  jle     short loc_140021878
0x140021823  test    ecx, ecx
0x140021825  jle     short loc_140021858
0x140021827  movsxd  r15, ecx
0x14002182a  mov     rcx, r9; void *
0x14002182d  cmp     rbx, r15
0x140021830  cmovl   r15, rbx
0x140021834  mov     r8, r15; Size
0x140021837  call    memcpy_0
0x14002183c  mov     rax, [rdi+58h]
0x140021840  sub     rbx, r15
0x140021843  sub     [rax], r15d
0x140021846  mov     rcx, [rdi+40h]
0x14002184a  movsxd  rax, r15d
0x14002184d  add     [rcx], rax
0x140021850  test    rbx, rbx
0x140021853  jle     short loc_140021878
0x140021855  add     rsi, r15
0x140021858  mov     r9, [rdi+80h]
0x14002185f  test    r9, r9
0x140021862  jz      short loc_140021878
0x140021864  mov     r8, rbx
0x140021867  mov     edx, 1
0x14002186c  mov     rcx, rsi
0x14002186f  call    cs:__imp__o_fwrite
0x140021875  sub     rbx, rax
0x140021878  sub     rbp, rbx
0x14002187b  mov     rax, rbp
0x14002187e  add     rsp, 28h
0x140021882  pop     r15
0x140021884  pop     r14
0x140021886  pop     rdi
0x140021887  pop     rsi
0x140021888  pop     rbp
0x140021889  pop     rbx
0x14002188a  retn
```
