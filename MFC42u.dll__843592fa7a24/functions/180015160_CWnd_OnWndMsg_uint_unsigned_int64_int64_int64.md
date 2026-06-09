# CWnd::OnWndMsg(uint,unsigned __int64,__int64,__int64 *)

- ea: `0x180015160`
- end: `0x180015e80`
- name: `?OnWndMsg@CWnd@@MEAAHI_K_JPEA_J@Z`
- size: `3360`
- prototype: `__int64 __usercall@<rax>(CWnd *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64 *)`
- caller_count: `4`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x180016810`
- `0x180017050`
- `0x180018670`
- `0x18001c040`

## callees

- `0x1800069d4`
- `0x18000ce50`
- `0x18000e1a0`
- `0x1800122f0`
- `0x180012eb0`
- `0x180013330`
- `0x180013840`
- `0x180013a90`
- `0x180015160`
- `0x180015e90`
- `0x1800166a0`
- `0x180017020`
- `0x18001a040`
- `0x180022880`
- `0x18002b290`
- `0x18002cdb0`
- `0x1800d1f92`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001544c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800156c1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001544c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800156c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800156ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800151fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800156ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001523f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001547e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001523f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800152cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001547e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180015430`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180015a7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180015430`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180015a7d`
- `USER32!GetLastActivePopup` at `0x180015512`
- `USER32!GetLastActivePopup` at `0x180015512`
- `USER32!GetForegroundWindow` at `0x18001552c`
- `USER32!GetForegroundWindow` at `0x18001552c`
- `USER32!SetForegroundWindow` at `0x180015557`
- `USER32!SetForegroundWindow` at `0x180015557`
- `USER32!GetParent` at `0x180015597`
- `USER32!GetParent` at `0x180015597`
- `GDI32!DeleteDC` at `0x180015d1b`
- `GDI32!DeleteDC` at `0x180015d1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWnd::OnWndMsg(CWnd *this, unsigned int a2, WPARAM a3, HWND a4, __int64 *a5)
{
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r13
  __int64 v12; // rdi
  void (__fastcall *v14)(CWnd *, struct CWnd *); // rbx
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned int v17; // r14d
  __int64 v18; // rcx
  __int64 v19; // r8
  _QWORD *v20; // rax
  signed int Version; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rax
  int v24; // ecx
  struct CWnd *TopLevelParent; // rax
  HWND LastActivePopup; // rax
  HWND *v27; // rdi
  HWND ForegroundWindow; // rax
  struct AFX_MODULE_THREAD_STATE *ModuleThreadState; // rdi
  __int64 v30; // rsi
  struct CObject *v31; // rax
  struct CObject *v32; // rdi
  HWND Parent; // rax
  __int64 v34; // r8
  _QWORD *i; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  int v38; // eax
  _DWORD *v39; // rax
  void ***v40; // r8
  __int64 v41; // rax
  struct CDC *v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  _QWORD *j; // rcx
  struct CWnd *v46; // rax
  struct CWnd *v47; // rdx
  unsigned int v48; // esi
  unsigned int v49; // r14d
  struct CWnd *v50; // rax
  struct CWnd *v51; // rax
  struct CWnd *v52; // rdi
  struct CWnd *v53; // rax
  struct CDC *v54; // rax
  struct CObject *v55; // rax
  __int64 v56; // rcx
  struct CWnd *v57; // rax
  struct CWnd *v58; // rax
  struct CMenu *v59; // rax
  struct CMenu *v60; // rax
  struct CMenu *v61; // rax
  struct CWnd *v62; // rax
  struct CWnd *v63; // rax
  struct CWnd *v64; // rax
  struct CWnd *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  HDC v68; // rax
  struct AFX_MODULE_THREAD_STATE *v69; // rax
  __int64 v70; // rsi
  CHandleMap *v71; // rax
  struct CWnd *v72; // rax
  __int64 v73; // [rsp+30h] [rbp-A1h] BYREF
  CHandleMap *v74; // [rsp+38h] [rbp-99h]
  void **v75; // [rsp+40h] [rbp-91h] BYREF
  __int64 v76; // [rsp+48h] [rbp-89h]
  __int64 v77; // [rsp+50h] [rbp-81h]
  int v78; // [rsp+58h] [rbp-79h]
  void **v79; // [rsp+60h] [rbp-71h] BYREF
  int v80; // [rsp+68h] [rbp-69h]
  __int64 v81; // [rsp+70h] [rbp-61h]
  __int64 v82; // [rsp+78h] [rbp-59h]
  __int64 v83; // [rsp+80h] [rbp-51h]
  int v84; // [rsp+88h] [rbp-49h]
  __int64 v85; // [rsp+90h] [rbp-41h]
  struct AFX_MODULE_STATE *ModuleState; // [rsp+98h] [rbp-39h]
  __int64 v87[6]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v88; // [rsp+D0h] [rbp-1h]

  v73 = 0;
  switch ( a2 )
  {
    case 0x111u:
      if ( (*(unsigned int (__fastcall **)(CWnd *, WPARAM, HWND))(*(_QWORD *)this + 256LL))(this, a3, a4) )
        goto LABEL_69;
      return 0;
    case 0x4Eu:
      if ( !*(_QWORD *)a4
        || !(*(unsigned int (__fastcall **)(CWnd *, WPARAM, HWND, __int64 *))(*(_QWORD *)this + 264LL))(
              this,
              a3,
              a4,
              &v73) )
      {
        return 0;
      }
      goto LABEL_46;
    case 6u:
      v72 = CWnd::FromHandle(a4);
      _AfxHandleActivate(this, a3, v72);
      break;
    default:
      if ( a2 == 32 && (_WORD)a4 == 0xFFFE )
      {
        v23 = (unsigned __int64)a4 >> 16;
        if ( (unsigned __int16)(WORD1(a4) - 513) <= 6u )
        {
          v24 = 73;
          LOWORD(v23) = WORD1(a4) - 513;
          if ( _bittest(&v24, v23) )
          {
            TopLevelParent = CWnd::GetTopLevelParent(this);
            if ( TopLevelParent )
            {
              LastActivePopup = GetLastActivePopup(*((HWND *)TopLevelParent + 8));
              v27 = (HWND *)CWnd::FromHandle(LastActivePopup);
              if ( v27 )
              {
                ForegroundWindow = GetForegroundWindow();
                if ( v27 != (HWND *)CWnd::FromHandle(ForegroundWindow) )
                {
                  if ( (unsigned int)CWnd::IsWindowEnabled((CWnd *)v27) )
                  {
                    SetForegroundWindow(v27[8]);
LABEL_69:
                    v73 = 1;
                    goto LABEL_46;
                  }
                }
              }
            }
          }
        }
      }
      break;
  }
  v9 = (*(__int64 (__fastcall **)(CWnd *))(*(_QWORD *)this + 96LL))(this);
  v10 = ((unsigned __int16)a2 ^ (unsigned __int16)v9) & 0x1FF;
  if ( !_afxCriticalInit )
  {
    _afxCriticalInit = 1;
    Version = GetVersion();
    if ( (unsigned __int8)Version >= 4u || Version >= 0 )
    {
      _afxCriticalWin32s = 0;
      InitializeCriticalSection(&_afxLockInitLock);
    }
    else
    {
      _afxCriticalWin32s = 1;
    }
  }
  if ( !_afxCriticalWin32s )
  {
    if ( !dword_180131D1C )
    {
      EnterCriticalSection(&_afxLockInitLock);
      if ( !dword_180131D1C )
      {
        InitializeCriticalSection(&stru_180131E88);
        ++dword_180131D1C;
      }
      LeaveCriticalSection(&_afxLockInitLock);
    }
    EnterCriticalSection(&stru_180131E88);
  }
  v11 = 3 * v10;
  if ( a2 != *((_DWORD *)&_afxMsgCache + 6 * v10) || v9 != qword_18012E870[v11] )
  {
    *((_DWORD *)&_afxMsgCache + 6 * v10) = a2;
    qword_18012E870[v11] = v9;
    while ( v9 )
    {
      v12 = *(_QWORD *)(v9 + 8);
      if ( a2 >= 0xC000 )
      {
        while ( 1 )
        {
          v39 = *(_DWORD **)(v12 + 16);
          if ( !v39 )
            break;
          if ( *(_DWORD *)v12 == 49152 && !*(_DWORD *)(v12 + 4) && !*(_DWORD *)(v12 + 8) && *v39 == a2 )
          {
            qword_18012E868[v11] = v12;
            AfxUnlockGlobals(7);
            goto LABEL_44;
          }
          v12 += 32;
        }
      }
      else
      {
        while ( *(_QWORD *)(v12 + 16) )
        {
          if ( *(_DWORD *)v12 == a2 && !*(_DWORD *)(v12 + 4) && !*(_DWORD *)(v12 + 8) )
          {
            qword_18012E868[v11] = v12;
            if ( !_afxCriticalWin32s )
              LeaveCriticalSection(&stru_180131E88);
            goto LABEL_27;
          }
          v12 += 32;
        }
      }
      v9 = (*(__int64 (**)(void))v9)();
    }
    qword_18012E868[v11] = 0;
    if ( !_afxCriticalWin32s )
      LeaveCriticalSection(&stru_180131E88);
    return 0;
  }
  v12 = qword_18012E868[3 * v10];
  if ( !_afxCriticalWin32s )
    LeaveCriticalSection(&stru_180131E88);
  if ( !v12 )
    return 0;
  if ( a2 >= 0xC000 )
  {
LABEL_44:
    v22 = (*(__int64 (__fastcall **)(CWnd *, WPARAM, HWND))(v12 + 24))(this, a3, a4);
LABEL_45:
    v73 = v22;
    goto LABEL_46;
  }
LABEL_27:
  v14 = *(void (__fastcall **)(CWnd *, struct CWnd *))(v12 + 24);
  if ( *(_DWORD *)(v12 + 8) == 26 )
  {
    if ( (unsigned __int8)GetVersion() < 4u )
    {
LABEL_105:
      v47 = (struct CWnd *)a4;
LABEL_106:
      v14(this, v47);
    }
    else
    {
LABEL_124:
      ((void (__fastcall *)(CWnd *, _QWORD, HWND))v14)(this, (unsigned int)a3, a4);
    }
    goto LABEL_46;
  }
  v15 = *(_QWORD *)(v12 + 16);
  switch ( v15 )
  {
    case 12LL:
      (*(void (__fastcall **)(CWnd *))(v12 + 24))(this);
      goto LABEL_46;
    case 10LL:
      goto LABEL_44;
    case 3LL:
      ModuleThreadState = AfxGetModuleThreadState();
      if ( !*((_QWORD *)ModuleThreadState + 5) )
      {
        v69 = AfxGetModuleThreadState();
        v70 = *((_QWORD *)v69 + 10);
        *((_QWORD *)v69 + 10) = AfxCriticalNewHandler;
        v71 = (CHandleMap *)operator new(0x88u);
        v74 = v71;
        if ( v71 )
          v71 = CHandleMap::CHandleMap(v71, (struct CRuntimeClass *)&CTempWnd::classCTempWnd, 0x40u, 1);
        *((_QWORD *)ModuleThreadState + 5) = v71;
        *((_QWORD *)AfxGetModuleThreadState() + 10) = v70;
      }
      v30 = *((_QWORD *)ModuleThreadState + 5);
      v31 = CHandleMap::FromHandle((CHandleMap *)v30, (void *)a3);
      v32 = v31;
      if ( v31 )
      {
        if ( !*((_QWORD *)v31 + 15) )
        {
          Parent = GetParent(*((HWND *)v31 + 8));
          v34 = *(_QWORD *)(v30 + 8);
          if ( v34 )
          {
            for ( i = *(_QWORD **)(v34 + 8LL * (((unsigned int)Parent >> 4) % *(_DWORD *)(v30 + 16))); i; i = (_QWORD *)*i )
            {
              if ( (HWND)i[1] == Parent )
              {
                v36 = i[2];
                if ( v36 )
                {
                  v37 = *(_QWORD *)(v36 + 112);
                  if ( v37 )
                  {
                    v55 = CHandleMap::LookupPermanent((CHandleMap *)(v37 + 72), *((void **)v32 + 8));
                    if ( v55 )
                    {
                      v56 = *((_QWORD *)v55 + 10);
                      if ( v56 && *(struct CObject **)(v56 + 120) == v55 )
                        *(_QWORD *)(v56 + 120) = 0;
                      *((_QWORD *)v32 + 15) = v55;
                      *((_QWORD *)v55 + 10) = v32;
                    }
                  }
                }
                break;
              }
            }
          }
        }
      }
      v73 = ((int (__fastcall *)(CWnd *, struct CObject *, _QWORD, _QWORD))v14)(
              this,
              v32,
              (unsigned int)(__int16)a4,
              WORD1(a4));
      goto LABEL_46;
  }
  if ( v15 != 46 )
  {
    switch ( v15 )
    {
      case 1LL:
        v42 = CDC::FromHandle((HDC)a3);
        goto LABEL_92;
      case 2LL:
        v73 = (*(int (__fastcall **)(CWnd *, _QWORD))(v12 + 24))(this, (unsigned int)a3);
        goto LABEL_46;
      case 4LL:
        v75 = &CDC::`vftable';
        v77 = 0;
        v78 = 0;
        v76 = *((_QWORD *)a4 + 1);
        ModuleState = AfxGetModuleState();
        v80 = 1;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        v84 = 1;
        v85 = 0;
        v79 = &CWnd::`vftable';
        v88 = 0;
        memset_0(v87, 0, 0x40u);
        v16 = *(_QWORD *)a4;
        v87[0] = *(_QWORD *)a4;
        v17 = *((_DWORD *)a4 + 4);
        v18 = *((_QWORD *)AfxGetModuleThreadState() + 5);
        if ( !v18 )
          goto LABEL_93;
        v19 = *(_QWORD *)(v18 + 8);
        if ( !v19 )
          goto LABEL_93;
        v20 = *(_QWORD **)(v19 + 8LL * (((unsigned int)v16 >> 4) % *(_DWORD *)(v18 + 16)));
        break;
      case 5LL:
        v75 = &CDC::`vftable';
        v77 = 0;
        v78 = 0;
        v76 = *((_QWORD *)a4 + 1);
        v73 = ((__int64 (__fastcall *)(CWnd *, void ***, _QWORD))v14)(this, &v75, *((unsigned int *)a4 + 4));
        goto LABEL_46;
      case 6LL:
        v58 = CWnd::FromHandle(a4);
        v73 = ((int (__fastcall *)(CWnd *, _QWORD, struct CWnd *, _QWORD))v14)(
                this,
                (unsigned __int16)a3,
                v58,
                WORD1(a3));
        goto LABEL_46;
      case 7LL:
        v73 = (*(int (__fastcall **)(CWnd *, _QWORD, _QWORD))(v12 + 24))(this, (unsigned __int16)a3, WORD1(a3));
        goto LABEL_46;
      case 8LL:
        v51 = CWnd::FromHandle((HWND)a3);
        v73 = ((int (__fastcall *)(CWnd *, struct CWnd *, _QWORD, _QWORD))v14)(
                this,
                v51,
                (unsigned int)(__int16)a4,
                WORD1(a4));
        goto LABEL_46;
      case 9LL:
      case 42LL:
        v42 = (struct CDC *)a4;
LABEL_92:
        v73 = ((int (__fastcall *)(CWnd *, struct CDC *))v14)(this, v42);
        goto LABEL_46;
      case 11LL:
        v59 = CMenu::FromHandle((HMENU)a4);
        v22 = ((__int64 (__fastcall *)(CWnd *, _QWORD, _QWORD, struct CMenu *))v14)(
                this,
                (unsigned __int16)a3,
                WORD1(a3),
                v59);
        goto LABEL_45;
      case 13LL:
        (*(void (__fastcall **)(CWnd *, _QWORD))(v12 + 24))(this, (unsigned int)a3);
        goto LABEL_46;
      case 14LL:
        (*(void (__fastcall **)(CWnd *, _QWORD, _QWORD))(v12 + 24))(this, (unsigned int)a3, (unsigned int)a4);
        goto LABEL_46;
      case 15LL:
        (*(void (__fastcall **)(CWnd *, _QWORD, _QWORD))(v12 + 24))(
          this,
          (unsigned int)(__int16)a4,
          (unsigned int)SWORD1(a4));
        goto LABEL_46;
      case 16LL:
      case 17LL:
        (*(void (__fastcall **)(CWnd *, _QWORD, _QWORD, _QWORD))(v12 + 24))(
          this,
          (unsigned int)a3,
          (unsigned __int16)a4,
          WORD1(a4));
        goto LABEL_46;
      case 18LL:
      case 51LL:
        (*(void (__fastcall **)(CWnd *, WPARAM, HWND))(v12 + 24))(this, a3, a4);
        goto LABEL_46;
      case 19LL:
        v52 = CWnd::FromHandle((HWND)a3);
        v53 = CWnd::FromHandle(a4);
        ((void (__fastcall *)(CWnd *, bool, struct CWnd *, struct CWnd *))v14)(
          this,
          *((_QWORD *)this + 8) == (_QWORD)a4,
          v53,
          v52);
        goto LABEL_46;
      case 20LL:
        v54 = CDC::FromHandle((HDC)a3);
        v14(this, v54);
        goto LABEL_46;
      case 21LL:
        v60 = CMenu::FromHandle((HMENU)a3);
        v14(this, v60);
        goto LABEL_46;
      case 22LL:
        v61 = CMenu::FromHandle((HMENU)a3);
        ((void (__fastcall *)(CWnd *, struct CMenu *, _QWORD, _QWORD))v14)(this, v61, (unsigned __int16)a4, WORD1(a4));
        goto LABEL_46;
      case 23LL:
        v47 = CWnd::FromHandle((HWND)a3);
        goto LABEL_106;
      case 24LL:
        v62 = CWnd::FromHandle((HWND)a3);
        ((void (__fastcall *)(CWnd *, struct CWnd *, _QWORD, _QWORD))v14)(this, v62, (unsigned __int16)a4, WORD1(a4));
        goto LABEL_46;
      case 25LL:
        v63 = CWnd::FromHandle((HWND)a3);
        ((void (__fastcall *)(CWnd *, struct CWnd *, unsigned __int64))v14)(
          this,
          v63,
          (unsigned int)(__int16)a4 | ((unsigned __int64)(unsigned int)SWORD1(a4) << 32));
        goto LABEL_46;
      case 26LL:
        v64 = CWnd::FromHandle((HWND)a3);
        ((void (__fastcall *)(CWnd *, struct CWnd *, HWND))v14)(this, v64, a4);
        goto LABEL_46;
      case 27LL:
        v46 = CWnd::FromHandle(a4);
        ((void (__fastcall *)(CWnd *, _QWORD, struct CWnd *))v14)(this, (unsigned int)a3, v46);
        goto LABEL_46;
      case 28LL:
        v65 = CWnd::FromHandle(a4);
        ((void (__fastcall *)(CWnd *, _QWORD, struct CWnd *, _QWORD))v14)(this, (unsigned __int16)a3, v65, WORD1(a3));
        goto LABEL_46;
      case 29LL:
      case 30LL:
        v48 = (__int16)a3;
        v49 = SWORD1(a3);
        if ( *(_QWORD *)(v12 + 16) == 29 )
        {
          v50 = CWnd::FromHandle(a4);
          ((void (__fastcall *)(CWnd *, _QWORD, _QWORD, struct CWnd *))v14)(this, v48, v49, v50);
        }
        else
        {
          (*(void (__fastcall **)(CWnd *, _QWORD, _QWORD))(v12 + 24))(this, v48, v49);
        }
        goto LABEL_46;
      case 31LL:
      case 36LL:
        goto LABEL_105;
      case 32LL:
        (*(void (__fastcall **)(CWnd *, _QWORD, HWND))(v12 + 24))(this, (unsigned int)a3, a4);
        v73 = 1;
        goto LABEL_46;
      case 33LL:
        v73 = (*(int (__fastcall **)(CWnd *, _QWORD, HWND))(v12 + 24))(this, (unsigned int)a3, a4);
        goto LABEL_46;
      case 34LL:
        LODWORD(v74) = (__int16)a4;
        HIDWORD(v74) = SWORD1(a4);
        v22 = ((unsigned int (__fastcall *)(CWnd *, CHandleMap *))v14)(this, v74);
        goto LABEL_45;
      case 35LL:
        v22 = (*(unsigned int (__fastcall **)(CWnd *))(v12 + 24))(this);
        goto LABEL_45;
      case 37LL:
      case 47LL:
      case 50LL:
        goto LABEL_124;
      case 43LL:
        (*(void (__fastcall **)(CWnd *, WPARAM, HWND))(v12 + 24))(this, a3, a4);
        v73 = 1;
        goto LABEL_46;
      case 44LL:
        v47 = CWnd::FromHandle(a4);
        goto LABEL_106;
      case 45LL:
        v57 = CWnd::FromHandle((HWND)a3);
        v73 = ((int (__fastcall *)(CWnd *, struct CWnd *, HWND))v14)(this, v57, a4);
        goto LABEL_46;
      case 48LL:
        (*(void (__fastcall **)(CWnd *, _QWORD, _QWORD, HWND))(v12 + 24))(this, (unsigned __int16)a3, WORD1(a3), a4);
        goto LABEL_46;
      case 49LL:
        LODWORD(v74) = (__int16)a4;
        HIDWORD(v74) = SWORD1(a4);
        ((void (__fastcall *)(CWnd *, _QWORD, CHandleMap *))v14)(this, (unsigned int)a3, v74);
        goto LABEL_46;
      case 52LL:
        (*(void (__fastcall **)(CWnd *, WPARAM))(v12 + 24))(this, a3);
        goto LABEL_46;
      default:
        goto LABEL_46;
    }
    while ( v20 )
    {
      if ( v20[1] == v16 )
      {
        v40 = (void ***)v20[2];
        if ( v40 )
          goto LABEL_88;
        break;
      }
      v20 = (_QWORD *)*v20;
    }
LABEL_93:
    v43 = *((_QWORD *)this + 14);
    if ( v43 )
    {
      v44 = *(_QWORD *)(v43 + 80);
      if ( v44 )
      {
        for ( j = *(_QWORD **)(v44 + 8LL * ((LODWORD(v87[0]) >> 4) % *(_DWORD *)(v43 + 88))); j; j = (_QWORD *)*j )
        {
          if ( j[1] == v87[0] )
          {
            v66 = j[2];
            v67 = *((_QWORD *)&v88 + 1);
            if ( v66 )
              v67 = v66;
            *((_QWORD *)&v88 + 1) = v67;
            break;
          }
        }
      }
    }
    v40 = &v79;
LABEL_88:
    v41 = ((__int64 (__fastcall *)(CWnd *, void ***, void ***, _QWORD))v14)(this, &v75, v40, v17);
    v76 = 0;
    v87[0] = 0;
    v73 = v41;
    CWnd::~CWnd((CWnd *)&v79);
    v75 = &CDC::`vftable';
    if ( v76 )
    {
      v68 = CDC::Detach((CDC *)&v75);
      DeleteDC(v68);
    }
    goto LABEL_46;
  }
  LODWORD(v74) = (unsigned __int16)a4;
  HIDWORD(v74) = WORD1(a4);
  v38 = ((__int64 (__fastcall *)(CWnd *, _QWORD, WPARAM, CHandleMap *))v14)(this, (unsigned __int16)a3, a3 >> 16, v74);
  v73 = v38;
  if ( !v38 )
    return 0;
LABEL_46:
  if ( a5 )
    *a5 = v73;
  return 1;
}

```

## disassembly

```asm
0x180015160  push    rbp
0x180015162  push    rbx
0x180015163  push    rsi
0x180015164  push    rdi
0x180015165  push    r12
0x180015167  push    r13
0x180015169  push    r14
0x18001516b  push    r15
0x18001516d  lea     rbp, [rsp-17h]
0x180015172  sub     rsp, 0E8h
0x180015179  mov     r12, r9
0x18001517c  mov     r14, r8
0x18001517f  mov     ebx, edx
0x180015181  mov     r15, rcx
0x180015184  xor     r13d, r13d
0x180015187  mov     [rsp+120h+var_F0], r13
0x18001518c  cmp     edx, 111h
0x180015192  jz      loc_180015605
0x180015198  cmp     edx, 4Eh ; 'N'
0x18001519b  jz      loc_180015630
0x1800151a1  cmp     edx, 6
0x1800151a4  jz      loc_180015D7C
0x1800151aa  cmp     edx, 20h ; ' '
0x1800151ad  jz      loc_1800154C7
0x1800151b3  mov     rax, [r15]
0x1800151b6  mov     rcx, r15
0x1800151b9  mov     rax, [rax+60h]
0x1800151bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151c2  mov     rsi, rax
0x1800151c5  movzx   edi, ax
0x1800151c8  xor     edi, ebx
0x1800151ca  and     edi, 1FFh
0x1800151d0  cmp     cs:?_afxCriticalInit@@3HA, r13d; int _afxCriticalInit
0x1800151d7  jz      loc_180015426
0x1800151dd  cmp     cs:?_afxCriticalWin32s@@3HA, r13d; int _afxCriticalWin32s
0x1800151e4  jnz     short loc_180015200
0x1800151e6  cmp     cs:dword_180131D1C, r13d
0x1800151ed  jz      loc_1800156A4
0x1800151f3  lea     rcx, stru_180131E88; lpCriticalSection
0x1800151fa  call    cs:__imp_EnterCriticalSection
0x180015200  lea     rcx, [rdi+rdi*2]
0x180015204  lea     r13, ds:0[rcx*8]
0x18001520c  lea     rcx, __ImageBase
0x180015213  cmp     ebx, rva ?_afxMsgCache@@3PAUAFX_MSG_CACHE@@A[rcx+r13]; AFX_MSG_CACHE near * _afxMsgCache ...
0x18001521b  jnz     short loc_180015264
0x18001521d  cmp     rsi, [r13+rcx+12E870h]
0x180015225  jnz     short loc_180015264
0x180015227  mov     rdi, rva qword_18012E868[rcx+r13]
0x18001522f  cmp     cs:?_afxCriticalWin32s@@3HA, 0; int _afxCriticalWin32s
0x180015236  jnz     short loc_180015245
0x180015238  lea     rcx, stru_180131E88; lpCriticalSection
0x18001523f  call    cs:__imp_LeaveCriticalSection
0x180015245  test    rdi, rdi
0x180015248  jnz     loc_1800152E1
0x18001524e  xor     eax, eax
0x180015250  add     rsp, 0E8h
0x180015257  pop     r15
0x180015259  pop     r14
0x18001525b  pop     r13
0x18001525d  pop     r12
0x18001525f  pop     rdi
0x180015260  pop     rsi
0x180015261  pop     rbx
0x180015262  pop     rbp
0x180015263  retn
0x180015264  mov     rva ?_afxMsgCache@@3PAUAFX_MSG_CACHE@@A[rcx+r13], ebx; AFX_MSG_CACHE near * _afxMsgCache ...
0x18001526c  mov     [r13+rcx+12E870h], rsi
0x180015274  test    rsi, rsi
0x180015277  jz      loc_180015457
0x18001527d  mov     rdi, [rsi+8]
0x180015281  cmp     ebx, 0C000h
0x180015287  jnb     loc_180015710
0x18001528d  nop     dword ptr [rax]
0x180015290  cmp     qword ptr [rdi+10h], 0
0x180015295  jz      short loc_1800152D4
0x180015297  cmp     [rdi], ebx
0x180015299  jz      short loc_1800152A1
0x18001529b  add     rdi, 20h ; ' '
0x18001529f  jmp     short loc_180015290
0x1800152a1  cmp     dword ptr [rdi+4], 0
0x1800152a5  jnz     short loc_18001529B
0x1800152a7  cmp     dword ptr [rdi+8], 0
0x1800152ab  ja      short loc_18001529B
0x1800152ad  lea     rsi, __ImageBase
0x1800152b4  mov     rva qword_18012E868[rsi+r13], rdi
0x1800152bc  cmp     cs:?_afxCriticalWin32s@@3HA, 0; int _afxCriticalWin32s
0x1800152c3  jnz     short loc_1800152F4
0x1800152c5  lea     rcx, stru_180131E88; lpCriticalSection
0x1800152cc  call    cs:__imp_LeaveCriticalSection
0x1800152d2  jmp     short loc_1800152F4
0x1800152d4  mov     rax, [rsi]
0x1800152d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152dc  mov     rsi, rax
0x1800152df  jmp     short loc_180015274
0x1800152e1  cmp     ebx, 0C000h
0x1800152e7  jnb     loc_1800156FC
0x1800152ed  lea     rsi, __ImageBase
0x1800152f4  mov     rbx, [rdi+18h]
0x1800152f8  cmp     dword ptr [rdi+8], 1Ah
0x1800152fc  jz      loc_180015A7D
0x180015302  mov     rax, [rdi+10h]
0x180015306  cmp     rax, 0Ch
0x18001530a  jz      loc_180015489
0x180015310  cmp     rax, 0Ah
0x180015314  jz      loc_180015496
0x18001531a  cmp     rax, 3
0x18001531e  jz      loc_180015562
0x180015324  cmp     rax, 2Eh ; '.'
0x180015328  jz      loc_180015660
0x18001532e  dec     rax; switch 52 cases
0x180015331  cmp     rax, 33h
0x180015335  ja      def_180015345; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x18001533b  mov     eax, ds:(jpt_180015345 - 180000000h)[rsi+rax*4]
0x180015342  add     rax, rsi
0x180015345  jmp     rax; switch jump
0x180015347  lea     rsi, ??_7CDC@@6B@; jumptable 0000000180015345 case 4
0x18001534e  mov     [rsp+120h+var_E0], rsi
0x180015353  mov     [rsp+120h+var_D0], 0
0x18001535c  mov     [rbp+4Fh+var_C8], 0
0x180015363  mov     rax, [r12+8]
0x180015368  mov     [rsp+120h+var_D8], rax
0x18001536d  lea     rax, ??_7CCmdTarget@@6B@; const CCmdTarget::`vftable'
0x180015374  mov     [rbp+4Fh+var_C0], rax
0x180015378  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18001537d  mov     [rbp+4Fh+var_88], rax
0x180015381  mov     [rbp+4Fh+var_B8], 1
0x180015388  mov     [rbp+4Fh+var_B0], 0
0x180015390  mov     [rbp+4Fh+var_A8], 0
0x180015398  mov     [rbp+4Fh+var_A0], 0
0x1800153a0  mov     [rbp+4Fh+var_98], 1
0x1800153a7  mov     [rbp+4Fh+var_90], 0
0x1800153af  lea     rax, ??_7CWnd@@6B@; const CWnd::`vftable'
0x1800153b6  mov     [rbp+4Fh+var_C0], rax
0x1800153ba  xorps   xmm0, xmm0
0x1800153bd  movdqa  [rbp+4Fh+var_50], xmm0
0x1800153c2  xor     edx, edx; Val
0x1800153c4  mov     r8d, 40h ; '@'; Size
0x1800153ca  lea     rcx, [rbp+4Fh+var_80]; void *
0x1800153ce  call    memset_0
0x1800153d3  nop
0x1800153d4  mov     rdi, [r12]
0x1800153d8  mov     [rbp+4Fh+var_80], rdi
0x1800153dc  mov     r14d, [r12+10h]
0x1800153e1  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1800153e6  mov     rcx, [rax+28h]
0x1800153ea  test    rcx, rcx
0x1800153ed  jz      loc_1800157C1
0x1800153f3  mov     r8, [rcx+8]
0x1800153f7  test    r8, r8
0x1800153fa  jz      loc_1800157C1
0x180015400  mov     eax, edi
0x180015402  shr     eax, 4
0x180015405  xor     edx, edx
0x180015407  div     dword ptr [rcx+10h]
0x18001540a  mov     rax, [r8+rdx*8]
0x18001540e  test    rax, rax
0x180015411  jz      loc_1800157C1
0x180015417  cmp     [rax+8], rdi
0x18001541b  jz      loc_180015739
0x180015421  mov     rax, [rax]
0x180015424  jmp     short loc_18001540E
0x180015426  mov     cs:?_afxCriticalInit@@3HA, 1; int _afxCriticalInit
0x180015430  call    cs:__imp_GetVersion
0x180015436  cmp     al, 4
0x180015438  jb      loc_180015D97
0x18001543e  mov     cs:?_afxCriticalWin32s@@3HA, r13d; int _afxCriticalWin32s
0x180015445  lea     rcx, ?_afxLockInitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001544c  call    cs:__imp_InitializeCriticalSection
0x180015452  jmp     loc_1800151DD
0x180015457  lea     rsi, __ImageBase
0x18001545e  mov     rva qword_18012E868[rsi+r13], 0
0x18001546a  cmp     cs:?_afxCriticalWin32s@@3HA, 0; int _afxCriticalWin32s
0x180015471  jnz     loc_18001524E
0x180015477  lea     rcx, stru_180131E88; lpCriticalSection
0x18001547e  call    cs:__imp_LeaveCriticalSection
0x180015484  jmp     loc_18001524E
0x180015489  mov     rcx, r15
0x18001548c  mov     rax, rbx
0x18001548f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015494  jmp     short def_180015345; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x180015496  mov     rax, rbx
0x180015499  mov     r8, r12
0x18001549c  mov     rdx, r14
0x18001549f  mov     rcx, r15
0x1800154a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a7  mov     [rsp+120h+var_F0], rax
0x1800154ac  mov     rdx, [rbp+4Fh+arg_20]; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x1800154b0  test    rdx, rdx
0x1800154b3  jz      short loc_1800154BD
0x1800154b5  mov     rcx, [rsp+120h+var_F0]
0x1800154ba  mov     [rdx], rcx
0x1800154bd  mov     eax, 1
0x1800154c2  jmp     loc_180015250
0x1800154c7  mov     ecx, 0FFFEh
0x1800154cc  cmp     r12w, cx
0x1800154d0  jnz     loc_1800151B3
0x1800154d6  mov     rax, r12
0x1800154d9  shr     rax, 10h
0x1800154dd  mov     ecx, 201h
0x1800154e2  sub     ax, cx
0x1800154e5  cmp     ax, 6
0x1800154e9  ja      loc_1800151B3
0x1800154ef  mov     ecx, 49h ; 'I'
0x1800154f4  bt      ecx, eax
0x1800154f7  jnb     loc_1800151B3
0x1800154fd  mov     rcx, r15; this
0x180015500  call    ?GetTopLevelParent@CWnd@@QEBAPEAV1@XZ; CWnd::GetTopLevelParent(void)
0x180015505  test    rax, rax
0x180015508  jz      loc_1800151B3
0x18001550e  mov     rcx, [rax+40h]; hWnd
0x180015512  call    cs:__imp_GetLastActivePopup
0x180015518  mov     rcx, rax; HWND
0x18001551b  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180015520  mov     rdi, rax
0x180015523  test    rax, rax
0x180015526  jz      loc_1800151B3
0x18001552c  call    cs:__imp_GetForegroundWindow
0x180015532  mov     rcx, rax; HWND
0x180015535  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x18001553a  cmp     rdi, rax
0x18001553d  jz      loc_1800151B3
0x180015543  mov     rcx, rdi; this
0x180015546  call    ?IsWindowEnabled@CWnd@@QEBAHXZ; CWnd::IsWindowEnabled(void)
0x18001554b  test    eax, eax
0x18001554d  jz      loc_1800151B3
0x180015553  mov     rcx, [rdi+40h]; hWnd
0x180015557  call    cs:__imp_SetForegroundWindow
0x18001555d  jmp     loc_180015622
0x180015562  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180015567  mov     rdi, rax
0x18001556a  cmp     qword ptr [rax+28h], 0
0x18001556f  jz      loc_180015D26
0x180015575  mov     rsi, [rdi+28h]
0x180015579  mov     rdx, r14; void *
0x18001557c  mov     rcx, rsi; this
0x18001557f  call    ?FromHandle@CHandleMap@@QEAAPEAVCObject@@PEAX@Z; CHandleMap::FromHandle(void *)
0x180015584  mov     rdi, rax
0x180015587  test    rax, rax
0x18001558a  jz      short loc_1800155DB
0x18001558c  cmp     qword ptr [rax+78h], 0
0x180015591  jnz     short loc_1800155DB
0x180015593  mov     rcx, [rax+40h]; hWnd
0x180015597  call    cs:__imp_GetParent
0x18001559d  mov     r9, rax
0x1800155a0  mov     r8, [rsi+8]
0x1800155a4  test    r8, r8
0x1800155a7  jz      short loc_1800155DB
0x1800155a9  shr     eax, 4
0x1800155ac  xor     edx, edx
0x1800155ae  div     dword ptr [rsi+10h]
0x1800155b1  mov     rdx, [r8+rdx*8]
0x1800155b5  test    rdx, rdx
0x1800155b8  jz      short loc_1800155DB
0x1800155ba  cmp     [rdx+8], r9
0x1800155be  jz      short loc_1800155C5
0x1800155c0  mov     rdx, [rdx]
0x1800155c3  jmp     short loc_1800155B5
0x1800155c5  mov     rax, [rdx+10h]
0x1800155c9  test    rax, rax
0x1800155cc  jz      short loc_1800155DB
0x1800155ce  mov     rcx, [rax+70h]
0x1800155d2  test    rcx, rcx
0x1800155d5  jnz     loc_1800159D3
0x1800155db  mov     rax, r12
0x1800155de  shr     rax, 10h
0x1800155e2  movzx   r9d, ax
0x1800155e6  movsx   r8d, r12w
0x1800155ea  mov     rdx, rdi
0x1800155ed  mov     rcx, r15
0x1800155f0  mov     rax, rbx
0x1800155f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155f8  movsxd  rcx, eax
0x1800155fb  mov     [rsp+120h+var_F0], rcx
0x180015600  jmp     def_180015345; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x180015605  mov     rax, [rcx]
0x180015608  mov     r8, r12
0x18001560b  mov     rdx, r14
0x18001560e  mov     rax, [rax+100h]
0x180015615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001561a  test    eax, eax
0x18001561c  jz      loc_18001524E
0x180015622  mov     [rsp+120h+var_F0], 1
0x18001562b  jmp     def_180015345; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x180015630  cmp     [r9], r13
0x180015633  jz      loc_18001524E
0x180015639  mov     rax, [rcx]
0x18001563c  lea     r9, [rsp+120h+var_F0]
0x180015641  mov     r8, r12
0x180015644  mov     rdx, r14
0x180015647  mov     rax, [rax+108h]
0x18001564e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015653  test    eax, eax
0x180015655  jz      loc_18001524E
0x18001565b  jmp     def_180015345; jumptable 0000000180015345 default case, cases 3,10,12,38-41,46
0x180015660  movzx   eax, r12w
0x180015664  mov     dword ptr [rsp+120h+var_E8], eax
0x180015668  shr     r12, 10h
0x18001566c  movzx   eax, r12w
0x180015670  mov     dword ptr [rsp+120h+var_E8+4], eax
0x180015674  mov     r8, r14
  ... truncated ...
```
