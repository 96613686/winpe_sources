# CreateCLSIDRegKey

- ea: `0x18006c224`
- end: `0x18006c39d`
- name: `CreateCLSIDRegKey`
- size: `377`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006bbf0`

## callees

- `0x18000ab90`
- `0x18006c07c`
- `0x18006c0cc`
- `0x18006c110`
- `0x18006c224`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18006c25e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18006c25e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18006c347`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18006c347`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18006c2be`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18006c314`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18006c2be`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18006c314`

## string_xrefs

- `0x18006c332`: `ThreadingModel`

## pseudocode

```c
int __fastcall CreateCLSIDRegKey(struct _GUID *a1)
{
  int result; // eax
  int v3; // ebx
  __int64 cbData; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v6; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v7[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[8]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v9[80]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Filename[272]; // [rsp+F0h] [rbp-10h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = MakeCLSIDRegPath(a1, v9);
  v3 = 0;
  if ( result >= 0 )
  {
    hKey = 0;
    CAutoHKey::CAutoHKey((CAutoHKey *)v7, HKEY_CLASSES_ROOT, v9, &hKey);
    if ( !hKey || RegSetValueA(hKey, 0, 1u, "Resampler DMO", 0xDu) )
    {
      CAutoHKey::~CAutoHKey((CAutoHKey *)v7);
      return -2147467259;
    }
    else
    {
      v6 = 0;
      CAutoHKey::CAutoHKey((CAutoHKey *)v8, hKey, L"InprocServer32", &v6);
      if ( !v6 )
        goto LABEL_9;
      cbData = -1;
      do
        ++cbData;
      while ( Filename[cbData] );
      if ( RegSetValueA(v6, 0, 1u, Filename, cbData) || RegSetValueExA(v6, "ThreadingModel", 0, 1u, "Both", 5u) )
LABEL_9:
        v3 = -2147467259;
      CAutoHKey::~CAutoHKey((CAutoHKey *)v8);
      CAutoHKey::~CAutoHKey((CAutoHKey *)v7);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006c224  mov     [rsp-8+arg_8], rbx
0x18006c229  push    rbp
0x18006c22a  lea     rbp, [rsp-110h]
0x18006c232  sub     rsp, 210h
0x18006c239  mov     rax, cs:__security_cookie
0x18006c240  xor     rax, rsp
0x18006c243  mov     [rbp+110h+var_10], rax
0x18006c24a  mov     rbx, rcx
0x18006c24d  lea     rdx, [rbp+110h+Filename]; lpFilename
0x18006c251  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18006c258  mov     r8d, 104h; nSize
0x18006c25e  call    cs:__imp_GetModuleFileNameA
0x18006c264  lea     rdx, [rsp+210h+var_1C0]; unsigned __int16 *
0x18006c269  mov     rcx, rbx; struct _GUID *
0x18006c26c  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18006c271  xor     ebx, ebx
0x18006c273  test    eax, eax
0x18006c275  js      loc_18006C37D
0x18006c27b  lea     r9, [rsp+210h+hKey]; HKEY *
0x18006c280  mov     [rsp+210h+hKey], rbx
0x18006c285  lea     r8, [rsp+210h+var_1C0]; unsigned __int16 *
0x18006c28a  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18006c291  lea     rcx, [rsp+210h+var_1D0]; this
0x18006c296  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18006c29b  mov     rcx, [rsp+210h+hKey]; hKey
0x18006c2a0  test    rcx, rcx
0x18006c2a3  jz      loc_18006C36E
0x18006c2a9  lea     r9, Data; "Resampler DMO"
0x18006c2b0  mov     [rsp+210h+cbData], 0Dh; cbData
0x18006c2b8  xor     edx, edx; lpSubKey
0x18006c2ba  lea     r8d, [rbx+1]; dwType
0x18006c2be  call    cs:__imp_RegSetValueA
0x18006c2c4  test    eax, eax
0x18006c2c6  jnz     loc_18006C36E
0x18006c2cc  mov     rdx, [rsp+210h+hKey]; HKEY
0x18006c2d1  lea     r9, [rsp+210h+var_1D8]; HKEY *
0x18006c2d6  lea     r8, aInprocserver32; "InprocServer32"
0x18006c2dd  mov     [rsp+210h+var_1D8], rbx
0x18006c2e2  lea     rcx, [rsp+210h+var_1C8]; this
0x18006c2e7  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18006c2ec  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18006c2f1  test    rcx, rcx
0x18006c2f4  jz      short loc_18006C351
0x18006c2f6  lea     rdx, [rbp+110h+Filename]
0x18006c2fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c2fe  inc     rax
0x18006c301  cmp     [rdx+rax], bl
0x18006c304  jnz     short loc_18006C2FE
0x18006c306  xor     edx, edx; lpSubKey
0x18006c308  mov     [rsp+210h+cbData], eax; cbData
0x18006c30c  lea     r9, [rbp+110h+Filename]; lpData
0x18006c310  lea     r8d, [rdx+1]; dwType
0x18006c314  call    cs:__imp_RegSetValueA
0x18006c31a  test    eax, eax
0x18006c31c  jnz     short loc_18006C351
0x18006c31e  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18006c323  lea     rax, aBoth; "Both"
0x18006c32a  mov     [rsp+210h+var_1E8], 5; cbData
0x18006c332  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18006c339  mov     r9d, 1; dwType
0x18006c33f  mov     qword ptr [rsp+210h+cbData], rax; lpData
0x18006c344  xor     r8d, r8d; Reserved
0x18006c347  call    cs:__imp_RegSetValueExA
0x18006c34d  test    eax, eax
0x18006c34f  jz      short loc_18006C356
0x18006c351  mov     ebx, 80004005h
0x18006c356  lea     rcx, [rsp+210h+var_1C8]; this
0x18006c35b  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18006c360  lea     rcx, [rsp+210h+var_1D0]; this
0x18006c365  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18006c36a  mov     eax, ebx
0x18006c36c  jmp     short loc_18006C37D
0x18006c36e  lea     rcx, [rsp+210h+var_1D0]; this
0x18006c373  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18006c378  mov     eax, 80004005h
0x18006c37d  mov     rcx, [rbp+110h+var_10]
0x18006c384  xor     rcx, rsp; StackCookie
0x18006c387  call    __security_check_cookie
0x18006c38c  mov     rbx, [rsp+210h+arg_8]
0x18006c394  add     rsp, 210h
0x18006c39b  pop     rbp
0x18006c39c  retn
```
