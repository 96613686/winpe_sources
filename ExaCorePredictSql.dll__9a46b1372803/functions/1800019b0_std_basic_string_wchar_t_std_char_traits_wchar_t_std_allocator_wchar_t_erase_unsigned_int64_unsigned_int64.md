# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::erase(unsigned __int64,unsigned __int64)

- ea: `0x1800019b0`
- end: `0x180001a57`
- name: `?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001670`

## callees

- `0x1800019b0`
- `0x180001ae0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180001a24`
- `VCRUNTIME140!memmove` at `0x180001a24`

## pseudocode

```c
_QWORD *__fastcall std::wstring::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  _QWORD *v4; // rbx
  _QWORD *v6; // rax
  unsigned __int64 v7; // rdi
  bool v8; // cf
  _QWORD *v9; // rcx

  v3 = a1[2];
  v4 = a1;
  if ( v3 < a2 )
    std::wstring::_Xran(a1, a2, a3, a3);
  if ( v3 - a2 > a3 )
  {
    if ( a3 )
    {
      if ( a1[3] < 8u )
        v6 = a1;
      else
        v6 = (_QWORD *)*a1;
      v7 = v3 - a3;
      if ( v7 != a2 )
        memmove((char *)v6 + 2 * a2, (char *)v6 + 2 * a2 + 2 * a3, 2 * (v7 - a2));
      v8 = v4[3] < 8u;
      v4[2] = v7;
      if ( v8 )
        v9 = v4;
      else
        v9 = (_QWORD *)*v4;
      *((_WORD *)v9 + v7) = 0;
    }
    return v4;
  }
  else
  {
    a1[2] = a2;
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    *((_WORD *)a1 + a2) = 0;
    return v4;
  }
}

```

## disassembly

```asm
0x1800019b0  mov     [rsp+arg_0], rbx
0x1800019b5  push    rdi
0x1800019b6  sub     rsp, 20h
0x1800019ba  mov     rdi, [rcx+10h]
0x1800019be  mov     r9, r8
0x1800019c1  mov     rbx, rcx
0x1800019c4  cmp     rdi, rdx
0x1800019c7  jb      loc_180001A51
0x1800019cd  mov     rax, rdi
0x1800019d0  sub     rax, rdx
0x1800019d3  cmp     rax, r8
0x1800019d6  ja      short loc_1800019FA
0x1800019d8  mov     [rcx+10h], rdx
0x1800019dc  cmp     qword ptr [rcx+18h], 8
0x1800019e1  jb      short loc_1800019E6
0x1800019e3  mov     rcx, [rcx]
0x1800019e6  xor     eax, eax
0x1800019e8  mov     [rcx+rdx*2], ax
0x1800019ec  mov     rax, rbx
0x1800019ef  mov     rbx, [rsp+28h+arg_0]
0x1800019f4  add     rsp, 20h
0x1800019f8  pop     rdi
0x1800019f9  retn
0x1800019fa  test    r9, r9
0x1800019fd  jz      short loc_180001A43
0x1800019ff  cmp     qword ptr [rcx+18h], 8
0x180001a04  jb      short loc_180001A0B
0x180001a06  mov     rax, [rcx]
0x180001a09  jmp     short loc_180001A0E
0x180001a0b  mov     rax, rbx
0x180001a0e  sub     rdi, r9
0x180001a11  lea     rcx, [rax+rdx*2]; void *
0x180001a15  mov     r8, rdi
0x180001a18  sub     r8, rdx
0x180001a1b  jz      short loc_180001A2A
0x180001a1d  add     r8, r8; Size
0x180001a20  lea     rdx, [rcx+r9*2]; Src
0x180001a24  call    cs:__imp_memmove
0x180001a2a  cmp     qword ptr [rbx+18h], 8
0x180001a2f  mov     [rbx+10h], rdi
0x180001a33  jb      short loc_180001A3A
0x180001a35  mov     rcx, [rbx]
0x180001a38  jmp     short loc_180001A3D
0x180001a3a  mov     rcx, rbx
0x180001a3d  xor     eax, eax
0x180001a3f  mov     [rcx+rdi*2], ax
0x180001a43  mov     rax, rbx
0x180001a46  mov     rbx, [rsp+28h+arg_0]
0x180001a4b  add     rsp, 20h
0x180001a4f  pop     rdi
0x180001a50  retn
0x180001a51  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
```
