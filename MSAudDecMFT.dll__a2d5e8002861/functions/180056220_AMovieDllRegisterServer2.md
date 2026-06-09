# AMovieDllRegisterServer2

- ea: `0x180056220`
- end: `0x180056414`
- name: `AMovieDllRegisterServer2`
- size: `500`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800556b0`
- `0x180055860`

## callees

- `0x18004d320`
- `0x1800560c4`
- `0x180056220`
- `0x18005641c`
- `0x1800566d8`
- `0x1800567b0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005626b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005626b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18005625b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18005625b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800562bf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800562bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800563d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800563d5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800562ee`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800562ee`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800563c9`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x1800563c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005632a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005635a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005632a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005635a`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  unsigned __int64 v2; // rdx
  __int64 result; // rax
  HRESULT v4; // ebx
  __int64 v5; // rdi
  __int64 v6; // rcx
  HRESULT v7; // eax
  LPVOID v8; // rcx
  LPVOID v9; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+150h] [rbp+50h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v9 = 0;
  result = StringCchLengthA(Filename, v2, (unsigned __int64 *)&v9);
  if ( (int)result >= 0 )
  {
    MultiByteToWideChar(0, 0, Filename, (_DWORD)v9 + 1, WideCharStr, 260);
    if ( !a1 || (v4 = RegisterAllServers(WideCharStr, 1), v4 >= 0) )
    {
      CoInitializeEx(0, 2u);
      ppv = 0;
      v9 = 0;
      v4 = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( v4 >= 0 || (v4 = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, &v9), v4 >= 0) )
      {
        v5 = 0;
        do
        {
          v6 = qword_1800E4020[5 * v5];
          if ( v6 )
          {
            if ( ppv )
              v7 = AMovieSetupRegisterFilter2(v6, ppv, a1);
            else
              v7 = AMovieSetupRegisterFilter(v6, v9, a1);
            v4 = v7;
          }
          if ( v4 < 0 )
            break;
          v5 = (unsigned int)(v5 + 1);
        }
        while ( (int)v5 < 3 );
        v8 = ppv;
        if ( !ppv )
          v8 = v9;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( v4 >= 0 && !a1 )
        return (unsigned int)RegisterAllServers(WideCharStr, 0);
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180056220  push    rbp
0x180056222  push    rbx
0x180056223  push    rsi
0x180056224  push    rdi
0x180056225  lea     rbp, [rsp-278h]
0x18005622d  sub     rsp, 378h
0x180056234  mov     rax, cs:__security_cookie
0x18005623b  xor     rax, rsp
0x18005623e  mov     [rbp+290h+var_30], rax
0x180056245  mov     esi, ecx
0x180056247  lea     rdx, [rsp+390h+Filename]; lpFilename
0x18005624c  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x180056253  mov     ebx, 104h
0x180056258  mov     r8d, ebx; nSize
0x18005625b  call    cs:__imp_GetModuleFileNameA
0x180056262  nop     dword ptr [rax+rax+00h]
0x180056267  test    eax, eax
0x180056269  jnz     short loc_180056281
0x18005626b  call    cs:__imp_GetLastError
0x180056272  nop     dword ptr [rax+rax+00h]
0x180056277  or      eax, 80070000h
0x18005627c  jmp     loc_1800563F8
0x180056281  lea     r8, [rsp+390h+var_360]; unsigned __int64 *
0x180056286  mov     [rsp+390h+var_360], 0
0x18005628f  lea     rcx, [rsp+390h+Filename]; char *
0x180056294  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180056299  test    eax, eax
0x18005629b  js      loc_1800563F8
0x1800562a1  mov     r9d, dword ptr [rsp+390h+var_360]
0x1800562a6  lea     rax, [rbp+290h+WideCharStr]
0x1800562aa  inc     r9d; cbMultiByte
0x1800562ad  mov     [rsp+390h+cchWideChar], ebx; cchWideChar
0x1800562b1  lea     r8, [rsp+390h+Filename]; lpMultiByteStr
0x1800562b6  mov     [rsp+390h+lpWideCharStr], rax; lpWideCharStr
0x1800562bb  xor     edx, edx; dwFlags
0x1800562bd  xor     ecx, ecx; CodePage
0x1800562bf  call    cs:__imp_MultiByteToWideChar
0x1800562c6  nop     dword ptr [rax+rax+00h]
0x1800562cb  test    esi, esi
0x1800562cd  jz      short loc_1800562E7
0x1800562cf  mov     edx, 1
0x1800562d4  lea     rcx, [rbp+290h+WideCharStr]
0x1800562d8  call    RegisterAllServers
0x1800562dd  mov     ebx, eax
0x1800562df  test    eax, eax
0x1800562e1  js      loc_1800563F6
0x1800562e7  mov     edx, 2; dwCoInit
0x1800562ec  xor     ecx, ecx; pvReserved
0x1800562ee  call    cs:__imp_CoInitializeEx
0x1800562f5  nop     dword ptr [rax+rax+00h]
0x1800562fa  xor     edx, edx; pUnkOuter
0x1800562fc  mov     [rsp+390h+ppv], 0
0x180056305  lea     rax, [rsp+390h+ppv]
0x18005630a  mov     [rsp+390h+var_360], 0
0x180056313  lea     r9, IID_IFilterMapper2; riid
0x18005631a  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18005631f  lea     rcx, CLSID_FilterMapper2; rclsid
0x180056326  lea     r8d, [rdx+1]; dwClsContext
0x18005632a  call    cs:__imp_CoCreateInstance
0x180056331  nop     dword ptr [rax+rax+00h]
0x180056336  mov     ebx, eax
0x180056338  test    eax, eax
0x18005633a  jns     short loc_18005636C
0x18005633c  xor     edx, edx; pUnkOuter
0x18005633e  lea     rax, [rsp+390h+var_360]
0x180056343  lea     r9, IID_IFilterMapper; riid
0x18005634a  mov     [rsp+390h+lpWideCharStr], rax; ppv
0x18005634f  lea     rcx, CLSID_FilterMapper; rclsid
0x180056356  lea     r8d, [rdx+1]; dwClsContext
0x18005635a  call    cs:__imp_CoCreateInstance
0x180056361  nop     dword ptr [rax+rax+00h]
0x180056366  mov     ebx, eax
0x180056368  test    eax, eax
0x18005636a  js      short loc_1800563C9
0x18005636c  xor     edi, edi
0x18005636e  lea     rcx, [rdi+rdi*4]
0x180056372  lea     rax, qword_1800E4020
0x180056379  mov     rcx, [rax+rcx*8]
0x18005637d  test    rcx, rcx
0x180056380  jz      short loc_1800563A2
0x180056382  mov     rdx, [rsp+390h+ppv]
0x180056387  mov     r8d, esi
0x18005638a  test    rdx, rdx
0x18005638d  jz      short loc_180056396
0x18005638f  call    AMovieSetupRegisterFilter2
0x180056394  jmp     short loc_1800563A0
0x180056396  mov     rdx, [rsp+390h+var_360]
0x18005639b  call    AMovieSetupRegisterFilter
0x1800563a0  mov     ebx, eax
0x1800563a2  test    ebx, ebx
0x1800563a4  js      short loc_1800563AD
0x1800563a6  inc     edi
0x1800563a8  cmp     edi, 3
0x1800563ab  jl      short loc_18005636E
0x1800563ad  mov     rcx, [rsp+390h+ppv]
0x1800563b2  test    rcx, rcx
0x1800563b5  jnz     short loc_1800563BC
0x1800563b7  mov     rcx, [rsp+390h+var_360]
0x1800563bc  mov     rax, [rcx]
0x1800563bf  mov     rax, [rax+10h]
0x1800563c3  call    cs:__guard_dispatch_icall_fptr
0x1800563c9  call    cs:__imp_CoFreeUnusedLibraries
0x1800563d0  nop     dword ptr [rax+rax+00h]
0x1800563d5  call    cs:__imp_CoUninitialize
0x1800563dc  nop     dword ptr [rax+rax+00h]
0x1800563e1  test    ebx, ebx
0x1800563e3  js      short loc_1800563F6
0x1800563e5  test    esi, esi
0x1800563e7  jnz     short loc_1800563F6
0x1800563e9  xor     edx, edx
0x1800563eb  lea     rcx, [rbp+290h+WideCharStr]
0x1800563ef  call    RegisterAllServers
0x1800563f4  mov     ebx, eax
0x1800563f6  mov     eax, ebx
0x1800563f8  mov     rcx, [rbp+290h+var_30]
0x1800563ff  xor     rcx, rsp; StackCookie
0x180056402  call    __security_check_cookie
0x180056407  add     rsp, 378h
0x18005640e  pop     rdi
0x18005640f  pop     rsi
0x180056410  pop     rbx
0x180056411  pop     rbp
0x180056412  retn
```
