# AppxAllUserStore::GetUInt32ConfigData(ushort const *,ushort const *,uint *)

- ea: `0x180015540`
- end: `0x1800156ca`
- name: `?GetUInt32ConfigData@AppxAllUserStore@@YAJPEBG0PEAI@Z`
- size: `394`
- prototype: `int(AppxAllUserStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x180004920`
- `0x180004940`
- `0x180004968`
- `0x180004b4c`
- `0x1800062c4`
- `0x18000a170`
- `0x18000d6a0`
- `0x18000d7b0`
- `0x180015540`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800155b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800155b8`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetUInt32ConfigData(
        AppxAllUserStore *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  int PackageFamilyNameFromPackageFullName; // eax
  LSTATUS UInt32Value; // ebx
  wchar_t **v7; // rbx
  struct Common::StringBuffer *v8; // rdx
  int ConfigFullPath; // eax
  __int64 v10; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-20h] BYREF
  int v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v17; // [rsp+70h] [rbp+20h] BYREF
  int v18; // [rsp+74h] [rbp+24h]
  LPCWCH lpString1; // [rsp+80h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+38h] BYREF

  v18 = HIDWORD(this);
  *a3 = 0;
  lpString1 = 0;
  v17 = 0;
  PackageFamilyNameFromPackageFullName = AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(
                                           a2,
                                           (unsigned __int16 *)&v17,
                                           (unsigned int *)&lpString1,
                                           a4);
  UInt32Value = PackageFamilyNameFromPackageFullName;
  if ( PackageFamilyNameFromPackageFullName >= 0 )
  {
    v7 = &off_18004E6E0;
    while ( CompareStringOrdinal(lpString1, -1, *v7, -1, 1) != 2 )
    {
      v7 += 2;
      if ( v7 == (wchar_t **)&qword_18004E750 )
      {
        v15 = 0;
        *(_OWORD *)lpSubKey = 0;
        ConfigFullPath = AppxAllUserStore::GetConfigFullPath((void **)lpSubKey, v8);
        UInt32Value = ConfigFullPath;
        if ( ConfigFullPath < 0 )
        {
          v10 = 422;
          goto LABEL_8;
        }
        ConfigFullPath = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)lpSubKey, lpString1);
        UInt32Value = ConfigFullPath;
        if ( ConfigFullPath < 0 )
        {
          v10 = 423;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v10,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)(unsigned int)ConfigFullPath,
            bIgnoreCasea);
LABEL_9:
          Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
          goto LABEL_18;
        }
        phkResult = 0;
        UInt32Value = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, lpSubKey[1], 0x20019u);
        if ( UInt32Value < 0
          || (UInt32Value = Common::RegistryKey::GetUInt32Value((Common::RegistryKey *)&phkResult, L"SetupPhase", a3),
              UInt32Value < 0) )
        {
          Common::RegistryKey::~RegistryKey(&phkResult);
          goto LABEL_9;
        }
        Common::RegistryKey::~RegistryKey(&phkResult);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
        Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)&lpString1);
        return 0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      *a3 = 2128;
      UInt32Value = 0;
      goto LABEL_18;
    }
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)&lpString1);
    return 2147942403LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromPackageFullName,
      bIgnoreCase);
LABEL_18:
    Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&void Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>((PVOID *)&lpString1);
    return (unsigned int)UInt32Value;
  }
}

```

## disassembly

```asm
0x180015540  mov     qword ptr [rsp-18h+arg_0], rcx
0x180015545  push    rbp
0x180015546  push    rbx
0x180015547  push    rdi
0x180015548  mov     rbp, rsp
0x18001554b  sub     rsp, 50h
0x18001554f  mov     rdi, r8
0x180015552  mov     dword ptr [r8], 0
0x180015559  mov     rcx, rdx; lpString1
0x18001555c  mov     [rbp+lpString1], 0
0x180015564  lea     r8, [rbp+lpString1]; unsigned int *
0x180015568  mov     [rbp+arg_0], 0
0x18001556f  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180015573  call    ?GetPackageFamilyNameFromPackageFullName@AppxAllUserStore@@YAJPEBGPEAIPEAPEAG@Z; AppxAllUserStore::GetPackageFamilyNameFromPackageFullName(ushort const *,uint *,ushort * *)
0x180015578  mov     ebx, eax
0x18001557a  test    eax, eax
0x18001557c  jns     short loc_18001559B
0x18001557e  mov     rcx, [rbp+18h]; this
0x180015582  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180015589  mov     r9d, eax; char *
0x18001558c  mov     edx, 17Bh; void *
0x180015591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015596  jmp     loc_1800156A7
0x18001559b  lea     rbx, off_18004E6E0; "Microsoft.Paint_8wekyb3d8bbwe"
0x1800155a2  mov     r8, [rbx]; lpString2
0x1800155a5  or      r9d, 0FFFFFFFFh; cchCount2
0x1800155a9  mov     rcx, [rbp+lpString1]; lpString1
0x1800155ad  or      edx, r9d; cchCount1
0x1800155b0  mov     [rsp+50h+bIgnoreCase], 1; int
0x1800155b8  call    cs:__imp_CompareStringOrdinal
0x1800155be  cmp     eax, 2
0x1800155c1  jz      loc_180015699
0x1800155c7  add     rbx, 10h
0x1800155cb  lea     rax, qword_18004E750
0x1800155d2  cmp     rbx, rax
0x1800155d5  jnz     short loc_1800155A2
0x1800155d7  xor     eax, eax
0x1800155d9  lea     rcx, [rbp+lpSubKey]; this
0x1800155dd  xorps   xmm0, xmm0
0x1800155e0  mov     [rbp+var_10], eax
0x1800155e3  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x1800155e7  call    ?GetConfigFullPath@AppxAllUserStore@@YAJPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetConfigFullPath(Common::StringBuffer *)
0x1800155ec  mov     ebx, eax
0x1800155ee  test    eax, eax
0x1800155f0  jns     short loc_180015618
0x1800155f2  mov     edx, 1A6h; void *
0x1800155f7  mov     rcx, [rbp+18h]; this
0x1800155fb  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x180015602  mov     r9d, eax; char *
0x180015605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001560a  lea     rcx, [rbp+lpSubKey]; this
0x18001560e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180015613  jmp     loc_1800156A7
0x180015618  mov     rdx, [rbp+lpString1]; unsigned __int16 *
0x18001561c  lea     rcx, [rbp+lpSubKey]; struct Common::StringBuffer *
0x180015620  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x180015625  mov     ebx, eax
0x180015627  test    eax, eax
0x180015629  jns     short loc_180015632
0x18001562b  mov     edx, 1A7h
0x180015630  jmp     short loc_1800155F7
0x180015632  mov     r8, [rbp+lpSubKey+8]; lpSubKey
0x180015636  lea     rcx, [rbp+phkResult]; phkResult
0x18001563a  mov     r9d, 20019h; samDesired
0x180015640  mov     [rbp+phkResult], 0
0x180015648  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001564f  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180015654  lea     rcx, [rbp+phkResult]; this
0x180015658  mov     ebx, eax
0x18001565a  test    eax, eax
0x18001565c  jns     short loc_180015665
0x18001565e  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180015663  jmp     short loc_18001560A
0x180015665  mov     r8, rdi; unsigned int *
0x180015668  lea     rdx, aSetupphase; "SetupPhase"
0x18001566f  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x180015674  lea     rcx, [rbp+phkResult]; this
0x180015678  mov     ebx, eax
0x18001567a  test    eax, eax
0x18001567c  js      short loc_18001565E
0x18001567e  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180015683  lea     rcx, [rbp+lpSubKey]; this
0x180015687  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18001568c  lea     rcx, [rbp+lpString1]
0x180015690  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x180015695  xor     eax, eax
0x180015697  jmp     short loc_1800156C2
0x180015699  cmp     byte ptr [rbx+8], 0
0x18001569d  jz      short loc_1800156B4
0x18001569f  mov     dword ptr [rdi], 850h
0x1800156a5  xor     ebx, ebx
0x1800156a7  lea     rcx, [rbp+lpString1]
0x1800156ab  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800156b0  mov     eax, ebx
0x1800156b2  jmp     short loc_1800156C2
0x1800156b4  lea     rcx, [rbp+lpString1]
0x1800156b8  call    ??1?$AutoArray@U_MainPackageInfo@AppxAllUserStore@@$1??$AutoArrayDeallocate@U_MainPackageInfo@AppxAllUserStore@@@Common@@YAXPEAU12@@Z@Common@@QEAA@XZ; Common::AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>::~AutoArray<AppxAllUserStore::_MainPackageInfo,&Common::AutoArrayDeallocate<AppxAllUserStore::_MainPackageInfo>(AppxAllUserStore::_MainPackageInfo *)>(void)
0x1800156bd  mov     eax, 80070003h
0x1800156c2  add     rsp, 50h
0x1800156c6  pop     rdi
0x1800156c7  pop     rbx
0x1800156c8  pop     rbp
0x1800156c9  retn
```
