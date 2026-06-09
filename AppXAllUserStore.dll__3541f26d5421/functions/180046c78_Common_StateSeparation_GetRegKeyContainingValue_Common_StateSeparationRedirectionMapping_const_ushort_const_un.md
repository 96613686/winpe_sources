# Common::StateSeparation::GetRegKeyContainingValue(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort const *,ulong,Common::RegistryKey *)

- ea: `0x180046c78`
- end: `0x180046ef2`
- name: `?GetRegKeyContainingValue@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEBGKPEAVRegistryKey@2@@Z`
- size: `634`
- prototype: `__int64 __usercall@<rax>(const struct Common::StateSeparationRedirectionMapping *@<rcx>, const unsigned __int16 **@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct Common::RegistryKey *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180046ef8`
- `0x180049070`
- `0x180049114`

## callees

- `0x180003da0`
- `0x180004920`
- `0x180004940`
- `0x180004968`
- `0x180004b4c`
- `0x180007278`
- `0x180007860`
- `0x180008db0`
- `0x18000d6a0`
- `0x180016a78`
- `0x180018248`
- `0x180046c78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d89`

## string_xrefs

- `0x180046cac`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180046cf9`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180046d42`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180046e3c`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180046e7b`: `onecore\base\appmodel\common\stateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Common::StateSeparation::GetRegKeyContainingValue(
        const struct Common::StateSeparationRedirectionMapping *a1,
        const unsigned __int16 **a2,
        HKEY a3,
        const unsigned __int16 *a4,
        bool a5,
        HKEY *phkResult)
{
  int IsStateSeparationEnabled; // eax
  unsigned __int64 v10; // r8
  unsigned int v11; // ebx
  int PersistedRegKeyPath; // eax
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  LSTATUS Value; // eax
  HKEY v18; // rbx
  HKEY *v19; // rdi
  const unsigned __int16 *v20; // r8
  int v21; // eax
  __int64 i; // rbx
  int appended; // eax
  unsigned int v24; // edi
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  unsigned int v27; // ecx
  int lpData; // [rsp+20h] [rbp-38h]
  LPCWSTR v29; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-20h] BYREF
  int v31; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  HKEY hKey; // [rsp+A0h] [rbp+48h] BYREF

  hKey = a3;
  a5 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&a5);
  v11 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
      (const char *)(unsigned int)IsStateSeparationEnabled,
      lpData);
    return v11;
  }
  if ( a5 )
  {
    v29 = 0;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(a1, a2, v10, (unsigned __int16 **)&v29);
    v11 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        lpData);
LABEL_21:
      Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)&v29);
      return v11;
    }
    hKey = 0;
    v14 = Common::RegistryKey::OpenIfExists(&hKey, HKEY_LOCAL_MACHINE, v29, 0x20119u);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = (unsigned int)v14;
      v16 = 146;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)v15,
        lpData);
      Common::RegistryKey::~RegistryKey(&hKey);
      goto LABEL_21;
    }
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      Value = RegQueryValueExW(hKey, a4, 0, 0, 0, 0);
      v11 = Value;
      if ( !Value || Value == 234 )
      {
        v18 = hKey;
        v19 = phkResult;
        hKey = 0;
        if ( *phkResult != v18 )
        {
          Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
          *v19 = v18;
        }
        Common::RegistryKey::~RegistryKey(&hKey);
        v11 = 0;
        goto LABEL_21;
      }
      if ( (unsigned int)(Value - 2) > 1 )
      {
        if ( Value > 0 )
          v11 = (unsigned __int16)Value | 0x80070000;
        if ( (v11 & 0x80000000) != 0 )
        {
          v15 = v11;
          v16 = 150;
          goto LABEL_9;
        }
      }
    }
    Common::RegistryKey::~RegistryKey(&hKey);
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)&v29);
  }
  v20 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
  if ( a2 )
  {
    v31 = 0;
    *(_OWORD *)lpSubKey = 0;
    v21 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)lpSubKey, v20);
    v11 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
        (const char *)(unsigned int)v21,
        lpData);
LABEL_34:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      return v11;
    }
    for ( i = 0; !i && *a2; i = 1 )
    {
      appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)lpSubKey, *a2);
      v24 = appended;
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
          (const char *)(unsigned int)appended,
          lpData);
        v11 = v24;
        goto LABEL_34;
      }
    }
    v25 = Common::RegistryKey::Open(phkResult, HKEY_LOCAL_MACHINE, lpSubKey[1], 0x20119u);
    if ( v25 < 0 )
    {
      v11 = v25;
      goto LABEL_34;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return 0;
  }
  else
  {
    v26 = Common::RegistryKey::Open(phkResult, HKEY_LOCAL_MACHINE, v20, 0x20119u);
    v27 = 0;
    if ( v26 < 0 )
      return (unsigned int)v26;
    return v27;
  }
}

```

## disassembly

```asm
0x180046c78  mov     [rsp-30h+hKey], r8
0x180046c7d  push    rbp
0x180046c7e  push    rbx
0x180046c7f  push    rsi
0x180046c80  push    rdi
0x180046c81  push    r13
0x180046c83  push    r14
0x180046c85  mov     rbp, rsp
0x180046c88  sub     rsp, 58h
0x180046c8c  mov     rdi, rcx
0x180046c8f  mov     [rbp+arg_20], 0
0x180046c93  lea     rcx, [rbp+arg_20]; bool *
0x180046c97  mov     r14, r9
0x180046c9a  mov     rsi, rdx
0x180046c9d  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180046ca2  mov     ebx, eax
0x180046ca4  test    eax, eax
0x180046ca6  jns     short loc_180046CC7
0x180046ca8  mov     rcx, [rbp+30h]; this
0x180046cac  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x180046cb3  mov     r9d, eax; char *
0x180046cb6  mov     edx, 8Ah; void *
0x180046cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046cc0  mov     eax, ebx
0x180046cc2  jmp     loc_180046EE5
0x180046cc7  cmp     [rbp+arg_20], 0
0x180046ccb  mov     r13, 0FFFFFFFF80000002h
0x180046cd2  jz      loc_180046E0D
0x180046cd8  lea     r9, [rbp+var_28]; unsigned __int16 **
0x180046cdc  mov     [rbp+var_28], 0
0x180046ce4  mov     rdx, rsi; unsigned __int16 **
0x180046ce7  mov     rcx, rdi; struct Common::StateSeparationRedirectionMapping *
0x180046cea  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x180046cef  mov     ebx, eax
0x180046cf1  test    eax, eax
0x180046cf3  jns     short loc_180046D12
0x180046cf5  mov     rcx, [rbp+30h]; this
0x180046cf9  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x180046d00  mov     r9d, eax; char *
0x180046d03  mov     edx, 90h; void *
0x180046d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046d0d  jmp     loc_180046DED
0x180046d12  mov     r8, [rbp+var_28]; lpSubKey
0x180046d16  lea     rcx, [rbp+hKey]; this
0x180046d1a  mov     r9d, 20119h; samDesired
0x180046d20  mov     [rbp+hKey], 0
0x180046d28  mov     rdx, r13; hKey
0x180046d2b  call    ?OpenIfExists@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::OpenIfExists(HKEY__ * const,ushort const *,ulong)
0x180046d30  mov     ebx, eax
0x180046d32  test    eax, eax
0x180046d34  jns     short loc_180046D5C
0x180046d36  mov     r9d, eax; char *
0x180046d39  mov     edx, 92h; void *
0x180046d3e  mov     rcx, [rbp+30h]; this
0x180046d42  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x180046d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046d4e  lea     rcx, [rbp+hKey]; this
0x180046d52  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180046d57  jmp     loc_180046DED
0x180046d5c  mov     rcx, [rbp+hKey]; hKey
0x180046d60  lea     rax, [rcx-1]
0x180046d64  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180046d68  ja      loc_180046DFB
0x180046d6e  mov     [rsp+58h+lpcbData], 0; lpcbData
0x180046d77  xor     r9d, r9d; lpType
0x180046d7a  xor     r8d, r8d; lpReserved
0x180046d7d  mov     [rsp+58h+lpData], 0; lpData
0x180046d86  mov     rdx, r14; lpValueName
0x180046d89  call    cs:__imp_RegQueryValueExW
0x180046d8f  mov     ebx, eax
0x180046d91  test    eax, eax
0x180046d93  jz      short loc_180046DC2
0x180046d95  cmp     eax, 0EAh
0x180046d9a  jz      short loc_180046DC2
0x180046d9c  lea     ecx, [rax-2]
0x180046d9f  cmp     ecx, 1
0x180046da2  jbe     short loc_180046DFB
0x180046da4  test    eax, eax
0x180046da6  jle     short loc_180046DB1
0x180046da8  movzx   ebx, ax
0x180046dab  or      ebx, 80070000h
0x180046db1  test    ebx, ebx
0x180046db3  jns     short loc_180046DFB
0x180046db5  mov     r9d, ebx
0x180046db8  mov     edx, 96h
0x180046dbd  jmp     loc_180046D3E
0x180046dc2  mov     rbx, [rbp+hKey]
0x180046dc6  mov     rdi, [rbp+phkResult]
0x180046dca  mov     [rbp+hKey], 0
0x180046dd2  cmp     [rdi], rbx
0x180046dd5  jz      short loc_180046DE2
0x180046dd7  mov     rcx, [rdi]
0x180046dda  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180046ddf  mov     [rdi], rbx
0x180046de2  lea     rcx, [rbp+hKey]; this
0x180046de6  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180046deb  xor     ebx, ebx
0x180046ded  lea     rcx, [rbp+var_28]
0x180046df1  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x180046df6  jmp     loc_180046CC0
0x180046dfb  lea     rcx, [rbp+hKey]; this
0x180046dff  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180046e04  lea     rcx, [rbp+var_28]
0x180046e08  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x180046e0d  mov     r8, [rdi+8]; lpSubKey
0x180046e11  test    rsi, rsi
0x180046e14  jz      loc_180046ECA
0x180046e1a  xor     eax, eax
0x180046e1c  lea     rcx, [rbp+lpSubKey]; this
0x180046e20  xorps   xmm0, xmm0
0x180046e23  mov     [rbp+var_10], eax
0x180046e26  mov     rdx, r8; Src
0x180046e29  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180046e2d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180046e32  mov     ebx, eax
0x180046e34  test    eax, eax
0x180046e36  jns     short loc_180046E52
0x180046e38  mov     rcx, [rbp+30h]; this
0x180046e3c  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x180046e43  mov     r9d, eax; char *
0x180046e46  mov     edx, 0A7h; void *
0x180046e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046e50  jmp     short loc_180046EAF
0x180046e52  xor     ebx, ebx
0x180046e54  cmp     rbx, 1
0x180046e58  jnb     short loc_180046E93
0x180046e5a  mov     rdx, [rsi+rbx*8]; unsigned __int16 *
0x180046e5e  test    rdx, rdx
0x180046e61  jz      short loc_180046E93
0x180046e63  lea     rcx, [rbp+lpSubKey]; struct Common::StringBuffer *
0x180046e67  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x180046e6c  mov     edi, eax
0x180046e6e  test    eax, eax
0x180046e70  js      short loc_180046E77
0x180046e72  inc     rbx
0x180046e75  jmp     short loc_180046E54
0x180046e77  mov     rcx, [rbp+30h]; this
0x180046e7b  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\common\\states"...
0x180046e82  mov     r9d, edi; char *
0x180046e85  mov     edx, 0AAh; void *
0x180046e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046e8f  mov     ebx, edi
0x180046e91  jmp     short loc_180046EAF
0x180046e93  mov     r8, [rbp+lpSubKey+8]; lpSubKey
0x180046e97  mov     r9d, 20119h; samDesired
0x180046e9d  mov     rcx, [rbp+phkResult]; phkResult
0x180046ea1  mov     rdx, r13; hKey
0x180046ea4  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180046ea9  test    eax, eax
0x180046eab  jns     short loc_180046EBD
0x180046ead  mov     ebx, eax
0x180046eaf  lea     rcx, [rbp+lpSubKey]; this
0x180046eb3  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180046eb8  jmp     loc_180046CC0
0x180046ebd  lea     rcx, [rbp+lpSubKey]; this
0x180046ec1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180046ec6  xor     eax, eax
0x180046ec8  jmp     short loc_180046EE5
0x180046eca  mov     rcx, [rbp+phkResult]; phkResult
0x180046ece  mov     r9d, 20119h; samDesired
0x180046ed4  mov     rdx, r13; hKey
0x180046ed7  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180046edc  xor     ecx, ecx
0x180046ede  test    eax, eax
0x180046ee0  cmovs   ecx, eax
0x180046ee3  mov     eax, ecx
0x180046ee5  add     rsp, 58h
0x180046ee9  pop     r14
0x180046eeb  pop     r13
0x180046eed  pop     rdi
0x180046eee  pop     rsi
0x180046eef  pop     rbx
0x180046ef0  pop     rbp
0x180046ef1  retn
```
