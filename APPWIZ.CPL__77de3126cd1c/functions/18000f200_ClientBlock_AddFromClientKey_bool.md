# ClientBlock::_AddFromClientKey(bool)

- ea: `0x18000f200`
- end: `0x18000f3c6`
- name: `?_AddFromClientKey@ClientBlock@@AEAAJ_N@Z`
- size: `454`
- prototype: `int(ClientBlock *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cec4`

## callees

- `0x18000625c`
- `0x180008ddc`
- `0x18000a460`
- `0x18000bc98`
- `0x18000f200`
- `0x18000fa5c`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f31a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f31a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f375`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f375`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f393`
- `ADVAPI32!RegEnumKeyW` at `0x18000f26d`
- `ADVAPI32!RegEnumKeyW` at `0x18000f26d`
- `KERNEL32!lstrcmpiW` at `0x18000f2b8`
- `KERNEL32!lstrcmpiW` at `0x18000f2b8`

## string_xrefs

- `0x18000f313`: `InstallInfo`

## pseudocode

```c
__int64 __fastcall ClientBlock::_AddFromClientKey(ClientBlock *this, bool a2)
{
  int v4; // edi
  HKEY v5; // r14
  DWORD v6; // esi
  __int64 i; // rbx
  _DWORD *v8; // rcx
  int v9; // edx
  _QWORD *v10; // rcx
  const WCHAR *v11; // rcx
  struct CLIENTINFO *v12; // rax
  CLIENTINFO *v13; // rbx
  void *v14; // rdx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = 0;
  v5 = ClientBlock::_OpenClientKey(this, HKEY_LOCAL_MACHINE, 0x20019u, a2);
  if ( v5 )
  {
    v6 = 0;
    do
    {
      if ( RegEnumKeyW(v5, v6, Name, 0x104u) )
        break;
      hKey = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v8 = (_DWORD *)*((_QWORD *)this + 25);
        v9 = *v8;
        if ( (unsigned int)i >= (*v8 & 0xFFFFFFFu) )
          break;
        v10 = v8 + 2;
        if ( (v9 & 0x10000000) != 0 )
          v10 = (_QWORD *)*v10;
        v11 = *(const WCHAR **)v10[i];
        if ( v11 && !lstrcmpiW(v11, Name) )
          goto LABEL_18;
      }
      if ( !RegOpenKeyExW(v5, Name, 0, 0x20019u, &hKey) )
      {
        phkResult = 0;
        if ( !RegOpenKeyExW(hKey, L"InstallInfo", 0, 0x20019u, &phkResult) )
        {
          v12 = CLIENTINFO::Create(hKey, phkResult, Name, a2);
          v13 = v12;
          if ( v12 )
          {
            v4 = DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(
                   *((_QWORD *)this + 25),
                   **((_DWORD **)this + 25) & 0xFFFFFFF,
                   v12);
            if ( v4 < 0 )
            {
              CLIENTINFO::~CLIENTINFO(v13);
              DirectUI::HFree(v13, v14);
            }
          }
          RegCloseKey(phkResult);
        }
        RegCloseKey(hKey);
      }
LABEL_18:
      ++v6;
    }
    while ( v4 >= 0 );
    RegCloseKey(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f200  mov     [rsp-8+arg_10], rbx
0x18000f205  mov     [rsp-8+arg_18], rsi
0x18000f20a  push    rbp
0x18000f20b  push    rdi
0x18000f20c  push    r12
0x18000f20e  push    r14
0x18000f210  push    r15
0x18000f212  lea     rbp, [rsp-160h]
0x18000f21a  sub     rsp, 260h
0x18000f221  mov     rax, cs:__security_cookie
0x18000f228  xor     rax, rsp
0x18000f22b  mov     [rbp+180h+var_30], rax
0x18000f232  mov     r12b, dl
0x18000f235  mov     r9b, dl; bool
0x18000f238  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000f23f  mov     r8d, 20019h; unsigned int
0x18000f245  mov     r15, rcx
0x18000f248  xor     edi, edi
0x18000f24a  call    ?_OpenClientKey@ClientBlock@@AEAAPEAUHKEY__@@PEAU2@K_N@Z; ClientBlock::_OpenClientKey(HKEY__ *,ulong,bool)
0x18000f24f  mov     r14, rax
0x18000f252  test    rax, rax
0x18000f255  jz      loc_18000F399
0x18000f25b  xor     esi, esi
0x18000f25d  mov     r9d, 104h; cchName
0x18000f263  lea     r8, [rsp+280h+Name]; lpName
0x18000f268  mov     edx, esi; dwIndex
0x18000f26a  mov     rcx, r14; hKey
0x18000f26d  call    cs:__imp_RegEnumKeyW
0x18000f273  test    eax, eax
0x18000f275  jnz     loc_18000F390
0x18000f27b  mov     [rsp+280h+hKey], 0
0x18000f284  xor     ebx, ebx
0x18000f286  mov     rcx, [r15+0C8h]
0x18000f28d  mov     edx, [rcx]
0x18000f28f  mov     eax, edx
0x18000f291  and     eax, 0FFFFFFFh
0x18000f296  cmp     ebx, eax
0x18000f298  jnb     short loc_18000F2CA
0x18000f29a  add     rcx, 8
0x18000f29e  bt      edx, 1Ch
0x18000f2a2  jnb     short loc_18000F2A7
0x18000f2a4  mov     rcx, [rcx]
0x18000f2a7  mov     rcx, [rcx+rbx*8]
0x18000f2ab  mov     rcx, [rcx]; lpString1
0x18000f2ae  test    rcx, rcx
0x18000f2b1  jz      short loc_18000F2C6
0x18000f2b3  lea     rdx, [rsp+280h+Name]; lpString2
0x18000f2b8  call    cs:__imp_lstrcmpiW
0x18000f2be  test    eax, eax
0x18000f2c0  jz      loc_18000F386
0x18000f2c6  inc     ebx
0x18000f2c8  jmp     short loc_18000F286
0x18000f2ca  lea     rax, [rsp+280h+hKey]
0x18000f2cf  mov     ebx, 20019h
0x18000f2d4  mov     r9d, ebx; samDesired
0x18000f2d7  mov     [rsp+280h+phkResult], rax; phkResult
0x18000f2dc  xor     r8d, r8d; ulOptions
0x18000f2df  lea     rdx, [rsp+280h+Name]; lpSubKey
0x18000f2e4  mov     rcx, r14; hKey
0x18000f2e7  call    cs:__imp_RegOpenKeyExW
0x18000f2ed  test    eax, eax
0x18000f2ef  jnz     loc_18000F386
0x18000f2f5  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f2fa  lea     rax, [rsp+280h+var_248]
0x18000f2ff  mov     r9d, ebx; samDesired
0x18000f302  mov     [rsp+280h+phkResult], rax; phkResult
0x18000f307  xor     r8d, r8d; ulOptions
0x18000f30a  mov     [rsp+280h+var_248], 0
0x18000f313  lea     rdx, aInstallinfo; "InstallInfo"
0x18000f31a  call    cs:__imp_RegOpenKeyExW
0x18000f320  test    eax, eax
0x18000f322  jnz     short loc_18000F37B
0x18000f324  mov     rdx, [rsp+280h+var_248]; HKEY
0x18000f329  lea     r8, [rsp+280h+Name]; pszSrch
0x18000f32e  mov     rcx, [rsp+280h+hKey]; hkey
0x18000f333  mov     r9b, r12b; bool
0x18000f336  call    ?Create@CLIENTINFO@@SAPEAV1@PEAUHKEY__@@0PEBG_N@Z; CLIENTINFO::Create(HKEY__ *,HKEY__ *,ushort const *,bool)
0x18000f33b  mov     rbx, rax
0x18000f33e  test    rax, rax
0x18000f341  jz      short loc_18000F370
0x18000f343  mov     rcx, [r15+0C8h]
0x18000f34a  mov     r8, rax
0x18000f34d  mov     edx, [rcx]
0x18000f34f  and     edx, 0FFFFFFFh
0x18000f355  call    ?Insert@?$DynamicArrayBase@PEAVCLIENTINFO@@V?$DoubleAllocationPolicy@PEAVCLIENTINFO@@@DirectUI@@$00$0A@@DirectUI@@QEAAJIPEAVCLIENTINFO@@@Z; DirectUI::DynamicArrayBase<CLIENTINFO *,DirectUI::DoubleAllocationPolicy<CLIENTINFO *>,1,0>::Insert(uint,CLIENTINFO *)
0x18000f35a  mov     edi, eax
0x18000f35c  test    eax, eax
0x18000f35e  jns     short loc_18000F370
0x18000f360  mov     rcx, rbx; this
0x18000f363  call    ??1CLIENTINFO@@QEAA@XZ; CLIENTINFO::~CLIENTINFO(void)
0x18000f368  mov     rcx, rbx; this
0x18000f36b  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x18000f370  mov     rcx, [rsp+280h+var_248]; hKey
0x18000f375  call    cs:__imp_RegCloseKey
0x18000f37b  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f380  call    cs:__imp_RegCloseKey
0x18000f386  inc     esi
0x18000f388  test    edi, edi
0x18000f38a  jns     loc_18000F25D
0x18000f390  mov     rcx, r14; hKey
0x18000f393  call    cs:__imp_RegCloseKey
0x18000f399  mov     eax, edi
0x18000f39b  mov     rcx, [rbp+180h+var_30]
0x18000f3a2  xor     rcx, rsp; StackCookie
0x18000f3a5  call    __security_check_cookie
0x18000f3aa  lea     r11, [rsp+280h+var_20]
0x18000f3b2  mov     rbx, [r11+40h]
0x18000f3b6  mov     rsi, [r11+48h]
0x18000f3ba  mov     rsp, r11
0x18000f3bd  pop     r15
0x18000f3bf  pop     r14
0x18000f3c1  pop     r12
0x18000f3c3  pop     rdi
0x18000f3c4  pop     rbp
0x18000f3c5  retn
```
