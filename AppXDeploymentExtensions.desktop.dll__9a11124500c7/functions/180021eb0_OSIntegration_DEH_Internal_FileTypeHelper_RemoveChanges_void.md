# OSIntegration::DEH::Internal::FileTypeHelper::RemoveChanges(void)

- ea: `0x180021eb0`
- end: `0x180022409`
- name: `?RemoveChanges@FileTypeHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `1369`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::FileTypeHelper *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180012fc8`
- `0x18001979c`
- `0x18001adb4`
- `0x18001f678`
- `0x180021eb0`
- `0x180022598`
- `0x180022f94`
- `0x18003193c`
- `0x1800490c4`
- `0x18004dd78`
- `0x18004e244`
- `0x18004f2cc`
- `0x180050e60`
- `0x180069eb4`
- `0x180074248`
- `0x1800afaa0`
- `0x1800afb60`
- `0x1800afc5d`
- `0x1800e21c0`
- `0x180173890`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800220f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800220f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800220c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800220c8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022147`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022147`
- `ADVAPI32!RevertToSelf` at `0x18002203e`
- `ADVAPI32!RevertToSelf` at `0x18002203e`

## string_xrefs

- `0x1800222f9`: `onecore\admin\appmodel\osim\src\deh\appx\common\progidregistryhelper.cpp`
- `0x180021fc3`: `OpenWithProgids`
- `0x1800223a4`: `onecore\base\appmodel\common\impersonationcontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall OSIntegration::DEH::Internal::FileTypeHelper::RemoveChanges(
        OSIntegration::DEH::Internal::FileTypeHelper *this)
{
  __int64 v2; // rax
  struct Common::AutoHandleHKEY *v4; // rdi
  int v5; // ebx
  HKEY *v6; // r14
  unsigned __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rdx
  LSTATUS v10; // eax
  bool v11; // sf
  _DWORD *v12; // rax
  LSTATUS v13; // eax
  bool v14; // sf
  HKEY v15; // rcx
  int ThreadImpersonationToken; // eax
  unsigned int v17; // eax
  unsigned __int64 i; // r14
  __int64 v19; // r12
  __int64 v20; // rdx
  LSTATUS v21; // eax
  signed int v22; // r15d
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rbx
  unsigned int v27; // eax
  int v28; // edx
  int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rcx
  int IsStateSeparationEnabled; // eax
  __int64 v33; // rdx
  int phkResult; // [rsp+20h] [rbp-48h]
  PHKEY phkResulta; // [rsp+20h] [rbp-48h]
  int phkResultb; // [rsp+20h] [rbp-48h]
  const unsigned __int16 *v37; // [rsp+40h] [rbp-28h] BYREF
  __int64 v38; // [rsp+48h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  HKEY hKey; // [rsp+B0h] [rbp+48h] BYREF
  HKEY v42; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v43; // [rsp+C0h] [rbp+58h]
  __int64 v44; // [rsp+C8h] [rbp+60h]

  v2 = *((_QWORD *)this + 3);
  if ( *(_BYTE *)(v2 + 403) || *((_DWORD *)this + 240) && !*(_BYTE *)(v2 + 405) )
    return 0;
  v4 = (OSIntegration::DEH::Internal::FileTypeHelper *)((char *)this + 560);
  if ( *((_QWORD *)this + 70) )
    goto LABEL_5;
  v6 = 0;
  v42 = 0;
  if ( *((_BYTE *)this + 409) || *(_BYTE *)(*((_QWORD *)this + 69) + 406LL) )
  {
    LOBYTE(hKey) = 0;
    IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled((bool *)&hKey);
    v5 = IsStateSeparationEnabled;
    if ( IsStateSeparationEnabled < 0 )
    {
      v33 = 192;
      goto LABEL_67;
    }
    IsStateSeparationEnabled = Common::RegistryKey::Open(
                                 &v42,
                                 HKEY_LOCAL_MACHINE,
                                 (LPCWSTR)((unsigned __int64)L"OSDATA" & -(__int64)((_BYTE)hKey != 0)),
                                 0xF003Fu);
    v5 = IsStateSeparationEnabled;
    if ( IsStateSeparationEnabled < 0 )
    {
      v33 = 194;
      goto LABEL_67;
    }
  }
  else
  {
    IsStateSeparationEnabled = Common::RegistryKey::OpenCurrentUser(&v42, 0xF003Fu);
    v5 = IsStateSeparationEnabled;
    if ( IsStateSeparationEnabled < 0 )
    {
      v33 = 198;
      goto LABEL_67;
    }
  }
  IsStateSeparationEnabled = Common::RegistryKey::OpenSubKey(
                               (Common::RegistryKey *)&v42,
                               L"Software\\Classes",
                               0xF003Fu,
                               v4);
  v5 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled >= 0 )
  {
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v42);
LABEL_5:
    v5 = 0;
    v6 = (HKEY *)v4;
    goto LABEL_6;
  }
  v33 = 204;
LABEL_67:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v33,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\progidregistryhelper.cpp",
    (const char *)(unsigned int)IsStateSeparationEnabled,
    phkResult);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v42);
LABEL_6:
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    return 0;
  }
  RegDeleteTreeW_0(*v6, *((LPCWSTR *)this + 18));
  v7 = 0;
  if ( *((_QWORD *)this + 42) )
    goto LABEL_8;
  while ( 1 )
  {
    v38 = 0;
    TokenHandle = 0;
    ThreadImpersonationToken = Common::ImpersonationContext::GetThreadImpersonationToken(&TokenHandle);
    v7 = (unsigned int)ThreadImpersonationToken;
    if ( ThreadImpersonationToken < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\appmodel\\common\\impersonationcontext.cpp",
        (const char *)(unsigned int)ThreadImpersonationToken,
        phkResult);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BC,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
        (const char *)(unsigned int)v7,
        phkResultb);
      goto LABEL_38;
    }
    if ( !TokenHandle || RevertToSelf() )
      break;
    Common::HandleInternalFailure();
LABEL_29:
    RegCloseKey(v15);
    while ( ++v7 < *((_QWORD *)this + 42) )
    {
LABEL_8:
      hKey = 0;
      v8 = 8 * v7;
      if ( v7 >= *((_QWORD *)this + 42) )
        v9 = 0;
      else
        v9 = *(_QWORD *)(v8 + *((_QWORD *)this + 40));
      v10 = RegOpenKeyExW_0(*v6, *(LPCWSTR *)(v9 + 8), 0, 0xF003Fu, &hKey);
      v11 = v10 < 0;
      if ( v10 > 0 )
        v11 = 1;
      if ( !v11 )
      {
        if ( v7 >= *((_QWORD *)this + 46) )
          v12 = 0;
        else
          v12 = *(_DWORD **)(v8 + *((_QWORD *)this + 44));
        if ( *v12 )
          Common::RegistryKey::DeleteValue((Common::RegistryKey *)&hKey, L"PerceivedType");
        v42 = 0;
        v13 = RegOpenKeyExW_0(hKey, L"OpenWithProgids", 0, 0xF003Fu, &v42);
        v14 = v13 < 0;
        if ( v13 > 0 )
          v14 = 1;
        if ( !v14 )
          RegDeleteValueW_0(v42, *((LPCWSTR *)this + 18));
        if ( (unsigned __int64)v42 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(v42);
      }
      v15 = hKey;
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_29;
    }
  }
  LODWORD(v38) = 1;
  v42 = 0;
  v17 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\KindMap\\",
          0,
          0x2001Fu,
          &v42);
  if ( !v17 )
  {
    for ( i = 0; i < *((_QWORD *)this + 114); ++i )
    {
      v19 = 8 * i;
      if ( i < *((_QWORD *)this + 42) )
        v20 = *(_QWORD *)(v19 + *((_QWORD *)this + 40));
      else
        v20 = 0;
      v21 = RegDeleteValueW(v42, *(LPCWSTR *)(v20 + 8));
      v22 = v21;
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
          (const char *)(unsigned int)v22,
          (int)phkResulta);
        if ( (byte_180245604 & 0x10) != 0 )
        {
          if ( i < *((_QWORD *)this + 42) )
            v23 = *(_QWORD *)(v19 + *((_QWORD *)this + 40));
          else
            v23 = 0;
          v24 = *(_QWORD *)(v23 + 8);
          v25 = *((_QWORD *)this + 3);
          v26 = *(_QWORD *)(v25 + 224);
          v27 = (unsigned int)RemovePIIfromFilePath(*(const unsigned __int16 **)(v25 + 272));
          McTemplateU0zdzz_EventWriteTransfer(v29, v28, v27, v22, v26, v24);
        }
        if ( i < *((_QWORD *)this + 42) )
          v30 = *(_QWORD *)(v19 + *((_QWORD *)this + 40));
        else
          v30 = 0;
        v43 = *(_QWORD *)(v30 + 8);
        v31 = *((_QWORD *)this + 3);
        v44 = *(_QWORD *)(v31 + 224);
        v37 = RemovePIIfromFilePath(*(const unsigned __int16 **)(v31 + 272));
        LODWORD(hKey) = v22;
        phkResulta = (PHKEY)&v37;
        SetAppXErrorFromLogMessage(
          v22,
          &APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID,
          &FTADEHErrorDeleteFailedRemovechanges,
          4u);
      }
    }
    if ( v42 )
      RegCloseKey(v42);
    if ( (_DWORD)v38 )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)&v38);
    return 0;
  }
  LODWORD(v7) = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4BF,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\filetype\\filetypehelper.cpp",
                  (const char *)v17,
                  (unsigned int)phkResulta);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v42);
LABEL_38:
  if ( (_DWORD)v38 )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)&v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021eb0  push    rbp
0x180021eb2  push    rbx
0x180021eb3  push    rsi
0x180021eb4  push    rdi
0x180021eb5  push    r12
0x180021eb7  push    r13
0x180021eb9  push    r14
0x180021ebb  push    r15
0x180021ebd  mov     rbp, rsp
0x180021ec0  sub     rsp, 68h
0x180021ec4  mov     rsi, rcx
0x180021ec7  mov     rax, [rcx+18h]
0x180021ecb  xor     r13d, r13d
0x180021ece  cmp     [rax+193h], r13b
0x180021ed5  jz      short loc_180021EEB
0x180021ed7  xor     eax, eax
0x180021ed9  add     rsp, 68h
0x180021edd  pop     r15
0x180021edf  pop     r14
0x180021ee1  pop     r13
0x180021ee3  pop     r12
0x180021ee5  pop     rdi
0x180021ee6  pop     rsi
0x180021ee7  pop     rbx
0x180021ee8  pop     rbp
0x180021ee9  retn
0x180021eeb  cmp     [rcx+3C0h], r13d
0x180021ef2  jnz     loc_18002228F
0x180021ef8  lea     rdi, [rcx+230h]
0x180021eff  mov     r15d, 0F003Fh
0x180021f05  mov     r12, 0FFFFFFFF80000002h
0x180021f0c  cmp     [rdi], r13
0x180021f0f  jz      loc_1800222A1
0x180021f15  mov     ebx, r13d
0x180021f18  mov     r14, rdi
0x180021f1b  mov     rcx, [rbp+40h]; this
0x180021f1f  test    ebx, ebx
0x180021f21  js      loc_180022373
0x180021f27  mov     rdx, [rsi+90h]; lpSubKey
0x180021f2e  mov     rcx, [r14]; hKey
0x180021f31  call    RegDeleteTreeW_0
0x180021f36  mov     rbx, r13
0x180021f39  cmp     [rsi+150h], r13
0x180021f40  jbe     loc_180022019
0x180021f46  mov     [rbp+hKey], r13
0x180021f4a  lea     rdi, ds:0[rbx*8]
0x180021f52  cmp     rbx, [rsi+150h]
0x180021f59  jnb     loc_180022091
0x180021f5f  mov     rax, [rsi+140h]
0x180021f66  mov     rdx, [rdi+rax]
0x180021f6a  lea     rax, [rbp+hKey]
0x180021f6e  mov     [rsp+68h+phkResult], rax; phkResult
0x180021f73  mov     r9d, r15d; samDesired
0x180021f76  xor     r8d, r8d; ulOptions
0x180021f79  mov     rdx, [rdx+8]; lpSubKey
0x180021f7d  mov     rcx, [r14]; hKey
0x180021f80  call    RegOpenKeyExW_0
0x180021f85  test    eax, eax
0x180021f87  jg      loc_180022062
0x180021f8d  js      short loc_180021FFB
0x180021f8f  cmp     rbx, [rsi+170h]
0x180021f96  jnb     loc_180022099
0x180021f9c  mov     rax, [rsi+160h]
0x180021fa3  mov     rax, [rdi+rax]
0x180021fa7  cmp     [rax], r13d
0x180021faa  ja      loc_18002238C
0x180021fb0  mov     [rbp+arg_8], r13
0x180021fb4  lea     rax, [rbp+arg_8]
0x180021fb8  mov     [rsp+68h+phkResult], rax; int
0x180021fbd  mov     r9d, r15d; samDesired
0x180021fc0  xor     r8d, r8d; ulOptions
0x180021fc3  lea     rdx, aOpenwithprogid; "OpenWithProgids"
0x180021fca  mov     rcx, [rbp+hKey]; hKey
0x180021fce  call    RegOpenKeyExW_0
0x180021fd3  test    eax, eax
0x180021fd5  jg      loc_180022082
0x180021fdb  js      short loc_180021FED
0x180021fdd  mov     rdx, [rsi+90h]; lpValueName
0x180021fe4  mov     rcx, [rbp+arg_8]; hKey
0x180021fe8  call    RegDeleteValueW_0
0x180021fed  mov     rcx, [rbp+arg_8]; hKey
0x180021ff1  lea     rax, [rcx-1]
0x180021ff5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021ff9  jbe     short loc_180022071
0x180021ffb  mov     rcx, [rbp+hKey]
0x180021fff  lea     rax, [rcx-1]
0x180022003  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022007  jbe     short loc_180022054
0x180022009  inc     rbx
0x18002200c  cmp     rbx, [rsi+150h]
0x180022013  jb      loc_180021F46
0x180022019  mov     [rbp+var_20], r13
0x18002201d  mov     [rbp+TokenHandle], r13
0x180022021  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180022025  call    ?GetThreadImpersonationToken@ImpersonationContext@Common@@SAJPEAPEAX@Z; Common::ImpersonationContext::GetThreadImpersonationToken(void * *)
0x18002202a  mov     ebx, eax
0x18002202c  mov     rcx, [rbp+40h]; this
0x180022030  test    eax, eax
0x180022032  js      loc_1800223A1
0x180022038  cmp     [rbp+TokenHandle], r13
0x18002203c  jz      short loc_1800220A1
0x18002203e  call    cs:__imp_RevertToSelf
0x180022045  nop     dword ptr [rax+rax+00h]
0x18002204a  test    eax, eax
0x18002204c  jnz     short loc_1800220A1
0x18002204e  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180022053  nop
0x180022054  call    cs:__imp_RegCloseKey
0x18002205b  nop     dword ptr [rax+rax+00h]
0x180022060  jmp     short loc_180022009
0x180022062  movzx   eax, ax
0x180022065  or      eax, 80070000h
0x18002206a  test    eax, eax
0x18002206c  jmp     loc_180021F8D
0x180022071  call    cs:__imp_RegCloseKey
0x180022078  nop     dword ptr [rax+rax+00h]
0x18002207d  jmp     loc_180021FFB
0x180022082  movzx   eax, ax
0x180022085  or      eax, 80070000h
0x18002208a  test    eax, eax
0x18002208c  jmp     loc_180021FDB
0x180022091  mov     rdx, r13
0x180022094  jmp     loc_180021F6A
0x180022099  mov     rax, r13
0x18002209c  jmp     loc_180021FA7
0x1800220a1  mov     dword ptr [rbp+var_20], 1
0x1800220a8  mov     [rbp+arg_8], r13
0x1800220ac  lea     rax, [rbp+arg_8]
0x1800220b0  mov     [rsp+68h+phkResult], rax; unsigned int
0x1800220b5  mov     r9d, 2001Fh; samDesired
0x1800220bb  xor     r8d, r8d; ulOptions
0x1800220be  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800220c5  mov     rcx, r12; hKey
0x1800220c8  call    cs:__imp_RegOpenKeyExW
0x1800220cf  nop     dword ptr [rax+rax+00h]
0x1800220d4  test    eax, eax
0x1800220d6  jnz     loc_1800223E0
0x1800220dc  mov     r14, r13
0x1800220df  cmp     [rsi+390h], r13
0x1800220e6  ja      short loc_180022127
0x1800220e8  mov     rcx, [rbp+arg_8]; hKey
0x1800220ec  test    rcx, rcx
0x1800220ef  jz      short loc_1800220FE
0x1800220f1  call    cs:__imp_RegCloseKey
0x1800220f8  nop     dword ptr [rax+rax+00h]
0x1800220fd  nop
0x1800220fe  cmp     dword ptr [rbp+var_20], r13d
0x180022102  jz      loc_180021ED7
0x180022108  lea     rcx, [rbp+var_20]; this
0x18002210c  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180022111  jmp     loc_180021ED7
0x180022116  cmp     dword ptr [rbp+var_20], r13d
0x18002211a  jnz     loc_1800223D2
0x180022120  mov     eax, ebx
0x180022122  jmp     loc_180021ED9
0x180022127  lea     r12, ds:0[r14*8]
0x18002212f  cmp     r14, [rsi+150h]
0x180022136  jb      loc_18002225F
0x18002213c  mov     rdx, r13
0x18002213f  mov     rdx, [rdx+8]; lpValueName
0x180022143  mov     rcx, [rbp+arg_8]; hKey
0x180022147  call    cs:__imp_RegDeleteValueW
0x18002214e  nop     dword ptr [rax+rax+00h]
0x180022153  mov     r15d, eax
0x180022156  test    eax, eax
0x180022158  jle     short loc_180022165
0x18002215a  movzx   r15d, ax
0x18002215e  or      r15d, 80070000h
0x180022165  test    r15d, r15d
0x180022168  jns     loc_18002224A
0x18002216e  mov     rcx, [rbp+40h]; this
0x180022172  mov     r9d, r15d; char *
0x180022175  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002217c  mov     edx, 4CEh; void *
0x180022181  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022186  test    cs:byte_180245604, 10h
0x18002218d  jz      short loc_1800221CF
0x18002218f  cmp     r14, [rsi+150h]
0x180022196  jb      loc_18002226F
0x18002219c  mov     rdi, r13
0x18002219f  mov     rdi, [rdi+8]
0x1800221a3  mov     rcx, [rsi+18h]
0x1800221a7  mov     rbx, [rcx+0E0h]
0x1800221ae  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800221b5  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x1800221ba  mov     [rsp+68h+var_40], rdi
0x1800221bf  mov     [rsp+68h+phkResult], rbx
0x1800221c4  mov     r9d, r15d
0x1800221c7  mov     r8, rax
0x1800221ca  call    McTemplateU0zdzz_EventWriteTransfer
0x1800221cf  cmp     r14, [rsi+150h]
0x1800221d6  jb      loc_18002227F
0x1800221dc  mov     rax, r13
0x1800221df  mov     rax, [rax+8]
0x1800221e3  mov     [rbp+arg_10], rax
0x1800221e7  mov     rcx, [rsi+18h]
0x1800221eb  mov     rax, [rcx+0E0h]
0x1800221f2  mov     [rbp+arg_18], rax
0x1800221f6  mov     rcx, [rcx+110h]; unsigned __int16 *
0x1800221fd  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180022202  mov     [rbp+var_28], rax
0x180022206  mov     dword ptr [rbp+hKey], r15d
0x18002220a  lea     rax, [rbp+arg_10]
0x18002220e  mov     [rsp+68h+var_30], rax
0x180022213  lea     rax, [rbp+arg_18]
0x180022217  mov     [rsp+68h+var_38], rax
0x18002221c  lea     rax, [rbp+hKey]
0x180022220  mov     [rsp+68h+var_40], rax
0x180022225  lea     rax, [rbp+var_28]
0x180022229  mov     [rsp+68h+phkResult], rax
0x18002222e  mov     r9d, 4; unsigned int
0x180022234  lea     r8, FTADEHErrorDeleteFailedRemovechanges; struct _EVENT_DESCRIPTOR *
0x18002223b  lea     rdx, APPXDEPLOYMENTSERVER_ETW_CONTROL_GUID; struct _GUID *
0x180022242  mov     ecx, r15d; int
0x180022245  call    ?SetAppXErrorFromLogMessage@@YAJJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@KZZ; SetAppXErrorFromLogMessage(long,_GUID const &,_EVENT_DESCRIPTOR const &,ulong,...)
0x18002224a  inc     r14
0x18002224d  cmp     r14, [rsi+390h]
0x180022254  jb      loc_180022127
0x18002225a  jmp     loc_1800220E8
0x18002225f  mov     rax, [rsi+140h]
0x180022266  mov     rdx, [r12+rax]
0x18002226a  jmp     loc_18002213F
0x18002226f  mov     rax, [rsi+140h]
0x180022276  mov     rdi, [r12+rax]
0x18002227a  jmp     loc_18002219F
0x18002227f  mov     rax, [rsi+140h]
0x180022286  mov     rax, [r12+rax]
0x18002228a  jmp     loc_1800221DF
0x18002228f  cmp     [rax+195h], r13b
0x180022296  jz      loc_180021ED7
0x18002229c  jmp     loc_180021EF8
0x1800222a1  mov     r14, r13
0x1800222a4  mov     [rbp+arg_8], r13
0x1800222a8  cmp     [rcx+199h], r13b
0x1800222af  jnz     short loc_1800222DA
0x1800222b1  mov     rax, [rcx+228h]
0x1800222b8  cmp     [rax+196h], r13b
0x1800222bf  jnz     short loc_1800222DA
0x1800222c1  mov     edx, r15d; samDesired
0x1800222c4  lea     rcx, [rbp+arg_8]; phkResult
0x1800222c8  call    ?OpenCurrentUser@RegistryKey@Common@@QEAAJK@Z; Common::RegistryKey::OpenCurrentUser(ulong)
0x1800222cd  mov     ebx, eax
0x1800222cf  test    eax, eax
0x1800222d1  jns     short loc_180022349
0x1800222d3  mov     edx, 0C6h
0x1800222d8  jmp     short loc_1800222F9
0x1800222da  mov     byte ptr [rbp+hKey], r13b
0x1800222de  lea     rcx, [rbp+hKey]; bool *
0x1800222e2  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800222e7  mov     ebx, eax
0x1800222e9  test    eax, eax
0x1800222eb  jns     short loc_18002231B
0x1800222ed  mov     edx, 0C0h
0x1800222f2  jmp     short loc_1800222F9
0x1800222f4  mov     edx, 0CCh; void *
0x1800222f9  lea     r8, aOnecoreAdminAp_137; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180022300  mov     r9d, eax; char *
0x180022303  mov     rcx, [rbp+40h]; this
0x180022307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002230c  nop
0x18002230d  lea     rcx, [rbp+arg_8]; this
0x180022311  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180022316  jmp     loc_180021F1B
0x18002231b  mov     al, byte ptr [rbp+hKey]
0x18002231e  neg     al
0x180022320  sbb     r8, r8
0x180022323  lea     rax, aOsdata; "OSDATA"
0x18002232a  and     r8, rax; lpSubKey
0x18002232d  mov     r9d, r15d; samDesired
0x180022330  mov     rdx, r12; hKey
0x180022333  lea     rcx, [rbp+arg_8]; phkResult
0x180022337  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002233c  mov     ebx, eax
0x18002233e  test    eax, eax
0x180022340  jns     short loc_180022349
0x180022342  mov     edx, 0C2h
0x180022347  jmp     short loc_1800222F9
0x180022349  mov     r9, rdi; struct Common::AutoHandleHKEY *
0x18002234c  mov     r8d, r15d; unsigned int
0x18002234f  lea     rdx, aSoftwareClasse_3; "Software\\Classes"
0x180022356  lea     rcx, [rbp+arg_8]; this
0x18002235a  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x18002235f  mov     ebx, eax
0x180022361  test    eax, eax
0x180022363  js      short loc_1800222F4
0x180022365  lea     rcx, [rbp+arg_8]; this
0x180022369  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18002236e  jmp     loc_180021F15
0x180022373  mov     r9d, ebx; char *
0x180022376  lea     r8, aOnecoreAdminAp_7; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002237d  mov     edx, 493h; void *
0x180022382  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022387  jmp     loc_180021ED7
0x18002238c  lea     rdx, aPerceivedtype; "PerceivedType"
0x180022393  lea     rcx, [rbp+hKey]; this
0x180022397  call    ?DeleteValue@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteValue(ushort const *)
0x18002239c  jmp     loc_180021FB0
0x1800223a1  mov     r9d, ebx; char *
0x1800223a4  lea     r8, aOnecoreBaseApp_84; "onecore\\base\\appmodel\\common\\impers"...
0x1800223ab  mov     edx, 2Eh ; '.'; void *
  ... truncated ...
```
