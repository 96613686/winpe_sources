# CreateCLSIDRegKey

- ea: `0x18000ffb4`
- end: `0x180010127`
- name: `CreateCLSIDRegKey`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000fb80`

## callees

- `0x18000e3a0`
- `0x18000fd40`
- `0x18000fd90`
- `0x18000fdd0`
- `0x18000ffb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000ffeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000ffeb`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180010048`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18001009e`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x180010048`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18001009e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800100d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800100d1`

## string_xrefs

- `0x1800100bc`: `ThreadingModel`

## pseudocode

```c
int CreateCLSIDRegKey()
{
  const struct _GUID *v0; // rcx
  int result; // eax
  int v2; // ebx
  __int64 cbData; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v5; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v7[8]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v8[80]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Filename[272]; // [rsp+F0h] [rbp-10h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = MakeCLSIDRegPath(v0, v8);
  v2 = 0;
  if ( result >= 0 )
  {
    hKey = 0;
    CAutoHKey::CAutoHKey((CAutoHKey *)v6, HKEY_CLASSES_ROOT, v8, &hKey);
    if ( !hKey || RegSetValueA(hKey, 0, 1u, "MP3 Decoder DMO", 0xFu) )
    {
      CAutoHKey::~CAutoHKey((CAutoHKey *)v6);
      return -2147467259;
    }
    else
    {
      v5 = 0;
      CAutoHKey::CAutoHKey((CAutoHKey *)v7, hKey, L"InprocServer32", &v5);
      if ( !v5 )
        goto LABEL_9;
      cbData = -1;
      do
        ++cbData;
      while ( Filename[cbData] );
      if ( RegSetValueA(v5, 0, 1u, Filename, cbData) || RegSetValueExA(v5, "ThreadingModel", 0, 1u, "Both", 5u) )
LABEL_9:
        v2 = -2147467259;
      CAutoHKey::~CAutoHKey((CAutoHKey *)v7);
      CAutoHKey::~CAutoHKey((CAutoHKey *)v6);
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ffb4  mov     [rsp-8+arg_0], rbx
0x18000ffb9  push    rbp
0x18000ffba  lea     rbp, [rsp-110h]
0x18000ffc2  sub     rsp, 210h
0x18000ffc9  mov     rax, cs:__security_cookie
0x18000ffd0  xor     rax, rsp
0x18000ffd3  mov     [rbp+110h+var_10], rax
0x18000ffda  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18000ffe1  lea     rdx, [rbp+110h+Filename]; lpFilename
0x18000ffe5  mov     r8d, 104h; nSize
0x18000ffeb  call    cs:__imp_GetModuleFileNameA
0x18000fff1  lea     rdx, [rsp+210h+var_1C0]; unsigned __int16 *
0x18000fff6  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18000fffb  xor     ebx, ebx
0x18000fffd  test    eax, eax
0x18000ffff  js      loc_180010107
0x180010005  lea     r9, [rsp+210h+hKey]; HKEY *
0x18001000a  mov     [rsp+210h+hKey], rbx
0x18001000f  lea     r8, [rsp+210h+var_1C0]; unsigned __int16 *
0x180010014  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18001001b  lea     rcx, [rsp+210h+var_1D0]; this
0x180010020  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180010025  mov     rcx, [rsp+210h+hKey]; hKey
0x18001002a  test    rcx, rcx
0x18001002d  jz      loc_1800100F8
0x180010033  lea     r9, Data; "MP3 Decoder DMO"
0x18001003a  mov     [rsp+210h+cbData], 0Fh; cbData
0x180010042  xor     edx, edx; lpSubKey
0x180010044  lea     r8d, [rbx+1]; dwType
0x180010048  call    cs:__imp_RegSetValueA
0x18001004e  test    eax, eax
0x180010050  jnz     loc_1800100F8
0x180010056  mov     rdx, [rsp+210h+hKey]; HKEY
0x18001005b  lea     r9, [rsp+210h+var_1D8]; HKEY *
0x180010060  lea     r8, aInprocserver32; "InprocServer32"
0x180010067  mov     [rsp+210h+var_1D8], rbx
0x18001006c  lea     rcx, [rsp+210h+var_1C8]; this
0x180010071  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180010076  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18001007b  test    rcx, rcx
0x18001007e  jz      short loc_1800100DB
0x180010080  lea     rdx, [rbp+110h+Filename]
0x180010084  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010088  inc     rax
0x18001008b  cmp     [rdx+rax], bl
0x18001008e  jnz     short loc_180010088
0x180010090  xor     edx, edx; lpSubKey
0x180010092  mov     [rsp+210h+cbData], eax; cbData
0x180010096  lea     r9, [rbp+110h+Filename]; lpData
0x18001009a  lea     r8d, [rdx+1]; dwType
0x18001009e  call    cs:__imp_RegSetValueA
0x1800100a4  test    eax, eax
0x1800100a6  jnz     short loc_1800100DB
0x1800100a8  mov     rcx, [rsp+210h+var_1D8]; hKey
0x1800100ad  lea     rax, aBoth; "Both"
0x1800100b4  mov     [rsp+210h+var_1E8], 5; cbData
0x1800100bc  lea     rdx, ValueName; "ThreadingModel"
0x1800100c3  mov     r9d, 1; dwType
0x1800100c9  mov     qword ptr [rsp+210h+cbData], rax; lpData
0x1800100ce  xor     r8d, r8d; Reserved
0x1800100d1  call    cs:__imp_RegSetValueExA
0x1800100d7  test    eax, eax
0x1800100d9  jz      short loc_1800100E0
0x1800100db  mov     ebx, 80004005h
0x1800100e0  lea     rcx, [rsp+210h+var_1C8]; this
0x1800100e5  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x1800100ea  lea     rcx, [rsp+210h+var_1D0]; this
0x1800100ef  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x1800100f4  mov     eax, ebx
0x1800100f6  jmp     short loc_180010107
0x1800100f8  lea     rcx, [rsp+210h+var_1D0]; this
0x1800100fd  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x180010102  mov     eax, 80004005h
0x180010107  mov     rcx, [rbp+110h+var_10]
0x18001010e  xor     rcx, rsp; StackCookie
0x180010111  call    __security_check_cookie
0x180010116  mov     rbx, [rsp+210h+arg_0]
0x18001011e  add     rsp, 210h
0x180010125  pop     rbp
0x180010126  retn
```
