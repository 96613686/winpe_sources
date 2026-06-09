# CSpellContextHandler::ShowModernContextMenu(tagPOINT const *,HWND__ *,int,bool,IEnumString *,bool)

- ea: `0x180275d5c`
- end: `0x18027640b`
- name: `?ShowModernContextMenu@CSpellContextHandler@@AEAAJPEBUtagPOINT@@PEAUHWND__@@H_NPEAUIEnumString@@2@Z`
- size: `1711`
- prototype: `__int64 __usercall@<rax>(CSpellContextHandler *__hidden this@<rcx>, const struct tagPOINT *@<rdx>, HWND@<r8>, int@<r9d>, bool, struct IEnumString *, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180275934`

## callees

- `0x180048d5c`
- `0x1800e1264`
- `0x18012f48c`
- `0x18013bad0`
- `0x18013beb8`
- `0x180273470`
- `0x18027355c`
- `0x1802735ac`
- `0x1802735fc`
- `0x180273788`
- `0x1802738bc`
- `0x18027398c`
- `0x180274474`
- `0x180274678`
- `0x18027494c`
- `0x180274d78`
- `0x180274f80`
- `0x180275d5c`
- `0x180276900`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1802763c1`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1802763c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18027610c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18027610c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802761fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802761fb`

## pseudocode

```c
__int64 __fastcall CSpellContextHandler::ShowModernContextMenu(
        CSpellContextHandler *this,
        const struct tagPOINT *a2,
        HWND a3,
        int a4,
        bool a5,
        struct IEnumString *a6,
        bool a7)
{
  __int64 *v7; // r15
  _QWORD *v11; // rax
  HRESULT ActivationFactory; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int inserted; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, __int64 *); // rbx
  __int64 v22; // rcx
  unsigned int v23; // r14d
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, double *); // rbx
  double v26; // rdi
  __int64 (__fastcall *v27)(_QWORD, __int64 *); // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  HRESULT v30; // eax
  HRESULT v31; // eax
  HSTRING v32; // rbx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rbx
  __int64 v35; // rax
  float v36; // xmm0_4
  float v37; // xmm0_4
  __int64 v38; // rax
  CSpellingCommandHandler *v39; // rax
  CSpellingCommandHandler *v40; // r15
  HRESULT (__stdcall *Clone)(IEnumString *, IEnumString **); // rbx
  __int64 v43; // [rsp+30h] [rbp-81h] BYREF
  __int64 v44; // [rsp+38h] [rbp-79h] BYREF
  HSTRING string; // [rsp+40h] [rbp-71h] BYREF
  double v46; // [rsp+48h] [rbp-69h] BYREF
  _QWORD v47[2]; // [rsp+50h] [rbp-61h] BYREF
  unsigned __int16 *v48[2]; // [rsp+60h] [rbp-51h] BYREF
  HWND hWnd; // [rsp+70h] [rbp-41h] BYREF
  __int64 v50; // [rsp+78h] [rbp-39h] BYREF
  __int64 v51; // [rsp+80h] [rbp-31h] BYREF
  __int64 v52; // [rsp+88h] [rbp-29h] BYREF
  HSTRING v53[2]; // [rsp+90h] [rbp-21h] BYREF

  v7 = (__int64 *)((char *)this + 144);
  v48[0] = (unsigned __int16 *)a2;
  if ( *((_QWORD *)this + 18) )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  v50 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v53, L"Windows.UI.Popups.PopupMenu");
  ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(
                        *v11,
                        &v50);
  if ( ActivationFactory < 0 )
    goto LABEL_74;
  v52 = 0;
  if ( !*((_BYTE *)this + 158) )
  {
    ActivationFactory = Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>::As<IInitializeWithWindow>(&v50, &v52);
    if ( ActivationFactory < 0 )
      goto LABEL_73;
  }
  v13 = v50;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v7);
  ActivationFactory = v14(v13, v7);
  if ( ActivationFactory < 0 )
    goto LABEL_73;
  if ( a4 == -1 )
    inserted = a5
             ? CSpellContextHandler::InsertRepeatedWordCommands(this, 0, a7)
             : CSpellContextHandler::InsertAlternates(this, 0, a6, a7);
  else
    inserted = CSpellContextHandler::InsertACCommands(this, 0, *((const unsigned __int16 **)this + 2), a7);
  ActivationFactory = inserted;
  if ( inserted < 0 )
    goto LABEL_73;
  v16 = *((_QWORD *)this + 3);
  v17 = *((_QWORD *)this + 1);
  v18 = *(_QWORD *)this;
  *(_OWORD *)v53 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, HSTRING *))(**(_QWORD **)(v16 + 72) + 216LL))(
                        *(_QWORD *)(v16 + 72),
                        v18,
                        v17,
                        v53);
  if ( ActivationFactory < 0 )
    goto LABEL_73;
  v19 = *((_QWORD *)this + 3);
  v51 = 0;
  v20 = *(_QWORD *)(v19 + 72);
  v21 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 200LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  if ( v21(v20, &v51) < 0 )
  {
    if ( *((_BYTE *)this + 158) )
    {
      string = 0;
      v46 = 0.0;
      ActivationFactory = Microsoft::WRL::Wrappers::HString::Set(
                            &string,
                            L"Windows.Graphics.Display.DisplayInformation",
                            0x2Bu);
      if ( ActivationFactory >= 0 )
      {
        v44 = 0;
        v32 = string;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
        ActivationFactory = RoGetActivationFactory(v32, &GUID_c6a02a6c_d452_44dc_ba07_96f3c6adf9d1, &v44);
        if ( ActivationFactory >= 0 )
        {
          v33 = v44;
          v43 = 0;
          v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          ActivationFactory = v34(v33, &v43);
          if ( ActivationFactory >= 0 )
          {
            v47[0] = 0;
            ActivationFactory = Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation>::As<Windows::Graphics::Display::IDisplayInformation2>(
                                  &v43,
                                  v47);
            if ( ActivationFactory >= 0 )
              ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, double *))(*(_QWORD *)v47[0] + 48LL))(v47[0], &v46);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
      }
      v48[1] = (unsigned __int16 *)0x4000000040000000LL;
      v35 = HIDWORD(*(_QWORD *)v48[0]);
      v36 = (double)(int)*(_QWORD *)v48[0] / v46;
      v37 = v36 - 1.0;
      *(float *)v48 = v37;
      *((float *)v48 + 1) = (float)((double)(int)v35 / v46) - 1.0;
      WindowsDeleteString(string);
    }
    else
    {
      ActivationFactory = 0;
      v48[0] = (unsigned __int16 *)v53[0];
      *(float *)&v48[1] = *(float *)&v53[1] - *(float *)v53;
      *((float *)&v48[1] + 1) = *((float *)&v53[1] + 1) - *((float *)v53 + 1);
    }
    v38 = *((_QWORD *)this + 3);
    hWnd = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, HWND, HWND *))(**(_QWORD **)(v38 + 72) + 296LL))(
           *(_QWORD *)(v38 + 72),
           a3,
           &hWnd) )
    {
      a3 = hWnd;
    }
    if ( !*((_BYTE *)this + 158) )
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v52 + 24LL))(v52, a3);
    if ( ActivationFactory >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 336LL))(
        *(_QWORD *)(*((_QWORD *)this + 3) + 72LL),
        0);
      v43 = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, __int64 *))(*(_QWORD *)v50 + 64LL))(
                            v50,
                            v48,
                            &v43);
      if ( ActivationFactory >= 0 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 72LL) + 304LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 72LL)) )
        {
          ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(v43);
          if ( ActivationFactory >= 0 && !*((_BYTE *)this + 157) )
            CSpellContextHandler::TelemetryLogDismissAlternates(this, a6);
        }
        else
        {
          v39 = (CSpellingCommandHandler *)operator new(0x20u);
          v40 = CSpellingCommandHandler::CSpellingCommandHandler(v39, this, 0);
          if ( a6 )
          {
            Clone = a6->lpVtbl->Clone;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
            ((void (__fastcall *)(struct IEnumString *, char *))Clone)(a6, (char *)this + 56);
          }
          else
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
          }
          if ( v40 )
          {
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v40 + 8LL))(v40);
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 48LL))(v43, (__int64)v40 + 8);
            *((_BYTE *)this + 155) = 1;
            (*(void (__fastcall **)(CSpellingCommandHandler *))(*(_QWORD *)v40 + 16LL))(v40);
          }
        }
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
    }
    if ( hWnd )
      DestroyWindow(hWnd);
    goto LABEL_72;
  }
  v44 = 0;
  ActivationFactory = Microsoft::WRL::ComPtr<IScrollableContextMenu>::As<IScrollableContextMenu2>(&v51, &v44);
  if ( ActivationFactory < 0 )
    goto LABEL_41;
  v22 = *v7;
  LODWORD(hWnd) = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v22 + 56LL))(v22, &hWnd);
  if ( ActivationFactory < 0 )
    goto LABEL_41;
  v23 = 0;
  while ( v23 < (unsigned int)hWnd )
  {
    v24 = *v7;
    v46 = 0.0;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    ActivationFactory = v25(v24, v23, &v46);
    if ( ActivationFactory >= 0 )
    {
      v47[0] = 0;
      ActivationFactory = (*(__int64 (__fastcall **)(double, _QWORD *))(**(_QWORD **)&v46 + 48LL))(
                            COERCE_DOUBLE(*(_QWORD *)&v46),
                            v47);
      if ( ActivationFactory >= 0 )
      {
        v48[0] = 0;
        ActivationFactory = Windows::Internal::String::GetLpcwstr(
                              (Windows::Internal::String *)v47,
                              (const unsigned __int16 **)v48);
        if ( ActivationFactory >= 0 )
        {
          v26 = v46;
          v43 = 0;
          v27 = *(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&v46 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          ActivationFactory = v27(*(_QWORD *)&v26, &v43);
          if ( ActivationFactory >= 0 )
          {
            v29 = 0xFFFFFFFFLL;
            LODWORD(string) = -1;
            if ( v43 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64))(*(_QWORD *)v43 + 96LL))(
                                    v43,
                                    &string,
                                    0xFFFFFFFFLL);
              if ( ActivationFactory >= 0 )
              {
                v29 = (unsigned int)string;
                goto LABEL_26;
              }
            }
            else
            {
LABEL_26:
              if ( (_DWORD)v29 != -1 || *v48[0] )
                v30 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v44 + 24LL))(v44, v48[0]);
              else
                v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int16 *))(*(_QWORD *)v44 + 40LL))(
                        v44,
                        v28,
                        v29,
                        v48[0]);
              ActivationFactory = v30;
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
        }
      }
      Windows::Internal::String::~String((Windows::Internal::String *)v47);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    ++v23;
    if ( ActivationFactory < 0 )
      goto LABEL_41;
  }
  LODWORD(string) = -1;
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING *))(*(_QWORD *)v44 + 32LL))(
          v44,
          (unsigned int)(int)*(float *)v53,
          (unsigned int)(int)*((float *)&v53[1] + 1),
          &string);
  ActivationFactory = v31;
  if ( *((_BYTE *)this + 159) )
  {
    if ( !v31 )
      ActivationFactory = CSpellContextHandler::Invoke(this, (UINT)string, 0);
    if ( ActivationFactory >= 0 && !*((_BYTE *)this + 157) )
      CSpellContextHandler::TelemetryLogDismissAlternates(this, a6);
  }
LABEL_41:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
LABEL_72:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
LABEL_73:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
LABEL_74:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180275d5c  mov     [rsp-8+arg_18], rbx
0x180275d61  push    rbp
0x180275d62  push    rsi
0x180275d63  push    rdi
0x180275d64  push    r12
0x180275d66  push    r13
0x180275d68  push    r14
0x180275d6a  push    r15
0x180275d6c  lea     rbp, [rsp-0Fh]
0x180275d71  sub     rsp, 0C0h
0x180275d78  mov     rax, cs:__security_cookie
0x180275d7f  xor     rax, rsp
0x180275d82  mov     [rbp+3Fh+var_40], rax
0x180275d86  mov     r12, [rbp+3Fh+arg_28]
0x180275d8a  lea     r15, [rcx+90h]
0x180275d91  xor     ebx, ebx
0x180275d93  mov     [rbp+3Fh+var_90], rdx
0x180275d97  mov     r14d, r9d
0x180275d9a  mov     r13, r8
0x180275d9d  mov     rsi, rcx
0x180275da0  cmp     [r15], rbx
0x180275da3  jz      short loc_180275DAD
0x180275da5  mov     rcx, r15
0x180275da8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180275dad  lea     rdx, ?RuntimeClass_Windows_UI_Popups_PopupMenu@@3QBGB; "Windows.UI.Popups.PopupMenu"
0x180275db4  mov     [rbp+3Fh+var_78], rbx
0x180275db8  lea     rcx, [rbp+3Fh+var_60]; string
0x180275dbc  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x180275dc1  lea     rdx, [rbp+3Fh+var_78]
0x180275dc5  mov     rcx, [rax]
0x180275dc8  call    ??$ActivateInstance@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>>)
0x180275dcd  mov     edi, eax
0x180275dcf  test    eax, eax
0x180275dd1  js      loc_1802763D9
0x180275dd7  mov     [rbp+3Fh+var_68], rbx
0x180275ddb  cmp     [rsi+9Eh], bl
0x180275de1  jnz     short loc_180275DFA
0x180275de3  lea     rdx, [rbp+3Fh+var_68]
0x180275de7  lea     rcx, [rbp+3Fh+var_78]
0x180275deb  call    ??$As@UIInitializeWithWindow@@@?$ComPtr@UIPopupMenu@Popups@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInitializeWithWindow@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Popups::IPopupMenu>::As<IInitializeWithWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInitializeWithWindow>>)
0x180275df0  mov     edi, eax
0x180275df2  test    eax, eax
0x180275df4  js      loc_1802763D0
0x180275dfa  mov     rdi, [rbp+3Fh+var_78]
0x180275dfe  mov     rcx, r15
0x180275e01  mov     rax, [rdi]
0x180275e04  mov     rbx, [rax+30h]
0x180275e08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180275e0d  mov     rdx, r15
0x180275e10  mov     rcx, rdi
0x180275e13  mov     rax, rbx
0x180275e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275e1b  mov     edi, eax
0x180275e1d  test    eax, eax
0x180275e1f  js      loc_1802763D0
0x180275e25  xor     edx, edx; HMENU
0x180275e27  mov     rcx, rsi; this
0x180275e2a  cmp     r14d, 0FFFFFFFFh
0x180275e2e  jz      short loc_180275E3F
0x180275e30  mov     r9b, [rbp+3Fh+arg_30]; bool
0x180275e34  mov     r8, [rsi+10h]; unsigned __int16 *
0x180275e38  call    ?InsertACCommands@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEBG_N@Z; CSpellContextHandler::InsertACCommands(HMENU__ *,ushort const *,bool)
0x180275e3d  jmp     short loc_180275E5C
0x180275e3f  cmp     [rbp+3Fh+arg_20], 0
0x180275e43  jz      short loc_180275E50
0x180275e45  mov     r8b, [rbp+3Fh+arg_30]; bool
0x180275e49  call    ?InsertRepeatedWordCommands@CSpellContextHandler@@AEAAJPEAUHMENU__@@_N@Z; CSpellContextHandler::InsertRepeatedWordCommands(HMENU__ *,bool)
0x180275e4e  jmp     short loc_180275E5C
0x180275e50  mov     r9b, [rbp+3Fh+arg_30]; bool
0x180275e54  mov     r8, r12; struct IEnumString *
0x180275e57  call    ?InsertAlternates@CSpellContextHandler@@AEAAJPEAUHMENU__@@PEAUIEnumString@@_N@Z; CSpellContextHandler::InsertAlternates(HMENU__ *,IEnumString *,bool)
0x180275e5c  mov     edi, eax
0x180275e5e  test    eax, eax
0x180275e60  js      loc_1802763D0
0x180275e66  mov     rax, [rsi+18h]
0x180275e6a  lea     r9, [rbp+3Fh+var_60]
0x180275e6e  mov     r8, [rsi+8]
0x180275e72  xorps   xmm0, xmm0
0x180275e75  mov     rdx, [rsi]
0x180275e78  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x180275e7c  mov     rcx, [rax+48h]
0x180275e80  mov     rax, [rcx]
0x180275e83  mov     rax, [rax+0D8h]
0x180275e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275e8f  mov     edi, eax
0x180275e91  test    eax, eax
0x180275e93  js      loc_1802763D0
0x180275e99  mov     rax, [rsi+18h]
0x180275e9d  lea     rcx, [rbp+3Fh+var_70]
0x180275ea1  mov     [rbp+3Fh+var_70], 0
0x180275ea9  mov     rdi, [rax+48h]
0x180275ead  mov     rax, [rdi]
0x180275eb0  mov     rbx, [rax+0C8h]
0x180275eb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180275ebc  lea     rdx, [rbp+3Fh+var_70]
0x180275ec0  mov     rcx, rdi
0x180275ec3  mov     rax, rbx
0x180275ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275ecb  xor     ebx, ebx
0x180275ecd  test    eax, eax
0x180275ecf  js      loc_1802760B5
0x180275ed5  lea     rdx, [rbp+3Fh+var_B8]
0x180275ed9  mov     [rbp+3Fh+var_B8], rbx
0x180275edd  lea     rcx, [rbp+3Fh+var_70]
0x180275ee1  call    ??$As@UIScrollableContextMenu2@@@?$ComPtr@UIScrollableContextMenu@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIScrollableContextMenu2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IScrollableContextMenu>::As<IScrollableContextMenu2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IScrollableContextMenu2>>)
0x180275ee6  mov     edi, eax
0x180275ee8  test    eax, eax
0x180275eea  js      loc_1802760A7
0x180275ef0  mov     rcx, [r15]
0x180275ef3  lea     rdx, [rbp+3Fh+hWnd]
0x180275ef7  mov     dword ptr [rbp+3Fh+hWnd], ebx
0x180275efa  mov     rax, [rcx]
0x180275efd  mov     rax, [rax+38h]
0x180275f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275f06  mov     edi, eax
0x180275f08  test    eax, eax
0x180275f0a  js      loc_1802760A7
0x180275f10  mov     r14d, ebx
0x180275f13  or      r13d, 0FFFFFFFFh
0x180275f17  cmp     r14d, dword ptr [rbp+3Fh+hWnd]
0x180275f1b  jnb     loc_18027604F
0x180275f21  mov     rdi, [r15]
0x180275f24  lea     rcx, [rbp+3Fh+var_A8]
0x180275f28  mov     [rbp+3Fh+var_A8], rbx
0x180275f2c  mov     rax, [rdi]
0x180275f2f  mov     rbx, [rax+30h]
0x180275f33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180275f38  lea     r8, [rbp+3Fh+var_A8]
0x180275f3c  mov     edx, r14d
0x180275f3f  mov     rcx, rdi
0x180275f42  mov     rax, rbx
0x180275f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275f4a  xor     ebx, ebx
0x180275f4c  mov     edi, eax
0x180275f4e  test    eax, eax
0x180275f50  js      loc_180276039
0x180275f56  mov     rcx, [rbp+3Fh+var_A8]
0x180275f5a  lea     rdx, [rbp+3Fh+var_A0]
0x180275f5e  mov     [rbp+3Fh+var_A0], rbx
0x180275f62  mov     rax, [rcx]
0x180275f65  mov     rax, [rax+30h]
0x180275f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275f6e  mov     edi, eax
0x180275f70  test    eax, eax
0x180275f72  js      loc_180276030
0x180275f78  lea     rdx, [rbp+3Fh+var_90]; unsigned __int16 **
0x180275f7c  mov     [rbp+3Fh+var_90], rbx
0x180275f80  lea     rcx, [rbp+3Fh+var_A0]; this
0x180275f84  call    ?GetLpcwstr@String@Internal@Windows@@QEBAJPEAPEBG@Z; Windows::Internal::String::GetLpcwstr(ushort const * *)
0x180275f89  mov     edi, eax
0x180275f8b  test    eax, eax
0x180275f8d  js      loc_180276030
0x180275f93  mov     rdi, [rbp+3Fh+var_A8]
0x180275f97  lea     rcx, [rsp+0F0h+var_C0]
0x180275f9c  mov     [rsp+0F0h+var_C0], rbx
0x180275fa1  mov     rax, [rdi]
0x180275fa4  mov     rbx, [rax+50h]
0x180275fa8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180275fad  lea     rdx, [rsp+0F0h+var_C0]
0x180275fb2  mov     rcx, rdi
0x180275fb5  mov     rax, rbx
0x180275fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275fbd  xor     ebx, ebx
0x180275fbf  mov     edi, eax
0x180275fc1  test    eax, eax
0x180275fc3  js      short loc_180276026
0x180275fc5  mov     rcx, [rsp+0F0h+var_C0]
0x180275fca  mov     r8d, r13d
0x180275fcd  mov     dword ptr [rbp+3Fh+string], r13d
0x180275fd1  test    rcx, rcx
0x180275fd4  jz      short loc_180275FF0
0x180275fd6  mov     rax, [rcx]
0x180275fd9  lea     rdx, [rbp+3Fh+string]
0x180275fdd  mov     rax, [rax+60h]
0x180275fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275fe6  mov     edi, eax
0x180275fe8  test    eax, eax
0x180275fea  js      short loc_180276026
0x180275fec  mov     r8d, dword ptr [rbp+3Fh+string]
0x180275ff0  mov     r9, [rbp+3Fh+var_90]
0x180275ff4  cmp     r8d, r13d
0x180275ff7  jnz     short loc_180276011
0x180275ff9  cmp     [r9], bx
0x180275ffd  jnz     short loc_180276011
0x180275fff  mov     rcx, [rbp+3Fh+var_B8]
0x180276003  mov     rax, [rcx]
0x180276006  mov     rax, [rax+28h]
0x18027600a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027600f  jmp     short loc_180276024
0x180276011  mov     rcx, [rbp+3Fh+var_B8]
0x180276015  mov     rdx, r9
0x180276018  mov     rax, [rcx]
0x18027601b  mov     rax, [rax+18h]
0x18027601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276024  mov     edi, eax
0x180276026  lea     rcx, [rsp+0F0h+var_C0]
0x18027602b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276030  lea     rcx, [rbp+3Fh+var_A0]; this
0x180276034  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180276039  lea     rcx, [rbp+3Fh+var_A8]
0x18027603d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276042  inc     r14d
0x180276045  test    edi, edi
0x180276047  jns     loc_180275F17
0x18027604d  jmp     short loc_1802760A7
0x18027604f  mov     rcx, [rbp+3Fh+var_B8]
0x180276053  lea     r9, [rbp+3Fh+string]
0x180276057  cvttss2si r8d, dword ptr [rbp+3Fh+var_60+0Ch]
0x18027605d  mov     dword ptr [rbp+3Fh+string], r13d
0x180276061  mov     rax, [rcx]
0x180276064  mov     rax, [rax+20h]
0x180276068  cvttss2si edx, dword ptr [rbp+3Fh+var_60]
0x18027606d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276072  mov     edi, eax
0x180276074  cmp     [rsi+9Fh], bl
0x18027607a  jz      short loc_1802760A7
0x18027607c  test    eax, eax
0x18027607e  jnz     short loc_180276090
0x180276080  mov     edx, dword ptr [rbp+3Fh+string]; item
0x180276083  xor     r8d, r8d; hmenu
0x180276086  mov     rcx, rsi; this
0x180276089  call    ?Invoke@CSpellContextHandler@@QEAAJHPEAUHMENU__@@@Z; CSpellContextHandler::Invoke(int,HMENU__ *)
0x18027608e  mov     edi, eax
0x180276090  test    edi, edi
0x180276092  js      short loc_1802760A7
0x180276094  cmp     [rsi+9Dh], bl
0x18027609a  jnz     short loc_1802760A7
0x18027609c  mov     rdx, r12; struct IEnumString *
0x18027609f  mov     rcx, rsi; this
0x1802760a2  call    ?TelemetryLogDismissAlternates@CSpellContextHandler@@AEAAXPEAUIEnumString@@@Z; CSpellContextHandler::TelemetryLogDismissAlternates(IEnumString *)
0x1802760a7  lea     rcx, [rbp+3Fh+var_B8]
0x1802760ab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802760b0  jmp     loc_1802763C7
0x1802760b5  cmp     [rsi+9Eh], bl
0x1802760bb  jz      loc_180276203
0x1802760c1  xorps   xmm0, xmm0
0x1802760c4  mov     [rbp+3Fh+string], rbx
0x1802760c8  mov     r8d, 2Bh ; '+'; unsigned int
0x1802760ce  movsd   [rbp+3Fh+var_A8], xmm0
0x1802760d3  lea     rdx, ?RuntimeClass_Windows_Graphics_Display_DisplayInformation@@3QBGB; "Windows.Graphics.Display.DisplayInforma"...
0x1802760da  lea     rcx, [rbp+3Fh+string]; this
0x1802760de  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1802760e3  mov     edi, eax
0x1802760e5  test    eax, eax
0x1802760e7  js      loc_180276196
0x1802760ed  mov     [rbp+3Fh+var_B8], rbx
0x1802760f1  lea     rcx, [rbp+3Fh+var_B8]
0x1802760f5  mov     rbx, [rbp+3Fh+string]
0x1802760f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1802760fe  lea     r8, [rbp+3Fh+var_B8]
0x180276102  mov     rcx, rbx
0x180276105  lea     rdx, _GUID_c6a02a6c_d452_44dc_ba07_96f3c6adf9d1
0x18027610c  call    cs:__imp_RoGetActivationFactory
0x180276112  xor     ebx, ebx
0x180276114  mov     edi, eax
0x180276116  test    eax, eax
0x180276118  js      short loc_18027618D
0x18027611a  mov     rdi, [rbp+3Fh+var_B8]
0x18027611e  lea     rcx, [rsp+0F0h+var_C0]
0x180276123  mov     [rsp+0F0h+var_C0], rbx
0x180276128  mov     rax, [rdi]
0x18027612b  mov     rbx, [rax+30h]
0x18027612f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276134  lea     rdx, [rsp+0F0h+var_C0]
0x180276139  mov     rcx, rdi
0x18027613c  mov     rax, rbx
0x18027613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276144  xor     ebx, ebx
0x180276146  mov     edi, eax
0x180276148  test    eax, eax
0x18027614a  js      short loc_180276183
0x18027614c  lea     rdx, [rbp+3Fh+var_A0]
0x180276150  mov     [rbp+3Fh+var_A0], rbx
0x180276154  lea     rcx, [rsp+0F0h+var_C0]
0x180276159  call    ??$As@UIDisplayInformation2@Display@Graphics@Windows@@@?$ComPtr@UIDisplayInformation@Display@Graphics@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDisplayInformation2@Display@Graphics@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation>::As<Windows::Graphics::Display::IDisplayInformation2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Graphics::Display::IDisplayInformation2>>)
0x18027615e  mov     edi, eax
0x180276160  test    eax, eax
0x180276162  js      short loc_18027617A
0x180276164  mov     rcx, [rbp+3Fh+var_A0]
0x180276168  lea     rdx, [rbp+3Fh+var_A8]
0x18027616c  mov     rax, [rcx]
0x18027616f  mov     rax, [rax+30h]
0x180276173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180276178  mov     edi, eax
0x18027617a  lea     rcx, [rbp+3Fh+var_A0]
0x18027617e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276183  lea     rcx, [rsp+0F0h+var_C0]
0x180276188  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18027618d  lea     rcx, [rbp+3Fh+var_B8]
0x180276191  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180276196  mov     rax, [rbp+3Fh+var_90]
0x18027619a  xorps   xmm0, xmm0
0x18027619d  mov     rcx, [rbp+3Fh+string]; string
0x1802761a1  mov     dword ptr [rbp+3Fh+var_90+8], 40000000h
0x1802761a8  mov     dword ptr [rbp+3Fh+var_90+0Ch], 40000000h
0x1802761af  mov     rax, [rax]
0x1802761b2  cvtsi2sd xmm0, eax
0x1802761b6  shr     rax, 20h
0x1802761ba  divsd   xmm0, [rbp+3Fh+var_A8]
0x1802761bf  cvtpd2ps xmm0, xmm0
  ... truncated ...
```
