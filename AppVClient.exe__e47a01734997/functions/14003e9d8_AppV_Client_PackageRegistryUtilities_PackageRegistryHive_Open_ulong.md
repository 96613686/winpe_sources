# AppV::Client::PackageRegistryUtilities::PackageRegistryHive::Open(ulong)

- ea: `0x14003e9d8`
- end: `0x14003ebf8`
- name: `?Open@PackageRegistryHive@PackageRegistryUtilities@Client@AppV@@QEAA_KK@Z`
- size: `544`
- prototype: `unsigned __int64(AppV::Client::PackageRegistryUtilities::PackageRegistryHive *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14003e6b0`

## callees

- `0x1400042a4`
- `0x140018bec`
- `0x14003e4dc`
- `0x14003e55c`
- `0x14003e9d8`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!RegOpenCurrentUser` at `0x14003eb4b`
- `ADVAPI32!RegOpenCurrentUser` at `0x14003eb4b`
- `KERNEL32!GetLastError` at `0x14003eab3`
- `KERNEL32!GetLastError` at `0x14003eab3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eacb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eb00`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eb63`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003ebb1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eacb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eb00`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003eb63`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003ebb1`

## string_xrefs

- `0x14003eac0`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003eadb`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003eb10`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003eb5c`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003eb73`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003ebaa`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003ebc1`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall AppV::Client::PackageRegistryUtilities::PackageRegistryHive::Open(HKEY *this, REGSAM a2)
{
  softgrid::shared::revert_to_self *v3; // rdi
  HKEY v4; // rbx
  volatile signed __int32 *v5; // rdi
  DWORD LastError; // eax
  __int64 v7; // rbx
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rax
  __int64 v11; // rcx
  char *v12; // rax
  const char *v13; // rax
  unsigned __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdi
  char *v17; // rax
  const char *v18; // rax
  char *v20; // rax
  const char *v21; // rax
  softgrid::shared::revert_to_self *v22; // [rsp+30h] [rbp+8h] BYREF

  if ( *this != HKEY_LOCAL_MACHINE )
  {
    if ( *this != HKEY_CURRENT_USER )
    {
      v20 = strrchr("admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp", 92);
      if ( v20 )
        v21 = v20 + 1;
      else
        v21 = "admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp";
      FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v21);
      v11 = 0x170500070001LL;
      goto LABEL_29;
    }
    v15 = RegOpenCurrentUser(a2, this + 1);
    v16 = v15;
    if ( v15 )
    {
      v17 = strrchr("admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp", 92);
      if ( v17 )
        v18 = v17 + 1;
      else
        v18 = "admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp";
      v14 = v16
          | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v18) << 52);
      goto LABEL_16;
    }
    *this = this[1];
    return 0x8000000000LL;
  }
  v22 = (softgrid::shared::revert_to_self *)operator new(0x10u);
  v3 = softgrid::shared::revert_to_self::revert_to_self(v22);
  v22 = v3;
  v4 = (HKEY)operator new(0x18u);
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count<softgrid::shared::revert_to_self>::`vftable';
  *((_QWORD *)v4 + 2) = v3;
  v22 = 0;
  std::_Temporary_owner<softgrid::shared::revert_to_self>::~_Temporary_owner<softgrid::shared::revert_to_self>((void **)&v22);
  this[4] = (HKEY)v3;
  v5 = (volatile signed __int32 *)this[5];
  this[5] = v4;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  if ( *(_BYTE *)this[4] )
    return 0x8000000000LL;
  LastError = GetLastError();
  v7 = LastError;
  if ( !LastError )
  {
    v8 = strrchr("admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = 0x152500000545LL;
LABEL_29:
    v14 = FileId << 52;
    return v11 | v14;
  }
  v12 = strrchr("admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp", 92);
  if ( v12 )
    v13 = v12 + 1;
  else
    v13 = "admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp";
  v14 = v7 | (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v13) << 52);
LABEL_16:
  v11 = 0x162500000000LL;
  return v11 | v14;
}

```

## disassembly

```asm
0x14003e9d8  mov     [rsp+arg_8], rbx
0x14003e9dd  mov     [rsp+arg_10], rsi
0x14003e9e2  push    rdi
0x14003e9e3  sub     rsp, 20h
0x14003e9e7  mov     eax, edx
0x14003e9e9  mov     rsi, rcx
0x14003e9ec  cmp     qword ptr [rcx], 0FFFFFFFF80000002h
0x14003e9f3  jnz     loc_14003EB3C
0x14003e9f9  mov     ecx, 10h; Size
0x14003e9fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003ea03  mov     [rsp+28h+arg_0], rax
0x14003ea08  mov     rcx, rax; this
0x14003ea0b  call    ??0revert_to_self@shared@softgrid@@QEAA@XZ; softgrid::shared::revert_to_self::revert_to_self(void)
0x14003ea10  mov     rdi, rax
0x14003ea13  mov     [rsp+28h+arg_0], rax
0x14003ea18  mov     ecx, 18h; Size
0x14003ea1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003ea22  mov     rbx, rax
0x14003ea25  mov     [rsp+28h+arg_0], rax
0x14003ea2a  xorps   xmm0, xmm0
0x14003ea2d  movups  xmmword ptr [rax], xmm0
0x14003ea30  mov     dword ptr [rax+8], 1
0x14003ea37  mov     dword ptr [rax+0Ch], 1
0x14003ea3e  lea     rax, ??_7?$_Ref_count@Urevert_to_self@shared@softgrid@@@std@@6B@; const std::_Ref_count<softgrid::shared::revert_to_self>::`vftable'
0x14003ea45  mov     [rbx], rax
0x14003ea48  mov     [rbx+10h], rdi
0x14003ea4c  mov     [rsp+28h+arg_0], 0
0x14003ea55  lea     rcx, [rsp+28h+arg_0]
0x14003ea5a  call    ??1?$_Temporary_owner@Urevert_to_self@shared@softgrid@@@std@@QEAA@XZ; std::_Temporary_owner<softgrid::shared::revert_to_self>::~_Temporary_owner<softgrid::shared::revert_to_self>(void)
0x14003ea5f  mov     [rsi+20h], rdi
0x14003ea63  mov     rdi, [rsi+28h]
0x14003ea67  mov     [rsi+28h], rbx
0x14003ea6b  test    rdi, rdi
0x14003ea6e  jz      short loc_14003EAA6
0x14003ea70  or      ebx, 0FFFFFFFFh
0x14003ea73  mov     eax, ebx
0x14003ea75  lock xadd [rdi+8], eax
0x14003ea7a  add     eax, ebx
0x14003ea7c  jnz     short loc_14003EAA6
0x14003ea7e  mov     rax, [rdi]
0x14003ea81  mov     rcx, rdi
0x14003ea84  mov     rax, [rax]
0x14003ea87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ea8c  mov     eax, ebx
0x14003ea8e  lock xadd [rdi+0Ch], eax
0x14003ea93  add     eax, ebx
0x14003ea95  jnz     short loc_14003EAA6
0x14003ea97  mov     rax, [rdi]
0x14003ea9a  mov     rcx, rdi
0x14003ea9d  mov     rax, [rax+8]
0x14003eaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eaa6  mov     rax, [rsi+20h]
0x14003eaaa  cmp     byte ptr [rax], 0
0x14003eaad  jnz     loc_14003EB99
0x14003eab3  call    cs:__imp_GetLastError
0x14003eab9  mov     ebx, eax
0x14003eabb  mov     edx, 5Ch ; '\'; Ch
0x14003eac0  lea     rcx, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003eac7  test    eax, eax
0x14003eac9  jnz     short loc_14003EB00
0x14003eacb  call    cs:__imp_strrchr
0x14003ead1  test    rax, rax
0x14003ead4  jz      short loc_14003EADB
0x14003ead6  inc     rax
0x14003ead9  jmp     short loc_14003EAE2
0x14003eadb  lea     rax, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003eae2  mov     rdx, rax; char *
0x14003eae5  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003eaec  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003eaf1  mov     rcx, 152500000545h
0x14003eafb  jmp     loc_14003EBE1
0x14003eb00  call    cs:__imp_strrchr
0x14003eb06  test    rax, rax
0x14003eb09  jz      short loc_14003EB10
0x14003eb0b  inc     rax
0x14003eb0e  jmp     short loc_14003EB17
0x14003eb10  lea     rax, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003eb17  mov     rdx, rax; char *
0x14003eb1a  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003eb21  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003eb26  shl     rax, 34h
0x14003eb2a  or      rax, rbx
0x14003eb2d  mov     rcx, 162500000000h
0x14003eb37  jmp     loc_14003EBE5
0x14003eb3c  cmp     qword ptr [rcx], 0FFFFFFFF80000001h
0x14003eb43  jnz     short loc_14003EBA5
0x14003eb45  lea     rdx, [rcx+8]; phkResult
0x14003eb49  mov     ecx, eax; samDesired
0x14003eb4b  call    cs:__imp_RegOpenCurrentUser
0x14003eb51  mov     edi, eax
0x14003eb53  test    eax, eax
0x14003eb55  jz      short loc_14003EB92
0x14003eb57  mov     edx, 5Ch ; '\'; Ch
0x14003eb5c  lea     rcx, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003eb63  call    cs:__imp_strrchr
0x14003eb69  test    rax, rax
0x14003eb6c  jz      short loc_14003EB73
0x14003eb6e  inc     rax
0x14003eb71  jmp     short loc_14003EB7A
0x14003eb73  lea     rax, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003eb7a  mov     rdx, rax; char *
0x14003eb7d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003eb84  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003eb89  shl     rax, 34h
0x14003eb8d  or      rax, rdi
0x14003eb90  jmp     short loc_14003EB2D
0x14003eb92  mov     rax, [rsi+8]
0x14003eb96  mov     [rsi], rax
0x14003eb99  mov     rax, 8000000000h
0x14003eba3  jmp     short loc_14003EBE8
0x14003eba5  mov     edx, 5Ch ; '\'; Ch
0x14003ebaa  lea     rcx, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003ebb1  call    cs:__imp_strrchr
0x14003ebb7  test    rax, rax
0x14003ebba  jz      short loc_14003EBC1
0x14003ebbc  inc     rax
0x14003ebbf  jmp     short loc_14003EBC8
0x14003ebc1  lea     rax, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003ebc8  mov     rdx, rax; char *
0x14003ebcb  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003ebd2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003ebd7  mov     rcx, 170500070001h
0x14003ebe1  shl     rax, 34h
0x14003ebe5  or      rax, rcx
0x14003ebe8  mov     rbx, [rsp+28h+arg_8]
0x14003ebed  mov     rsi, [rsp+28h+arg_10]
0x14003ebf2  add     rsp, 20h
0x14003ebf6  pop     rdi
0x14003ebf7  retn
```
