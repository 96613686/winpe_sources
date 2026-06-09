# GetPTITaskFolder(void)

- ea: `0x18003331c`
- end: `0x18003346b`
- name: `?GetPTITaskFolder@@YA?AV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@XZ`
- size: `335`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800338b4`
- `0x180033af0`

## callees

- `0x18002008c`
- `0x18003331c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033362`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033362`

## string_xrefs

- `0x18003342f`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033444`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x180033459`: `onecoreuap\enduser\winstore\pushtoinstall\lib\tasks.cpp`
- `0x1800333e2`: `\Microsoft\Windows\PushToInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall GetPTITaskFolder(_QWORD *a1)
{
  HRESULT v2; // eax
  int v3; // eax
  int v4; // eax
  LPVOID v5; // rcx
  int ppv; // [rsp+20h] [rbp-49h]
  int v8[4]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v9; // [rsp+50h] [rbp-19h]
  __int128 v10; // [rsp+60h] [rbp-9h] BYREF
  __int64 v11; // [rsp+70h] [rbp+7h]
  __int128 v12; // [rsp+80h] [rbp+17h] BYREF
  __int64 v13; // [rsp+90h] [rbp+27h]
  __int128 v14; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v15; // [rsp+B0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPVOID v17; // [rsp+D8h] [rbp+6Fh] BYREF

  v17 = 0;
  v2 = CoCreateInstance(
         &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
         0,
         1u,
         &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
         &v17);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  *(_OWORD *)v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v17 + 80LL))(
         v17,
         &v14,
         &v12,
         &v10);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v3,
      (int)v8);
  *a1 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD *))(*(_QWORD *)v17 + 56LL))(
         v17,
         L"\\Microsoft\\Windows\\PushToInstall",
         a1);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\tasks.cpp",
      (const char *)(unsigned int)v4,
      (int)v8);
  v5 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18003331c  mov     [rsp-8+arg_10], rbx
0x180033321  mov     [rsp-8+arg_0], rcx
0x180033326  push    rbp
0x180033327  lea     rbp, [rsp-57h]
0x18003332c  sub     rsp, 0C0h
0x180033333  mov     rbx, rcx
0x180033336  mov     [rbp+57h+var_90], 0
0x18003333d  mov     [rbp+57h+arg_8], 0
0x180033345  lea     rax, [rbp+57h+arg_8]
0x180033349  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x18003334e  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180033355  xor     edx, edx; pUnkOuter
0x180033357  lea     r8d, [rdx+1]; dwClsContext
0x18003335b  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180033362  call    cs:__imp_CoCreateInstance
0x180033368  mov     rcx, [rbp+5Fh]; this
0x18003336c  test    eax, eax
0x18003336e  js      loc_180033441
0x180033374  xorps   xmm1, xmm1
0x180033377  xor     eax, eax
0x180033379  mov     rcx, [rbp+57h+arg_8]
0x18003337d  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x180033381  mov     [rbp+57h+var_70], rax
0x180033385  movaps  [rbp+57h+var_60], xmm1
0x180033389  mov     [rbp+57h+var_50], rax
0x18003338d  movaps  [rbp+57h+var_40], xmm1
0x180033391  mov     [rbp+57h+var_30], rax
0x180033395  movaps  [rbp+57h+var_20], xmm1
0x180033399  mov     [rbp+57h+var_10], rax
0x18003339d  mov     rax, [rcx]
0x1800333a0  lea     rdx, [rbp+57h+var_80]
0x1800333a4  mov     qword ptr [rsp+0C0h+ppv], rdx; int
0x1800333a9  lea     r9, [rbp+57h+var_60]
0x1800333ad  lea     r8, [rbp+57h+var_40]
0x1800333b1  lea     rdx, [rbp+57h+var_20]
0x1800333b5  mov     rax, [rax+50h]
0x1800333b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333be  mov     rcx, [rbp+5Fh]; this
0x1800333c2  test    eax, eax
0x1800333c4  js      loc_180033456
0x1800333ca  mov     qword ptr [rbx], 0
0x1800333d1  mov     [rbp+57h+var_90], 1
0x1800333d8  mov     rcx, [rbp+57h+arg_8]
0x1800333dc  mov     rax, [rcx]
0x1800333df  mov     r8, rbx
0x1800333e2  lea     rdx, aMicrosoftWindo_2; "\\Microsoft\\Windows\\PushToInstall"
0x1800333e9  mov     rax, [rax+38h]
0x1800333ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333f2  mov     rcx, [rbp+5Fh]; this
0x1800333f6  test    eax, eax
0x1800333f8  js      short loc_18003342C
0x1800333fa  mov     rcx, [rbp+57h+arg_8]
0x1800333fe  test    rcx, rcx
0x180033401  jz      short loc_180033418
0x180033403  mov     [rbp+57h+arg_8], 0
0x18003340b  mov     rax, [rcx]
0x18003340e  mov     rax, [rax+10h]
0x180033412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033417  nop
0x180033418  mov     rax, rbx
0x18003341b  mov     rbx, [rsp+0C0h+arg_10]
0x180033423  add     rsp, 0C0h
0x18003342a  pop     rbp
0x18003342b  retn
0x18003342c  mov     r9d, eax; char *
0x18003342f  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033436  mov     edx, 33h ; '3'; void *
0x18003343b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033441  mov     r9d, eax; char *
0x180033444  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003344b  mov     edx, 2Dh ; '-'; void *
0x180033450  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180033456  mov     r9d, eax; char *
0x180033459  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180033460  mov     edx, 30h ; '0'; void *
0x180033465  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
