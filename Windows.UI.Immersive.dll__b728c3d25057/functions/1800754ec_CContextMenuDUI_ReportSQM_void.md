# CContextMenuDUI::ReportSQM(void)

- ea: `0x1800754ec`
- end: `0x1800756bc`
- name: `?ReportSQM@CContextMenuDUI@@QEAAXXZ`
- size: `464`
- prototype: `void __fastcall(CContextMenuDUI *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071260`
- `0x1800714f4`

## callees

- `0x18000a910`
- `0x180013244`
- `0x180050ba0`
- `0x1800754ec`
- `0x1800d8494`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800755c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800755c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180075552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180075552`
- `ntdll!WinSqmAddToStreamEx` at `0x180075689`
- `ntdll!WinSqmAddToStreamEx` at `0x180075689`
- `ntdll!WinSqmIsOptedIn` at `0x180075517`
- `ntdll!WinSqmIsOptedIn` at `0x180075517`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007559a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007559a`

## pseudocode

```c
void __fastcall CContextMenuDUI::ReportSQM(CContextMenuDUI *this)
{
  HANDLE CurrentProcess; // rax
  unsigned __int16 **v3; // r8
  HRESULT v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  __int64 v8; // rcx
  int v9; // eax
  LPVOID ppv; // [rsp+40h] [rbp-29h] BYREF
  __int64 v11; // [rsp+48h] [rbp-21h] BYREF
  __int64 v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  _DWORD v14[2]; // [rsp+60h] [rbp-9h] BYREF
  const wchar_t *v15; // [rsp+68h] [rbp-1h]
  int v16; // [rsp+70h] [rbp+7h]
  int v17; // [rsp+74h] [rbp+Bh]
  const wchar_t *v18; // [rsp+78h] [rbp+Fh]
  int v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+84h] [rbp+1Bh]
  int v21; // [rsp+88h] [rbp+1Fh]
  int v22; // [rsp+8Ch] [rbp+23h]
  int v23; // [rsp+90h] [rbp+27h]
  int v24; // [rsp+94h] [rbp+2Bh]
  int v25; // [rsp+98h] [rbp+2Fh]
  int v26; // [rsp+9Ch] [rbp+33h]

  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    v11 = 0;
    v12 = 0;
    v13 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
    v12 = -1;
    v13 = -1;
    CurrentProcess = GetCurrentProcess();
    if ( (int)CallerIdentity::GetProcessAppId(CurrentProcess, &v11, v3) >= 0 )
      goto LABEL_6;
    ppv = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    v4 = CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_de25675a_72de_44b4_9373_05170450c140, &ppv);
    if ( v4 >= 0 )
    {
      v5 = ppv;
      v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 48LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
      v12 = -1;
      v13 = -1;
      CurrentProcessId = GetCurrentProcessId();
      v4 = v6(v5, CurrentProcessId, &v11, 0, 0, 0);
    }
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    if ( v4 >= 0 )
    {
LABEL_6:
      v8 = *((_QWORD *)this + 18);
      LODWORD(ppv) = 0;
      if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 56LL))(v8, &ppv) >= 0 )
      {
        v22 = 0;
        v14[0] = 16;
        v15 = L"(null)";
        v18 = L"(null)";
        v16 = 16;
        v20 = 1;
        v14[1] = 2;
        v17 = 2;
        v24 = 1;
        v19 = 16;
        v21 = (int)ppv;
        v9 = *((_DWORD *)this + 40);
        v23 = 16;
        v26 = 0;
        v25 = v9;
        WinSqmAddToStreamEx(0, 8712, 4, v14, 0);
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v11);
  }
}

```

## disassembly

```asm
0x1800754ec  mov     [rsp-8+arg_8], rbx
0x1800754f1  mov     [rsp-8+arg_10], rsi
0x1800754f6  push    rbp
0x1800754f7  push    rdi
0x1800754f8  push    r15
0x1800754fa  lea     rbp, [rsp-47h]
0x1800754ff  sub     rsp, 0B0h
0x180075506  mov     rax, cs:__security_cookie
0x18007550d  xor     rax, rsp
0x180075510  mov     [rbp+57h+var_20], rax
0x180075514  mov     rsi, rcx
0x180075517  call    cs:__imp_WinSqmIsOptedIn
0x18007551d  test    eax, eax
0x18007551f  jz      loc_180075698
0x180075525  lea     rcx, [rbp+57h+var_78]
0x180075529  mov     [rbp+57h+var_78], 0
0x180075531  mov     [rbp+57h+var_70], 0
0x180075539  mov     [rbp+57h+var_68], 0
0x180075541  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075546  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007554a  mov     [rbp+57h+var_70], r15
0x18007554e  mov     [rbp+57h+var_68], r15
0x180075552  call    cs:__imp_GetCurrentProcess
0x180075558  mov     rcx, rax; ProcessHandle
0x18007555b  lea     rdx, [rbp+57h+var_78]; void *
0x18007555f  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180075564  test    eax, eax
0x180075566  jns     loc_180075601
0x18007556c  lea     rcx, [rbp+57h+var_80]
0x180075570  mov     [rbp+57h+var_80], 0
0x180075578  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18007557d  lea     rax, [rbp+57h+var_80]
0x180075581  xor     edx, edx; pUnkOuter
0x180075583  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x18007558a  mov     [rsp+0C0h+ppv], rax; ppv
0x18007558f  lea     r8d, [r15+4]; dwClsContext
0x180075593  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x18007559a  call    cs:__imp_CoCreateInstance
0x1800755a0  mov     ebx, eax
0x1800755a2  test    eax, eax
0x1800755a4  js      short loc_1800755F0
0x1800755a6  mov     rdi, [rbp+57h+var_80]
0x1800755aa  lea     rcx, [rbp+57h+var_78]
0x1800755ae  mov     rax, [rdi]
0x1800755b1  mov     rbx, [rax+30h]
0x1800755b5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800755ba  mov     [rbp+57h+var_70], r15
0x1800755be  mov     [rbp+57h+var_68], r15
0x1800755c2  call    cs:__imp_GetCurrentProcessId
0x1800755c8  mov     [rsp+0C0h+var_98], 0
0x1800755d1  lea     r8, [rbp+57h+var_78]
0x1800755d5  mov     edx, eax
0x1800755d7  mov     [rsp+0C0h+ppv], 0
0x1800755e0  mov     rax, rbx
0x1800755e3  xor     r9d, r9d
0x1800755e6  mov     rcx, rdi
0x1800755e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800755ee  mov     ebx, eax
0x1800755f0  lea     rcx, [rbp+57h+var_80]
0x1800755f4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800755f9  test    ebx, ebx
0x1800755fb  js      loc_18007568F
0x180075601  mov     rcx, [rsi+90h]
0x180075608  lea     rdx, [rbp+57h+var_80]
0x18007560c  mov     dword ptr [rbp+57h+var_80], 0
0x180075613  mov     rax, [rcx]
0x180075616  mov     rax, [rax+38h]
0x18007561a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007561f  test    eax, eax
0x180075621  js      short loc_18007568F
0x180075623  mov     edx, 10h
0x180075628  mov     [rbp+57h+var_34], 0
0x18007562f  lea     rcx, aNull; "(null)"
0x180075636  mov     [rbp+57h+var_60], edx
0x180075639  mov     [rbp+57h+var_58], rcx
0x18007563d  lea     r9, [rbp+57h+var_60]
0x180075641  mov     [rbp+57h+var_48], rcx
0x180075645  lea     ecx, [rdx-0Fh]
0x180075648  mov     [rbp+57h+var_50], edx
0x18007564b  lea     eax, [rdx-0Eh]
0x18007564e  mov     [rbp+57h+var_3C], ecx
0x180075651  mov     [rbp+57h+var_5C], eax
0x180075654  mov     [rbp+57h+var_4C], eax
0x180075657  mov     eax, dword ptr [rbp+57h+var_80]
0x18007565a  mov     [rbp+57h+var_2C], ecx
0x18007565d  xor     ecx, ecx
0x18007565f  mov     [rbp+57h+var_40], edx
0x180075662  mov     [rbp+57h+var_38], eax
0x180075665  mov     eax, [rsi+0A0h]
0x18007566b  mov     [rbp+57h+var_30], edx
0x18007566e  lea     r8d, [rcx+4]
0x180075672  mov     edx, 2208h
0x180075677  mov     [rbp+57h+var_24], 0
0x18007567e  mov     [rbp+57h+var_28], eax
0x180075681  mov     dword ptr [rsp+0C0h+ppv], 0
0x180075689  call    cs:__imp_WinSqmAddToStreamEx
0x18007568f  lea     rcx, [rbp+57h+var_78]
0x180075693  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075698  mov     rcx, [rbp+57h+var_20]
0x18007569c  xor     rcx, rsp; StackCookie
0x18007569f  call    __security_check_cookie
0x1800756a4  lea     r11, [rsp+0C0h+var_10]
0x1800756ac  mov     rbx, [r11+28h]
0x1800756b0  mov     rsi, [r11+30h]
0x1800756b4  mov     rsp, r11
0x1800756b7  pop     r15
0x1800756b9  pop     rdi
0x1800756ba  pop     rbp
0x1800756bb  retn
```
