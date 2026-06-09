# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x180005950`
- end: `0x1800059fd`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `51`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e40`
- `0x180002000`
- `0x180002080`
- `0x1800020c0`
- `0x1800021e0`
- `0x180002220`
- `0x1800022e0`
- `0x1800026c0`
- `0x1800027b0`
- `0x1800027f0`
- `0x180002830`
- `0x180002910`
- `0x180002970`
- `0x1800029b0`
- `0x1800029f0`
- `0x180002a30`
- `0x180002a70`
- `0x180002af0`
- `0x180002b70`
- `0x180002bf0`
- `0x180002c70`
- `0x180002cf0`
- `0x180002d70`
- `0x180002db0`
- `0x180002df0`
- `0x180002e30`
- `0x180002e70`
- `0x180006e00`
- `0x18000c648`
- `0x18000c9a0`
- `0x18000ca70`
- `0x18000cb40`
- `0x18000ccd0`
- `0x180010488`
- `0x180014600`
- `0x180016bfc`
- `0x1800171f0`
- `0x18001757c`
- `0x180017ee0`
- `0x1800184e8`
- `0x180018a70`
- `0x180018d94`
- `0x1800199a0`
- `0x18001ac84`
- `0x18001bb28`
- `0x18001bcac`
- `0x18001cad0`
- `0x18001cdb8`
- `0x18001e824`
- `0x1800236e0`

## callees

- `0x18000490d`
- `0x1800058d8`
- `0x180005950`
- `0x18000a998`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005950  push    rbx
0x180005952  push    rbp
0x180005953  push    rsi
0x180005954  push    rdi
0x180005955  sub     rsp, 28h
0x180005959  mov     rax, 7FFFFFFFFFFFFFFEh
0x180005963  mov     rbx, r8
0x180005966  mov     rbp, rdx
0x180005969  mov     rsi, rcx
0x18000596c  cmp     r8, rax
0x18000596f  ja      loc_1800059F7
0x180005975  cmp     rbx, 7
0x180005979  ja      short loc_18000599A
0x18000597b  mov     [rcx+10h], rbx
0x18000597f  add     rbx, rbx
0x180005982  mov     r8, rbx; Size
0x180005985  mov     qword ptr [rcx+18h], 7
0x18000598d  call    memcpy_0
0x180005992  xor     eax, eax
0x180005994  mov     [rbx+rsi], ax
0x180005998  jmp     short loc_1800059EE
0x18000599a  mov     rcx, rbx
0x18000599d  or      rcx, 7
0x1800059a1  cmp     rcx, rax
0x1800059a4  ja      short loc_1800059B5
0x1800059a6  mov     edx, 0Ah
0x1800059ab  mov     rax, rcx
0x1800059ae  cmp     rcx, rdx
0x1800059b1  cmovb   rax, rdx
0x1800059b5  lea     rdx, [rsp+48h+arg_0]
0x1800059ba  mov     [rsp+48h+arg_0], rax
0x1800059bf  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800059c4  mov     rcx, [rsp+48h+arg_0]
0x1800059c9  mov     rdx, rbp; Src
0x1800059cc  mov     [rsi+10h], rbx
0x1800059d0  mov     rdi, rax
0x1800059d3  mov     [rsi+18h], rcx
0x1800059d7  add     rbx, rbx
0x1800059da  mov     rcx, rax; void *
0x1800059dd  mov     [rsi], rax
0x1800059e0  mov     r8, rbx; Size
0x1800059e3  call    memcpy_0
0x1800059e8  xor     eax, eax
0x1800059ea  mov     [rbx+rdi], ax
0x1800059ee  add     rsp, 28h
0x1800059f2  pop     rdi
0x1800059f3  pop     rsi
0x1800059f4  pop     rbp
0x1800059f5  pop     rbx
0x1800059f6  retn
0x1800059f7  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
