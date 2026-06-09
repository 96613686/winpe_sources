# Microsoft::Windows::DisplayEnhancement::Foundation::SurfaceHelper::GetMinimumBacklight(void)

- ea: `0x180056ec8`
- end: `0x1800571d7`
- name: `?GetMinimumBacklight@SurfaceHelper@Foundation@DisplayEnhancement@Windows@Microsoft@@SAEXZ`
- size: `783`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800571e0`

## callees

- `0x180005860`
- `0x18001f890`
- `0x18001f9d8`
- `0x180056ec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057198`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057156`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057156`

## pseudocode

```c
BYTE Microsoft::Windows::DisplayEnhancement::Foundation::SurfaceHelper::GetMinimumBacklight(void)
{
  LSTATUS v0; // ebx
  LSTATUS v1; // eax
  BYTE v2; // bl
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY *p_hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  char v9; // [rsp+50h] [rbp-B0h]
  WCHAR ValueName[20]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[136]; // [rsp+80h] [rbp-80h] BYREF

  wcscpy(
    SubKey,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AdaptiveDisplayBrightness\\{23B44AF2-78CE-4943-81DF-89817E8D23FD}\\"
     "CustomAdbConfiguration");
  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  wcscpy(ValueName, L"MinimumBacklight");
  p_hKey = &hKey;
  phkResult = 0;
  v9 = 1;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v0 || (cbData = 4, v1 = RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData), v2 = Data[0], v1) )
    v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x180056ec8  push    rbp
0x180056eca  push    rbx
0x180056ecb  push    rsi
0x180056ecc  push    rdi
0x180056ecd  push    r12
0x180056ecf  push    r13
0x180056ed1  push    r14
0x180056ed3  push    r15
0x180056ed5  lea     rbp, [rsp-0A8h]
0x180056edd  sub     rsp, 1A8h
0x180056ee4  mov     rax, cs:__security_cookie
0x180056eeb  xor     rax, rsp
0x180056eee  mov     [rbp+0E0h+var_50], rax
0x180056ef5  xor     edi, edi
0x180056ef7  mov     dword ptr [rbp+0E0h+SubKey], 6F0053h
0x180056efe  mov     [rbp+0E0h+var_58], di
0x180056f05  lea     rax, [rsp+1E0h+hKey]
0x180056f0a  mov     [rsp+1E0h+var_168], di
0x180056f0f  mov     [rsp+1E0h+hKey], rdi
0x180056f14  mov     [rsp+1E0h+cbData], edi
0x180056f18  mov     dword ptr [rsp+1E0h+Data], edi
0x180056f1c  mov     [rbp+0E0h+var_15C], 740066h
0x180056f23  mov     [rbp+0E0h+var_158], 610077h
0x180056f2a  mov     [rbp+0E0h+var_154], 650072h
0x180056f31  mov     [rbp+0E0h+var_150], 4D005Ch
0x180056f38  mov     [rbp+0E0h+var_14C], 630069h
0x180056f3f  mov     [rbp+0E0h+var_148], 6F0072h
0x180056f46  mov     [rbp+0E0h+var_144], 6F0073h
0x180056f4d  mov     [rbp+0E0h+var_140], 740066h
0x180056f54  mov     [rbp+0E0h+var_13C], 57005Ch
0x180056f5b  mov     [rbp+0E0h+var_138], 6E0069h
0x180056f62  mov     [rbp+0E0h+var_134], 6F0064h
0x180056f69  mov     [rbp+0E0h+var_130], 730077h
0x180056f70  mov     [rbp+0E0h+var_12C], 4E0020h
0x180056f77  mov     [rbp+0E0h+var_128], 5C0054h
0x180056f7e  mov     [rbp+0E0h+var_124], 750043h
0x180056f85  mov     [rbp+0E0h+var_120], 720072h
0x180056f8c  mov     [rbp+0E0h+var_11C], 6E0065h
0x180056f93  mov     [rbp+0E0h+var_118], 560074h
0x180056f9a  mov     [rbp+0E0h+var_114], 720065h
0x180056fa1  mov     [rbp+0E0h+var_110], 690073h
0x180056fa8  mov     [rbp+0E0h+var_10C], 6E006Fh
0x180056faf  mov     [rbp+0E0h+var_108], 41005Ch
0x180056fb6  mov     [rbp+0E0h+var_104], 610064h
0x180056fbd  mov     [rbp+0E0h+var_100], 740070h
0x180056fc4  mov     [rbp+0E0h+var_FC], 760069h
0x180056fcb  mov     [rbp+0E0h+var_F8], 440065h
0x180056fd2  mov     [rbp+0E0h+var_F4], 730069h
0x180056fd9  mov     [rbp+0E0h+var_F0], 6C0070h
0x180056fe0  mov     [rbp+0E0h+var_EC], 790061h
0x180056fe7  mov     [rbp+0E0h+var_E8], 720042h
0x180056fee  mov     [rbp+0E0h+var_E4], 670069h
0x180056ff5  mov     [rbp+0E0h+var_E0], 740068h
0x180056ffc  mov     [rbp+0E0h+var_DC], 65006Eh
0x180057003  mov     [rbp+0E0h+var_D8], 730073h
0x18005700a  mov     [rbp+0E0h+var_D4], 7B005Ch
0x180057011  mov     [rbp+0E0h+var_D0], 330032h
0x180057018  mov     [rbp+0E0h+var_CC], 340042h
0x18005701f  mov     [rbp+0E0h+var_C8], 410034h
0x180057026  mov     [rbp+0E0h+var_C4], 320046h
0x18005702d  mov     [rbp+0E0h+var_C0], 37002Dh
0x180057034  mov     [rbp+0E0h+var_BC], 430038h
0x18005703b  mov     [rbp+0E0h+var_B8], 2D0045h
0x180057042  mov     [rbp+0E0h+var_B4], 390034h
0x180057049  mov     [rbp+0E0h+var_B0], 330034h
0x180057050  mov     [rbp+0E0h+var_AC], 38002Dh
0x180057057  mov     [rbp+0E0h+var_A8], 440031h
0x18005705e  mov     [rbp+0E0h+var_A4], 2D0046h
0x180057065  mov     [rbp+0E0h+var_A0], 390038h
0x18005706c  mov     [rbp+0E0h+var_9C], 310038h
0x180057073  mov     [rbp+0E0h+var_98], 450037h
0x18005707a  mov     [rbp+0E0h+var_94], 440038h
0x180057081  mov     [rbp+0E0h+var_90], 330032h
0x180057088  mov     [rbp+0E0h+var_8C], 440046h
0x18005708f  mov     [rbp+0E0h+var_88], 5C007Dh
0x180057096  mov     [rbp+0E0h+var_84], 750043h
0x18005709d  mov     [rbp+0E0h+var_80], 740073h
0x1800570a4  mov     [rbp+0E0h+var_7C], 6D006Fh
0x1800570ab  mov     [rbp+0E0h+var_78], 640041h
0x1800570b2  mov     [rbp+0E0h+var_74], 430062h
0x1800570b9  mov     [rbp+0E0h+var_70], 6E006Fh
0x1800570c0  mov     [rbp+0E0h+var_6C], 690066h
0x1800570c7  mov     [rbp+0E0h+var_68], 750067h
0x1800570ce  mov     [rbp+0E0h+var_64], 610072h
0x1800570d5  mov     [rbp+0E0h+var_60], 690074h
0x1800570df  mov     [rbp+0E0h+var_5C], 6E006Fh
0x1800570e9  mov     dword ptr [rsp+1E0h+ValueName], 69004Dh
0x1800570f1  mov     [rsp+1E0h+var_184], 69006Eh
0x1800570f9  mov     [rsp+1E0h+var_180], 75006Dh
0x180057101  mov     [rsp+1E0h+var_17C], 42006Dh
0x180057109  mov     [rsp+1E0h+var_178], 630061h
0x180057111  mov     [rsp+1E0h+var_174], 6C006Bh
0x180057119  mov     [rsp+1E0h+var_170], 670069h
0x180057121  mov     [rsp+1E0h+var_16C], 740068h
0x180057129  mov     [rsp+1E0h+var_1A0], rax
0x18005712e  lea     rdx, [rbp+0E0h+SubKey]; lpSubKey
0x180057132  lea     rax, [rsp+1E0h+var_198]
0x180057137  mov     [rsp+1E0h+var_198], rdi
0x18005713c  mov     r9d, 20019h; samDesired
0x180057142  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180057147  xor     r8d, r8d; ulOptions
0x18005714a  mov     [rsp+1E0h+var_190], 1
0x18005714f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057156  call    cs:__imp_RegOpenKeyExW
0x18005715c  lea     rcx, [rsp+1E0h+var_1A0]
0x180057161  mov     ebx, eax
0x180057163  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180057168  test    ebx, ebx
0x18005716a  jnz     short loc_1800571A6
0x18005716c  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180057171  lea     rax, [rsp+1E0h+cbData]
0x180057176  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x18005717b  lea     rdx, [rsp+1E0h+ValueName]; lpValueName
0x180057180  lea     rax, [rsp+1E0h+Data]
0x180057185  mov     [rsp+1E0h+cbData], 4
0x18005718d  xor     r9d, r9d; lpType
0x180057190  mov     [rsp+1E0h+phkResult], rax; lpData
0x180057195  xor     r8d, r8d; lpReserved
0x180057198  call    cs:__imp_RegQueryValueExW
0x18005719e  mov     bl, [rsp+1E0h+Data]
0x1800571a2  test    eax, eax
0x1800571a4  jz      short loc_1800571A8
0x1800571a6  mov     bl, 1
0x1800571a8  lea     rcx, [rsp+1E0h+hKey]
0x1800571ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800571b2  mov     al, bl
0x1800571b4  mov     rcx, [rbp+0E0h+var_50]
0x1800571bb  xor     rcx, rsp; StackCookie
0x1800571be  call    __security_check_cookie
0x1800571c3  add     rsp, 1A8h
0x1800571ca  pop     r15
0x1800571cc  pop     r14
0x1800571ce  pop     r13
0x1800571d0  pop     r12
0x1800571d2  pop     rdi
0x1800571d3  pop     rsi
0x1800571d4  pop     rbx
0x1800571d5  pop     rbp
0x1800571d6  retn
```
