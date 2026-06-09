# AppxAllUserStore::GetAllUpdatedPackagesImplementation(AppxAllUserStore::_PackageInfo * *,uint *)

- ea: `0x180003e28`
- end: `0x1800040d3`
- name: `?GetAllUpdatedPackagesImplementation@AppxAllUserStore@@YAJPEAPEAU_PackageInfo@1@PEAI@Z`
- size: `683`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, struct AppxAllUserStore::_PackageInfo **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ee70`

## callees

- `0x1800027a8`
- `0x180003e28`
- `0x180004920`
- `0x180004940`
- `0x180004968`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x18000d710`
- `0x180012910`
- `0x180017f50`
- `0x18004c98a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003f51`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003f51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ebd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003ebd`

## string_xrefs

- `0x180003e5b`: `UpdatedApplications`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetAllUpdatedPackagesImplementation(
        AppxAllUserStore *this,
        struct AppxAllUserStore::_PackageInfo **a2,
        unsigned int *a3,
        struct Common::StringBuffer *a4)
{
  struct AppxAllUserStore::_PackageInfo **v4; // r14
  int AllUserChildStorePath; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // rbx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // edi
  unsigned __int64 v13; // rsi
  SIZE_T v14; // rax
  void *v15; // rbx
  struct _FILETIME *v16; // r9
  DWORD i; // esi
  DWORD v18; // eax
  int v19; // eax
  __int128 v20; // [rsp+60h] [rbp-9h] BYREF
  int v21; // [rsp+70h] [rbp+7h]
  LPCWSTR lpSubKey[2]; // [rsp+78h] [rbp+Fh] BYREF
  int v23; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cSubKeys; // [rsp+D0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+6Fh] BYREF
  void *v27; // [rsp+E0h] [rbp+77h] BYREF

  *(_QWORD *)this = 0;
  v4 = a2;
  *(_DWORD *)a2 = 0;
  v23 = 0;
  LOBYTE(a2) = 1;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"UpdatedApplications",
                            (const unsigned __int16 *)a2,
                            (unsigned int *)lpSubKey,
                            a4);
  v7 = AllUserChildStorePath;
  if ( AllUserChildStorePath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xECC,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath);
LABEL_30:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return v7;
  }
  v8 = lpSubKey[1];
  hKey = 0;
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  hKey = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
  v7 = v9;
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  if ( v7 == -2147024894 )
  {
    Common::RegistryKey::~RegistryKey(&hKey);
    v7 = 0;
    goto LABEL_30;
  }
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xED2,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v7);
    Common::RegistryKey::~RegistryKey(&hKey);
    goto LABEL_30;
  }
  cSubKeys = 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xED5,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)v10);
    goto LABEL_29;
  }
  if ( cSubKeys )
  {
    v13 = cSubKeys;
    v27 = 0;
    v14 = 24LL * cSubKeys;
    if ( !is_mul_ok(cSubKeys, 0x18u) )
      v14 = -1;
    Common::GlobalHeap::Alloc(v14, &v27);
    v15 = v27;
    if ( v27 )
      `vector constructor iterator'(v27, 0x18u, v13, (void *(*)(void *))AppxAllUserStore::_PackageInfo::_PackageInfo);
    else
      v15 = 0;
    v27 = v15;
    if ( !v15 )
    {
      Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v27);
      Common::RegistryKey::~RegistryKey(&hKey);
      v7 = -2147024882;
      goto LABEL_30;
    }
    memset_0(v15, 0, 24LL * cSubKeys);
    for ( i = 0; ; ++i )
    {
      v18 = cSubKeys;
      if ( i >= cSubKeys )
        break;
      v21 = 0;
      v20 = 0;
      v19 = Common::RegistryKey::EnumKey((Common::RegistryKey *)&hKey, i, (struct Common::StringBuffer *)&v20, v16);
      v11 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEDF,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)(unsigned int)v19);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v20);
        goto LABEL_28;
      }
      LODWORD(v20) = 0;
      v21 = 0;
      *((_QWORD *)v15 + 3 * i) = *((_QWORD *)&v20 + 1);
      *((_QWORD *)&v20 + 1) = 0;
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v20);
    }
    *(_QWORD *)this = v15;
    *(_DWORD *)v4 = v18;
    v27 = 0;
LABEL_28:
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(&v27);
LABEL_29:
    Common::RegistryKey::~RegistryKey(&hKey);
    v7 = v11;
    goto LABEL_30;
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(hKey);
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  return 0;
}

```

## disassembly

```asm
0x180003e28  push    rbp
0x180003e2a  push    rbx
0x180003e2b  push    rsi
0x180003e2c  push    rdi
0x180003e2d  push    r12
0x180003e2f  push    r14
0x180003e31  push    r15
0x180003e33  lea     rbp, [rsp-27h]
0x180003e38  sub     rsp, 90h
0x180003e3f  xor     r12d, r12d
0x180003e42  lea     r8, [rbp+57h+lpSubKey]; bool
0x180003e46  mov     [rcx], r12
0x180003e49  mov     r14, rdx
0x180003e4c  mov     [rdx], r12d
0x180003e4f  mov     r15, rcx
0x180003e52  xorps   xmm0, xmm0
0x180003e55  mov     [rbp+57h+var_38], r12d
0x180003e59  mov     dl, 1; unsigned __int16 *
0x180003e5b  lea     rcx, ?updatedApplicationsString@AppxAllUserStore@@3QBGB; "UpdatedApplications"
0x180003e62  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x180003e66  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180003e6b  mov     ebx, eax
0x180003e6d  test    eax, eax
0x180003e6f  jns     short loc_180003E8E
0x180003e71  mov     rcx, [rbp+5Fh]; this
0x180003e75  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180003e7c  mov     r9d, eax; char *
0x180003e7f  mov     edx, 0ECCh; void *
0x180003e84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003e89  jmp     loc_1800040B6
0x180003e8e  mov     rbx, [rbp+57h+lpSubKey+8]
0x180003e92  xor     ecx, ecx
0x180003e94  mov     [rbp+57h+hKey], r12
0x180003e98  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003e9d  lea     rax, [rbp+57h+hKey]
0x180003ea1  mov     [rbp+57h+hKey], r12
0x180003ea5  mov     r9d, 20019h; samDesired
0x180003eab  mov     [rsp+0C0h+phkResult], rax; int
0x180003eb0  xor     r8d, r8d; ulOptions
0x180003eb3  mov     rdx, rbx; lpSubKey
0x180003eb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003ebd  call    cs:__imp_RegOpenKeyExW
0x180003ec3  mov     ebx, eax
0x180003ec5  test    eax, eax
0x180003ec7  jle     short loc_180003ED2
0x180003ec9  movzx   ebx, ax
0x180003ecc  or      ebx, 80070000h
0x180003ed2  cmp     ebx, 80070002h
0x180003ed8  jnz     short loc_180003EEB
0x180003eda  lea     rcx, [rbp+57h+hKey]; this
0x180003ede  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180003ee3  mov     ebx, r12d
0x180003ee6  jmp     loc_1800040B6
0x180003eeb  test    ebx, ebx
0x180003eed  jns     short loc_180003F15
0x180003eef  mov     rcx, [rbp+5Fh]; this
0x180003ef3  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180003efa  mov     r9d, ebx; char *
0x180003efd  mov     edx, 0ED2h; void *
0x180003f02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003f07  lea     rcx, [rbp+57h+hKey]; this
0x180003f0b  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180003f10  jmp     loc_1800040B6
0x180003f15  mov     rcx, [rbp+57h+hKey]; hKey
0x180003f19  lea     rax, [rbp+57h+cSubKeys]
0x180003f1d  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180003f22  xor     r9d, r9d; lpReserved
0x180003f25  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180003f2a  xor     r8d, r8d; lpcchClass
0x180003f2d  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180003f32  xor     edx, edx; lpClass
0x180003f34  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180003f39  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x180003f3e  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180003f43  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180003f48  mov     [rsp+0C0h+phkResult], rax; int
0x180003f4d  mov     [rbp+57h+cSubKeys], r12d
0x180003f51  call    cs:__imp_RegQueryInfoKeyW
0x180003f57  mov     edi, eax
0x180003f59  test    eax, eax
0x180003f5b  jns     short loc_180003F7A
0x180003f5d  mov     rcx, [rbp+5Fh]; this
0x180003f61  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180003f68  mov     r9d, eax; char *
0x180003f6b  mov     edx, 0ED5h; void *
0x180003f70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003f75  jmp     loc_1800040AB
0x180003f7a  mov     eax, [rbp+57h+cSubKeys]
0x180003f7d  test    eax, eax
0x180003f7f  jnz     short loc_180003F9F
0x180003f81  mov     rcx, [rbp+57h+hKey]
0x180003f85  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180003f8a  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x180003f8e  test    rcx, rcx
0x180003f91  jz      short loc_180003F98
0x180003f93  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180003f98  xor     eax, eax
0x180003f9a  jmp     loc_1800040C1
0x180003f9f  mov     rsi, rax
0x180003fa2  mov     [rbp+57h+arg_10], r12
0x180003fa6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003fad  mov     eax, 18h
0x180003fb2  mul     rsi
0x180003fb5  lea     rdx, [rbp+57h+arg_10]; void **
0x180003fb9  cmovb   rax, rcx
0x180003fbd  mov     rcx, rax; Size
0x180003fc0  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180003fc5  mov     rbx, [rbp+57h+arg_10]
0x180003fc9  test    rbx, rbx
0x180003fcc  jz      short loc_180003FE7
0x180003fce  lea     r9, ??0_PackageInfo@AppxAllUserStore@@QEAA@XZ; void *(*)(void *)
0x180003fd5  mov     r8, rsi; unsigned __int64
0x180003fd8  mov     edx, 18h; unsigned __int64
0x180003fdd  mov     rcx, rbx; void *
0x180003fe0  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180003fe5  jmp     short loc_180003FEA
0x180003fe7  mov     rbx, r12
0x180003fea  mov     [rbp+57h+arg_10], rbx
0x180003fee  test    rbx, rbx
0x180003ff1  jnz     short loc_18000400F
0x180003ff3  lea     rcx, [rbp+57h+arg_10]
0x180003ff7  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x180003ffc  lea     rcx, [rbp+57h+hKey]; this
0x180004000  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180004005  mov     ebx, 8007000Eh
0x18000400a  jmp     loc_1800040B6
0x18000400f  mov     eax, [rbp+57h+cSubKeys]
0x180004012  xor     edx, edx; Val
0x180004014  mov     rcx, rbx; void *
0x180004017  lea     r8, [rax+rax*2]
0x18000401b  shl     r8, 3; Size
0x18000401f  call    memset_0
0x180004024  mov     esi, r12d
0x180004027  mov     eax, [rbp+57h+cSubKeys]
0x18000402a  cmp     esi, eax
0x18000402c  jnb     short loc_180004098
0x18000402e  xorps   xmm0, xmm0
0x180004031  mov     [rbp+57h+var_50], r12d
0x180004035  lea     r8, [rbp+57h+var_60]; struct Common::StringBuffer *
0x180004039  mov     edx, esi; unsigned int
0x18000403b  lea     rcx, [rbp+57h+hKey]; this
0x18000403f  movups  [rbp+57h+var_60], xmm0
0x180004043  call    ?EnumKey@RegistryKey@Common@@QEAAJKAEAVStringBuffer@2@PEAU_FILETIME@@@Z; Common::RegistryKey::EnumKey(ulong,Common::StringBuffer &,_FILETIME *)
0x180004048  mov     edi, eax
0x18000404a  test    eax, eax
0x18000404c  js      short loc_180004075
0x18000404e  mov     eax, esi
0x180004050  mov     dword ptr [rbp+57h+var_60], r12d
0x180004054  mov     [rbp+57h+var_50], r12d
0x180004058  lea     rcx, [rax+rax*2]
0x18000405c  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180004060  mov     [rbx+rcx*8], rax
0x180004064  lea     rcx, [rbp+57h+var_60]; this
0x180004068  mov     qword ptr [rbp+57h+var_60+8], r12
0x18000406c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180004071  inc     esi
0x180004073  jmp     short loc_180004027
0x180004075  mov     rcx, [rbp+5Fh]; this
0x180004079  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180004080  mov     r9d, edi; char *
0x180004083  mov     edx, 0EDFh; void *
0x180004088  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000408d  lea     rcx, [rbp+57h+var_60]; this
0x180004091  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180004096  jmp     short loc_1800040A2
0x180004098  mov     [r15], rbx
0x18000409b  mov     [r14], eax
0x18000409e  mov     [rbp+57h+arg_10], r12
0x1800040a2  lea     rcx, [rbp+57h+arg_10]
0x1800040a6  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800040ab  lea     rcx, [rbp+57h+hKey]; this
0x1800040af  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800040b4  mov     ebx, edi
0x1800040b6  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800040ba  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800040bf  mov     eax, ebx
0x1800040c1  add     rsp, 90h
0x1800040c8  pop     r15
0x1800040ca  pop     r14
0x1800040cc  pop     r12
0x1800040ce  pop     rdi
0x1800040cf  pop     rsi
0x1800040d0  pop     rbx
0x1800040d1  pop     rbp
0x1800040d2  retn
```
