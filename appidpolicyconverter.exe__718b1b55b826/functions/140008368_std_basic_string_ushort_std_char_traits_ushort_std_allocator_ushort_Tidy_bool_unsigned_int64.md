# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x140008368`
- end: `0x1400083c2`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `90`
- prototype: `__int64 __fastcall(_QWORD *, char, __int64)`
- caller_count: `48`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140007e2c`
- `0x140007edc`
- `0x140008188`
- `0x14000829c`
- `0x140009520`
- `0x140009c34`
- `0x140009efc`
- `0x14000a034`
- `0x14000a094`
- `0x14000a560`
- `0x14000a9ac`
- `0x14000ac40`
- `0x14000af60`
- `0x14000bd68`
- `0x14000bee4`
- `0x14000c138`
- `0x14000c810`
- `0x14000cba0`
- `0x14000cdf0`
- `0x14000cf50`
- `0x14000da10`
- `0x14000db9c`
- `0x14000dc30`
- `0x14000dd60`
- `0x14000e190`
- `0x14000e340`
- `0x14000e4f0`
- `0x14000e5e0`
- `0x14000f200`
- `0x14000f44c`
- `0x14000f610`
- `0x14000f958`
- `0x14000fbd8`
- `0x140010a98`
- `0x140010c78`
- `0x140010d90`
- `0x14001108c`
- `0x140011240`
- `0x1400114e0`
- `0x1400119d4`
- `0x1400126cc`
- `0x140012fa0`
- `0x140013044`
- `0x140013338`
- `0x140013808`
- `0x140013918`
- `0x140013fd5`
- `0x140014d78`

## callees

- `0x14000157c`
- `0x140008368`
- `0x140008568`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(_QWORD *a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && a1[3] >= 8u )
  {
    v5 = (void *)*a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  result = 0;
  a1[3] = 7;
  a1[2] = a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x140008368  mov     [rsp+arg_0], rbx
0x14000836d  mov     [rsp+arg_8], rsi
0x140008372  push    rdi
0x140008373  sub     rsp, 20h
0x140008377  mov     rdi, r8
0x14000837a  mov     rbx, rcx
0x14000837d  test    dl, dl
0x14000837f  jz      short loc_1400083A0
0x140008381  cmp     qword ptr [rcx+18h], 8
0x140008386  jb      short loc_1400083A0
0x140008388  mov     rsi, [rcx]
0x14000838b  test    r8, r8
0x14000838e  jz      short loc_140008398
0x140008390  mov     rdx, rsi
0x140008393  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140008398  mov     rcx, rsi; Block
0x14000839b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400083a0  mov     rsi, [rsp+28h+arg_8]
0x1400083a5  xor     eax, eax
0x1400083a7  mov     qword ptr [rbx+18h], 7
0x1400083af  mov     [rbx+10h], rdi
0x1400083b3  mov     [rbx+rdi*2], ax
0x1400083b7  mov     rbx, [rsp+28h+arg_0]
0x1400083bc  add     rsp, 20h
0x1400083c0  pop     rdi
0x1400083c1  retn
```
