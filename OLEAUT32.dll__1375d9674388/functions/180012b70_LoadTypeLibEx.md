# LoadTypeLibEx

- ea: `0x180012b70`
- end: `0x180013061`
- name: `LoadTypeLibEx`
- size: `1265`
- prototype: `HRESULT __stdcall(LPCOLESTR szFile, REGKIND regkind, ITypeLib **pptlib)`
- caller_count: `9`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x180012020`
- `0x1800128fc`
- `0x1800138f0`
- `0x180013900`
- `0x180014840`
- `0x18004396c`
- `0x180048808`
- `0x180059664`
- `0x180072d10`

## callees

- `0x1800024f4`
- `0x1800039b8`
- `0x180012b70`
- `0x1800229b8`
- `0x1800234fc`
- `0x18002f808`
- `0x180031f58`
- `0x180035560`
- `0x180040d20`
- `0x180044c0c`
- `0x18004d900`
- `0x18004e530`
- `0x18004e87c`
- `0x180057114`
- `0x180057e0c`
- `0x180058240`
- `0x180058d74`
- `0x180067e54`
- `0x180067f0c`
- `0x180067fcc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012e13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012e2c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012e13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012e2c`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180012e66`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x180012e66`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180012dff`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180012dff`
- `ext-ms-win-ole32-oleautomation-l1-1-0!MonikerLoadTypeLib` at `0x180012fe5`
- `ext-ms-win-ole32-oleautomation-l1-1-0!MonikerLoadTypeLib` at `0x180012fe5`

## pseudocode

```c
HRESULT __stdcall LoadTypeLibEx(LPCOLESTR szFile, REGKIND regkind, ITypeLib **pptlib)
{
  __m128i si128; // xmm6
  int v7; // r12d
  struct ILockBytes *v8; // rdi
  HRESULT inited; // ebx
  int v10; // ebx
  struct ITypeLib *v11; // rax
  const char *v12; // rdx
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  int TypeLib2LockBytes; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  bool v19[8]; // [rsp+58h] [rbp-B0h] BYREF
  ITypeLib *ptlib; // [rsp+60h] [rbp-A8h] BYREF
  struct ILockBytes *v21; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v22[2]; // [rsp+70h] [rbp-98h] BYREF
  void *v23; // [rsp+78h] [rbp-90h] BYREF
  LPCOLESTR szFullPath; // [rsp+88h] [rbp-80h] BYREF
  int v25; // [rsp+90h] [rbp-78h]
  int v26; // [rsp+94h] [rbp-74h]
  int v27[4]; // [rsp+98h] [rbp-70h]
  int v28; // [rsp+A8h] [rbp-60h]
  _IMAGE_DOS_HEADER v29; // [rsp+ACh] [rbp-5Ch] BYREF
  enum tagSYSKIND v30; // [rsp+ECh] [rbp-1Ch]
  int v31; // [rsp+F0h] [rbp-18h]
  wchar_t Drive[8]; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t Ext[256]; // [rsp+108h] [rbp+0h] BYREF
  wchar_t Filename[256]; // [rsp+308h] [rbp+200h] BYREF
  wchar_t Dir[256]; // [rsp+508h] [rbp+400h] BYREF
  _BYTE v36[528]; // [rsp+708h] [rbp+600h] BYREF

  memset_0(&szFullPath, 0, 0x70u);
  v23 = 0;
  v19[1] = 0;
  v19[0] = 0;
  if ( (regkind & 0x60) == 0x60 )
    v30 = -1;
  else
    v30 = (~(_BYTE)regkind & 0x20 | 0x10u) >> 4;
  if ( (regkind & 0xFFFFFF9F) != 0 )
  {
    if ( (regkind & 0xFFFFFF9F) == 1 )
    {
      regkind = REGKIND_REGISTER;
    }
    else if ( (regkind & 0xFFFFFF9F) == 2 )
    {
      regkind = REGKIND_NONE;
    }
  }
  else
  {
    regkind = REGKIND_DEFAULT;
  }
  if ( !szFile || !pptlib || (unsigned int)regkind > REGKIND_NONE )
    return -2147024809;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v7 = 0;
  *(__m128i *)v27 = si128;
  v8 = 0;
  *pptlib = 0;
  ptlib = 0;
  v21 = 0;
  szFullPath = 0;
  v25 = -1;
  v26 = 0;
  v28 = 3;
  v31 = 0;
  inited = InitAppData();
  if ( inited < 0 )
    goto LABEL_56;
  while ( 1 )
  {
    if ( !*szFile )
    {
      inited = -2147287038;
      goto LABEL_56;
    }
    v10 = FFullyQualified(szFile);
    if ( v10 )
    {
      v11 = OLE_TYPEMGR::LookupTypeLib(g_poletmgr, szFile, v30);
      ptlib = v11;
      if ( v11 )
        goto LABEL_46;
    }
    if ( (unsigned int)FindTypeLib(szFile, (struct LoadInfo *)&szFullPath, v10) )
      break;
    ptlib = OLE_TYPEMGR::LookupTypeLib(g_poletmgr, szFullPath, v30);
    if ( ptlib )
      goto LABEL_45;
    v13 = 0;
    v22[0] = 0;
    v14 = 0;
    v22[1] = 0;
    if ( v27[3] )
    {
      inited = GetOffsetOfResource(v25, v12, v27[2], &v29, (int *)v22, (int *)&v22[1]);
      if ( inited < 0 )
        goto LABEL_56;
      v13 = v22[0];
      v14 = v22[1];
    }
    inited = CreateFileLockBytesOnHFILE(v25, 0, v13, v14, &v23, &v21);
    if ( inited < 0 )
      goto LABEL_47;
    v8 = v21;
    v25 = -1;
    if ( v27[1] || v27[3] )
    {
      TypeLib2LockBytes = LoadTypeLib2LockBytes(v21, (unsigned __int16 *)szFullPath, (__int64)&ptlib, v30);
      inited = TypeLib2LockBytes;
      if ( TypeLib2LockBytes >= 0 )
      {
        if ( v8 )
        {
          ((void (__fastcall *)(struct ILockBytes *))v8->lpVtbl->Release)(v8);
          v8 = 0;
        }
LABEL_40:
        inited = OLE_TYPEMGR::TypeLibLoaded(g_poletmgr, szFullPath, v31, ptlib, v30);
        if ( inited < 0 )
          goto LABEL_56;
        TraceTypeLibLoad(szFullPath, (unsigned int)v27[1]);
        if ( regkind == REGKIND_DEFAULT && v26 || regkind == REGKIND_REGISTER )
          RegisterTypeLib(ptlib, szFullPath, 0);
        goto LABEL_45;
      }
      if ( TypeLib2LockBytes != -2147319783 )
        goto LABEL_56;
    }
    if ( v30 != SYS_WIN64 )
    {
      inited = LoadTypeLib1LockBytes(&v21, szFullPath, (unsigned int)v31, &ptlib);
      if ( inited < 0 )
      {
LABEL_47:
        v8 = v21;
        goto LABEL_56;
      }
      v8 = v21;
      goto LABEL_40;
    }
    if ( v7
      || (_wsplitpath_s(szFile, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u),
          (unsigned int)_o__wcsicmp(Filename, L"stdole32"))
      || (unsigned int)_o__wcsicmp(Ext, L".tlb") )
    {
      inited = -2147319783;
      goto LABEL_56;
    }
    _o__wmakepath_s(v36, 260, Drive, Dir, L"stdole2", Ext);
    if ( v8 )
      ((void (__fastcall *)(struct ILockBytes *))v8->lpVtbl->Release)(v8);
    UninitLoadInfo((struct LoadInfo *)&szFullPath);
    ptlib = 0;
    v8 = 0;
    v21 = 0;
    szFullPath = 0;
    v25 = -1;
    v26 = 0;
    *(__m128i *)v27 = si128;
    v28 = 3;
    v31 = 0;
    inited = InitAppData();
    if ( inited < 0 )
      goto LABEL_56;
    szFile = (LPCOLESTR)v36;
    v7 = 1;
  }
  if ( !(unsigned __int8)IsMonikerLoadTypeLibPresent() )
    goto LABEL_49;
  inited = CheckProtectedProcessForHardening(v19, (struct _PS_PROTECTION *)&v19[1]);
  if ( inited >= 0 )
  {
    if ( v19[0] )
    {
      LOBYTE(v17) = v19[1];
      TraceTypeLibMonikerFallback(szFile, v17);
      LOBYTE(v18) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp>::GetImpl'::`2'::impl,
        v18);
      goto LABEL_49;
    }
    TraceTypeLibMonikerLoad(szFile);
    if ( (unsigned int)MonikerLoadTypeLib(szFile, &ptlib) )
    {
LABEL_49:
      inited = -2147312566;
      goto LABEL_56;
    }
LABEL_45:
    UninitLoadInfo((struct LoadInfo *)&szFullPath);
    v11 = ptlib;
LABEL_46:
    *pptlib = v11;
    return 0;
  }
LABEL_56:
  if ( ptlib )
    ((void (__fastcall *)(ITypeLib *))ptlib->lpVtbl->Release)(ptlib);
  if ( v8 )
    ((void (__fastcall *)(struct ILockBytes *))v8->lpVtbl->Release)(v8);
  UninitLoadInfo((struct LoadInfo *)&szFullPath);
  return inited;
}

```

## disassembly

```asm
0x180012b70  mov     rax, rsp
0x180012b73  mov     [rax+10h], rbx
0x180012b77  push    rbp
0x180012b78  push    rsi
0x180012b79  push    rdi
0x180012b7a  push    r12
0x180012b7c  push    r13
0x180012b7e  push    r14
0x180012b80  push    r15
0x180012b82  lea     rbp, [rax-868h]
0x180012b89  sub     rsp, 930h
0x180012b90  movaps  xmmword ptr [rax-48h], xmm6
0x180012b94  mov     rax, cs:__security_cookie
0x180012b9b  xor     rax, rsp
0x180012b9e  mov     [rbp+860h+var_50], rax
0x180012ba5  mov     esi, edx
0x180012ba7  mov     r15, r8
0x180012baa  xor     edx, edx; Val
0x180012bac  mov     r14, rcx
0x180012baf  lea     rcx, [rbp+860h+szFullPath]; void *
0x180012bb3  lea     r8d, [rdx+70h]; Size
0x180012bb7  call    memset_0
0x180012bbc  xor     r13d, r13d
0x180012bbf  mov     eax, esi
0x180012bc1  and     eax, 60h
0x180012bc4  mov     [rsp+960h+var_8F0], r13
0x180012bc9  or      edx, 0FFFFFFFFh
0x180012bcc  mov     [rsp+960h+var_910+1], r13b
0x180012bd1  mov     [rsp+960h+var_910], r13b
0x180012bd6  cmp     al, 60h ; '`'
0x180012bd8  jnz     short loc_180012BDF
0x180012bda  mov     [rbp+860h+var_87C], edx
0x180012bdd  jmp     short loc_180012BF3
0x180012bdf  mov     al, sil
0x180012be2  not     al
0x180012be4  movzx   ecx, al
0x180012be7  and     ecx, 20h
0x180012bea  or      ecx, 10h
0x180012bed  shr     ecx, 4
0x180012bf0  mov     [rbp+860h+var_87C], ecx
0x180012bf3  mov     ecx, esi
0x180012bf5  and     ecx, 0FFFFFF9Fh
0x180012bf8  jz      short loc_180012C10
0x180012bfa  sub     ecx, 1
0x180012bfd  jz      short loc_180012C09
0x180012bff  cmp     ecx, 1
0x180012c02  jnz     short loc_180012C13
0x180012c04  lea     esi, [rcx+1]
0x180012c07  jmp     short loc_180012C13
0x180012c09  mov     esi, 1
0x180012c0e  jmp     short loc_180012C13
0x180012c10  mov     esi, r13d
0x180012c13  test    r14, r14
0x180012c16  jz      loc_18001302D
0x180012c1c  test    r15, r15
0x180012c1f  jz      loc_18001302D
0x180012c25  cmp     esi, 2
0x180012c28  ja      loc_18001302D
0x180012c2e  movdqa  xmm6, cs:__xmm@00000000ffffffff0000000000000000
0x180012c36  mov     r12d, r13d
0x180012c39  movdqa  xmmword ptr [rbp+860h+var_8D0], xmm6
0x180012c3e  mov     rdi, r13
0x180012c41  mov     [r15], r13
0x180012c44  mov     [rsp+960h+ptlib], r13
0x180012c49  mov     [rsp+960h+var_900], r13
0x180012c4e  mov     [rbp+860h+szFullPath], r13
0x180012c52  mov     [rbp+860h+var_8D8], edx
0x180012c55  mov     [rbp+860h+var_8D4], r13d
0x180012c59  mov     [rbp+860h+var_8C0], 3
0x180012c60  mov     [rbp+860h+var_878], r13d
0x180012c64  call    InitAppData
0x180012c69  mov     ebx, eax
0x180012c6b  test    eax, eax
0x180012c6d  js      loc_180012FF6
0x180012c73  cmp     [r14], r13w
0x180012c77  jz      loc_180012FF1
0x180012c7d  mov     rcx, r14
0x180012c80  call    FFullyQualified
0x180012c85  mov     ebx, eax
0x180012c87  test    eax, eax
0x180012c89  jz      short loc_180012CAC
0x180012c8b  mov     r8d, [rbp+860h+var_87C]; enum tagSYSKIND
0x180012c8f  mov     rdx, r14; unsigned __int16 *
0x180012c92  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180012c99  call    ?LookupTypeLib@OLE_TYPEMGR@@QEAAPEAUITypeLib@@PEBGW4tagSYSKIND@@@Z; OLE_TYPEMGR::LookupTypeLib(ushort const *,tagSYSKIND)
0x180012c9e  mov     [rsp+960h+ptlib], rax
0x180012ca3  test    rax, rax
0x180012ca6  jnz     loc_180012F7F
0x180012cac  mov     r8d, ebx; int
0x180012caf  lea     rdx, [rbp+860h+szFullPath]; struct LoadInfo *
0x180012cb3  mov     rcx, r14; unsigned __int16 *
0x180012cb6  call    ?FindTypeLib@@YAJPEBGPEAULoadInfo@@H@Z; FindTypeLib(ushort const *,LoadInfo *,int)
0x180012cbb  test    eax, eax
0x180012cbd  jnz     loc_180012F90
0x180012cc3  mov     r8d, [rbp+860h+var_87C]; enum tagSYSKIND
0x180012cc7  mov     rdx, [rbp+860h+szFullPath]; unsigned __int16 *
0x180012ccb  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180012cd2  call    ?LookupTypeLib@OLE_TYPEMGR@@QEAAPEAUITypeLib@@PEBGW4tagSYSKIND@@@Z; OLE_TYPEMGR::LookupTypeLib(ushort const *,tagSYSKIND)
0x180012cd7  mov     [rsp+960h+ptlib], rax
0x180012cdc  test    rax, rax
0x180012cdf  jnz     loc_180012F71
0x180012ce5  mov     r8d, r13d
0x180012ce8  mov     [rsp+960h+var_8F8], r13d
0x180012ced  mov     r9d, r13d
0x180012cf0  mov     [rsp+960h+var_8F8+4], r13d
0x180012cf5  cmp     [rbp+860h+var_8D0+0Ch], r13d
0x180012cf9  jz      short loc_180012D33
0x180012cfb  mov     r8d, [rbp+860h+var_8D0+8]; int
0x180012cff  lea     rax, [rsp+960h+var_8F8+4]
0x180012d04  mov     ecx, [rbp+860h+var_8D8]; int
0x180012d07  lea     r9, [rbp+860h+var_8BC]; struct _IMAGE_DOS_HEADER *
0x180012d0b  mov     [rsp+960h+Filename], rax; int *
0x180012d10  lea     rax, [rsp+960h+var_8F8]
0x180012d15  mov     [rsp+960h+DirCount], rax; int *
0x180012d1a  call    ?GetOffsetOfResource@@YAJHPEBDHPEAU_IMAGE_DOS_HEADER@@PEAJ2@Z; GetOffsetOfResource(int,char const *,int,_IMAGE_DOS_HEADER *,long *,long *)
0x180012d1f  mov     ebx, eax
0x180012d21  test    eax, eax
0x180012d23  js      loc_180012FF6
0x180012d29  mov     r8d, [rsp+960h+var_8F8]; unsigned int
0x180012d2e  mov     r9d, [rsp+960h+var_8F8+4]; unsigned int
0x180012d33  mov     ecx, [rbp+860h+var_8D8]; int
0x180012d36  lea     rax, [rsp+960h+var_900]
0x180012d3b  mov     [rsp+960h+Filename], rax; struct ILockBytes **
0x180012d40  xor     edx, edx; int
0x180012d42  lea     rax, [rsp+960h+var_8F0]
0x180012d47  mov     [rsp+960h+DirCount], rax; void **
0x180012d4c  call    ?CreateFileLockBytesOnHFILE@@YAJHHKKPEAPEAXPEAPEAUILockBytes@@@Z; CreateFileLockBytesOnHFILE(int,int,ulong,ulong,void * *,ILockBytes * *)
0x180012d51  mov     ebx, eax
0x180012d53  test    eax, eax
0x180012d55  js      loc_180012F89
0x180012d5b  mov     rdi, [rsp+960h+var_900]
0x180012d60  mov     [rbp+860h+var_8D8], 0FFFFFFFFh
0x180012d67  cmp     [rbp+860h+var_8D0+4], r13d
0x180012d6b  jnz     short loc_180012D73
0x180012d6d  cmp     [rbp+860h+var_8D0+0Ch], r13d
0x180012d71  jz      short loc_180012DAE
0x180012d73  mov     eax, [rbp+860h+var_87C]
0x180012d76  mov     rcx, rdi; struct ILockBytes *
0x180012d79  mov     r9, [rsp+960h+var_8F0]
0x180012d7e  mov     r8d, [rbp+860h+var_878]
0x180012d82  mov     rdx, [rbp+860h+szFullPath]; unsigned __int16 *
0x180012d86  mov     dword ptr [rsp+960h+Filename], eax; enum tagSYSKIND
0x180012d8a  lea     rax, [rsp+960h+ptlib]
0x180012d8f  mov     [rsp+960h+DirCount], rax; __int64
0x180012d94  call    LoadTypeLib2LockBytes
0x180012d99  mov     ebx, eax
0x180012d9b  test    eax, eax
0x180012d9d  jns     loc_180012F04
0x180012da3  cmp     eax, 80028019h
0x180012da8  jnz     loc_180012FF6
0x180012dae  mov     ebx, 3
0x180012db3  cmp     [rbp+860h+var_87C], ebx
0x180012db6  jnz     loc_180012EDC
0x180012dbc  test    r12d, r12d
0x180012dbf  jnz     loc_180012ED2
0x180012dc5  mov     ecx, 100h
0x180012dca  lea     rax, [rbp+860h+var_860]
0x180012dce  mov     [rsp+960h+ExtCount], rcx; ExtCount
0x180012dd3  lea     r9, [rbp+860h+Dir]; Dir
0x180012dda  mov     [rsp+960h+Ext], rax; Ext
0x180012ddf  lea     rdx, [rbp+860h+Drive]; Drive
0x180012de3  mov     [rsp+960h+FilenameCount], rcx; FilenameCount
0x180012de8  lea     rax, [rbp+860h+var_660]
0x180012def  mov     [rsp+960h+Filename], rax; Filename
0x180012df4  mov     r8d, ebx; DriveCount
0x180012df7  mov     [rsp+960h+DirCount], rcx; DirCount
0x180012dfc  mov     rcx, r14; FullPath
0x180012dff  call    cs:__imp__wsplitpath_s
0x180012e05  lea     rdx, aStdole32; "stdole32"
0x180012e0c  lea     rcx, [rbp+860h+var_660]
0x180012e13  call    cs:__imp__o__wcsicmp
0x180012e19  test    eax, eax
0x180012e1b  jnz     loc_180012ED2
0x180012e21  lea     rdx, aTlb; ".tlb"
0x180012e28  lea     rcx, [rbp+860h+var_860]
0x180012e2c  call    cs:__imp__o__wcsicmp
0x180012e32  test    eax, eax
0x180012e34  jnz     loc_180012ED2
0x180012e3a  lea     rax, [rbp+860h+var_860]
0x180012e3e  mov     edx, 104h
0x180012e43  mov     [rsp+960h+Filename], rax
0x180012e48  lea     r9, [rbp+860h+Dir]
0x180012e4f  lea     rax, aStdole2; "stdole2"
0x180012e56  lea     r8, [rbp+860h+Drive]
0x180012e5a  mov     [rsp+960h+DirCount], rax
0x180012e5f  lea     rcx, [rbp+860h+var_260]
0x180012e66  call    cs:__imp__o__wmakepath_s
0x180012e6c  test    rdi, rdi
0x180012e6f  jz      short loc_180012E80
0x180012e71  mov     rax, [rdi]
0x180012e74  mov     rcx, rdi
0x180012e77  mov     rax, [rax+10h]
0x180012e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e80  lea     rcx, [rbp+860h+szFullPath]; struct LoadInfo *
0x180012e84  call    ?UninitLoadInfo@@YAXPEAULoadInfo@@@Z; UninitLoadInfo(LoadInfo *)
0x180012e89  mov     [rsp+960h+ptlib], r13
0x180012e8e  mov     rdi, r13
0x180012e91  mov     [rsp+960h+var_900], r13
0x180012e96  mov     [rbp+860h+szFullPath], r13
0x180012e9a  mov     [rbp+860h+var_8D8], 0FFFFFFFFh
0x180012ea1  mov     [rbp+860h+var_8D4], r13d
0x180012ea5  movdqa  xmmword ptr [rbp+860h+var_8D0], xmm6
0x180012eaa  mov     [rbp+860h+var_8C0], ebx
0x180012ead  mov     [rbp+860h+var_878], r13d
0x180012eb1  call    InitAppData
0x180012eb6  mov     ebx, eax
0x180012eb8  test    eax, eax
0x180012eba  js      loc_180012FF6
0x180012ec0  lea     r14, [rbp+860h+var_260]
0x180012ec7  mov     r12d, 1
0x180012ecd  jmp     loc_180012C73
0x180012ed2  mov     ebx, 80028019h
0x180012ed7  jmp     loc_180012FF6
0x180012edc  mov     r8d, [rbp+860h+var_878]
0x180012ee0  lea     r9, [rsp+960h+ptlib]
0x180012ee5  mov     rdx, [rbp+860h+szFullPath]
0x180012ee9  lea     rcx, [rsp+960h+var_900]
0x180012eee  call    LoadTypeLib1LockBytes
0x180012ef3  mov     ebx, eax
0x180012ef5  test    eax, eax
0x180012ef7  js      loc_180012F89
0x180012efd  mov     rdi, [rsp+960h+var_900]
0x180012f02  jmp     short loc_180012F1B
0x180012f04  test    rdi, rdi
0x180012f07  jz      short loc_180012F1B
0x180012f09  mov     rax, [rdi]
0x180012f0c  mov     rcx, rdi
0x180012f0f  mov     rax, [rax+10h]
0x180012f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f18  mov     rdi, r13
0x180012f1b  mov     eax, [rbp+860h+var_87C]
0x180012f1e  mov     r9, [rsp+960h+ptlib]; struct ITypeLib *
0x180012f23  mov     r8d, [rbp+860h+var_878]; int
0x180012f27  mov     rdx, [rbp+860h+szFullPath]; unsigned __int16 *
0x180012f2b  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180012f32  mov     dword ptr [rsp+960h+DirCount], eax; enum tagSYSKIND
0x180012f36  call    ?TypeLibLoaded@OLE_TYPEMGR@@QEAAJPEBGHPEAUITypeLib@@W4tagSYSKIND@@@Z; OLE_TYPEMGR::TypeLibLoaded(ushort const *,int,ITypeLib *,tagSYSKIND)
0x180012f3b  mov     ebx, eax
0x180012f3d  test    eax, eax
0x180012f3f  js      loc_180012FF6
0x180012f45  mov     edx, [rbp+860h+var_8D0+4]
0x180012f48  mov     rcx, [rbp+860h+szFullPath]
0x180012f4c  call    TraceTypeLibLoad
0x180012f51  test    esi, esi
0x180012f53  jnz     short loc_180012F5B
0x180012f55  cmp     [rbp+860h+var_8D4], r13d
0x180012f59  jnz     short loc_180012F60
0x180012f5b  cmp     esi, 1
0x180012f5e  jnz     short loc_180012F71
0x180012f60  mov     rdx, [rbp+860h+szFullPath]; szFullPath
0x180012f64  xor     r8d, r8d; szHelpDir
0x180012f67  mov     rcx, [rsp+960h+ptlib]; ptlib
0x180012f6c  call    RegisterTypeLib
0x180012f71  lea     rcx, [rbp+860h+szFullPath]; struct LoadInfo *
0x180012f75  call    ?UninitLoadInfo@@YAXPEAULoadInfo@@@Z; UninitLoadInfo(LoadInfo *)
0x180012f7a  mov     rax, [rsp+960h+ptlib]
0x180012f7f  mov     [r15], rax
0x180012f82  xor     eax, eax
0x180012f84  jmp     loc_180013032
0x180012f89  mov     rdi, [rsp+960h+var_900]
0x180012f8e  jmp     short loc_180012FF6
0x180012f90  call    IsMonikerLoadTypeLibPresent
0x180012f95  test    al, al
0x180012f97  jnz     short loc_180012FA0
0x180012f99  mov     ebx, 80029C4Ah
0x180012f9e  jmp     short loc_180012FF6
0x180012fa0  lea     rdx, [rsp+960h+var_910+1]; struct _PS_PROTECTION *
0x180012fa5  lea     rcx, [rsp+960h+var_910]; bool *
0x180012faa  call    ?CheckProtectedProcessForHardening@@YAJPEA_NPEAU_PS_PROTECTION@@@Z; CheckProtectedProcessForHardening(bool *,_PS_PROTECTION *)
0x180012faf  mov     ebx, eax
0x180012fb1  test    eax, eax
0x180012fb3  js      short loc_180012FF6
0x180012fb5  mov     rcx, r14
0x180012fb8  cmp     [rsp+960h+var_910], r13b
0x180012fbd  jz      short loc_180012FD8
0x180012fbf  mov     dl, [rsp+960h+var_910+1]
0x180012fc3  call    TraceTypeLibMonikerFallback
0x180012fc8  mov     dl, 1
0x180012fca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp> `wil::Feature<__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp>::GetImpl(void)'::`2'::impl
0x180012fd1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableTypeLibMonikerFallbackForPp>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180012fd6  jmp     short loc_180012F99
0x180012fd8  call    TraceTypeLibMonikerLoad
0x180012fdd  lea     rdx, [rsp+960h+ptlib]
0x180012fe2  mov     rcx, r14
0x180012fe5  call    cs:__imp_MonikerLoadTypeLib
0x180012feb  test    eax, eax
0x180012fed  jz      short loc_180012F71
0x180012fef  jmp     short loc_180012F99
0x180012ff1  mov     ebx, 80030002h
0x180012ff6  mov     rcx, [rsp+960h+ptlib]
0x180012ffb  test    rcx, rcx
0x180012ffe  jz      short loc_18001300C
0x180013000  mov     rax, [rcx]
0x180013003  mov     rax, [rax+10h]
0x180013007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001300c  test    rdi, rdi
0x18001300f  jz      short loc_180013020
0x180013011  mov     rax, [rdi]
0x180013014  mov     rcx, rdi
0x180013017  mov     rax, [rax+10h]
  ... truncated ...
```
