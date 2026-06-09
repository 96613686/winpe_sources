# PopupUnenrollmentUI(ushort *)

- ea: `0x1400332e4`
- end: `0x140033448`
- name: `?PopupUnenrollmentUI@@YAJPEAG@Z`
- size: `356`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x1400332a8`
- `0x1400332e4`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x140033408`
- `DMCmnUtils!DmRaiseToastNotification` at `0x140033408`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140033327`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140033327`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140033369`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140033389`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140033369`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140033389`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033418`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140033418`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400333bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400333bd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003341f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003341f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003330a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003330a`

## string_xrefs

- `0x1400333ec`: `protocol`
- `0x140033320`: `Windows.Internal.Management.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall PopupUnenrollmentUI(unsigned __int16 *a1)
{
  HRESULT result; // eax
  HMODULE Library; // rax
  HMODULE v4; // rdi
  signed int v5; // eax
  signed int v6; // ebx
  WCHAR *v7; // r9
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-648h] BYREF
  WCHAR v10[264]; // [rsp+240h] [rbp-438h] BYREF
  unsigned __int16 v11[264]; // [rsp+450h] [rbp-228h] BYREF

  result = CoInitializeEx(0, 0);
  if ( result >= 0 )
  {
    Library = LoadLibraryExW(L"Windows.Internal.Management.dll", 0, 0x800u);
    v4 = Library;
    if ( Library && (a1 || LoadStringW(Library, 0x66u, Buffer, 260)) && LoadStringW(v4, 0x67u, v10, 260) )
    {
      v7 = Buffer;
      if ( a1 )
        v7 = a1;
      if ( (unsigned int)_snwprintf_s<260>(v11, 260, v10, v7) )
        goto LABEL_14;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
LABEL_14:
        v6 = DmRaiseToastNotification(
               L"Windows.SystemToast.DeviceEnrollmentActivity",
               L"DeviceEnrollment",
               L"ms-settings:workplace",
               L"protocol",
               0,
               v11);
    }
    else
    {
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    if ( v4 )
      FreeLibrary(v4);
    CoUninitialize();
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1400332e4  mov     [rsp+arg_8], rbx
0x1400332e9  push    rdi
0x1400332ea  sub     rsp, 670h
0x1400332f1  mov     rax, cs:__security_cookie
0x1400332f8  xor     rax, rsp
0x1400332fb  mov     [rsp+678h+var_18], rax
0x140033303  mov     rbx, rcx
0x140033306  xor     edx, edx; dwCoInit
0x140033308  xor     ecx, ecx; pvReserved
0x14003330a  call    cs:__imp_CoInitializeEx
0x140033310  test    eax, eax
0x140033312  js      loc_140033427
0x140033318  xor     edx, edx; hFile
0x14003331a  mov     r8d, 800h; dwFlags
0x140033320  lea     rcx, aWindowsInterna; "Windows.Internal.Management.dll"
0x140033327  call    cs:__imp_LoadLibraryExW
0x14003332d  mov     rdi, rax
0x140033330  test    rax, rax
0x140033333  jnz     short loc_140033353
0x140033335  call    cs:__imp_GetLastError
0x14003333b  mov     ebx, eax
0x14003333d  test    eax, eax
0x14003333f  jle     loc_140033410
0x140033345  movzx   ebx, ax
0x140033348  or      ebx, 80070000h
0x14003334e  jmp     loc_140033410
0x140033353  test    rbx, rbx
0x140033356  jnz     short loc_140033373
0x140033358  mov     r9d, 104h; cchBufferMax
0x14003335e  lea     r8, [rsp+678h+Buffer]; lpBuffer
0x140033363  lea     edx, [rbx+66h]; uID
0x140033366  mov     rcx, rdi; hInstance
0x140033369  call    cs:__imp_LoadStringW
0x14003336f  test    eax, eax
0x140033371  jz      short loc_140033335
0x140033373  mov     r9d, 104h; cchBufferMax
0x140033379  lea     r8, [rsp+678h+var_438]; lpBuffer
0x140033381  mov     edx, 67h ; 'g'; uID
0x140033386  mov     rcx, rdi; hInstance
0x140033389  call    cs:__imp_LoadStringW
0x14003338f  test    eax, eax
0x140033391  jz      short loc_140033335
0x140033393  lea     r9, [rsp+678h+Buffer]
0x140033398  test    rbx, rbx
0x14003339b  cmovnz  r9, rbx
0x14003339f  lea     r8, [rsp+678h+var_438]
0x1400333a7  mov     edx, 104h
0x1400333ac  lea     rcx, [rsp+678h+var_228]
0x1400333b4  call    ??$_snwprintf_s@$0BAE@@@YAHAEAY0BAE@G_KPEBGZZ; _snwprintf_s<260>(ushort (&)[260],unsigned __int64,ushort const *,...)
0x1400333b9  test    eax, eax
0x1400333bb  jnz     short loc_1400333D6
0x1400333bd  call    cs:__imp_GetLastError
0x1400333c3  mov     ebx, eax
0x1400333c5  test    eax, eax
0x1400333c7  jle     short loc_1400333D2
0x1400333c9  movzx   ebx, ax
0x1400333cc  or      ebx, 80070000h
0x1400333d2  test    ebx, ebx
0x1400333d4  js      short loc_140033410
0x1400333d6  lea     rax, [rsp+678h+var_228]
0x1400333de  mov     [rsp+678h+var_650], rax
0x1400333e3  mov     [rsp+678h+var_658], 0
0x1400333ec  lea     r9, aProtocol; "protocol"
0x1400333f3  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1400333fa  lea     rdx, aDeviceenrollme; "DeviceEnrollment"
0x140033401  lea     rcx, aWindowsSystemt_0; "Windows.SystemToast.DeviceEnrollmentAct"...
0x140033408  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x14003340e  mov     ebx, eax
0x140033410  test    rdi, rdi
0x140033413  jz      short loc_14003341F
0x140033415  mov     rcx, rdi; hLibModule
0x140033418  call    cs:__imp_FreeLibrary
0x14003341e  nop
0x14003341f  call    cs:__imp_CoUninitialize
0x140033425  mov     eax, ebx
0x140033427  mov     rcx, [rsp+678h+var_18]
0x14003342f  xor     rcx, rsp; StackCookie
0x140033432  call    __security_check_cookie
0x140033437  mov     rbx, [rsp+678h+arg_8]
0x14003343f  add     rsp, 670h
0x140033446  pop     rdi
0x140033447  retn
```
