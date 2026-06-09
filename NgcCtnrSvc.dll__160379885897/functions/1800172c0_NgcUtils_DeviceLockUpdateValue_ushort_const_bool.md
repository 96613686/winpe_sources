# NgcUtils::DeviceLockUpdateValue(ushort const *,bool)

- ea: `0x1800172c0`
- end: `0x180017562`
- name: `?DeviceLockUpdateValue@NgcUtils@@YAJPEBG_N@Z`
- size: `674`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017280`

## callees

- `0x1800172c0`
- `0x180017570`
- `0x180019c94`
- `0x18001a77c`
- `0x180023278`
- `0x1800232a0`
- `0x180029314`
- `0x18005b308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001734c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001734c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001750d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800173c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001750d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18001749d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18001749d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017452`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017452`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017412`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017412`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800172fe`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017399`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800172fe`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017399`

## string_xrefs

- `0x18001746b`: `onecore\ds\security\ngc\utils\common\lib\devicelockutils.cpp`
- `0x1800174b1`: `onecore\ds\security\ngc\utils\common\lib\devicelockutils.cpp`
- `0x18001753e`: `onecore\ds\security\ngc\utils\common\lib\devicelockutils.cpp`
- `0x18001732c`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x1800173ad`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`
- `0x180017521`: `onecore\ds\security\ngc\utils\common\lib\registryutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DeviceLockUpdateValue(NgcUtils *this, const unsigned __int16 *a2)
{
  WCHAR *v2; // rbx
  int PersistedRegistryLocationW; // eax
  signed int v4; // esi
  __int64 v5; // rsi
  _BYTE *v6; // rax
  void *v7; // rdi
  _BYTE *i; // rcx
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v14; // eax
  signed int LastError; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  void **v20; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  NgcUtils *Data; // [rsp+60h] [rbp+20h] BYREF
  SIZE_T uBytes; // [rsp+68h] [rbp+28h] BYREF
  void *v25; // [rsp+70h] [rbp+30h] BYREF

  Data = this;
  v2 = 0;
  v25 = 0;
  LODWORD(uBytes) = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"NgcLogonUi",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\NgcPin",
                                 0,
                                 0);
  v4 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW != 234 )
  {
    if ( PersistedRegistryLocationW > 0 )
      v4 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_14;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)(unsigned int)v4,
      (int)&uBytes);
LABEL_11:
    if ( v4 >= 0 )
      goto LABEL_14;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\devicelockutils.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    return (unsigned int)v4;
  }
  v5 = (unsigned int)uBytes;
  v6 = LocalAlloc(0, (unsigned int)uBytes);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
      (const char *)0x8007000ELL,
      (int)&uBytes);
    goto LABEL_31;
  }
  for ( i = &v6[v5]; v6 != i; ++v6 )
    *v6 = 0;
  v9 = GetPersistedRegistryLocationW(
         L"NgcLogonUi",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\NgcPin",
         v7,
         (unsigned int)uBytes);
  if ( v9 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xC0,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\registryutils.cpp",
           (const char *)v9,
           (unsigned int)&uBytes);
    LocalFree(v7);
    goto LABEL_11;
  }
  v2 = (WCHAR *)v7;
  v25 = v7;
LABEL_14:
  hKey = 0;
  v20 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20006u, &hKey);
  if ( v10 )
  {
    v11 = 62;
LABEL_18:
    v20 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\devicelockutils.cpp",
            (const char *)v10,
            phkResulta);
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
    return v12;
  }
  LODWORD(Data) = 0;
  v10 = RegSetValueExW(hKey, L"DeviceLockEnforcementPending", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v10 )
  {
    v11 = 71;
    goto LABEL_18;
  }
  v14 = RegFlushKey(hKey);
  if ( v14 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\devicelockutils.cpp",
      (const char *)v14,
      phkResulta);
  v20 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  if ( hKey )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v20) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v16, v17);
      __debugbreak();
    }
    hKey = 0;
  }
  if ( v2 )
    LocalFree(v2);
  return 0;
}

```

## disassembly

```asm
0x1800172c0  mov     [rsp-18h+arg_18], rbx
0x1800172c5  mov     byte ptr [rsp-18h+uBytes], dl
0x1800172c9  mov     [rsp-18h+Data], rcx
0x1800172ce  push    rbp
0x1800172cf  push    rsi
0x1800172d0  push    rdi
0x1800172d1  mov     rbp, rsp
0x1800172d4  sub     rsp, 40h
0x1800172d8  xor     ebx, ebx
0x1800172da  lea     rax, [rbp+uBytes]
0x1800172de  xor     r9d, r9d
0x1800172e1  mov     [rbp+arg_10], rbx
0x1800172e5  xor     r8d, r8d
0x1800172e8  mov     dword ptr [rbp+uBytes], ebx
0x1800172eb  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800172f2  mov     [rsp+40h+phkResult], rax; int
0x1800172f7  lea     rcx, aNgclogonui; "NgcLogonUi"
0x1800172fe  call    cs:__imp_GetPersistedRegistryLocationW
0x180017305  nop     dword ptr [rax+rax+00h]
0x18001730a  mov     esi, eax
0x18001730c  cmp     eax, 0EAh
0x180017311  jz      short loc_180017345
0x180017313  test    eax, eax
0x180017315  jle     short loc_180017320
0x180017317  movzx   esi, ax
0x18001731a  or      esi, 80070000h
0x180017320  test    esi, esi
0x180017322  jns     loc_1800173E3
0x180017328  mov     rcx, [rbp+18h]; this
0x18001732c  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017333  mov     r9d, esi; char *
0x180017336  mov     edx, 0B6h; void *
0x18001733b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017340  jmp     loc_1800173D2
0x180017345  mov     esi, dword ptr [rbp+uBytes]
0x180017348  xor     ecx, ecx; uFlags
0x18001734a  mov     edx, esi; uBytes
0x18001734c  call    cs:__imp_LocalAlloc
0x180017353  nop     dword ptr [rax+rax+00h]
0x180017358  mov     rdi, rax
0x18001735b  test    rax, rax
0x18001735e  jz      loc_18001751D
0x180017364  lea     rcx, [rsi+rax]
0x180017368  cmp     rax, rcx
0x18001736b  jz      short loc_18001737B
0x18001736d  xor     r8d, r8d
0x180017370  mov     [rax], r8b
0x180017373  inc     rax
0x180017376  cmp     rax, rcx
0x180017379  jnz     short loc_18001736D
0x18001737b  mov     r9d, dword ptr [rbp+uBytes]
0x18001737f  lea     rax, [rbp+uBytes]
0x180017383  mov     r8, rdi
0x180017386  mov     [rsp+40h+phkResult], rax; unsigned int
0x18001738b  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017392  lea     rcx, aNgclogonui; "NgcLogonUi"
0x180017399  call    cs:__imp_GetPersistedRegistryLocationW
0x1800173a0  nop     dword ptr [rax+rax+00h]
0x1800173a5  test    eax, eax
0x1800173a7  jz      short loc_1800173DC
0x1800173a9  mov     rcx, [rbp+18h]; this
0x1800173ad  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800173b4  mov     r9d, eax; char *
0x1800173b7  mov     edx, 0C0h; void *
0x1800173bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800173c1  mov     rcx, rdi; hMem
0x1800173c4  mov     esi, eax
0x1800173c6  call    cs:__imp_LocalFree
0x1800173cd  nop     dword ptr [rax+rax+00h]
0x1800173d2  test    esi, esi
0x1800173d4  js      loc_18001753A
0x1800173da  jmp     short loc_1800173E3
0x1800173dc  mov     rbx, rdi
0x1800173df  mov     [rbp+arg_10], rbx
0x1800173e3  lea     rax, [rbp+hKey]
0x1800173e7  mov     [rbp+hKey], 0
0x1800173ef  lea     rdi, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x1800173f6  mov     [rsp+40h+phkResult], rax; phkResult
0x1800173fb  mov     r9d, 20006h; samDesired
0x180017401  mov     [rbp+var_10], rdi
0x180017405  xor     r8d, r8d; ulOptions
0x180017408  mov     rdx, rbx; lpSubKey
0x18001740b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017412  call    cs:__imp_RegOpenKeyExW
0x180017419  nop     dword ptr [rax+rax+00h]
0x18001741e  test    eax, eax
0x180017420  jz      short loc_180017429
0x180017422  mov     edx, 3Eh ; '>'
0x180017427  jmp     short loc_180017467
0x180017429  mov     rcx, [rbp+hKey]; hKey
0x18001742d  lea     rax, [rbp+Data]
0x180017431  mov     r9d, 4; dwType
0x180017437  mov     dword ptr [rbp+Data], 0
0x18001743e  mov     [rsp+40h+cbData], r9d; cbData
0x180017443  lea     rdx, ValueName; "DeviceLockEnforcementPending"
0x18001744a  xor     r8d, r8d; Reserved
0x18001744d  mov     [rsp+40h+phkResult], rax; unsigned int
0x180017452  call    cs:__imp_RegSetValueExW
0x180017459  nop     dword ptr [rax+rax+00h]
0x18001745e  test    eax, eax
0x180017460  jz      short loc_180017499
0x180017462  mov     edx, 47h ; 'G'; void *
0x180017467  mov     rcx, [rbp+18h]; this
0x18001746b  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017472  mov     r9d, eax; char *
0x180017475  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001747a  lea     rcx, [rbp+var_10]
0x18001747e  mov     [rbp+var_10], rdi
0x180017482  mov     ebx, eax
0x180017484  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180017489  lea     rcx, [rbp+arg_10]
0x18001748d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180017492  mov     eax, ebx
0x180017494  jmp     loc_180017554
0x180017499  mov     rcx, [rbp+hKey]; hKey
0x18001749d  call    cs:__imp_RegFlushKey
0x1800174a4  nop     dword ptr [rax+rax+00h]
0x1800174a9  test    eax, eax
0x1800174ab  jz      short loc_1800174C5
0x1800174ad  mov     rcx, [rbp+18h]; this
0x1800174b1  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800174b8  mov     r9d, eax; char *
0x1800174bb  mov     edx, 49h ; 'I'; void *
0x1800174c0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800174c5  cmp     [rbp+hKey], 0
0x1800174ca  mov     [rbp+var_10], rdi
0x1800174ce  jz      short loc_180017505
0x1800174d0  lea     rcx, [rbp+var_10]
0x1800174d4  call    ?InternalClose@?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(void)
0x1800174d9  test    al, al
0x1800174db  jnz     short loc_1800174FD
0x1800174dd  call    cs:__imp_GetLastError
0x1800174e4  nop     dword ptr [rax+rax+00h]
0x1800174e9  test    eax, eax
0x1800174eb  jle     short loc_1800174F5
0x1800174ed  movzx   eax, ax
0x1800174f0  or      eax, 80070000h
0x1800174f5  mov     ecx, eax; this
0x1800174f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800174fc  int     3; Trap to Debugger
0x1800174fd  mov     [rbp+hKey], 0
0x180017505  test    rbx, rbx
0x180017508  jz      short loc_180017519
0x18001750a  mov     rcx, rbx; hMem
0x18001750d  call    cs:__imp_LocalFree
0x180017514  nop     dword ptr [rax+rax+00h]
0x180017519  xor     eax, eax
0x18001751b  jmp     short loc_180017554
0x18001751d  mov     rcx, [rbp+18h]; this
0x180017521  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017528  mov     esi, 8007000Eh
0x18001752d  mov     edx, 0B9h; void *
0x180017532  mov     r9d, esi; char *
0x180017535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001753a  mov     rcx, [rbp+18h]; this
0x18001753e  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017545  mov     r9d, esi; char *
0x180017548  mov     edx, 36h ; '6'; void *
0x18001754d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017552  mov     eax, esi
0x180017554  mov     rbx, [rsp+40h+arg_18]
0x180017559  add     rsp, 40h
0x18001755d  pop     rdi
0x18001755e  pop     rsi
0x18001755f  pop     rbp
0x180017560  retn
```
