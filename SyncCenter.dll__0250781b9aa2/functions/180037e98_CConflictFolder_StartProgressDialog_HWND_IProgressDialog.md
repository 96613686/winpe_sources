# CConflictFolder::_StartProgressDialog(HWND__ *,IProgressDialog * *)

- ea: `0x180037e98`
- end: `0x180038098`
- name: `?_StartProgressDialog@CConflictFolder@@AEAAJPEAUHWND__@@PEAPEAUIProgressDialog@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(CConflictFolder *this, HWND, LPVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035358`

## callees

- `0x180037e98`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037f26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037f63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037faf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037ff8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037f26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037f63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037faf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180037ff8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037eff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180037eff`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_StartProgressDialog(CConflictFolder *this, HWND a2, LPVOID *a3)
{
  HRESULT v5; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[512]; // [rsp+40h] [rbp-C0h] BYREF

  *a3 = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_ProgressDialog, 0, 1u, &GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4, &ppv);
  if ( v5 >= 0 )
  {
    LoadStringW(g_hmodThisDll, 0x157Cu, Buffer, 512);
    v5 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 40LL))(ppv, Buffer);
    if ( v5 < 0
      || (LoadStringW(g_hmodThisDll, 0x157Du, Buffer, 512),
          v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, WCHAR *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
                 ppv,
                 1,
                 Buffer,
                 1,
                 0),
          v5 < 0)
      || (LoadStringW(g_hmodThisDll, 0x157Eu, Buffer, 512),
          v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, WCHAR *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
                 ppv,
                 2,
                 Buffer,
                 1,
                 0),
          v5 < 0)
      || (LoadStringW(g_hmodThisDll, 0x157Fu, Buffer, 512),
          v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, WCHAR *, __int64, _QWORD))(*(_QWORD *)ppv + 80LL))(
                 ppv,
                 3,
                 Buffer,
                 1,
                 0),
          v5 < 0)
      || (v5 = (*(__int64 (__fastcall **)(LPVOID, HWND, _QWORD, __int64, _QWORD))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 a2,
                 0,
                 41,
                 0),
          v5 < 0) )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      *a3 = ppv;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180037e98  mov     [rsp-8+arg_0], rbx
0x180037e9d  mov     [rsp-8+arg_18], rsi
0x180037ea2  push    rbp
0x180037ea3  push    rdi
0x180037ea4  push    r15
0x180037ea6  lea     rbp, [rsp-350h]
0x180037eae  sub     rsp, 450h
0x180037eb5  mov     rax, cs:__security_cookie
0x180037ebc  xor     rax, rsp
0x180037ebf  mov     [rbp+360h+var_20], rax
0x180037ec6  mov     rdi, r8
0x180037ec9  mov     qword ptr [r8], 0
0x180037ed0  mov     rsi, rdx
0x180037ed3  mov     [rsp+460h+var_430], 0
0x180037edc  lea     rax, [rsp+460h+var_430]
0x180037ee1  mov     r15d, 1
0x180037ee7  mov     r8d, r15d; dwClsContext
0x180037eea  mov     [rsp+460h+ppv], rax; ppv
0x180037eef  lea     r9, _GUID_ebbc7c04_315e_11d2_b62f_006097df5bd4; riid
0x180037ef6  xor     edx, edx; pUnkOuter
0x180037ef8  lea     rcx, CLSID_ProgressDialog; rclsid
0x180037eff  call    cs:__imp_CoCreateInstance
0x180037f05  mov     ebx, eax
0x180037f07  test    eax, eax
0x180037f09  js      loc_18003806F
0x180037f0f  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180037f16  lea     r8, [rsp+460h+Buffer]; lpBuffer
0x180037f1b  mov     r9d, 200h; cchBufferMax
0x180037f21  mov     edx, 157Ch; uID
0x180037f26  call    cs:__imp_LoadStringW
0x180037f2c  mov     rcx, [rsp+460h+var_430]
0x180037f31  lea     rdx, [rsp+460h+Buffer]
0x180037f36  mov     rax, [rcx]
0x180037f39  mov     rax, [rax+28h]
0x180037f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f42  mov     ebx, eax
0x180037f44  test    eax, eax
0x180037f46  js      loc_18003805E
0x180037f4c  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180037f53  lea     r8, [rsp+460h+Buffer]; lpBuffer
0x180037f58  mov     r9d, 200h; cchBufferMax
0x180037f5e  mov     edx, 157Dh; uID
0x180037f63  call    cs:__imp_LoadStringW
0x180037f69  mov     rcx, [rsp+460h+var_430]
0x180037f6e  lea     r8, [rsp+460h+Buffer]
0x180037f73  mov     r9d, r15d
0x180037f76  mov     [rsp+460h+ppv], 0
0x180037f7f  mov     edx, r15d
0x180037f82  mov     rax, [rcx]
0x180037f85  mov     rax, [rax+50h]
0x180037f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f8e  mov     ebx, eax
0x180037f90  test    eax, eax
0x180037f92  js      loc_18003805E
0x180037f98  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180037f9f  lea     r8, [rsp+460h+Buffer]; lpBuffer
0x180037fa4  mov     r9d, 200h; cchBufferMax
0x180037faa  mov     edx, 157Eh; uID
0x180037faf  call    cs:__imp_LoadStringW
0x180037fb5  mov     rcx, [rsp+460h+var_430]
0x180037fba  lea     r8, [rsp+460h+Buffer]
0x180037fbf  mov     r9d, r15d
0x180037fc2  mov     [rsp+460h+ppv], 0
0x180037fcb  lea     edx, [r15+1]
0x180037fcf  mov     rax, [rcx]
0x180037fd2  mov     rax, [rax+50h]
0x180037fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fdb  mov     ebx, eax
0x180037fdd  test    eax, eax
0x180037fdf  js      short loc_18003805E
0x180037fe1  mov     rcx, cs:?g_hmodThisDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180037fe8  lea     r8, [rsp+460h+Buffer]; lpBuffer
0x180037fed  mov     r9d, 200h; cchBufferMax
0x180037ff3  mov     edx, 157Fh; uID
0x180037ff8  call    cs:__imp_LoadStringW
0x180037ffe  mov     rcx, [rsp+460h+var_430]
0x180038003  lea     r8, [rsp+460h+Buffer]
0x180038008  mov     r9d, r15d
0x18003800b  mov     [rsp+460h+ppv], 0
0x180038014  lea     edx, [r15+2]
0x180038018  mov     rax, [rcx]
0x18003801b  mov     rax, [rax+50h]
0x18003801f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038024  mov     ebx, eax
0x180038026  test    eax, eax
0x180038028  js      short loc_18003805E
0x18003802a  mov     rcx, [rsp+460h+var_430]
0x18003802f  lea     r9d, [r15+28h]
0x180038033  xor     r8d, r8d
0x180038036  mov     [rsp+460h+ppv], 0
0x18003803f  mov     rdx, rsi
0x180038042  mov     rax, [rcx]
0x180038045  mov     rax, [rax+18h]
0x180038049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003804e  mov     ebx, eax
0x180038050  test    eax, eax
0x180038052  js      short loc_18003805E
0x180038054  mov     rax, [rsp+460h+var_430]
0x180038059  mov     [rdi], rax
0x18003805c  jmp     short loc_18003806F
0x18003805e  mov     rcx, [rsp+460h+var_430]
0x180038063  mov     rax, [rcx]
0x180038066  mov     rax, [rax+10h]
0x18003806a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003806f  mov     eax, ebx
0x180038071  mov     rcx, [rbp+360h+var_20]
0x180038078  xor     rcx, rsp; StackCookie
0x18003807b  call    __security_check_cookie
0x180038080  lea     r11, [rsp+460h+var_10]
0x180038088  mov     rbx, [r11+20h]
0x18003808c  mov     rsi, [r11+38h]
0x180038090  mov     rsp, r11
0x180038093  pop     r15
0x180038095  pop     rdi
0x180038096  pop     rbp
0x180038097  retn
```
