# ClassicAppInfoInternal::GetInstalledApplicationInfo(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x180041190`
- end: `0x1800413a0`
- name: `?GetInstalledApplicationInfo@ClassicAppInfoInternal@@UEAAJPEAUHSTRING__@@PEAPEAU2@1@Z`
- size: `528`
- prototype: `__int64 __fastcall(ClassicAppInfoInternal *this, HSTRING, HSTRING *, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005c48`
- `0x180005eb8`
- `0x180007560`
- `0x180007960`
- `0x1800405c4`
- `0x180041190`
- `0x1800418dc`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041289`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800412f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041289`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800412f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800412bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800412bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800411dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800411dc`

## string_xrefs

- `0x1800411fb`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x180041341`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x18004123e`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\%s`

## pseudocode

```c
__int64 __fastcall ClassicAppInfoInternal::GetInstalledApplicationInfo(
        ClassicAppInfoInternal *this,
        HSTRING a2,
        HSTRING *a3,
        HSTRING *a4)
{
  PCWSTR StringRawBuffer; // rax
  PCWSTR v7; // rbx
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 i; // rcx
  LSTATUS v11; // eax
  HKEY v12; // rbx
  LSTATUS v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int ValueAsHString; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[360]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  *a3 = 0;
  *a4 = 0;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
  v7 = StringRawBuffer;
  if ( !StringRawBuffer )
  {
    v8 = 256;
LABEL_3:
    v9 = -2147024809;
    goto LABEL_4;
  }
  for ( i = 0; (unsigned int)i < length; i = (unsigned int)(i + 1) )
  {
    if ( StringRawBuffer[i] == 92 )
    {
      v8 = 263;
      goto LABEL_3;
    }
  }
  memset_0(SubKey, 0, 0x2C8u);
  v9 = StringCchPrintfW(SubKey, 0x164u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\%s", v7);
  if ( (v9 & 0x80000000) == 0 )
  {
    hKey = 0;
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20219u, &hKey);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( v9 == -2147024894 )
    {
      v12 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v22);
        RegCloseKey(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
      }
      hKey = 0;
      v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hKey);
      v9 = v13;
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
    }
    if ( (v9 & 0x80000000) == 0 )
    {
      ValueAsHString = RegQueryValueAsHString(hKey, L"DisplayName", a3);
      v9 = ValueAsHString;
      if ( ValueAsHString >= 0 )
      {
        ValueAsHString = RegQueryValueAsHString(hKey, L"DisplayVersion", a4);
        v9 = ValueAsHString;
        if ( ValueAsHString >= 0 )
        {
          v9 = 0;
          goto LABEL_28;
        }
        v15 = 290;
      }
      else
      {
        v15 = 289;
      }
      v14 = (unsigned int)ValueAsHString;
    }
    else
    {
      v14 = v9;
      v15 = 285;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
      (const char *)v14,
      phkResulta);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  v8 = 269;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
    (const char *)v9,
    phkResult);
  return v9;
}

```

## disassembly

```asm
0x180041190  mov     [rsp-8+arg_0], rbx
0x180041195  push    rbp
0x180041196  push    rsi
0x180041197  push    rdi
0x180041198  lea     rbp, [rsp-230h]
0x1800411a0  sub     rsp, 330h
0x1800411a7  mov     rax, cs:__security_cookie
0x1800411ae  xor     rax, rsp
0x1800411b1  mov     [rbp+240h+var_20], rax
0x1800411b8  mov     rcx, rdx; string
0x1800411bb  mov     qword ptr [r8], 0
0x1800411c2  lea     rdx, [rsp+340h+length]; length
0x1800411c7  mov     qword ptr [r9], 0
0x1800411ce  mov     rsi, r9
0x1800411d1  mov     [rsp+340h+length], 0
0x1800411d9  mov     rdi, r8
0x1800411dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800411e2  mov     rbx, rax
0x1800411e5  test    rax, rax
0x1800411e8  jnz     short loc_18004120F
0x1800411ea  mov     edx, 100h; void *
0x1800411ef  mov     ebx, 80070057h
0x1800411f4  mov     rcx, [rbp+248h]; this
0x1800411fb  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041202  mov     r9d, ebx; char *
0x180041205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004120a  jmp     loc_18004137C
0x18004120f  xor     ecx, ecx
0x180041211  cmp     ecx, [rsp+340h+length]
0x180041215  jnb     short loc_180041229
0x180041217  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x18004121c  jz      short loc_180041222
0x18004121e  inc     ecx
0x180041220  jmp     short loc_180041211
0x180041222  mov     edx, 107h
0x180041227  jmp     short loc_1800411EF
0x180041229  xor     edx, edx; Val
0x18004122b  lea     rcx, [rsp+340h+SubKey]; void *
0x180041230  mov     r8d, 2C8h; Size
0x180041236  call    memset_0
0x18004123b  mov     r9, rbx
0x18004123e  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041245  mov     edx, 164h; unsigned __int64
0x18004124a  lea     rcx, [rsp+340h+SubKey]; unsigned __int16 *
0x18004124f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041254  mov     ebx, eax
0x180041256  test    eax, eax
0x180041258  jns     short loc_180041261
0x18004125a  mov     edx, 10Dh
0x18004125f  jmp     short loc_1800411F4
0x180041261  lea     rax, [rsp+340h+hKey]
0x180041266  mov     [rsp+340h+hKey], 0
0x18004126f  mov     r9d, 20219h; samDesired
0x180041275  mov     qword ptr [rsp+340h+phkResult], rax; phkResult
0x18004127a  xor     r8d, r8d; ulOptions
0x18004127d  lea     rdx, [rsp+340h+SubKey]; lpSubKey
0x180041282  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041289  call    cs:__imp_RegOpenKeyExW
0x18004128f  mov     ebx, eax
0x180041291  test    eax, eax
0x180041293  jle     short loc_18004129E
0x180041295  movzx   ebx, ax
0x180041298  or      ebx, 80070000h
0x18004129e  cmp     ebx, 80070002h
0x1800412a4  jnz     short loc_18004130A
0x1800412a6  mov     rbx, [rsp+340h+hKey]
0x1800412ab  test    rbx, rbx
0x1800412ae  jz      short loc_1800412CD
0x1800412b0  lea     rcx, [rsp+340h+var_300]; this
0x1800412b5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800412ba  mov     rcx, rbx; hKey
0x1800412bd  call    cs:__imp_RegCloseKey
0x1800412c3  lea     rcx, [rsp+340h+var_300]; this
0x1800412c8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800412cd  lea     rax, [rsp+340h+hKey]
0x1800412d2  mov     [rsp+340h+hKey], 0
0x1800412db  mov     r9d, 20119h; samDesired
0x1800412e1  mov     qword ptr [rsp+340h+phkResult], rax; int
0x1800412e6  xor     r8d, r8d; ulOptions
0x1800412e9  lea     rdx, [rsp+340h+SubKey]; lpSubKey
0x1800412ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800412f5  call    cs:__imp_RegOpenKeyExW
0x1800412fb  mov     ebx, eax
0x1800412fd  test    eax, eax
0x1800412ff  jle     short loc_18004130A
0x180041301  movzx   ebx, ax
0x180041304  or      ebx, 80070000h
0x18004130a  test    ebx, ebx
0x18004130c  jns     short loc_180041318
0x18004130e  mov     r9d, ebx
0x180041311  mov     edx, 11Dh
0x180041316  jmp     short loc_18004133A
0x180041318  mov     rcx, [rsp+340h+hKey]; hkey
0x18004131d  lea     rdx, aDisplayname; "DisplayName"
0x180041324  mov     r8, rdi; string
0x180041327  call    ?RegQueryValueAsHString@@YAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; RegQueryValueAsHString(HKEY__ *,ushort const *,HSTRING__ * *)
0x18004132c  mov     ebx, eax
0x18004132e  test    eax, eax
0x180041330  jns     short loc_18004134F
0x180041332  mov     edx, 121h; void *
0x180041337  mov     r9d, eax; char *
0x18004133a  mov     rcx, [rbp+248h]; this
0x180041341  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004134d  jmp     short loc_180041372
0x18004134f  mov     rcx, [rsp+340h+hKey]; hkey
0x180041354  lea     rdx, aDisplayversion; "DisplayVersion"
0x18004135b  mov     r8, rsi; string
0x18004135e  call    ?RegQueryValueAsHString@@YAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; RegQueryValueAsHString(HKEY__ *,ushort const *,HSTRING__ * *)
0x180041363  mov     ebx, eax
0x180041365  test    eax, eax
0x180041367  jns     short loc_180041370
0x180041369  mov     edx, 122h
0x18004136e  jmp     short loc_180041337
0x180041370  xor     ebx, ebx
0x180041372  lea     rcx, [rsp+340h+hKey]
0x180041377  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004137c  mov     eax, ebx
0x18004137e  mov     rcx, [rbp+240h+var_20]
0x180041385  xor     rcx, rsp; StackCookie
0x180041388  call    __security_check_cookie
0x18004138d  mov     rbx, [rsp+340h+arg_0]
0x180041395  add     rsp, 330h
0x18004139c  pop     rdi
0x18004139d  pop     rsi
0x18004139e  pop     rbp
0x18004139f  retn
```
