# CPreLoadDataset::InitializeComponents(void)

- ea: `0x180130984`
- end: `0x180130c2c`
- name: `?InitializeComponents@CPreLoadDataset@@AEAAKXZ`
- size: `680`
- prototype: `unsigned int __fastcall(CPreLoadDataset *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180130540`

## callees

- `0x18000573c`
- `0x18000801c`
- `0x180008290`
- `0x180009ec4`
- `0x18000cf48`
- `0x18002155c`
- `0x180130984`
- `0x180130c6c`
- `0x180138f50`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180130a9e`
- `msvcrt!swprintf_s` at `0x180130a9e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180130b0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180130b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180130b6b`
- `KERNEL32!GetSystemDirectoryW` at `0x180130a6f`
- `KERNEL32!GetSystemDirectoryW` at `0x180130a6f`

## string_xrefs

- `0x180130b57`: `CreateCacheMgr`
- `0x180130b9a`: `CreateCacheMgr`
- `0x180130a7d`: `PeerDistCacheProvider.dll`

## pseudocode

```c
__int64 __fastcall CPreLoadDataset::InitializeComponents(CPreLoadDataset *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  DWORD LastError; // esi
  signed int SystemDirectoryW; // eax
  CHostedCacheMsgEncoding *v7; // rax
  __int64 v8; // rdx
  HMODULE Library; // rax
  __int64 (*ProcAddressW)(void); // rax
  __int64 v11; // rbx
  struct ITnoCfgMgr *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t LibFileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  LibFileName[0] = 0;
  v13 = 0;
  v2 = ITnoCfgMgr::Create(&v13);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return TnoWin32ErrFromHR(v2);
    }
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 12);
    v4 = 21;
LABEL_6:
    WPP_SF_d(v3, v4, WPP_dab15540eef43723d0278e8a55c95337_Traceguids, (unsigned int)v2);
    return TnoWin32ErrFromHR(v2);
  }
  std::auto_ptr<IPeerDiscovery>::reset((char *)this + 88, v13);
  if ( CPreLoadDataset::SetConfigurationOverrides(this) )
  {
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return TnoWin32ErrFromHR(v2);
    }
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 12);
    v4 = 22;
    goto LABEL_6;
  }
  Buffer[0] = 0;
  LibFileName[0] = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW && SystemDirectoryW <= 260 )
  {
    if ( swprintf_s(LibFileName, 0x104u, L"%s\\%s", Buffer, L"PeerDistCacheProvider.dll") == -1 )
    {
      LastError = 774;
LABEL_18:
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 23;
LABEL_22:
        WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_dab15540eef43723d0278e8a55c95337_Traceguids, LastError);
        return LastError;
      }
      return LastError;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_18;
  }
  Library = LoadLibraryExW(LibFileName, 0, 0);
  *((_QWORD *)this + 10) = Library;
  if ( Library )
  {
    ProcAddressW = GetProcAddressW(Library, L"CreateCacheMgr");
    if ( ProcAddressW )
    {
      v14 = 0;
      LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddressW)(&v14);
      if ( !LastError )
      {
        v11 = v14;
        SmartPointer<CHostedCacheListManager>::Release((char *)this + 112);
        *((_QWORD *)this + 14) = v11;
        return LastError;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 26;
        goto LABEL_22;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          25,
          (unsigned int)WPP_dab15540eef43723d0278e8a55c95337_Traceguids,
          (unsigned int)L"CreateCacheMgr",
          LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 24;
      goto LABEL_22;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180130984  push    rbp
0x180130986  push    rbx
0x180130987  push    rsi
0x180130988  push    rdi
0x180130989  lea     rbp, [rsp-378h]
0x180130991  sub     rsp, 478h
0x180130998  mov     rax, cs:__security_cookie
0x18013099f  xor     rax, rsp
0x1801309a2  mov     [rbp+390h+var_30], rax
0x1801309a9  xor     eax, eax
0x1801309ab  mov     rdi, rcx
0x1801309ae  lea     rcx, [rsp+490h+var_460]; struct ITnoCfgMgr **
0x1801309b3  mov     [rsp+490h+LibFileName], ax
0x1801309b8  mov     [rsp+490h+var_460], rax
0x1801309bd  call    ?Create@ITnoCfgMgr@@SAJPEAPEAV1@@Z; ITnoCfgMgr::Create(ITnoCfgMgr * *)
0x1801309c2  mov     ebx, eax
0x1801309c4  test    eax, eax
0x1801309c6  jns     short loc_180130A0F
0x1801309c8  mov     r10, cs:WPP_GLOBAL_Control
0x1801309cf  lea     rcx, WPP_GLOBAL_Control
0x1801309d6  cmp     r10, rcx
0x1801309d9  jz      short loc_180130A01
0x1801309db  test    byte ptr [r10+6Ch], 4
0x1801309e0  jz      short loc_180130A01
0x1801309e2  cmp     byte ptr [r10+69h], 1
0x1801309e7  jb      short loc_180130A01
0x1801309e9  mov     rcx, [r10+60h]
0x1801309ed  mov     edx, 15h
0x1801309f2  lea     r8, WPP_dab15540eef43723d0278e8a55c95337_Traceguids
0x1801309f9  mov     r9d, ebx
0x1801309fc  call    WPP_SF_d
0x180130a01  mov     ecx, ebx; int
0x180130a03  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180130a08  mov     esi, eax
0x180130a0a  jmp     loc_180130C0F
0x180130a0f  mov     rdx, [rsp+490h+var_460]
0x180130a14  lea     rcx, [rdi+58h]
0x180130a18  call    ?reset@?$auto_ptr@VIPeerDiscovery@@@std@@QEAAXPEAVIPeerDiscovery@@@Z; std::auto_ptr<IPeerDiscovery>::reset(IPeerDiscovery *)
0x180130a1d  mov     rcx, rdi; this
0x180130a20  call    ?SetConfigurationOverrides@CPreLoadDataset@@AEAAKXZ; CPreLoadDataset::SetConfigurationOverrides(void)
0x180130a25  test    eax, eax
0x180130a27  jz      short loc_180130A53
0x180130a29  mov     rax, cs:WPP_GLOBAL_Control
0x180130a30  lea     rcx, WPP_GLOBAL_Control
0x180130a37  cmp     rax, rcx
0x180130a3a  jz      short loc_180130A01
0x180130a3c  test    byte ptr [rax+6Ch], 4
0x180130a40  jz      short loc_180130A01
0x180130a42  cmp     byte ptr [rax+69h], 1
0x180130a46  jb      short loc_180130A01
0x180130a48  mov     rcx, [rax+60h]
0x180130a4c  mov     edx, 16h
0x180130a51  jmp     short loc_1801309F2
0x180130a53  xor     eax, eax
0x180130a55  lea     rcx, [rbp+390h+Buffer]; lpBuffer
0x180130a5c  mov     ebx, 104h
0x180130a61  mov     [rbp+390h+Buffer], ax
0x180130a68  mov     edx, ebx; uSize
0x180130a6a  mov     [rsp+490h+LibFileName], ax
0x180130a6f  call    cs:__imp_GetSystemDirectoryW
0x180130a75  test    eax, eax
0x180130a77  jz      short loc_180130AB0
0x180130a79  cmp     eax, ebx
0x180130a7b  jg      short loc_180130AB0
0x180130a7d  lea     rax, aPeerdistcachep; "PeerDistCacheProvider.dll"
0x180130a84  mov     edx, ebx; BufferCount
0x180130a86  lea     r9, [rbp+390h+Buffer]
0x180130a8d  mov     [rsp+490h+var_470], rax
0x180130a92  lea     r8, aSS; "%s\\%s"
0x180130a99  lea     rcx, [rsp+490h+LibFileName]; Buffer
0x180130a9e  call    cs:__imp_swprintf_s
0x180130aa4  cmp     eax, 0FFFFFFFFh
0x180130aa7  jnz     short loc_180130B04
0x180130aa9  mov     esi, 306h
0x180130aae  jmp     short loc_180130ABC
0x180130ab0  call    cs:__imp_GetLastError
0x180130ab6  mov     esi, eax
0x180130ab8  test    eax, eax
0x180130aba  jz      short loc_180130B04
0x180130abc  mov     rax, cs:WPP_GLOBAL_Control
0x180130ac3  lea     rcx, WPP_GLOBAL_Control
0x180130aca  cmp     rax, rcx
0x180130acd  jz      loc_180130C0F
0x180130ad3  test    byte ptr [rax+6Ch], 4
0x180130ad7  jz      loc_180130C0F
0x180130add  cmp     byte ptr [rax+69h], 1
0x180130ae1  jb      loc_180130C0F
0x180130ae7  mov     edx, 17h
0x180130aec  mov     rcx, [rax+60h]
0x180130af0  lea     r8, WPP_dab15540eef43723d0278e8a55c95337_Traceguids
0x180130af7  mov     r9d, esi
0x180130afa  call    WPP_SF_d
0x180130aff  jmp     loc_180130C0F
0x180130b04  xor     r8d, r8d; dwFlags
0x180130b07  lea     rcx, [rsp+490h+LibFileName]; lpLibFileName
0x180130b0c  xor     edx, edx; hFile
0x180130b0e  call    cs:__imp_LoadLibraryExW
0x180130b14  mov     [rdi+50h], rax
0x180130b18  test    rax, rax
0x180130b1b  jnz     short loc_180130B57
0x180130b1d  call    cs:__imp_GetLastError
0x180130b23  mov     esi, eax
0x180130b25  mov     rax, cs:WPP_GLOBAL_Control
0x180130b2c  lea     rcx, WPP_GLOBAL_Control
0x180130b33  cmp     rax, rcx
0x180130b36  jz      loc_180130C0F
0x180130b3c  test    byte ptr [rax+6Ch], 4
0x180130b40  jz      loc_180130C0F
0x180130b46  cmp     byte ptr [rax+69h], 1
0x180130b4a  jb      loc_180130C0F
0x180130b50  mov     edx, 18h
0x180130b55  jmp     short loc_180130AEC
0x180130b57  lea     rdx, WideCharStr; "CreateCacheMgr"
0x180130b5e  mov     rcx, rax; hModule
0x180130b61  call    ?GetProcAddressW@@YAP6A_JXZPEAUHINSTANCE__@@PEBG@Z; GetProcAddressW(HINSTANCE__ *,ushort const *)
0x180130b66  test    rax, rax
0x180130b69  jnz     short loc_180130BB8
0x180130b6b  call    cs:__imp_GetLastError
0x180130b71  mov     esi, eax
0x180130b73  mov     rax, cs:WPP_GLOBAL_Control
0x180130b7a  lea     rcx, WPP_GLOBAL_Control
0x180130b81  cmp     rax, rcx
0x180130b84  jz      loc_180130C0F
0x180130b8a  test    byte ptr [rax+6Ch], 4
0x180130b8e  jz      short loc_180130C0F
0x180130b90  cmp     byte ptr [rax+69h], 1
0x180130b94  jb      short loc_180130C0F
0x180130b96  mov     rcx, [rax+60h]
0x180130b9a  lea     r9, WideCharStr; "CreateCacheMgr"
0x180130ba1  mov     edx, 19h
0x180130ba6  mov     dword ptr [rsp+490h+var_470], esi
0x180130baa  lea     r8, WPP_dab15540eef43723d0278e8a55c95337_Traceguids
0x180130bb1  call    WPP_SF_Sd
0x180130bb6  jmp     short loc_180130C0F
0x180130bb8  lea     rcx, [rsp+490h+var_458]
0x180130bbd  mov     [rsp+490h+var_458], 0
0x180130bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180130bcb  mov     esi, eax
0x180130bcd  test    eax, eax
0x180130bcf  jz      short loc_180130BFD
0x180130bd1  mov     rax, cs:WPP_GLOBAL_Control
0x180130bd8  lea     rcx, WPP_GLOBAL_Control
0x180130bdf  cmp     rax, rcx
0x180130be2  jz      short loc_180130C0F
0x180130be4  test    dword ptr [rax+6Ch], 800h
0x180130beb  jz      short loc_180130C0F
0x180130bed  cmp     byte ptr [rax+69h], 1
0x180130bf1  jb      short loc_180130C0F
0x180130bf3  mov     edx, 1Ah
0x180130bf8  jmp     loc_180130AEC
0x180130bfd  mov     rbx, [rsp+490h+var_458]
0x180130c02  lea     rcx, [rdi+70h]
0x180130c06  call    ?Release@?$SmartPointer@VCHostedCacheListManager@@@@IEAAXXZ; SmartPointer<CHostedCacheListManager>::Release(void)
0x180130c0b  mov     [rdi+70h], rbx
0x180130c0f  mov     eax, esi
0x180130c11  mov     rcx, [rbp+390h+var_30]
0x180130c18  xor     rcx, rsp; StackCookie
0x180130c1b  call    __security_check_cookie
0x180130c20  add     rsp, 478h
0x180130c27  pop     rdi
0x180130c28  pop     rsi
0x180130c29  pop     rbx
0x180130c2a  pop     rbp
0x180130c2b  retn
```
