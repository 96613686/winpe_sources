# ServiceManager::EnableMapsUpdateTask(void)

- ea: `0x1800155ec`
- end: `0x1800157cb`
- name: `?EnableMapsUpdateTask@ServiceManager@@AEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180015898`

## callees

- `0x1800117c0`
- `0x180011b5c`
- `0x1800155ec`
- `0x1800171d0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001564d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001564d`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015669`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015669`
- `OLEAUT32!__imp_SysFreeString` at `0x18001570a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001570a`
- `OLEAUT32!__imp_VariantInit` at `0x180015621`
- `OLEAUT32!__imp_VariantInit` at `0x180015621`

## string_xrefs

- `0x180015662`: `ServiceManager::EnableMapsUpdateTask`
- `0x180015739`: `\Microsoft\Windows\Maps\MapsUpdateTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::EnableMapsUpdateTask(ServiceManager *this)
{
  unsigned int v2; // esi
  HRESULT v3; // eax
  int v4; // r8d
  HRESULT v5; // ecx
  unsigned __int64 v6; // rdx
  LPVOID v7; // rdi
  __int64 (__fastcall *v8)(LPVOID, _QWORD, __int64 *); // rbx
  const unsigned __int16 *v9; // rdx
  ATL::CComBSTR *v10; // rax
  int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, __int64 *); // rbx
  __int64 v15; // [rsp+30h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-61h] BYREF
  VARIANTARG v17; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG v18; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG v19; // [rsp+90h] [rbp-9h] BYREF
  VARIANTARG v20; // [rsp+B0h] [rbp+17h] BYREF
  BSTR bstrString; // [rsp+108h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+110h] [rbp+77h] BYREF
  __int64 v23; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = 0;
  ppv = 0;
  v15 = 0;
  v23 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&ppv);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v3 < 0 )
  {
    v4 = 3066;
LABEL_3:
    v5 = v3;
LABEL_4:
    v2 = ZTraceReportOrigination(v5, "ServiceManager::EnableMapsUpdateTask", v4, this);
    goto LABEL_14;
  }
  v17 = pvarg;
  v18 = pvarg;
  v19 = pvarg;
  v20 = pvarg;
  v3 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v20,
         &v19,
         &v18,
         &v17);
  if ( v3 < 0 )
  {
    v4 = 3069;
    goto LABEL_3;
  }
  v7 = ppv;
  v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 56LL);
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v15);
  v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v9);
  v11 = v8(v7, *(_QWORD *)v10, &v15);
  SysFreeString(bstrString);
  if ( v11 < 0 )
  {
    v4 = 3072;
    v5 = v11;
    goto LABEL_4;
  }
  v12 = v15;
  v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v15 + 104LL);
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v23);
  v3 = v13(v12, L"\\Microsoft\\Windows\\Maps\\MapsUpdateTask", &v23);
  if ( v3 < 0 )
  {
    v4 = 3075;
    goto LABEL_3;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 88LL))(v23, 0xFFFFFFFFLL);
  if ( v3 < 0 )
  {
    v4 = 3078;
    goto LABEL_3;
  }
  *((_BYTE *)this + 4316) = 1;
LABEL_14:
  if ( v2 == -2147024891 )
  {
    v2 = -2080374780;
    LODWORD(bstrString) = -2080374780;
    OfflineMapsTelemetry::MapsCacheAccessDenied<long &>((int *)&bstrString, v6);
  }
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(&ppv);
  return v2;
}

```

## disassembly

```asm
0x1800155ec  push    rbp
0x1800155ee  push    rbx
0x1800155ef  push    rsi
0x1800155f0  push    rdi
0x1800155f1  push    r14
0x1800155f3  lea     rbp, [rsp-37h]
0x1800155f8  sub     rsp, 0D0h
0x1800155ff  mov     r14, rcx
0x180015602  xor     esi, esi
0x180015604  mov     [rbp+57h+arg_10], rsi
0x180015608  mov     [rbp+57h+var_C0], rsi
0x18001560c  mov     [rbp+57h+arg_18], rsi
0x180015610  xorps   xmm0, xmm0
0x180015613  xor     eax, eax
0x180015615  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180015619  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001561d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180015621  call    cs:__imp_VariantInit
0x180015627  lea     rcx, [rbp+57h+arg_10]
0x18001562b  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x180015630  lea     rax, [rbp+57h+arg_10]
0x180015634  mov     [rsp+0F0h+ppv], rax; ppv
0x180015639  lea     r9, IID_ITaskService; riid
0x180015640  xor     edx, edx; pUnkOuter
0x180015642  lea     r8d, [rsi+1]; dwClsContext
0x180015646  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001564d  call    cs:__imp_CoCreateInstance
0x180015653  test    eax, eax
0x180015655  jns     short loc_180015676
0x180015657  mov     r8d, 0BFAh
0x18001565d  mov     ecx, eax
0x18001565f  mov     r9, r14
0x180015662  lea     rdx, aServicemanager_2; "ServiceManager::EnableMapsUpdateTask"
0x180015669  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001566f  mov     esi, eax
0x180015671  jmp     loc_180015784
0x180015676  mov     rcx, [rbp+57h+arg_10]
0x18001567a  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001567e  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180015683  movaps  [rbp+57h+var_A0], xmm1
0x180015687  movsd   [rbp+57h+var_90], xmm0
0x18001568c  movaps  [rbp+57h+var_80], xmm1
0x180015690  movsd   [rbp+57h+var_70], xmm0
0x180015695  movaps  [rbp+57h+var_60], xmm1
0x180015699  movsd   [rbp+57h+var_50], xmm0
0x18001569e  movaps  [rbp+57h+var_40], xmm1
0x1800156a2  movsd   [rbp+57h+var_30], xmm0
0x1800156a7  mov     rax, [rcx]
0x1800156aa  lea     rdx, [rbp+57h+var_A0]
0x1800156ae  mov     [rsp+0F0h+ppv], rdx
0x1800156b3  lea     r9, [rbp+57h+var_80]
0x1800156b7  lea     r8, [rbp+57h+var_60]
0x1800156bb  lea     rdx, [rbp+57h+var_40]
0x1800156bf  mov     rax, [rax+50h]
0x1800156c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c8  test    eax, eax
0x1800156ca  jns     short loc_1800156D4
0x1800156cc  mov     r8d, 0BFDh
0x1800156d2  jmp     short loc_18001565D
0x1800156d4  mov     rdi, [rbp+57h+arg_10]
0x1800156d8  mov     rax, [rdi]
0x1800156db  mov     rbx, [rax+38h]
0x1800156df  lea     rcx, [rbp+57h+var_C0]
0x1800156e3  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x1800156e8  lea     rcx, [rbp+57h+bstrString]; this
0x1800156ec  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800156f1  nop
0x1800156f2  lea     r8, [rbp+57h+var_C0]
0x1800156f6  mov     rdx, [rax]
0x1800156f9  mov     rcx, rdi
0x1800156fc  mov     rax, rbx
0x1800156ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015704  mov     ebx, eax
0x180015706  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001570a  call    cs:__imp_SysFreeString
0x180015710  test    ebx, ebx
0x180015712  jns     short loc_180015721
0x180015714  mov     r8d, 0C00h
0x18001571a  mov     ecx, ebx
0x18001571c  jmp     loc_18001565F
0x180015721  mov     rdi, [rbp+57h+var_C0]
0x180015725  mov     rax, [rdi]
0x180015728  mov     rbx, [rax+68h]
0x18001572c  lea     rcx, [rbp+57h+arg_18]
0x180015730  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x180015735  lea     r8, [rbp+57h+arg_18]
0x180015739  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Maps\\MapsUpdateT"...
0x180015740  mov     rcx, rdi
0x180015743  mov     rax, rbx
0x180015746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001574b  test    eax, eax
0x18001574d  jns     short loc_18001575A
0x18001574f  mov     r8d, 0C03h
0x180015755  jmp     loc_18001565D
0x18001575a  mov     rcx, [rbp+57h+arg_18]
0x18001575e  mov     rax, [rcx]
0x180015761  or      edx, 0FFFFFFFFh
0x180015764  mov     rax, [rax+58h]
0x180015768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001576d  test    eax, eax
0x18001576f  jns     short loc_18001577C
0x180015771  mov     r8d, 0C06h
0x180015777  jmp     loc_18001565D
0x18001577c  mov     byte ptr [r14+10DCh], 1
0x180015784  cmp     esi, 80070005h
0x18001578a  jnz     short loc_18001579E
0x18001578c  mov     esi, 84000004h
0x180015791  mov     dword ptr [rbp+57h+bstrString], esi
0x180015794  lea     rcx, [rbp+57h+bstrString]
0x180015798  call    ??$MapsCacheAccessDenied@AEAJ@OfflineMapsTelemetry@@SAXAEAJ@Z; OfflineMapsTelemetry::MapsCacheAccessDenied<long &>(long &)
0x18001579d  nop
0x18001579e  lea     rcx, [rbp+57h+arg_18]
0x1800157a2  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x1800157a7  nop
0x1800157a8  lea     rcx, [rbp+57h+var_C0]
0x1800157ac  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x1800157b1  nop
0x1800157b2  lea     rcx, [rbp+57h+arg_10]
0x1800157b6  call    ?InternalRelease@?$ComPtr@UIClientProxyResolver@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IClientProxyResolver>::InternalRelease(void)
0x1800157bb  mov     eax, esi
0x1800157bd  add     rsp, 0D0h
0x1800157c4  pop     r14
0x1800157c6  pop     rdi
0x1800157c7  pop     rsi
0x1800157c8  pop     rbx
0x1800157c9  pop     rbp
0x1800157ca  retn
```
