# SetSystemRestorePoint

- ea: `0x180002788`
- end: `0x180002a15`
- name: `SetSystemRestorePoint`
- size: `653`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003370`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x180002024`
- `0x180002788`
- `0x180002a1c`
- `0x180002aa0`
- `0x180012d70`
- `0x18001309c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002810`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002810`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002851`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000285c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000285c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800028b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800028b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800028d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800028d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002929`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002929`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800028f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800028f8`

## string_xrefs

- `0x1800027d4`: `Software\Policies\Microsoft\Windows\Installer`
- `0x1800028c9`: `sfc.dll`

## pseudocode

```c
__int64 __fastcall SetSystemRestorePoint(unsigned __int16 *a1, __int64 a2)
{
  int (*v4)(HINSTANCE, unsigned int, unsigned __int16 *, int); // rbx
  HINSTANCE HandleForCallingDll; // rax
  DWORD LastError; // edi
  HMODULE *v7; // rbx
  HMODULE Library; // rax
  __int64 result; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE *v15; // [rsp+40h] [rbp-C0h]
  _QWORD v16[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[256]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(v17, 0, 0x210u);
  memset(v16, 0, 12);
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\Installer", 0, 0x20019u, &hKey) )
    return 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  RegQueryValueExW(hKey, L"LimitSystemRestoreCheckpointing", 0, 0, Data, &cbData);
  RegCloseKey(hKey);
  if ( *(_DWORD *)Data )
    return 0;
  if ( !(unsigned int)LoadLoadString() )
    return 0;
  v4 = pfnLoadStringW;
  HandleForCallingDll = AppmgmtGetHandleForCallingDll();
  LastError = ((__int64 (__fastcall *)(HINSTANCE, __int64, unsigned __int16 *, __int64))v4)(
                HandleForCallingDll,
                3009,
                v18,
                256);
  if ( !LastError )
    return 0;
  v15 = (HMODULE *)LocalAlloc(0, 8u);
  v7 = v15;
  if ( v15 )
  {
    Library = LoadLibraryExW(L"sfc.dll", 0, 0x800u);
    *v7 = Library;
    if ( Library )
    {
      gpfnSRSetRetorePointW = (int (*)(struct _RESTOREPTINFOW *, struct _SMGRSTATUS *))GetProcAddress(
                                                                                         Library,
                                                                                         "SRSetRestorePointW");
      LastError = gpfnSRSetRetorePointW == 0 ? 0x7F : 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    v7 = 0;
  }
  *(_QWORD *)(a2 + 32) = v7;
  if ( LastError )
  {
    if ( v7 )
    {
      if ( *v7 )
        FreeLibrary(*v7);
      operator delete(v7);
    }
    *(_QWORD *)(a2 + 32) = 0;
    return 0;
  }
  if ( !v7 )
    return 0;
  v10 = -1;
  v17[0] = 102;
  v11 = -1;
  v17[1] = 0;
  do
    ++v11;
  while ( v18[v11] );
  if ( a1 )
  {
    do
      ++v10;
    while ( a1[v10] );
  }
  else
  {
    LODWORD(v10) = 0;
  }
  if ( (unsigned int)(v10 + v11) >= 0x100 )
  {
    StringCchCopyNW(&v18[(unsigned int)v11], (unsigned int)(256 - v11), a1, (unsigned int)(255 - v11));
    goto LABEL_27;
  }
  if ( (int)StringCchCopyW(&v18[(unsigned int)v11], (unsigned int)(255 - v11), a1) < 0 )
    return 0;
LABEL_27:
  result = ((__int64 (__fastcall *)(_QWORD *, _QWORD *))gpfnSRSetRetorePointW)(v17, v16);
  if ( (_DWORD)result )
    *(_QWORD *)(a2 + 48) = *(_QWORD *)((char *)v16 + 4);
  return result;
}

```

## disassembly

```asm
0x180002788  mov     [rsp-8+arg_10], rbx
0x18000278d  mov     [rsp-8+arg_18], rsi
0x180002792  push    rbp
0x180002793  push    rdi
0x180002794  push    r12
0x180002796  push    r14
0x180002798  push    r15
0x18000279a  lea     rbp, [rsp-180h]
0x1800027a2  sub     rsp, 280h
0x1800027a9  mov     rax, cs:__security_cookie
0x1800027b0  xor     rax, rsp
0x1800027b3  mov     [rbp+1A0h+var_30], rax
0x1800027ba  mov     r15, rdx
0x1800027bd  mov     r14, rcx
0x1800027c0  xor     edx, edx; Val
0x1800027c2  lea     rcx, [rsp+2A0h+var_240]; void *
0x1800027c7  mov     r8d, 210h; Size
0x1800027cd  call    memset_0
0x1800027d2  xor     eax, eax
0x1800027d4  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800027db  xor     r12d, r12d
0x1800027de  mov     [rsp+2A0h+var_258], rax
0x1800027e3  mov     [rsp+2A0h+var_250], eax
0x1800027e7  mov     r9d, 20019h; samDesired
0x1800027ed  lea     rax, [rsp+2A0h+hKey]
0x1800027f2  mov     [rsp+2A0h+hKey], r12
0x1800027f7  xor     r8d, r8d; ulOptions
0x1800027fa  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800027ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002806  mov     dword ptr [rsp+2A0h+Data], r12d
0x18000280b  mov     [rsp+2A0h+cbData], r12d
0x180002810  call    cs:__imp_RegOpenKeyExW
0x180002816  test    eax, eax
0x180002818  jnz     loc_180002940
0x18000281e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180002823  lea     rax, [rsp+2A0h+cbData]
0x180002828  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x18000282d  lea     rdx, aLimitsystemres; "LimitSystemRestoreCheckpointing"
0x180002834  lea     rax, [rsp+2A0h+Data]
0x180002839  mov     dword ptr [rsp+2A0h+Data], r12d
0x18000283e  xor     r9d, r9d; lpType
0x180002841  mov     [rsp+2A0h+phkResult], rax; lpData
0x180002846  xor     r8d, r8d; lpReserved
0x180002849  mov     [rsp+2A0h+cbData], 4
0x180002851  call    cs:__imp_RegQueryValueExW
0x180002857  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000285c  call    cs:__imp_RegCloseKey
0x180002862  cmp     dword ptr [rsp+2A0h+Data], r12d
0x180002867  jnz     loc_180002940
0x18000286d  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x180002872  test    eax, eax
0x180002874  jz      loc_180002940
0x18000287a  mov     rbx, cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x180002881  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x180002886  mov     rcx, rax
0x180002889  lea     r8, [rsp+2A0h+var_230]
0x18000288e  mov     esi, 100h
0x180002893  mov     rax, rbx
0x180002896  mov     r9d, esi
0x180002899  mov     edx, 0BC1h
0x18000289e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028a3  mov     edi, eax
0x1800028a5  test    eax, eax
0x1800028a7  jz      loc_180002940
0x1800028ad  lea     edx, [r12+8]; uBytes
0x1800028b2  xor     ecx, ecx; uFlags
0x1800028b4  call    cs:__imp_LocalAlloc
0x1800028ba  mov     [rsp+2A0h+var_260], rax
0x1800028bf  mov     rbx, rax
0x1800028c2  test    rax, rax
0x1800028c5  jz      short loc_180002911
0x1800028c7  xor     edx, edx; hFile
0x1800028c9  lea     rcx, LibFileName; "sfc.dll"
0x1800028d0  mov     r8d, 800h; dwFlags
0x1800028d6  call    cs:__imp_LoadLibraryExW
0x1800028dc  mov     [rbx], rax
0x1800028df  test    rax, rax
0x1800028e2  jnz     short loc_1800028EE
0x1800028e4  call    cs:__imp_GetLastError
0x1800028ea  mov     edi, eax
0x1800028ec  jmp     short loc_180002914
0x1800028ee  lea     rdx, ProcName; "SRSetRestorePointW"
0x1800028f5  mov     rcx, rax; hModule
0x1800028f8  call    cs:__imp_GetProcAddress
0x1800028fe  mov     cs:?gpfnSRSetRetorePointW@@3P6AHPEAU_RESTOREPTINFOW@@PEAU_SMGRSTATUS@@@ZEA, rax; int (*gpfnSRSetRetorePointW)(_RESTOREPTINFOW *,_SMGRSTATUS *)
0x180002905  neg     rax
0x180002908  sbb     edi, edi
0x18000290a  not     edi
0x18000290c  and     edi, 7Fh
0x18000290f  jmp     short loc_180002914
0x180002911  mov     rbx, r12
0x180002914  mov     [r15+20h], rbx
0x180002918  test    edi, edi
0x18000291a  jz      short loc_18000296D
0x18000291c  test    rbx, rbx
0x18000291f  jz      short loc_18000293C
0x180002921  mov     rcx, [rbx]; hLibModule
0x180002924  test    rcx, rcx
0x180002927  jz      short loc_18000292F
0x180002929  call    cs:__imp_FreeLibrary
0x18000292f  mov     edx, 8; unsigned __int64
0x180002934  mov     rcx, rbx; void *
0x180002937  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000293c  mov     [r15+20h], r12
0x180002940  xor     eax, eax
0x180002942  mov     rcx, [rbp+1A0h+var_30]
0x180002949  xor     rcx, rsp; StackCookie
0x18000294c  call    __security_check_cookie
0x180002951  lea     r11, [rsp+2A0h+var_20]
0x180002959  mov     rbx, [r11+40h]
0x18000295d  mov     rsi, [r11+48h]
0x180002961  mov     rsp, r11
0x180002964  pop     r15
0x180002966  pop     r14
0x180002968  pop     r12
0x18000296a  pop     rdi
0x18000296b  pop     rbp
0x18000296c  retn
0x18000296d  test    rbx, rbx
0x180002970  jz      short loc_180002940
0x180002972  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002976  mov     [rsp+2A0h+var_240], 66h ; 'f'
0x18000297f  mov     rcx, rdx
0x180002982  mov     [rsp+2A0h+var_238], r12
0x180002987  lea     rax, [rsp+2A0h+var_230]
0x18000298c  inc     rcx
0x18000298f  cmp     [rax+rcx*2], r12w
0x180002994  jnz     short loc_18000298C
0x180002996  test    r14, r14
0x180002999  jnz     short loc_1800029A0
0x18000299b  mov     edx, r12d
0x18000299e  jmp     short loc_1800029AA
0x1800029a0  inc     rdx
0x1800029a3  cmp     [r14+rdx*2], r12w
0x1800029a8  jnz     short loc_1800029A0
0x1800029aa  mov     eax, ecx
0x1800029ac  lea     r10, [rsp+2A0h+var_230]
0x1800029b1  mov     r9d, 0FFh
0x1800029b7  mov     r8, r14; unsigned __int16 *
0x1800029ba  sub     r9d, ecx; unsigned __int64
0x1800029bd  lea     r10, [r10+rax*2]
0x1800029c1  lea     eax, [rdx+rcx]
0x1800029c4  cmp     eax, esi
0x1800029c6  jb      short loc_1800029D6
0x1800029c8  sub     esi, ecx
0x1800029ca  mov     rcx, r10; unsigned __int16 *
0x1800029cd  mov     edx, esi; unsigned __int64
0x1800029cf  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800029d4  jmp     short loc_1800029E9
0x1800029d6  mov     rdx, r9; unsigned __int64
0x1800029d9  mov     rcx, r10; unsigned __int16 *
0x1800029dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800029e1  test    eax, eax
0x1800029e3  js      loc_180002940
0x1800029e9  mov     rax, cs:?gpfnSRSetRetorePointW@@3P6AHPEAU_RESTOREPTINFOW@@PEAU_SMGRSTATUS@@@ZEA; int (*gpfnSRSetRetorePointW)(_RESTOREPTINFOW *,_SMGRSTATUS *)
0x1800029f0  lea     rdx, [rsp+2A0h+var_258]
0x1800029f5  lea     rcx, [rsp+2A0h+var_240]
0x1800029fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ff  test    eax, eax
0x180002a01  jz      loc_180002942
0x180002a07  mov     rcx, [rsp+2A0h+var_258+4]
0x180002a0c  mov     [r15+30h], rcx
0x180002a10  jmp     loc_180002942
```
