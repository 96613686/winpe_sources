# CUHHandlerManager::ReadHandlerMappingsFromRegistry(void)

- ea: `0x180017618`
- end: `0x180017845`
- name: `?ReadHandlerMappingsFromRegistry@CUHHandlerManager@@AEAAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(CUHHandlerManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800175c4`

## callees

- `0x180003180`
- `0x180009438`
- `0x180017618`
- `0x1800197fc`
- `0x180061960`
- `0x180061d54`
- `0x180062558`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017811`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800176d6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800176d6`

## string_xrefs

- `0x180017669`: `SOFTWARE\Microsoft\WindowsUpdate\UpdateHandlers`
- `0x18001768b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800177ac`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800177d5`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUHHandlerManager::ReadHandlerMappingsFromRegistry(CUHHandlerManager *this)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  DWORD v4; // esi
  CUHPlugin *v5; // rbx
  unsigned int v6; // eax
  CUHPlugin *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+28h] [rbp-E0h]
  _QWORD v14[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+68h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\UpdateHandlers", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x164,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
           (const char *)v2,
           phkResult);
  }
  else
  {
    v4 = 0;
    while ( 1 )
    {
      cchName = 260;
      v5 = 0;
      v6 = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0);
      if ( v6 == 259 )
      {
LABEL_22:
        v3 = 0;
        goto LABEL_23;
      }
      if ( v6 )
        break;
      v7 = (CUHPlugin *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = -1;
        *((_QWORD *)v7 + 2) = 0;
        *(_QWORD *)v7 = &CUHPluginRegistryInfo::`vftable';
        *((_QWORD *)v7 + 3) = 0;
        *((_QWORD *)v7 + 4) = 0;
        *((_QWORD *)v7 + 5) = 0;
        *((_QWORD *)v7 + 6) = 0;
        *((_QWORD *)v7 + 7) = 0;
      }
      else
      {
        v5 = 0;
      }
      v14[1] = v5;
      v3 = v5 == 0 ? 0x8007000E : 0;
      if ( !v5 )
      {
        v10 = v3;
        v9 = 382;
        goto LABEL_16;
      }
      v8 = (*(__int64 (__fastcall **)(CUHPlugin *, HKEY, WCHAR *))(*(_QWORD *)v5 + 8LL))(v5, hKey, Name);
      v3 = v8;
      if ( v8 < 0 )
      {
        v9 = 383;
        goto LABEL_15;
      }
      v14[0] = v5;
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD *, _QWORD))(*((_QWORD *)this + 2) + 8LL))(
             (char *)this + 16,
             v14,
             0);
      v3 = v8;
      if ( v8 < 0 )
      {
        v9 = 384;
LABEL_15:
        v10 = (unsigned int)v8;
LABEL_16:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
          (const char *)v10,
          phkResulta);
        goto LABEL_20;
      }
      if ( ++v4 >= 0x14 )
        goto LABEL_22;
    }
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x17D,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
           (const char *)v6,
           phkResulta);
LABEL_20:
    if ( v5 )
    {
      CUHPlugin::~CUHPlugin(v5);
      operator delete(v5, (const struct std::nothrow_t *)0x40);
    }
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180017618  mov     rax, rsp
0x18001761b  mov     [rax+10h], rbx
0x18001761f  mov     [rax+18h], rsi
0x180017623  mov     [rax+20h], rdi
0x180017627  push    rbp
0x180017628  push    r14
0x18001762a  push    r15
0x18001762c  lea     rbp, [rax-198h]
0x180017633  sub     rsp, 280h
0x18001763a  mov     rax, cs:__security_cookie
0x180017641  xor     rax, rsp
0x180017644  mov     [rbp+190h+var_20], rax
0x18001764b  mov     r14, rcx
0x18001764e  xor     r15d, r15d
0x180017651  mov     [rsp+290h+hKey], r15
0x180017656  lea     rax, [rsp+290h+hKey]
0x18001765b  mov     [rsp+290h+phkResult], rax; unsigned int
0x180017660  mov     r9d, 20019h; samDesired
0x180017666  xor     r8d, r8d; ulOptions
0x180017669  lea     rdx, ?c_szUpdateHandlersKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Upd"...
0x180017670  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017677  call    cs:__imp_RegOpenKeyExW
0x18001767d  test    eax, eax
0x18001767f  jz      short loc_1800176A3
0x180017681  mov     rcx, [rbp+198h]; this
0x180017688  mov     r9d, eax; char *
0x18001768b  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017692  mov     edx, 164h; void *
0x180017697  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001769c  mov     edi, eax
0x18001769e  jmp     loc_180017807
0x1800176a3  mov     esi, r15d
0x1800176a6  mov     [rsp+290h+cchName], 104h
0x1800176ae  mov     rbx, r15
0x1800176b1  mov     [rsp+290h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800176b6  mov     [rsp+290h+lpcchClass], r15; lpcchClass
0x1800176bb  mov     [rsp+290h+lpClass], r15; lpClass
0x1800176c0  mov     [rsp+290h+phkResult], r15; unsigned int
0x1800176c5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800176ca  lea     r8, [rsp+290h+Name]; lpName
0x1800176cf  mov     edx, esi; dwIndex
0x1800176d1  mov     rcx, [rsp+290h+hKey]; hKey
0x1800176d6  call    cs:__imp_RegEnumKeyExW
0x1800176dc  cmp     eax, 103h
0x1800176e1  jz      loc_180017804
0x1800176e7  test    eax, eax
0x1800176e9  jnz     loc_1800177CB
0x1800176ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800176f6  lea     ecx, [rax+40h]; unsigned __int64
0x1800176f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800176fe  mov     rbx, rax
0x180017701  test    rax, rax
0x180017704  jz      short loc_180017731
0x180017706  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18001770d  mov     [rax+10h], r15
0x180017711  lea     rax, ??_7CUHPluginRegistryInfo@@6B@; const CUHPluginRegistryInfo::`vftable'
0x180017718  mov     [rbx], rax
0x18001771b  mov     [rbx+18h], r15
0x18001771f  mov     [rbx+20h], r15
0x180017723  mov     [rbx+28h], r15
0x180017727  mov     [rbx+30h], r15
0x18001772b  mov     [rbx+38h], r15
0x18001772f  jmp     short loc_180017734
0x180017731  mov     rbx, r15
0x180017734  mov     [rsp+290h+var_248], rbx
0x180017739  mov     rax, rbx
0x18001773c  neg     rax
0x18001773f  sbb     edi, edi
0x180017741  not     edi
0x180017743  and     edi, 8007000Eh
0x180017749  test    rbx, rbx
0x18001774c  jz      short loc_1800177C1
0x18001774e  mov     rax, [rbx]
0x180017751  lea     r8, [rsp+290h+Name]
0x180017756  mov     rdx, [rsp+290h+hKey]
0x18001775b  mov     rcx, rbx
0x18001775e  mov     rax, [rax+8]
0x180017762  call    _guard_dispatch_icall
0x180017767  mov     edi, eax
0x180017769  test    eax, eax
0x18001776b  js      short loc_1800177BA
0x18001776d  lea     rcx, [r14+10h]
0x180017771  mov     [rsp+290h+var_250], rbx
0x180017776  mov     rax, [rcx]
0x180017779  xor     r8d, r8d
0x18001777c  lea     rdx, [rsp+290h+var_250]
0x180017781  mov     rax, [rax+8]
0x180017785  call    _guard_dispatch_icall
0x18001778a  mov     edi, eax
0x18001778c  test    eax, eax
0x18001778e  js      short loc_18001779D
0x180017790  inc     esi
0x180017792  cmp     esi, 14h
0x180017795  jb      loc_1800176A6
0x18001779b  jmp     short loc_180017804
0x18001779d  mov     edx, 180h; void *
0x1800177a2  mov     r9d, eax; char *
0x1800177a5  mov     rcx, [rbp+198h]; this
0x1800177ac  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800177b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177b8  jmp     short loc_1800177E8
0x1800177ba  mov     edx, 17Fh
0x1800177bf  jmp     short loc_1800177A2
0x1800177c1  mov     r9d, edi
0x1800177c4  mov     edx, 17Eh
0x1800177c9  jmp     short loc_1800177A5
0x1800177cb  mov     rcx, [rbp+198h]; this
0x1800177d2  mov     r9d, eax; char *
0x1800177d5  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800177dc  mov     edx, 17Dh; void *
0x1800177e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800177e6  mov     edi, eax
0x1800177e8  test    rbx, rbx
0x1800177eb  jz      short loc_180017807
0x1800177ed  mov     rcx, rbx; this
0x1800177f0  call    ??1CUHPlugin@@QEAA@XZ; CUHPlugin::~CUHPlugin(void)
0x1800177f5  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x1800177fa  mov     rcx, rbx; void *
0x1800177fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017802  jmp     short loc_180017807
0x180017804  mov     edi, r15d
0x180017807  mov     rcx, [rsp+290h+hKey]; hKey
0x18001780c  test    rcx, rcx
0x18001780f  jz      short loc_180017817
0x180017811  call    cs:__imp_RegCloseKey
0x180017817  mov     eax, edi
0x180017819  mov     rcx, [rbp+190h+var_20]
0x180017820  xor     rcx, rsp; StackCookie
0x180017823  call    __security_check_cookie
0x180017828  lea     r11, [rsp+290h+var_10]
0x180017830  mov     rbx, [r11+28h]
0x180017834  mov     rsi, [r11+30h]
0x180017838  mov     rdi, [r11+38h]
0x18001783c  mov     rsp, r11
0x18001783f  pop     r15
0x180017841  pop     r14
0x180017843  pop     rbp
0x180017844  retn
```
