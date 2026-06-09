# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Rehash_for_1(void)

- ea: `0x180011148`
- end: `0x1800111f3`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ`
- size: `171`
- prototype: `int __fastcall(float *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e5a0`
- `0x18000f224`

## callees

- `0x180002104`
- `0x180010f28`
- `0x180011148`

## pseudocode

```c
int __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Rehash_for_1(
        float *a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx

  v1 = *((_QWORD *)a1 + 2);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *((_QWORD *)a1 + 7);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
  v7 = o_ceilf_0(v6 / *a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  return std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Forced_rehash(
           a1,
           v5);
}

```

## disassembly

```asm
0x180011148  mov     [rsp+arg_0], rbx
0x18001114d  push    rdi
0x18001114e  sub     rsp, 20h
0x180011152  mov     rdx, [rcx+10h]
0x180011156  mov     rdi, rcx
0x180011159  add     rdx, 1
0x18001115d  mov     rbx, [rcx+38h]
0x180011161  xorps   xmm0, xmm0
0x180011164  js      short loc_18001116D
0x180011166  cvtsi2ss xmm0, rdx
0x18001116b  jmp     short loc_180011182
0x18001116d  mov     rax, rdx
0x180011170  and     edx, 1
0x180011173  shr     rax, 1
0x180011176  or      rax, rdx
0x180011179  cvtsi2ss xmm0, rax
0x18001117e  addss   xmm0, xmm0
0x180011182  divss   xmm0, dword ptr [rcx]; X
0x180011186  call    _o_ceilf_0
0x18001118b  movss   xmm1, cs:__real@5f000000
0x180011193  xor     ecx, ecx
0x180011195  comiss  xmm0, xmm1
0x180011198  jb      short loc_1800111B0
0x18001119a  subss   xmm0, xmm1
0x18001119e  comiss  xmm0, xmm1
0x1800111a1  jnb     short loc_1800111B0
0x1800111a3  mov     rax, 8000000000000000h
0x1800111ad  mov     rcx, rax
0x1800111b0  cvttss2si rax, xmm0
0x1800111b5  add     rax, rcx
0x1800111b8  mov     ecx, 8
0x1800111bd  cmp     rax, rcx
0x1800111c0  cmova   rcx, rax
0x1800111c4  cmp     rbx, rcx
0x1800111c7  jnb     short loc_1800111DE
0x1800111c9  cmp     rbx, 200h
0x1800111d0  jnb     short loc_1800111DB
0x1800111d2  shl     rbx, 3
0x1800111d6  cmp     rbx, rcx
0x1800111d9  jnb     short loc_1800111DE
0x1800111db  mov     rbx, rcx
0x1800111de  mov     rdx, rbx
0x1800111e1  mov     rcx, rdi
0x1800111e4  mov     rbx, [rsp+28h+arg_0]
0x1800111e9  add     rsp, 20h
0x1800111ed  pop     rdi
0x1800111ee  jmp     ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Forced_rehash(unsigned __int64)
```
