# CreateCommonRecognizer(_GUID *,HRECOGNIZER__ * *,int)

- ea: `0x18007aabc`
- end: `0x18007ad75`
- name: `?CreateCommonRecognizer@@YAJPEAU_GUID@@PEAPEAUHRECOGNIZER__@@H@Z`
- size: `697`
- prototype: `__int64 __fastcall(GUID *rguid, HRECOGNIZER *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006aab0`
- `0x18007af18`
- `0x18007e92c`

## callees

- `0x180044ac6`
- `0x180060fe4`
- `0x180076d74`
- `0x180079b1c`
- `0x18007aabc`
- `0x180089488`
- `0x180104ece`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007acde`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18007acde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aba6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007aba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ac16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ac30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ac16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ac30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007abf4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007abf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ac3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ac70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ac3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007ac70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ad3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007acfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ad3b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007ab64`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007ab64`

## string_xrefs

- `0x18007abdc`: `Recognizer dll`
- `0x18007ad21`: `CreateCommonRecognizer`
- `0x18007ad28`: `%s - RecoAPIs::CreateRecognizer failed.\n`

## pseudocode

```c
__int64 __fastcall CreateCommonRecognizer(GUID *rguid, HRECOGNIZER *a2, int a3)
{
  const unsigned __int16 *v6; // r8
  LSTATUS v7; // eax
  HKEY v8; // rcx
  LSTATUS ValueW; // eax
  bool v10; // sf
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  __int64 v13; // rax
  SIZE_T v14; // r14
  struct _RTL_CRITICAL_SECTION_DEBUG *v15; // rax
  int v16; // edi
  GUID v17; // xmm0
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-B4h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 Src[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  hkey = 0;
  pdwType = 0;
  pcbData = 0;
  if ( !rguid || !a2 )
    return 2147500035LL;
  memset_0(SubKey, 0, sizeof(SubKey));
  v6 = L"Software\\Microsoft\\TPG\\System Recognizers\\";
  if ( !a3 )
    v6 = L"Software\\Microsoft\\TPG\\Recognizers\\";
  if ( (int)StringCchCopyW(SubKey, 0x100u, v6) < 0 )
    return 2147500037LL;
  StringFromGUID2(rguid, sz, 39);
  if ( (int)StringCchCatW(SubKey, 0x100u, sz) < 0 )
    return 2147500037LL;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hkey);
  v8 = hkey;
  if ( !v7 )
  {
    pcbData = 518;
    pdwType = 7;
    Src[0] = 0;
    ValueW = RegGetValueW(hkey, 0, L"Recognizer dll", 0x22u, &pdwType, Src, &pcbData);
    v10 = ValueW < 0;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v10 = 1;
      if ( v10 )
      {
        v8 = hkey;
        goto LABEL_13;
      }
    }
    if ( hkey )
      RegCloseKey(hkey);
    v12 = (struct _RTL_CRITICAL_SECTION *)CoTaskMemAlloc(0x170u);
    if ( !v12 )
      return 2147942414LL;
    v13 = -1;
    do
      ++v13;
    while ( Src[v13] );
    v14 = 2 * v13 + 2;
    v15 = (struct _RTL_CRITICAL_SECTION_DEBUG *)CoTaskMemAlloc(v14);
    v12[9].DebugInfo = v15;
    if ( v15 )
    {
      memcpy_0(v15, Src, v14);
      if ( RecoAPIs::LoadAPI((RecoAPIs *)&v12->LockCount, Src) < 0 )
      {
        CoTaskMemFree(v12[9].DebugInfo);
        v16 = -2147467259;
        goto LABEL_28;
      }
      v17 = *rguid;
      v12[7].SpinCount = 0;
      v12->DebugInfo = 0;
      *(GUID *)&v12[7].LockCount = v17;
      v12[7].LockSemaphore = 0;
      if ( InitializeCriticalSectionAndSpinCount(v12 + 8, 0x8001FA0u) )
      {
        v16 = (*(__int64 (__fastcall **)(GUID *, struct _RTL_CRITICAL_SECTION *))&v12->LockCount)(rguid, v12);
        if ( v16 >= 0 )
        {
          *a2 = (HRECOGNIZER)v12;
          return (unsigned int)v16;
        }
        WispTraceInformation("%s - RecoAPIs::CreateRecognizer failed.\n", "CreateCommonRecognizer");
        CoTaskMemFree(v12[9].DebugInfo);
LABEL_28:
        CoTaskMemFree(v12);
        return (unsigned int)v16;
      }
      CoTaskMemFree(v12[9].DebugInfo);
    }
    v16 = -2147024882;
    goto LABEL_28;
  }
LABEL_13:
  if ( v8 )
    RegCloseKey(v8);
  return 2147746357LL;
}

```

## disassembly

```asm
0x18007aabc  mov     [rsp-8+arg_10], rbx
0x18007aac1  push    rbp
0x18007aac2  push    rsi
0x18007aac3  push    rdi
0x18007aac4  push    r14
0x18007aac6  push    r15
0x18007aac8  lea     rbp, [rsp-3C0h]
0x18007aad0  sub     rsp, 4C0h
0x18007aad7  mov     rax, cs:__security_cookie
0x18007aade  xor     rax, rsp
0x18007aae1  mov     [rbp+3E0h+var_30], rax
0x18007aae8  xor     r15d, r15d
0x18007aaeb  mov     ebx, r8d
0x18007aaee  mov     [rsp+4E0h+hkey], r15
0x18007aaf3  mov     rsi, rdx
0x18007aaf6  mov     [rsp+4E0h+pdwType], r15d
0x18007aafb  mov     rdi, rcx
0x18007aafe  mov     [rsp+4E0h+var_498], r15d
0x18007ab03  test    rcx, rcx
0x18007ab06  jz      loc_18007AD4A
0x18007ab0c  test    rdx, rdx
0x18007ab0f  jz      loc_18007AD4A
0x18007ab15  xor     edx, edx; Val
0x18007ab17  lea     rcx, [rbp+3E0h+SubKey]; void *
0x18007ab1e  mov     r8d, 200h; Size
0x18007ab24  call    memset_0
0x18007ab29  test    ebx, ebx
0x18007ab2b  lea     rax, aSoftwareMicros_4; "Software\\Microsoft\\TPG\\Recognizers\\"
0x18007ab32  mov     ebx, 100h
0x18007ab37  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\TPG\\System Recogn"...
0x18007ab3e  cmovz   r8, rax; unsigned __int16 *
0x18007ab42  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x18007ab49  mov     edx, ebx; unsigned __int64
0x18007ab4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007ab50  test    eax, eax
0x18007ab52  js      loc_18007AD43
0x18007ab58  lea     r8d, [r15+27h]; cchMax
0x18007ab5c  mov     rcx, rdi; rguid
0x18007ab5f  lea     rdx, [rsp+4E0h+sz]; lpsz
0x18007ab64  call    cs:__imp_StringFromGUID2
0x18007ab6a  lea     r8, [rsp+4E0h+sz]; unsigned __int16 *
0x18007ab6f  mov     edx, ebx; unsigned __int64
0x18007ab71  lea     rcx, [rbp+3E0h+SubKey]; unsigned __int16 *
0x18007ab78  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007ab7d  test    eax, eax
0x18007ab7f  js      loc_18007AD43
0x18007ab85  lea     rax, [rsp+4E0h+hkey]
0x18007ab8a  mov     r9d, 20019h; samDesired
0x18007ab90  xor     r8d, r8d; ulOptions
0x18007ab93  mov     [rsp+4E0h+phkResult], rax; phkResult
0x18007ab98  lea     rdx, [rbp+3E0h+SubKey]; lpSubKey
0x18007ab9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007aba6  call    cs:__imp_RegOpenKeyExW
0x18007abac  mov     rcx, [rsp+4E0h+hkey]; hkey
0x18007abb1  test    eax, eax
0x18007abb3  jnz     short loc_18007AC11
0x18007abb5  lea     rax, [rsp+4E0h+var_498]
0x18007abba  mov     [rsp+4E0h+var_498], 206h
0x18007abc2  mov     [rsp+4E0h+pcbData], rax; pcbData
0x18007abc7  lea     r9d, [r15+22h]; dwFlags
0x18007abcb  lea     rax, [rbp+3E0h+Src]
0x18007abcf  mov     [rsp+4E0h+pdwType], 7
0x18007abd7  mov     [rsp+4E0h+pvData], rax; pvData
0x18007abdc  lea     r8, Value; "Recognizer dll"
0x18007abe3  lea     rax, [rsp+4E0h+pdwType]
0x18007abe8  mov     [rbp+3E0h+Src], r15w
0x18007abed  xor     edx, edx; lpSubKey
0x18007abef  mov     [rsp+4E0h+phkResult], rax; pdwType
0x18007abf4  call    cs:__imp_RegGetValueW
0x18007abfa  test    eax, eax
0x18007abfc  jz      short loc_18007AC26
0x18007abfe  jle     short loc_18007AC0A
0x18007ac00  movzx   eax, ax
0x18007ac03  or      eax, 80070000h
0x18007ac08  test    eax, eax
0x18007ac0a  jns     short loc_18007AC26
0x18007ac0c  mov     rcx, [rsp+4E0h+hkey]; hKey
0x18007ac11  test    rcx, rcx
0x18007ac14  jz      short loc_18007AC1C
0x18007ac16  call    cs:__imp_RegCloseKey
0x18007ac1c  mov     eax, 80040235h
0x18007ac21  jmp     loc_18007AD4F
0x18007ac26  mov     rcx, [rsp+4E0h+hkey]; hKey
0x18007ac2b  test    rcx, rcx
0x18007ac2e  jz      short loc_18007AC36
0x18007ac30  call    cs:__imp_RegCloseKey
0x18007ac36  mov     ecx, 170h; cb
0x18007ac3b  call    cs:__imp_CoTaskMemAlloc
0x18007ac41  mov     rbx, rax
0x18007ac44  test    rax, rax
0x18007ac47  jnz     short loc_18007AC53
0x18007ac49  mov     eax, 8007000Eh
0x18007ac4e  jmp     loc_18007AD4F
0x18007ac53  lea     rcx, [rbp+3E0h+Src]
0x18007ac57  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007ac5b  inc     rax
0x18007ac5e  cmp     [rcx+rax*2], r15w
0x18007ac63  jnz     short loc_18007AC5B
0x18007ac65  lea     r14, ds:2[rax*2]
0x18007ac6d  mov     rcx, r14; cb
0x18007ac70  call    cs:__imp_CoTaskMemAlloc
0x18007ac76  mov     [rbx+168h], rax
0x18007ac7d  test    rax, rax
0x18007ac80  jz      short loc_18007ACF5
0x18007ac82  mov     r8, r14; Size
0x18007ac85  lea     rdx, [rbp+3E0h+Src]; Src
0x18007ac89  mov     rcx, rax; void *
0x18007ac8c  call    memcpy_0
0x18007ac91  lea     rdx, [rbp+3E0h+Src]; unsigned __int16 *
0x18007ac95  lea     rcx, [rbx+8]; this
0x18007ac99  call    ?LoadAPI@RecoAPIs@@QEAAJPEBG@Z; RecoAPIs::LoadAPI(ushort const *)
0x18007ac9e  test    eax, eax
0x18007aca0  jns     short loc_18007ACB6
0x18007aca2  mov     rcx, [rbx+168h]; pv
0x18007aca9  call    cs:__imp_CoTaskMemFree
0x18007acaf  mov     edi, 80004005h
0x18007acb4  jmp     short loc_18007ACFA
0x18007acb6  movups  xmm0, xmmword ptr [rdi]
0x18007acb9  lea     rcx, [rbx+140h]; lpCriticalSection
0x18007acc0  mov     [rbx+138h], r15
0x18007acc7  mov     edx, 8001FA0h; dwSpinCount
0x18007accc  mov     [rbx], r15
0x18007accf  movdqu  xmmword ptr [rbx+120h], xmm0
0x18007acd7  mov     [rbx+130h], r15
0x18007acde  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18007ace4  test    eax, eax
0x18007ace6  jnz     short loc_18007AD07
0x18007ace8  mov     rcx, [rbx+168h]; pv
0x18007acef  call    cs:__imp_CoTaskMemFree
0x18007acf5  mov     edi, 8007000Eh
0x18007acfa  mov     rcx, rbx; pv
0x18007acfd  call    cs:__imp_CoTaskMemFree
0x18007ad03  mov     eax, edi
0x18007ad05  jmp     short loc_18007AD4F
0x18007ad07  mov     rax, [rbx+8]
0x18007ad0b  mov     rdx, rbx
0x18007ad0e  mov     rcx, rdi
0x18007ad11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad16  mov     edi, eax
0x18007ad18  test    eax, eax
0x18007ad1a  js      short loc_18007AD21
0x18007ad1c  mov     [rsi], rbx
0x18007ad1f  jmp     short loc_18007AD03
0x18007ad21  lea     rdx, aCreatecommonre; "CreateCommonRecognizer"
0x18007ad28  lea     rcx, aSRecoapisCreat; "%s - RecoAPIs::CreateRecognizer failed."...
0x18007ad2f  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x18007ad34  mov     rcx, [rbx+168h]; pv
0x18007ad3b  call    cs:__imp_CoTaskMemFree
0x18007ad41  jmp     short loc_18007ACFA
0x18007ad43  mov     eax, 80004005h
0x18007ad48  jmp     short loc_18007AD4F
0x18007ad4a  mov     eax, 80004003h
0x18007ad4f  mov     rcx, [rbp+3E0h+var_30]
0x18007ad56  xor     rcx, rsp; StackCookie
0x18007ad59  call    __security_check_cookie
0x18007ad5e  mov     rbx, [rsp+4E0h+arg_10]
0x18007ad66  add     rsp, 4C0h
0x18007ad6d  pop     r15
0x18007ad6f  pop     r14
0x18007ad71  pop     rdi
0x18007ad72  pop     rsi
0x18007ad73  pop     rbp
0x18007ad74  retn
```
