# OSCleanup::CleanupEnvironment::StopCleanupTaskInternal(void)

- ea: `0x14001f358`
- end: `0x14001f65f`
- name: `?StopCleanupTaskInternal@CleanupEnvironment@OSCleanup@@CAJXZ`
- size: `775`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14001f300`

## callees

- `0x14001f358`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14001f560`
- `msvcrt!_wcsicmp` at `0x14001f560`
- `ole32!CoCreateInstance` at `0x14001f408`
- `ole32!CoCreateInstance` at `0x14001f408`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f526`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5fc`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f526`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5fc`

## string_xrefs

- `0x14001f3be`: `SetupCleanupTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 OSCleanup::CleanupEnvironment::StopCleanupTaskInternal(void)
{
  HRESULT v0; // ebx
  int v1; // edi
  __int64 v3; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v4; // [rsp+40h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v6; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v8[3]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+78h] [rbp-90h]
  __int128 v10; // [rsp+88h] [rbp-80h]
  __int64 v11; // [rsp+98h] [rbp-70h]
  __int128 v12; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v13; // [rsp+B8h] [rbp-50h]
  __int64 v14; // [rsp+C8h] [rbp-40h]
  __int128 v15; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v16; // [rsp+E8h] [rbp-20h]
  __int128 v17; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v18; // [rsp+108h] [rbp+0h]
  wchar_t String2[20]; // [rsp+118h] [rbp+10h] BYREF

  v14 = -2;
  ppv = 0;
  v6 = 0;
  *(_OWORD *)&v8[1] = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  bstrString = 0;
  LODWORD(v3) = 0;
  wcscpy(String2, L"SetupCleanupTask");
  LOWORD(v8[1]) = 1;
  v0 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v0 >= 0 )
  {
    v15 = *(_OWORD *)&v8[1];
    v16 = v9;
    v17 = *(_OWORD *)&v8[1];
    v18 = v9;
    v12 = *(_OWORD *)&v8[1];
    v13 = v9;
    v0 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, _QWORD *, __int128 *))(*(_QWORD *)ppv + 80LL))(
           ppv,
           &v12,
           &v17,
           &v8[1],
           &v15);
    if ( v0 >= 0 )
    {
      v0 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, 1, &v6);
      if ( v0 >= 0 )
      {
        v0 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 56LL))(v6, &v3);
        if ( v0 >= 0 )
        {
          v1 = 1;
          if ( (int)v3 >= 1 )
          {
            while ( 1 )
            {
              LOWORD(v10) = 3;
              DWORD2(v10) = v1;
              v4 = 0;
              v12 = v10;
              v13 = v11;
              v0 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v6 + 64LL))(v6, &v12, &v4);
              if ( v0 < 0 )
                break;
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              v0 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 56LL))(v4, &bstrString);
              if ( v0 < 0 )
              {
                if ( v4 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
                goto LABEL_23;
              }
              if ( !_wcsicmp(bstrString, String2) )
              {
                v0 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 96LL))(v4);
                if ( v4 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
                goto LABEL_23;
              }
              if ( v4 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
              if ( ++v1 > (int)v3 )
                goto LABEL_23;
            }
            if ( v4 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          }
        }
      }
    }
  }
LABEL_23:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14001f358  mov     rax, rsp
0x14001f35b  push    rbp
0x14001f35c  lea     rbp, [rax-48h]
0x14001f360  sub     rsp, 140h
0x14001f367  mov     [rbp+40h+var_80], 0FFFFFFFFFFFFFFFEh
0x14001f36f  mov     [rax+8], rbx
0x14001f373  mov     [rax+10h], rdi
0x14001f377  mov     [rax+18h], r14
0x14001f37b  mov     rax, cs:__security_cookie
0x14001f382  xor     rax, rsp
0x14001f385  mov     [rbp+40h+var_8], rax
0x14001f389  mov     [rsp+140h+var_F0], 0
0x14001f392  mov     [rsp+140h+var_F8], 0
0x14001f39b  xorps   xmm0, xmm0
0x14001f39e  xor     eax, eax
0x14001f3a0  movups  xmmword ptr [rsp+140h+var_E8+8], xmm0
0x14001f3a5  mov     [rsp+140h+var_D0], rax
0x14001f3aa  xorps   xmm1, xmm1
0x14001f3ad  movups  [rbp+40h+var_C0], xmm1
0x14001f3b1  mov     [rbp+40h+var_B0], rax
0x14001f3b5  mov     [rsp+140h+bstrString], rax
0x14001f3ba  mov     dword ptr [rsp+140h+var_110], eax
0x14001f3be  movups  xmm0, xmmword ptr cs:aSetupcleanupta; "SetupCleanupTask"
0x14001f3c5  movups  xmmword ptr [rbp+40h+String2], xmm0
0x14001f3c9  movups  xmm1, xmmword ptr cs:aSetupcleanupta+10h; "anupTask"
0x14001f3d0  movups  [rbp+40h+var_20], xmm1
0x14001f3d4  movzx   eax, word ptr cs:aSetupcleanupta+20h; ""
0x14001f3db  mov     [rbp+40h+var_10], ax
0x14001f3df  mov     r14d, 1
0x14001f3e5  mov     word ptr [rsp+140h+var_E8+8], r14w
0x14001f3eb  lea     rax, [rsp+140h+var_F0]
0x14001f3f0  mov     [rsp+140h+ppv], rax; ppv
0x14001f3f5  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14001f3fc  mov     r8d, r14d; dwClsContext
0x14001f3ff  xor     edx, edx; pUnkOuter
0x14001f401  lea     rcx, CLSID_TaskScheduler; rclsid
0x14001f408  call    cs:__imp_CoCreateInstance
0x14001f40f  nop     dword ptr [rax+rax+00h]
0x14001f414  mov     ebx, eax
0x14001f416  test    eax, eax
0x14001f418  js      loc_14001F5F2
0x14001f41e  movups  xmm1, xmmword ptr [rsp+140h+var_E8+8]
0x14001f423  movaps  [rbp+40h+var_70], xmm1
0x14001f427  movsd   xmm0, [rsp+140h+var_D0]
0x14001f42d  movsd   [rbp+40h+var_60], xmm0
0x14001f432  movaps  xmmword ptr [rsp+140h+var_E8+8], xmm1
0x14001f437  movsd   [rsp+140h+var_D0], xmm0
0x14001f43d  movaps  [rbp+40h+var_50], xmm1
0x14001f441  movsd   [rbp+40h+var_40], xmm0
0x14001f446  movaps  [rbp+40h+var_A0], xmm1
0x14001f44a  movsd   [rbp+40h+var_90], xmm0
0x14001f44f  mov     rcx, [rsp+140h+var_F0]
0x14001f454  mov     rax, [rcx]
0x14001f457  lea     rdx, [rbp+40h+var_70]
0x14001f45b  mov     [rsp+140h+ppv], rdx
0x14001f460  lea     r9, [rsp+140h+var_E8+8]
0x14001f465  lea     r8, [rbp+40h+var_50]
0x14001f469  lea     rdx, [rbp+40h+var_A0]
0x14001f46d  mov     rax, [rax+50h]
0x14001f471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f476  mov     ebx, eax
0x14001f478  test    eax, eax
0x14001f47a  js      loc_14001F5F2
0x14001f480  mov     rcx, [rsp+140h+var_F0]
0x14001f485  mov     rax, [rcx]
0x14001f488  lea     r8, [rsp+140h+var_F8]
0x14001f48d  mov     edx, r14d
0x14001f490  mov     rax, [rax+40h]
0x14001f494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f499  mov     ebx, eax
0x14001f49b  test    eax, eax
0x14001f49d  js      loc_14001F5F2
0x14001f4a3  mov     rcx, [rsp+140h+var_F8]
0x14001f4a8  mov     rax, [rcx]
0x14001f4ab  lea     rdx, [rsp+140h+var_110]
0x14001f4b0  mov     rax, [rax+38h]
0x14001f4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f4b9  mov     ebx, eax
0x14001f4bb  test    eax, eax
0x14001f4bd  js      loc_14001F5F2
0x14001f4c3  mov     edi, r14d
0x14001f4c6  cmp     dword ptr [rsp+140h+var_110], r14d
0x14001f4cb  jl      loc_14001F5F2
0x14001f4d1  mov     eax, 3
0x14001f4d6  mov     word ptr [rbp+40h+var_C0], ax
0x14001f4da  mov     dword ptr [rbp+40h+var_C0+8], edi
0x14001f4dd  mov     [rsp+140h+var_108], 0
0x14001f4e6  movups  xmm0, [rbp+40h+var_C0]
0x14001f4ea  movaps  [rbp+40h+var_A0], xmm0
0x14001f4ee  movsd   xmm0, [rbp+40h+var_B0]
0x14001f4f3  movsd   [rbp+40h+var_90], xmm0
0x14001f4f8  mov     rcx, [rsp+140h+var_F8]
0x14001f4fd  mov     rax, [rcx]
0x14001f500  lea     r8, [rsp+140h+var_108]
0x14001f505  lea     rdx, [rbp+40h+var_A0]
0x14001f509  mov     rax, [rax+40h]
0x14001f50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f512  mov     ebx, eax
0x14001f514  test    eax, eax
0x14001f516  js      loc_14001F5DB
0x14001f51c  mov     rcx, [rsp+140h+bstrString]; bstrString
0x14001f521  test    rcx, rcx
0x14001f524  jz      short loc_14001F53B
0x14001f526  call    cs:__imp_SysFreeString
0x14001f52d  nop     dword ptr [rax+rax+00h]
0x14001f532  mov     [rsp+140h+bstrString], 0
0x14001f53b  mov     rcx, [rsp+140h+var_108]
0x14001f540  mov     rax, [rcx]
0x14001f543  lea     rdx, [rsp+140h+bstrString]
0x14001f548  mov     rax, [rax+38h]
0x14001f54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f551  mov     ebx, eax
0x14001f553  test    eax, eax
0x14001f555  js      short loc_14001F5C2
0x14001f557  lea     rdx, [rbp+40h+String2]; String2
0x14001f55b  mov     rcx, [rsp+140h+bstrString]; String1
0x14001f560  call    cs:__imp__wcsicmp
0x14001f567  nop     dword ptr [rax+rax+00h]
0x14001f56c  test    eax, eax
0x14001f56e  jz      short loc_14001F596
0x14001f570  mov     rcx, [rsp+140h+var_108]
0x14001f575  test    rcx, rcx
0x14001f578  jz      short loc_14001F587
0x14001f57a  mov     rax, [rcx]
0x14001f57d  mov     rax, [rax+10h]
0x14001f581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f586  nop
0x14001f587  add     edi, r14d
0x14001f58a  cmp     edi, dword ptr [rsp+140h+var_110]
0x14001f58e  jle     loc_14001F4D1
0x14001f594  jmp     short loc_14001F5F2
0x14001f596  mov     rcx, [rsp+140h+var_108]
0x14001f59b  mov     rax, [rcx]
0x14001f59e  mov     rax, [rax+60h]
0x14001f5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5a7  mov     ebx, eax
0x14001f5a9  mov     rcx, [rsp+140h+var_108]
0x14001f5ae  test    rcx, rcx
0x14001f5b1  jz      short loc_14001F5C0
0x14001f5b3  mov     rax, [rcx]
0x14001f5b6  mov     rax, [rax+10h]
0x14001f5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5bf  nop
0x14001f5c0  jmp     short loc_14001F5F2
0x14001f5c2  mov     rcx, [rsp+140h+var_108]
0x14001f5c7  test    rcx, rcx
0x14001f5ca  jz      short loc_14001F5D9
0x14001f5cc  mov     rax, [rcx]
0x14001f5cf  mov     rax, [rax+10h]
0x14001f5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5d8  nop
0x14001f5d9  jmp     short loc_14001F5F2
0x14001f5db  mov     rcx, [rsp+140h+var_108]
0x14001f5e0  test    rcx, rcx
0x14001f5e3  jz      short loc_14001F5F2
0x14001f5e5  mov     rax, [rcx]
0x14001f5e8  mov     rax, [rax+10h]
0x14001f5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f5f1  nop
0x14001f5f2  mov     rcx, [rsp+140h+bstrString]; bstrString
0x14001f5f7  test    rcx, rcx
0x14001f5fa  jz      short loc_14001F609
0x14001f5fc  call    cs:__imp_SysFreeString
0x14001f603  nop     dword ptr [rax+rax+00h]
0x14001f608  nop
0x14001f609  mov     rcx, [rsp+140h+var_F8]
0x14001f60e  test    rcx, rcx
0x14001f611  jz      short loc_14001F620
0x14001f613  mov     rax, [rcx]
0x14001f616  mov     rax, [rax+10h]
0x14001f61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f61f  nop
0x14001f620  mov     rcx, [rsp+140h+var_F0]
0x14001f625  test    rcx, rcx
0x14001f628  jz      short loc_14001F637
0x14001f62a  mov     rax, [rcx]
0x14001f62d  mov     rax, [rax+10h]
0x14001f631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f636  nop
0x14001f637  mov     eax, ebx
0x14001f639  mov     rcx, [rbp+40h+var_8]
0x14001f63d  xor     rcx, rsp; StackCookie
0x14001f640  call    __security_check_cookie
0x14001f645  lea     r11, [rsp+140h+var_s0]
0x14001f64d  mov     rbx, [r11+10h]
0x14001f651  mov     rdi, [r11+18h]
0x14001f655  mov     r14, [r11+20h]
0x14001f659  mov     rsp, r11
0x14001f65c  pop     rbp
0x14001f65d  retn
```
