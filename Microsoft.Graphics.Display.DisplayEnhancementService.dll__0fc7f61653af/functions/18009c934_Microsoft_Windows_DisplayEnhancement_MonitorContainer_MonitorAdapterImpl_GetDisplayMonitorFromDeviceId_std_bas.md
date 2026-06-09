# Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18009c934`
- end: `0x18009ca90`
- name: `?GetDisplayMonitorFromDeviceId@MonitorAdapterImpl@MonitorContainer@DisplayEnhancement@Windows@Microsoft@@SA?AV?$ComPtr@UIDisplayMonitor@Display@Devices@Windows@@@WRL@5@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `348`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009cf28`
- `0x18009d6c0`
- `0x18009df78`

## callees

- `0x180013138`
- `0x180013578`
- `0x18002774c`
- `0x18003b1f0`
- `0x1800663d4`
- `0x1800753fc`
- `0x18009c934`
- `0x18009efcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c9fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c9fd`

## string_xrefs

- `0x18009ca6f`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`
- `0x18009c9bf`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayadapter\lib\displayadapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Microsoft::Windows::DisplayEnhancement::MonitorContainer::MonitorAdapterImpl::GetDisplayMonitorFromDeviceId(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rax
  unsigned __int64 v6; // r8
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  int v11; // esi
  __int64 v12; // r8
  __int64 v14; // rax
  __int64 v15; // r9
  int v16; // [rsp+20h] [rbp-60h]
  _QWORD v17[2]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v18[16]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v19[3]; // [rsp+58h] [rbp-28h] BYREF
  __int16 v20; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HSTRING string; // [rsp+B8h] [rbp+38h] BYREF

  string = 0;
  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3);
  if ( !v5 )
  {
    LODWORD(v6) = 0;
    v7 = &dword_180100DC4;
    goto LABEL_7;
  }
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = (const unsigned __int16 *)v5;
LABEL_7:
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v7, v6);
  }
  *a1 = 0;
  v8 = lambda_41cc18e1948b5b0af9c7633853752ecc_::_lambda_41cc18e1948b5b0af9c7633853752ecc_(v18, &string, a1);
  v19[0] = retaddr;
  v19[1] = "onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp";
  v19[2] = 0;
  v20 = 744;
  v17[0] = off_1800F3D18;
  v17[1] = v8;
  v11 = wil::details::ResultFromException(v19, v9, v17);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v10, v12);
      WPP_SF_sS(*(_QWORD *)(v15 + 16), 21, (unsigned int)&WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids, v15, v14);
    }
    MicrosoftTelemetryAssertTriggeredArgs(
      "Microsoft.Graphics.Display.DisplayEnhancementService.dll",
      (unsigned int)v11,
      *a1 == 0);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2FC,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayadapter\\lib\\displayadapter.cpp",
      (const char *)(unsigned int)v11,
      v16);
  }
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x18009c934  mov     [rsp-28h+arg_10], rbx
0x18009c939  mov     [rsp-28h+arg_0], rcx
0x18009c93e  push    rbp
0x18009c93f  push    rsi
0x18009c940  push    rdi
0x18009c941  push    r14
0x18009c943  push    r15
0x18009c945  mov     rbp, rsp
0x18009c948  sub     rsp, 80h
0x18009c94f  mov     rdi, rdx
0x18009c952  mov     rbx, rcx
0x18009c955  xor     r14d, r14d
0x18009c958  mov     [rbp+var_50], r14d
0x18009c95c  mov     [rbp+string], r14
0x18009c960  mov     rcx, rdx
0x18009c963  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009c968  test    rax, rax
0x18009c96b  jz      short loc_18009C98A
0x18009c96d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009c971  inc     r8
0x18009c974  cmp     [rax+r8*2], r14w
0x18009c979  jnz     short loc_18009C971
0x18009c97b  mov     ecx, 0FFFFFFFFh
0x18009c980  cmp     r8, rcx
0x18009c983  ja      short loc_18009C99D
0x18009c985  mov     rdx, rax
0x18009c988  jmp     short loc_18009C994
0x18009c98a  xor     r8d, r8d; unsigned int
0x18009c98d  lea     rdx, dword_180100DC4; unsigned __int16 *
0x18009c994  lea     rcx, [rbp+string]; this
0x18009c998  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18009c99d  mov     [rbx], r14
0x18009c9a0  mov     [rbp+var_50], 1
0x18009c9a7  mov     r8, rbx
0x18009c9aa  lea     rdx, [rbp+string]
0x18009c9ae  lea     rcx, [rbp+var_38]
0x18009c9b2  call    _lambda_41cc18e1948b5b0af9c7633853752ecc____lambda_41cc18e1948b5b0af9c7633853752ecc_
0x18009c9b7  mov     rcx, [rbp+28h]
0x18009c9bb  mov     [rbp+var_28], rcx
0x18009c9bf  lea     r15, aOnecoreuapDriv_42; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18009c9c6  mov     [rbp+var_20], r15
0x18009c9ca  mov     [rbp+var_18], r14
0x18009c9ce  mov     ecx, 2E8h
0x18009c9d3  mov     [rbp+var_10], cx
0x18009c9d7  lea     rcx, off_1800F3D18
0x18009c9de  mov     [rbp+var_48], rcx
0x18009c9e2  mov     [rbp+var_40], rax
0x18009c9e6  lea     r8, [rbp+var_48]
0x18009c9ea  lea     rcx, [rbp+var_28]
0x18009c9ee  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x18009c9f3  mov     esi, eax
0x18009c9f5  test    eax, eax
0x18009c9f7  js      short loc_18009CA1D
0x18009c9f9  mov     rcx, [rbp+string]; string
0x18009c9fd  call    cs:__imp_WindowsDeleteString
0x18009ca03  mov     rax, rbx
0x18009ca06  mov     rbx, [rsp+80h+arg_10]
0x18009ca0e  add     rsp, 80h
0x18009ca15  pop     r15
0x18009ca17  pop     r14
0x18009ca19  pop     rdi
0x18009ca1a  pop     rsi
0x18009ca1b  pop     rbp
0x18009ca1c  retn
0x18009ca1d  lea     rax, WPP_GLOBAL_Control
0x18009ca24  mov     r9, cs:WPP_GLOBAL_Control
0x18009ca2b  cmp     r9, rax
0x18009ca2e  jz      short loc_18009CA63
0x18009ca30  test    dword ptr [r9+1Ch], 100h
0x18009ca38  jz      short loc_18009CA63
0x18009ca3a  cmp     byte ptr [r9+19h], 2
0x18009ca3f  jb      short loc_18009CA63
0x18009ca41  mov     rcx, rdi
0x18009ca44  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009ca49  mov     edx, 15h
0x18009ca4e  mov     qword ptr [rsp+80h+var_60], rax; int
0x18009ca53  lea     r8, WPP_5d1638309ca23a32fb5c63fc7ed00874_Traceguids
0x18009ca5a  mov     rcx, [r9+10h]
0x18009ca5e  call    WPP_SF_sS
0x18009ca63  mov     r8d, r14d
0x18009ca66  cmp     [rbx], r14
0x18009ca69  setz    r8b
0x18009ca6d  mov     edx, esi
0x18009ca6f  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x18009ca76  call    MicrosoftTelemetryAssertTriggeredArgs
0x18009ca7b  mov     rcx, [rbp+28h]; this
0x18009ca7f  mov     r9d, esi; char *
0x18009ca82  mov     r8, r15; unsigned int
0x18009ca85  mov     edx, 2FCh; void *
0x18009ca8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
