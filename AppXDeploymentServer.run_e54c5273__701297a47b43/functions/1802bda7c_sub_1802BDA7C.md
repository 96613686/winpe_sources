# sub_1802BDA7C

- ea: `0x1802bda7c`
- end: `0x1802bdd32`
- name: `sub_1802BDA7C`
- size: `694`
- prototype: `__int64 __fastcall(SC_HANDLE **, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x1802bcf6c`

## callees

- `0x180059ef8`
- `0x18005a63c`
- `0x18007a044`
- `0x1800a2770`
- `0x18011cfc4`
- `0x180132494`
- `0x18013c650`
- `0x18013c798`
- `0x180153ff8`
- `0x1801c56e0`
- `0x18020ae2c`
- `0x180272fe0`
- `0x1802bda7c`
- `0x1802bfda4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bdb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bdb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bdb0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bdb0f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802bdb24`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1802bdb24`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802bdab0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1802bdab0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1802bdb7d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1802bdbe8`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1802bdb7d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1802bdbe8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1802bdc62`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1802bdc62`

## string_xrefs

- `0x1802bdc01`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdca2`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdcb7`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdccc`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdcde`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdcf6`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdd0b`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdd20`: `onecore\admin\appmodel\lifetimemanagers\servicelifetimemanager.cpp`
- `0x1802bdbf2`: `Error in QueryServiceConfig`

## pseudocode

```c
__int64 __fastcall sub_1802BDA7C(SC_HANDLE **a1, __int64 a2)
{
  SC_HANDLE *v4; // rdi
  SC_HANDLE v5; // rax
  int v6; // eax
  const WCHAR *StringRawBuffer; // rax
  SC_HANDLE v8; // rbx
  signed int LastError; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // eax
  LPQUERY_SERVICE_CONFIGW v13; // rdi
  unsigned int v14; // eax
  HSTRING string; // [rsp+60h] [rbp-20h] BYREF
  DWORD cbBufSize[2]; // [rsp+68h] [rbp-18h] BYREF
  LPQUERY_SERVICE_CONFIGW lpServiceConfig; // [rsp+70h] [rbp-10h]
  int v19; // [rsp+78h] [rbp-8h]
  void *retaddr; // [rsp+A8h] [rbp+28h]
  DWORD pcbBytesNeeded; // [rsp+B0h] [rbp+30h] BYREF
  SC_HANDLE dwStartType; // [rsp+C0h] [rbp+40h] BYREF
  SC_HANDLE hService; // [rsp+C8h] [rbp+48h] BYREF

  v4 = *a1;
  if ( !**a1 )
  {
    v5 = OpenSCManagerW(0, 0, 1u);
    sub_180272FE0(v4, v5);
    if ( !**a1 )
      sub_18020AE2C(retaddr, 526, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp");
  }
  string = 0;
  sub_18013C650(a2, &string);
  hService = 0;
  *(_QWORD *)cbBufSize = 0;
  lpServiceConfig = 0;
  v6 = sub_180059EF8(cbBufSize, 0);
  if ( v6 < 0 )
    sub_180132494(
      retaddr,
      536,
      "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
      (unsigned int)v6);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  dwStartType = OpenServiceW(**a1, StringRawBuffer, 0xF01FFu);
  sub_18011CFC4(&hService, &dwStartType);
  sub_1800A2770(&dwStartType);
  v8 = hService;
  if ( !hService )
    sub_18020AE2C(retaddr, 538, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp");
  if ( cbBufSize[0] )
    sub_18005A63C(cbBufSize);
  pcbBytesNeeded = 0;
  if ( QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded) )
    sub_180132494(retaddr, 542, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", 2147500037LL);
  LastError = GetLastError();
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  else
    v11 = (unsigned int)LastError;
  if ( LastError != 122 )
    sub_180132494(retaddr, 545, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp", v11);
  lpServiceConfig = 0;
  cbBufSize[0] = 0;
  v19 = 0;
  v12 = sub_18007A044(cbBufSize, pcbBytesNeeded, v10, v11);
  if ( v12 < 0 )
    sub_180132494(
      retaddr,
      548,
      "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
      (unsigned int)v12);
  v13 = lpServiceConfig;
  v14 = QueryServiceConfigW(v8, lpServiceConfig, cbBufSize[0], &pcbBytesNeeded);
  sub_1802BFDA4(
    retaddr,
    553,
    "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp",
    v14,
    "Error in QueryServiceConfig");
  if ( v13->dwStartType == 4 )
  {
    LODWORD(dwStartType) = 0;
    sub_18013C798(a2, &dwStartType);
    if ( (_DWORD)dwStartType != 4
      && !ChangeServiceConfigW(v8, 0xFFFFFFFF, (DWORD)dwStartType, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      sub_18020AE2C(retaddr, 576, "onecore\\admin\\appmodel\\lifetimemanagers\\servicelifetimemanager.cpp");
    }
  }
  PackageRepositoryFree_0(v13);
  sub_1800A2770(&hService);
  return sub_180153FF8(&string);
}

```

## disassembly

```asm
0x1802bda7c  mov     [rsp-28h+arg_8], rbx
0x1802bda81  push    rbp
0x1802bda82  push    rsi
0x1802bda83  push    rdi
0x1802bda84  push    r14
0x1802bda86  push    r15
0x1802bda88  mov     rbp, rsp
0x1802bda8b  sub     rsp, 80h
0x1802bda92  mov     rsi, rdx
0x1802bda95  mov     rbx, rcx
0x1802bda98  mov     rdi, [rcx]
0x1802bda9b  mov     r15d, 1
0x1802bdaa1  xor     r14d, r14d
0x1802bdaa4  cmp     [rdi], r14
0x1802bdaa7  jnz     short loc_1802BDAD6
0x1802bdaa9  mov     r8d, r15d; dwDesiredAccess
0x1802bdaac  xor     edx, edx; lpDatabaseName
0x1802bdaae  xor     ecx, ecx; lpMachineName
0x1802bdab0  call    cs:OpenSCManagerW
0x1802bdab6  mov     rdx, rax
0x1802bdab9  mov     rcx, rdi
0x1802bdabc  call    sub_180272FE0
0x1802bdac1  mov     rax, [rbx]
0x1802bdac4  cmp     [rax], r14
0x1802bdac7  setz    al
0x1802bdaca  mov     rcx, [rbp+28h]
0x1802bdace  test    al, al
0x1802bdad0  jnz     loc_1802BDCB7
0x1802bdad6  mov     [rbp+string], r14
0x1802bdada  lea     rdx, [rbp+string]
0x1802bdade  mov     rcx, rsi
0x1802bdae1  call    sub_18013C650
0x1802bdae6  mov     [rbp+hService], r14
0x1802bdaea  mov     qword ptr [rbp+cbBufSize], r14
0x1802bdaee  mov     [rbp+lpServiceConfig], r14
0x1802bdaf2  xor     edx, edx
0x1802bdaf4  lea     rcx, [rbp+cbBufSize]
0x1802bdaf8  call    sub_180059EF8
0x1802bdafd  mov     rcx, [rbp+28h]
0x1802bdb01  test    eax, eax
0x1802bdb03  js      loc_1802BDCC9
0x1802bdb09  xor     edx, edx; length
0x1802bdb0b  mov     rcx, [rbp+string]; string
0x1802bdb0f  call    cs:WindowsGetStringRawBuffer
0x1802bdb15  mov     rcx, [rbx]
0x1802bdb18  mov     r8d, 0F01FFh; dwDesiredAccess
0x1802bdb1e  mov     rdx, rax; lpServiceName
0x1802bdb21  mov     rcx, [rcx]; hSCManager
0x1802bdb24  call    cs:OpenServiceW
0x1802bdb2a  mov     [rbp+dwStartType], rax
0x1802bdb2e  lea     rdx, [rbp+dwStartType]
0x1802bdb32  lea     rcx, [rbp+hService]
0x1802bdb36  call    sub_18011CFC4
0x1802bdb3b  lea     rcx, [rbp+dwStartType]
0x1802bdb3f  call    sub_1800A2770
0x1802bdb44  mov     rbx, [rbp+hService]
0x1802bdb48  test    rbx, rbx
0x1802bdb4b  setz    al
0x1802bdb4e  mov     rcx, [rbp+28h]
0x1802bdb52  test    al, al
0x1802bdb54  jnz     loc_1802BDCDE
0x1802bdb5a  cmp     [rbp+cbBufSize], r14d
0x1802bdb5e  jz      short loc_1802BDB69
0x1802bdb60  lea     rcx, [rbp+cbBufSize]
0x1802bdb64  call    sub_18005A63C
0x1802bdb69  mov     [rbp+pcbBytesNeeded], r14d
0x1802bdb6d  mov     rdi, [rbp+28h]
0x1802bdb71  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x1802bdb75  xor     r8d, r8d; cbBufSize
0x1802bdb78  xor     edx, edx; lpServiceConfig
0x1802bdb7a  mov     rcx, rbx; hService
0x1802bdb7d  call    cs:QueryServiceConfigW
0x1802bdb83  test    eax, eax
0x1802bdb85  jnz     loc_1802BDCF0
0x1802bdb8b  call    cs:GetLastError
0x1802bdb91  test    eax, eax
0x1802bdb93  jg      short loc_1802BDB9A
0x1802bdb95  mov     r9d, eax
0x1802bdb98  jmp     short loc_1802BDBA5
0x1802bdb9a  movzx   r9d, ax
0x1802bdb9e  or      r9d, 80070000h
0x1802bdba5  mov     rcx, [rbp+28h]
0x1802bdba9  cmp     eax, 7Ah ; 'z'
0x1802bdbac  jnz     loc_1802BDD0B
0x1802bdbb2  mov     [rbp+lpServiceConfig], r14
0x1802bdbb6  mov     [rbp+cbBufSize], r14d
0x1802bdbba  mov     [rbp+var_8], r14d
0x1802bdbbe  mov     edx, [rbp+pcbBytesNeeded]
0x1802bdbc1  lea     rcx, [rbp+cbBufSize]
0x1802bdbc5  call    sub_18007A044
0x1802bdbca  mov     rcx, [rbp+28h]
0x1802bdbce  test    eax, eax
0x1802bdbd0  js      loc_1802BDD1D
0x1802bdbd6  lea     r9, [rbp+pcbBytesNeeded]; pcbBytesNeeded
0x1802bdbda  mov     r8d, [rbp+cbBufSize]; cbBufSize
0x1802bdbde  mov     rdi, [rbp+lpServiceConfig]
0x1802bdbe2  mov     rdx, rdi; lpServiceConfig
0x1802bdbe5  mov     rcx, rbx; hService
0x1802bdbe8  call    cs:QueryServiceConfigW
0x1802bdbee  mov     rcx, [rbp+28h]
0x1802bdbf2  lea     r8, aErrorInQueryse; "Error in QueryServiceConfig"
0x1802bdbf9  mov     [rsp+80h+lpBinaryPathName], r8
0x1802bdbfe  mov     r9d, eax
0x1802bdc01  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdc08  mov     edx, 229h
0x1802bdc0d  call    sub_1802BFDA4
0x1802bdc12  cmp     dword ptr [rdi+4], 4
0x1802bdc16  jnz     short loc_1802BDC6C
0x1802bdc18  mov     dword ptr [rbp+dwStartType], r14d
0x1802bdc1c  lea     rdx, [rbp+dwStartType]
0x1802bdc20  mov     rcx, rsi
0x1802bdc23  call    sub_18013C798
0x1802bdc28  mov     r8d, dword ptr [rbp+dwStartType]; dwStartType
0x1802bdc2c  cmp     r8d, 4
0x1802bdc30  jz      short loc_1802BDC6C
0x1802bdc32  mov     rsi, [rbp+28h]
0x1802bdc36  mov     [rsp+80h+lpDisplayName], r14; lpDisplayName
0x1802bdc3b  mov     [rsp+80h+lpPassword], r14; lpPassword
0x1802bdc40  mov     [rsp+80h+lpServiceStartName], r14; lpServiceStartName
0x1802bdc45  mov     [rsp+80h+lpDependencies], r14; lpDependencies
0x1802bdc4a  mov     [rsp+80h+lpdwTagId], r14; lpdwTagId
0x1802bdc4f  mov     [rsp+80h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1802bdc54  mov     [rsp+80h+lpBinaryPathName], r14; lpBinaryPathName
0x1802bdc59  or      edx, 0FFFFFFFFh; dwServiceType
0x1802bdc5c  mov     r9d, edx; dwErrorControl
0x1802bdc5f  mov     rcx, rbx; hService
0x1802bdc62  call    cs:ChangeServiceConfigW
0x1802bdc68  test    eax, eax
0x1802bdc6a  jz      short loc_1802BDCA2
0x1802bdc6c  mov     rdx, r15
0x1802bdc6f  mov     rcx, rdi
0x1802bdc72  call    PackageRepositoryFree_0
0x1802bdc77  nop
0x1802bdc78  lea     rcx, [rbp+hService]
0x1802bdc7c  call    sub_1800A2770
0x1802bdc81  nop
0x1802bdc82  lea     rcx, [rbp+string]
0x1802bdc86  call    sub_180153FF8
0x1802bdc8b  mov     rbx, [rsp+80h+arg_8]
0x1802bdc93  add     rsp, 80h
0x1802bdc9a  pop     r15
0x1802bdc9c  pop     r14
0x1802bdc9e  pop     rdi
0x1802bdc9f  pop     rsi
0x1802bdca0  pop     rbp
0x1802bdca1  retn
0x1802bdca2  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdca9  mov     edx, 240h
0x1802bdcae  mov     rcx, rsi
0x1802bdcb1  call    sub_18020AE2C
0x1802bdcb7  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdcbe  mov     edx, 20Eh
0x1802bdcc3  call    sub_18020AE2C
0x1802bdcc9  mov     r9d, eax
0x1802bdccc  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdcd3  mov     edx, 218h
0x1802bdcd8  call    sub_180132494
0x1802bdcde  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdce5  mov     edx, 21Ah
0x1802bdcea  call    sub_18020AE2C
0x1802bdcf0  mov     r9d, 80004005h
0x1802bdcf6  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdcfd  mov     edx, 21Eh
0x1802bdd02  mov     rcx, rdi
0x1802bdd05  call    sub_180132494
0x1802bdd0b  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdd12  mov     edx, 221h
0x1802bdd17  call    sub_180132494
0x1802bdd1d  mov     r9d, eax
0x1802bdd20  lea     r8, aOnecoreAdminAp_100; "onecore\\admin\\appmodel\\lifetimemanag"...
0x1802bdd27  mov     edx, 224h
0x1802bdd2c  call    sub_180132494
```
