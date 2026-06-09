# CStaticHandlerEnum::Next(ulong,ushort * *,ulong *)

- ea: `0x180005a10`
- end: `0x180005bfc`
- name: `?Next@CStaticHandlerEnum@@UEAAJKPEAPEAGPEAK@Z`
- size: `492`
- prototype: `int(CStaticHandlerEnum *__hidden this, unsigned int, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005a10`
- `0x180008584`
- `0x180009940`
- `0x180009d1c`
- `0x18000a5e4`
- `0x18000a6ac`
- `0x18001cd90`
- `0x180051dd4`
- `0x18005292a`
- `0x180052950`

## import_xrefs

- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180005ba2`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180005ba2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180005ade`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180005ade`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005b37`
- `ADVAPI32!RegEnumKeyW` at `0x180005ac2`
- `ADVAPI32!RegEnumKeyW` at `0x180005b28`
- `ADVAPI32!RegEnumKeyW` at `0x180005ac2`
- `ADVAPI32!RegEnumKeyW` at `0x180005b28`

## pseudocode

```c
__int64 __fastcall CStaticHandlerEnum::Next(
        CStaticHandlerEnum *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  unsigned int v8; // edi
  DWORD i; // r12d
  unsigned int j; // r12d
  int v12; // edx
  struct _DSA *v13; // rcx
  unsigned __int16 *v14; // rax
  void **v15; // r13
  HKEY hKey; // [rsp+30h] [rbp-288h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-280h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-268h] BYREF

  memset_0(a3, 0, 8LL * a2);
  v8 = 0;
  if ( !*((_QWORD *)this + 2) )
  {
    hKey = 0;
    if ( (int)StringCchPrintfW(
                Name,
                0x104u,
                L"%ws\\%ws",
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
                L"Handlers") >= 0 )
      CSettingsBase::OpenKey(HKEY_LOCAL_MACHINE, Name, &hKey);
    if ( hKey )
    {
      for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x104u); ++i )
      {
        pclsid = 0;
        if ( !CLSIDFromString(Name, &pclsid)
          && (!*((_QWORD *)this + 2) && !(unsigned int)CDSA_Base<_GUID>::Create((char *)this + 16, 4)
           || (int)CDSA_Base<_GUID>::AppendItem((char *)this + 16, &pclsid) < 0) )
        {
          break;
        }
      }
      RegCloseKey(hKey);
    }
    if ( !*((_QWORD *)this + 2) )
      return 1;
  }
  for ( j = 0; j < a2; ++j )
  {
    v12 = *((_DWORD *)this + 3);
    v13 = (struct _DSA *)*((_QWORD *)this + 2);
    pclsid = 0;
    if ( !DSA_GetItem(v13, v12, &pclsid) )
      break;
    v14 = (unsigned __int16 *)operator new(0x4Eu);
    a3[j] = v14;
    v15 = (void **)&a3[j];
    if ( !v14 )
      break;
    if ( (int)SHStringFromGUIDW(&pclsid, v14, 39) < 0 )
    {
      CZeroInitNew::operator delete(*v15);
      *v15 = 0;
      break;
    }
    ++*((_DWORD *)this + 3);
  }
  if ( a4 )
    *a4 = j;
  LOBYTE(v8) = j != a2;
  return v8;
}

```

## disassembly

```asm
0x180005a10  push    rbx
0x180005a12  push    rbp
0x180005a13  push    rsi
0x180005a14  push    rdi
0x180005a15  push    r12
0x180005a17  push    r14
0x180005a19  push    r15
0x180005a1b  sub     rsp, 280h
0x180005a22  mov     rax, cs:__security_cookie
0x180005a29  xor     rax, rsp
0x180005a2c  mov     [rsp+2B8h+var_58], rax
0x180005a34  mov     r14, r8
0x180005a37  mov     ebp, edx
0x180005a39  mov     r8d, edx
0x180005a3c  mov     rsi, rcx
0x180005a3f  shl     r8, 3; Size
0x180005a43  xor     edx, edx; Val
0x180005a45  mov     rcx, r14; void *
0x180005a48  mov     r15, r9
0x180005a4b  call    memset_0
0x180005a50  xor     edi, edi
0x180005a52  cmp     [rsi+10h], rdi
0x180005a56  jnz     loc_180005B4D
0x180005a5c  lea     rax, ?s_szHandlers_regkey@CSettingsBase@@1QBGB; "Handlers"
0x180005a63  mov     [rsp+2B8h+hKey], rdi
0x180005a68  lea     r9, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180005a6f  mov     [rsp+2B8h+var_298], rax
0x180005a74  lea     r8, aWsWs; "%ws\\%ws"
0x180005a7b  mov     edx, 104h; unsigned __int64
0x180005a80  lea     rcx, [rsp+2B8h+Name]; unsigned __int16 *
0x180005a85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005a8a  test    eax, eax
0x180005a8c  js      short loc_180005AA4
0x180005a8e  lea     r8, [rsp+2B8h+hKey]; HKEY *
0x180005a93  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180005a9a  lea     rdx, [rsp+2B8h+Name]; unsigned __int16 *
0x180005a9f  call    ?OpenKey@CSettingsBase@@KAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSettingsBase::OpenKey(HKEY__ *,ushort const *,HKEY__ * *)
0x180005aa4  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180005aa9  test    rcx, rcx
0x180005aac  jz      loc_180005B3D
0x180005ab2  mov     r9d, 104h; cchName
0x180005ab8  lea     r8, [rsp+2B8h+Name]; lpName
0x180005abd  xor     edx, edx; dwIndex
0x180005abf  mov     r12d, edi
0x180005ac2  call    cs:__imp_RegEnumKeyW
0x180005ac8  test    eax, eax
0x180005aca  jnz     short loc_180005B32
0x180005acc  xorps   xmm0, xmm0
0x180005acf  lea     rdx, [rsp+2B8h+pclsid]; pclsid
0x180005ad4  lea     rcx, [rsp+2B8h+Name]; lpsz
0x180005ad9  movups  xmmword ptr [rsp+2B8h+pclsid.Data1], xmm0
0x180005ade  call    cs:__imp_CLSIDFromString
0x180005ae4  test    eax, eax
0x180005ae6  jnz     short loc_180005B12
0x180005ae8  cmp     [rsi+10h], rdi
0x180005aec  jnz     short loc_180005B00
0x180005aee  mov     edx, 4
0x180005af3  lea     rcx, [rsi+10h]
0x180005af7  call    ?Create@?$CDSA_Base@U_GUID@@@@QEAAHH@Z; CDSA_Base<_GUID>::Create(int)
0x180005afc  test    eax, eax
0x180005afe  jz      short loc_180005B32
0x180005b00  lea     rdx, [rsp+2B8h+pclsid]
0x180005b05  lea     rcx, [rsi+10h]
0x180005b09  call    ?AppendItem@?$CDSA_Base@U_GUID@@@@QEAAJPEBU_GUID@@PEAH@Z; CDSA_Base<_GUID>::AppendItem(_GUID const *,int *)
0x180005b0e  test    eax, eax
0x180005b10  js      short loc_180005B32
0x180005b12  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180005b17  lea     r8, [rsp+2B8h+Name]; lpName
0x180005b1c  inc     r12d
0x180005b1f  mov     r9d, 104h; cchName
0x180005b25  mov     edx, r12d; dwIndex
0x180005b28  call    cs:__imp_RegEnumKeyW
0x180005b2e  test    eax, eax
0x180005b30  jz      short loc_180005ACC
0x180005b32  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180005b37  call    cs:__imp_RegCloseKey
0x180005b3d  cmp     [rsi+10h], rdi
0x180005b41  jnz     short loc_180005B4D
0x180005b43  mov     eax, 1
0x180005b48  jmp     loc_180005BDA
0x180005b4d  mov     r12d, edi
0x180005b50  mov     [rsp+2B8h+var_40], r13
0x180005b58  cmp     r12d, ebp
0x180005b5b  jnb     short loc_180005BC1
0x180005b5d  mov     edx, [rsi+0Ch]; i
0x180005b60  lea     r8, [rsp+2B8h+pclsid]; pitem
0x180005b65  mov     rcx, [rsi+10h]; hdsa
0x180005b69  xorps   xmm0, xmm0
0x180005b6c  movups  xmmword ptr [rsp+2B8h+pclsid.Data1], xmm0
0x180005b71  call    DSA_GetItem
0x180005b76  test    eax, eax
0x180005b78  jz      short loc_180005BC1
0x180005b7a  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x180005b7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005b84  mov     ecx, r12d
0x180005b87  mov     [r14+rcx*8], rax
0x180005b8b  lea     r13, [r14+rcx*8]
0x180005b8f  test    rax, rax
0x180005b92  jz      short loc_180005BC1
0x180005b94  mov     r8d, 27h ; '''
0x180005b9a  lea     rcx, [rsp+2B8h+pclsid]
0x180005b9f  mov     rdx, rax
0x180005ba2  call    cs:__imp_SHStringFromGUIDW
0x180005ba8  test    eax, eax
0x180005baa  js      short loc_180005BB4
0x180005bac  inc     r12d
0x180005baf  inc     dword ptr [rsi+0Ch]
0x180005bb2  jmp     short loc_180005B58
0x180005bb4  mov     rcx, [r13+0]; lpMem
0x180005bb8  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180005bbd  mov     [r13+0], rdi
0x180005bc1  mov     r13, [rsp+2B8h+var_40]
0x180005bc9  test    r15, r15
0x180005bcc  jz      short loc_180005BD1
0x180005bce  mov     [r15], r12d
0x180005bd1  cmp     r12d, ebp
0x180005bd4  setnz   dil
0x180005bd8  mov     eax, edi
0x180005bda  mov     rcx, [rsp+2B8h+var_58]
0x180005be2  xor     rcx, rsp; StackCookie
0x180005be5  call    __security_check_cookie
0x180005bea  add     rsp, 280h
0x180005bf1  pop     r15
0x180005bf3  pop     r14
0x180005bf5  pop     r12
0x180005bf7  pop     rdi
0x180005bf8  pop     rsi
0x180005bf9  pop     rbp
0x180005bfa  pop     rbx
0x180005bfb  retn
```
