# _SetSoundEnabled(ushort const *,bool,bool)

- ea: `0x1800f369c`
- end: `0x1800f387c`
- name: `?_SetSoundEnabled@@YAJPEBG_N1@Z`
- size: `480`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f2960`
- `0x1800f2a30`

## callees

- `0x180010a90`
- `0x1800165ac`
- `0x180016664`
- `0x180087e80`
- `0x18009d564`
- `0x1800c87dc`
- `0x1800c89e8`
- `0x1800f369c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f3868`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f3868`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f37e1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800f37e1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800f3819`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800f3819`

## string_xrefs

- `0x1800f3703`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f377e`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`
- `0x1800f37f7`: `avcore\audiocore\client\audiopolicymanager\lib\audiopolicyconfigmanager.cpp`

## pseudocode

```c
__int64 __fastcall _SetSoundEnabled(const unsigned __int16 *a1, char a2, unsigned __int8 a3)
{
  int v3; // esi
  int v5; // r14d
  int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *v8; // rdi
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  bool v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v3 = a3;
  dwOptions = (int)a1;
  v5 = (int)a1;
  v15 = 1;
  v6 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\EventSounds\\Sounds");
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = L"DisabledForDoNotDisturb";
    if ( !a2 )
      v8 = L"Disabled";
    ReadBoolFromRegistry(SubKey, v8, 1, &v15);
    hKey = 0;
    v9 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSDATA\\SOFTWARE\\Microsoft\\EventSounds\\Sounds");
    v7 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x582,
        (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
        (const char *)(unsigned int)v9,
        v5);
LABEL_13:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v7;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v10 )
    {
      v11 = 1413;
LABEL_9:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
             (const char *)v10,
             dwOptionsa);
      goto LABEL_13;
    }
    if ( v15 == (_BYTE)v3 )
    {
      RegDeleteKeyW(hKey, v8);
    }
    else
    {
      *(_DWORD *)Data = v3;
      v10 = RegSetValueExW(hKey, v8, 0, 4u, Data, 4u);
      if ( v10 )
      {
        v11 = 1435;
        goto LABEL_9;
      }
    }
    v7 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x57D,
    (unsigned int)"avcore\\audiocore\\client\\audiopolicymanager\\lib\\audiopolicyconfigmanager.cpp",
    (const char *)(unsigned int)v6,
    dwOptions);
  return v7;
}

```

## disassembly

```asm
0x1800f369c  push    rbp
0x1800f369e  push    rbx
0x1800f369f  push    rsi
0x1800f36a0  push    rdi
0x1800f36a1  push    r14
0x1800f36a3  push    r15
0x1800f36a5  lea     rbp, [rsp-198h]
0x1800f36ad  sub     rsp, 298h
0x1800f36b4  mov     rax, cs:__security_cookie
0x1800f36bb  xor     rax, rsp
0x1800f36be  mov     [rbp+1C0h+var_40], rax
0x1800f36c5  movzx   esi, r8b
0x1800f36c9  lea     r9, aSoftwareMicros; "Software\\Microsoft\\EventSounds\\Sound"...
0x1800f36d0  mov     r15b, dl
0x1800f36d3  mov     qword ptr [rsp+2C0h+dwOptions], rcx; int
0x1800f36d8  mov     r14, rcx
0x1800f36db  mov     [rsp+2C0h+var_270], 1
0x1800f36e0  lea     r8, aSS; "%s\\%s"
0x1800f36e7  mov     edx, 104h; unsigned __int64
0x1800f36ec  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1800f36f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f36f6  mov     ebx, eax
0x1800f36f8  test    eax, eax
0x1800f36fa  jns     short loc_1800F371C
0x1800f36fc  mov     rcx, [rbp+1C8h]; this
0x1800f3703  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f370a  mov     r9d, eax; char *
0x1800f370d  mov     edx, 57Dh; void *
0x1800f3712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3717  jmp     loc_1800F382B
0x1800f371c  lea     rax, aDisabled_0; "Disabled"
0x1800f3723  test    r15b, r15b
0x1800f3726  lea     rdi, aDisabledfordon; "DisabledForDoNotDisturb"
0x1800f372d  mov     r8b, 1; bool
0x1800f3730  cmovz   rdi, rax
0x1800f3734  lea     r9, [rsp+2C0h+var_270]; bool *
0x1800f3739  mov     rdx, rdi; lpValue
0x1800f373c  lea     rcx, [rsp+2C0h+SubKey]; lpSubKey
0x1800f3741  call    ?ReadBoolFromRegistry@@YAXPEBG0_NPEA_N@Z; ReadBoolFromRegistry(ushort const *,ushort const *,bool,bool *)
0x1800f3746  lea     r9, aOsdataSoftware; "OSDATA\\SOFTWARE\\Microsoft\\EventSound"...
0x1800f374d  mov     [rsp+2C0h+hKey], 0
0x1800f3756  lea     r8, aSS; "%s\\%s"
0x1800f375d  mov     qword ptr [rsp+2C0h+dwOptions], r14; int
0x1800f3762  mov     edx, 104h; unsigned __int64
0x1800f3767  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1800f376c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f3771  mov     ebx, eax
0x1800f3773  test    eax, eax
0x1800f3775  jns     short loc_1800F3797
0x1800f3777  mov     rcx, [rbp+1C8h]; this
0x1800f377e  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f3785  mov     r9d, eax; char *
0x1800f3788  mov     edx, 582h; void *
0x1800f378d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f3792  jmp     loc_1800F3821
0x1800f3797  xor     edx, edx
0x1800f3799  lea     rcx, [rsp+2C0h+hKey]
0x1800f379e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f37a3  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x1800f37ac  lea     rax, [rsp+2C0h+hKey]
0x1800f37b1  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800f37b6  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1800f37bb  mov     [rsp+2C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800f37c4  xor     r9d, r9d; lpClass
0x1800f37c7  mov     [rsp+2C0h+samDesired], 2; samDesired
0x1800f37cf  xor     r8d, r8d; Reserved
0x1800f37d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f37d9  mov     [rsp+2C0h+dwOptions], 0; unsigned int
0x1800f37e1  call    cs:__imp_RegCreateKeyExW
0x1800f37e7  test    eax, eax
0x1800f37e9  jz      short loc_1800F380A
0x1800f37eb  mov     edx, 585h; void *
0x1800f37f0  mov     rcx, [rbp+1C8h]; this
0x1800f37f7  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\client\\audiopolicym"...
0x1800f37fe  mov     r9d, eax; char *
0x1800f3801  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f3806  mov     ebx, eax
0x1800f3808  jmp     short loc_1800F3821
0x1800f380a  mov     rdx, rdi; lpValueName
0x1800f380d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800f3812  cmp     [rsp+2C0h+var_270], sil
0x1800f3817  jnz     short loc_1800F384C
0x1800f3819  call    cs:__imp_RegDeleteKeyW
0x1800f381f  xor     ebx, ebx
0x1800f3821  lea     rcx, [rsp+2C0h+hKey]
0x1800f3826  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f382b  mov     eax, ebx
0x1800f382d  mov     rcx, [rbp+1C0h+var_40]
0x1800f3834  xor     rcx, rsp; StackCookie
0x1800f3837  call    __security_check_cookie
0x1800f383c  add     rsp, 298h
0x1800f3843  pop     r15
0x1800f3845  pop     r14
0x1800f3847  pop     rdi
0x1800f3848  pop     rsi
0x1800f3849  pop     rbx
0x1800f384a  pop     rbp
0x1800f384b  retn
0x1800f384c  mov     r9d, 4; dwType
0x1800f3852  mov     dword ptr [rsp+2C0h+Data], esi
0x1800f3856  lea     rax, [rsp+2C0h+Data]
0x1800f385b  mov     [rsp+2C0h+samDesired], r9d; cbData
0x1800f3860  xor     r8d, r8d; Reserved
0x1800f3863  mov     qword ptr [rsp+2C0h+dwOptions], rax; lpData
0x1800f3868  call    cs:__imp_RegSetValueExW
0x1800f386e  test    eax, eax
0x1800f3870  jz      short loc_1800F381F
0x1800f3872  mov     edx, 59Bh
0x1800f3877  jmp     loc_1800F37F0
```
