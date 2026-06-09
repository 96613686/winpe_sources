# ScheduleHelpers::GetOrCreateSyncCenterTaskFolder(ITaskFolder * *)

- ea: `0x18002841c`
- end: `0x180028571`
- name: `?GetOrCreateSyncCenterTaskFolder@ScheduleHelpers@@YAJPEAPEAUITaskFolder@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct ITaskService *this, struct ITaskFolder **)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025070`
- `0x1800250c0`
- `0x180025180`
- `0x1800252b0`

## callees

- `0x18000b310`
- `0x1800133b0`
- `0x1800134dc`
- `0x180024f6c`
- `0x18002834c`
- `0x18002841c`
- `0x180028578`
- `0x1800286bc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002845a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002845a`
- `OLEAUT32!__imp_SysFreeString` at `0x180028534`
- `OLEAUT32!__imp_SysFreeString` at `0x18002854c`
- `OLEAUT32!__imp_SysFreeString` at `0x180028534`
- `OLEAUT32!__imp_SysFreeString` at `0x18002854c`

## pseudocode

```c
__int64 __fastcall ScheduleHelpers::GetOrCreateSyncCenterTaskFolder(struct ITaskService *this, struct ITaskFolder **a2)
{
  LPVOID *ppv; // rax
  HRESULT Instance; // ebx
  __int64 v5; // rax
  __int64 (__fastcall *v6)(ScheduleHelpers *, __int128 *, __int128 *, __int128 *); // rax
  struct ITaskFolder **v7; // r8
  OLECHAR *v8; // rbx
  BSTR bstrString; // [rsp+30h] [rbp-49h] BYREF
  struct ITaskFolder *v11[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+50h] [rbp-29h]
  __int128 v13; // [rsp+60h] [rbp-19h] BYREF
  __int64 v14; // [rsp+70h] [rbp-9h]
  __int128 v15; // [rsp+80h] [rbp+7h] BYREF
  __int64 v16; // [rsp+90h] [rbp+17h]
  __int128 v17; // [rsp+A0h] [rbp+27h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+37h]
  ScheduleHelpers *v19; // [rsp+E8h] [rbp+6Fh] BYREF
  BSTR v20; // [rsp+F0h] [rbp+77h] BYREF
  ScheduleHelpers *v21; // [rsp+F8h] [rbp+7Fh] BYREF

  ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v19);
  ppv = (LPVOID *)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&v19);
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance >= 0 )
  {
    v12 = 0;
    v14 = 0;
    v16 = 0;
    v18 = 0;
    v5 = *(_QWORD *)v19;
    *(_OWORD *)v11 = 0;
    v13 = 0;
    v15 = 0;
    v6 = *(__int64 (__fastcall **)(ScheduleHelpers *, __int128 *, __int128 *, __int128 *))(v5 + 80);
    v17 = 0;
    Instance = v6(v19, &v17, &v15, &v13);
    if ( Instance >= 0 )
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v21);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v20, L"Microsoft\\Windows");
      if ( v20
        && (*(int (__fastcall **)(ScheduleHelpers *, BSTR, ScheduleHelpers **))(*(_QWORD *)v19 + 56LL))(v19, v20, &v21) >= 0 )
      {
        bstrString = 0;
        ATL::CComBSTR::operator=(&bstrString, L"O:BAD:P(A;;0x1200AD;;;BU)(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)");
        v8 = bstrString;
        if ( bstrString )
          ScheduleHelpers::GetOrCreateTaskFolder(
            v21,
            (struct ITaskFolder *)&stru_18005DDF0,
            bstrString,
            (unsigned __int16 *)this,
            v11);
        SysFreeString(v8);
      }
      Instance = ScheduleHelpers::GetSyncCenterTaskFolder(v19, this, v7);
      SysFreeString(v20);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v21);
    }
  }
  ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v19);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002841c  push    rbp
0x18002841e  push    rbx
0x18002841f  push    rsi
0x180028420  lea     rbp, [rsp-47h]
0x180028425  sub     rsp, 0C0h
0x18002842c  mov     rsi, rcx
0x18002842f  lea     rcx, [rbp+57h+arg_8]; void *
0x180028433  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180028438  lea     rcx, [rbp+57h+arg_8]; void *
0x18002843c  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180028441  xor     edx, edx; pUnkOuter
0x180028443  mov     [rsp+0D0h+ppv], rax; ppv
0x180028448  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002844f  lea     rcx, CLSID_TaskScheduler; rclsid
0x180028456  lea     r8d, [rdx+1]; dwClsContext
0x18002845a  call    cs:__imp_CoCreateInstance
0x180028460  mov     ebx, eax
0x180028462  test    eax, eax
0x180028464  js      loc_18002855B
0x18002846a  mov     rcx, [rbp+57h+arg_8]
0x18002846e  lea     rdx, [rbp+57h+var_90]
0x180028472  xor     eax, eax
0x180028474  mov     [rsp+0D0h+ppv], rdx; struct ITaskFolder **
0x180028479  xorps   xmm1, xmm1
0x18002847c  mov     [rbp+57h+var_80], rax
0x180028480  mov     [rbp+57h+var_60], rax
0x180028484  lea     r9, [rbp+57h+var_70]
0x180028488  mov     [rbp+57h+var_40], rax
0x18002848c  lea     r8, [rbp+57h+var_50]
0x180028490  mov     [rbp+57h+var_20], rax
0x180028494  lea     rdx, [rbp+57h+var_30]
0x180028498  mov     rax, [rcx]
0x18002849b  movaps  xmmword ptr [rbp+57h+var_90], xmm1
0x18002849f  movaps  [rbp+57h+var_70], xmm1
0x1800284a3  movaps  [rbp+57h+var_50], xmm1
0x1800284a7  mov     rax, [rax+50h]
0x1800284ab  movaps  [rbp+57h+var_30], xmm1
0x1800284af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284b4  mov     ebx, eax
0x1800284b6  test    eax, eax
0x1800284b8  js      loc_18002855B
0x1800284be  lea     rcx, [rbp+57h+arg_18]; void *
0x1800284c2  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x1800284c7  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows"
0x1800284ce  lea     rcx, [rbp+57h+arg_10]; this
0x1800284d2  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800284d7  cmp     [rbp+57h+arg_10], 0
0x1800284dc  jz      short loc_18002853A
0x1800284de  mov     rcx, [rbp+57h+arg_8]
0x1800284e2  lea     r8, [rbp+57h+arg_18]
0x1800284e6  mov     rdx, [rbp+57h+arg_10]
0x1800284ea  mov     rax, [rcx]
0x1800284ed  mov     rax, [rax+38h]
0x1800284f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284f6  test    eax, eax
0x1800284f8  js      short loc_18002853A
0x1800284fa  lea     rdx, aOBadPA0x1200ad; "O:BAD:P(A;;0x1200AD;;;BU)(A;OICI;GA;;;B"...
0x180028501  mov     [rbp+57h+bstrString], 0
0x180028509  lea     rcx, [rbp+57h+bstrString]
0x18002850d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180028512  mov     rbx, [rbp+57h+bstrString]
0x180028516  test    rbx, rbx
0x180028519  jz      short loc_180028531
0x18002851b  mov     rcx, [rbp+57h+arg_18]; this
0x18002851f  lea     rdx, stru_18005DDF0; struct ITaskFolder *
0x180028526  mov     r9, rsi; unsigned __int16 *
0x180028529  mov     r8, rbx; unsigned __int16 *
0x18002852c  call    ?GetOrCreateTaskFolder@ScheduleHelpers@@YAJPEAUITaskFolder@@PEBGPEAGPEAPEAU2@@Z; ScheduleHelpers::GetOrCreateTaskFolder(ITaskFolder *,ushort const *,ushort *,ITaskFolder * *)
0x180028531  mov     rcx, rbx; bstrString
0x180028534  call    cs:__imp_SysFreeString
0x18002853a  mov     rcx, [rbp+57h+arg_8]; this
0x18002853e  mov     rdx, rsi; struct ITaskService *
0x180028541  call    ?GetSyncCenterTaskFolder@ScheduleHelpers@@YAJPEAUITaskService@@PEAPEAUITaskFolder@@@Z; ScheduleHelpers::GetSyncCenterTaskFolder(ITaskService *,ITaskFolder * *)
0x180028546  mov     rcx, [rbp+57h+arg_10]; bstrString
0x18002854a  mov     ebx, eax
0x18002854c  call    cs:__imp_SysFreeString
0x180028552  lea     rcx, [rbp+57h+arg_18]
0x180028556  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x18002855b  lea     rcx, [rbp+57h+arg_8]
0x18002855f  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180028564  mov     eax, ebx
0x180028566  add     rsp, 0C0h
0x18002856d  pop     rsi
0x18002856e  pop     rbx
0x18002856f  pop     rbp
0x180028570  retn
```
