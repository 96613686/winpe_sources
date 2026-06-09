# AfxDelRegTreeHelper(HKEY__ *,CString const &)

- ea: `0x1800052e0`
- end: `0x1800053e6`
- name: `?AfxDelRegTreeHelper@@YAJPEAUHKEY__@@AEBVCString@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(HKEY, const struct CString *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800052e0`
- `0x1800053f0`
- `0x18002a540`
- `0x1800c59e8`

## callees

- `0x1800052e0`
- `0x18000c950`
- `0x180019290`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800053ac`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800053ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800053b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005329`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005329`
- `ADVAPI32!RegEnumKeyW` at `0x18000534b`
- `ADVAPI32!RegEnumKeyW` at `0x18000534b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall AfxDelRegTreeHelper(HKEY a1, LPCWSTR *a2)
{
  unsigned int v4; // ebx
  int v6; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, *a2, 0, 0x2000000u, &hKey);
  if ( !v4 )
  {
    do
    {
      v4 = RegEnumKeyW(hKey, 0, Name, 0x104u);
      if ( v4 )
        break;
      CString::CString((CString *)&v6, Name);
      v4 = AfxDelRegTreeHelper(hKey, (const struct CString *)&v6);
      CString::~CString((CString *)&v6);
    }
    while ( !v4 );
    if ( v4 == 259 || v4 == 1010 )
      v4 = RegDeleteKeyExW(a1, *a2, 0, 0);
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800052e0  mov     [rsp+arg_10], rbx
0x1800052e5  mov     [rsp+arg_18], rsi
0x1800052ea  push    rdi
0x1800052eb  sub     rsp, 270h
0x1800052f2  mov     rax, cs:__security_cookie
0x1800052f9  xor     rax, rsp
0x1800052fc  mov     [rsp+278h+var_18], rax
0x180005304  mov     rsi, rdx
0x180005307  mov     rdi, rcx
0x18000530a  mov     [rsp+278h+hKey], 0
0x180005313  lea     rax, [rsp+278h+hKey]
0x180005318  mov     [rsp+278h+phkResult], rax; phkResult
0x18000531d  mov     r9d, 2000000h; samDesired
0x180005323  xor     r8d, r8d; ulOptions
0x180005326  mov     rdx, [rdx]; lpSubKey
0x180005329  call    cs:__imp_RegOpenKeyExW
0x18000532f  mov     ebx, eax
0x180005331  test    eax, eax
0x180005333  jnz     loc_1800053BF
0x180005339  mov     r9d, 104h; cchName
0x18000533f  lea     r8, [rsp+278h+Name]; lpName
0x180005344  xor     edx, edx; dwIndex
0x180005346  mov     rcx, [rsp+278h+hKey]; hKey
0x18000534b  call    cs:__imp_RegEnumKeyW
0x180005351  mov     ebx, eax
0x180005353  test    eax, eax
0x180005355  jnz     short loc_180005390
0x180005357  lea     rdx, [rsp+278h+Name]; unsigned __int16 *
0x18000535c  lea     rcx, [rsp+278h+var_248]; this
0x180005361  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180005366  nop
0x180005367  lea     rdx, [rsp+278h+var_248]; struct CString *
0x18000536c  mov     rcx, [rsp+278h+hKey]; HKEY
0x180005371  call    ?AfxDelRegTreeHelper@@YAJPEAUHKEY__@@AEBVCString@@@Z; AfxDelRegTreeHelper(HKEY__ *,CString const &)
0x180005376  mov     ebx, eax
0x180005378  lea     rcx, [rsp+278h+var_248]; this
0x18000537d  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180005382  test    ebx, ebx
0x180005384  jz      short loc_180005388
0x180005386  jmp     short loc_180005390
0x180005388  jmp     short loc_180005339
0x18000538a  mov     ebx, [rsp+278h+var_248]
0x18000538e  jmp     short loc_1800053B4
0x180005390  cmp     ebx, 103h
0x180005396  jz      short loc_1800053A0
0x180005398  cmp     ebx, 3F2h
0x18000539e  jnz     short loc_1800053B4
0x1800053a0  xor     r9d, r9d; Reserved
0x1800053a3  xor     r8d, r8d; samDesired
0x1800053a6  mov     rdx, [rsi]; lpSubKey
0x1800053a9  mov     rcx, rdi; hKey
0x1800053ac  call    cs:__imp_RegDeleteKeyExW
0x1800053b2  mov     ebx, eax
0x1800053b4  mov     rcx, [rsp+278h+hKey]; hKey
0x1800053b9  call    cs:__imp_RegCloseKey
0x1800053bf  mov     eax, ebx
0x1800053c1  mov     rcx, [rsp+278h+var_18]
0x1800053c9  xor     rcx, rsp; StackCookie
0x1800053cc  call    __security_check_cookie
0x1800053d1  lea     r11, [rsp+278h+var_8]
0x1800053d9  mov     rbx, [r11+20h]
0x1800053dd  mov     rsi, [r11+28h]
0x1800053e1  mov     rsp, r11
0x1800053e4  pop     rdi
0x1800053e5  retn
```
