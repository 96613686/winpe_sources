# SHRegSetPercentW

- ea: `0x18000ca70`
- end: `0x18000cb1d`
- name: `SHRegSetPercentW`
- size: `173`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000470c`
- `0x180009d00`
- `0x18000ca70`
- `0x180012fc0`

## pseudocode

```c
int __fastcall SHRegSetPercentW(HKEY a1, unsigned __int16 *a2, unsigned __int16 *a3, double a4, unsigned int a5)
{
  int result; // eax
  unsigned __int16 v9[264]; // [rsp+20h] [rbp-458h] BYREF
  unsigned __int16 v10[264]; // [rsp+230h] [rbp-248h] BYREF

  result = StringCchPrintfW(v9, 0x104u, L"%%#.%df%%%%", a5);
  if ( result >= 0 )
  {
    result = StringCchPrintfW(v10, 0x104u, v9, a4);
    if ( result >= 0 )
      return HrRegSetValueStringW(a1, a2, a3, v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000ca70  mov     rax, rsp
0x18000ca73  push    rbx
0x18000ca74  push    rsi
0x18000ca75  push    rdi
0x18000ca76  sub     rsp, 460h
0x18000ca7d  movaps  xmmword ptr [rax-28h], xmm6
0x18000ca81  mov     rax, cs:__security_cookie
0x18000ca88  xor     rax, rsp
0x18000ca8b  mov     [rsp+478h+var_38], rax
0x18000ca93  mov     r9d, [rsp+478h+arg_20]
0x18000ca9b  mov     rsi, r8
0x18000ca9e  mov     rdi, rdx
0x18000caa1  lea     r8, aDf; "%%#.%df%%%%"
0x18000caa8  mov     rbx, rcx
0x18000caab  mov     edx, 104h; unsigned __int64
0x18000cab0  lea     rcx, [rsp+478h+var_458]; unsigned __int16 *
0x18000cab5  movaps  xmm6, xmm3
0x18000cab8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cabd  test    eax, eax
0x18000cabf  js      short loc_18000CAFA
0x18000cac1  movaps  xmm3, xmm6
0x18000cac4  lea     r8, [rsp+478h+var_458]; unsigned __int16 *
0x18000cac9  movq    r9, xmm6
0x18000cace  lea     rcx, [rsp+478h+var_248]; unsigned __int16 *
0x18000cad6  mov     edx, 104h; unsigned __int64
0x18000cadb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cae0  test    eax, eax
0x18000cae2  js      short loc_18000CAFA
0x18000cae4  lea     r9, [rsp+478h+var_248]; unsigned __int16 *
0x18000caec  mov     r8, rsi; unsigned __int16 *
0x18000caef  mov     rdx, rdi; unsigned __int16 *
0x18000caf2  mov     rcx, rbx; HKEY
0x18000caf5  call    ?HrRegSetValueStringW@@YAJPEAUHKEY__@@PEBG11@Z; HrRegSetValueStringW(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18000cafa  mov     rcx, [rsp+478h+var_38]
0x18000cb02  xor     rcx, rsp; StackCookie
0x18000cb05  call    __security_check_cookie
0x18000cb0a  movaps  xmm6, [rsp+478h+var_28]
0x18000cb12  add     rsp, 460h
0x18000cb19  pop     rdi
0x18000cb1a  pop     rsi
0x18000cb1b  pop     rbx
0x18000cb1c  retn
```
