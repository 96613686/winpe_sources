# UserOOBEController::s_RemoveUserOOBEMonitorTask(bool)

- ea: `0x180029890`
- end: `0x180029a72`
- name: `?s_RemoveUserOOBEMonitorTask@UserOOBEController@@CAJ_N@Z`
- size: `482`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024320`

## callees

- `0x1800032b0`
- `0x1800067b0`
- `0x180007134`
- `0x180024830`
- `0x180029890`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800298e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800298e3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800299dc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800299dc`

## string_xrefs

- `0x180029970`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180029a32`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserOOBEController::s_RemoveUserOOBEMonitorTask(char a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, const wchar_t *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v12; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[22]; // [rsp+42h] [rbp-BEh]
  _QWORD v15[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v16; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[22]; // [rsp+82h] [rbp-7Eh]
  __int16 v18; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+A2h] [rbp-5Eh]
  OLECHAR sz[40]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v12 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  v2 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v12);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 770;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v2,
      (int)ppv);
    goto LABEL_15;
  }
  LOWORD(v15[0]) = 0;
  *(_OWORD *)((char *)v15 + 2) = *(_OWORD *)v14;
  v15[2] = *(_QWORD *)&v14[14];
  v16 = 0;
  *(_OWORD *)v17 = *(_OWORD *)v14;
  *(_QWORD *)&v17[14] = *(_QWORD *)&v14[14];
  v18 = 0;
  *(_OWORD *)v19 = *(_OWORD *)v14;
  *(_QWORD *)&v19[14] = *(_QWORD *)&v14[14];
  v13 = 0;
  ppv = (LPVOID *)v15;
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *, __int16 *, __int16 *))(*(_QWORD *)v12 + 80LL))(
         v12,
         &v13,
         &v18,
         &v16);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 771;
    goto LABEL_5;
  }
  v11 = 0;
  v5 = v12;
  v6 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v12 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  v7 = v6(v5, L"\\", &v11);
  v3 = v7;
  if ( v7 < 0 )
  {
    v8 = 773;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v7,
      (int)v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
    goto LABEL_15;
  }
  StringFromGUID2(&GUID_b08ee1c0_1212_4416_8bd9_4a3b767ddfad, sz, 39);
  v7 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v11 + 120LL))(v11, sz, 0);
  v3 = v7;
  if ( v7 <= -2147024895 || (unsigned int)(v7 + 2147024892) <= 0x7FF8FFFB )
  {
    v8 = 780;
    goto LABEL_14;
  }
  if ( a1 )
    FireOOBEMonitorEvent();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v11);
  v3 = 0;
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return v3;
}

```

## disassembly

```asm
0x180029890  push    rbp
0x180029892  push    rbx
0x180029893  push    rsi
0x180029894  push    rdi
0x180029895  lea     rbp, [rsp-28h]
0x18002989a  sub     rsp, 128h
0x1800298a1  mov     rax, cs:__security_cookie
0x1800298a8  xor     rax, rsp
0x1800298ab  mov     [rbp+40h+var_30], rax
0x1800298af  mov     sil, cl
0x1800298b2  mov     [rsp+140h+var_108], 0
0x1800298bb  lea     rcx, [rsp+140h+var_108]
0x1800298c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800298c5  lea     rax, [rsp+140h+var_108]
0x1800298ca  mov     [rsp+140h+ppv], rax; ppv
0x1800298cf  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800298d6  xor     edx, edx; pUnkOuter
0x1800298d8  lea     r8d, [rdx+1]; dwClsContext
0x1800298dc  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x1800298e3  call    cs:__imp_CoCreateInstance
0x1800298e9  mov     ebx, eax
0x1800298eb  test    eax, eax
0x1800298ed  jns     short loc_1800298F6
0x1800298ef  mov     edx, 302h
0x1800298f4  jmp     short loc_180029970
0x1800298f6  mov     rcx, [rsp+140h+var_108]
0x1800298fb  xor     eax, eax
0x1800298fd  mov     word ptr [rsp+140h+var_E0], ax
0x180029902  movups  xmm1, xmmword ptr [rsp+140h+var_FE]
0x180029907  movups  xmmword ptr [rsp+140h+var_E0+2], xmm1
0x18002990c  movsd   xmm0, qword ptr [rsp+140h+var_FE+0Eh]
0x180029912  movsd   qword ptr [rsp+140h+var_E0+10h], xmm0
0x180029918  mov     [rbp+40h+var_C0], ax
0x18002991c  movups  xmmword ptr [rbp+40h+var_BE], xmm1
0x180029920  movsd   qword ptr [rbp+40h+var_BE+0Eh], xmm0
0x180029925  mov     [rbp+40h+var_A0], ax
0x180029929  movups  xmmword ptr [rbp+40h+var_9E], xmm1
0x18002992d  movsd   qword ptr [rbp+40h+var_9E+0Eh], xmm0
0x180029932  mov     [rsp+140h+var_100], ax
0x180029937  movups  xmmword ptr [rsp+140h+var_FE], xmm1
0x18002993c  movsd   qword ptr [rsp+140h+var_FE+0Eh], xmm0
0x180029942  mov     rax, [rcx]
0x180029945  lea     rdx, [rsp+140h+var_E0]
0x18002994a  mov     [rsp+140h+ppv], rdx; int
0x18002994f  lea     r9, [rbp+40h+var_C0]
0x180029953  lea     r8, [rbp+40h+var_A0]
0x180029957  lea     rdx, [rsp+140h+var_100]
0x18002995c  mov     rax, [rax+50h]
0x180029960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029965  mov     ebx, eax
0x180029967  test    eax, eax
0x180029969  jns     short loc_180029988
0x18002996b  mov     edx, 303h; void *
0x180029970  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029977  mov     r9d, eax; char *
0x18002997a  mov     rcx, [rbp+48h]; this
0x18002997e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029983  jmp     loc_180029A4E
0x180029988  mov     [rsp+140h+var_110], 0
0x180029991  mov     rdi, [rsp+140h+var_108]
0x180029996  mov     rax, [rdi]
0x180029999  mov     rbx, [rax+38h]
0x18002999d  lea     rcx, [rsp+140h+var_110]
0x1800299a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800299a7  lea     r8, [rsp+140h+var_110]
0x1800299ac  lea     rdx, pszSrc; "\\"
0x1800299b3  mov     rcx, rdi
0x1800299b6  mov     rax, rbx
0x1800299b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299be  mov     ebx, eax
0x1800299c0  test    eax, eax
0x1800299c2  jns     short loc_1800299CB
0x1800299c4  mov     edx, 305h
0x1800299c9  jmp     short loc_180029A2F
0x1800299cb  mov     r8d, 27h ; '''; cchMax
0x1800299d1  lea     rdx, [rbp+40h+sz]; lpsz
0x1800299d5  lea     rcx, _GUID_b08ee1c0_1212_4416_8bd9_4a3b767ddfad; rguid
0x1800299dc  call    cs:__imp_StringFromGUID2
0x1800299e2  mov     rcx, [rsp+140h+var_110]
0x1800299e7  mov     rax, [rcx]
0x1800299ea  xor     r8d, r8d
0x1800299ed  lea     rdx, [rbp+40h+sz]
0x1800299f1  mov     rax, [rax+78h]
0x1800299f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299fa  mov     ebx, eax
0x1800299fc  cmp     eax, 80070001h
0x180029a01  jle     short loc_180029A2A
0x180029a03  lea     ecx, [rax+7FF8FFFCh]
0x180029a09  cmp     ecx, 7FF8FFFBh
0x180029a0f  jbe     short loc_180029A2A
0x180029a11  test    sil, sil
0x180029a14  jz      short loc_180029A1C
0x180029a16  call    ?FireOOBEMonitorEvent@@YAJW4OOBEMonitorEvent@@@Z; FireOOBEMonitorEvent(OOBEMonitorEvent)
0x180029a1b  nop
0x180029a1c  lea     rcx, [rsp+140h+var_110]
0x180029a21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029a26  xor     ebx, ebx
0x180029a28  jmp     short loc_180029A4E
0x180029a2a  mov     edx, 30Ch; void *
0x180029a2f  mov     r9d, eax; char *
0x180029a32  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180029a39  mov     rcx, [rbp+48h]; this
0x180029a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a42  nop
0x180029a43  lea     rcx, [rsp+140h+var_110]
0x180029a48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029a4d  nop
0x180029a4e  lea     rcx, [rsp+140h+var_108]
0x180029a53  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029a58  mov     eax, ebx
0x180029a5a  mov     rcx, [rbp+40h+var_30]
0x180029a5e  xor     rcx, rsp; StackCookie
0x180029a61  call    __security_check_cookie
0x180029a66  add     rsp, 128h
0x180029a6d  pop     rdi
0x180029a6e  pop     rsi
0x180029a6f  pop     rbx
0x180029a70  pop     rbp
0x180029a71  retn
```
