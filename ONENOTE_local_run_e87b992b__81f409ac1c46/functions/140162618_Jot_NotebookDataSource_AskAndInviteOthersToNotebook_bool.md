# Jot::NotebookDataSource::AskAndInviteOthersToNotebook(bool)

- ea: `0x140162618`
- end: `0x1401629cb`
- name: `?AskAndInviteOthersToNotebook@NotebookDataSource@Jot@@AEAAX_N@Z`
- size: `947`
- prototype: `void __fastcall(struct IDataSource *this, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401636cc`
- `0x140164030`

## callees

- `0x1400209a0`
- `0x14003f250`
- `0x140048a58`
- `0x140056ac0`
- `0x140057580`
- `0x14007c30c`
- `0x14008d154`
- `0x14008d6b8`
- `0x140162618`

## import_xrefs

- `onmain!?IsPathUnderMyDocumentsFolder@Jot@@YA_NPEB_W@Z` at `0x1401626bf`
- `onmain!?IsPathUnderMyDocumentsFolder@Jot@@YA_NPEB_W@Z` at `0x1401626bf`
- `onmain!?SetFrom@CWzInBuffer@Jot@@QEAAXV?$String@UWzTraits@MsoCF@@@MsoCF@@@Z` at `0x140162678`
- `onmain!?SetFrom@CWzInBuffer@Jot@@QEAAXV?$String@UWzTraits@MsoCF@@@MsoCF@@@Z` at `0x140162678`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1401627df`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140162819`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x14016283a`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140162874`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x1401627df`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140162819`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x14016283a`
- `onmain!?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140162874`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x1401626ea`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x1401626ea`
- `onmain!?GetFileProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFileProxy@1@_NPEA_N2@Z` at `0x140162703`
- `onmain!?GetFileProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFileProxy@1@_NPEA_N2@Z` at `0x140162703`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162682`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14016269b`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401626b6`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162809`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162864`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401628b0`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401628dd`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162682`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14016269b`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401626b6`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162809`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140162864`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401628b0`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401628dd`
- `SHLWAPI!PathIsURLW` at `0x14016268b`
- `SHLWAPI!PathIsURLW` at `0x14016268b`
- `SHLWAPI!PathIsNetworkPathW` at `0x1401626a4`
- `SHLWAPI!PathIsNetworkPathW` at `0x1401626a4`
- `Mso30Win32Client!__imp_?LDoAlertTFC@@YAHPEAUIMsoUser@@PEB_W1HHHHH1JPEBQEB_WPEAUHWND__@@@Z` at `0x140162930`
- `Mso30Win32Client!__imp_?LDoAlertTFC@@YAHPEAUIMsoUser@@PEB_W1HHHHH1JPEBQEB_WPEAUHWND__@@@Z` at `0x140162930`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Jot::NotebookDataSource::AskAndInviteOthersToNotebook(struct IDataSource *this, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  const WCHAR *v6; // rax
  BOOL IsURLW; // esi
  const WCHAR *v8; // rax
  Jot *v9; // rax
  const wchar_t *v10; // rdx
  char v11; // di
  _QWORD *v12; // rax
  __int64 v13; // rcx
  void (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // r9
  __int64 v15; // r8
  __int64 v16; // rax
  const wchar_t *v17; // rax
  __int64 v18; // rax
  const wchar_t *v19; // rax
  HWND v20; // rbx
  const wchar_t *v21; // rdi
  __int64 v22; // rax
  const wchar_t *v23; // rax
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-E0h]
  void (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[8]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[368]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[368]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v32[368]; // [rsp+360h] [rbp+260h] BYREF

  NotebookDSSP::NotebookDSSP((NotebookDSSP *)&v28, this);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v30);
  v5 = FlexUI::DataSourceGetImpl<FlexUI::TypeTraits<wchar_t const *>>(v28, v4, 1);
  Jot::CWzInBuffer::SetFrom(v30, v5);
  v6 = (const WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v30);
  IsURLW = PathIsURLW(v6);
  if ( IsURLW || (v8 = (const WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v30), PathIsNetworkPathW(v8)) )
  {
    v9 = (Jot *)Jot::CWzInBuffer::operator wchar_t *(v30);
    if ( !Jot::IsPathUnderMyDocumentsFolder(v9, v10) )
    {
      v11 = 0;
      if ( !IsURLW )
        goto LABEL_15;
      v26 = 0;
      v12 = (_QWORD *)Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(v30, v29);
      Jot::GetFileProxyFromPath_Exported(*v12, &v26, 0, 0, 0);
      v13 = 0;
      v27 = 0;
      v14 = v26;
      if ( v26 )
      {
        (**v26)(v26, &GUID_45aaf9e1_3466_48d1_806f_5edf97172c08, &v27);
        v14 = v26;
        v13 = v27;
      }
      if ( v13 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 104LL))(v13);
        v14 = v26;
        v13 = v27;
      }
      if ( v13 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        v14 = v26;
      }
      if ( v14 )
        ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
      if ( v11 )
        v15 = a2 != 0 ? 1251907180 : -1321704305;
      else
LABEL_15:
        v15 = a2 != 0 ? 1184172466 : -1914535518;
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
        v31,
        *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
        v15);
      Jot::CWzInBuffer::AppendWz((Jot::CWzInBuffer *)v31, L"\a");
      v16 = Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
              v32,
              *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
              4076974399LL);
      v17 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v16);
      Jot::CWzInBuffer::AppendWz((Jot::CWzInBuffer *)v31, v17);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v32);
      Jot::CWzInBuffer::AppendWz((Jot::CWzInBuffer *)v31, L"\a");
      v18 = Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
              v32,
              *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
              3161425470LL);
      v19 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v18);
      Jot::CWzInBuffer::AppendWz((Jot::CWzInBuffer *)v31, v19);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v32);
      v20 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 58)
                                                                  + 104LL)
                                                    + 120LL))(*(_QWORD *)(*((_QWORD *)Jot::CJotApp::s_pSingletonJotApp
                                                                          + 58)
                                                                        + 104LL));
      v21 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v31);
      v22 = Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
              v32,
              *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
              645739117);
      v23 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v22);
      LODWORD(v20) = LDoAlertTFC(0, v23, v21, 8, 4, 0, 1, 0, 0, 0, 0, v20);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v32);
      if ( (_DWORD)v20 == 101 )
      {
        v24 = (*((__int64 (__fastcall **)(struct IDataSourceVtbl *))this[17].lpVtbl->QueryInterface + 6))(this[17].lpVtbl);
        LOBYTE(v25) = 0;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v24 + 288LL))(v24, 26594, 0, 0, v25);
      }
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v31);
    }
  }
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v30);
  NotebookListDSSP::~NotebookListDSSP((NotebookListDSSP *)&v28);
}

```

## disassembly

```asm
0x140162618  mov     [rsp-8+arg_8], rbx
0x14016261d  mov     [rsp-8+arg_10], rsi
0x140162622  push    rbp
0x140162623  push    rdi
0x140162624  push    r14
0x140162626  lea     rbp, [rsp-3E0h]
0x14016262e  sub     rsp, 4E0h
0x140162635  mov     rax, cs:__security_cookie
0x14016263c  xor     rax, rsp
0x14016263f  mov     [rbp+3F0h+var_20], rax
0x140162646  mov     bl, dl
0x140162648  mov     r14, rcx
0x14016264b  mov     rdx, rcx; struct IDataSource *
0x14016264e  lea     rcx, [rsp+4F0h+var_480]; this
0x140162653  call    ??0NotebookDSSP@@QEAA@PEAUIDataSource@FlexUI@@@Z; NotebookDSSP::NotebookDSSP(FlexUI::IDataSource *)
0x140162658  lea     rcx, [rbp+3F0h+var_470]
0x14016265c  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140162661  mov     r8d, 1
0x140162667  mov     rcx, [rsp+4F0h+var_480]
0x14016266c  call    ??$DataSourceGetImpl@V?$TypeTraits@PEB_W@FlexUI@@@FlexUI@@YAPEB_WPEAUIDataSource@0@IH@Z; FlexUI::DataSourceGetImpl<FlexUI::TypeTraits<wchar_t const *>>(FlexUI::IDataSource *,uint,int)
0x140162671  mov     rdx, rax
0x140162674  lea     rcx, [rbp+3F0h+var_470]
0x140162678  call    cs:__imp_?SetFrom@CWzInBuffer@Jot@@QEAAXV?$String@UWzTraits@MsoCF@@@MsoCF@@@Z; Jot::CWzInBuffer::SetFrom(MsoCF::String<MsoCF::WzTraits>)
0x14016267e  lea     rcx, [rbp+3F0h+var_470]
0x140162682  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140162688  mov     rcx, rax; pszPath
0x14016268b  call    cs:__imp_PathIsURLW
0x140162691  mov     esi, eax
0x140162693  test    eax, eax
0x140162695  jnz     short loc_1401626B2
0x140162697  lea     rcx, [rbp+3F0h+var_470]
0x14016269b  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1401626a1  mov     rcx, rax; pszPath
0x1401626a4  call    cs:__imp_PathIsNetworkPathW
0x1401626aa  test    eax, eax
0x1401626ac  jz      loc_140162991
0x1401626b2  lea     rcx, [rbp+3F0h+var_470]
0x1401626b6  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1401626bc  mov     rcx, rax
0x1401626bf  call    cs:__imp_?IsPathUnderMyDocumentsFolder@Jot@@YA_NPEB_W@Z; Jot::IsPathUnderMyDocumentsFolder(wchar_t const *)
0x1401626c5  test    al, al
0x1401626c7  jnz     loc_140162991
0x1401626cd  xor     dil, dil
0x1401626d0  test    esi, esi
0x1401626d2  jz      loc_1401627A4
0x1401626d8  mov     [rsp+4F0h+var_490], 0
0x1401626e1  lea     rdx, [rsp+4F0h+var_478]
0x1401626e6  lea     rcx, [rbp+3F0h+var_470]
0x1401626ea  call    cs:__imp_??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ; Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(void)
0x1401626f0  mov     byte ptr [rsp+4F0h+var_4D0], dil
0x1401626f5  xor     r9d, r9d
0x1401626f8  xor     r8d, r8d
0x1401626fb  lea     rdx, [rsp+4F0h+var_490]
0x140162700  mov     rcx, [rax]
0x140162703  call    cs:__imp_?GetFileProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFileProxy@1@_NPEA_N2@Z; Jot::GetFileProxyFromPath_Exported(MsoCF::String<MsoCF::WzTraits>,Jot::IFileProxy * *,bool,bool *,bool)
0x140162709  xor     ecx, ecx
0x14016270b  mov     [rsp+4F0h+var_488], rcx
0x140162710  mov     r9, [rsp+4F0h+var_490]
0x140162715  test    r9, r9
0x140162718  jz      short loc_14016273F
0x14016271a  mov     rax, [r9]
0x14016271d  lea     r8, [rsp+4F0h+var_488]
0x140162722  lea     rdx, _GUID_45aaf9e1_3466_48d1_806f_5edf97172c08
0x140162729  mov     rcx, r9
0x14016272c  mov     rax, [rax]
0x14016272f  call    cs:__guard_dispatch_icall_fptr
0x140162735  mov     r9, [rsp+4F0h+var_490]
0x14016273a  mov     rcx, [rsp+4F0h+var_488]
0x14016273f  test    rcx, rcx
0x140162742  jz      short loc_14016275E
0x140162744  mov     rax, [rcx]
0x140162747  mov     rax, [rax+68h]
0x14016274b  call    cs:__guard_dispatch_icall_fptr
0x140162751  mov     dil, al
0x140162754  mov     r9, [rsp+4F0h+var_490]
0x140162759  mov     rcx, [rsp+4F0h+var_488]
0x14016275e  test    rcx, rcx
0x140162761  jz      short loc_140162775
0x140162763  mov     rdx, [rcx]
0x140162766  mov     rax, [rdx+10h]
0x14016276a  call    cs:__guard_dispatch_icall_fptr
0x140162770  mov     r9, [rsp+4F0h+var_490]
0x140162775  test    r9, r9
0x140162778  jz      short loc_14016278A
0x14016277a  mov     rax, [r9]
0x14016277d  mov     rcx, r9
0x140162780  mov     rax, [rax+10h]
0x140162784  call    cs:__guard_dispatch_icall_fptr
0x14016278a  test    dil, dil
0x14016278d  jz      short loc_1401627A4
0x14016278f  neg     bl
0x140162791  sbb     r8d, r8d
0x140162794  and     r8d, 996631DDh
0x14016279b  add     r8d, 0B138648Fh
0x1401627a2  jmp     short loc_1401627B7
0x1401627a4  neg     bl
0x1401627a6  sbb     r8d, r8d
0x1401627a9  and     r8d, 0B8B28810h
0x1401627b0  add     r8d, 8DE281A2h
0x1401627b7  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1401627be  mov     rdx, [rdx+1F0h]
0x1401627c5  lea     rcx, [rbp+3F0h+var_300]
0x1401627cc  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x1401627d1  lea     rdx, asc_14020768C; "\a"
0x1401627d8  lea     rcx, [rbp+3F0h+var_300]
0x1401627df  call    cs:__imp_?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x1401627e5  mov     r8d, 0F301B13Fh
0x1401627eb  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1401627f2  mov     rdx, [rdx+1F0h]
0x1401627f9  lea     rcx, [rbp+3F0h+var_190]
0x140162800  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x140162805  nop
0x140162806  mov     rcx, rax
0x140162809  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14016280f  mov     rdx, rax
0x140162812  lea     rcx, [rbp+3F0h+var_300]
0x140162819  call    cs:__imp_?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x14016281f  nop
0x140162820  lea     rcx, [rbp+3F0h+var_190]
0x140162827  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x14016282c  lea     rdx, asc_14020768C; "\a"
0x140162833  lea     rcx, [rbp+3F0h+var_300]
0x14016283a  call    cs:__imp_?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x140162840  mov     r8d, 0BC6F863Eh
0x140162846  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14016284d  mov     rdx, [rdx+1F0h]
0x140162854  lea     rcx, [rbp+3F0h+var_190]
0x14016285b  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x140162860  nop
0x140162861  mov     rcx, rax
0x140162864  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14016286a  mov     rdx, rax
0x14016286d  lea     rcx, [rbp+3F0h+var_300]
0x140162874  call    cs:__imp_?AppendWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::AppendWz(wchar_t const *)
0x14016287a  nop
0x14016287b  lea     rcx, [rbp+3F0h+var_190]
0x140162882  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x140162887  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14016288e  mov     rcx, [rax+1D0h]
0x140162895  mov     rcx, [rcx+68h]
0x140162899  mov     rax, [rcx]
0x14016289c  mov     rax, [rax+78h]
0x1401628a0  call    cs:__guard_dispatch_icall_fptr
0x1401628a6  mov     rbx, rax
0x1401628a9  lea     rcx, [rbp+3F0h+var_300]
0x1401628b0  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1401628b6  mov     rdi, rax
0x1401628b9  mov     r8d, 267D326Dh
0x1401628bf  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1401628c6  mov     rdx, [rdx+1F0h]
0x1401628cd  lea     rcx, [rbp+3F0h+var_190]
0x1401628d4  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x1401628d9  nop
0x1401628da  mov     rcx, rax
0x1401628dd  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1401628e3  mov     [rsp+4F0h+var_498], rbx
0x1401628e8  mov     [rsp+4F0h+var_4A0], 0
0x1401628f1  mov     [rsp+4F0h+var_4A8], 0
0x1401628f9  mov     [rsp+4F0h+var_4B0], 0
0x140162902  mov     [rsp+4F0h+var_4B8], 0
0x14016290a  mov     [rsp+4F0h+var_4C0], 1
0x140162912  mov     [rsp+4F0h+var_4C8], 0
0x14016291a  mov     [rsp+4F0h+var_4D0], 4
0x140162922  mov     r9d, 8
0x140162928  mov     r8, rdi
0x14016292b  mov     rdx, rax
0x14016292e  xor     ecx, ecx
0x140162930  call    cs:__imp_?LDoAlertTFC@@YAHPEAUIMsoUser@@PEB_W1HHHHH1JPEBQEB_WPEAUHWND__@@@Z; LDoAlertTFC(IMsoUser *,wchar_t const *,wchar_t const *,int,int,int,int,int,wchar_t const *,long,wchar_t const * const *,HWND__ *)
0x140162936  mov     ebx, eax
0x140162938  lea     rcx, [rbp+3F0h+var_190]
0x14016293f  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x140162944  cmp     ebx, 65h ; 'e'
0x140162947  jnz     short loc_140162984
0x140162949  mov     rcx, [r14+88h]
0x140162950  mov     rax, [rcx]
0x140162953  mov     rax, [rax+30h]
0x140162957  call    cs:__guard_dispatch_icall_fptr
0x14016295d  mov     r10, rax
0x140162960  mov     rcx, [rax]
0x140162963  mov     rax, [rcx+120h]
0x14016296a  mov     byte ptr [rsp+4F0h+var_4D0], 0
0x14016296f  xor     r9d, r9d
0x140162972  xor     r8d, r8d
0x140162975  mov     edx, 67E2h
0x14016297a  mov     rcx, r10
0x14016297d  call    cs:__guard_dispatch_icall_fptr
0x140162983  nop
0x140162984  lea     rcx, [rbp+3F0h+var_300]
0x14016298b  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x140162990  nop
0x140162991  lea     rcx, [rbp+3F0h+var_470]
0x140162995  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x14016299a  lea     rcx, [rsp+4F0h+var_480]; this
0x14016299f  call    ??1NotebookListDSSP@@QEAA@XZ; NotebookListDSSP::~NotebookListDSSP(void)
0x1401629a4  mov     rcx, [rbp+3F0h+var_20]
0x1401629ab  xor     rcx, rsp; StackCookie
0x1401629ae  call    __security_check_cookie
0x1401629b3  lea     r11, [rsp+4F0h+var_10]
0x1401629bb  mov     rbx, [r11+28h]
0x1401629bf  mov     rsi, [r11+30h]
0x1401629c3  mov     rsp, r11
0x1401629c6  pop     r14
0x1401629c8  pop     rdi
0x1401629c9  pop     rbp
0x1401629ca  retn
```
