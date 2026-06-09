# RegisterLocalServer(_GUID,_GUID)

- ea: `0x409551`
- end: `0x4098b5`
- name: `?RegisterLocalServer@@YGJU_GUID@@U1@@Z`
- size: `868`
- prototype: `unsigned int __stdcall(GUID, GUID)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x409212`

## callees

- `0x402625`
- `0x40285e`
- `0x402918`
- `0x409551`
- `0x409c72`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x40973f`
- `ADVAPI32!RegDeleteValueW` at `0x40973f`
- `ADVAPI32!RegSetValueExW` at `0x4096f2`
- `ADVAPI32!RegSetValueExW` at `0x40977a`
- `ADVAPI32!RegSetValueExW` at `0x4097bb`
- `ADVAPI32!RegSetValueExW` at `0x4096f2`
- `ADVAPI32!RegSetValueExW` at `0x40977a`
- `ADVAPI32!RegSetValueExW` at `0x4097bb`
- `ADVAPI32!RegCreateKeyExW` at `0x409671`
- `ADVAPI32!RegCreateKeyExW` at `0x4096ce`
- `ADVAPI32!RegCreateKeyExW` at `0x409724`
- `ADVAPI32!RegCreateKeyExW` at `0x409827`
- `ADVAPI32!RegCreateKeyExW` at `0x409854`
- `ADVAPI32!RegCreateKeyExW` at `0x409671`
- `ADVAPI32!RegCreateKeyExW` at `0x4096ce`
- `ADVAPI32!RegCreateKeyExW` at `0x409724`
- `ADVAPI32!RegCreateKeyExW` at `0x409827`
- `ADVAPI32!RegCreateKeyExW` at `0x409854`
- `ADVAPI32!RegCloseKey` at `0x4097c9`
- `ADVAPI32!RegCloseKey` at `0x4097ec`
- `ADVAPI32!RegCloseKey` at `0x4097f8`
- `ADVAPI32!RegCloseKey` at `0x409873`
- `ADVAPI32!RegCloseKey` at `0x40987f`
- `ADVAPI32!RegCloseKey` at `0x4097c9`
- `ADVAPI32!RegCloseKey` at `0x4097ec`
- `ADVAPI32!RegCloseKey` at `0x4097f8`
- `ADVAPI32!RegCloseKey` at `0x409873`
- `ADVAPI32!RegCloseKey` at `0x40987f`
- `KERNEL32!GetCurrentProcess` at `0x4095ce`
- `KERNEL32!GetCurrentProcess` at `0x4095ce`
- `KERNEL32!GetModuleHandleW` at `0x4095c6`
- `KERNEL32!GetModuleHandleW` at `0x4095c6`
- `KERNEL32!K32GetModuleBaseNameW` at `0x4095e3`
- `KERNEL32!K32GetModuleBaseNameW` at `0x4095e3`
- `KERNEL32!GetLastError` at `0x409887`
- `KERNEL32!GetLastError` at `0x409887`
- `ole32!StringFromGUID2` at `0x409691`
- `ole32!StringFromGUID2` at `0x4096a4`
- `ole32!StringFromGUID2` at `0x409691`
- `ole32!StringFromGUID2` at `0x4096a4`

## string_xrefs

- `0x409667`: `CLSID`
- `0x409734`: `ThreadingModel`

## pseudocode

```c
unsigned int __stdcall RegisterLocalServer(GUID a1, GUID a2)
{
  HMODULE ModuleHandleW; // esi
  HANDLE CurrentProcess; // eax
  int LastError; // esi
  unsigned int result; // eax
  unsigned int v6; // [esp+0h] [ebp-6FCh]
  unsigned int v7; // [esp+0h] [ebp-6FCh]
  const unsigned __int16 *v8; // [esp+4h] [ebp-6F8h]
  unsigned __int16 *v9; // [esp+4h] [ebp-6F8h]
  HKEY v10; // [esp+Ch] [ebp-6F0h] BYREF
  HKEY phkResult; // [esp+10h] [ebp-6ECh] BYREF
  DWORD dwDisposition; // [esp+14h] [ebp-6E8h] BYREF
  HKEY v13; // [esp+18h] [ebp-6E4h] BYREF
  HKEY hKey; // [esp+1Ch] [ebp-6E0h] BYREF
  GUID v15; // [esp+20h] [ebp-6DCh] BYREF
  GUID rguid; // [esp+30h] [ebp-6CCh] BYREF
  WCHAR BaseName[260]; // [esp+40h] [ebp-6BCh] BYREF
  BYTE Data[2]; // [esp+248h] [ebp-4B4h] BYREF
  _BYTE v19[518]; // [esp+24Ah] [ebp-4B2h] BYREF
  BYTE v20[520]; // [esp+450h] [ebp-2ACh] BYREF
  OLECHAR sz[40]; // [esp+658h] [ebp-A4h] BYREF
  OLECHAR SubKey[40]; // [esp+6A8h] [ebp-54h] BYREF

  rguid = a1;
  v15 = a2;
  qmemcpy(v20, L"%ProgramFiles%\\Internet Explorer\\", 0x44u);
  memset(&v20[68], 0, 0x1C4u);
  memset(BaseName, 0, sizeof(BaseName));
  ModuleHandleW = GetModuleHandleW(0);
  CurrentProcess = GetCurrentProcess();
  if ( K32GetModuleBaseNameW(CurrentProcess, ModuleHandleW, BaseName, 0x104u) )
  {
    LastError = StringCchCatW(BaseName, v6, v8);
    if ( LastError < 0 )
      goto LABEL_21;
    *(_WORD *)Data = 0;
    memset(v19, 0, sizeof(v19));
    LastError = QuotePath(260, v20, (unsigned __int16 *)Data, v7, v9);
    if ( LastError < 0 )
      goto LABEL_21;
    LastError = RegCreateKeyExW(
                  HKEY_CLASSES_ROOT,
                  L"CLSID",
                  0,
                  (LPWSTR)L"REG_SZ",
                  0,
                  0xF003Fu,
                  0,
                  &phkResult,
                  &dwDisposition);
    if ( LastError )
      goto LABEL_21;
    StringFromGUID2(&rguid, sz, 39);
    StringFromGUID2(&v15, SubKey, 39);
    LastError = RegCreateKeyExW(phkResult, sz, 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( !LastError )
    {
      LastError = RegSetValueExW(hKey, L"AppID", 0, 1u, (const BYTE *)SubKey, 0x4Eu);
      if ( !LastError )
      {
        LastError = RegCreateKeyExW(
                      hKey,
                      L"LocalServer32",
                      0,
                      (LPWSTR)L"REG_EXPAND_SZ",
                      0,
                      0xF003Fu,
                      0,
                      &v13,
                      &dwDisposition);
        if ( !LastError )
        {
          RegDeleteValueW(v13, L"ThreadingModel");
          LastError = RegSetValueExW(v13, &::Data, 0, 2u, Data, 2 * wcslen((const unsigned __int16 *)Data) + 2);
          if ( !LastError )
            LastError = RegSetValueExW(
                          v13,
                          L"ServerExecutable",
                          0,
                          2u,
                          v20,
                          2 * wcslen((const unsigned __int16 *)v20) + 2);
          RegCloseKey(v13);
          if ( !LastError )
            LastError = RegisterCLSID(hKey, (unsigned __int16 *)v20);
        }
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
    if ( LastError )
      goto LABEL_21;
    LastError = RegCreateKeyExW(HKEY_CLASSES_ROOT, L"AppID", 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &v10, &dwDisposition);
    if ( LastError )
      goto LABEL_21;
    LastError = RegCreateKeyExW(v10, SubKey, 0, (LPWSTR)L"REG_SZ", 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( !LastError )
    {
      LastError = RegisterAppID(hKey);
      RegCloseKey(hKey);
    }
    RegCloseKey(v10);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
    return 0;
LABEL_21:
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return LastError;
  return result;
}

```

## disassembly

```asm
0x409551  mov     edi, edi
0x409553  push    ebp
0x409554  mov     ebp, esp
0x409556  sub     esp, 6F0h
0x40955c  mov     eax, ___security_cookie
0x409561  xor     eax, ebp
0x409563  mov     [ebp+var_4], eax
0x409566  push    ebx
0x409567  push    esi; unsigned __int16 *
0x409568  push    edi; HKEY
0x409569  lea     esi, [ebp+arg_0]
0x40956c  lea     edi, [ebp+rguid]
0x409572  movsd
0x409573  lea     eax, [ebp+var_268]
0x409579  push    11h
0x40957b  pop     ecx
0x40957c  push    1C4h; Size
0x409581  movsd
0x409582  movsd
0x409583  movsd
0x409584  lea     esi, [ebp+arg_10]
0x409587  lea     edi, [ebp+var_6DC]
0x40958d  movsd
0x40958e  movsd
0x40958f  movsd
0x409590  movsd
0x409591  mov     esi, offset aProgramfilesIn; "%ProgramFiles%\\Internet Explorer\\"
0x409596  lea     edi, [ebp+var_2AC]
0x40959c  rep movsd
0x40959e  xor     edi, edi
0x4095a0  push    edi; Val
0x4095a1  push    eax; void *
0x4095a2  call    _memset
0x4095a7  xor     eax, eax
0x4095a9  push    206h; Size
0x4095ae  mov     [ebp+BaseName], ax
0x4095b5  lea     eax, [ebp+var_6BA]
0x4095bb  push    edi; Val
0x4095bc  push    eax; void *
0x4095bd  call    _memset
0x4095c2  add     esp, 18h
0x4095c5  push    edi; lpModuleName
0x4095c6  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x4095cc  mov     esi, eax
0x4095ce  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x4095d4  mov     ebx, 104h
0x4095d9  lea     ecx, [ebp+BaseName]
0x4095df  push    ebx; nSize
0x4095e0  push    ecx; lpBaseName
0x4095e1  push    esi; hModule
0x4095e2  push    eax; hProcess
0x4095e3  call    ds:__imp__K32GetModuleBaseNameW@16; K32GetModuleBaseNameW(x,x,x,x)
0x4095e9  test    eax, eax
0x4095eb  jz      loc_409887
0x4095f1  lea     eax, [ebp+BaseName]
0x4095f7  mov     edx, ebx
0x4095f9  push    eax; unsigned __int16 *
0x4095fa  lea     ecx, [ebp+var_2AC]
0x409600  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x409605  mov     esi, eax
0x409607  test    esi, esi
0x409609  js      loc_409897
0x40960f  xor     eax, eax
0x409611  push    206h; Size
0x409616  mov     word ptr [ebp+Data], ax
0x40961d  lea     eax, [ebp+var_4B2]
0x409623  push    edi; Val
0x409624  push    eax; void *
0x409625  call    _memset
0x40962a  add     esp, 0Ch
0x40962d  lea     eax, [ebp+Data]
0x409633  mov     edx, ebx
0x409635  lea     ecx, [ebp+var_2AC]
0x40963b  push    eax; unsigned __int16 *
0x40963c  call    ?QuotePath@@YGJPBGKPAG@Z; QuotePath(ushort const *,ulong,ushort *)
0x409641  mov     esi, eax
0x409643  test    esi, esi
0x409645  js      loc_409897
0x40964b  lea     eax, [ebp+dwDisposition]
0x409651  mov     ebx, 0F003Fh
0x409656  push    eax; lpdwDisposition
0x409657  lea     eax, [ebp+phkResult]
0x40965d  push    eax; phkResult
0x40965e  push    edi; lpSecurityAttributes
0x40965f  push    ebx; samDesired
0x409660  push    edi; dwOptions
0x409661  push    offset Class; "REG_SZ"
0x409666  push    edi; Reserved
0x409667  push    offset aClsid_0; "CLSID"
0x40966c  push    80000000h; hKey
0x409671  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x409677  mov     esi, eax
0x409679  test    esi, esi
0x40967b  jnz     loc_409897
0x409681  push    27h ; '''; cchMax
0x409683  lea     eax, [ebp+sz]
0x409689  push    eax; lpsz
0x40968a  lea     eax, [ebp+rguid]
0x409690  push    eax; rguid
0x409691  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x409697  push    27h ; '''; cchMax
0x409699  lea     eax, [ebp+SubKey]
0x40969c  push    eax; lpsz
0x40969d  lea     eax, [ebp+var_6DC]
0x4096a3  push    eax; rguid
0x4096a4  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x4096aa  lea     eax, [ebp+dwDisposition]
0x4096b0  push    eax; lpdwDisposition
0x4096b1  lea     eax, [ebp+hKey]
0x4096b7  push    eax; phkResult
0x4096b8  push    edi; lpSecurityAttributes
0x4096b9  push    ebx; samDesired
0x4096ba  push    edi; dwOptions
0x4096bb  push    offset Class; "REG_SZ"
0x4096c0  push    edi; Reserved
0x4096c1  lea     eax, [ebp+sz]
0x4096c7  push    eax; lpSubKey
0x4096c8  push    [ebp+phkResult]; hKey
0x4096ce  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x4096d4  mov     esi, eax
0x4096d6  test    esi, esi
0x4096d8  jnz     loc_4097F2
0x4096de  push    4Eh ; 'N'; cbData
0x4096e0  lea     eax, [ebp+SubKey]
0x4096e3  push    eax; lpData
0x4096e4  push    1; dwType
0x4096e6  push    edi; Reserved
0x4096e7  push    offset aAppid; "AppID"
0x4096ec  push    [ebp+hKey]; hKey
0x4096f2  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x4096f8  mov     esi, eax
0x4096fa  test    esi, esi
0x4096fc  jnz     loc_4097E6
0x409702  lea     eax, [ebp+dwDisposition]
0x409708  push    eax; lpdwDisposition
0x409709  lea     eax, [ebp+var_6E4]
0x40970f  push    eax; phkResult
0x409710  push    edi; lpSecurityAttributes
0x409711  push    ebx; samDesired
0x409712  push    edi; dwOptions
0x409713  push    offset aRegExpandSz; "REG_EXPAND_SZ"
0x409718  push    edi; Reserved
0x409719  push    offset aLocalserver32; "LocalServer32"
0x40971e  push    [ebp+hKey]; hKey
0x409724  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x40972a  mov     esi, eax
0x40972c  test    esi, esi
0x40972e  jnz     loc_4097E6
0x409734  push    offset aThreadingmodel; "ThreadingModel"
0x409739  push    [ebp+var_6E4]; hKey
0x40973f  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x409745  lea     ecx, [ebp+Data]
0x40974b  lea     edx, [ecx+2]
0x40974e  mov     ax, [ecx]
0x409751  add     ecx, 2
0x409754  cmp     ax, di
0x409757  jnz     short loc_40974E
0x409759  sub     ecx, edx
0x40975b  sar     ecx, 1
0x40975d  lea     eax, ds:2[ecx*2]
0x409764  push    eax; cbData
0x409765  lea     eax, [ebp+Data]
0x40976b  push    eax; lpData
0x40976c  push    2; dwType
0x40976e  push    edi; Reserved
0x40976f  push    offset Data; lpValueName
0x409774  push    [ebp+var_6E4]; hKey
0x40977a  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x409780  mov     esi, eax
0x409782  test    esi, esi
0x409784  jnz     short loc_4097C3
0x409786  lea     ecx, [ebp+var_2AC]
0x40978c  lea     edx, [ecx+2]
0x40978f  mov     ax, [ecx]
0x409792  add     ecx, 2
0x409795  cmp     ax, di
0x409798  jnz     short loc_40978F
0x40979a  sub     ecx, edx
0x40979c  sar     ecx, 1
0x40979e  lea     eax, ds:2[ecx*2]
0x4097a5  push    eax; cbData
0x4097a6  lea     eax, [ebp+var_2AC]
0x4097ac  push    eax; lpData
0x4097ad  push    2; dwType
0x4097af  push    edi; Reserved
0x4097b0  push    offset aServerexecutab; "ServerExecutable"
0x4097b5  push    [ebp+var_6E4]; hKey
0x4097bb  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x4097c1  mov     esi, eax
0x4097c3  push    [ebp+var_6E4]; hKey
0x4097c9  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4097cf  test    esi, esi
0x4097d1  jnz     short loc_4097E6
0x4097d3  mov     ecx, [ebp+hKey]
0x4097d9  lea     edx, [ebp+var_2AC]
0x4097df  call    ?RegisterCLSID@@YGKPAUHKEY__@@PBG@Z; RegisterCLSID(HKEY__ *,ushort const *)
0x4097e4  mov     esi, eax
0x4097e6  push    [ebp+hKey]; hKey
0x4097ec  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4097f2  push    [ebp+phkResult]; hKey
0x4097f8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x4097fe  test    esi, esi
0x409800  jnz     loc_409897
0x409806  lea     eax, [ebp+dwDisposition]
0x40980c  push    eax; lpdwDisposition
0x40980d  lea     eax, [ebp+var_6F0]
0x409813  push    eax; phkResult
0x409814  push    edi; lpSecurityAttributes
0x409815  push    ebx; samDesired
0x409816  push    edi; dwOptions
0x409817  push    offset Class; "REG_SZ"
0x40981c  push    edi; Reserved
0x40981d  push    offset aAppid; "AppID"
0x409822  push    80000000h; hKey
0x409827  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x40982d  mov     esi, eax
0x40982f  test    esi, esi
0x409831  jnz     short loc_409897
0x409833  lea     eax, [ebp+dwDisposition]
0x409839  push    eax; lpdwDisposition
0x40983a  lea     eax, [ebp+hKey]
0x409840  push    eax; phkResult
0x409841  push    edi; lpSecurityAttributes
0x409842  push    ebx; samDesired
0x409843  push    edi; dwOptions
0x409844  push    offset Class; "REG_SZ"
0x409849  push    edi; Reserved
0x40984a  lea     eax, [ebp+SubKey]
0x40984d  push    eax; lpSubKey
0x40984e  push    [ebp+var_6F0]; hKey
0x409854  call    ds:__imp__RegCreateKeyExW@36; RegCreateKeyExW(x,x,x,x,x,x,x,x,x)
0x40985a  mov     esi, eax
0x40985c  test    esi, esi
0x40985e  jnz     short loc_409879
0x409860  mov     ecx, [ebp+hKey]
0x409866  call    ?RegisterAppID@@YGKPAUHKEY__@@@Z; RegisterAppID(HKEY__ *)
0x40986b  push    [ebp+hKey]; hKey
0x409871  mov     esi, eax
0x409873  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x409879  push    [ebp+var_6F0]; hKey
0x40987f  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x409885  jmp     short loc_40988F
0x409887  call    ds:__imp__GetLastError@0; GetLastError()
0x40988d  mov     esi, eax
0x40988f  test    esi, esi
0x409891  jnz     short loc_409897
0x409893  mov     eax, edi
0x409895  jmp     short loc_4098A4
0x409897  movzx   eax, si
0x40989a  or      eax, 80070000h
0x40989f  test    esi, esi
0x4098a1  cmovle  eax, esi
0x4098a4  mov     ecx, [ebp+var_4]
0x4098a7  pop     edi
0x4098a8  pop     esi
0x4098a9  xor     ecx, ebp; StackCookie
0x4098ab  pop     ebx
0x4098ac  call    @__security_check_cookie@4; __security_check_cookie(x)
0x4098b1  leave
0x4098b2  retn    20h ; ' '
```
