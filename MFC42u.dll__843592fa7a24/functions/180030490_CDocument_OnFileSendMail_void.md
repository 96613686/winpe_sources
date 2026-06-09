# CDocument::OnFileSendMail(void)

- ea: `0x180030490`
- end: `0x180030845`
- name: `?OnFileSendMail@CDocument@@IEAAXXZ`
- size: `949`
- prototype: `void __fastcall(CDocument *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, loader_planting`

## callers

- `0x18006c8d0`

## callees

- `0x1800096d0`
- `0x180013330`
- `0x180013520`
- `0x180019290`
- `0x180020ac0`
- `0x180026a40`
- `0x18002ac00`
- `0x18002d770`
- `0x18002da20`
- `0x18002e1f0`
- `0x18002e2e0`
- `0x180030490`
- `0x180030850`
- `0x180032330`
- `0x180033f20`
- `0x18003fb90`
- `0x180040350`
- `0x1800441c0`
- `0x1800d1f92`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800306d2`
- `msvcrt!wcscat_s` at `0x1800306d2`
- `msvcrt!wcscpy_s` at `0x180030587`
- `msvcrt!wcscpy_s` at `0x180030653`
- `msvcrt!wcscpy_s` at `0x180030587`
- `msvcrt!wcscpy_s` at `0x180030653`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800305c0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800305c0`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800305a2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800305a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030535`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030535`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180030507`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180030507`
- `USER32!SetActiveWindow` at `0x1800307b0`
- `USER32!SetActiveWindow` at `0x1800307b0`
- `USER32!SetFocus` at `0x180030770`
- `USER32!SetFocus` at `0x180030770`
- `USER32!EnableWindow` at `0x1800307d3`
- `USER32!EnableWindow` at `0x1800307d3`
- `USER32!ReleaseCapture` at `0x180030799`
- `USER32!ReleaseCapture` at `0x180030799`

## string_xrefs

- `0x180030500`: `MAPI32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDocument::OnFileSendMail(const wchar_t **this)
{
  struct CNoTrackObject *Data; // rax
  struct CNoTrackObject *v3; // rbx
  HMODULE Library; // rax
  UINT v5; // ecx
  FARPROC ProcAddress; // r15
  int v7; // edi
  unsigned int v8; // edi
  int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rbx
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  struct AFX_MODULE_STATE *ModuleState; // rax
  unsigned int *SafeOwner; // rbx
  int v16; // esi
  struct AFX_MODULE_STATE *v17; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  CHAR *v23; // [rsp+50h] [rbp-B0h]
  CHAR *v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  _BYTE v26[80]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+C0h] [rbp-40h]
  __int64 *v28; // [rsp+C8h] [rbp-38h]
  wchar_t WideCharStr[264]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Destination[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+4F0h] [rbp+3F0h] BYREF
  CHAR v32[272]; // [rsp+600h] [rbp+500h] BYREF
  WCHAR Buffer[264]; // [rsp+710h] [rbp+610h] BYREF

  CWaitCursor::CWaitCursor((CWaitCursor *)v18);
  Data = CProcessLocalObject::GetData(
           (CProcessLocalObject *)&_afxMailState,
           CProcessLocal<_AFX_MAIL_STATE>::CreateObject);
  v3 = Data;
  if ( !Data )
    AfxThrowInvalidArgException();
  Library = (HMODULE)*((_QWORD *)Data + 1);
  if ( !Library )
  {
    Library = LoadLibraryExA("MAPI32.DLL", 0, 0x800u);
    *((_QWORD *)v3 + 1) = Library;
    if ( !Library )
    {
      v5 = 61840;
LABEL_6:
      AfxMessageBox(v5, 0, 0xFFFFFFFF);
      goto LABEL_32;
    }
  }
  ProcAddress = GetProcAddress(Library, "MAPISendMail");
  if ( !ProcAddress )
  {
    v5 = 61841;
    goto LABEL_6;
  }
  if ( !*((_DWORD *)this[9] - 2) || (*((unsigned int (__fastcall **)(const wchar_t **))*this + 24))(this) )
  {
    GetTempPathW(0x104u, Buffer);
    GetTempFileNameW(Buffer, L"afx", 0, Destination);
    v8 = (*((__int64 (__fastcall **)(const wchar_t **))*this + 24))(this);
    v9 = (*((__int64 (__fastcall **)(const wchar_t **, wchar_t *, _QWORD))*this + 40))(this, Destination, 0);
    (*((void (__fastcall **)(const wchar_t **, _QWORD))*this + 25))(this, v8);
    if ( !v9 )
      goto LABEL_32;
    v7 = 1;
  }
  else
  {
    v7 = 0;
    wcscpy_s(Destination, 0x104u, this[9]);
  }
  _wcstombsz(MultiByteStr, Destination, 0x104u);
  v10 = (wchar_t *)this[9];
  if ( *((_DWORD *)v10 - 2) )
  {
    AfxGetFileName(v10, WideCharStr, 0x104u);
  }
  else
  {
    wcscpy_s(WideCharStr, 0x104u, this[8]);
    v11 = -1;
    if ( (unsigned int)CString::Find((CString *)(this + 8), 0x2Eu, 0) == -1 )
    {
      Source = (wchar_t *)_afxPchNil;
      v12 = this[10];
      if ( v12 )
      {
        if ( (*(unsigned int (__fastcall **)(const wchar_t *, wchar_t **, __int64))(*(_QWORD *)v12 + 216LL))(
               v12,
               &Source,
               4) )
        {
          v13 = -1;
          do
            ++v13;
          while ( WideCharStr[v13] );
          do
            ++v11;
          while ( Source[v11] );
          if ( (unsigned __int64)(v11 + v13) < 0x104 )
            wcscat_s(WideCharStr, 0x104u, Source);
        }
      }
      CString::~CString((CString *)&Source);
    }
  }
  _wcstombsz(v32, WideCharStr, 0x104u);
  v20 = 0;
  v22 = 0;
  v25 = 0;
  v21 = -1;
  v23 = MultiByteStr;
  v24 = v32;
  memset_0(v26, 0, 0x60u);
  v27 = 1;
  v28 = &v20;
  ModuleState = AfxGetModuleState();
  CWinApp::EnableModeless(*((CWinApp **)ModuleState + 1), 0);
  Source = 0;
  SafeOwner = (unsigned int *)CWnd::GetSafeOwner(0, (HWND *)&Source);
  CWnd::SetCapture((CWnd *)SafeOwner);
  SetFocus(0);
  SafeOwner[20] |= 4u;
  v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _BYTE *, __int64, _DWORD))ProcAddress)(0, SafeOwner[16], v26, 9, 0);
  ReleaseCapture();
  SafeOwner[20] &= ~4u;
  CWnd::EnableWindow((CWnd *)SafeOwner, 1);
  SetActiveWindow(0);
  CWnd::SetActiveWindow((CWnd *)SafeOwner);
  CWnd::SetFocus((CWnd *)SafeOwner);
  if ( Source )
    EnableWindow((HWND)Source, 1);
  v17 = AfxGetModuleState();
  CWinApp::EnableModeless(*((CWinApp **)v17 + 1), 1);
  if ( (v16 & 0xFFFFFFFC) != 0 || v16 == 2 )
    AfxMessageBox(0xF192u, 0, 0xFFFFFFFF);
  if ( v7 )
    CFile::Remove(Destination);
LABEL_32:
  CWaitCursor::~CWaitCursor((CWaitCursor *)v18);
}

```

## disassembly

```asm
0x180030490  push    rbp
0x180030492  push    rbx
0x180030493  push    rsi
0x180030494  push    rdi
0x180030495  push    r12
0x180030497  push    r13
0x180030499  push    r14
0x18003049b  push    r15
0x18003049d  lea     rbp, [rsp-838h]
0x1800304a5  sub     rsp, 938h
0x1800304ac  mov     rax, cs:__security_cookie
0x1800304b3  xor     rax, rsp
0x1800304b6  mov     [rbp+870h+var_50], rax
0x1800304bd  mov     rsi, rcx
0x1800304c0  lea     rcx, [rsp+970h+var_940]; this
0x1800304c5  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x1800304ca  nop
0x1800304cb  lea     rdx, ?CreateObject@?$CProcessLocal@V_AFX_MAIL_STATE@@@@SAPEAVCNoTrackObject@@XZ; struct CNoTrackObject *(*)(void)
0x1800304d2  lea     rcx, ?_afxMailState@@3V?$CProcessLocal@V_AFX_MAIL_STATE@@@@A; this
0x1800304d9  call    ?GetData@CProcessLocalObject@@QEAAPEAVCNoTrackObject@@P6APEAV2@XZ@Z; CProcessLocalObject::GetData(CNoTrackObject * (*)(void))
0x1800304de  mov     rbx, rax
0x1800304e1  xor     r12d, r12d
0x1800304e4  test    rax, rax
0x1800304e7  jnz     short loc_1800304EF
0x1800304e9  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x1800304ef  mov     rax, [rax+8]
0x1800304f3  test    rax, rax
0x1800304f6  jnz     short loc_18003052B
0x1800304f8  xor     edx, edx; hFile
0x1800304fa  mov     r8d, 800h; dwFlags
0x180030500  lea     rcx, aMapi32Dll_0; "MAPI32.DLL"
0x180030507  call    cs:__imp_LoadLibraryExA
0x18003050d  mov     [rbx+8], rax
0x180030511  test    rax, rax
0x180030514  jnz     short loc_18003052B
0x180030516  mov     ecx, 0F190h; uID
0x18003051b  or      r8d, 0FFFFFFFFh; unsigned int
0x18003051f  xor     edx, edx; unsigned int
0x180030521  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180030526  jmp     loc_180030818
0x18003052b  lea     rdx, aMapisendmail; "MAPISendMail"
0x180030532  mov     rcx, rax; hModule
0x180030535  call    cs:__imp_GetProcAddress
0x18003053b  mov     r15, rax
0x18003053e  test    rax, rax
0x180030541  jnz     short loc_18003054A
0x180030543  mov     ecx, 0F191h
0x180030548  jmp     short loc_18003051B
0x18003054a  mov     rax, [rsi+48h]
0x18003054e  mov     r13d, 1
0x180030554  cmp     [rax-8], r12d
0x180030558  jz      short loc_180030592
0x18003055a  mov     rax, [rsi]
0x18003055d  mov     rcx, rsi
0x180030560  mov     rax, [rax+0C0h]
0x180030567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003056c  test    eax, eax
0x18003056e  jnz     short loc_180030592
0x180030570  mov     edi, r12d
0x180030573  mov     r8, [rsi+48h]; Source
0x180030577  mov     r14d, 104h
0x18003057d  mov     edx, r14d; SizeInWords
0x180030580  lea     rcx, [rbp+870h+Destination]; Destination
0x180030587  call    cs:__imp_wcscpy_s
0x18003058d  jmp     loc_180030617
0x180030592  lea     rdx, [rbp+870h+Buffer]; lpBuffer
0x180030599  mov     r14d, 104h
0x18003059f  mov     ecx, r14d; nBufferLength
0x1800305a2  call    cs:__imp_GetTempPathW
0x1800305a8  lea     r9, [rbp+870h+Destination]; lpTempFileName
0x1800305af  xor     r8d, r8d; uUnique
0x1800305b2  lea     rdx, PrefixString; "afx"
0x1800305b9  lea     rcx, [rbp+870h+Buffer]; lpPathName
0x1800305c0  call    cs:__imp_GetTempFileNameW
0x1800305c6  mov     rax, [rsi]
0x1800305c9  mov     rcx, rsi
0x1800305cc  mov     rax, [rax+0C0h]
0x1800305d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305d8  mov     edi, eax
0x1800305da  mov     rcx, [rsi]
0x1800305dd  mov     rax, [rcx+140h]
0x1800305e4  xor     r8d, r8d
0x1800305e7  lea     rdx, [rbp+870h+Destination]
0x1800305ee  mov     rcx, rsi
0x1800305f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305f6  mov     ebx, eax
0x1800305f8  mov     rcx, [rsi]
0x1800305fb  mov     rax, [rcx+0C8h]
0x180030602  mov     edx, edi
0x180030604  mov     rcx, rsi
0x180030607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003060c  test    ebx, ebx
0x18003060e  jz      loc_180030818
0x180030614  mov     edi, r13d
0x180030617  mov     r8d, r14d; cbMultiByte
0x18003061a  lea     rdx, [rbp+870h+Destination]; lpWideCharStr
0x180030621  lea     rcx, [rbp+870h+MultiByteStr]; lpMultiByteStr
0x180030628  call    ?_wcstombsz@@YAHPEADPEBGI@Z; _wcstombsz(char *,ushort const *,uint)
0x18003062d  mov     rcx, [rsi+48h]; Source
0x180030631  cmp     [rcx-8], r12d
0x180030635  jz      short loc_180030648
0x180030637  mov     r8d, r14d; SizeInWords
0x18003063a  lea     rdx, [rbp+870h+WideCharStr]; Destination
0x18003063e  call    ?AfxGetFileName@@YAIPEBGPEAGI@Z; AfxGetFileName(ushort const *,ushort *,uint)
0x180030643  jmp     loc_1800306E3
0x180030648  mov     r8, [rsi+40h]; Source
0x18003064c  mov     rdx, r14; SizeInWords
0x18003064f  lea     rcx, [rbp+870h+WideCharStr]; Destination
0x180030653  call    cs:__imp_wcscpy_s
0x180030659  mov     edx, 2Eh ; '.'; unsigned __int16
0x18003065e  xor     r8d, r8d; int
0x180030661  lea     rcx, [rsi+40h]; this
0x180030665  call    ?Find@CString@@QEBAHGH@Z; CString::Find(ushort,int)
0x18003066a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003066e  cmp     eax, ebx
0x180030670  jnz     short loc_1800306E3
0x180030672  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180030679  mov     [rsp+970h+Source], rax
0x18003067e  mov     rcx, [rsi+50h]
0x180030682  test    rcx, rcx
0x180030685  jz      short loc_1800306D9
0x180030687  mov     rax, [rcx]
0x18003068a  lea     r8d, [rbx+5]
0x18003068e  lea     rdx, [rsp+970h+Source]
0x180030693  mov     rax, [rax+0D8h]
0x18003069a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003069f  test    eax, eax
0x1800306a1  jz      short loc_1800306D9
0x1800306a3  lea     rcx, [rbp+870h+WideCharStr]
0x1800306a7  mov     rax, rbx
0x1800306aa  inc     rax
0x1800306ad  cmp     [rcx+rax*2], r12w
0x1800306b2  jnz     short loc_1800306AA
0x1800306b4  mov     r8, [rsp+970h+Source]; Source
0x1800306b9  inc     rbx
0x1800306bc  cmp     [r8+rbx*2], r12w
0x1800306c1  jnz     short loc_1800306B9
0x1800306c3  add     rax, rbx
0x1800306c6  cmp     rax, r14
0x1800306c9  jnb     short loc_1800306D9
0x1800306cb  mov     rdx, r14; SizeInWords
0x1800306ce  lea     rcx, [rbp+870h+WideCharStr]; Destination
0x1800306d2  call    cs:__imp_wcscat_s
0x1800306d8  nop
0x1800306d9  lea     rcx, [rsp+970h+Source]; this
0x1800306de  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800306e3  mov     r8d, r14d; cbMultiByte
0x1800306e6  lea     rdx, [rbp+870h+WideCharStr]; lpWideCharStr
0x1800306ea  lea     rcx, [rbp+870h+var_370]; lpMultiByteStr
0x1800306f1  call    ?_wcstombsz@@YAHPEADPEBGI@Z; _wcstombsz(char *,ushort const *,uint)
0x1800306f6  mov     [rsp+970h+var_930], r12
0x1800306fb  mov     [rsp+970h+var_924], r12d
0x180030700  mov     [rsp+970h+var_910], r12
0x180030705  mov     [rsp+970h+var_928], 0FFFFFFFFh
0x18003070d  lea     rax, [rbp+870h+MultiByteStr]
0x180030714  mov     [rsp+970h+var_920], rax
0x180030719  lea     rax, [rbp+870h+var_370]
0x180030720  mov     [rsp+970h+var_918], rax
0x180030725  xor     edx, edx; Val
0x180030727  lea     r8d, [rdx+60h]; Size
0x18003072b  lea     rcx, [rsp+970h+var_900]; void *
0x180030730  call    memset_0
0x180030735  mov     [rbp+870h+var_8B0], r13d
0x180030739  lea     rax, [rsp+970h+var_930]
0x18003073e  mov     [rbp+870h+var_8A8], rax
0x180030742  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180030747  xor     edx, edx; int
0x180030749  mov     rcx, [rax+8]; this
0x18003074d  call    ?EnableModeless@CWinApp@@QEAAXH@Z; CWinApp::EnableModeless(int)
0x180030752  mov     [rsp+970h+Source], r12
0x180030757  lea     rdx, [rsp+970h+Source]; HWND *
0x18003075c  xor     ecx, ecx; struct CWnd *
0x18003075e  call    ?GetSafeOwner@CWnd@@SAPEAV1@PEAV1@PEAPEAUHWND__@@@Z; CWnd::GetSafeOwner(CWnd *,HWND__ * *)
0x180030763  mov     rbx, rax
0x180030766  mov     rcx, rax; this
0x180030769  call    ?SetCapture@CWnd@@QEAAPEAV1@XZ; CWnd::SetCapture(void)
0x18003076e  xor     ecx, ecx; hWnd
0x180030770  call    cs:__imp_SetFocus
0x180030776  or      dword ptr [rbx+50h], 4
0x18003077a  mov     edx, [rbx+40h]
0x18003077d  mov     [rsp+970h+var_950], r12d
0x180030782  mov     r9d, 9
0x180030788  lea     r8, [rsp+970h+var_900]
0x18003078d  xor     ecx, ecx
0x18003078f  mov     rax, r15
0x180030792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030797  mov     esi, eax
0x180030799  call    cs:__imp_ReleaseCapture
0x18003079f  and     dword ptr [rbx+50h], 0FFFFFFFBh
0x1800307a3  mov     edx, r13d; int
0x1800307a6  mov     rcx, rbx; this
0x1800307a9  call    ?EnableWindow@CWnd@@QEAAHH@Z; CWnd::EnableWindow(int)
0x1800307ae  xor     ecx, ecx; hWnd
0x1800307b0  call    cs:__imp_SetActiveWindow
0x1800307b6  mov     rcx, rbx; this
0x1800307b9  call    ?SetActiveWindow@CWnd@@QEAAPEAV1@XZ; CWnd::SetActiveWindow(void)
0x1800307be  mov     rcx, rbx; this
0x1800307c1  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x1800307c6  mov     rcx, [rsp+970h+Source]; hWnd
0x1800307cb  test    rcx, rcx
0x1800307ce  jz      short loc_1800307D9
0x1800307d0  mov     edx, r13d; bEnable
0x1800307d3  call    cs:__imp_EnableWindow
0x1800307d9  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800307de  mov     edx, r13d; int
0x1800307e1  mov     rcx, [rax+8]; this
0x1800307e5  call    ?EnableModeless@CWinApp@@QEAAXH@Z; CWinApp::EnableModeless(int)
0x1800307ea  test    esi, 0FFFFFFFCh
0x1800307f0  jnz     short loc_1800307F7
0x1800307f2  cmp     esi, 2
0x1800307f5  jnz     short loc_180030807
0x1800307f7  or      r8d, 0FFFFFFFFh; unsigned int
0x1800307fb  xor     edx, edx; unsigned int
0x1800307fd  mov     ecx, 0F192h; uID
0x180030802  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180030807  test    edi, edi
0x180030809  jz      short loc_180030818
0x18003080b  lea     rcx, [rbp+870h+Destination]; unsigned __int16 *
0x180030812  call    ?Remove@CFile@@SAXPEBG@Z; CFile::Remove(ushort const *)
0x180030817  nop
0x180030818  lea     rcx, [rsp+970h+var_940]; this
0x18003081d  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x180030822  mov     rcx, [rbp+870h+var_50]
0x180030829  xor     rcx, rsp; StackCookie
0x18003082c  call    __security_check_cookie
0x180030831  add     rsp, 938h
0x180030838  pop     r15
0x18003083a  pop     r14
0x18003083c  pop     r13
0x18003083e  pop     r12
0x180030840  pop     rdi
0x180030841  pop     rsi
0x180030842  pop     rbx
0x180030843  pop     rbp
0x180030844  retn
```
