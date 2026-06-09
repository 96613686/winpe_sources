# CallerIdentity::VerifyWindowIsInSpecifiedApplication(HWND__ *,ushort const *,IUnknown *)

- ea: `0x14001d968`
- end: `0x14001dad5`
- name: `?VerifyWindowIsInSpecifiedApplication@CallerIdentity@@YAJPEAUHWND__@@PEBGPEAUIUnknown@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(CallerIdentity *this, const WCHAR *, const unsigned __int16 *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010f10`
- `0x14001d730`

## callees

- `0x14000e920`
- `0x140013600`
- `0x14001d968`
- `0x14001dadc`
- `0x14001f010`

## import_xrefs

- `USER32!GetWindowBand` at `0x14001d9b8`
- `USER32!GetWindowBand` at `0x14001d9b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001da52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001daba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001d990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001da52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001daba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001da37`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001da37`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001daa3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001daa3`

## pseudocode

```c
__int64 __fastcall CallerIdentity::VerifyWindowIsInSpecifiedApplication(
        CallerIdentity *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4)
{
  unsigned __int16 **v7; // r8
  signed int Error; // ebx
  __int64 (__fastcall *v9)(const unsigned __int16 *, GUID *, LPVOID *); // rbx
  HRESULT v10; // eax
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, CallerIdentity *, LPVOID *, _QWORD, _QWORD, _QWORD); // rbx
  LPVOID ppv; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  pv = 0;
  CoTaskMemFree(0);
  if ( CallerIdentity::GetImmersiveAppIdFromWindow(this, (HWND)&pv, v7) >= 0 )
    goto LABEL_12;
  v16 = 0;
  if ( (unsigned int)GetWindowBand(this, &v16) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( v16 != 1 )
    {
      Error = -2147024809;
      goto LABEL_13;
    }
    ppv = 0;
    if ( a3 )
    {
      v9 = **(__int64 (__fastcall ***)(const unsigned __int16 *, GUID *, LPVOID *))a3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      v10 = v9(a3, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      v10 = CoCreateInstance(
              &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
              0,
              3u,
              &GUID_de25675a_72de_44b4_9373_05170450c140,
              &ppv);
    }
    Error = v10;
    if ( v10 >= 0 )
    {
      v11 = ppv;
      v12 = *(__int64 (__fastcall **)(LPVOID, CallerIdentity *, LPVOID *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 40LL);
      CoTaskMemFree(pv);
      Error = v12(v11, this, &pv, 0, 0, 0);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    if ( Error >= 0 )
LABEL_12:
      Error = CompareStringOrdinal(a2, -1, (LPCWCH)pv, -1, 1) != 2 ? 0x80070005 : 0;
  }
LABEL_13:
  CoTaskMemFree(pv);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14001d968  mov     [rsp-18h+arg_0], rbx
0x14001d96d  mov     [rsp-18h+arg_8], rsi
0x14001d972  push    rbp
0x14001d973  push    rdi
0x14001d974  push    r14
0x14001d976  mov     rbp, rsp
0x14001d979  sub     rsp, 50h
0x14001d97d  mov     rsi, rcx
0x14001d980  mov     [rbp+pv], 0
0x14001d988  xor     ecx, ecx; pv
0x14001d98a  mov     rdi, r8
0x14001d98d  mov     r14, rdx
0x14001d990  call    cs:__imp_CoTaskMemFree
0x14001d996  lea     rdx, [rbp+pv]; HWND
0x14001d99a  mov     rcx, rsi; this
0x14001d99d  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x14001d9a2  test    eax, eax
0x14001d9a4  jns     loc_14001DA8E
0x14001d9aa  lea     rdx, [rbp+arg_18]
0x14001d9ae  mov     [rbp+arg_18], 0
0x14001d9b5  mov     rcx, rsi
0x14001d9b8  call    cs:__imp_GetWindowBand
0x14001d9be  test    eax, eax
0x14001d9c0  jnz     short loc_14001D9D1
0x14001d9c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001d9c7  mov     ebx, eax
0x14001d9c9  test    eax, eax
0x14001d9cb  js      loc_14001DAB6
0x14001d9d1  cmp     [rbp+arg_18], 1
0x14001d9d5  jz      short loc_14001D9E1
0x14001d9d7  mov     ebx, 80070057h
0x14001d9dc  jmp     loc_14001DAB6
0x14001d9e1  mov     [rbp+var_10], 0
0x14001d9e9  lea     rcx, [rbp+var_10]
0x14001d9ed  test    rdi, rdi
0x14001d9f0  jz      short loc_14001DA15
0x14001d9f2  mov     rax, [rdi]
0x14001d9f5  mov     rbx, [rax]
0x14001d9f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001d9fd  lea     r8, [rbp+var_10]
0x14001da01  mov     rcx, rdi
0x14001da04  lea     rdx, _GUID_de25675a_72de_44b4_9373_05170450c140
0x14001da0b  mov     rax, rbx
0x14001da0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da13  jmp     short loc_14001DA3D
0x14001da15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001da1a  xor     edx, edx; pUnkOuter
0x14001da1c  lea     rax, [rbp+var_10]
0x14001da20  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x14001da27  mov     [rsp+50h+ppv], rax; ppv
0x14001da2c  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x14001da33  lea     r8d, [rdx+3]; dwClsContext
0x14001da37  call    cs:__imp_CoCreateInstance
0x14001da3d  mov     ebx, eax
0x14001da3f  test    eax, eax
0x14001da41  js      short loc_14001DA81
0x14001da43  mov     rdi, [rbp+var_10]
0x14001da47  mov     rcx, [rbp+pv]; pv
0x14001da4b  mov     rax, [rdi]
0x14001da4e  mov     rbx, [rax+28h]
0x14001da52  call    cs:__imp_CoTaskMemFree
0x14001da58  xor     r9d, r9d
0x14001da5b  mov     [rsp+50h+var_28], 0
0x14001da64  lea     r8, [rbp+pv]
0x14001da68  mov     [rsp+50h+ppv], 0
0x14001da71  mov     rdx, rsi
0x14001da74  mov     rcx, rdi
0x14001da77  mov     rax, rbx
0x14001da7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da7f  mov     ebx, eax
0x14001da81  lea     rcx, [rbp+var_10]
0x14001da85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001da8a  test    ebx, ebx
0x14001da8c  js      short loc_14001DAB6
0x14001da8e  mov     r8, [rbp+pv]; lpString2
0x14001da92  or      edx, 0FFFFFFFFh; cchCount1
0x14001da95  mov     r9d, edx; cchCount2
0x14001da98  mov     dword ptr [rsp+50h+ppv], 1; bIgnoreCase
0x14001daa0  mov     rcx, r14; lpString1
0x14001daa3  call    cs:__imp_CompareStringOrdinal
0x14001daa9  sub     eax, 2
0x14001daac  neg     eax
0x14001daae  sbb     ebx, ebx
0x14001dab0  and     ebx, 80070005h
0x14001dab6  mov     rcx, [rbp+pv]; pv
0x14001daba  call    cs:__imp_CoTaskMemFree
0x14001dac0  mov     rsi, [rsp+50h+arg_8]
0x14001dac5  mov     eax, ebx
0x14001dac7  mov     rbx, [rsp+50h+arg_0]
0x14001dacc  add     rsp, 50h
0x14001dad0  pop     r14
0x14001dad2  pop     rdi
0x14001dad3  pop     rbp
0x14001dad4  retn
```
