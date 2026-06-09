# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x140007610`
- end: `0x140007672`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003380`
- `0x14000363c`
- `0x140004d3c`
- `0x14000727c`
- `0x140008694`
- `0x14000a2a1`

## callees

- `0x140007610`
- `0x140007db4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140007643`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007643`

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
0x140007610  mov     [rsp+arg_0], rbx
0x140007615  mov     [rsp+arg_8], rsi
0x14000761a  push    rdi
0x14000761b  sub     rsp, 20h
0x14000761f  mov     rdi, r8
0x140007622  mov     rbx, rcx
0x140007625  test    dl, dl
0x140007627  jz      short loc_14000764F
0x140007629  cmp     qword ptr [rcx+18h], 8
0x14000762e  jb      short loc_14000764F
0x140007630  mov     rsi, [rcx]
0x140007633  test    r8, r8
0x140007636  jz      short loc_140007640
0x140007638  mov     rdx, rsi
0x14000763b  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007640  mov     rcx, rsi
0x140007643  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000764a  nop     dword ptr [rax+rax+00h]
0x14000764f  mov     rsi, [rsp+28h+arg_8]
0x140007654  xor     eax, eax
0x140007656  mov     qword ptr [rbx+18h], 7
0x14000765e  mov     [rbx+10h], rdi
0x140007662  mov     [rbx+rdi*2], ax
0x140007666  mov     rbx, [rsp+28h+arg_0]
0x14000766b  add     rsp, 20h
0x14000766f  pop     rdi
0x140007670  retn
```
