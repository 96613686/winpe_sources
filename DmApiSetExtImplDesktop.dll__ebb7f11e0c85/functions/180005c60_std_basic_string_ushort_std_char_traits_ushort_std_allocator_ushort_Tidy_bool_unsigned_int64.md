# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x180005c60`
- end: `0x180005cc2`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `98`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002fe0`
- `0x1800059a4`
- `0x180006840`
- `0x18000a681`

## callees

- `0x180005c60`
- `0x1800062dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005c93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005c93`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = *a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = (void *)7;
  a1[2] = (void *)a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180005c60  mov     [rsp+arg_0], rbx
0x180005c65  mov     [rsp+arg_8], rsi
0x180005c6a  push    rdi
0x180005c6b  sub     rsp, 20h
0x180005c6f  mov     rdi, r8
0x180005c72  mov     rbx, rcx
0x180005c75  test    dl, dl
0x180005c77  jz      short loc_180005C9F
0x180005c79  cmp     qword ptr [rcx+18h], 8
0x180005c7e  jb      short loc_180005C9F
0x180005c80  mov     rsi, [rcx]
0x180005c83  test    r8, r8
0x180005c86  jz      short loc_180005C90
0x180005c88  mov     rdx, rsi
0x180005c8b  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180005c90  mov     rcx, rsi
0x180005c93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005c9a  nop     dword ptr [rax+rax+00h]
0x180005c9f  mov     rsi, [rsp+28h+arg_8]
0x180005ca4  xor     eax, eax
0x180005ca6  mov     qword ptr [rbx+18h], 7
0x180005cae  mov     [rbx+10h], rdi
0x180005cb2  mov     [rbx+rdi*2], ax
0x180005cb6  mov     rbx, [rsp+28h+arg_0]
0x180005cbb  add     rsp, 20h
0x180005cbf  pop     rdi
0x180005cc0  retn
```
