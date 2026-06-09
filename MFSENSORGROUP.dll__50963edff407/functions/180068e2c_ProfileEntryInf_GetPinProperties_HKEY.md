# ProfileEntryInf::GetPinProperties(HKEY__ *)

- ea: `0x180068e2c`
- end: `0x18006939b`
- name: `?GetPinProperties@ProfileEntryInf@@IEAAJPEAUHKEY__@@@Z`
- size: `1391`
- prototype: `int(ProfileEntryInf *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800419a0`

## callees

- `0x180005fa0`
- `0x180044f30`
- `0x180067d90`
- `0x180068da8`
- `0x180068e2c`
- `0x180069a9c`
- `0x18006d7f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069021`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006911a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068f28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069021`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006911a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068eb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069301`

## pseudocode

```c
__int64 __fastcall ProfileEntryInf::GetPinProperties(ProfileEntryInf *this, HKEY a2)
{
  signed int v2; // ebx
  DWORD i; // esi
  LSTATUS v6; // eax
  ProfileEntryInf *v7; // rcx
  int PinId; // eax
  ProfileEntryInf *v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  ProfileEntryInf *v12; // rcx
  int v13; // ebx
  int v14; // ebx
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  for ( i = 0; ; ++i )
  {
    cchName[0] = 260;
    v6 = RegEnumKeyExW(a2, i, Name, cchName, 0, 0, 0, 0);
    if ( v6 )
    {
      if ( v6 != 259 )
      {
        v2 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, this, v2);
      }
      goto LABEL_61;
    }
    v7 = (ProfileEntryInf *)hKey;
    v16 = 0;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    PinId = ProfileEntryInf::GetPinId(v7, Name, L"PINNAME_VIDEO_PREVIEW", &v16);
    v2 = PinId;
    if ( PinId < 0 )
      break;
    if ( PinId )
    {
      PinId = ProfileEntryInf::GetPinId(v9, Name, L"PINNAME_VIDEO_CAPTURE", &v16);
      v2 = PinId;
      if ( PinId < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v11 = 84;
LABEL_44:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
          this,
          PinId);
        goto LABEL_61;
      }
      if ( PinId )
      {
        PinId = ProfileEntryInf::GetPinId(v12, Name, L"PINNAME_IMAGE", &v16);
        v2 = PinId;
        if ( PinId < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_61;
          v11 = 88;
          goto LABEL_44;
        }
        if ( PinId )
        {
          if ( (unsigned __int8)byte_18008D62F >= 0x10u )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              92,
              (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
              (_DWORD)this + 184,
              (__int64)Name);
          MFTraceValidation(
            *((_QWORD *)this + 92),
            1,
            0,
            "[profile_inf] profile %S has invalid entry %S.",
            (const wchar_t *)this + 92,
            Name);
        }
        else
        {
          v14 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &hKey);
          if ( v14 )
          {
            if ( byte_18008D62F )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                89,
                (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
                (_DWORD)this + 184,
                (__int64)Name);
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            PinId = MFTraceValidation(
                      *((_QWORD *)this + 92),
                      1,
                      (unsigned int)v14,
                      "profile %S\\%S does not have a valid OEMINF key",
                      (const wchar_t *)this + 92,
                      Name);
            v2 = PinId;
            if ( PinId < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_61;
              v11 = 90;
              goto LABEL_44;
            }
          }
          PinId = ProfileEntryInf::InfAddPin(this, hKey, 2, v16);
          v2 = PinId;
          if ( PinId < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_61;
            v11 = 91;
            goto LABEL_44;
          }
        }
      }
      else
      {
        v13 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &hKey);
        if ( v13 )
        {
          if ( byte_18008D62F )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              85,
              (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
              (_DWORD)this + 184,
              (__int64)Name);
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          PinId = MFTraceValidation(
                    *((_QWORD *)this + 92),
                    1,
                    (unsigned int)v13,
                    "profile %S\\%S does not have a valid OEMINF key",
                    (const wchar_t *)this + 92,
                    Name);
          v2 = PinId;
          if ( PinId < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_61;
            v11 = 86;
            goto LABEL_44;
          }
        }
        PinId = ProfileEntryInf::InfAddPin(this, hKey, 1, v16);
        v2 = PinId;
        if ( PinId < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_61;
          v11 = 87;
          goto LABEL_44;
        }
      }
    }
    else
    {
      v10 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &hKey);
      if ( v10 )
      {
        if ( byte_18008D62F )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            81,
            (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
            (_DWORD)this + 184,
            (__int64)Name);
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        PinId = MFTraceValidation(
                  *((_QWORD *)this + 92),
                  1,
                  (unsigned int)v10,
                  "profile %S\\%S does not have a valid OEMINF key",
                  (const wchar_t *)this + 92,
                  Name);
        v2 = PinId;
        if ( PinId < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_61;
          v11 = 82;
          goto LABEL_44;
        }
      }
      PinId = ProfileEntryInf::InfAddPin(this, hKey, 0, v16);
      v2 = PinId;
      if ( PinId < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v11 = 83;
        goto LABEL_44;
      }
    }
  }
  if ( g_wppLevels )
  {
    v11 = 80;
    goto LABEL_44;
  }
LABEL_61:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  if ( v2 < 0 )
  {
    if ( (unsigned __int8)byte_18008D62F >= 0x10u )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        94,
        (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
        (_DWORD)this + 184,
        (__int64)Name);
    MFTraceValidation(*((_QWORD *)this + 92), 1, 0, "profile %S has no preview pin.", (const wchar_t *)this + 92);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180068e2c  mov     [rsp-8+arg_10], rbx
0x180068e31  mov     [rsp-8+arg_18], rsi
0x180068e36  push    rbp
0x180068e37  push    rdi
0x180068e38  push    r12
0x180068e3a  push    r13
0x180068e3c  push    r14
0x180068e3e  lea     rbp, [rsp-180h]
0x180068e46  sub     rsp, 280h
0x180068e4d  mov     rax, cs:__security_cookie
0x180068e54  xor     rax, rsp
0x180068e57  mov     [rbp+1A0h+var_30], rax
0x180068e5e  xor     ebx, ebx
0x180068e60  mov     [rsp+2A0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180068e69  mov     r14, rdx
0x180068e6c  lea     r13, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180068e73  mov     rdi, rcx
0x180068e76  xor     esi, esi
0x180068e78  lea     r12d, [rbx+1]
0x180068e7c  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180068e85  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180068e8a  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180068e93  lea     r8, [rsp+2A0h+Name]; lpName
0x180068e98  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180068ea1  mov     edx, esi; dwIndex
0x180068ea3  mov     rcx, r14; hKey
0x180068ea6  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x180068eaf  mov     [rsp+2A0h+cchName], 104h
0x180068eb7  call    cs:__imp_RegEnumKeyExW
0x180068ebd  test    eax, eax
0x180068ebf  jnz     loc_1800692AE
0x180068ec5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180068eca  mov     [rsp+2A0h+var_260], eax
0x180068ece  lea     rax, [rcx-1]
0x180068ed2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180068ed6  ja      short loc_180068EE7
0x180068ed8  call    cs:__imp_RegCloseKey
0x180068ede  mov     [rsp+2A0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180068ee7  lea     r9, [rsp+2A0h+var_260]; unsigned int *
0x180068eec  lea     r8, aPinnameVideoPr; "PINNAME_VIDEO_PREVIEW"
0x180068ef3  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180068ef8  call    ?GetPinId@ProfileEntryInf@@IEAAJPEBG0AEAK@Z; ProfileEntryInf::GetPinId(ushort const *,ushort const *,ulong &)
0x180068efd  mov     ebx, eax
0x180068eff  test    eax, eax
0x180068f01  js      loc_18006929E
0x180068f07  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180068f0c  jnz     loc_180068FE5
0x180068f12  lea     rax, [rsp+2A0h+hKey]
0x180068f17  mov     r9d, 20019h; samDesired
0x180068f1d  xor     r8d, r8d; ulOptions
0x180068f20  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x180068f25  mov     rcx, r14; hKey
0x180068f28  call    cs:__imp_RegOpenKeyExW
0x180068f2e  mov     ebx, eax
0x180068f30  test    eax, eax
0x180068f32  jz      short loc_180068FAF
0x180068f34  cmp     cs:byte_18008D62F, r12b
0x180068f3b  jb      short loc_180068F69
0x180068f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f44  lea     rax, [rsp+2A0h+Name]
0x180068f49  lea     r9, [rdi+0B8h]
0x180068f50  mov     [rsp+2A0h+lpReserved], rax
0x180068f55  mov     edx, 51h ; 'Q'
0x180068f5a  mov     r8, r13
0x180068f5d  mov     rcx, [rcx+128h]
0x180068f64  call    WPP_SF_SS
0x180068f69  test    ebx, ebx
0x180068f6b  jle     short loc_180068F76
0x180068f6d  movzx   ebx, bx
0x180068f70  or      ebx, 80070000h
0x180068f76  lea     rcx, [rsp+2A0h+Name]
0x180068f7b  mov     r8d, ebx
0x180068f7e  mov     [rsp+2A0h+lpClass], rcx
0x180068f83  lea     rax, [rdi+0B8h]
0x180068f8a  mov     rcx, [rdi+2E0h]
0x180068f91  lea     r9, aProfileSSDoesN; "profile %S\\%S does not have a valid OE"...
0x180068f98  mov     edx, r12d
0x180068f9b  mov     [rsp+2A0h+lpReserved], rax
0x180068fa0  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180068fa5  mov     ebx, eax
0x180068fa7  test    eax, eax
0x180068fa9  js      loc_18006923F
0x180068faf  mov     r9d, [rsp+2A0h+var_260]
0x180068fb4  xor     r8d, r8d
0x180068fb7  mov     rdx, [rsp+2A0h+hKey]
0x180068fbc  mov     rcx, rdi
0x180068fbf  call    ?InfAddPin@ProfileEntryInf@@IEAAJPEAUHKEY__@@W4_KSCameraProfilePinType@@K@Z; ProfileEntryInf::InfAddPin(HKEY__ *,_KSCameraProfilePinType,ulong)
0x180068fc4  mov     ebx, eax
0x180068fc6  test    eax, eax
0x180068fc8  jns     loc_180069237
0x180068fce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180068fd5  jb      loc_1800692F2
0x180068fdb  mov     edx, 53h ; 'S'
0x180068fe0  jmp     loc_180069251
0x180068fe5  lea     r9, [rsp+2A0h+var_260]; unsigned int *
0x180068fea  lea     r8, aPinnameVideoCa; "PINNAME_VIDEO_CAPTURE"
0x180068ff1  call    ?GetPinId@ProfileEntryInf@@IEAAJPEBG0AEAK@Z; ProfileEntryInf::GetPinId(ushort const *,ushort const *,ulong &)
0x180068ff6  mov     ebx, eax
0x180068ff8  test    eax, eax
0x180068ffa  js      loc_18006928E
0x180069000  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180069005  jnz     loc_1800690DE
0x18006900b  lea     rax, [rsp+2A0h+hKey]
0x180069010  mov     r9d, 20019h; samDesired
0x180069016  xor     r8d, r8d; ulOptions
0x180069019  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x18006901e  mov     rcx, r14; hKey
0x180069021  call    cs:__imp_RegOpenKeyExW
0x180069027  mov     ebx, eax
0x180069029  test    eax, eax
0x18006902b  jz      short loc_1800690A8
0x18006902d  cmp     cs:byte_18008D62F, r12b
0x180069034  jb      short loc_180069062
0x180069036  mov     rcx, cs:WPP_GLOBAL_Control
0x18006903d  lea     rax, [rsp+2A0h+Name]
0x180069042  lea     r9, [rdi+0B8h]
0x180069049  mov     [rsp+2A0h+lpReserved], rax
0x18006904e  mov     edx, 55h ; 'U'
0x180069053  mov     r8, r13
0x180069056  mov     rcx, [rcx+128h]
0x18006905d  call    WPP_SF_SS
0x180069062  test    ebx, ebx
0x180069064  jle     short loc_18006906F
0x180069066  movzx   ebx, bx
0x180069069  or      ebx, 80070000h
0x18006906f  lea     rcx, [rsp+2A0h+Name]
0x180069074  mov     r8d, ebx
0x180069077  mov     [rsp+2A0h+lpClass], rcx
0x18006907c  lea     rax, [rdi+0B8h]
0x180069083  mov     rcx, [rdi+2E0h]
0x18006908a  lea     r9, aProfileSSDoesN; "profile %S\\%S does not have a valid OE"...
0x180069091  mov     edx, r12d
0x180069094  mov     [rsp+2A0h+lpReserved], rax
0x180069099  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006909e  mov     ebx, eax
0x1800690a0  test    eax, eax
0x1800690a2  js      loc_18006925A
0x1800690a8  mov     r9d, [rsp+2A0h+var_260]
0x1800690ad  mov     r8d, r12d
0x1800690b0  mov     rdx, [rsp+2A0h+hKey]
0x1800690b5  mov     rcx, rdi
0x1800690b8  call    ?InfAddPin@ProfileEntryInf@@IEAAJPEAUHKEY__@@W4_KSCameraProfilePinType@@K@Z; ProfileEntryInf::InfAddPin(HKEY__ *,_KSCameraProfilePinType,ulong)
0x1800690bd  mov     ebx, eax
0x1800690bf  test    eax, eax
0x1800690c1  jns     loc_180069237
0x1800690c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800690ce  jb      loc_1800692F2
0x1800690d4  mov     edx, 57h ; 'W'
0x1800690d9  jmp     loc_180069251
0x1800690de  lea     r9, [rsp+2A0h+var_260]; unsigned int *
0x1800690e3  lea     r8, aPinnameImage; "PINNAME_IMAGE"
0x1800690ea  call    ?GetPinId@ProfileEntryInf@@IEAAJPEBG0AEAK@Z; ProfileEntryInf::GetPinId(ushort const *,ushort const *,ulong &)
0x1800690ef  mov     ebx, eax
0x1800690f1  test    eax, eax
0x1800690f3  js      loc_18006927E
0x1800690f9  jnz     loc_1800691D3
0x1800690ff  lea     rax, [rsp+2A0h+hKey]
0x180069104  mov     r9d, 20019h; samDesired
0x18006910a  xor     r8d, r8d; ulOptions
0x18006910d  mov     [rsp+2A0h+lpReserved], rax; phkResult
0x180069112  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x180069117  mov     rcx, r14; hKey
0x18006911a  call    cs:__imp_RegOpenKeyExW
0x180069120  mov     ebx, eax
0x180069122  test    eax, eax
0x180069124  jz      short loc_1800691A1
0x180069126  cmp     cs:byte_18008D62F, r12b
0x18006912d  jb      short loc_18006915B
0x18006912f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069136  lea     rax, [rsp+2A0h+Name]
0x18006913b  lea     r9, [rdi+0B8h]
0x180069142  mov     [rsp+2A0h+lpReserved], rax
0x180069147  mov     edx, 59h ; 'Y'
0x18006914c  mov     r8, r13
0x18006914f  mov     rcx, [rcx+128h]
0x180069156  call    WPP_SF_SS
0x18006915b  test    ebx, ebx
0x18006915d  jle     short loc_180069168
0x18006915f  movzx   ebx, bx
0x180069162  or      ebx, 80070000h
0x180069168  lea     rcx, [rsp+2A0h+Name]
0x18006916d  mov     r8d, ebx
0x180069170  mov     [rsp+2A0h+lpClass], rcx
0x180069175  lea     rax, [rdi+0B8h]
0x18006917c  mov     rcx, [rdi+2E0h]
0x180069183  lea     r9, aProfileSSDoesN; "profile %S\\%S does not have a valid OE"...
0x18006918a  mov     edx, r12d
0x18006918d  mov     [rsp+2A0h+lpReserved], rax
0x180069192  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180069197  mov     ebx, eax
0x180069199  test    eax, eax
0x18006919b  js      loc_18006926E
0x1800691a1  mov     r9d, [rsp+2A0h+var_260]
0x1800691a6  mov     r8d, 2
0x1800691ac  mov     rdx, [rsp+2A0h+hKey]
0x1800691b1  mov     rcx, rdi
0x1800691b4  call    ?InfAddPin@ProfileEntryInf@@IEAAJPEAUHKEY__@@W4_KSCameraProfilePinType@@K@Z; ProfileEntryInf::InfAddPin(HKEY__ *,_KSCameraProfilePinType,ulong)
0x1800691b9  mov     ebx, eax
0x1800691bb  test    eax, eax
0x1800691bd  jns     short loc_180069237
0x1800691bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800691c6  jb      loc_1800692F2
0x1800691cc  mov     edx, 5Bh ; '['
0x1800691d1  jmp     short loc_180069251
0x1800691d3  cmp     cs:byte_18008D62F, 10h
0x1800691da  jb      short loc_180069208
0x1800691dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691e3  lea     rax, [rsp+2A0h+Name]
0x1800691e8  lea     r9, [rdi+0B8h]
0x1800691ef  mov     [rsp+2A0h+lpReserved], rax
0x1800691f4  mov     edx, 5Ch ; '\'
0x1800691f9  mov     r8, r13
0x1800691fc  mov     rcx, [rcx+128h]
0x180069203  call    WPP_SF_SS
0x180069208  lea     rcx, [rsp+2A0h+Name]
0x18006920d  xor     r8d, r8d
0x180069210  mov     [rsp+2A0h+lpClass], rcx
0x180069215  lea     rax, [rdi+0B8h]
0x18006921c  mov     rcx, [rdi+2E0h]
0x180069223  lea     r9, aProfileInfProf; "[profile_inf] profile %S has invalid en"...
0x18006922a  mov     edx, r12d
0x18006922d  mov     [rsp+2A0h+lpReserved], rax
0x180069232  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180069237  add     esi, r12d
0x18006923a  jmp     loc_180068E7C
0x18006923f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180069246  jb      loc_1800692F2
0x18006924c  mov     edx, 52h ; 'R'
0x180069251  mov     dword ptr [rsp+2A0h+lpReserved], eax
0x180069255  jmp     loc_1800692DC
0x18006925a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180069261  jb      loc_1800692F2
0x180069267  mov     edx, 56h ; 'V'
0x18006926c  jmp     short loc_180069251
0x18006926e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180069275  jb      short loc_1800692F2
0x180069277  mov     edx, 5Ah ; 'Z'
0x18006927c  jmp     short loc_180069251
0x18006927e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180069285  jb      short loc_1800692F2
0x180069287  mov     edx, 58h ; 'X'
0x18006928c  jmp     short loc_180069251
0x18006928e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180069295  jb      short loc_1800692F2
0x180069297  mov     edx, 54h ; 'T'
0x18006929c  jmp     short loc_180069251
0x18006929e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800692a5  jb      short loc_1800692F2
0x1800692a7  mov     edx, 50h ; 'P'
0x1800692ac  jmp     short loc_180069251
0x1800692ae  cmp     eax, 103h
0x1800692b3  jz      short loc_1800692F2
0x1800692b5  test    eax, eax
0x1800692b7  jg      short loc_1800692BD
0x1800692b9  mov     ebx, eax
0x1800692bb  jmp     short loc_1800692C6
0x1800692bd  movzx   ebx, ax
0x1800692c0  or      ebx, 80070000h
0x1800692c6  test    ebx, ebx
0x1800692c8  jns     short loc_1800692F2
0x1800692ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800692d1  jb      short loc_1800692F2
0x1800692d3  mov     edx, 5Dh ; ']'
0x1800692d8  mov     dword ptr [rsp+2A0h+lpReserved], ebx
0x1800692dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800692e3  mov     r9, rdi
0x1800692e6  mov     r8, r13
0x1800692e9  mov     rcx, [rcx+10h]
0x1800692ed  call    WPP_SF_qD
0x1800692f2  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800692f7  lea     rax, [rcx-1]
0x1800692fb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800692ff  ja      short loc_180069310
0x180069301  call    cs:__imp_RegCloseKey
0x180069307  mov     [rsp+2A0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180069310  test    ebx, ebx
0x180069312  jns     short loc_18006936E
0x180069314  cmp     cs:byte_18008D62F, 10h
0x18006931b  jb      short loc_180069349
0x18006931d  mov     rcx, cs:WPP_GLOBAL_Control
0x180069324  lea     rax, [rsp+2A0h+Name]
0x180069329  lea     r9, [rdi+0B8h]
0x180069330  mov     [rsp+2A0h+lpReserved], rax
0x180069335  mov     edx, 5Eh ; '^'
0x18006933a  mov     r8, r13
0x18006933d  mov     rcx, [rcx+128h]
0x180069344  call    WPP_SF_SS
0x180069349  mov     rcx, [rdi+2E0h]
0x180069350  lea     rax, [rdi+0B8h]
0x180069357  lea     r9, aProfileSHasNoP; "profile %S has no preview pin."
0x18006935e  mov     [rsp+2A0h+lpReserved], rax
0x180069363  xor     r8d, r8d
0x180069366  mov     edx, r12d
0x180069369  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x18006936e  mov     eax, ebx
0x180069370  mov     rcx, [rbp+1A0h+var_30]
0x180069377  xor     rcx, rsp; StackCookie
0x18006937a  call    __security_check_cookie
0x18006937f  lea     r11, [rsp+2A0h+var_20]
0x180069387  mov     rbx, [r11+40h]
  ... truncated ...
```
