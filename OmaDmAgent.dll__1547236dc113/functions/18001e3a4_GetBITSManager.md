# GetBITSManager

- ea: `0x18001e3a4`
- end: `0x18001e47a`
- name: `GetBITSManager`
- size: `214`
- prototype: `__int64 __fastcall(wchar_t *String1, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e07c`

## callees

- `0x18000bae8`
- `0x18001dfe0`
- `0x18001e3a4`
- `0x18001e480`
- `0x18001e4f8`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001e43e`
- `msvcrt!_wcsnicmp` at `0x18001e43e`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e3f6`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e3f6`

## pseudocode

```c
__int64 __fastcall GetBITSManager(wchar_t *String1, LPVOID *ppv)
{
  LSTATUS v4; // ebx
  unsigned int HttpBITSManager; // eax
  unsigned int v6; // ebx
  __int64 *v8; // [rsp+30h] [rbp-28h] BYREF
  HKEY v9; // [rsp+38h] [rbp-20h] BYREF
  char v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF

  v9 = 0;
  v8 = &v11;
  v11 = 0;
  v10 = 1;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\EnterpriseDesktopAppManagement\\AllowLocalFileDownload",
         0,
         0x20019u,
         &v9);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v8);
  if ( v4 )
  {
    if ( *((_QWORD *)String1 + 2) < 4u )
      goto LABEL_9;
    if ( *((_QWORD *)String1 + 3) >= 8u )
      String1 = *(wchar_t **)String1;
    if ( _wcsnicmp(String1, L"http", 4u) )
    {
LABEL_9:
      v6 = -2147024809;
      goto LABEL_10;
    }
    HttpBITSManager = GetHttpBITSManager(ppv);
  }
  else
  {
    HttpBITSManager = GetNonHttpBITSManager(ppv);
  }
  v6 = HttpBITSManager;
LABEL_10:
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)&v11);
  return v6;
}

```

## disassembly

```asm
0x18001e3a4  mov     r11, rsp
0x18001e3a7  mov     [r11+8], rbx
0x18001e3ab  mov     [r11+10h], rsi
0x18001e3af  push    rdi
0x18001e3b0  sub     rsp, 50h
0x18001e3b4  lea     rax, [r11+18h]
0x18001e3b8  mov     qword ptr [r11-20h], 0
0x18001e3c0  mov     [r11-28h], rax
0x18001e3c4  mov     rsi, rdx
0x18001e3c7  lea     rax, [r11-20h]
0x18001e3cb  mov     qword ptr [r11+18h], 0
0x18001e3d3  mov     rdi, rcx
0x18001e3d6  mov     [r11-38h], rax
0x18001e3da  mov     r9d, 20019h; samDesired
0x18001e3e0  mov     [rsp+58h+var_18], 1
0x18001e3e5  xor     r8d, r8d; ulOptions
0x18001e3e8  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\EnterpriseDesktopA"...
0x18001e3ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e3f6  call    cs:__imp_RegOpenKeyExW
0x18001e3fd  nop     dword ptr [rax+rax+00h]
0x18001e402  lea     rcx, [rsp+58h+var_28]
0x18001e407  mov     ebx, eax
0x18001e409  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001e40e  test    ebx, ebx
0x18001e410  jnz     short loc_18001E41E
0x18001e412  mov     rcx, rsi; ppv
0x18001e415  call    GetNonHttpBITSManager
0x18001e41a  mov     ebx, eax
0x18001e41c  jmp     short loc_18001E45D
0x18001e41e  mov     r8d, 4; MaxCount
0x18001e424  cmp     [rdi+10h], r8
0x18001e428  jb      short loc_18001E458
0x18001e42a  cmp     qword ptr [rdi+18h], 8
0x18001e42f  jb      short loc_18001E434
0x18001e431  mov     rdi, [rdi]
0x18001e434  lea     rdx, aHttp_0; "http"
0x18001e43b  mov     rcx, rdi; String1
0x18001e43e  call    cs:__imp__wcsnicmp
0x18001e445  nop     dword ptr [rax+rax+00h]
0x18001e44a  test    eax, eax
0x18001e44c  jnz     short loc_18001E458
0x18001e44e  mov     rcx, rsi; ppv
0x18001e451  call    GetHttpBITSManager
0x18001e456  jmp     short loc_18001E41A
0x18001e458  mov     ebx, 80070057h
0x18001e45d  lea     rcx, [rsp+58h+arg_10]; this
0x18001e462  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18001e467  mov     rsi, [rsp+58h+arg_8]
0x18001e46c  mov     eax, ebx
0x18001e46e  mov     rbx, [rsp+58h+arg_0]
0x18001e473  add     rsp, 50h
0x18001e477  pop     rdi
0x18001e478  retn
```
