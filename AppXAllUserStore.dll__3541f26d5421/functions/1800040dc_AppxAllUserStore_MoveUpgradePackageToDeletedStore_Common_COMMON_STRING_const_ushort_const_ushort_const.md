# AppxAllUserStore::MoveUpgradePackageToDeletedStore(Common::COMMON_STRING const *,ushort const *,ushort const *)

- ea: `0x1800040dc`
- end: `0x18000462e`
- name: `?MoveUpgradePackageToDeletedStore@AppxAllUserStore@@YAJPEBUCOMMON_STRING@Common@@PEBG1@Z`
- size: `1362`
- prototype: `int(AppxAllUserStore *__hidden this, const struct Common::COMMON_STRING *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c94`

## callees

- `0x180002b1c`
- `0x1800036d4`
- `0x1800040dc`
- `0x180004920`
- `0x180004968`
- `0x180004b4c`
- `0x1800054a4`
- `0x180005540`
- `0x1800055ac`
- `0x180006c00`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x18000ce40`
- `0x18000d6a0`
- `0x180017f50`
- `0x180018248`
- `0x18001baf4`
- `0x18001f738`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004489`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800044fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004489`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800044fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000435e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000435e`

## string_xrefs

- `0x180004105`: `Deleted`
- `0x1800041bc`: `onecore\base\appmodel\common\pathhelpers.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::MoveUpgradePackageToDeletedStore(
        AppxAllUserStore *this,
        const struct Common::COMMON_STRING *a2,
        const unsigned __int16 *a3,
        struct Common::StringBuffer *a4)
{
  const unsigned __int16 *v5; // r14
  int AllUserChildStorePath; // ebx
  __int64 v8; // rdx
  const unsigned __int16 *v10; // rdi
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rdx
  LSTATUS v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rcx
  struct Common::StringBuffer *v16; // r9
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  const unsigned __int16 *v20; // rdx
  int appended; // eax
  const WCHAR *v22; // rbx
  LSTATUS v23; // eax
  __int64 v24; // rcx
  LSTATUS v25; // eax
  __int64 v26; // rcx
  const unsigned __int16 *v27; // r8
  __int64 *v28; // rdx
  LSTATUS v29; // eax
  __int64 v30; // rdx
  const unsigned __int16 *v31; // rdx
  struct Common::StringBuffer *v32; // r9
  int v33; // eax
  LSTATUS v34; // eax
  __int64 v35; // rcx
  LSTATUS v36; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  struct _SECURITY_ATTRIBUTES *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-91h]
  HKEY v39; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  HKEY v41; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR v42[2]; // [rsp+78h] [rbp-41h] BYREF
  LPCWSTR *v43; // [rsp+88h] [rbp-31h]
  LPCWSTR v44[2]; // [rsp+90h] [rbp-29h] BYREF
  int v45; // [rsp+A0h] [rbp-19h]
  DWORD v46; // [rsp+A8h] [rbp-11h] BYREF
  HKEY v47; // [rsp+B0h] [rbp-9h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+B8h] [rbp-1h] BYREF
  int v49; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  DWORD cSubKeys; // [rsp+138h] [rbp+7Fh] BYREF

  v5 = (const unsigned __int16 *)a2;
  LOBYTE(a2) = 1;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"Deleted",
                            (const unsigned __int16 *)a2,
                            (unsigned int *)v44,
                            a4);
  if ( AllUserChildStorePath < 0 )
  {
    v8 = 2674;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v8,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)AllUserChildStorePath);
LABEL_4:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v44);
    return (unsigned int)AllUserChildStorePath;
  }
  v42[1] = (LPCWSTR)v44;
  v42[0] = (LPCWSTR)&Common::StringBufferBuilder::`vftable';
  v43 = v44;
  v10 = L"Upgrade";
  do
  {
    if ( !(unsigned __int8)Common::IsPathSeparator(*v10) )
      break;
    ++v10;
  }
  while ( v10 );
  if ( v10 && *v10 )
  {
    AllUserChildStorePath = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBufferBuilder *)v42);
    if ( AllUserChildStorePath < 0 )
    {
      v11 = 140;
      goto LABEL_15;
    }
    AllUserChildStorePath = Common::StringBuilder::AppendString((Common::StringBuilder *)v42, v10);
    if ( AllUserChildStorePath < 0 )
    {
      v11 = 141;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\common\\pathhelpers.cpp",
        (const char *)(unsigned int)AllUserChildStorePath,
        phkResult);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA73,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)AllUserChildStorePath);
      if ( v44[1] )
        Common::GlobalHeap::Free((void *)v44[1]);
      return (unsigned int)AllUserChildStorePath;
    }
  }
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v42[1] = (LPCWSTR)v44;
  v42[0] = (LPCWSTR)&Common::StringBufferBuilder::`vftable';
  v43 = v44;
  AllUserChildStorePath = Common::PathHelpers::AppendPathSegment((struct Common::StringBufferBuilder *)v42, v12);
  if ( AllUserChildStorePath < 0 )
  {
    v8 = 2676;
    goto LABEL_3;
  }
  AllUserChildStorePath = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v44, v5);
  if ( AllUserChildStorePath < 0 )
  {
    v8 = 2677;
    goto LABEL_3;
  }
  AllUserChildStorePath = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v44, a3);
  if ( AllUserChildStorePath < 0 )
  {
    v8 = 2678;
    goto LABEL_3;
  }
  v41 = 0;
  v13 = Common::RegistryKey::Create(&v41, HKEY_LOCAL_MACHINE, v44[1], 0xF001Fu, phkResult, lpcbMaxSubKeyLen, 0);
  AllUserChildStorePath = v13;
  if ( v13 < 0 )
  {
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      McTemplateU0zd_EventWriteTransfer(v15, AppxAllUserStoreCreateKeyError, v44[1], (unsigned int)v13);
    goto LABEL_26;
  }
  v49 = 0;
  LOBYTE(v14) = 1;
  *(_OWORD *)lpSubKey = 0;
  v17 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"Upgrade", v14, (unsigned int *)lpSubKey, v16);
  AllUserChildStorePath = v17;
  if ( v17 < 0 )
  {
    v18 = (unsigned int)v17;
    v19 = 2693;
LABEL_29:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v19,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)v18);
LABEL_30:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
LABEL_26:
    Common::RegistryKey::~RegistryKey(&v41);
    goto LABEL_4;
  }
  v20 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v42[1] = (LPCWSTR)lpSubKey;
  v42[0] = (LPCWSTR)&Common::StringBufferBuilder::`vftable';
  v43 = lpSubKey;
  appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBufferBuilder *)v42, v20);
  AllUserChildStorePath = appended;
  if ( appended < 0 )
  {
    v18 = (unsigned int)appended;
    v19 = 2694;
    goto LABEL_29;
  }
  v22 = lpSubKey[1];
  Common::AutoHandleCloseHKEY<HKEY__ *>(0);
  v39 = 0;
  v23 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v22, 0, 0x2001Fu, &v39);
  AllUserChildStorePath = v23;
  if ( v23 > 0 )
    AllUserChildStorePath = (unsigned __int16)v23 | 0x80070000;
  if ( (unsigned int)(AllUserChildStorePath + 2147024894) > 1 )
  {
    if ( AllUserChildStorePath < 0 )
    {
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        McTemplateU0zd_EventWriteTransfer(
          v24,
          AppxAllUserStoreOpenKeyError,
          lpSubKey[1],
          (unsigned int)AllUserChildStorePath);
      goto LABEL_67;
    }
    hKey = 0;
    v25 = Common::RegistryKey::OpenSubKey(
            (Common::RegistryKey *)&v39,
            v5,
            0x20019u,
            (struct Common::AutoHandleHKEY *)&hKey);
    AllUserChildStorePath = v25;
    if ( v25 >= 0 )
    {
      v25 = Common::RegistryKey::CopyTree(&hKey, a3, &v41);
      AllUserChildStorePath = v25;
      if ( v25 < 0 )
      {
        if ( Microsoft_Windows_AppXDeployment_ServerEnableBits >= 0 )
          goto LABEL_66;
        v27 = a3;
        v28 = AppxAllUserStoreCopyRegTreeError;
        goto LABEL_42;
      }
      v29 = Common::RegistryKey::DeleteSubKeyTree(&hKey, a3);
      AllUserChildStorePath = v29;
      if ( v29 >= 0 )
      {
        cSubKeys = 0;
        v29 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        AllUserChildStorePath = v29;
        if ( v29 >= 0 )
        {
          if ( cSubKeys )
            goto LABEL_66;
          v29 = Common::RegistryKey::DeleteSubKeyTree(&v39, v5);
          AllUserChildStorePath = v29;
          if ( v29 >= 0 )
          {
            v46 = 0;
            v29 = RegQueryInfoKeyW(v39, 0, 0, 0, &v46, 0, 0, 0, 0, 0, 0, 0);
            AllUserChildStorePath = v29;
            if ( v29 >= 0 )
            {
              if ( !v46 )
              {
                LODWORD(v43) = 0;
                LOBYTE(v31) = 1;
                *(_OWORD *)v42 = 0;
                v33 = AppxAllUserStore::GetAllUserChildStorePath(
                        (AppxAllUserStore *)L"Upgrade",
                        v31,
                        (unsigned int *)v42,
                        v32);
                AllUserChildStorePath = v33;
                if ( v33 >= 0 )
                {
                  v47 = 0;
                  v34 = Common::RegistryKey::Open(&v47, HKEY_LOCAL_MACHINE, v42[1], 0x2001Fu);
                  AllUserChildStorePath = v34;
                  if ( v34 >= 0 )
                  {
                    v36 = Common::RegistryKey::DeleteSubKeyTree(&v47, *((const unsigned __int16 **)this + 1));
                    AllUserChildStorePath = v36;
                    if ( v36 < 0 )
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0xAC9,
                        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                        (const char *)(unsigned int)v36);
                  }
                  else if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
                  {
                    McTemplateU0zd_EventWriteTransfer(v35, AppxAllUserStoreOpenKeyError, v42[1], (unsigned int)v34);
                  }
                  Common::RegistryKey::~RegistryKey(&v47);
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0xAC0,
                    (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                    (const char *)(unsigned int)v33);
                }
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v42);
              }
              goto LABEL_66;
            }
            v30 = 2746;
          }
          else
          {
            v30 = 2742;
          }
        }
        else
        {
          v30 = 2737;
        }
      }
      else
      {
        v30 = 2733;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v30,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v29);
    }
    else if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    {
      v27 = v5;
      v28 = AppxAllUserStoreOpenKeyError;
LABEL_42:
      McTemplateU0zd_EventWriteTransfer(v26, v28, v27, (unsigned int)v25);
    }
LABEL_66:
    Common::RegistryKey::~RegistryKey(&hKey);
LABEL_67:
    Common::RegistryKey::~RegistryKey(&v39);
    goto LABEL_30;
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(v39);
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  Common::AutoHandleCloseHKEY<HKEY__ *>(v41);
  if ( v44[1] )
    Common::GlobalHeap::Free((void *)v44[1]);
  return 0;
}

```

## disassembly

```asm
0x1800040dc  push    rbp
0x1800040de  push    rbx
0x1800040df  push    rsi
0x1800040e0  push    rdi
0x1800040e1  push    r12
0x1800040e3  push    r13
0x1800040e5  push    r14
0x1800040e7  push    r15
0x1800040e9  lea     rbp, [rsp-1Fh]
0x1800040ee  sub     rsp, 0D8h
0x1800040f5  mov     rsi, r8
0x1800040f8  mov     r14, rdx
0x1800040fb  mov     r15, rcx
0x1800040fe  lea     r8, [rbp+57h+var_80]; bool
0x180004102  xorps   xmm0, xmm0
0x180004105  lea     rcx, ?deletedApplicationsString@AppxAllUserStore@@3QBGB; "Deleted"
0x18000410c  xor     r12d, r12d
0x18000410f  mov     dl, 1; unsigned __int16 *
0x180004111  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180004115  mov     [rbp+57h+var_70], r12d
0x180004119  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18000411e  mov     ebx, eax
0x180004120  test    eax, eax
0x180004122  jns     short loc_18000414C
0x180004124  mov     edx, 0A72h; void *
0x180004129  mov     rcx, [rbp+5Fh]; this
0x18000412d  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180004134  mov     r9d, ebx; char *
0x180004137  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000413c  lea     rcx, [rbp+57h+var_80]; this
0x180004140  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180004145  mov     eax, ebx
0x180004147  jmp     loc_18000461A
0x18000414c  lea     rax, [rbp+57h+var_80]
0x180004150  mov     [rbp+57h+var_98+8], rax
0x180004154  lea     r13, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18000415b  lea     rax, [rbp+57h+var_80]
0x18000415f  mov     [rbp+57h+var_98], r13
0x180004163  mov     [rbp+57h+var_88], rax
0x180004167  lea     rdi, ?upgradeApplicationsString@AppxAllUserStore@@3QBGB; "Upgrade"
0x18000416e  movzx   ecx, word ptr [rdi]
0x180004171  call    Common__IsPathSeparator
0x180004176  test    al, al
0x180004178  jz      short loc_180004180
0x18000417a  add     rdi, 2
0x18000417e  jnz     short loc_18000416E
0x180004180  test    rdi, rdi
0x180004183  jz      short loc_1800041FA
0x180004185  cmp     [rdi], r12w
0x180004189  jz      short loc_1800041FA
0x18000418b  lea     rcx, [rbp+57h+var_98]; struct Common::StringBufferBuilder *
0x18000418f  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBufferBuilder *)
0x180004194  mov     ebx, eax
0x180004196  test    eax, eax
0x180004198  jns     short loc_1800041A1
0x18000419a  mov     edx, 8Ch
0x18000419f  jmp     short loc_1800041B8
0x1800041a1  mov     rdx, rdi; unsigned __int16 *
0x1800041a4  lea     rcx, [rbp+57h+var_98]; this
0x1800041a8  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800041ad  mov     ebx, eax
0x1800041af  test    eax, eax
0x1800041b1  jns     short loc_1800041FA
0x1800041b3  mov     edx, 8Dh; void *
0x1800041b8  mov     rcx, [rbp+5Fh]; this
0x1800041bc  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\common\\pathhe"...
0x1800041c3  mov     r9d, ebx; char *
0x1800041c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041cb  mov     rcx, [rbp+5Fh]; this
0x1800041cf  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800041d6  mov     r9d, ebx; char *
0x1800041d9  mov     edx, 0A73h; void *
0x1800041de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800041e3  mov     rcx, [rbp+57h+var_80+8]; void *
0x1800041e7  test    rcx, rcx
0x1800041ea  jz      loc_180004145
0x1800041f0  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800041f5  jmp     loc_180004145
0x1800041fa  mov     rdx, [r15+8]; unsigned __int16 *
0x1800041fe  lea     rax, [rbp+57h+var_80]
0x180004202  mov     [rbp+57h+var_98+8], rax
0x180004206  lea     rcx, [rbp+57h+var_98]; struct Common::StringBufferBuilder *
0x18000420a  lea     rax, [rbp+57h+var_80]
0x18000420e  mov     [rbp+57h+var_98], r13
0x180004212  mov     [rbp+57h+var_88], rax
0x180004216  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBufferBuilder *,ushort const *)
0x18000421b  mov     ebx, eax
0x18000421d  test    eax, eax
0x18000421f  jns     short loc_18000422B
0x180004221  mov     edx, 0A74h
0x180004226  jmp     loc_180004129
0x18000422b  mov     rdx, r14; unsigned __int16 *
0x18000422e  lea     rcx, [rbp+57h+var_80]; struct Common::StringBuffer *
0x180004232  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x180004237  mov     ebx, eax
0x180004239  test    eax, eax
0x18000423b  jns     short loc_180004247
0x18000423d  mov     edx, 0A75h
0x180004242  jmp     loc_180004129
0x180004247  mov     rdx, rsi; unsigned __int16 *
0x18000424a  lea     rcx, [rbp+57h+var_80]; struct Common::StringBuffer *
0x18000424e  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x180004253  mov     ebx, eax
0x180004255  test    eax, eax
0x180004257  jns     short loc_180004263
0x180004259  mov     edx, 0A76h
0x18000425e  jmp     loc_180004129
0x180004263  mov     r8, [rbp+57h+var_80+8]; lpSubKey
0x180004267  lea     rcx, [rbp+57h+var_A0]; phkResult
0x18000426b  mov     rdi, 0FFFFFFFF80000002h
0x180004272  mov     [rbp+57h+var_A0], r12
0x180004276  mov     rdx, rdi; hKey
0x180004279  mov     [rsp+110h+lpcbMaxClassLen], r12; LPDWORD
0x18000427e  mov     r9d, 0F001Fh; samDesired
0x180004284  call    ?Create@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAK@Z; Common::RegistryKey::Create(HKEY__ * const,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,ulong *)
0x180004289  mov     ebx, eax
0x18000428b  test    eax, eax
0x18000428d  jns     short loc_1800042B9
0x18000428f  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r12b
0x180004296  jge     short loc_1800042AB
0x180004298  mov     r8, [rbp+57h+var_80+8]
0x18000429c  lea     rdx, AppxAllUserStoreCreateKeyError
0x1800042a3  mov     r9d, eax
0x1800042a6  call    McTemplateU0zd_EventWriteTransfer
0x1800042ab  lea     rcx, [rbp+57h+var_A0]; this
0x1800042af  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x1800042b4  jmp     loc_18000413C
0x1800042b9  xorps   xmm0, xmm0
0x1800042bc  mov     [rbp+57h+var_48], r12d
0x1800042c0  lea     r8, [rbp+57h+lpSubKey]; bool
0x1800042c4  mov     dl, 1; unsigned __int16 *
0x1800042c6  lea     rcx, ?upgradeApplicationsString@AppxAllUserStore@@3QBGB; "Upgrade"
0x1800042cd  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x1800042d1  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x1800042d6  mov     ebx, eax
0x1800042d8  test    eax, eax
0x1800042da  jns     short loc_1800042FF
0x1800042dc  mov     r9d, eax; char *
0x1800042df  mov     edx, 0A85h; void *
0x1800042e4  mov     rcx, [rbp+5Fh]; this
0x1800042e8  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800042ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800042f4  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800042f8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800042fd  jmp     short loc_1800042AB
0x1800042ff  mov     rdx, [r15+8]; unsigned __int16 *
0x180004303  lea     rax, [rbp+57h+lpSubKey]
0x180004307  mov     [rbp+57h+var_98+8], rax
0x18000430b  lea     rcx, [rbp+57h+var_98]; struct Common::StringBufferBuilder *
0x18000430f  lea     rax, [rbp+57h+lpSubKey]
0x180004313  mov     [rbp+57h+var_98], r13
0x180004317  mov     [rbp+57h+var_88], rax
0x18000431b  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBufferBuilder *,ushort const *)
0x180004320  mov     ebx, eax
0x180004322  test    eax, eax
0x180004324  jns     short loc_180004330
0x180004326  mov     r9d, eax
0x180004329  mov     edx, 0A86h
0x18000432e  jmp     short loc_1800042E4
0x180004330  mov     rbx, [rbp+57h+lpSubKey+8]
0x180004334  xor     ecx, ecx
0x180004336  mov     [rbp+57h+var_B0], r12
0x18000433a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000433f  lea     rax, [rbp+57h+var_B0]
0x180004343  mov     [rbp+57h+var_B0], r12
0x180004347  mov     r13d, 2001Fh
0x18000434d  mov     [rsp+110h+phkResult], rax; int
0x180004352  mov     r9d, r13d; samDesired
0x180004355  xor     r8d, r8d; ulOptions
0x180004358  mov     rdx, rbx; lpSubKey
0x18000435b  mov     rcx, rdi; hKey
0x18000435e  call    cs:__imp_RegOpenKeyExW
0x180004364  mov     ebx, eax
0x180004366  test    eax, eax
0x180004368  jle     short loc_180004373
0x18000436a  movzx   ebx, ax
0x18000436d  or      ebx, 80070000h
0x180004373  lea     eax, [rbx+7FF8FFFEh]
0x180004379  cmp     eax, 1
0x18000437c  jbe     loc_1800045EA
0x180004382  test    ebx, ebx
0x180004384  jns     short loc_1800043AB
0x180004386  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r12b
0x18000438d  jge     loc_1800045DC
0x180004393  mov     r8, [rbp+57h+lpSubKey+8]
0x180004397  lea     rdx, AppxAllUserStoreOpenKeyError
0x18000439e  mov     r9d, ebx
0x1800043a1  call    McTemplateU0zd_EventWriteTransfer
0x1800043a6  jmp     loc_1800045DC
0x1800043ab  lea     r9, [rbp+57h+hKey]; struct Common::AutoHandleHKEY *
0x1800043af  mov     [rbp+57h+hKey], r12
0x1800043b3  mov     r8d, 20019h; unsigned int
0x1800043b9  lea     rcx, [rbp+57h+var_B0]; this
0x1800043bd  mov     rdx, r14; unsigned __int16 *
0x1800043c0  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x1800043c5  mov     ebx, eax
0x1800043c7  test    eax, eax
0x1800043c9  jns     short loc_1800043EF
0x1800043cb  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r12b
0x1800043d2  jge     loc_1800045D3
0x1800043d8  mov     r8, r14
0x1800043db  lea     rdx, AppxAllUserStoreOpenKeyError
0x1800043e2  mov     r9d, eax
0x1800043e5  call    McTemplateU0zd_EventWriteTransfer
0x1800043ea  jmp     loc_1800045D3
0x1800043ef  lea     r8, [rbp+57h+var_A0]; struct Common::AutoHandleHKEY *
0x1800043f3  mov     rdx, rsi; unsigned __int16 *
0x1800043f6  lea     rcx, [rbp+57h+hKey]; this
0x1800043fa  call    ?CopyTree@RegistryKey@Common@@QEAAJPEBGAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::CopyTree(ushort const *,Common::AutoHandleHKEY &)
0x1800043ff  mov     ebx, eax
0x180004401  test    eax, eax
0x180004403  jns     short loc_18000441E
0x180004405  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r12b
0x18000440c  jge     loc_1800045D3
0x180004412  mov     r8, rsi
0x180004415  lea     rdx, AppxAllUserStoreCopyRegTreeError
0x18000441c  jmp     short loc_1800043E2
0x18000441e  mov     rdx, rsi; unsigned __int16 *
0x180004421  lea     rcx, [rbp+57h+hKey]; this
0x180004425  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18000442a  mov     ebx, eax
0x18000442c  test    eax, eax
0x18000442e  jns     short loc_18000444D
0x180004430  mov     edx, 0AADh; void *
0x180004435  mov     rcx, [rbp+5Fh]; this
0x180004439  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180004440  mov     r9d, eax; char *
0x180004443  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004448  jmp     loc_1800045D3
0x18000444d  mov     rcx, [rbp+57h+hKey]; hKey
0x180004451  lea     rax, [rbp+57h+cSubKeys]
0x180004455  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000445a  xor     r9d, r9d; lpReserved
0x18000445d  mov     [rsp+110h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180004462  xor     r8d, r8d; lpcchClass
0x180004465  mov     [rsp+110h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000446a  xor     edx, edx; lpClass
0x18000446c  mov     [rsp+110h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180004471  mov     [rsp+110h+lpcValues], r12; lpcValues
0x180004476  mov     [rsp+110h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000447b  mov     [rsp+110h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180004480  mov     [rsp+110h+phkResult], rax; lpcSubKeys
0x180004485  mov     [rbp+57h+cSubKeys], r12d
0x180004489  call    cs:__imp_RegQueryInfoKeyW
0x18000448f  mov     ebx, eax
0x180004491  test    eax, eax
0x180004493  jns     short loc_18000449C
0x180004495  mov     edx, 0AB1h
0x18000449a  jmp     short loc_180004435
0x18000449c  cmp     [rbp+57h+cSubKeys], r12d
0x1800044a0  jnz     loc_1800045D3
0x1800044a6  mov     rdx, r14; unsigned __int16 *
0x1800044a9  lea     rcx, [rbp+57h+var_B0]; this
0x1800044ad  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x1800044b2  mov     ebx, eax
0x1800044b4  test    eax, eax
0x1800044b6  jns     short loc_1800044C2
0x1800044b8  mov     edx, 0AB6h
0x1800044bd  jmp     loc_180004435
0x1800044c2  mov     rcx, [rbp+57h+var_B0]; hKey
0x1800044c6  lea     rax, [rbp+57h+var_68]
0x1800044ca  mov     [rsp+110h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800044cf  xor     r9d, r9d; lpReserved
0x1800044d2  mov     [rsp+110h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800044d7  xor     r8d, r8d; lpcchClass
0x1800044da  mov     [rsp+110h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800044df  xor     edx, edx; lpClass
0x1800044e1  mov     [rsp+110h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1800044e6  mov     [rsp+110h+lpcValues], r12; lpcValues
0x1800044eb  mov     [rsp+110h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800044f0  mov     [rsp+110h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800044f5  mov     [rsp+110h+phkResult], rax; int
0x1800044fa  mov     [rbp+57h+var_68], r12d
0x1800044fe  call    cs:__imp_RegQueryInfoKeyW
0x180004504  mov     ebx, eax
0x180004506  test    eax, eax
0x180004508  jns     short loc_180004514
0x18000450a  mov     edx, 0ABAh
0x18000450f  jmp     loc_180004435
0x180004514  cmp     [rbp+57h+var_68], r12d
0x180004518  jnz     loc_1800045D3
0x18000451e  xorps   xmm0, xmm0
0x180004521  mov     dword ptr [rbp+57h+var_88], r12d
0x180004525  lea     r8, [rbp+57h+var_98]; bool
0x180004529  mov     dl, 1; unsigned __int16 *
0x18000452b  lea     rcx, ?upgradeApplicationsString@AppxAllUserStore@@3QBGB; "Upgrade"
0x180004532  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180004536  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18000453b  mov     ebx, eax
0x18000453d  test    eax, eax
0x18000453f  jns     short loc_18000455B
0x180004541  mov     rcx, [rbp+5Fh]; this
0x180004545  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000454c  mov     r9d, eax; char *
0x18000454f  mov     edx, 0AC0h; void *
0x180004554  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004559  jmp     short loc_1800045CA
0x18000455b  mov     r8, [rbp+57h+var_98+8]; lpSubKey
0x18000455f  lea     rcx, [rbp+57h+var_60]; phkResult
0x180004563  mov     r9d, r13d; samDesired
  ... truncated ...
```
