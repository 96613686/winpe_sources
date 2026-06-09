# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x180009a68`
- end: `0x180009b03`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VAppPrinterEndPointBase@AppMon@@@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008428`
- `0x18000ad94`
- `0x18000bafc`

## callees

- `0x180001f94`
- `0x180009a68`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<AppMon::AppPrinterEndPointBase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<AppMon::AppPrinterEndPointBase>>>,0>>::_Desired_grow_bucket_count(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  float v3; // xmm0_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx

  v2 = *(_QWORD *)(a1 + 56);
  if ( a2 < 0 )
    v3 = (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1))
       + (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1));
  else
    v3 = (float)(int)a2;
  v4 = o_ceilf_0(v3 / *(float *)a1);
  v5 = 0;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v5 = 0x8000000000000000uLL;
  }
  v6 = 8;
  if ( v5 + (unsigned int)(int)v4 > 8 )
    v6 = v5 + (unsigned int)(int)v4;
  if ( v2 >= v6 )
    return v2;
  if ( v2 < 0x200 && 8 * v2 >= v6 )
    return 8 * v2;
  return v6;
}

```

## disassembly

```asm
0x180009a68  push    rbx
0x180009a6a  sub     rsp, 20h
0x180009a6e  mov     rbx, [rcx+38h]
0x180009a72  xorps   xmm0, xmm0
0x180009a75  test    rdx, rdx
0x180009a78  js      short loc_180009A81
0x180009a7a  cvtsi2ss xmm0, rdx
0x180009a7f  jmp     short loc_180009A96
0x180009a81  mov     rax, rdx
0x180009a84  and     edx, 1
0x180009a87  shr     rax, 1
0x180009a8a  or      rax, rdx
0x180009a8d  cvtsi2ss xmm0, rax
0x180009a92  addss   xmm0, xmm0
0x180009a96  divss   xmm0, dword ptr [rcx]; X
0x180009a9a  call    _o_ceilf_0
0x180009a9f  movss   xmm1, cs:__real@5f000000
0x180009aa7  xor     eax, eax
0x180009aa9  comiss  xmm0, xmm1
0x180009aac  jb      short loc_180009AC4
0x180009aae  subss   xmm0, xmm1
0x180009ab2  comiss  xmm0, xmm1
0x180009ab5  jnb     short loc_180009AC4
0x180009ab7  mov     rcx, 8000000000000000h
0x180009ac1  mov     rax, rcx
0x180009ac4  mov     edx, 8
0x180009ac9  cvttss2si rcx, xmm0
0x180009ace  add     rcx, rax
0x180009ad1  cmp     rcx, rdx
0x180009ad4  cmova   rdx, rcx
0x180009ad8  cmp     rbx, rdx
0x180009adb  jb      short loc_180009AE2
0x180009add  mov     rax, rbx
0x180009ae0  jmp     short loc_180009AFD
0x180009ae2  cmp     rbx, 200h
0x180009ae9  jnb     short loc_180009AFA
0x180009aeb  lea     rax, ds:0[rbx*8]
0x180009af3  cmp     rax, rdx
0x180009af6  cmovnb  rdx, rax
0x180009afa  mov     rax, rdx
0x180009afd  add     rsp, 20h
0x180009b01  pop     rbx
0x180009b02  retn
```
