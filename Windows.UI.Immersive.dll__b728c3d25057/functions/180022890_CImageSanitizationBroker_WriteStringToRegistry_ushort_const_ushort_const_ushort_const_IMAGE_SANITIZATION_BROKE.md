# CImageSanitizationBroker::WriteStringToRegistry(ushort const *,ushort const *,ushort const *,IMAGE_SANITIZATION_BROKER_REGISTRY_FLAGS)

- ea: `0x180022890`
- end: `0x180022b3c`
- name: `?WriteStringToRegistry@CImageSanitizationBroker@@UEAAJPEBG00W4IMAGE_SANITIZATION_BROKER_REGISTRY_FLAGS@@@Z`
- size: `684`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum IMAGE_SANITIZATION_BROKER_REGISTRY_FLAGS)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d2b8`
- `0x180013244`
- `0x180022890`
- `0x180023448`
- `0x180028cd0`
- `0x18002d8a4`
- `0x18003aa84`
- `0x180050ba0`
- `0x1800d0f30`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800228fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002291f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002294a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800228fc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002291f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002294a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022af6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002299c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002299c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022a62`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022a62`

## string_xrefs

- `0x180022a80`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall CImageSanitizationBroker::WriteStringToRegistry(
        __int64 a1,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5)
{
  unsigned int v6; // esi
  unsigned __int64 v7; // rdi
  int RegKeyWithSDDL; // ebx
  unsigned __int64 v11; // rbx
  LPWSTR v12; // rdi
  HRESULT v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  void *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  char hKey; // [rsp+40h] [rbp-C0h]
  void *ppInterface; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = 0;
  v7 = -1;
  while ( 1 )
  {
    RegKeyWithSDDL = -2147024809;
    if ( v6 >= 0xB )
      return (unsigned int)RegKeyWithSDDL;
    if ( CompareStringOrdinal(a2, -1, off_18012D780[v6], -1, 0) == 2 )
    {
      if ( CompareStringOrdinal(a2, -1, L"LockScreen\\Creative", -1, 0) == 2 )
      {
        v11 = 0x8000;
      }
      else
      {
        v11 = 1024;
        if ( CompareStringOrdinal(a2, -1, L"LanguageProfile", -1, 0) == 2 )
          v11 = 4096;
      }
      do
        ++v7;
      while ( a4[v7] );
      if ( v7 > v11 )
        return (unsigned int)-2147024809;
      StringSid[0] = 0;
      v12 = 0;
      hKey = 0;
      ppInterface = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppInterface);
      v13 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
      RegKeyWithSDDL = v13;
      if ( v13 != -2147417833 )
      {
        if ( !v13 )
        {
          if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
            goto LABEL_18;
          RegKeyWithSDDL = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
          if ( RegKeyWithSDDL >= 0 )
          {
            hKey = 1;
            goto LABEL_18;
          }
LABEL_19:
          if ( hKey )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
          v16 = ppInterface;
          if ( ppInterface )
          {
            ppInterface = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
          }
          if ( RegKeyWithSDDL >= 0 )
          {
            if ( (a5 & 2) != 0 )
            {
              RegKeyWithSDDL = _WriteSystemDataRegistryStringForUser(v12, a2, a3);
            }
            else
            {
              StringSid[0] = 0;
              if ( ConvertSidToStringSidW(v12, StringSid)
                || (RegKeyWithSDDL = ResultFromKnownLastError(), RegKeyWithSDDL >= 0) )
              {
                RegKeyWithSDDL = StringCchPrintfW(
                                   v23,
                                   0x104u,
                                   L"%s\\%s\\%s\\%s",
                                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                                   StringSid[0],
                                   L"AnyoneRead",
                                   a2);
                if ( RegKeyWithSDDL >= 0 )
                {
                  RegKeyWithSDDL = _CreateRegKeyWithSDDL(v18, v17, v23);
                  if ( RegKeyWithSDDL >= 0 )
                  {
                    RegKeyWithSDDL = SHRegSetString(0, 0, a3, a4);
                    RegCloseKey(0);
                  }
                }
                LocalFree(StringSid[0]);
              }
            }
            CoTaskMemFree(v12);
          }
          return (unsigned int)RegKeyWithSDDL;
        }
        if ( v13 < 0 )
          goto LABEL_19;
      }
LABEL_18:
      v15 = SHGetUserSidFallbackForImpersonation(v14, StringSid);
      v12 = StringSid[0];
      RegKeyWithSDDL = v15;
      goto LABEL_19;
    }
    ++v6;
  }
}

```

## disassembly

```asm
0x180022890  mov     [rsp-8+arg_0], rbx
0x180022895  push    rbp
0x180022896  push    rsi
0x180022897  push    rdi
0x180022898  push    r12
0x18002289a  push    r13
0x18002289c  push    r14
0x18002289e  push    r15
0x1800228a0  lea     rbp, [rsp-180h]
0x1800228a8  sub     rsp, 280h
0x1800228af  mov     rax, cs:__security_cookie
0x1800228b6  xor     rax, rsp
0x1800228b9  mov     [rbp+1B0h+var_40], rax
0x1800228c0  xor     r13d, r13d
0x1800228c3  mov     r15, r9
0x1800228c6  mov     esi, r13d
0x1800228c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800228cd  mov     r12, r8
0x1800228d0  mov     r14, rdx
0x1800228d3  mov     ebx, 80070057h
0x1800228d8  cmp     esi, 0Bh
0x1800228db  jnb     loc_180022B10
0x1800228e1  lea     rax, off_18012D780; "LockScreen"
0x1800228e8  movsxd  r8, esi
0x1800228eb  mov     r9d, edi; cchCount2
0x1800228ee  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x1800228f3  mov     edx, edi; cchCount1
0x1800228f5  mov     rcx, r14; lpString1
0x1800228f8  mov     r8, [rax+r8*8]; lpString2
0x1800228fc  call    cs:__imp_CompareStringOrdinal
0x180022902  cmp     eax, 2
0x180022905  jz      short loc_18002290B
0x180022907  inc     esi
0x180022909  jmp     short loc_1800228D3
0x18002290b  mov     r9d, edi; cchCount2
0x18002290e  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x180022913  lea     r8, aLockscreenCrea; "LockScreen\\Creative"
0x18002291a  mov     edx, edi; cchCount1
0x18002291c  mov     rcx, r14; lpString1
0x18002291f  call    cs:__imp_CompareStringOrdinal
0x180022925  cmp     eax, 2
0x180022928  jnz     short loc_180022931
0x18002292a  mov     ebx, 8000h
0x18002292f  jmp     short loc_18002295B
0x180022931  mov     r9d, edi; cchCount2
0x180022934  mov     [rsp+2B0h+bIgnoreCase], r13d; bIgnoreCase
0x180022939  lea     r8, aLanguageprofil; "LanguageProfile"
0x180022940  mov     edx, edi; cchCount1
0x180022942  mov     rcx, r14; lpString1
0x180022945  mov     ebx, 400h
0x18002294a  call    cs:__imp_CompareStringOrdinal
0x180022950  cmp     eax, 2
0x180022953  mov     ecx, 1000h
0x180022958  cmovz   ebx, ecx
0x18002295b  inc     rdi
0x18002295e  cmp     [r15+rdi*2], r13w
0x180022963  jnz     short loc_18002295B
0x180022965  cmp     rdi, rbx
0x180022968  jbe     short loc_180022974
0x18002296a  mov     ebx, 80070057h
0x18002296f  jmp     loc_180022B10
0x180022974  lea     rcx, [rsp+2B0h+ppInterface]
0x180022979  mov     [rsp+2B0h+StringSid], r13
0x18002297e  mov     rdi, r13
0x180022981  mov     byte ptr [rsp+2B0h+hKey], r13b
0x180022986  mov     [rsp+2B0h+ppInterface], r13
0x18002298b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180022990  lea     rdx, [rsp+2B0h+ppInterface]; ppInterface
0x180022995  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x18002299c  call    cs:__imp_CoGetCallContext
0x1800229a2  mov     ebx, eax
0x1800229a4  cmp     eax, 80010117h
0x1800229a9  jz      short loc_1800229E4
0x1800229ab  test    eax, eax
0x1800229ad  jnz     short loc_1800229E2
0x1800229af  mov     rcx, [rsp+2B0h+ppInterface]
0x1800229b4  mov     rax, [rcx]
0x1800229b7  mov     rax, [rax+30h]
0x1800229bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229c0  test    eax, eax
0x1800229c2  jnz     short loc_1800229E4
0x1800229c4  mov     rcx, [rsp+2B0h+ppInterface]
0x1800229c9  mov     rax, [rcx]
0x1800229cc  mov     rax, [rax+20h]
0x1800229d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229d5  mov     ebx, eax
0x1800229d7  test    eax, eax
0x1800229d9  js      short loc_1800229F5
0x1800229db  mov     byte ptr [rsp+2B0h+hKey], 1
0x1800229e0  jmp     short loc_1800229E4
0x1800229e2  js      short loc_1800229F5
0x1800229e4  lea     rdx, [rsp+2B0h+StringSid]
0x1800229e9  call    SHGetUserSidFallbackForImpersonation
0x1800229ee  mov     rdi, [rsp+2B0h+StringSid]
0x1800229f3  mov     ebx, eax
0x1800229f5  cmp     byte ptr [rsp+2B0h+hKey], r13b
0x1800229fa  jz      short loc_180022A0D
0x1800229fc  mov     rcx, [rsp+2B0h+ppInterface]
0x180022a01  mov     rax, [rcx]
0x180022a04  mov     rax, [rax+28h]
0x180022a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a0d  mov     rcx, [rsp+2B0h+ppInterface]
0x180022a12  test    rcx, rcx
0x180022a15  jz      short loc_180022A28
0x180022a17  mov     [rsp+2B0h+ppInterface], r13
0x180022a1c  mov     rax, [rcx]
0x180022a1f  mov     rax, [rax+10h]
0x180022a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a28  test    ebx, ebx
0x180022a2a  js      loc_180022B10
0x180022a30  test    [rbp+1B0h+arg_20], 2
0x180022a37  mov     rcx, rdi; Sid
0x180022a3a  jz      short loc_180022A58
0x180022a3c  mov     byte ptr [rsp+2B0h+var_288], 1
0x180022a41  mov     r8, r12
0x180022a44  mov     rdx, r14
0x180022a47  mov     qword ptr [rsp+2B0h+bIgnoreCase], r15
0x180022a4c  call    ?_WriteSystemDataRegistryStringForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@1_N@Z; _WriteSystemDataRegistryStringForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ushort const *,bool)
0x180022a51  mov     ebx, eax
0x180022a53  jmp     loc_180022B07
0x180022a58  lea     rdx, [rsp+2B0h+StringSid]; StringSid
0x180022a5d  mov     [rsp+2B0h+StringSid], r13
0x180022a62  call    cs:__imp_ConvertSidToStringSidW
0x180022a68  test    eax, eax
0x180022a6a  jnz     short loc_180022A7B
0x180022a6c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180022a71  mov     ebx, eax
0x180022a73  test    eax, eax
0x180022a75  js      loc_180022B07
0x180022a7b  mov     rcx, [rsp+2B0h+StringSid]
0x180022a80  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180022a87  mov     rax, cs:off_1800E67F8; "AnyoneRead"
0x180022a8e  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180022a95  mov     [rsp+2B0h+var_280], r14
0x180022a9a  mov     edx, 104h; unsigned __int64
0x180022a9f  mov     [rsp+2B0h+var_288], rax
0x180022aa4  mov     qword ptr [rsp+2B0h+bIgnoreCase], rcx
0x180022aa9  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180022aae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022ab3  mov     ebx, eax
0x180022ab5  test    eax, eax
0x180022ab7  js      short loc_180022AFC
0x180022ab9  lea     rax, [rsp+2B0h+hKey]
0x180022abe  mov     [rsp+2B0h+hKey], r13
0x180022ac3  mov     [rsp+2B0h+var_288], rax
0x180022ac8  lea     r8, [rsp+2B0h+var_250]
0x180022acd  mov     byte ptr [rsp+2B0h+bIgnoreCase], r13b
0x180022ad2  call    ?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z; _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)
0x180022ad7  mov     ebx, eax
0x180022ad9  test    eax, eax
0x180022adb  js      short loc_180022AFC
0x180022add  mov     rcx, [rsp+2B0h+hKey]; HKEY
0x180022ae2  mov     r9, r15; unsigned __int16 *
0x180022ae5  mov     r8, r12; unsigned __int16 *
0x180022ae8  xor     edx, edx; unsigned __int16 *
0x180022aea  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180022aef  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180022af4  mov     ebx, eax
0x180022af6  call    cs:__imp_RegCloseKey
0x180022afc  mov     rcx, [rsp+2B0h+StringSid]; hMem
0x180022b01  call    cs:__imp_LocalFree
0x180022b07  mov     rcx, rdi; pv
0x180022b0a  call    cs:__imp_CoTaskMemFree
0x180022b10  mov     eax, ebx
0x180022b12  mov     rcx, [rbp+1B0h+var_40]
0x180022b19  xor     rcx, rsp; StackCookie
0x180022b1c  call    __security_check_cookie
0x180022b21  mov     rbx, [rsp+2B0h+arg_0]
0x180022b29  add     rsp, 280h
0x180022b30  pop     r15
0x180022b32  pop     r14
0x180022b34  pop     r13
0x180022b36  pop     r12
0x180022b38  pop     rdi
0x180022b39  pop     rsi
0x180022b3a  pop     rbp
0x180022b3b  retn
```
