# MFValidateSensorProfile

- ea: `0x1800583e0`
- end: `0x1800586c4`
- name: `MFValidateSensorProfile`
- size: `740`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, struct IMFSensorProfileValidationCallback *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x1800357dc`
- `0x180044f30`
- `0x180045900`
- `0x1800583e0`
- `0x18005aff0`
- `0x18005b8d8`
- `0x18005c2b8`
- `0x18005c544`
- `0x18005cb10`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005850f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005867e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005868c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005850f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005867e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005868c`

## string_xrefs

- `0x1800584a9`: `SymbolicName`

## pseudocode

```c
__int64 __fastcall MFValidateSensorProfile(LPCWSTR pszDeviceInterface, struct IMFSensorProfileValidationCallback *a2)
{
  HKEY v2; // rsi
  __int64 v5; // rbx
  __int64 v6; // rdx
  HKEY v7; // r14
  DWORD v8; // r15d
  __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  HKEY v16; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFSensorProfileValidationCallback *v18; // [rsp+40h] [rbp-C0h] BYREF
  GUID iid; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v21[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  hKey = 0;
  v16 = 0;
  v18 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( pszDeviceInterface )
  {
    if ( !a2 )
    {
      LODWORD(v5) = -2147024809;
      if ( !g_wppLevels )
        goto LABEL_37;
      v6 = 102;
      goto LABEL_6;
    }
    v5 = (unsigned int)OpenSensorProfileV2Store(pszDeviceInterface, &hKey);
    (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *, __int64, const wchar_t *, LPCWSTR))(*(_QWORD *)a2 + 24LL))(
      a2,
      v5,
      L"SymbolicName",
      pszDeviceInterface);
    v7 = hKey;
    if ( (int)v5 >= 0 )
    {
      v8 = 0;
      while ( 1 )
      {
        if ( (int)v5 < 0 )
          goto LABEL_33;
        memset_0(v21, 0, 0x208u);
        LODWORD(hKey) = 0;
        v20 = 0;
        iid = 0;
        if ( v2 )
        {
          RegCloseKey(v2);
          v16 = 0;
        }
        v10 = EnumProfileStore(v7, v8, v21, v9, (unsigned int *)&hKey, &v16);
        if ( v10 < 0 )
          break;
        LODWORD(v20) = 0;
        ++v8;
        iid = GUID_00000000_0000_0000_0000_000000000000;
        v11 = ParseProfileName(v21, &iid);
        v12 = *(_QWORD *)a2;
        if ( v11 >= 0 )
        {
          if ( (int)v20 < 0 )
            v11 = -1072875841;
          (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *, _QWORD, unsigned __int16 *))(v12 + 32))(
            a2,
            (unsigned int)v11,
            v21);
          v2 = v16;
          v13 = ValidateProfileConstraints(v16, a2);
          LODWORD(v5) = v13;
          if ( v13 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_33;
            v14 = 103;
            goto LABEL_31;
          }
          v13 = ValidateProfileBlockedControls(v2, a2);
          LODWORD(v5) = v13;
          if ( v13 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_33;
            v14 = 104;
            goto LABEL_31;
          }
          v13 = ValidateProfileFilterSets(v2, a2);
          LODWORD(v5) = v13;
          if ( v13 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_33;
            v14 = 105;
LABEL_31:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
              0,
              v13);
            goto LABEL_33;
          }
          (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *, unsigned __int16 *))(*(_QWORD *)a2 + 40LL))(
            a2,
            v21);
        }
        else
        {
          (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *, _QWORD, unsigned __int16 *))(v12 + 32))(
            a2,
            (unsigned int)v11,
            v21);
          v2 = v16;
          LODWORD(v5) = 0;
        }
      }
      (*(void (__fastcall **)(struct IMFSensorProfileValidationCallback *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 24LL))(
        a2,
        (unsigned int)v10,
        L"EnumProfiles",
        0);
      v2 = v16;
      LODWORD(v5) = 0;
LABEL_33:
      if ( v2 )
        RegCloseKey(v2);
    }
    else
    {
      LODWORD(v5) = 0;
    }
    if ( v7 )
      RegCloseKey(v7);
  }
  else
  {
    LODWORD(v5) = -2147024809;
    if ( g_wppLevels )
    {
      v6 = 101;
LABEL_6:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
        0,
        -2147024809);
    }
  }
LABEL_37:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800583e0  mov     [rsp-8+arg_10], rbx
0x1800583e5  push    rbp
0x1800583e6  push    rsi
0x1800583e7  push    rdi
0x1800583e8  push    r14
0x1800583ea  push    r15
0x1800583ec  lea     rbp, [rsp-180h]
0x1800583f4  sub     rsp, 280h
0x1800583fb  mov     rax, cs:__security_cookie
0x180058402  xor     rax, rsp
0x180058405  mov     [rbp+1A0h+var_30], rax
0x18005840c  xor     esi, esi
0x18005840e  mov     [rsp+2A0h+hKey], 0
0x180058417  mov     [rsp+2A0h+var_270], rsi
0x18005841c  mov     rdi, rdx
0x18005841f  mov     [rsp+2A0h+var_260], rdx
0x180058424  mov     r14, rcx
0x180058427  test    rdx, rdx
0x18005842a  jz      short loc_18005843B
0x18005842c  mov     rax, [rdx]
0x18005842f  mov     rcx, rdx
0x180058432  mov     rax, [rax+8]
0x180058436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005843b  test    r14, r14
0x18005843e  jnz     short loc_18005847B
0x180058440  mov     eax, 80070057h
0x180058445  mov     ebx, eax
0x180058447  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005844e  jb      loc_180058692
0x180058454  lea     edx, [r14+65h]
0x180058458  mov     rcx, cs:WPP_GLOBAL_Control
0x18005845f  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180058466  xor     r9d, r9d
0x180058469  mov     dword ptr [rsp+2A0h+var_280], eax
0x18005846d  mov     rcx, [rcx+10h]
0x180058471  call    WPP_SF_qD
0x180058476  jmp     loc_180058692
0x18005847b  test    rdi, rdi
0x18005847e  jnz     short loc_180058499
0x180058480  mov     eax, 80070057h
0x180058485  mov     ebx, eax
0x180058487  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005848e  jb      loc_180058692
0x180058494  lea     edx, [rdi+66h]
0x180058497  jmp     short loc_180058458
0x180058499  lea     rdx, [rsp+2A0h+hKey]; HKEY *
0x18005849e  mov     rcx, r14; pszDeviceInterface
0x1800584a1  call    ?OpenSensorProfileV2Store@@YAJPEBGPEAPEAUHKEY__@@@Z; OpenSensorProfileV2Store(ushort const *,HKEY__ * *)
0x1800584a6  mov     rcx, [rdi]
0x1800584a9  lea     r8, aSymbolicname; "SymbolicName"
0x1800584b0  mov     ebx, eax
0x1800584b2  mov     r9, r14
0x1800584b5  mov     edx, ebx
0x1800584b7  mov     rax, [rcx+18h]
0x1800584bb  mov     rcx, rdi
0x1800584be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584c3  mov     r14, [rsp+2A0h+hKey]
0x1800584c8  test    ebx, ebx
0x1800584ca  jns     short loc_1800584D3
0x1800584cc  xor     ebx, ebx
0x1800584ce  jmp     loc_180058684
0x1800584d3  xor     r15d, r15d
0x1800584d6  test    ebx, ebx
0x1800584d8  js      loc_180058676
0x1800584de  xor     edx, edx; Val
0x1800584e0  lea     rcx, [rsp+2A0h+var_240]; void *
0x1800584e5  mov     r8d, 208h; Size
0x1800584eb  call    memset_0
0x1800584f0  xor     eax, eax
0x1800584f2  mov     dword ptr [rsp+2A0h+hKey], 0
0x1800584fa  mov     [rsp+2A0h+var_248], rax
0x1800584ff  xorps   xmm0, xmm0
0x180058502  movups  xmmword ptr [rsp+2A0h+iid.Data1], xmm0
0x180058507  test    rsi, rsi
0x18005850a  jz      short loc_18005851E
0x18005850c  mov     rcx, rsi; hKey
0x18005850f  call    cs:__imp_RegCloseKey
0x180058515  mov     [rsp+2A0h+var_270], 0
0x18005851e  lea     rax, [rsp+2A0h+var_270]
0x180058523  mov     edx, r15d; unsigned int
0x180058526  mov     [rsp+2A0h+var_278], rax; HKEY *
0x18005852b  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x180058530  lea     rax, [rsp+2A0h+hKey]
0x180058535  mov     rcx, r14; hKey
0x180058538  mov     [rsp+2A0h+var_280], rax; unsigned int *
0x18005853d  call    ?EnumProfileStore@@YAJPEAUHKEY__@@KPEAGKPEAKPEAPEAU1@@Z; EnumProfileStore(HKEY__ *,ulong,ushort *,ulong,ulong *,HKEY__ * *)
0x180058542  mov     edx, eax
0x180058544  test    eax, eax
0x180058546  js      loc_180058656
0x18005854c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180058553  lea     rdx, [rsp+2A0h+iid]; lpiid
0x180058558  mov     dword ptr [rsp+2A0h+var_248], 0
0x180058560  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x180058565  inc     r15d
0x180058568  movdqu  xmmword ptr [rsp+2A0h+iid.Data1], xmm0
0x18005856e  call    ?ParseProfileName@@YAJPEBGPEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@@Z; ParseProfileName(ushort const *,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *)
0x180058573  mov     r9, [rdi]
0x180058576  lea     r8, [rsp+2A0h+var_240]
0x18005857b  test    eax, eax
0x18005857d  jns     short loc_180058599
0x18005857f  mov     edx, eax
0x180058581  mov     rcx, rdi
0x180058584  mov     rax, [r9+20h]
0x180058588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005858d  mov     rsi, [rsp+2A0h+var_270]
0x180058592  xor     ebx, ebx
0x180058594  jmp     loc_1800584D6
0x180058599  test    dword ptr [rsp+2A0h+var_248], 80000000h
0x1800585a1  mov     ecx, 0C00D36BFh
0x1800585a6  cmovnz  eax, ecx
0x1800585a9  mov     rcx, rdi
0x1800585ac  mov     edx, eax
0x1800585ae  mov     rax, [r9+20h]
0x1800585b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800585b7  mov     rsi, [rsp+2A0h+var_270]
0x1800585bc  mov     rdx, rdi; struct IMFSensorProfileValidationCallback *
0x1800585bf  mov     rcx, rsi; hKey
0x1800585c2  call    ?ValidateProfileConstraints@@YAJPEAUHKEY__@@PEAUIMFSensorProfileValidationCallback@@@Z; ValidateProfileConstraints(HKEY__ *,IMFSensorProfileValidationCallback *)
0x1800585c7  mov     ebx, eax
0x1800585c9  test    eax, eax
0x1800585cb  js      short loc_180058628
0x1800585cd  mov     rdx, rdi; struct IMFSensorProfileValidationCallback *
0x1800585d0  mov     rcx, rsi; hKey
0x1800585d3  call    ?ValidateProfileBlockedControls@@YAJPEAUHKEY__@@PEAUIMFSensorProfileValidationCallback@@@Z; ValidateProfileBlockedControls(HKEY__ *,IMFSensorProfileValidationCallback *)
0x1800585d8  mov     ebx, eax
0x1800585da  test    eax, eax
0x1800585dc  js      short loc_180058618
0x1800585de  mov     rdx, rdi; struct IMFSensorProfileValidationCallback *
0x1800585e1  mov     rcx, rsi; hKey
0x1800585e4  call    ?ValidateProfileFilterSets@@YAJPEAUHKEY__@@PEAUIMFSensorProfileValidationCallback@@@Z; ValidateProfileFilterSets(HKEY__ *,IMFSensorProfileValidationCallback *)
0x1800585e9  mov     ebx, eax
0x1800585eb  test    eax, eax
0x1800585ed  js      short loc_180058608
0x1800585ef  mov     rax, [rdi]
0x1800585f2  lea     rdx, [rsp+2A0h+var_240]
0x1800585f7  mov     rcx, rdi
0x1800585fa  mov     rax, [rax+28h]
0x1800585fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058603  jmp     loc_1800584D6
0x180058608  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005860f  jb      short loc_180058676
0x180058611  mov     edx, 69h ; 'i'
0x180058616  jmp     short loc_180058636
0x180058618  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005861f  jb      short loc_180058676
0x180058621  mov     edx, 68h ; 'h'
0x180058626  jmp     short loc_180058636
0x180058628  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005862f  jb      short loc_180058676
0x180058631  mov     edx, 67h ; 'g'
0x180058636  mov     rcx, cs:WPP_GLOBAL_Control
0x18005863d  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180058644  xor     r9d, r9d
0x180058647  mov     dword ptr [rsp+2A0h+var_280], eax
0x18005864b  mov     rcx, [rcx+10h]
0x18005864f  call    WPP_SF_qD
0x180058654  jmp     short loc_180058676
0x180058656  mov     rax, [rdi]
0x180058659  lea     r8, aEnumprofiles; "EnumProfiles"
0x180058660  xor     r9d, r9d
0x180058663  mov     rcx, rdi
0x180058666  mov     rax, [rax+18h]
0x18005866a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005866f  mov     rsi, [rsp+2A0h+var_270]
0x180058674  xor     ebx, ebx
0x180058676  test    rsi, rsi
0x180058679  jz      short loc_180058684
0x18005867b  mov     rcx, rsi; hKey
0x18005867e  call    cs:__imp_RegCloseKey
0x180058684  test    r14, r14
0x180058687  jz      short loc_180058692
0x180058689  mov     rcx, r14; hKey
0x18005868c  call    cs:__imp_RegCloseKey
0x180058692  lea     rcx, [rsp+2A0h+var_260]
0x180058697  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18005869c  mov     eax, ebx
0x18005869e  mov     rcx, [rbp+1A0h+var_30]
0x1800586a5  xor     rcx, rsp; StackCookie
0x1800586a8  call    __security_check_cookie
0x1800586ad  mov     rbx, [rsp+2A0h+arg_10]
0x1800586b5  add     rsp, 280h
0x1800586bc  pop     r15
0x1800586be  pop     r14
0x1800586c0  pop     rdi
0x1800586c1  pop     rsi
0x1800586c2  pop     rbp
0x1800586c3  retn
```
