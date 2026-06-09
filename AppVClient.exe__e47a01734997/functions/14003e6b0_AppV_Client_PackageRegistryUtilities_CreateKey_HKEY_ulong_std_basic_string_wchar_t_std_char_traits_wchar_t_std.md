# AppV::Client::PackageRegistryUtilities::CreateKey(HKEY__ *,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ATL::CRegKey &)

- ea: `0x14003e6b0`
- end: `0x14003e809`
- name: `?CreateKey@PackageRegistryUtilities@Client@AppV@@SA_KPEAUHKEY__@@KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVCRegKey@ATL@@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003e264`

## callees

- `0x140018bec`
- `0x14003e5d0`
- `0x14003e6b0`
- `0x14003e9d8`
- `0x14003ec74`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003e785`
- `ADVAPI32!RegCloseKey` at `0x14003e785`
- `ADVAPI32!RegCreateKeyExW` at `0x14003e76f`
- `ADVAPI32!RegCreateKeyExW` at `0x14003e76f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003e7ad`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003e7ad`

## string_xrefs

- `0x14003e7a6`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`
- `0x14003e7bd`: `admin\appman\appv\shared\client\packageregistry\packageregistryutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall AppV::Client::PackageRegistryUtilities::CreateKey(
        HKEY a1,
        DWORD a2,
        const WCHAR *a3,
        HKEY *a4)
{
  int wow64_access_flag; // eax
  unsigned __int64 v7; // rdi
  REGSAM samDesired; // eax
  unsigned int v9; // ebx
  char *v10; // rax
  const char *v11; // rax
  _OWORD hKey[4]; // [rsp+50h] [rbp-48h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+10h] BYREF

  dwDisposition = a2;
  phkResult = a1;
  hKey[0] = _mm_load_si128((const __m128i *)&_xmm);
  memset(&hKey[1], 0, 32);
  wow64_access_flag = AppV::shared::system::get_wow64_access_flag();
  v7 = AppV::Client::PackageRegistryUtilities::PackageRegistryHive::Open((HKEY *)hKey, wow64_access_flag | 0x2001Du);
  if ( (v7 & 0x8000000000LL) != 0 )
  {
    samDesired = AppV::shared::system::get_wow64_access_flag() | 1;
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    dwDisposition = 0;
    phkResult = 0;
    v9 = RegCreateKeyExW(*(HKEY *)&hKey[0], a3, 0, 0, 0, samDesired, 0, &phkResult, &dwDisposition);
    if ( v9 )
      goto LABEL_9;
    v9 = 0;
    if ( *a4 )
      v9 = RegCloseKey(*a4);
    *a4 = phkResult;
    if ( v9 )
    {
LABEL_9:
      v10 = strrchr("admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp", 92);
      if ( v10 )
        v11 = v10 + 1;
      else
        v11 = "admin\\appman\\appv\\shared\\client\\packageregistry\\packageregistryutilities.cpp";
      v7 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v11) << 52)
         | v9
         | 0xA2500000000LL;
    }
    else
    {
      v7 = 0x8000000000LL;
    }
  }
  AppV::Client::PackageRegistryUtilities::PackageRegistryHive::~PackageRegistryHive((AppV::Client::PackageRegistryUtilities::PackageRegistryHive *)hKey);
  return v7;
}

```

## disassembly

```asm
0x14003e6b0  mov     rax, rsp
0x14003e6b3  mov     [rax+18h], rbx
0x14003e6b7  mov     [rax+10h], edx
0x14003e6ba  mov     [rax+8], rcx
0x14003e6be  push    rbp
0x14003e6bf  push    rsi
0x14003e6c0  push    rdi
0x14003e6c1  sub     rsp, 80h
0x14003e6c8  mov     rsi, r9
0x14003e6cb  mov     rbx, r8
0x14003e6ce  movdqa  xmm0, cs:__xmm@0000000000000000ffffffff80000002
0x14003e6d6  movdqu  xmmword ptr [rax-48h], xmm0
0x14003e6db  xorps   xmm0, xmm0
0x14003e6de  movdqu  xmmword ptr [rax-38h], xmm0
0x14003e6e3  xorps   xmm1, xmm1
0x14003e6e6  movdqu  xmmword ptr [rax-28h], xmm1
0x14003e6eb  call    AppV__shared__system__get_wow64_access_flag
0x14003e6f0  or      eax, 2001Dh
0x14003e6f5  mov     edx, eax; unsigned int
0x14003e6f7  lea     rcx, [rsp+98h+hKey]; this
0x14003e6fc  call    ?Open@PackageRegistryHive@PackageRegistryUtilities@Client@AppV@@QEAA_KK@Z; AppV::Client::PackageRegistryUtilities::PackageRegistryHive::Open(ulong)
0x14003e701  mov     rdi, rax
0x14003e704  mov     rbp, 8000000000h
0x14003e70e  test    rbp, rax
0x14003e711  jz      loc_14003E7E9
0x14003e717  call    AppV__shared__system__get_wow64_access_flag
0x14003e71c  or      eax, 1
0x14003e71f  cmp     qword ptr [rbx+18h], 7
0x14003e724  jbe     short loc_14003E729
0x14003e726  mov     rbx, [rbx]
0x14003e729  xor     edi, edi
0x14003e72b  mov     [rsp+98h+dwDisposition], edi
0x14003e732  mov     [rsp+98h+arg_0], rdi
0x14003e73a  lea     rcx, [rsp+98h+dwDisposition]
0x14003e742  mov     [rsp+98h+lpdwDisposition], rcx; lpdwDisposition
0x14003e747  lea     rcx, [rsp+98h+arg_0]
0x14003e74f  mov     [rsp+98h+phkResult], rcx; phkResult
0x14003e754  mov     [rsp+98h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14003e759  mov     [rsp+98h+samDesired], eax; samDesired
0x14003e75d  mov     [rsp+98h+dwOptions], edi; dwOptions
0x14003e761  xor     r9d, r9d; lpClass
0x14003e764  xor     r8d, r8d; Reserved
0x14003e767  mov     rdx, rbx; lpSubKey
0x14003e76a  mov     rcx, qword ptr [rsp+98h+hKey]; hKey
0x14003e76f  call    cs:__imp_RegCreateKeyExW
0x14003e775  mov     ebx, eax
0x14003e777  test    eax, eax
0x14003e779  jnz     short loc_14003E7A1
0x14003e77b  mov     ebx, edi
0x14003e77d  mov     rcx, [rsi]; hKey
0x14003e780  test    rcx, rcx
0x14003e783  jz      short loc_14003E78D
0x14003e785  call    cs:__imp_RegCloseKey
0x14003e78b  mov     ebx, eax
0x14003e78d  mov     rax, [rsp+98h+arg_0]
0x14003e795  mov     [rsi], rax
0x14003e798  test    ebx, ebx
0x14003e79a  jnz     short loc_14003E7A1
0x14003e79c  mov     rdi, rbp
0x14003e79f  jmp     short loc_14003E7E9
0x14003e7a1  mov     edx, 5Ch ; '\'; Ch
0x14003e7a6  lea     rcx, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003e7ad  call    cs:__imp_strrchr
0x14003e7b3  test    rax, rax
0x14003e7b6  jz      short loc_14003E7BD
0x14003e7b8  inc     rax
0x14003e7bb  jmp     short loc_14003E7C4
0x14003e7bd  lea     rax, aAdminAppmanApp_22; "admin\\appman\\appv\\shared\\client\\pa"...
0x14003e7c4  mov     rdx, rax; char *
0x14003e7c7  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003e7ce  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003e7d3  shl     rax, 34h
0x14003e7d7  mov     edi, ebx
0x14003e7d9  or      rdi, rax
0x14003e7dc  mov     rcx, 0A2500000000h
0x14003e7e6  or      rdi, rcx
0x14003e7e9  lea     rcx, [rsp+98h+hKey]; this
0x14003e7ee  call    ??1PackageRegistryHive@PackageRegistryUtilities@Client@AppV@@QEAA@XZ; AppV::Client::PackageRegistryUtilities::PackageRegistryHive::~PackageRegistryHive(void)
0x14003e7f3  mov     rax, rdi
0x14003e7f6  mov     rbx, [rsp+98h+arg_10]
0x14003e7fe  add     rsp, 80h
0x14003e805  pop     rdi
0x14003e806  pop     rsi
0x14003e807  pop     rbp
0x14003e808  retn
```
