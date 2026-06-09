# _lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_::operator()(Windows::Storage::Streams::IRandomAccessStream *,Windows::Internal::CNoResult &)

- ea: `0x1800adeb0`
- end: `0x1800ae070`
- name: `??R_lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_@@QEBAJPEAUIRandomAccessStream@Streams@Storage@Windows@@AEAVCNoResult@Internal@4@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b4c40`

## callees

- `0x180030304`
- `0x18003217c`
- `0x180036358`
- `0x180036a6c`
- `0x1800387c8`
- `0x1800abc94`
- `0x1800adeb0`
- `0x1800e5010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x1800ae022`
- `ntdll!WinSqmSetDWORD` at `0x1800ae022`
- `ntdll!WinSqmIncrementDWORD` at `0x1800ae011`
- `ntdll!WinSqmIncrementDWORD` at `0x1800ae011`
- `USER32!SystemParametersInfoW` at `0x1800adfd3`
- `USER32!SystemParametersInfoW` at `0x1800adfd3`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800adee0`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800adee0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adf89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800adf89`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _lambda_7322bff9dbafb524f5c3fdecbc3ef0d8_::operator()(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 a3)
{
  HRESULT v5; // ebx
  int (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // edi
  HKEY v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+80h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+38h] BYREF

  v13 = a3;
  v5 = 1;
  if ( !(unsigned int)SHWindowsPolicy(POLID_NoChangingLockScreen) )
  {
    v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v11);
    v10 = 0;
    LOBYTE(v13) = 0;
    v6 = **a2;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    if ( v6(a2, &GUID_29d25bfc_e5db_473e_9e19_cdb9c77393a4, &v10) >= 0
      && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL))(v10, &v13) >= 0
      && (_BYTE)v13 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      v5 = CoCreateInstance(&CLSID_LockScreenStore, 0, 1u, &GUID_fb37854f_513a_4ca8_9a06_4adab5968a23, &ppv);
      v7 = 0;
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1);
        if ( v5 >= 0 )
        {
          SHRegSetBOOL(v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen", L"SlideshowEnabled", 0);
          SystemParametersInfoW(0xA9u, 0, 0, 1u);
          v7 = 1;
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
    else
    {
      v5 = CSetLockScreenImageTask::SetStream<Windows::Storage::Streams::IRandomAccessStream>(*(CSetLockScreenImageTask **)a1);
      v7 = 0;
    }
    if ( v5 >= 0 )
    {
      CSetLockScreenImageTask::s_SendChangeNotification();
      WinSqmIncrementDWORD(0, 8874, 1);
      WinSqmSetDWORD(0, 10453, 6);
      v12 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
      LODWORD(ppv) = v7 + 1;
      LockScreenTelemetry::SetImageByApiEvent<enum LockScreenTelemetry::SetImageApiType,unsigned short const *>(
        &ppv,
        &v12);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800adeb0  mov     [rsp-18h+arg_0], rbx
0x1800adeb5  mov     [rsp-18h+arg_8], rsi
0x1800adeba  mov     [rsp-18h+arg_10], r8
0x1800adebf  push    rbp
0x1800adec0  push    rdi
0x1800adec1  push    r15
0x1800adec3  mov     rbp, rsp
0x1800adec6  sub     rsp, 50h
0x1800adeca  mov     rdi, rdx
0x1800adecd  mov     rsi, rcx
0x1800aded0  mov     r15d, 1
0x1800aded6  mov     ebx, r15d
0x1800aded9  lea     rcx, POLID_NoChangingLockScreen
0x1800adee0  call    cs:__imp_SHWindowsPolicy
0x1800adee6  test    eax, eax
0x1800adee8  jnz     loc_1800AE05B
0x1800adeee  mov     [rbp+var_18], rdi
0x1800adef2  lea     rcx, [rbp+var_18]
0x1800adef6  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800adefb  nop
0x1800adefc  mov     [rbp+var_20], 0
0x1800adf04  mov     byte ptr [rbp+arg_10], 0
0x1800adf08  mov     rax, [rdi]
0x1800adf0b  mov     rbx, [rax]
0x1800adf0e  lea     rcx, [rbp+var_20]
0x1800adf12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800adf17  lea     r8, [rbp+var_20]
0x1800adf1b  lea     rdx, _GUID_29d25bfc_e5db_473e_9e19_cdb9c77393a4
0x1800adf22  mov     rcx, rdi
0x1800adf25  mov     rax, rbx
0x1800adf28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf2d  nop
0x1800adf2e  test    eax, eax
0x1800adf30  js      loc_1800ADFE7
0x1800adf36  mov     rcx, [rbp+var_20]
0x1800adf3a  mov     rax, [rcx]
0x1800adf3d  lea     rdx, [rbp+arg_10]
0x1800adf41  mov     rax, [rax+30h]
0x1800adf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adf4a  test    eax, eax
0x1800adf4c  js      loc_1800ADFE7
0x1800adf52  cmp     byte ptr [rbp+arg_10], 0
0x1800adf56  jz      loc_1800ADFE7
0x1800adf5c  mov     [rbp+arg_18], 0
0x1800adf64  lea     rcx, [rbp+arg_18]
0x1800adf68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800adf6d  lea     rax, [rbp+arg_18]
0x1800adf71  mov     [rsp+50h+ppv], rax; ppv
0x1800adf76  lea     r9, _GUID_fb37854f_513a_4ca8_9a06_4adab5968a23; riid
0x1800adf7d  mov     r8d, r15d; dwClsContext
0x1800adf80  xor     edx, edx; pUnkOuter
0x1800adf82  lea     rcx, CLSID_LockScreenStore; rclsid
0x1800adf89  call    cs:__imp_CoCreateInstance
0x1800adf8f  mov     ebx, eax
0x1800adf91  xor     edi, edi
0x1800adf93  test    eax, eax
0x1800adf95  js      short loc_1800ADFDC
0x1800adf97  mov     rcx, [rbp+arg_18]
0x1800adf9b  mov     rax, [rcx]
0x1800adf9e  mov     edx, r15d
0x1800adfa1  mov     rax, [rax+28h]
0x1800adfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adfaa  mov     ebx, eax
0x1800adfac  test    eax, eax
0x1800adfae  js      short loc_1800ADFDC
0x1800adfb0  xor     r9d, r9d; int
0x1800adfb3  lea     r8, aSlideshowenabl; "SlideshowEnabled"
0x1800adfba  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800adfc1  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800adfc6  mov     r9d, r15d; fWinIni
0x1800adfc9  xor     r8d, r8d; pvParam
0x1800adfcc  xor     edx, edx; uiParam
0x1800adfce  mov     ecx, 0A9h; uiAction
0x1800adfd3  call    cs:__imp_SystemParametersInfoW
0x1800adfd9  mov     edi, r15d
0x1800adfdc  lea     rcx, [rbp+arg_18]
0x1800adfe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800adfe5  jmp     short loc_1800ADFFE
0x1800adfe7  mov     r8, [rsi+8]
0x1800adfeb  mov     r8, [r8+8]
0x1800adfef  mov     rdx, rdi
0x1800adff2  mov     rcx, [rsi]; this
0x1800adff5  call    ??$SetStream@UIRandomAccessStream@Streams@Storage@Windows@@@CSetLockScreenImageTask@@QEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@PEBGPEBU_GUID@@@Z; CSetLockScreenImageTask::SetStream<Windows::Storage::Streams::IRandomAccessStream>(Windows::Storage::Streams::IRandomAccessStream *,ushort const *,_GUID const *)
0x1800adffa  mov     ebx, eax
0x1800adffc  xor     edi, edi
0x1800adffe  test    ebx, ebx
0x1800ae000  js      short loc_1800AE048
0x1800ae002  call    ?s_SendChangeNotification@CSetLockScreenImageTask@@SAXXZ; CSetLockScreenImageTask::s_SendChangeNotification(void)
0x1800ae007  mov     r8d, r15d
0x1800ae00a  mov     edx, 22AAh
0x1800ae00f  xor     ecx, ecx
0x1800ae011  call    cs:__imp_WinSqmIncrementDWORD
0x1800ae017  mov     edx, 28D5h
0x1800ae01c  xor     ecx, ecx
0x1800ae01e  lea     r8d, [rcx+6]
0x1800ae022  call    cs:__imp_WinSqmSetDWORD
0x1800ae028  mov     rax, [rsi+8]
0x1800ae02c  mov     rcx, [rax+8]
0x1800ae030  mov     [rbp+var_10], rcx
0x1800ae034  lea     eax, [rdi+1]
0x1800ae037  mov     dword ptr [rbp+arg_18], eax
0x1800ae03a  lea     rdx, [rbp+var_10]
0x1800ae03e  lea     rcx, [rbp+arg_18]
0x1800ae042  call    ??$SetImageByApiEvent@W4SetImageApiType@LockScreenTelemetry@@PEBG@LockScreenTelemetry@@SAX$$QEAW4SetImageApiType@0@$$QEAPEBG@Z; LockScreenTelemetry::SetImageByApiEvent<LockScreenTelemetry::SetImageApiType,ushort const *>(LockScreenTelemetry::SetImageApiType &&,ushort const * &&)
0x1800ae047  nop
0x1800ae048  lea     rcx, [rbp+var_20]
0x1800ae04c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ae051  nop
0x1800ae052  lea     rcx, [rbp+var_18]
0x1800ae056  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ae05b  mov     eax, ebx
0x1800ae05d  mov     rbx, [rsp+50h+arg_0]
0x1800ae062  mov     rsi, [rsp+50h+arg_8]
0x1800ae067  add     rsp, 50h
0x1800ae06b  pop     r15
0x1800ae06d  pop     rdi
0x1800ae06e  pop     rbp
0x1800ae06f  retn
```
