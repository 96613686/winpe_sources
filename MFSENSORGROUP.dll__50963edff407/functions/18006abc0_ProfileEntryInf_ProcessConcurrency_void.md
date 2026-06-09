# ProfileEntryInf::ProcessConcurrency(void)

- ea: `0x18006abc0`
- end: `0x18006aef5`
- name: `?ProcessConcurrency@ProfileEntryInf@@UEAAJXZ`
- size: `821`
- prototype: `__int64 __fastcall(ProfileEntryInf *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config`

## callees

- `0x180005fa0`
- `0x18002d02c`
- `0x180041074`
- `0x180044f30`
- `0x180045900`
- `0x180067d90`
- `0x180068318`
- `0x180069f34`
- `0x18006a228`
- `0x18006abc0`
- `0x18006d7f4`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006ad68`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18006ad68`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006adb6`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006adb6`

## string_xrefs

- `0x18006add5`: `profile %S, failed to open device interface (%S) key!`

## pseudocode

```c
__int64 __fastcall ProfileEntryInf::ProcessConcurrency(ProfileEntryInf *this)
{
  HKEY v2; // rcx
  unsigned int v3; // ebx
  int SymbolicLinkNameByReferenceGuid; // eax
  __int64 v5; // rdx
  unsigned __int16 *v6; // r14
  HKEY *v7; // r15
  CONFIGRET v8; // r12d
  signed int v9; // eax
  int v11; // [rsp+30h] [rbp-D0h]
  struct ProfileConcurrency *v12; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-B8h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v16[264]; // [rsp+270h] [rbp+170h] BYREF

  rguid = GUID_00000000_0000_0000_0000_000000000000;
  memset_0(v16, 0, 0x208u);
  v2 = (HKEY)*((_QWORD *)this + 88);
  v13 = 0;
  v12 = 0;
  if ( (int)ProfileRegReadValue(v2, L"Concurrency", (unsigned __int16 **)this + 89, (int *)this + 180) >= 0 )
  {
    SymbolicLinkNameByReferenceGuid = MFProfileInternalParseConcurrencyReferenceGuid(
                                        (const unsigned __int16 *)this + 92,
                                        *((const unsigned __int16 **)this + 89),
                                        *((_DWORD *)this + 180),
                                        *((struct IMFCameraProfileValidation **)this + 92),
                                        &rguid,
                                        v16,
                                        v11,
                                        (const unsigned __int16 **)&v13);
    v3 = SymbolicLinkNameByReferenceGuid;
    if ( SymbolicLinkNameByReferenceGuid >= 0 )
    {
      v6 = v13;
      if ( !v13 || !*v13 )
        return v3;
      memset_0(pszDeviceInterface, 0, 0x208u);
      SymbolicLinkNameByReferenceGuid = FindSymbolicLinkNameByReferenceGuid(&rguid, (LPBYTE)pszDeviceInterface);
      v3 = SymbolicLinkNameByReferenceGuid;
      if ( SymbolicLinkNameByReferenceGuid >= 0 )
      {
        v7 = (HKEY *)((char *)this + 728);
        v8 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, (PHKEY)this + 91, 0);
        if ( v8 )
        {
          if ( byte_18008D62F )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              111,
              (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
              (_DWORD)this + 184,
              (__int64)pszDeviceInterface);
          v9 = CM_MapCrToWin32Err(v8, 0xDu);
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
          SymbolicLinkNameByReferenceGuid = MFTraceValidation(
                                              *((_QWORD *)this + 92),
                                              4,
                                              (unsigned int)v9,
                                              "profile %S, failed to open device interface (%S) key!",
                                              (const wchar_t *)this + 92,
                                              pszDeviceInterface);
          v3 = SymbolicLinkNameByReferenceGuid;
          if ( SymbolicLinkNameByReferenceGuid < 0 )
          {
            if ( !g_wppLevels )
              return v3;
            v5 = 112;
            goto LABEL_32;
          }
          *v7 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        }
        if ( *v7 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          return v3;
        SymbolicLinkNameByReferenceGuid = (*(__int64 (__fastcall **)(ProfileEntryInf *, struct ProfileConcurrency **))(*(_QWORD *)this + 96LL))(
                                            this,
                                            &v12);
        v3 = SymbolicLinkNameByReferenceGuid;
        if ( SymbolicLinkNameByReferenceGuid >= 0 )
        {
          SymbolicLinkNameByReferenceGuid = MFProfileInternalParseConcurrencyProfileIds(
                                              (const unsigned __int16 *)this + 92,
                                              v6,
                                              *((struct IMFCameraProfileValidation **)this + 92),
                                              *v7,
                                              v12);
          v3 = SymbolicLinkNameByReferenceGuid;
          if ( SymbolicLinkNameByReferenceGuid >= 0 )
          {
            SymbolicLinkNameByReferenceGuid = (*(__int64 (__fastcall **)(struct ProfileConcurrency *, GUID *, WCHAR *))(*(_QWORD *)v12 + 56LL))(
                                                v12,
                                                &rguid,
                                                pszDeviceInterface);
            v3 = SymbolicLinkNameByReferenceGuid;
            if ( SymbolicLinkNameByReferenceGuid >= 0 || !g_wppLevels )
              return v3;
            v5 = 115;
          }
          else
          {
            if ( !g_wppLevels )
              return v3;
            v5 = 114;
          }
        }
        else
        {
          if ( !g_wppLevels )
            return v3;
          v5 = 113;
        }
      }
      else
      {
        if ( !g_wppLevels )
          return v3;
        v5 = 110;
      }
    }
    else
    {
      if ( !g_wppLevels )
        return v3;
      v5 = 109;
    }
LABEL_32:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
      this,
      SymbolicLinkNameByReferenceGuid);
    return v3;
  }
  if ( (unsigned __int8)byte_18008D62F >= 0x10u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      108,
      &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
      (char *)this + 184);
  MFTraceValidation(*((_QWORD *)this + 92), 4, 0, "profile %S, no concurrency defined.", (const wchar_t *)this + 92);
  return 0;
}

```

## disassembly

```asm
0x18006abc0  push    rbp
0x18006abc2  push    rbx
0x18006abc3  push    rsi
0x18006abc4  push    rdi
0x18006abc5  push    r12
0x18006abc7  push    r13
0x18006abc9  push    r14
0x18006abcb  push    r15
0x18006abcd  lea     rbp, [rsp-398h]
0x18006abd5  sub     rsp, 498h
0x18006abdc  mov     rax, cs:__security_cookie
0x18006abe3  xor     rax, rsp
0x18006abe6  mov     [rbp+3D0h+var_50], rax
0x18006abed  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006abf4  mov     rdi, rcx
0x18006abf7  mov     r15d, 208h
0x18006abfd  mov     r8d, r15d; Size
0x18006ac00  lea     rcx, [rbp+3D0h+var_260]; void *
0x18006ac07  xor     edx, edx; Val
0x18006ac09  movdqu  xmmword ptr [rsp+4D0h+rguid.Data1], xmm0
0x18006ac0f  call    memset_0
0x18006ac14  mov     rcx, [rdi+2C0h]; hkey
0x18006ac1b  lea     rbx, [rdi+2D0h]
0x18006ac22  xor     r13d, r13d
0x18006ac25  lea     r14, [rdi+2C8h]
0x18006ac2c  mov     r9, rbx; int *
0x18006ac2f  mov     [rsp+4D0h+var_488], r13
0x18006ac34  mov     r8, r14; unsigned __int16 **
0x18006ac37  mov     [rsp+4D0h+var_490], r13
0x18006ac3c  lea     rdx, aConcurrency; "Concurrency"
0x18006ac43  lea     rsi, [rdi+0B8h]
0x18006ac4a  call    ?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAPEAGPEAH@Z; ProfileRegReadValue(HKEY__ *,ushort const *,ushort * *,int *)
0x18006ac4f  test    eax, eax
0x18006ac51  jns     short loc_18006ACA4
0x18006ac53  cmp     cs:byte_18008D62F, 10h
0x18006ac5a  jb      short loc_18006AC7D
0x18006ac5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ac63  lea     edx, [r13+6Ch]
0x18006ac67  mov     r9, rsi
0x18006ac6a  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006ac71  mov     rcx, [rcx+128h]
0x18006ac78  call    WPP_SF_S
0x18006ac7d  mov     rcx, [rdi+2E0h]
0x18006ac84  lea     r9, aProfileSNoConc; "profile %S, no concurrency defined."
0x18006ac8b  xor     r8d, r8d
0x18006ac8e  mov     qword ptr [rsp+4D0h+ulFlags], rsi
0x18006ac93  lea     edx, [r8+4]
0x18006ac97  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006ac9c  mov     ebx, r13d
0x18006ac9f  jmp     loc_18006AED0
0x18006aca4  mov     r9, [rdi+2E0h]; struct IMFCameraProfileValidation *
0x18006acab  lea     rax, [rsp+4D0h+var_488]
0x18006acb0  mov     r8d, [rbx]; int
0x18006acb3  mov     rcx, rsi; unsigned __int16 *
0x18006acb6  mov     rdx, [r14]; unsigned __int16 *
0x18006acb9  mov     [rsp+4D0h+var_498], rax; unsigned __int16 **
0x18006acbe  lea     rax, [rbp+3D0h+var_260]
0x18006acc5  mov     [rsp+4D0h+var_4A8], rax; unsigned __int16 *
0x18006acca  lea     rax, [rsp+4D0h+rguid]
0x18006accf  mov     qword ptr [rsp+4D0h+ulFlags], rax; struct _GUID *
0x18006acd4  call    ?MFProfileInternalParseConcurrencyReferenceGuid@@YAJPEBG0HPEAUIMFCameraProfileValidation@@PEAU_GUID@@PEAGHPEAPEBG@Z; MFProfileInternalParseConcurrencyReferenceGuid(ushort const *,ushort const *,int,IMFCameraProfileValidation *,_GUID *,ushort *,int,ushort const * *)
0x18006acd9  mov     ebx, eax
0x18006acdb  test    eax, eax
0x18006acdd  jns     short loc_18006ACF6
0x18006acdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ace6  jb      loc_18006AED0
0x18006acec  mov     edx, 6Dh ; 'm'
0x18006acf1  jmp     loc_18006AEB2
0x18006acf6  mov     r14, [rsp+4D0h+var_488]
0x18006acfb  test    r14, r14
0x18006acfe  jz      loc_18006AED0
0x18006ad04  cmp     [r14], r13w
0x18006ad08  jz      loc_18006AED0
0x18006ad0e  mov     r8, r15; Size
0x18006ad11  lea     rcx, [rsp+4D0h+pszDeviceInterface]; void *
0x18006ad16  xor     edx, edx; Val
0x18006ad18  call    memset_0
0x18006ad1d  lea     rdx, [rsp+4D0h+pszDeviceInterface]; lpData
0x18006ad22  lea     rcx, [rsp+4D0h+rguid]; rguid
0x18006ad27  call    ?FindSymbolicLinkNameByReferenceGuid@@YAJAEBU_GUID@@PEAGH@Z; FindSymbolicLinkNameByReferenceGuid(_GUID const &,ushort *,int)
0x18006ad2c  mov     ebx, eax
0x18006ad2e  test    eax, eax
0x18006ad30  jns     short loc_18006AD49
0x18006ad32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ad39  jb      loc_18006AED0
0x18006ad3f  mov     edx, 6Eh ; 'n'
0x18006ad44  jmp     loc_18006AEB2
0x18006ad49  lea     r15, [rdi+2D8h]
0x18006ad50  mov     [rsp+4D0h+ulFlags], r13d; ulFlags
0x18006ad55  mov     r9, r15; phkDeviceInterface
0x18006ad58  lea     rcx, [rsp+4D0h+pszDeviceInterface]; pszDeviceInterface
0x18006ad5d  mov     edx, 20019h; samDesired
0x18006ad62  mov     r8d, 1; Disposition
0x18006ad68  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18006ad6e  mov     r12d, eax
0x18006ad71  test    eax, eax
0x18006ad73  jz      loc_18006AE16
0x18006ad79  cmp     cs:byte_18008D62F, 1
0x18006ad80  jb      short loc_18006ADAE
0x18006ad82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad89  lea     rax, [rsp+4D0h+pszDeviceInterface]
0x18006ad8e  mov     edx, 6Fh ; 'o'
0x18006ad93  mov     qword ptr [rsp+4D0h+ulFlags], rax
0x18006ad98  mov     r9, rsi
0x18006ad9b  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006ada2  mov     rcx, [rcx+128h]
0x18006ada9  call    WPP_SF_SS
0x18006adae  mov     edx, 0Dh; DefaultErr
0x18006adb3  mov     ecx, r12d; CmReturnCode
0x18006adb6  call    cs:__imp_CM_MapCrToWin32Err
0x18006adbc  test    eax, eax
0x18006adbe  jle     short loc_18006ADC8
0x18006adc0  movzx   eax, ax
0x18006adc3  or      eax, 80070000h
0x18006adc8  lea     rcx, [rsp+4D0h+pszDeviceInterface]
0x18006adcd  mov     r8d, eax
0x18006add0  mov     [rsp+4D0h+var_4A8], rcx
0x18006add5  lea     r9, aProfileSFailed; "profile %S, failed to open device inter"...
0x18006addc  mov     rcx, [rdi+2E0h]
0x18006ade3  mov     edx, 4
0x18006ade8  mov     qword ptr [rsp+4D0h+ulFlags], rsi
0x18006aded  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006adf2  mov     ebx, eax
0x18006adf4  test    eax, eax
0x18006adf6  jns     short loc_18006AE0F
0x18006adf8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006adff  jb      loc_18006AED0
0x18006ae05  mov     edx, 70h ; 'p'
0x18006ae0a  jmp     loc_18006AEB2
0x18006ae0f  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18006ae16  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18006ae1a  jz      loc_18006AED0
0x18006ae20  mov     rax, [rdi]
0x18006ae23  lea     rdx, [rsp+4D0h+var_490]
0x18006ae28  mov     rcx, rdi
0x18006ae2b  mov     rax, [rax+60h]
0x18006ae2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae34  mov     ebx, eax
0x18006ae36  test    eax, eax
0x18006ae38  jns     short loc_18006AE4E
0x18006ae3a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ae41  jb      loc_18006AED0
0x18006ae47  mov     edx, 71h ; 'q'
0x18006ae4c  jmp     short loc_18006AEB2
0x18006ae4e  mov     rax, [rsp+4D0h+var_490]
0x18006ae53  mov     rdx, r14; unsigned __int16 *
0x18006ae56  mov     r9, [r15]; HKEY
0x18006ae59  mov     rcx, rsi; unsigned __int16 *
0x18006ae5c  mov     r8, [rdi+2E0h]; struct IMFCameraProfileValidation *
0x18006ae63  mov     qword ptr [rsp+4D0h+ulFlags], rax; struct ProfileConcurrency *
0x18006ae68  call    ?MFProfileInternalParseConcurrencyProfileIds@@YAJPEBG0PEAUIMFCameraProfileValidation@@PEAUHKEY__@@PEAVProfileConcurrency@@@Z; MFProfileInternalParseConcurrencyProfileIds(ushort const *,ushort const *,IMFCameraProfileValidation *,HKEY__ *,ProfileConcurrency *)
0x18006ae6d  mov     ebx, eax
0x18006ae6f  test    eax, eax
0x18006ae71  jns     short loc_18006AE83
0x18006ae73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006ae7a  jb      short loc_18006AED0
0x18006ae7c  mov     edx, 72h ; 'r'
0x18006ae81  jmp     short loc_18006AEB2
0x18006ae83  mov     rcx, [rsp+4D0h+var_490]
0x18006ae88  lea     r8, [rsp+4D0h+pszDeviceInterface]
0x18006ae8d  lea     rdx, [rsp+4D0h+rguid]
0x18006ae92  mov     rax, [rcx]
0x18006ae95  mov     rax, [rax+38h]
0x18006ae99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ae9e  mov     ebx, eax
0x18006aea0  test    eax, eax
0x18006aea2  jns     short loc_18006AED0
0x18006aea4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006aeab  jb      short loc_18006AED0
0x18006aead  mov     edx, 73h ; 's'
0x18006aeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aeb9  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006aec0  mov     r9, rdi
0x18006aec3  mov     [rsp+4D0h+ulFlags], eax
0x18006aec7  mov     rcx, [rcx+10h]
0x18006aecb  call    WPP_SF_qD
0x18006aed0  mov     eax, ebx
0x18006aed2  mov     rcx, [rbp+3D0h+var_50]
0x18006aed9  xor     rcx, rsp; StackCookie
0x18006aedc  call    __security_check_cookie
0x18006aee1  add     rsp, 498h
0x18006aee8  pop     r15
0x18006aeea  pop     r14
0x18006aeec  pop     r13
0x18006aeee  pop     r12
0x18006aef0  pop     rdi
0x18006aef1  pop     rsi
0x18006aef2  pop     rbx
0x18006aef3  pop     rbp
0x18006aef4  retn
```
