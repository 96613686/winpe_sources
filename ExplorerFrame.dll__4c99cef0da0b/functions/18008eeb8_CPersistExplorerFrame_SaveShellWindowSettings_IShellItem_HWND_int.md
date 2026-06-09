# CPersistExplorerFrame::_SaveShellWindowSettings(IShellItem *,HWND__ *,int)

- ea: `0x18008eeb8`
- end: `0x18008f192`
- name: `?_SaveShellWindowSettings@CPersistExplorerFrame@@AEAAHPEAUIShellItem@@PEAUHWND__@@H@Z`
- size: `730`
- prototype: `__int64 __fastcall(CPersistExplorerFrame *__hidden this, struct IShellItem *, HWND, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e36a4`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x18008dd08`
- `0x18008eeb8`
- `0x180090e14`
- `0x180124710`
- `0x18013f7d0`

## import_xrefs

- `SHLWAPI!__imp_SHGetPerScreenResName` at `0x18008f00e`
- `SHLWAPI!__imp_SHGetPerScreenResName` at `0x18008f084`
- `SHLWAPI!__imp_SHGetPerScreenResName` at `0x18008f00e`
- `SHLWAPI!__imp_SHGetPerScreenResName` at `0x18008f084`
- `USER32!SendMessageW` at `0x18008f111`
- `USER32!SendMessageW` at `0x18008f111`
- `USER32!GetWindowPlacement` at `0x18008ef3b`
- `USER32!GetWindowPlacement` at `0x18008ef3b`
- `PROPSYS!PSPropertyBag_WritePOINTL` at `0x18008f16f`
- `PROPSYS!PSPropertyBag_WritePOINTL` at `0x18008f186`
- `PROPSYS!PSPropertyBag_WritePOINTL` at `0x18008f16f`
- `PROPSYS!PSPropertyBag_WritePOINTL` at `0x18008f186`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f0e1`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f0fe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f126`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f0e1`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f0fe`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18008f126`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistExplorerFrame::_SaveShellWindowSettings(
        CPersistExplorerFrame *this,
        struct IShellItem *a2,
        HWND a3,
        int a4)
{
  unsigned int v7; // ebx
  struct IShellItem *v8; // rdx
  const struct _GUID *v9; // r8
  UINT showCmd; // r15d
  __int64 v11; // rsi
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  WCHAR *v15; // rax
  __int64 v16; // r9
  unsigned __int16 v17; // r10
  __int64 v18; // r8
  WCHAR *v19; // rcx
  IPropertyBag *v20; // r14
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  WCHAR *v23; // rax
  __int64 v24; // rcx
  unsigned __int16 v25; // r9
  __int64 v26; // r9
  WCHAR *v27; // rcx
  IPropertyBag *v28; // rsi
  IPropertyBag *v29; // rax
  DWORD v30; // eax
  IPropertyBag *propBag; // [rsp+20h] [rbp-E0h] BYREF
  POINTL value; // [rsp+28h] [rbp-D8h] BYREF
  POINTL ptMaxPosition; // [rsp+30h] [rbp-D0h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+38h] [rbp-C8h] BYREF
  RECT rcNormalPosition; // [rsp+68h] [rbp-98h]
  WCHAR propName[128]; // [rsp+80h] [rbp-80h] BYREF

  v7 = 0;
  ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&propBag);
  if ( CPersistExplorerFrame::_GetFrameStatePropertyBag(this, v8, v9, (void **)&propBag) >= 0 )
  {
    wndpl.length = 44;
    memset(&wndpl.flags, 0, 40);
    GetWindowPlacement(a3, &wndpl);
    v7 = 1;
    showCmd = 1;
    if ( ((wndpl.showCmd - 2) & 0xFFFFFFFB) != 0 )
      showCmd = wndpl.showCmd;
    if ( a4 )
    {
      value = (POINTL)wndpl.ptMinPosition;
      ptMaxPosition = (POINTL)wndpl.ptMaxPosition;
      rcNormalPosition = wndpl.rcNormalPosition;
      v11 = 2147483646;
      v12 = 2147483646;
      v13 = L"MinPos";
      v14 = 128;
      v15 = propName;
      v16 = 0;
      do
      {
        if ( !v12 )
          break;
        v17 = *v13;
        if ( !*v13 )
          break;
        ++v13;
        *v15++ = v17;
        --v12;
        ++v16;
        --v14;
      }
      while ( v14 );
      v18 = v16 - 1;
      if ( v14 )
        v18 = v16;
      v19 = v15 - 1;
      if ( v14 )
        v19 = v15;
      *v19 = 0;
      if ( v14 )
      {
        v20 = propBag;
        if ( (unsigned int)SHGetPerScreenResName(&propName[v18], (unsigned int)(128 - v18), 1) )
          PSPropertyBag_WritePOINTL(v20, propName, &value);
      }
      v21 = L"MaxPos";
      v22 = 128;
      v23 = propName;
      v24 = 0;
      do
      {
        if ( !v11 )
          break;
        v25 = *v21;
        if ( !*v21 )
          break;
        ++v21;
        *v23++ = v25;
        --v11;
        ++v24;
        --v22;
      }
      while ( v22 );
      v26 = v24 - 1;
      if ( v22 )
        v26 = v24;
      v27 = v23 - 1;
      if ( v22 )
        v27 = v23;
      *v27 = 0;
      if ( v22 )
      {
        v28 = propBag;
        if ( (unsigned int)SHGetPerScreenResName(&propName[v26], (unsigned int)(128 - v26), 1) )
          PSPropertyBag_WritePOINTL(v28, propName, &ptMaxPosition);
      }
      SHPropertyBag_WriteRECTLScreenRes(propBag);
      if ( !*((_DWORD *)this + 14) )
        CPersistExplorerFrame::s_rcExplorerFrame = wndpl.rcNormalPosition;
    }
    PSPropertyBag_WriteDWORD(propBag, L"WFlags", wndpl.flags);
    v29 = (IPropertyBag *)ATL::CComPtrBase<IUICommandHandler>::operator->(&propBag);
    PSPropertyBag_WriteDWORD(v29, L"ShowCmd", showCmd);
    v30 = SendMessageW(a3, 0x33u, 0, 0);
    PSPropertyBag_WriteDWORD(propBag, L"HotKey", v30);
  }
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&propBag);
  return v7;
}

```

## disassembly

```asm
0x18008eeb8  mov     [rsp-8+arg_18], rbx
0x18008eebd  push    rbp
0x18008eebe  push    rsi
0x18008eebf  push    rdi
0x18008eec0  push    r12
0x18008eec2  push    r13
0x18008eec4  push    r14
0x18008eec6  push    r15
0x18008eec8  lea     rbp, [rsp-90h]
0x18008eed0  sub     rsp, 190h
0x18008eed7  mov     rax, cs:__security_cookie
0x18008eede  xor     rax, rsp
0x18008eee1  mov     [rbp+0C0h+var_40], rax
0x18008eee8  mov     edi, r9d
0x18008eeeb  mov     r13, r8
0x18008eeee  mov     r12, rcx
0x18008eef1  xor     r14d, r14d
0x18008eef4  mov     ebx, r14d
0x18008eef7  lea     rcx, [rsp+1C0h+propBag]; void *
0x18008eefc  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x18008ef01  nop
0x18008ef02  lea     r9, [rsp+1C0h+propBag]; void **
0x18008ef07  mov     rcx, r12; this
0x18008ef0a  call    ?_GetFrameStatePropertyBag@CPersistExplorerFrame@@AEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; CPersistExplorerFrame::_GetFrameStatePropertyBag(IShellItem *,_GUID const &,void * *)
0x18008ef0f  test    eax, eax
0x18008ef11  js      loc_18008F12D
0x18008ef17  mov     [rsp+1C0h+wndpl.length], 2Ch ; ','
0x18008ef1f  xorps   xmm0, xmm0
0x18008ef22  xor     eax, eax
0x18008ef24  movups  xmmword ptr [rsp+1C0h+wndpl.flags], xmm0
0x18008ef29  movups  xmmword ptr [rsp+1C0h+wndpl.ptMaxPosition.x], xmm0
0x18008ef2e  mov     qword ptr [rsp+1C0h+wndpl.rcNormalPosition.right], rax
0x18008ef33  lea     rdx, [rsp+1C0h+wndpl]; lpwndpl
0x18008ef38  mov     rcx, r13; hWnd
0x18008ef3b  call    cs:__imp_GetWindowPlacement
0x18008ef41  mov     ecx, [rsp+1C0h+wndpl.showCmd]
0x18008ef45  lea     eax, [rcx-2]
0x18008ef48  test    eax, 0FFFFFFFBh
0x18008ef4d  lea     ebx, [r14+1]
0x18008ef51  mov     r15d, ebx
0x18008ef54  cmovnz  r15d, ecx
0x18008ef58  test    edi, edi
0x18008ef5a  jz      loc_18008F0D0
0x18008ef60  mov     eax, [rsp+1C0h+wndpl.ptMinPosition.x]
0x18008ef64  mov     [rsp+1C0h+value.x], eax
0x18008ef68  mov     eax, [rsp+1C0h+wndpl.ptMinPosition.y]
0x18008ef6c  mov     [rsp+1C0h+value.y], eax
0x18008ef70  mov     eax, [rsp+1C0h+wndpl.ptMaxPosition.x]
0x18008ef74  mov     [rsp+1C0h+var_190.x], eax
0x18008ef78  mov     eax, [rsp+1C0h+wndpl.ptMaxPosition.y]
0x18008ef7c  mov     [rsp+1C0h+var_190.y], eax
0x18008ef80  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.left]
0x18008ef84  mov     [rsp+1C0h+var_158], eax
0x18008ef88  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.top]
0x18008ef8c  mov     [rsp+1C0h+var_154], eax
0x18008ef90  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.right]
0x18008ef94  mov     [rsp+1C0h+var_150], eax
0x18008ef98  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.bottom]
0x18008ef9c  mov     [rsp+1C0h+var_14C], eax
0x18008efa0  mov     esi, 7FFFFFFEh
0x18008efa5  mov     ecx, esi
0x18008efa7  lea     r8, aMinpos; "MinPos"
0x18008efae  lea     edi, [rbx+7Fh]
0x18008efb1  mov     edx, edi
0x18008efb3  lea     rax, [rbp+0C0h+propName]
0x18008efb7  mov     r9d, r14d
0x18008efba  test    rcx, rcx
0x18008efbd  jz      short loc_18008EFE0
0x18008efbf  movzx   r10d, word ptr [r8]
0x18008efc3  test    r10w, r10w
0x18008efc7  jz      short loc_18008EFE0
0x18008efc9  add     r8, 2
0x18008efcd  mov     [rax], r10w
0x18008efd1  add     rax, 2
0x18008efd5  sub     rcx, rbx
0x18008efd8  add     r9, rbx
0x18008efdb  sub     rdx, rbx
0x18008efde  jnz     short loc_18008EFBA
0x18008efe0  lea     r8, [r9-1]
0x18008efe4  test    rdx, rdx
0x18008efe7  cmovnz  r8, r9
0x18008efeb  lea     rcx, [rax-2]
0x18008efef  cmovnz  rcx, rax
0x18008eff3  mov     [rcx], r14w
0x18008eff7  jz      short loc_18008F01F
0x18008eff9  mov     r14, [rsp+1C0h+propBag]
0x18008effe  mov     edx, edi
0x18008f000  sub     edx, r8d
0x18008f003  lea     rcx, [rbp+0C0h+propName]
0x18008f007  lea     rcx, [rcx+r8*2]
0x18008f00b  mov     r8d, ebx
0x18008f00e  call    cs:__imp_SHGetPerScreenResName
0x18008f014  test    eax, eax
0x18008f016  jnz     loc_18008F163
0x18008f01c  xor     r14d, r14d
0x18008f01f  lea     rdx, aMaxpos; "MaxPos"
0x18008f026  mov     r8, rdi
0x18008f029  lea     rax, [rbp+0C0h+propName]
0x18008f02d  mov     rcx, r14
0x18008f030  test    rsi, rsi
0x18008f033  jz      short loc_18008F056
0x18008f035  movzx   r9d, word ptr [rdx]
0x18008f039  test    r9w, r9w
0x18008f03d  jz      short loc_18008F056
0x18008f03f  add     rdx, 2
0x18008f043  mov     [rax], r9w
0x18008f047  add     rax, 2
0x18008f04b  sub     rsi, rbx
0x18008f04e  add     rcx, rbx
0x18008f051  sub     r8, rbx
0x18008f054  jnz     short loc_18008F030
0x18008f056  lea     r9, [rcx-1]
0x18008f05a  test    r8, r8
0x18008f05d  cmovnz  r9, rcx
0x18008f061  lea     rcx, [rax-2]
0x18008f065  cmovnz  rcx, rax
0x18008f069  mov     [rcx], r14w
0x18008f06d  jz      short loc_18008F092
0x18008f06f  mov     rsi, [rsp+1C0h+propBag]
0x18008f074  sub     edi, r9d
0x18008f077  lea     rcx, [rbp+0C0h+propName]
0x18008f07b  lea     rcx, [rcx+r9*2]
0x18008f07f  mov     r8d, ebx
0x18008f082  mov     edx, edi
0x18008f084  call    cs:__imp_SHGetPerScreenResName
0x18008f08a  test    eax, eax
0x18008f08c  jnz     loc_18008F17A
0x18008f092  lea     r8, [rsp+1C0h+var_158]
0x18008f097  mov     rcx, [rsp+1C0h+propBag]; propBag
0x18008f09c  call    SHPropertyBag_WriteRECTLScreenRes
0x18008f0a1  cmp     [r12+38h], r14d
0x18008f0a6  jnz     short loc_18008F0D0
0x18008f0a8  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.left]
0x18008f0ac  mov     dword ptr cs:?s_rcExplorerFrame@CPersistExplorerFrame@@0UtagRECT@@A, eax; tagRECT CPersistExplorerFrame::s_rcExplorerFrame
0x18008f0b2  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.top]
0x18008f0b6  mov     dword ptr cs:?s_rcExplorerFrame@CPersistExplorerFrame@@0UtagRECT@@A+4, eax; tagRECT CPersistExplorerFrame::s_rcExplorerFrame
0x18008f0bc  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.right]
0x18008f0c0  mov     dword ptr cs:?s_rcExplorerFrame@CPersistExplorerFrame@@0UtagRECT@@A+8, eax; tagRECT CPersistExplorerFrame::s_rcExplorerFrame
0x18008f0c6  mov     eax, [rsp+1C0h+wndpl.rcNormalPosition.bottom]
0x18008f0ca  mov     dword ptr cs:?s_rcExplorerFrame@CPersistExplorerFrame@@0UtagRECT@@A+0Ch, eax; tagRECT CPersistExplorerFrame::s_rcExplorerFrame
0x18008f0d0  mov     r8d, [rsp+1C0h+wndpl.flags]; value
0x18008f0d5  lea     rdx, aWflags; "WFlags"
0x18008f0dc  mov     rcx, [rsp+1C0h+propBag]; propBag
0x18008f0e1  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18008f0e7  lea     rcx, [rsp+1C0h+propBag]
0x18008f0ec  call    ??C?$CComPtrBase@UIUICommandHandler@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUICommandHandler@@@1@XZ; ATL::CComPtrBase<IUICommandHandler>::operator->(void)
0x18008f0f1  mov     rcx, rax; propBag
0x18008f0f4  mov     r8d, r15d; value
0x18008f0f7  lea     rdx, aShowcmd; "ShowCmd"
0x18008f0fe  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18008f104  xor     r9d, r9d; lParam
0x18008f107  xor     r8d, r8d; wParam
0x18008f10a  lea     edx, [r9+33h]; Msg
0x18008f10e  mov     rcx, r13; hWnd
0x18008f111  call    cs:__imp_SendMessageW
0x18008f117  mov     r8d, eax; value
0x18008f11a  lea     rdx, aHotkey; "HotKey"
0x18008f121  mov     rcx, [rsp+1C0h+propBag]; propBag
0x18008f126  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18008f12c  nop
0x18008f12d  lea     rcx, [rsp+1C0h+propBag]; void *
0x18008f132  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18008f137  mov     eax, ebx
0x18008f139  mov     rcx, [rbp+0C0h+var_40]
0x18008f140  xor     rcx, rsp; StackCookie
0x18008f143  call    __security_check_cookie
0x18008f148  mov     rbx, [rsp+1C0h+arg_18]
0x18008f150  add     rsp, 190h
0x18008f157  pop     r15
0x18008f159  pop     r14
0x18008f15b  pop     r13
0x18008f15d  pop     r12
0x18008f15f  pop     rdi
0x18008f160  pop     rsi
0x18008f161  pop     rbp
0x18008f162  retn
0x18008f163  lea     r8, [rsp+1C0h+value]; value
0x18008f168  lea     rdx, [rbp+0C0h+propName]; propName
0x18008f16c  mov     rcx, r14; propBag
0x18008f16f  call    cs:__imp_PSPropertyBag_WritePOINTL
0x18008f175  jmp     loc_18008F01C
0x18008f17a  lea     r8, [rsp+1C0h+var_190]; value
0x18008f17f  lea     rdx, [rbp+0C0h+propName]; propName
0x18008f183  mov     rcx, rsi; propBag
0x18008f186  call    cs:__imp_PSPropertyBag_WritePOINTL
0x18008f18c  jmp     loc_18008F092
```
