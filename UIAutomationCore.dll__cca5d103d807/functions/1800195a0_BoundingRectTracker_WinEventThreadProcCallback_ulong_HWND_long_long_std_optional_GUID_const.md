# BoundingRectTracker::WinEventThreadProcCallback(ulong,HWND__ *,long,long,std::optional<_GUID> const &)

- ea: `0x1800195a0`
- end: `0x180019b87`
- name: `?WinEventThreadProcCallback@BoundingRectTracker@@MEAAXKPEAUHWND__@@JJAEBV?$optional@U_GUID@@@std@@@Z`
- size: `1511`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18000b790`
- `0x18000f680`
- `0x180017a7c`
- `0x1800195a0`
- `0x180019b90`
- `0x180019cd8`
- `0x180019ec4`
- `0x18002f580`
- `0x180037570`
- `0x180064788`
- `0x1800c20c0`
- `0x18010dc74`
- `0x180181818`
- `0x180181888`
- `0x1801a3598`
- `0x1801e8320`
- `0x1801e887c`
- `0x1801e924c`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18001967b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18001967b`
- `OLEAUT32!__imp_VariantInit` at `0x1800197ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800197b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800197ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800197b7`
- `OLEAUT32!__imp_VariantClear` at `0x180019993`
- `OLEAUT32!__imp_VariantClear` at `0x180019993`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180019800`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180019800`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180019864`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180019864`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800197da`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800197da`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x1800199cd`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!EqualRect` at `0x1800199cd`

## string_xrefs

- `0x18001962c`: `BoundingRectTracker::WinEventThreadProcCallback`
- `0x180019ab5`: `BoundingRectTracker::WinEventThreadProcCallback`
- `0x180019b6b`: `onecore\windows\accessibletech\uiautomationcore\proxies\hwndproxy.cpp`
- `0x180019a42`: `onecore\windows\accessibletech\uiautomationcore\cautomation.cpp`
- `0x180019a91`: `onecore\windows\accessibletech\uiautomationcore\cautomation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall BoundingRectTracker::WinEventThreadProcCallback(
        __int64 a1,
        int a2,
        HWND a3,
        int a4,
        int a5,
        __int64 a6)
{
  HWND v7; // r14
  char v10; // di
  int ClassNameW; // eax
  __int64 v12; // r8
  WCHAR *v13; // r9
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  void **v16; // rdi
  __int64 v17; // rbx
  void **v18; // r9
  void **v19; // r8
  HWND v20; // [rsp+58h] [rbp-A8h]
  void *v21[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+E0h] [rbp-20h]
  void *v23[2]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v24; // [rsp+100h] [rbp+0h]
  int v25; // [rsp+110h] [rbp+10h]
  int v26; // [rsp+114h] [rbp+14h]
  int v27; // [rsp+118h] [rbp+18h]
  int v28; // [rsp+11Ch] [rbp+1Ch]
  int v29; // [rsp+120h] [rbp+20h]
  WCHAR ClassName[264]; // [rsp+130h] [rbp+30h] BYREF

  v7 = a3;
  v20 = a3;
  v10 = *(_BYTE *)(a6 + 16);
  *(_OWORD *)v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21[0]) = 0;
  *(_OWORD *)v23 = 0;
  v24 = si128;
  LOWORD(v23[0]) = 0;
  if ( _mm_srli_si128(si128, 8).m128i_u64[0] >= 0x2F )
  {
    si128.m128i_i64[0] = 47;
    memmove_0(v21[0], L"BoundingRectTracker::WinEventThreadProcCallback", 0x5Eu);
    *((_WORD *)v21[0] + 47) = 0;
  }
  else
  {
    LOBYTE(a3) = 0;
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v21,
      47,
      a3,
      L"BoundingRectTracker::WinEventThreadProcCallback");
  }
  v25 = (int)v7;
  v26 = HIDWORD(v20);
  v27 = a2;
  v28 = a4;
  v29 = a5;
  if ( a2 == 32769 )
  {
    std::wstring::_Assign<unsigned short>(v23, L"Window destroyed", 16);
  }
  else if ( v10 )
  {
    std::wstring::assign(v23, L"[Cross-Machine]");
  }
  else
  {
    ClassNameW = GetClassNameW(v7, ClassName, 260);
    v13 = ClassName;
    if ( !ClassNameW )
      v13 = L"Failed to get window class name";
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    if ( v14 <= v24.m128i_i64[1] )
    {
      v16 = v23;
      if ( v24.m128i_i64[1] > 7uLL )
        v16 = (void **)v23[0];
      v24.m128i_i64[0] = v14;
      v17 = 2 * v14;
      memmove_0(v16, v13, 2 * v14);
      *(_WORD *)((char *)v16 + v17) = 0;
    }
    else
    {
      LOBYTE(v12) = 0;
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v23,
        v14,
        v12,
        v13);
    }
  }
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v18 = v23;
    if ( v24.m128i_i64[1] > 7uLL )
      v18 = (void **)v23[0];
    v19 = v21;
    if ( si128.m128i_i64[1] > 7uLL )
      LODWORD(v19) = v21[0];
    McTemplateU0zdzddq_EventWriteTransfer(
      v28,
      (unsigned int)HandleWinEvent_Start,
      (_DWORD)v19,
      v25,
      (__int64)v18,
      v27,
      v28,
      v29);
  }
  if ( v7 )
  {
    if ( !a4 )
    {
      v15 = *(_QWORD *)(a1 + 8);
      if ( v15 )
      {
        if ( *(_QWORD *)(v15 + 32) )
        {
          if ( a2 == 32771 )
          {
            *(_QWORD *)(a1 + 48) = v7;
            *(_OWORD *)(a1 + 56) = xmmword_180309940;
            *(_BYTE *)(a1 + 88) = 0;
          }
          else
          {
            HwndUtils::GetWindowVisibility(v7, 0);
          }
        }
      }
    }
  }
  HandleWinEventTrace::~HandleWinEventTrace((HandleWinEventTrace *)v21);
}

```

## disassembly

```asm
0x1800195a0  mov     [rsp-8+arg_8], rbx
0x1800195a5  push    rbp
0x1800195a6  push    rsi
0x1800195a7  push    rdi
0x1800195a8  push    r12
0x1800195aa  push    r13
0x1800195ac  push    r14
0x1800195ae  push    r15
0x1800195b0  lea     rbp, [rsp-250h]
0x1800195b8  sub     rsp, 350h
0x1800195bf  mov     rax, cs:__security_cookie
0x1800195c6  xor     rax, rsp
0x1800195c9  mov     [rbp+280h+var_40], rax
0x1800195d0  mov     r13d, r9d
0x1800195d3  mov     r14, r8
0x1800195d6  mov     r12d, edx
0x1800195d9  mov     rsi, rcx
0x1800195dc  mov     [rsp+380h+var_328], r8
0x1800195e1  mov     r15, [rbp+280h+arg_28]
0x1800195e8  mov     dil, [r15+10h]
0x1800195ec  xorps   xmm0, xmm0
0x1800195ef  movups  xmmword ptr [rbp+280h+var_2B0], xmm0
0x1800195f3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800195fb  movdqa  [rbp+280h+var_2A0], xmm1
0x180019600  xor     ebx, ebx
0x180019602  mov     word ptr [rbp+280h+var_2B0], bx
0x180019606  movups  xmmword ptr [rbp+280h+var_290], xmm0
0x18001960a  movdqa  [rbp+280h+var_280], xmm1
0x18001960f  mov     word ptr [rbp+280h+var_290], bx
0x180019613  psrldq  xmm1, 8
0x180019618  movq    rax, xmm1
0x18001961d  lea     edx, [rbx+2Fh]
0x180019620  cmp     rax, rdx
0x180019623  jnb     loc_180019AA7
0x180019629  mov     r8b, bl
0x18001962c  lea     r9, aBoundingrecttr; "BoundingRectTracker::WinEventThreadProc"...
0x180019633  lea     rcx, [rbp+280h+var_2B0]
0x180019637  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001963c  mov     [rbp+280h+var_270], r14d
0x180019640  mov     eax, dword ptr [rsp+380h+var_328+4]
0x180019644  mov     [rbp+280h+var_26C], eax
0x180019647  mov     [rbp+280h+var_268], r12d
0x18001964b  mov     [rbp+280h+var_264], r13d
0x18001964f  mov     eax, [rbp+280h+arg_20]
0x180019655  mov     [rbp+280h+var_260], eax
0x180019658  cmp     r12d, 8001h
0x18001965f  jz      loc_1800199E0
0x180019665  test    dil, dil
0x180019668  jnz     loc_180019ACF
0x18001966e  mov     r8d, 104h; nMaxCount
0x180019674  lea     rdx, [rbp+280h+ClassName]; lpClassName
0x180019678  mov     rcx, r14; hWnd
0x18001967b  call    cs:__imp_GetClassNameW
0x180019681  lea     rcx, aFailedToGetWin; "Failed to get window class name"
0x180019688  lea     r9, [rbp+280h+ClassName]
0x18001968c  xor     edi, edi
0x18001968e  test    eax, eax
0x180019690  cmovz   r9, rcx
0x180019694  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019698  inc     rdx
0x18001969b  cmp     [r9+rdx*2], di
0x1800196a0  jnz     short loc_180019698
0x1800196a2  cmp     rdx, qword ptr [rbp+280h+var_280+8]
0x1800196a6  jbe     loc_180019AE4
0x1800196ac  mov     r8b, dil
0x1800196af  lea     rcx, [rbp+280h+var_290]
0x1800196b3  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800196b8  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800196bf  jnz     loc_180019B13
0x1800196c5  test    r14, r14
0x1800196c8  jnz     short loc_1800196FD
0x1800196ca  lea     rcx, [rbp+280h+var_2B0]; this
0x1800196ce  call    ??1HandleWinEventTrace@@QEAA@XZ; HandleWinEventTrace::~HandleWinEventTrace(void)
0x1800196d3  mov     rcx, [rbp+280h+var_40]
0x1800196da  xor     rcx, rsp; StackCookie
0x1800196dd  call    __security_check_cookie
0x1800196e2  mov     rbx, [rsp+380h+arg_8]
0x1800196ea  add     rsp, 350h
0x1800196f1  pop     r15
0x1800196f3  pop     r14
0x1800196f5  pop     r13
0x1800196f7  pop     r12
0x1800196f9  pop     rdi
0x1800196fa  pop     rsi
0x1800196fb  pop     rbp
0x1800196fc  retn
0x1800196fd  test    r13d, r13d
0x180019700  jnz     short loc_1800196CA
0x180019702  mov     rax, [rsi+8]
0x180019706  test    rax, rax
0x180019709  jz      short loc_1800196CA
0x18001970b  cmp     [rax+20h], rdi
0x18001970f  jz      short loc_1800196CA
0x180019711  cmp     r12d, 8003h
0x180019718  jz      loc_180019A5C
0x18001971e  mov     [rsp+380h+var_340], dil
0x180019723  mov     [rsp+380h+var_360], rdi; int
0x180019728  lea     r9, [rsp+380h+var_340]
0x18001972d  xor     r8d, r8d
0x180019730  mov     rdx, r15
0x180019733  mov     rcx, r14; hWnd
0x180019736  call    ?GetWindowVisibility@HwndUtils@@SAJPEAUHWND__@@AEBV?$optional@U_GUID@@@std@@PEA_N2PEAW4VisibilityOverride@BasicHwndUtils@@@Z; HwndUtils::GetWindowVisibility(HWND__ *,std::optional<_GUID> const &,bool *,bool *,BasicHwndUtils::VisibilityOverride *)
0x18001973b  test    eax, eax
0x18001973d  js      short loc_1800196CA
0x18001973f  cmp     [rsp+380h+var_340], dil
0x180019744  jz      short loc_1800196CA
0x180019746  xorps   xmm0, xmm0
0x180019749  movups  xmmword ptr [rbp+280h+rc1.left], xmm0
0x18001974d  lea     r8, [rbp+280h+rc1]
0x180019751  mov     rdx, r15
0x180019754  mov     rcx, r14
0x180019757  call    ?GetWindowRect@HwndUtils@@SAJPEAUHWND__@@AEBV?$optional@U_GUID@@@std@@PEAUtagRECT@@@Z; HwndUtils::GetWindowRect(HWND__ *,std::optional<_GUID> const &,tagRECT *)
0x18001975c  test    eax, eax
0x18001975e  js      loc_1800196CA
0x180019764  cmp     r14, [rsi+30h]
0x180019768  jnz     short loc_180019781
0x18001976a  mov     al, [rsi+58h]
0x18001976d  cmp     [r15+10h], dil
0x180019771  jnz     loc_18001999E
0x180019777  cmp     [r15+10h], al
0x18001977b  jz      loc_1800199C5
0x180019781  xor     edx, edx; Val
0x180019783  lea     r8d, [rdx+40h]; Size
0x180019787  lea     rcx, [rsp+380h+var_310]; void *
0x18001978c  call    memset_0
0x180019791  mov     [rsp+380h+var_310.Type], 1
0x180019799  mov     [rsp+380h+var_310.EventId], 4E24h
0x1800197a1  mov     [rsp+380h+var_308], 7531h
0x1800197a9  lea     rcx, [rbp+280h+pvarg]; pvarg
0x1800197ad  call    cs:__imp_VariantInit
0x1800197b3  lea     rcx, [rbp+280h+var_2E8]; pvarg
0x1800197b7  call    cs:__imp_VariantInit
0x1800197bd  mov     r13d, [rbp+280h+rc1.left]
0x1800197c1  mov     eax, [rbp+280h+rc1.top]
0x1800197c4  mov     [rsp+380h+var_320], eax
0x1800197c8  mov     edi, [rbp+280h+rc1.right]
0x1800197cb  mov     r12d, [rbp+280h+rc1.bottom]
0x1800197cf  mov     ecx, 5; vt
0x1800197d4  xor     edx, edx; lLbound
0x1800197d6  lea     r8d, [rcx-1]; cElements
0x1800197da  call    cs:__imp_SafeArrayCreateVector
0x1800197e0  mov     rbx, rax
0x1800197e3  mov     [rsp+380h+var_328], rax
0x1800197e8  xor     eax, eax
0x1800197ea  test    rbx, rbx
0x1800197ed  jz      loc_180019A37
0x1800197f3  mov     [rsp+380h+ppvData], rax
0x1800197f8  lea     rdx, [rsp+380h+ppvData]; ppvData
0x1800197fd  mov     rcx, rbx; psa
0x180019800  call    cs:__imp_SafeArrayAccessData
0x180019806  test    eax, eax
0x180019808  js      loc_180019A7D
0x18001980e  movd    xmm0, r13d
0x180019813  cvtdq2pd xmm0, xmm0
0x180019817  mov     rax, [rsp+380h+ppvData]
0x18001981c  movsd   qword ptr [rax], xmm0
0x180019820  mov     ecx, [rsp+380h+var_320]
0x180019824  movd    xmm1, ecx
0x180019828  cvtdq2pd xmm1, xmm1
0x18001982c  mov     rax, [rsp+380h+ppvData]
0x180019831  movsd   qword ptr [rax+8], xmm1
0x180019836  sub     edi, r13d
0x180019839  movd    xmm0, edi
0x18001983d  cvtdq2pd xmm0, xmm0
0x180019841  mov     rax, [rsp+380h+ppvData]
0x180019846  movsd   qword ptr [rax+10h], xmm0
0x18001984b  sub     r12d, ecx
0x18001984e  movd    xmm0, r12d
0x180019853  cvtdq2pd xmm0, xmm0
0x180019857  mov     rax, [rsp+380h+ppvData]
0x18001985c  movsd   qword ptr [rax+18h], xmm0
0x180019861  mov     rcx, rbx; psa
0x180019864  call    cs:__imp_SafeArrayUnaccessData
0x18001986a  xor     edi, edi
0x18001986c  test    eax, eax
0x18001986e  js      loc_180019A87
0x180019874  mov     eax, 2005h
0x180019879  mov     word ptr [rbp+280h+var_2E8], ax
0x18001987d  mov     qword ptr [rbp+280h+var_2E8+8], rbx
0x180019881  mov     [rsp+380h+var_328], rdi
0x180019886  lea     rcx, [rsp+380h+var_328]
0x18001988b  call    ?SafeRelease@?$AutoCleanupInfo@PEAUtagSAFEARRAY@@@@SAXAEAPEAUtagSAFEARRAY@@@Z; AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(tagSAFEARRAY * &)
0x180019890  lea     rax, [rsp+380h+var_310]
0x180019895  mov     [rbp+280h+var_2D0], rax
0x180019899  mov     [rbp+280h+var_2C8], 1
0x18001989d  mov     rax, [rsi+8]
0x1800198a1  mov     rcx, [rax+20h]
0x1800198a5  mov     [rsp+380h+ppvData], rdi
0x1800198aa  lea     rdx, [rsp+380h+ppvData]; struct UiaClientState **
0x1800198af  mov     rcx, [rcx+2A8h]; this
0x1800198b6  call    ?GetClientState@CUIAutomation@@QEAAJPEAPEAVUiaClientState@@@Z; CUIAutomation::GetClientState(UiaClientState * *)
0x1800198bb  test    eax, eax
0x1800198bd  js      loc_1800199FD
0x1800198c3  mov     [rsp+380h+var_330], rdi
0x1800198c8  lea     rcx, [rsp+380h+var_330]
0x1800198cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800198d2  mov     [rsp+380h+var_330], rdi
0x1800198d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800198de  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800198e3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800198e8  mov     [rsp+380h+var_328], rax
0x1800198ed  mov     rbx, [rsp+380h+ppvData]
0x1800198f2  test    rax, rax
0x1800198f5  jz      loc_180019A75
0x1800198fb  mov     [rsp+380h+var_360], rdi; int
0x180019900  mov     r9, r15
0x180019903  mov     r8, rbx
0x180019906  mov     rdx, r14
0x180019909  mov     rcx, rax
0x18001990c  call    ??0HwndProxy@@AEAA@PEAUHWND__@@PEAVUiaClientState@@AEBV?$optional@U_GUID@@@std@@0@Z; HwndProxy::HwndProxy(HWND__ *,UiaClientState *,std::optional<_GUID> const &,HWND__ *)
0x180019911  mov     rcx, rax
0x180019914  lea     rax, [rcx+10h]
0x180019918  neg     rcx
0x18001991b  sbb     rcx, rcx
0x18001991e  and     rcx, rax; struct IRawElementProviderSimple *
0x180019921  mov     [rsp+380h+var_330], rcx
0x180019926  jz      loc_180019B5E
0x18001992c  test    rcx, rcx
0x18001992f  jz      loc_180019A1D
0x180019935  xor     r8d, r8d; bool
0x180019938  lea     rdx, [rsp+380h+var_310]; struct UiaEventArgs *
0x18001993d  call    ?RaiseEvent@EventManager@@SAXPEAUIRawElementProviderSimple@@PEAUUiaEventArgs@@_N@Z; EventManager::RaiseEvent(IRawElementProviderSimple *,UiaEventArgs *,bool)
0x180019942  mov     [rsi+30h], r14
0x180019946  movups  xmm0, xmmword ptr [rbp+280h+rc1.left]
0x18001994a  movdqu  xmmword ptr [rsi+38h], xmm0
0x18001994f  movups  xmm0, xmmword ptr [r15]
0x180019953  movups  xmmword ptr [rsi+48h], xmm0
0x180019957  mov     eax, [r15+10h]
0x18001995b  mov     [rsi+58h], eax
0x18001995e  mov     rcx, [rsp+380h+var_330]
0x180019963  test    rcx, rcx
0x180019966  jz      short loc_18001997A
0x180019968  mov     [rsp+380h+var_330], rdi
0x18001996d  mov     rax, [rcx]
0x180019970  mov     rax, [rax+10h]
0x180019974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019979  nop
0x18001997a  test    rbx, rbx
0x18001997d  jz      short loc_18001998F
0x18001997f  mov     rax, [rbx]
0x180019982  mov     rcx, rbx
0x180019985  mov     rax, [rax+10h]
0x180019989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001998e  nop
0x18001998f  lea     rcx, [rbp+280h+var_2E8]; pvarg
0x180019993  call    cs:__imp_VariantClear
0x180019999  jmp     loc_1800196CA
0x18001999e  test    al, al
0x1800199a0  jz      loc_180019781
0x1800199a6  mov     rax, [r15]
0x1800199a9  sub     rax, [rsi+48h]
0x1800199ad  jnz     short loc_1800199B7
0x1800199af  mov     rax, [r15+8]
0x1800199b3  sub     rax, [rsi+50h]
0x1800199b7  test    rax, rax
0x1800199ba  setz    al
0x1800199bd  test    al, al
0x1800199bf  jz      loc_180019781
0x1800199c5  lea     rdx, [rsi+38h]; lprc2
0x1800199c9  lea     rcx, [rbp+280h+rc1]; lprc1
0x1800199cd  call    cs:__imp_EqualRect
0x1800199d3  test    eax, eax
0x1800199d5  jnz     loc_1800196CA
0x1800199db  jmp     loc_180019781
0x1800199e0  mov     r8d, 10h
0x1800199e6  lea     rdx, aWindowDestroye; "Window destroyed"
0x1800199ed  lea     rcx, [rbp+280h+var_290]
0x1800199f1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800199f6  xor     edi, edi
0x1800199f8  jmp     loc_1800196B8
0x1800199fd  mov     rcx, [rsp+380h+ppvData]
0x180019a02  test    rcx, rcx
0x180019a05  jz      short loc_180019A14
0x180019a07  mov     rax, [rcx]
0x180019a0a  mov     rax, [rax+10h]
0x180019a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a13  nop
0x180019a14  lea     rcx, [rbp+280h+var_2E8]
0x180019a18  jmp     loc_180019993
0x180019a1d  lea     rcx, [rsp+380h+var_330]
0x180019a22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019a27  nop
0x180019a28  lea     rcx, [rsp+380h+ppvData]; void *
0x180019a2d  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x180019a32  jmp     loc_18001998F
0x180019a37  mov     r9d, 8007000Eh; char *
0x180019a3d  mov     edx, 8A0h; void *
0x180019a42  lea     r8, aOnecoreWindows_118; "onecore\\windows\\accessibletech\\uiaut"...
0x180019a49  mov     rcx, [rbp+288h]; this
0x180019a50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a55  xor     edi, edi
0x180019a57  jmp     loc_180019886
0x180019a5c  mov     [rsi+30h], r14
0x180019a60  movups  xmm0, cs:xmmword_180309940
0x180019a67  movdqu  xmmword ptr [rsi+38h], xmm0
0x180019a6c  mov     [rsi+58h], dil
0x180019a70  jmp     loc_1800196CA
0x180019a75  mov     rcx, rdi
0x180019a78  jmp     loc_180019914
0x180019a7d  mov     r9d, eax
  ... truncated ...
```
