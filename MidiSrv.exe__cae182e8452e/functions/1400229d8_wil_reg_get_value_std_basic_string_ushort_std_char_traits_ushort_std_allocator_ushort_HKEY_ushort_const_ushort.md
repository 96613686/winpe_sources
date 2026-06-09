# wil::reg::get_value<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1400229d8`
- end: `0x140022b80`
- name: `??$get_value@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@reg@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1@Z`
- size: `424`
- prototype: `_QWORD *__fastcall(_QWORD *Src, HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140023678`
- `0x1400238a4`

## callees

- `0x140005170`
- `0x14001f64c`
- `0x1400229d8`
- `0x1400261b4`
- `0x140026528`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140022a64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140022a64`

## string_xrefs

- `0x140022b3a`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x140022b54`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x140022b6e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::reg::get_value<std::wstring>(_QWORD *Src, HKEY hkey, LPCWSTR lpSubKey, LPCWSTR lpValue)
{
  int i; // eax
  void *pvData; // rax
  int ValueW; // eax
  _QWORD *v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  _QWORD *v15; // rsi
  int v16; // eax
  char *v17; // rbx
  __int64 trivial_2; // rax
  int pdwType; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD pcbData; // [rsp+78h] [rbp+10h] BYREF

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  for ( i = 2 * *((_DWORD *)Src + 4) + 2; ; i = pcbData )
  {
    pcbData = i;
    if ( Src[3] <= 7u )
      pvData = Src;
    else
      pvData = (void *)*Src;
    ValueW = RegGetValueW(hkey, lpSubKey, lpValue, 0x10000006u, 0, pvData, &pcbData);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW == -2147024662 )
    {
      v12 = pcbData;
      goto LABEL_19;
    }
    if ( ValueW < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)ValueW,
        pdwType);
    v11 = Src[3] <= 7u ? Src : (_QWORD *)*Src;
    v12 = pcbData;
    if ( v11 || !pcbData )
      break;
LABEL_19:
    v16 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(Src, v12);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v16,
        pdwType);
  }
  if ( 2 * *((_DWORD *)Src + 4) + 2 != pcbData )
  {
    v13 = wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(Src, pcbData);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v13,
        pdwType);
  }
  v14 = Src[2];
  if ( Src[3] <= 7u )
    v15 = Src;
  else
    v15 = (_QWORD *)*Src;
  if ( v14 )
  {
    v17 = (char *)v15 + 2 * v14;
    trivial_2 = _std_find_trivial_2(v15, v17, 0);
    if ( (char *)trivial_2 != v17 && (trivial_2 - (__int64)v15) >> 1 != -1 )
      std::wstring::resize(Src);
  }
  return Src;
}

```

## disassembly

```asm
0x1400229d8  mov     [rsp+arg_10], rbx
0x1400229dd  mov     [rsp+arg_0], rcx
0x1400229e2  push    rbp
0x1400229e3  push    rsi
0x1400229e4  push    rdi
0x1400229e5  sub     rsp, 50h
0x1400229e9  mov     rbx, r9
0x1400229ec  mov     rsi, r8
0x1400229ef  mov     rbp, rdx
0x1400229f2  mov     rdi, rcx
0x1400229f5  mov     [rsp+68h+var_28], 0
0x1400229fd  xorps   xmm0, xmm0
0x140022a00  movups  xmmword ptr [rcx], xmm0
0x140022a03  mov     qword ptr [rcx+10h], 0
0x140022a0b  mov     qword ptr [rcx+18h], 7
0x140022a13  xor     eax, eax
0x140022a15  mov     [rcx], ax
0x140022a18  mov     [rsp+68h+var_28], 1
0x140022a20  mov     eax, [rcx+10h]
0x140022a23  lea     eax, ds:2[rax*2]
0x140022a2a  mov     [rsp+68h+arg_8], eax
0x140022a2e  cmp     qword ptr [rdi+18h], 7
0x140022a33  jbe     short loc_140022A3A
0x140022a35  mov     rax, [rdi]
0x140022a38  jmp     short loc_140022A3D
0x140022a3a  mov     rax, rdi
0x140022a3d  lea     rcx, [rsp+68h+arg_8]
0x140022a42  mov     [rsp+68h+pcbData], rcx; pcbData
0x140022a47  mov     [rsp+68h+pvData], rax; pvData
0x140022a4c  mov     [rsp+68h+pdwType], 0; int
0x140022a55  mov     r9d, 10000006h; dwFlags
0x140022a5b  mov     r8, rbx; lpValue
0x140022a5e  mov     rdx, rsi; lpSubKey
0x140022a61  mov     rcx, rbp; hkey
0x140022a64  call    cs:__imp_RegGetValueW
0x140022a6a  test    eax, eax
0x140022a6c  jle     short loc_140022A76
0x140022a6e  movzx   eax, ax
0x140022a71  or      eax, 80070000h
0x140022a76  cmp     eax, 800700EAh
0x140022a7b  jz      short loc_140022ACF
0x140022a7d  test    eax, eax
0x140022a7f  js      loc_140022B32
0x140022a85  cmp     qword ptr [rdi+18h], 7
0x140022a8a  jbe     short loc_140022A91
0x140022a8c  mov     rax, [rdi]
0x140022a8f  jmp     short loc_140022A94
0x140022a91  mov     rax, rdi
0x140022a94  mov     edx, [rsp+68h+arg_8]
0x140022a98  test    rax, rax
0x140022a9b  jnz     short loc_140022AA1
0x140022a9d  test    edx, edx
0x140022a9f  jnz     short loc_140022AD3
0x140022aa1  mov     eax, [rdi+10h]
0x140022aa4  lea     eax, ds:2[rax*2]
0x140022aab  cmp     eax, edx
0x140022aad  jz      short loc_140022ABF
0x140022aaf  mov     rcx, rdi
0x140022ab2  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x140022ab7  test    eax, eax
0x140022ab9  js      loc_140022B66
0x140022abf  mov     rax, [rdi+10h]
0x140022ac3  cmp     qword ptr [rdi+18h], 7
0x140022ac8  jbe     short loc_140022AE8
0x140022aca  mov     rsi, [rdi]
0x140022acd  jmp     short loc_140022AEB
0x140022acf  mov     edx, [rsp+68h+arg_8]
0x140022ad3  mov     rcx, rdi
0x140022ad6  call    ?resize_buffer_bytes@reg_value_type_info@reg_view_details@reg@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; wil::reg::reg_view_details::reg_value_type_info::resize_buffer_bytes(std::wstring &,ulong)
0x140022adb  test    eax, eax
0x140022add  js      short loc_140022B4C
0x140022adf  mov     eax, [rsp+68h+arg_8]
0x140022ae3  jmp     loc_140022A2A
0x140022ae8  mov     rsi, rdi
0x140022aeb  test    rax, rax
0x140022aee  jz      short loc_140022B1F
0x140022af0  lea     rbx, [rsi+rax*2]
0x140022af4  xor     r8d, r8d
0x140022af7  mov     rdx, rbx
0x140022afa  mov     rcx, rsi
0x140022afd  call    __std_find_trivial_2
0x140022b02  cmp     rax, rbx
0x140022b05  jz      short loc_140022B1F
0x140022b07  sub     rax, rsi
0x140022b0a  sar     rax, 1
0x140022b0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022b11  jz      short loc_140022B1F
0x140022b13  mov     rdx, rax
0x140022b16  mov     rcx, rdi; Src
0x140022b19  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x140022b1e  nop
0x140022b1f  mov     rax, rdi
0x140022b22  mov     rbx, [rsp+68h+arg_10]
0x140022b2a  add     rsp, 50h
0x140022b2e  pop     rdi
0x140022b2f  pop     rsi
0x140022b30  pop     rbp
0x140022b31  retn
0x140022b32  mov     rcx, [rsp+68h]; this
0x140022b37  mov     r9d, eax; char *
0x140022b3a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140022b41  mov     edx, 1CBEh; void *
0x140022b46  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140022b4c  mov     rcx, [rsp+68h]; this
0x140022b51  mov     r9d, eax; char *
0x140022b54  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140022b5b  mov     edx, 1CBEh; void *
0x140022b60  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140022b66  mov     rcx, [rsp+68h]; this
0x140022b6b  mov     r9d, eax; char *
0x140022b6e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140022b75  mov     edx, 1CBEh; void *
0x140022b7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
