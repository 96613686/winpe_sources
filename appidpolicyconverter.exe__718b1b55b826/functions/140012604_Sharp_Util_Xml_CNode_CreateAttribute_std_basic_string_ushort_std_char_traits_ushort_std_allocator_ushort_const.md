# Sharp::Util::Xml::CNode::CreateAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012604`
- end: `0x1400126c6`
- name: `?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `194`
- prototype: `HRESULT __fastcall(__int64, const unsigned __int16 *, const OLECHAR *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ac40`
- `0x14000cdf0`
- `0x14000dd60`
- `0x14000f610`
- `0x140011240`
- `0x1400126cc`

## callees

- `0x140002b90`
- `0x1400070e4`
- `0x140012278`
- `0x140012604`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14001266a`
- `OLEAUT32!__imp_SysAllocString` at `0x14001266a`
- `OLEAUT32!__imp_VariantClear` at `0x14001265c`
- `OLEAUT32!__imp_VariantClear` at `0x1400126b7`
- `OLEAUT32!__imp_VariantClear` at `0x14001265c`
- `OLEAUT32!__imp_VariantClear` at `0x1400126b7`

## pseudocode

```c
HRESULT __fastcall Sharp::Util::Xml::CNode::CreateAttribute(__int64 a1, const unsigned __int16 *a2, const OLECHAR *a3)
{
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  if ( *((_QWORD *)a3 + 3) >= 8u )
    a3 = *(const OLECHAR **)a3;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  if ( !pvarg.llVal && a3 )
  {
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(pvarg.cyVal.Hi);
  }
  Sharp::Util::Xml::CNode::CreateAttribute(a1, a2, &pvarg);
  return VariantClear(&pvarg);
}

```

## disassembly

```asm
0x140012604  push    rbx
0x140012606  push    rbp
0x140012607  push    rsi
0x140012608  push    rdi
0x140012609  sub     rsp, 48h
0x14001260d  mov     rbx, r8
0x140012610  mov     rdi, rdx
0x140012613  mov     rsi, rcx
0x140012616  lea     rax, WPP_GLOBAL_Control
0x14001261d  mov     ebp, 8
0x140012622  mov     rcx, cs:WPP_GLOBAL_Control
0x140012629  cmp     rcx, rax
0x14001262c  jz      short loc_140012647
0x14001262e  test    [rcx+1Ch], bpl
0x140012632  jz      short loc_140012647
0x140012634  lea     edx, [rbp+2Bh]
0x140012637  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x14001263e  mov     rcx, [rcx+10h]
0x140012642  call    WPP_SF_
0x140012647  cmp     [rbx+18h], rbp
0x14001264b  jb      short loc_140012650
0x14001264d  mov     rbx, [rbx]
0x140012650  xor     eax, eax
0x140012652  mov     word ptr [rsp+68h+pvarg], ax
0x140012657  lea     rcx, [rsp+68h+pvarg]; pvarg
0x14001265c  call    cs:__imp_VariantClear
0x140012662  mov     word ptr [rsp+68h+pvarg], bp
0x140012667  mov     rcx, rbx; psz
0x14001266a  call    cs:__imp_SysAllocString
0x140012670  mov     dword ptr [rsp+68h+pvarg+8], eax
0x140012674  mov     rcx, rax
0x140012677  sar     rcx, 20h; int
0x14001267b  mov     dword ptr [rsp+68h+pvarg+0Ch], ecx
0x14001267f  test    rax, rax
0x140012682  jnz     short loc_1400126A1
0x140012684  test    rbx, rbx
0x140012687  jz      short loc_1400126A1
0x140012689  mov     eax, 0Ah
0x14001268e  mov     word ptr [rsp+68h+pvarg], ax
0x140012693  mov     dword ptr [rsp+68h+pvarg+8], 8007000Eh
0x14001269b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400126a1  lea     r8, [rsp+68h+pvarg]
0x1400126a6  mov     rdx, rdi
0x1400126a9  mov     rcx, rsi
0x1400126ac  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCComVariant@ATL@@@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,ATL::CComVariant const &)
0x1400126b1  nop
0x1400126b2  lea     rcx, [rsp+68h+pvarg]; pvarg
0x1400126b7  call    cs:__imp_VariantClear
0x1400126bd  add     rsp, 48h
0x1400126c1  pop     rdi
0x1400126c2  pop     rsi
0x1400126c3  pop     rbp
0x1400126c4  pop     rbx
0x1400126c5  retn
```
