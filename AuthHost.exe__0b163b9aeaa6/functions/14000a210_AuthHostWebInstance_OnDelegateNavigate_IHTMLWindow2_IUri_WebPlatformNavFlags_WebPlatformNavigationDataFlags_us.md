# AuthHostWebInstance::OnDelegateNavigate(IHTMLWindow2 *,IUri *,WebPlatformNavFlags,WebPlatformNavigationDataFlags,ushort const *,uchar const *,ulong,ushort const *,IBindCtx *,WebPlatformDelegateFetchDetails const *,ushort const *,IUri *,ushort const *)

- ea: `0x14000a210`
- end: `0x14000a321`
- name: `?OnDelegateNavigate@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@W4WebPlatformNavFlags@@W4WebPlatformNavigationDataFlags@@PEBGPEBEK4PEAUIBindCtx@@PEBUWebPlatformDelegateFetchDetails@@414@Z`
- size: `273`
- prototype: `int __high(struct IHTMLWindow2 *, struct IUri *, enum WebPlatformNavFlags, enum WebPlatformNavigationDataFlags, const unsigned __int16 *, const unsigned __int8 *, unsigned int, const unsigned __int16 *, struct IBindCtx *, const struct WebPlatformDelegateFetchDetails *, const unsigned __int16 *, struct IUri *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000a210`
- `0x14000c2dc`
- `0x14000c3dc`
- `0x14000caa0`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000a304`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a310`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a304`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a310`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AuthHostWebInstance::OnDelegateNavigate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8,
        __int64 a9,
        BSTR bstrString,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  const wchar_t *v15; // rbx
  BSTR v16; // rbp
  __int64 v17; // rcx
  BSTR v19[7]; // [rsp+50h] [rbp-38h] BYREF

  if ( bstrString )
  {
    v19[0] = 0;
    v15 = 0;
    bstrString = 0;
    v16 = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, v19) < 0 )
      v15 = v19[0];
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a13 + 56LL))(a13, &bstrString) < 0 )
      v16 = bstrString;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_SDdSSS(*((_QWORD *)WPP_GLOBAL_Control + 7), a4, a8, a9, a12, (__int64)v16);
    }
    TraceWindow(a2);
    if ( (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v17, (const EVENT_DESCRIPTOR *)DelegateNavigateEvent, v15);
    SysFreeString(bstrString);
    SysFreeString(v19[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x14000a210  mov     r11, rsp
0x14000a213  push    rbx
0x14000a214  push    rbp
0x14000a215  push    rsi
0x14000a216  push    rdi
0x14000a217  sub     rsp, 68h
0x14000a21b  mov     esi, r9d
0x14000a21e  mov     rdi, rdx
0x14000a221  cmp     [rsp+88h+bstrString], 0
0x14000a22a  jz      loc_14000A316
0x14000a230  mov     qword ptr [r11-38h], 0
0x14000a238  xor     ebx, ebx
0x14000a23a  mov     [r11+50h], rbx
0x14000a23e  xor     ebp, ebp
0x14000a240  mov     rax, [r8]
0x14000a243  lea     rdx, [r11-38h]
0x14000a247  mov     rcx, r8
0x14000a24a  mov     rax, [rax+38h]
0x14000a24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a253  test    eax, eax
0x14000a255  cmovs   rbx, [rsp+88h+var_38]
0x14000a25b  mov     rcx, [rsp+88h+arg_60]
0x14000a263  mov     rax, [rcx]
0x14000a266  lea     rdx, [rsp+88h+bstrString]
0x14000a26e  mov     rax, [rax+38h]
0x14000a272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a277  test    eax, eax
0x14000a279  cmovs   rbp, [rsp+88h+bstrString]
0x14000a282  lea     rax, WPP_GLOBAL_Control
0x14000a289  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a290  cmp     rcx, rax
0x14000a293  jz      short loc_14000A2DB
0x14000a295  test    byte ptr [rcx+44h], 4
0x14000a299  jz      short loc_14000A2DB
0x14000a29b  cmp     byte ptr [rcx+41h], 5
0x14000a29f  jb      short loc_14000A2DB
0x14000a2a1  mov     [rsp+88h+var_48], rbp; __int64
0x14000a2a6  mov     rax, [rsp+88h+arg_58]
0x14000a2ae  mov     [rsp+88h+var_50], rax; __int64
0x14000a2b3  mov     rax, [rsp+88h+arg_40]
0x14000a2bb  mov     [rsp+88h+var_58], rax; __int64
0x14000a2c0  mov     eax, dword ptr [rsp+88h+arg_38]
0x14000a2c7  mov     dword ptr [rsp+88h+var_60], eax; char
0x14000a2cb  mov     dword ptr [rsp+88h+var_68], esi; char
0x14000a2cf  mov     r9, rbx
0x14000a2d2  mov     rcx, [rcx+38h]; LoggerHandle
0x14000a2d6  call    WPP_SF_SDdSSS
0x14000a2db  mov     rcx, rdi
0x14000a2de  call    _TraceWindow
0x14000a2e3  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000a2ea  jz      short loc_14000A2FC
0x14000a2ec  mov     r8, rbx
0x14000a2ef  lea     rdx, DelegateNavigateEvent
0x14000a2f6  call    McTemplateU0z_EventWriteTransfer
0x14000a2fb  nop
0x14000a2fc  mov     rcx, [rsp+88h+bstrString]; bstrString
0x14000a304  call    cs:__imp_SysFreeString
0x14000a30a  nop
0x14000a30b  mov     rcx, [rsp+88h+var_38]; bstrString
0x14000a310  call    cs:__imp_SysFreeString
0x14000a316  xor     eax, eax
0x14000a318  add     rsp, 68h
0x14000a31c  pop     rdi
0x14000a31d  pop     rsi
0x14000a31e  pop     rbp
0x14000a31f  pop     rbx
0x14000a320  retn
```
