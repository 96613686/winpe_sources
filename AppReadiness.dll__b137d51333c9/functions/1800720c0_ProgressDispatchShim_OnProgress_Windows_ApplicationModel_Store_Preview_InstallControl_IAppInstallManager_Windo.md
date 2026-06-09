# ProgressDispatchShim::OnProgress(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *)

- ea: `0x1800720c0`
- end: `0x1800725c1`
- name: `?OnProgress@ProgressDispatchShim@@QEAAJPEAUIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIAppInstallManagerItemEventArgs@34567@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(ProgressDispatchShim *__hidden this, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *, struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002958`
- `0x18006d37c`
- `0x18006d514`
- `0x18006fa04`
- `0x180071b54`
- `0x1800720c0`
- `0x18007265c`
- `0x1800733d8`
- `0x1800736ac`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800721cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800721cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180072583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007245f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800724cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072504`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072423`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007245f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800724cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180072504`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProgressDispatchShim::OnProgress(
        ProgressDispatchShim *this,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager *a2,
        struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *a3)
{
  int (__fastcall *v5)(struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *, GUID *, _QWORD); // rbx
  __int64 v6; // r13
  __int64 (__fastcall ***v7)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64); // rbx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  unsigned int v11; // esi
  unsigned int v12; // r15d
  struct IPropertyStore **v13; // r12
  int v14; // ebx
  unsigned int *v15; // rdi
  __int64 (__fastcall *v16)(unsigned int *, __int64 *); // rbx
  __int64 v17; // rdi
  int (__fastcall *v18)(__int64, __int64 *); // rbx
  int i; // eax
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData **); // rbx
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *v22; // rdi
  int (__fastcall *v23)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, unsigned int **); // rbx
  __int64 v24; // r8
  int v25; // r14d
  __int64 v26; // rdi
  void (__fastcall *v27)(__int64, _QWORD, PCWSTR, _QWORD, int); // rbx
  PCWSTR v28; // rax
  __int64 v29; // rdi
  void (__fastcall *v30)(__int64, _QWORD, PCWSTR, struct IPropertyStore **, unsigned int); // rbx
  PCWSTR v31; // rax
  __int64 v32; // rdi
  void (__fastcall *v33)(__int64, _QWORD, PCWSTR, _QWORD); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v35; // rdi
  void (__fastcall *v36)(__int64, _QWORD, PCWSTR); // rbx
  PCWSTR v37; // rax
  __int64 v38; // rdi
  void (__fastcall *v39)(__int64, _QWORD, PCWSTR, _QWORD, int, _DWORD); // rbx
  PCWSTR v40; // rax
  __int64 v42; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  int v44; // [rsp+50h] [rbp-19h] BYREF
  unsigned int *v45; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *v46; // [rsp+60h] [rbp-9h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-1h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h] BYREF
  unsigned int v49; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v50; // [rsp+80h] [rbp+17h]
  struct IPropertyStore **v51; // [rsp+88h] [rbp+1Fh] BYREF
  double v52; // [rsp+E0h] [rbp+77h] BYREF
  int v53; // [rsp+E8h] [rbp+7Fh] BYREF

  v47 = 0;
  v5 = **(int (__fastcall ***)(struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerItemEventArgs *, GUID *, _QWORD))a3;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  if ( v5(a3, &GUID_49d3dfab_168a_4cbf_a93a_9e448c82737d, &v47) >= 0 )
  {
    v49 = 0;
    if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), unsigned int *))(*v47)[8])(v47, &v49) >= 0 )
    {
      v6 = (unsigned int)MapType(v49);
      if ( (unsigned __int8)ProgressDispatchShim::DoAnyHandlersWantThisEvent(this, v6) )
      {
        v48 = 0;
        v44 = 0;
        string = 0;
        v53 = 0;
        v7 = v47;
        v8 = (*v47)[10];
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
        if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))v8)(v7, &v48) < 0
          || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 48LL))(v48, &v44) < 0
          || (v9 = v47,
              v10 = (*v47)[7],
              WindowsDeleteString(string),
              string = 0,
              ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v10)(v9, &string) < 0)
          || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 80LL))(v48, &v53) < 0 )
        {
LABEL_52:
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v48);
          goto LABEL_53;
        }
        if ( !v44 || (v11 = 2, v44 == 2) )
        {
          v11 = 0;
        }
        else
        {
          switch ( v44 )
          {
            case 3:
              goto LABEL_14;
            case 5:
              break;
            case 8:
LABEL_14:
              v11 = 1;
              break;
            default:
              v11 = 4;
              break;
          }
        }
        v12 = 0;
        LODWORD(v52) = 0;
        v13 = 0;
        v51 = 0;
        LODWORD(v50) = 0;
        if ( v53 >= 0 )
        {
          if ( v44 )
          {
            if ( ((v44 - 3) & 0xFFFFFFFD) == 0 )
            {
              v52 = 0.0;
              if ( (*(int (__fastcall **)(__int64, double *))(*(_QWORD *)v48 + 72LL))(v48, &v52) >= 0 )
                v50 = (unsigned int)(int)v52;
            }
          }
          else
          {
            v45 = 0;
            v14 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::As<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallItemInternal>(
                    &v47,
                    (__int64)&v45);
            if ( v14 >= 0 )
            {
              v42 = 0;
              v15 = v45;
              v16 = *(__int64 (__fastcall **)(unsigned int *, __int64 *))(*(_QWORD *)v45 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
              v14 = v16(v15, &v42);
              if ( v14 >= 0 )
              {
                v46 = 0;
                v14 = BlockOnCompletionAndGetResults<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(
                        v42,
                        (__int64)&v46);
                if ( v14 >= 0 )
                {
                  v14 = PropertyStoreFromInstallItem(v46, &v51, (unsigned int *)&v52);
                  v12 = LODWORD(v52);
                  v13 = v51;
                }
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
              }
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
            LODWORD(v50) = 0;
            if ( v14 < 0 )
              goto LABEL_49;
          }
        }
        v42 = 0;
        v17 = *((_QWORD *)this + 7);
        v18 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v17 + 16) + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
        if ( v18(v17 + 16, &v42) >= 0 )
        {
          LOBYTE(v52) = 0;
          for ( i = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v42 + 56LL))(v42, &v52);
                i >= 0 && LOBYTE(v52);
                i = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v42 + 64LL))(v42, &v52) )
          {
            v46 = 0;
            v45 = 0;
            v20 = v42;
            v21 = *(int (__fastcall **)(__int64, struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData **))(*(_QWORD *)v42 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
            if ( v21(v20, &v46) >= 0 )
            {
              v22 = v46;
              v23 = *(int (__fastcall **)(struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *, unsigned int **))(*(_QWORD *)v46 + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
              if ( v23(v22, &v45) >= 0 )
              {
                if ( (unsigned __int8)ShouldSendProgressToHandler(v45[10], (unsigned int)v6) )
                {
                  v25 = v53;
                  if ( v53 >= 0 )
                  {
                    if ( v44 )
                    {
                      if ( v44 == 8 )
                      {
                        v32 = *(_QWORD *)(v24 + 32);
                        v33 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, _QWORD))(*(_QWORD *)v32 + 56LL);
                        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                        v33(v32, (unsigned int)v6, StringRawBuffer, v11);
                      }
                      else if ( v44 == 7 )
                      {
                        v35 = *(_QWORD *)(v24 + 32);
                        v36 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR))(*(_QWORD *)v35 + 72LL);
                        v37 = WindowsGetStringRawBuffer(string, 0);
                        v36(v35, (unsigned int)v6, v37);
                      }
                      else if ( ((v44 - 2) & 0xFFFFFFFC) == 0 && v44 != 4 )
                      {
                        v38 = *(_QWORD *)(v24 + 32);
                        v39 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, _QWORD, int, _DWORD))(*(_QWORD *)v38 + 40LL);
                        v40 = WindowsGetStringRawBuffer(string, 0);
                        v39(v38, (unsigned int)v6, v40, v11, 20, v50);
                      }
                    }
                    else
                    {
                      v29 = *(_QWORD *)(v24 + 32);
                      v30 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, struct IPropertyStore **, unsigned int))(*(_QWORD *)v29 + 24LL);
                      v31 = WindowsGetStringRawBuffer(string, 0);
                      v30(v29, (unsigned int)v6, v31, v13, v12);
                    }
                  }
                  else
                  {
                    v26 = *(_QWORD *)(v24 + 32);
                    v27 = *(void (__fastcall **)(__int64, _QWORD, PCWSTR, _QWORD, int))(*(_QWORD *)v26 + 48LL);
                    v28 = WindowsGetStringRawBuffer(string, 0);
                    v27(v26, (unsigned int)v6, v28, v11, v25);
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
LABEL_49:
        if ( v53 >= 0 && !v44 )
          ReleasePropertyStore(v13, v12);
        goto LABEL_52;
      }
    }
  }
LABEL_53:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  return 0;
}

```

## disassembly

```asm
0x1800720c0  mov     [rsp-8+arg_0], rbx
0x1800720c5  push    rbp
0x1800720c6  push    rsi
0x1800720c7  push    rdi
0x1800720c8  push    r12
0x1800720ca  push    r13
0x1800720cc  push    r14
0x1800720ce  push    r15
0x1800720d0  lea     rbp, [rsp-27h]
0x1800720d5  sub     rsp, 90h
0x1800720dc  mov     rdi, r8
0x1800720df  mov     r14, rcx
0x1800720e2  mov     [rbp+57h+var_58], 0
0x1800720ea  mov     rax, [r8]
0x1800720ed  mov     rbx, [rax]
0x1800720f0  lea     rcx, [rbp+57h+var_58]
0x1800720f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800720f9  lea     r8, [rbp+57h+var_58]
0x1800720fd  lea     rdx, _GUID_49d3dfab_168a_4cbf_a93a_9e448c82737d
0x180072104  mov     rcx, rdi
0x180072107  mov     rax, rbx
0x18007210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007210f  test    eax, eax
0x180072111  js      loc_18007259B
0x180072117  mov     [rbp+57h+var_48], 0
0x18007211e  mov     rcx, [rbp+57h+var_58]
0x180072122  mov     rax, [rcx]
0x180072125  lea     rdx, [rbp+57h+var_48]
0x180072129  mov     rax, [rax+40h]
0x18007212d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072132  test    eax, eax
0x180072134  js      loc_18007259B
0x18007213a  mov     ecx, [rbp+57h+var_48]
0x18007213d  call    ?MapType@@YA?AW4__MIDL_IWindowsStoreInstallProgress_0002@@W4AppInstallType@InstallControl@Preview@Store@ApplicationModel@Windows@@@Z; MapType(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallType)
0x180072142  mov     r13d, eax
0x180072145  mov     edx, eax
0x180072147  mov     rcx, r14
0x18007214a  call    ?DoAnyHandlersWantThisEvent@ProgressDispatchShim@@AEAA_NW4__MIDL_IWindowsStoreInstallProgress_0002@@@Z; ProgressDispatchShim::DoAnyHandlersWantThisEvent(__MIDL_IWindowsStoreInstallProgress_0002)
0x18007214f  test    al, al
0x180072151  jz      loc_18007259B
0x180072157  mov     [rbp+57h+var_50], 0
0x18007215f  mov     [rbp+57h+var_70], 0
0x180072166  mov     [rbp+57h+string], 0
0x18007216e  mov     [rbp+57h+arg_18], 0
0x180072175  mov     rdi, [rbp+57h+var_58]
0x180072179  mov     rax, [rdi]
0x18007217c  mov     rbx, [rax+50h]
0x180072180  lea     rcx, [rbp+57h+var_50]
0x180072184  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072189  lea     rdx, [rbp+57h+var_50]
0x18007218d  mov     rcx, rdi
0x180072190  mov     rax, rbx
0x180072193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072198  test    eax, eax
0x18007219a  js      loc_18007257F
0x1800721a0  mov     rcx, [rbp+57h+var_50]
0x1800721a4  mov     rax, [rcx]
0x1800721a7  lea     rdx, [rbp+57h+var_70]
0x1800721ab  mov     rax, [rax+30h]
0x1800721af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721b4  test    eax, eax
0x1800721b6  js      loc_18007257F
0x1800721bc  mov     rdi, [rbp+57h+var_58]
0x1800721c0  mov     rax, [rdi]
0x1800721c3  mov     rbx, [rax+38h]
0x1800721c7  mov     rcx, [rbp+57h+string]; string
0x1800721cb  call    cs:__imp_WindowsDeleteString
0x1800721d1  mov     [rbp+57h+string], 0
0x1800721d9  lea     rdx, [rbp+57h+string]
0x1800721dd  mov     rcx, rdi
0x1800721e0  mov     rax, rbx
0x1800721e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721e8  test    eax, eax
0x1800721ea  js      loc_18007257F
0x1800721f0  mov     rcx, [rbp+57h+var_50]
0x1800721f4  mov     rax, [rcx]
0x1800721f7  lea     rdx, [rbp+57h+arg_18]
0x1800721fb  mov     rax, [rax+50h]
0x1800721ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072204  test    eax, eax
0x180072206  js      loc_18007257F
0x18007220c  mov     edx, [rbp+57h+var_70]
0x18007220f  mov     ecx, edx
0x180072211  test    edx, edx
0x180072213  jz      short loc_18007223A
0x180072215  mov     esi, 2
0x18007221a  sub     ecx, esi
0x18007221c  jz      short loc_18007223A
0x18007221e  sub     ecx, 1
0x180072221  jz      short loc_180072233
0x180072223  sub     ecx, esi
0x180072225  jz      short loc_18007223C
0x180072227  cmp     ecx, 3
0x18007222a  jz      short loc_180072233
0x18007222c  mov     esi, 4
0x180072231  jmp     short loc_18007223C
0x180072233  mov     esi, 1
0x180072238  jmp     short loc_18007223C
0x18007223a  xor     esi, esi
0x18007223c  xor     r15d, r15d
0x18007223f  mov     [rbp+57h+arg_10], r15d
0x180072243  xor     r12d, r12d
0x180072246  mov     [rbp+57h+var_38], r12
0x18007224a  mov     dword ptr [rbp+57h+var_40], r12d
0x18007224e  cmp     [rbp+57h+arg_18], r12d
0x180072252  jl      loc_180072338
0x180072258  test    edx, edx
0x18007225a  jnz     loc_180072304
0x180072260  mov     [rbp+57h+var_68], r12
0x180072264  lea     rdx, [rbp+57h+var_68]
0x180072268  lea     rcx, [rbp+57h+var_58]
0x18007226c  call    ??$As@UIAppInstallItemInternal@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@?$ComPtr@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppInstallItemInternal@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::As<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallItemInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppInstallItemInternal>>)
0x180072271  mov     ebx, eax
0x180072273  test    eax, eax
0x180072275  js      short loc_1800722EA
0x180072277  mov     [rbp+57h+var_80], r12
0x18007227b  mov     rdi, [rbp+57h+var_68]
0x18007227f  mov     rax, [rdi]
0x180072282  mov     rbx, [rax+30h]
0x180072286  lea     rcx, [rbp+57h+var_80]
0x18007228a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007228f  lea     rdx, [rbp+57h+var_80]
0x180072293  mov     rcx, rdi
0x180072296  mov     rax, rbx
0x180072299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007229e  mov     ebx, eax
0x1800722a0  test    eax, eax
0x1800722a2  js      short loc_1800722E0
0x1800722a4  mov     [rbp+57h+var_60], r12
0x1800722a8  lea     rdx, [rbp+57h+var_60]
0x1800722ac  mov     rcx, [rbp+57h+var_80]
0x1800722b0  call    ??$BlockOnCompletionAndGetResults@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@UIAppData@234567@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData>>,tagCOWAIT_FLAGS,void *)
0x1800722b5  mov     ebx, eax
0x1800722b7  test    eax, eax
0x1800722b9  js      short loc_1800722D6
0x1800722bb  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x1800722bf  lea     rdx, [rbp+57h+var_38]; struct IPropertyStore ***
0x1800722c3  mov     rcx, [rbp+57h+var_60]; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *
0x1800722c7  call    ?PropertyStoreFromInstallItem@@YAJPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAPEAPEAUIPropertyStore@@PEAI@Z; PropertyStoreFromInstallItem(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,IPropertyStore * * *,uint *)
0x1800722cc  mov     ebx, eax
0x1800722ce  mov     r15d, [rbp+57h+arg_10]
0x1800722d2  mov     r12, [rbp+57h+var_38]
0x1800722d6  lea     rcx, [rbp+57h+var_60]
0x1800722da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800722df  nop
0x1800722e0  lea     rcx, [rbp+57h+var_80]
0x1800722e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800722e9  nop
0x1800722ea  lea     rcx, [rbp+57h+var_68]
0x1800722ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800722f3  mov     dword ptr [rbp+57h+var_40], 0
0x1800722fa  test    ebx, ebx
0x1800722fc  js      loc_180072567
0x180072302  jmp     short loc_180072338
0x180072304  lea     eax, [rdx-3]
0x180072307  test    eax, 0FFFFFFFDh
0x18007230c  jnz     short loc_180072338
0x18007230e  xorps   xmm0, xmm0
0x180072311  movsd   qword ptr [rbp+57h+arg_10], xmm0
0x180072316  mov     rcx, [rbp+57h+var_50]
0x18007231a  mov     rax, [rcx]
0x18007231d  lea     rdx, [rbp+57h+arg_10]
0x180072321  mov     rax, [rax+48h]
0x180072325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007232a  test    eax, eax
0x18007232c  js      short loc_180072338
0x18007232e  cvttsd2si rax, qword ptr [rbp+57h+arg_10]
0x180072334  mov     [rbp+57h+var_40], rax
0x180072338  mov     [rbp+57h+var_80], 0
0x180072340  mov     rdi, [r14+38h]
0x180072344  mov     rax, [rdi+10h]
0x180072348  mov     rbx, [rax+30h]
0x18007234c  lea     rcx, [rbp+57h+var_80]
0x180072350  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180072355  lea     rdx, [rbp+57h+var_80]
0x180072359  lea     rcx, [rdi+10h]
0x18007235d  mov     rax, rbx
0x180072360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072365  test    eax, eax
0x180072367  js      loc_18007255E
0x18007236d  mov     byte ptr [rbp+57h+arg_10], 0
0x180072371  mov     rcx, [rbp+57h+var_80]
0x180072375  mov     rax, [rcx]
0x180072378  mov     rax, [rax+38h]
0x18007237c  jmp     loc_18007254D
0x180072381  cmp     byte ptr [rbp+57h+arg_10], 0
0x180072385  jz      loc_18007255E
0x18007238b  mov     [rbp+57h+var_60], 0
0x180072393  mov     [rbp+57h+var_68], 0
0x18007239b  mov     rdi, [rbp+57h+var_80]
0x18007239f  mov     rax, [rdi]
0x1800723a2  mov     rbx, [rax+30h]
0x1800723a6  lea     rcx, [rbp+57h+var_60]
0x1800723aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800723af  lea     rdx, [rbp+57h+var_60]
0x1800723b3  mov     rcx, rdi
0x1800723b6  mov     rax, rbx
0x1800723b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723be  test    eax, eax
0x1800723c0  js      loc_18007252F
0x1800723c6  mov     rdi, [rbp+57h+var_60]
0x1800723ca  mov     rax, [rdi]
0x1800723cd  mov     rbx, [rax+38h]
0x1800723d1  lea     rcx, [rbp+57h+var_68]
0x1800723d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800723da  lea     rdx, [rbp+57h+var_68]
0x1800723de  mov     rcx, rdi
0x1800723e1  mov     rax, rbx
0x1800723e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723e9  test    eax, eax
0x1800723eb  js      loc_18007252F
0x1800723f1  mov     edx, r13d
0x1800723f4  mov     r8, [rbp+57h+var_68]
0x1800723f8  mov     ecx, [r8+28h]
0x1800723fc  call    ?ShouldSendProgressToHandler@@YA_NW4__MIDL_IWindowsStoreInstallProgress_0003@@W4__MIDL_IWindowsStoreInstallProgress_0002@@@Z; ShouldSendProgressToHandler(__MIDL_IWindowsStoreInstallProgress_0003,__MIDL_IWindowsStoreInstallProgress_0002)
0x180072401  test    al, al
0x180072403  jz      loc_18007252F
0x180072409  mov     r14d, [rbp+57h+arg_18]
0x18007240d  test    r14d, r14d
0x180072410  jns     short loc_180072447
0x180072412  mov     rdi, [r8+20h]
0x180072416  mov     rax, [rdi]
0x180072419  mov     rbx, [rax+30h]
0x18007241d  xor     edx, edx; length
0x18007241f  mov     rcx, [rbp+57h+string]; string
0x180072423  call    cs:__imp_WindowsGetStringRawBuffer
0x180072429  mov     [rsp+0C0h+var_A0], r14d
0x18007242e  mov     r9d, esi
0x180072431  mov     r8, rax
0x180072434  mov     edx, r13d
0x180072437  mov     rcx, rdi
0x18007243a  mov     rax, rbx
0x18007243d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072442  jmp     loc_18007252F
0x180072447  mov     ecx, [rbp+57h+var_70]
0x18007244a  test    ecx, ecx
0x18007244c  jnz     short loc_180072483
0x18007244e  mov     rdi, [r8+20h]
0x180072452  mov     rax, [rdi]
0x180072455  mov     rbx, [rax+18h]
0x180072459  xor     edx, edx; length
0x18007245b  mov     rcx, [rbp+57h+string]; string
0x18007245f  call    cs:__imp_WindowsGetStringRawBuffer
0x180072465  mov     [rsp+0C0h+var_A0], r15d
0x18007246a  mov     r9, r12
0x18007246d  mov     r8, rax
0x180072470  mov     edx, r13d
0x180072473  mov     rcx, rdi
0x180072476  mov     rax, rbx
0x180072479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007247e  jmp     loc_18007252F
0x180072483  cmp     ecx, 8
0x180072486  jnz     short loc_1800724B5
0x180072488  mov     rdi, [r8+20h]
0x18007248c  mov     rax, [rdi]
0x18007248f  mov     rbx, [rax+38h]
0x180072493  xor     edx, edx; length
0x180072495  mov     rcx, [rbp+57h+string]; string
0x180072499  call    cs:__imp_WindowsGetStringRawBuffer
0x18007249f  mov     r9d, esi
0x1800724a2  mov     r8, rax
0x1800724a5  mov     edx, r13d
0x1800724a8  mov     rcx, rdi
0x1800724ab  mov     rax, rbx
0x1800724ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724b3  jmp     short loc_18007252F
0x1800724b5  cmp     ecx, 7
0x1800724b8  jnz     short loc_1800724E4
0x1800724ba  mov     rdi, [r8+20h]
0x1800724be  mov     rax, [rdi]
0x1800724c1  mov     rbx, [rax+48h]
0x1800724c5  xor     edx, edx; length
0x1800724c7  mov     rcx, [rbp+57h+string]; string
0x1800724cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800724d1  mov     r8, rax
0x1800724d4  mov     edx, r13d
0x1800724d7  mov     rcx, rdi
0x1800724da  mov     rax, rbx
0x1800724dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724e2  jmp     short loc_18007252F
0x1800724e4  lea     eax, [rcx-2]
0x1800724e7  test    eax, 0FFFFFFFCh
0x1800724ec  jnz     short loc_18007252F
0x1800724ee  cmp     ecx, 4
0x1800724f1  jz      short loc_18007252F
0x1800724f3  mov     rdi, [r8+20h]
0x1800724f7  mov     rax, [rdi]
0x1800724fa  mov     rbx, [rax+28h]
0x1800724fe  xor     edx, edx; length
0x180072500  mov     rcx, [rbp+57h+string]; string
0x180072504  call    cs:__imp_WindowsGetStringRawBuffer
0x18007250a  mov     rcx, [rbp+57h+var_40]
0x18007250e  mov     [rsp+0C0h+var_98], ecx
0x180072512  mov     [rsp+0C0h+var_A0], 14h
0x18007251a  mov     r9d, esi
0x18007251d  mov     r8, rax
0x180072520  mov     edx, r13d
0x180072523  mov     rcx, rdi
0x180072526  mov     rax, rbx
0x180072529  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
