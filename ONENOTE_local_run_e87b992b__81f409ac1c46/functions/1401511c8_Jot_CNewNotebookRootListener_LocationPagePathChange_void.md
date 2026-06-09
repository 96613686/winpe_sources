# Jot::CNewNotebookRootListener::LocationPagePathChange(void)

- ea: `0x1401511c8`
- end: `0x1401515db`
- name: `?LocationPagePathChange@CNewNotebookRootListener@Jot@@AEAAXXZ`
- size: `1043`
- prototype: `void __fastcall(Jot::CNewNotebookRootListener *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140151ccc`

## callees

- `0x14003f250`
- `0x1400488d0`
- `0x140048a58`
- `0x140048fb0`
- `0x140054290`
- `0x140056ac0`
- `0x140057580`
- `0x140074598`
- `0x1400aa238`
- `0x1400cdd94`
- `0x140150a54`
- `0x1401511c8`

## import_xrefs

- `onmain!?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z` at `0x140151364`
- `onmain!?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z` at `0x140151364`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x140151532`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x140151532`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x1401514b9`
- `onmain!?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z` at `0x1401514b9`
- `onmain!?priNotebookName@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14015124a`
- `onmain!?priNotebookEntityPath@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140151283`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140151572`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14015158b`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140151572`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14015158b`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401515a8`
- `mso40uiWin32Client!__imp_?EndDefer@Node@NetUI@@SAXXZ` at `0x1401515a8`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401511ff`
- `mso40uiWin32Client!__imp_?StartDefer@Node@NetUI@@SAXXZ` at `0x1401511ff`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14015134a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401513c9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401514c8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401514e7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x14015134a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401513c9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401514c8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1401514e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
void __fastcall Jot::CNewNotebookRootListener::LocationPagePathChange(Jot::CNewNotebookRootListener *this, __int64 a2)
{
  Jot::CNewNotebookRootListener *v2; // r13
  struct MsoCF::IPropertySet *v3; // rax
  _WORD **v4; // r14
  _WORD *v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  int v8; // ecx
  __int64 v9; // r9
  __int64 v10; // rdx
  char v11; // al
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64 *, __int64, _QWORD, _QWORD, char); // r12
  __int64 v17; // rax
  __int64 v18; // r15
  __int64 v19; // rdi
  __int64 *v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // rax
  _WORD **v25; // rbx
  _WORD **v26; // [rsp+40h] [rbp-228h] BYREF
  __int64 v27; // [rsp+48h] [rbp-220h] BYREF
  int v28; // [rsp+50h] [rbp-218h]
  __int64 v29; // [rsp+58h] [rbp-210h] BYREF
  int v30; // [rsp+60h] [rbp-208h]
  __int64 v31; // [rsp+68h] [rbp-200h] BYREF
  _QWORD *v32; // [rsp+70h] [rbp-1F8h]
  __int64 v33; // [rsp+78h] [rbp-1F0h] BYREF
  Jot::CNewNotebookRootListener *v34; // [rsp+80h] [rbp-1E8h]
  _WORD **v35; // [rsp+88h] [rbp-1E0h] BYREF
  __int64 v36; // [rsp+90h] [rbp-1D8h] BYREF
  _BYTE v37[40]; // [rsp+98h] [rbp-1D0h] BYREF
  _BYTE v38[376]; // [rsp+C0h] [rbp-1A8h] BYREF

  v2 = this;
  v34 = this;
  NetUI::Node::StartDefer(this, a2);
  v3 = Jot::CBaseRootElement::UsePropertySet(*((Jot::CBaseRootElement **)v2 + 9), 1);
  MsoCF::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>(
    &v35,
    v3);
  v4 = (_WORD **)((char *)v2 + 40);
  v26 = (_WORD **)((char *)v2 + 40);
  *((_QWORD *)v2 + 7) = 0;
  v5 = (_WORD *)((char *)v2 + 40);
  v6 = (_QWORD *)((char *)v2 + 64);
  v32 = (_QWORD *)((char *)v2 + 64);
  if ( *((_QWORD *)v2 + 8) > 7u )
    v5 = *v4;
  *v5 = 0;
  v7 = *((_QWORD *)v2 + 3);
  v27 = 0;
  if ( v7
    && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 48LL))(
         v7,
         Jot::PropertySpace_JotMain::priNotebookName,
         &v27) )
  {
    v8 = *((_DWORD *)&Jot::PropertySpace_JotMain::priNotebookName + 1);
  }
  else
  {
    v8 = 0;
  }
  v28 = v8;
  v9 = *((_QWORD *)v2 + 3);
  v10 = 0;
  v29 = 0;
  if ( v9
    && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 48LL))(
                v9,
                Jot::PropertySpace_Jot11::priNotebookEntityPath,
                &v29),
        v8 = v28,
        v10 = v29,
        v11) )
  {
    v12 = *((_DWORD *)&Jot::PropertySpace_Jot11::priNotebookEntityPath + 1);
  }
  else
  {
    v12 = 0;
  }
  v30 = v12;
  if ( v8 && v8 != 2031647 && v12 && v12 != 2031647 )
  {
    v31 = 0;
    if ( v12 != 117899322 || !v10 )
    {
      CrashWithRecovery(0x65756F6Eu, 0);
      goto LABEL_35;
    }
    v13 = (*(_DWORD *)(v10 + 4) >> 1) & 0x1FFFFFFF;
    v14 = v10 + 8;
    if ( v10 != -8 && (!(_DWORD)v13 || _std_find_trivial_2(v14, v10 + 2 * (v13 + 4), 0) == v10 + 2 * (v13 + 4)) )
    {
      CrashWithRecovery(0x1F46100Du, 0);
      __debugbreak();
    }
    Jot::GetFolderProxyFromPath_Exported(v14, &v31, 0, 0, 0);
    v15 = v31;
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, _QWORD, char))(*(_QWORD *)v31 + 80LL);
    if ( v28 == 117899322 && v27 )
    {
      v17 = (*(_DWORD *)(v27 + 4) >> 1) & 0x1FFFFFFF;
      v18 = v27 + 8;
      if ( v27 != -8 )
      {
        if ( !(_DWORD)v17 || (v19 = v27 + 8 + 2 * v17, _std_find_trivial_2(v27 + 8, v19, 0) == v19) )
        {
          CrashWithRecovery(0x1F46100Du, 0);
          __debugbreak();
        }
      }
      v20 = (__int64 *)v16(v15, &v33, v18, 0, 0, 1);
      v21 = *v20;
      *v20 = 0;
      v36 = v21;
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
      v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v22 + 112LL))(v22, v37, 0);
      std::wstring::operator=((char *)v2 + 40, v23);
      std::wstring::~wstring(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    else
    {
      CrashWithRecovery(0x65756F6Eu, 0);
      v2 = v34;
      v4 = v26;
    }
    v6 = v32;
  }
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v38);
  if ( !*((_QWORD *)v2 + 7) )
  {
    Jot::CWzInBuffer::SetFromResource(
      (Jot::CWzInBuffer *)v38,
      *((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 62),
      0x4146025Eu);
    goto LABEL_38;
  }
LABEL_35:
  if ( *v6 > 7u )
    v4 = (_WORD **)*v4;
  v26 = v4;
  Jot::CWzInBuffer::SetFromPattern<wchar_t const *>(
    v38,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    2291401780LL,
    &v26);
LABEL_38:
  v24 = (_QWORD *)Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(v38, &v36);
  v25 = v35;
  v26 = v35;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotExe::prtidNewNotebook_FullPathLabel,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v26,
    *v24);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v38);
  if ( (v30 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v29);
  if ( (v28 & 0x2000000) != 0 )
    MsoCF::CPropertyData::FreeAndZero_ComplexType(&v27);
  if ( v25 )
    (*((void (__fastcall **)(_WORD **))*v25 + 2))(v25);
  NetUI::Node::EndDefer();
}

```

## disassembly

```asm
0x1401511c8  mov     [rsp+arg_8], rbx
0x1401511cd  mov     [rsp+arg_10], rsi
0x1401511d2  push    rdi
0x1401511d3  push    r12
0x1401511d5  push    r13
0x1401511d7  push    r14
0x1401511d9  push    r15
0x1401511db  sub     rsp, 240h
0x1401511e2  mov     rax, cs:__security_cookie
0x1401511e9  xor     rax, rsp
0x1401511ec  mov     [rsp+268h+var_30], rax
0x1401511f4  mov     r13, rcx
0x1401511f7  mov     [rsp+268h+var_1E8], rcx
0x1401511ff  call    cs:__imp_?StartDefer@Node@NetUI@@SAXXZ; NetUI::Node::StartDefer(void)
0x140151205  mov     edx, 1; int
0x14015120a  mov     rcx, [r13+48h]; this
0x14015120e  call    ?UsePropertySet@CBaseRootElement@Jot@@QEAAPEAUIPropertySet@MsoCF@@H@Z; Jot::CBaseRootElement::UsePropertySet(int)
0x140151213  mov     rdx, rax
0x140151216  lea     rcx, [rsp+268h+var_1E0]
0x14015121e  call    ??0?$CIPtr@VCHiddenChunkControlUser@Jot@@V12@@MsoCF@@QEAA@PEAVCHiddenChunkControlUser@Jot@@@Z; MsoCF::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>::CIPtr<Jot::CHiddenChunkControlUser,Jot::CHiddenChunkControlUser>(Jot::CHiddenChunkControlUser *)
0x140151223  lea     r14, [r13+28h]
0x140151227  mov     [rsp+268h+var_228], r14
0x14015122c  xor     esi, esi
0x14015122e  mov     [r14+10h], rsi
0x140151232  mov     rax, r14
0x140151235  lea     rdi, [r14+18h]
0x140151239  mov     [rsp+268h+var_1F8], rdi
0x14015123e  cmp     qword ptr [rdi], 7
0x140151242  jbe     short loc_140151247
0x140151244  mov     rax, [r14]
0x140151247  mov     [rax], si
0x14015124a  mov     rbx, cs:__imp_?priNotebookName@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priNotebookName
0x140151251  mov     rcx, [r13+18h]
0x140151255  mov     [rsp+268h+var_220], rsi
0x14015125a  test    rcx, rcx
0x14015125d  jz      short loc_14015127D
0x14015125f  mov     rax, [rcx]
0x140151262  lea     r8, [rsp+268h+var_220]
0x140151267  mov     rdx, rbx
0x14015126a  mov     rax, [rax+30h]
0x14015126e  call    cs:__guard_dispatch_icall_fptr
0x140151274  test    al, al
0x140151276  jz      short loc_14015127D
0x140151278  mov     ecx, [rbx+4]
0x14015127b  jmp     short loc_14015127F
0x14015127d  mov     ecx, esi
0x14015127f  mov     [rsp+268h+var_218], ecx
0x140151283  mov     rbx, cs:__imp_?priNotebookEntityPath@PropertySpace_Jot11@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_Jot11::priNotebookEntityPath
0x14015128a  mov     r9, [r13+18h]
0x14015128e  mov     rdx, rsi
0x140151291  mov     [rsp+268h+var_210], rdx
0x140151296  test    r9, r9
0x140151299  jz      short loc_1401512C5
0x14015129b  mov     rax, [r9]
0x14015129e  lea     r8, [rsp+268h+var_210]
0x1401512a3  mov     rdx, rbx
0x1401512a6  mov     rcx, r9
0x1401512a9  mov     rax, [rax+30h]
0x1401512ad  call    cs:__guard_dispatch_icall_fptr
0x1401512b3  mov     ecx, [rsp+268h+var_218]
0x1401512b7  mov     rdx, [rsp+268h+var_210]
0x1401512bc  test    al, al
0x1401512be  jz      short loc_1401512C5
0x1401512c0  mov     eax, [rbx+4]
0x1401512c3  jmp     short loc_1401512C7
0x1401512c5  mov     eax, esi
0x1401512c7  mov     [rsp+268h+var_208], eax
0x1401512cb  test    ecx, ecx
0x1401512cd  jz      loc_14015148A
0x1401512d3  mov     r8d, 1F001Fh
0x1401512d9  cmp     ecx, r8d
0x1401512dc  jz      loc_14015148A
0x1401512e2  test    eax, eax
0x1401512e4  jz      loc_14015148A
0x1401512ea  cmp     eax, r8d
0x1401512ed  jz      loc_14015148A
0x1401512f3  mov     [rsp+268h+var_200], rsi
0x1401512f8  mov     r15d, 707003Ah
0x1401512fe  cmp     eax, r15d
0x140151301  jnz     loc_1401514E0
0x140151307  test    rdx, rdx
0x14015130a  jz      loc_1401514E0
0x140151310  mov     eax, [rdx+4]
0x140151313  shr     eax, 1
0x140151315  and     eax, 1FFFFFFFh
0x14015131a  lea     rdi, [rdx+8]
0x14015131e  test    rdi, rdi
0x140151321  jz      short loc_140151351
0x140151323  cmp     eax, 1
0x140151326  jb      short loc_140151343
0x140151328  add     rax, 4
0x14015132c  lea     rbx, [rdx+rax*2]
0x140151330  xor     r8d, r8d
0x140151333  mov     rdx, rbx
0x140151336  mov     rcx, rdi
0x140151339  call    __std_find_trivial_2
0x14015133e  cmp     rax, rbx
0x140151341  jnz     short loc_140151351
0x140151343  xor     edx, edx
0x140151345  mov     ecx, 1F46100Dh
0x14015134a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140151350  int     3; Trap to Debugger
0x140151351  mov     byte ptr [rsp+268h+var_248], sil
0x140151356  xor     r9d, r9d
0x140151359  xor     r8d, r8d
0x14015135c  lea     rdx, [rsp+268h+var_200]
0x140151361  mov     rcx, rdi
0x140151364  call    cs:__imp_?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z; Jot::GetFolderProxyFromPath_Exported(MsoCF::String<MsoCF::WzTraits>,Jot::IFolderProxy * *,bool,bool *,bool)
0x14015136a  mov     rbx, [rsp+268h+var_200]
0x14015136f  mov     rax, [rbx]
0x140151372  mov     r12, [rax+50h]
0x140151376  cmp     [rsp+268h+var_218], r15d
0x14015137b  jnz     loc_1401514C1
0x140151381  mov     rcx, [rsp+268h+var_220]
0x140151386  test    rcx, rcx
0x140151389  jz      loc_1401514C1
0x14015138f  mov     eax, [rcx+4]
0x140151392  shr     eax, 1
0x140151394  and     eax, 1FFFFFFFh
0x140151399  lea     r15, [rcx+8]
0x14015139d  test    r15, r15
0x1401513a0  jz      short loc_1401513D0
0x1401513a2  cmp     eax, 1
0x1401513a5  jb      short loc_1401513C2
0x1401513a7  add     rcx, 8
0x1401513ab  lea     rdi, [rcx+rax*2]
0x1401513af  xor     r8d, r8d
0x1401513b2  mov     rdx, rdi
0x1401513b5  mov     rcx, r15
0x1401513b8  call    __std_find_trivial_2
0x1401513bd  cmp     rax, rdi
0x1401513c0  jnz     short loc_1401513D0
0x1401513c2  xor     edx, edx
0x1401513c4  mov     ecx, 1F46100Dh
0x1401513c9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1401513cf  int     3; Trap to Debugger
0x1401513d0  mov     [rsp+268h+var_240], 1
0x1401513d5  mov     [rsp+268h+var_248], rsi
0x1401513da  xor     r9d, r9d
0x1401513dd  mov     r8, r15
0x1401513e0  lea     rdx, [rsp+268h+var_1F0]
0x1401513e5  mov     rcx, rbx
0x1401513e8  mov     rax, r12
0x1401513eb  call    cs:__guard_dispatch_icall_fptr
0x1401513f1  mov     rbx, [rax]
0x1401513f4  mov     [rax], rsi
0x1401513f7  mov     [rsp+268h+var_1D8], rbx
0x1401513ff  mov     rcx, [rsp+268h+var_1F0]
0x140151404  test    rcx, rcx
0x140151407  jz      short loc_140151416
0x140151409  mov     rax, [rcx]
0x14015140c  mov     rax, [rax+10h]
0x140151410  call    cs:__guard_dispatch_icall_fptr
0x140151416  mov     rax, [rbx]
0x140151419  mov     rcx, rbx
0x14015141c  mov     rax, [rax+18h]
0x140151420  call    cs:__guard_dispatch_icall_fptr
0x140151426  mov     r9, rax
0x140151429  mov     rcx, [rax]
0x14015142c  mov     rax, [rcx+70h]
0x140151430  xor     r8d, r8d
0x140151433  lea     rdx, [rsp+268h+var_1D0]
0x14015143b  mov     rcx, r9
0x14015143e  call    cs:__guard_dispatch_icall_fptr
0x140151444  mov     rdx, rax
0x140151447  mov     rcx, r14
0x14015144a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14015144f  lea     rcx, [rsp+268h+var_1D0]; void *
0x140151457  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14015145c  nop
0x14015145d  mov     rax, [rbx]
0x140151460  mov     rcx, rbx
0x140151463  mov     rax, [rax+10h]
0x140151467  call    cs:__guard_dispatch_icall_fptr
0x14015146d  mov     rcx, [rsp+268h+var_200]
0x140151472  test    rcx, rcx
0x140151475  jz      short loc_140151485
0x140151477  mov     rax, [rcx]
0x14015147a  mov     rax, [rax+10h]
0x14015147e  call    cs:__guard_dispatch_icall_fptr
0x140151484  nop
0x140151485  mov     rdi, [rsp+268h+var_1F8]
0x14015148a  lea     rcx, [rsp+268h+var_1A8]
0x140151492  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140151497  cmp     [r13+38h], rsi
0x14015149b  jnz     short loc_1401514EE
0x14015149d  mov     r8d, 4146025Eh
0x1401514a3  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1401514aa  mov     rdx, [rdx+1F0h]
0x1401514b1  lea     rcx, [rsp+268h+var_1A8]
0x1401514b9  call    cs:__imp_?SetFromResource@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer::SetFromResource(HINSTANCE__ *,uint)
0x1401514bf  jmp     short loc_140151522
0x1401514c1  xor     edx, edx
0x1401514c3  mov     ecx, 65756F6Eh
0x1401514c8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1401514ce  nop
0x1401514cf  xor     esi, esi
0x1401514d1  mov     r13, [rsp+268h+var_1E8]
0x1401514d9  mov     r14, [rsp+268h+var_228]
0x1401514de  jmp     short loc_140151485
0x1401514e0  xor     edx, edx
0x1401514e2  mov     ecx, 65756F6Eh
0x1401514e7  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1401514ed  nop
0x1401514ee  cmp     qword ptr [rdi], 7
0x1401514f2  jbe     short loc_1401514F7
0x1401514f4  mov     r14, [r14]
0x1401514f7  mov     [rsp+268h+var_228], r14
0x1401514fc  lea     r9, [rsp+268h+var_228]
0x140151501  mov     r8d, 88940434h
0x140151507  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14015150e  mov     rdx, [rdx+1F0h]
0x140151515  lea     rcx, [rsp+268h+var_1A8]
0x14015151d  call    ??$SetFromPattern@PEB_W@CWzInBuffer@Jot@@QEAAXPEAUHINSTANCE__@@IAEBQEB_W@Z; Jot::CWzInBuffer::SetFromPattern<wchar_t const *>(HINSTANCE__ *,uint,wchar_t const * const &)
0x140151522  lea     rdx, [rsp+268h+var_1D8]
0x14015152a  lea     rcx, [rsp+268h+var_1A8]
0x140151532  call    cs:__imp_??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ; Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(void)
0x140151538  mov     rbx, [rsp+268h+var_1E0]
0x140151540  mov     [rsp+268h+var_228], rbx
0x140151545  mov     rdx, [rax]
0x140151548  lea     rcx, [rsp+268h+var_228]
0x14015154d  call    ??4?$CEntry@VprtidNewNotebook_FullPathLabel@PropertySpace_JotExe@Jot@@V?$CIPtr@V?$IStringInAtom@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@V12@@MsoCF@@@IPropertySet@MsoCF@@QEAAAEAV012@V?$String@UWzTraits@MsoCF@@@2@@Z; MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotExe::prtidNewNotebook_FullPathLabel,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(MsoCF::String<MsoCF::WzTraits>)
0x140151552  nop
0x140151553  lea     rcx, [rsp+268h+var_1A8]
0x14015155b  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x140151560  mov     edx, [rsp+268h+var_208]
0x140151564  mov     eax, edx
0x140151566  shr     eax, 19h
0x140151569  test    al, 1
0x14015156b  jz      short loc_140151579
0x14015156d  lea     rcx, [rsp+268h+var_210]
0x140151572  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140151578  nop
0x140151579  mov     edx, [rsp+268h+var_218]
0x14015157d  mov     eax, edx
0x14015157f  shr     eax, 19h
0x140151582  test    al, 1
0x140151584  jz      short loc_140151592
0x140151586  lea     rcx, [rsp+268h+var_220]
0x14015158b  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140151591  nop
0x140151592  test    rbx, rbx
0x140151595  jz      short loc_1401515A8
0x140151597  mov     rax, [rbx]
0x14015159a  mov     rcx, rbx
0x14015159d  mov     rax, [rax+10h]
0x1401515a1  call    cs:__guard_dispatch_icall_fptr
0x1401515a7  nop
0x1401515a8  call    cs:__imp_?EndDefer@Node@NetUI@@SAXXZ; NetUI::Node::EndDefer(void)
0x1401515ae  mov     rcx, [rsp+268h+var_30]
0x1401515b6  xor     rcx, rsp; StackCookie
0x1401515b9  call    __security_check_cookie
0x1401515be  lea     r11, [rsp+268h+var_28]
0x1401515c6  mov     rbx, [r11+38h]
0x1401515ca  mov     rsi, [r11+40h]
0x1401515ce  mov     rsp, r11
0x1401515d1  pop     r15
0x1401515d3  pop     r14
0x1401515d5  pop     r13
0x1401515d7  pop     r12
0x1401515d9  pop     rdi
0x1401515da  retn
```
