# FrameWindow::ShowHideConsole(void)

- ea: `0x180028a60`
- end: `0x180028d32`
- name: `?ShowHideConsole@FrameWindow@@AEAAXXZ`
- size: `722`
- prototype: `void __fastcall(FrameWindow *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x1800232e8`
- `0x180023660`
- `0x18002b910`

## callees

- `0x180001800`
- `0x18000193c`
- `0x180020528`
- `0x180020bac`
- `0x180021e24`
- `0x180022204`
- `0x180022f44`
- `0x180024b9c`
- `0x180028834`
- `0x180028a60`
- `0x1800290f4`
- `0x18002f988`
- `0x180035010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180028be1`
- `ADVAPI32!RegCloseKey` at `0x180028be1`
- `ADVAPI32!RegSetValueExW` at `0x180028bd3`
- `ADVAPI32!RegSetValueExW` at `0x180028bd3`
- `USER32!ShowWindow` at `0x180028c28`
- `USER32!ShowWindow` at `0x180028c28`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FrameWindow::ShowHideConsole(FrameWindow *this)
{
  _BYTE *v2; // rsi
  void *v3; // rbx
  signed int v4; // edx
  bool v5; // si
  struct ATL::CRegKey *v6; // rdx
  HKEY v7; // rcx
  HKEY v8; // rsi
  __int64 v9; // rax
  unsigned int v10; // edx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  int *lpData; // [rsp+20h] [rbp-99h]
  char v14; // [rsp+30h] [rbp-89h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  char *v17; // [rsp+48h] [rbp-71h]
  __int64 v18; // [rsp+50h] [rbp-69h]
  _BYTE *v19; // [rsp+58h] [rbp-61h]
  void *v20; // [rsp+60h] [rbp-59h]
  _QWORD v21[7]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD *v22; // [rsp+A8h] [rbp-11h]
  _QWORD v23[7]; // [rsp+B0h] [rbp-9h] BYREF
  _QWORD *v24; // [rsp+E8h] [rbp+2Fh]

  v2 = (char *)this + 439;
  if ( *((_BYTE *)this + 439) )
    return;
  *v2 = 1;
  v14 = 0;
  hKey = (HKEY)((char *)this + 439);
  v17 = &v14;
  LOBYTE(v18) = 1;
  v3 = operator new(0x18u);
  *(_QWORD *)Data = v3;
  *(_OWORD *)v3 = 0;
  *((_DWORD *)v3 + 2) = 1;
  *((_DWORD *)v3 + 3) = 1;
  *(_QWORD *)v3 = &std::_Ref_count_resource<bool *,_lambda_37637c8b52e7f5910352e2380eaa98ac_>::`vftable';
  *((_QWORD *)v3 + 2) = v2;
  v19 = v2;
  v20 = v3;
  if ( ((*((_DWORD *)this + 138) + 1) & 0xFFFFFFFD) != 0 )
  {
    if ( !(unsigned __int8)FrameWindow::IsPluginLoaded(this, 1) )
    {
      *((_BYTE *)this + 438) = (unsigned int)FrameWindow::CreateTabFromId((__int64)this, v4) == 0;
      goto LABEL_22;
    }
    FrameWindow::DismissPopupWindow(this);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 89) + 56LL))(
      *((_QWORD *)this + 89),
      *((unsigned int *)this + 138),
      *((unsigned __int8 *)this + 432));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 89) + 24LL))(*((_QWORD *)this + 89));
    v5 = *((_BYTE *)this + 432) == 0;
    *((_BYTE *)this + 432) = v5;
    hKey = 0;
    v17 = 0;
    v18 = 0;
    if ( F12::CreateOrOpenF12RegRoot(&hKey, v6) )
    {
      v7 = hKey;
      if ( !hKey )
        goto LABEL_11;
    }
    else
    {
      *(_DWORD *)Data = v5;
      v8 = hKey;
      RegSetValueExW(hKey, L"showconsole", 0, 4u, Data, 4u);
      if ( !v8 )
        goto LABEL_11;
      v7 = v8;
    }
    RegCloseKey(v7);
LABEL_11:
    if ( *((_DWORD *)this + 138) == 3 )
    {
      if ( *((_BYTE *)this + 432) )
      {
LABEL_16:
        v21[0] = &std::_Func_impl_no_alloc<_lambda_1aaf7ff59a74806734d73328f08f98bd_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
        v22 = v21;
        FrameWindow::CallbackOnEachScriptPlugin((__int64)this, (__int64)v21);
        if ( v22 )
        {
          v11 = v21;
          LOBYTE(v11) = v22 != v21;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v22 + 32LL))(v22, v11);
        }
        FrameWindow::OnNotifyKeydown(this, v10, 0x49u, 6, lpData);
        goto LABEL_22;
      }
      *(_DWORD *)Data = 1;
      v9 = std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[]((__int64 *)this + 56, (int *)Data);
      ShowWindow(*(HWND *)(*(_QWORD *)v9 + 16LL), 0);
    }
    else
    {
      FrameWindow::ShowSplitter(this, *((_BYTE *)this + 432));
    }
    if ( !*((_BYTE *)this + 432) )
    {
      v23[0] = &std::_Func_impl_no_alloc<_lambda_1316c44c1f8e79d4b67347e42314cd54_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
      v24 = v23;
      FrameWindow::CallbackOnEachScriptPlugin((__int64)this, (__int64)v23);
      if ( v24 )
      {
        v12 = v23;
        LOBYTE(v12) = v24 != v23;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v12);
      }
      FrameWindow::SetPrimaryFocus(this, *((unsigned int *)this + 138));
      goto LABEL_22;
    }
    goto LABEL_16;
  }
LABEL_22:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(void *))v3)(v3);
    if ( !_InterlockedDecrement((volatile signed __int32 *)v3 + 3) )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x180028a60  mov     [rsp-8+arg_8], rbx
0x180028a65  mov     [rsp-8+arg_10], rsi
0x180028a6a  push    rbp
0x180028a6b  push    rdi
0x180028a6c  push    r15
0x180028a6e  lea     rbp, [rsp-47h]
0x180028a73  sub     rsp, 100h
0x180028a7a  mov     rax, cs:__security_cookie
0x180028a81  xor     rax, rsp
0x180028a84  mov     [rbp+57h+var_20], rax
0x180028a88  mov     rdi, rcx
0x180028a8b  lea     rsi, [rcx+1B7h]
0x180028a92  cmp     byte ptr [rsi], 0
0x180028a95  jnz     loc_180028D0E
0x180028a9b  mov     r15d, 1
0x180028aa1  mov     [rsi], r15b
0x180028aa4  mov     [rsp+110h+var_E0], 0
0x180028aa9  mov     [rbp+57h+hKey], rsi
0x180028aad  lea     rax, [rsp+110h+var_E0]
0x180028ab2  mov     [rbp+57h+var_C8], rax
0x180028ab6  mov     byte ptr [rbp+57h+var_C0], r15b
0x180028aba  lea     ecx, [r15+17h]; Size
0x180028abe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028ac3  mov     rbx, rax
0x180028ac6  mov     qword ptr [rsp+110h+Data], rax
0x180028acb  xorps   xmm0, xmm0
0x180028ace  movups  xmmword ptr [rax], xmm0
0x180028ad1  mov     [rax+8], r15d
0x180028ad5  mov     [rax+0Ch], r15d
0x180028ad9  lea     rax, ??_7?$_Ref_count_resource@PEA_NV_lambda_37637c8b52e7f5910352e2380eaa98ac_@@@std@@6B@; const std::_Ref_count_resource<bool *,_lambda_37637c8b52e7f5910352e2380eaa98ac_>::`vftable'
0x180028ae0  mov     [rbx], rax
0x180028ae3  mov     [rbx+10h], rsi
0x180028ae7  mov     [rbp+57h+var_B8], rsi
0x180028aeb  mov     [rbp+57h+var_B0], rbx
0x180028aef  mov     eax, [rdi+228h]
0x180028af5  add     eax, r15d
0x180028af8  test    eax, 0FFFFFFFDh
0x180028afd  jz      loc_180028CD8
0x180028b03  mov     edx, r15d
0x180028b06  mov     rcx, rdi
0x180028b09  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x180028b0e  mov     rcx, rdi; this
0x180028b11  test    al, al
0x180028b13  jnz     short loc_180028B2A
0x180028b15  call    ?CreateTabFromId@FrameWindow@@AEAAJW4PluginId@@@Z; FrameWindow::CreateTabFromId(PluginId)
0x180028b1a  test    eax, eax
0x180028b1c  setz    al
0x180028b1f  mov     [rdi+1B6h], al
0x180028b25  jmp     loc_180028CD8
0x180028b2a  call    ?DismissPopupWindow@FrameWindow@@AEAAXXZ; FrameWindow::DismissPopupWindow(void)
0x180028b2f  mov     rcx, [rdi+2C8h]
0x180028b36  mov     rax, [rcx]
0x180028b39  movzx   r8d, byte ptr [rdi+1B0h]
0x180028b41  mov     edx, [rdi+228h]
0x180028b47  mov     rax, [rax+38h]
0x180028b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b50  mov     rcx, [rdi+2C8h]
0x180028b57  mov     rax, [rcx]
0x180028b5a  mov     rax, [rax+18h]
0x180028b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b63  cmp     byte ptr [rdi+1B0h], 0
0x180028b6a  setz    sil
0x180028b6e  mov     [rdi+1B0h], sil
0x180028b75  mov     [rbp+57h+hKey], 0
0x180028b7d  mov     [rbp+57h+var_C8], 0
0x180028b85  mov     [rbp+57h+var_C0], 0
0x180028b8d  lea     rcx, [rbp+57h+hKey]; this
0x180028b91  call    ?CreateOrOpenF12RegRoot@F12@@YAJAEAVCRegKey@ATL@@@Z; F12::CreateOrOpenF12RegRoot(ATL::CRegKey &)
0x180028b96  test    eax, eax
0x180028b98  jz      short loc_180028BA5
0x180028b9a  mov     rcx, [rbp+57h+hKey]
0x180028b9e  test    rcx, rcx
0x180028ba1  jz      short loc_180028BE7
0x180028ba3  jmp     short loc_180028BE1
0x180028ba5  movzx   eax, sil
0x180028ba9  mov     dword ptr [rsp+110h+Data], eax
0x180028bad  mov     r9d, 4; dwType
0x180028bb3  mov     [rsp+110h+cbData], r9d; cbData
0x180028bb8  lea     rax, [rsp+110h+Data]
0x180028bbd  mov     [rsp+110h+lpData], rax; int *
0x180028bc2  xor     r8d, r8d; Reserved
0x180028bc5  lea     rdx, ValueName; "showconsole"
0x180028bcc  mov     rsi, [rbp+57h+hKey]
0x180028bd0  mov     rcx, rsi; hKey
0x180028bd3  call    cs:__imp_RegSetValueExW
0x180028bd9  test    rsi, rsi
0x180028bdc  jz      short loc_180028BE7
0x180028bde  mov     rcx, rsi; hKey
0x180028be1  call    cs:__imp_RegCloseKey
0x180028be7  cmp     dword ptr [rdi+228h], 3
0x180028bee  jz      short loc_180028C00
0x180028bf0  mov     dl, [rdi+1B0h]; bool
0x180028bf6  mov     rcx, rdi; this
0x180028bf9  call    ?ShowSplitter@FrameWindow@@AEAAX_N@Z; FrameWindow::ShowSplitter(bool)
0x180028bfe  jmp     short loc_180028C2E
0x180028c00  cmp     byte ptr [rdi+1B0h], 0
0x180028c07  jnz     short loc_180028C37
0x180028c09  mov     dword ptr [rsp+110h+Data], r15d
0x180028c0e  lea     rcx, [rdi+1C0h]
0x180028c15  lea     rdx, [rsp+110h+Data]
0x180028c1a  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x180028c1f  mov     rcx, [rax]
0x180028c22  xor     edx, edx; nCmdShow
0x180028c24  mov     rcx, [rcx+10h]; hWnd
0x180028c28  call    cs:__imp_ShowWindow
0x180028c2e  cmp     byte ptr [rdi+1B0h], 0
0x180028c35  jz      short loc_180028C8A
0x180028c37  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1aaf7ff59a74806734d73328f08f98bd_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1aaf7ff59a74806734d73328f08f98bd_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180028c3e  mov     [rbp+57h+var_A0], rax
0x180028c42  lea     rax, [rbp+57h+var_A0]
0x180028c46  mov     [rbp+57h+var_68], rax
0x180028c4a  lea     rdx, [rbp+57h+var_A0]
0x180028c4e  mov     rcx, rdi
0x180028c51  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180028c56  nop
0x180028c57  mov     rcx, [rbp+57h+var_68]
0x180028c5b  test    rcx, rcx
0x180028c5e  jz      short loc_180028C76
0x180028c60  mov     rax, [rcx]
0x180028c63  lea     rdx, [rbp+57h+var_A0]
0x180028c67  cmp     rcx, rdx
0x180028c6a  setnz   dl
0x180028c6d  mov     rax, [rax+20h]
0x180028c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c76  mov     r9d, 6; __int64
0x180028c7c  lea     r8d, [r9+43h]; unsigned __int64
0x180028c80  mov     rcx, rdi; this
0x180028c83  call    ?OnNotifyKeydown@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnNotifyKeydown(uint,unsigned __int64,__int64,int &)
0x180028c88  jmp     short loc_180028CD8
0x180028c8a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1316c44c1f8e79d4b67347e42314cd54_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1316c44c1f8e79d4b67347e42314cd54_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180028c91  mov     [rbp+57h+var_60], rax
0x180028c95  lea     rax, [rbp+57h+var_60]
0x180028c99  mov     [rbp+57h+var_28], rax
0x180028c9d  lea     rdx, [rbp+57h+var_60]
0x180028ca1  mov     rcx, rdi
0x180028ca4  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180028ca9  nop
0x180028caa  mov     rcx, [rbp+57h+var_28]
0x180028cae  test    rcx, rcx
0x180028cb1  jz      short loc_180028CC9
0x180028cb3  mov     rax, [rcx]
0x180028cb6  lea     rdx, [rbp+57h+var_60]
0x180028cba  cmp     rcx, rdx
0x180028cbd  setnz   dl
0x180028cc0  mov     rax, [rax+20h]
0x180028cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cc9  mov     edx, [rdi+228h]
0x180028ccf  mov     rcx, rdi
0x180028cd2  call    ?SetPrimaryFocus@FrameWindow@@AEAAXW4PluginId@@@Z; FrameWindow::SetPrimaryFocus(PluginId)
0x180028cd7  nop
0x180028cd8  or      edi, 0FFFFFFFFh
0x180028cdb  mov     eax, edi
0x180028cdd  lock xadd [rbx+8], eax
0x180028ce2  add     eax, edi
0x180028ce4  jnz     short loc_180028D0E
0x180028ce6  mov     rax, [rbx]
0x180028ce9  mov     rcx, rbx
0x180028cec  mov     rax, [rax]
0x180028cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cf4  mov     eax, edi
0x180028cf6  lock xadd [rbx+0Ch], eax
0x180028cfb  add     eax, edi
0x180028cfd  jnz     short loc_180028D0E
0x180028cff  mov     rax, [rbx]
0x180028d02  mov     rcx, rbx
0x180028d05  mov     rax, [rax+8]
0x180028d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d0e  mov     rcx, [rbp+57h+var_20]
0x180028d12  xor     rcx, rsp; StackCookie
0x180028d15  call    __security_check_cookie
0x180028d1a  lea     r11, [rsp+110h+var_10]
0x180028d22  mov     rbx, [r11+28h]
0x180028d26  mov     rsi, [r11+30h]
0x180028d2a  mov     rsp, r11
0x180028d2d  pop     r15
0x180028d2f  pop     rdi
0x180028d30  pop     rbp
0x180028d31  retn
```
