# ProfileEntryInf::SetProfileId(HKEY__ *,ushort const *,_GUID const &,uint)

- ea: `0x1800419a0`
- end: `0x180041e04`
- name: `?SetProfileId@ProfileEntryInf@@UEAAJPEAUHKEY__@@PEBGAEBU_GUID@@I@Z`
- size: `1124`
- prototype: `__int64 __fastcall(ProfileEntryInf *__hidden this, HKEY hKey, const unsigned __int16 *, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180005fa0`
- `0x180015e80`
- `0x18002d02c`
- `0x1800419a0`
- `0x180041e10`
- `0x180068e2c`
- `0x18006af9c`
- `0x18006d7f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041a2d`

## pseudocode

```c
__int64 __fastcall ProfileEntryInf::SetProfileId(
        ProfileEntryInf *this,
        HKEY hKey,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned int a5)
{
  int PinProperties; // eax
  unsigned int v10; // esi
  __int64 v11; // rdx
  unsigned int v12; // r9d
  int v13; // r12d
  HKEY *v14; // r12
  bool v15; // al
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v23[22]; // [rsp+30h] [rbp-58h] BYREF

  v23[0] = 0;
  PinProperties = ProfileEntry::SetProfileId(this, a4, a5);
  v10 = PinProperties;
  if ( PinProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v11 = 95;
LABEL_67:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
        this,
        PinProperties);
      return v10;
    }
    return v10;
  }
  StringCchCopyW((unsigned __int16 *)this + 92, 0x104u, a3);
  v13 = RegOpenKeyExW(hKey, (LPCWSTR)this + 92, 0, 0x20019u, (PHKEY)this + 88);
  if ( !v13 )
  {
    v14 = (HKEY *)((char *)this + 704);
LABEL_14:
    ProfileRegReadValue(*((HKEY *)this + 88), L"Disabled", v23, v12);
    v15 = v23[0] == 0;
    *((_BYTE *)this + 176) = v23[0] == 0;
    if ( v15 )
    {
      PinProperties = ProfileEntryInf::GetPinProperties(this, *v14);
      v10 = PinProperties;
      if ( PinProperties >= 0 )
      {
        v16 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data1 )
          v16 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data4;
        if ( !v16 )
          goto LABEL_65;
        v17 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data1 )
          v17 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data4;
        if ( v17 )
        {
          v18 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data1;
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data1 )
            v18 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data4;
          if ( !v18 )
            goto LABEL_58;
          v19 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data1;
          if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data1 )
            v19 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data4;
          if ( v19 )
          {
            v20 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data1;
            if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data1 )
              v20 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data4;
            if ( v20 )
            {
              v21 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1;
              if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1 )
                v21 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data4;
              if ( !v21 && !*((_DWORD *)this + 22) && !*((_DWORD *)this + 28) )
              {
                if ( byte_18008D62F )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 37),
                    106,
                    &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
                    (char *)this + 184);
                PinProperties = MFTraceValidation(
                                  *((_QWORD *)this + 92),
                                  1,
                                  2147942487LL,
                                  "profile %S must have a preview or capture pin defined.",
                                  (const wchar_t *)this + 92);
                v10 = PinProperties;
                if ( PinProperties < 0 )
                {
                  if ( g_wppLevels )
                  {
                    v11 = 107;
                    goto LABEL_67;
                  }
                }
              }
            }
            else if ( !*((_DWORD *)this + 28) || !*((_DWORD *)this + 34) )
            {
              if ( byte_18008D62F )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  104,
                  &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
                  (char *)this + 184);
              PinProperties = MFTraceValidation(
                                *((_QWORD *)this + 92),
                                1,
                                2147942487LL,
                                "profile %S must have a capture & image pin defined.",
                                (const wchar_t *)this + 92);
              v10 = PinProperties;
              if ( PinProperties < 0 )
              {
                if ( g_wppLevels )
                {
                  v11 = 105;
                  goto LABEL_67;
                }
              }
            }
          }
          else
          {
LABEL_58:
            if ( !*((_DWORD *)this + 22) || !*((_DWORD *)this + 34) )
            {
              if ( byte_18008D62F )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 37),
                  102,
                  &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
                  (char *)this + 184);
              PinProperties = MFTraceValidation(
                                *((_QWORD *)this + 92),
                                1,
                                2147942487LL,
                                "profile %S must have a preview & image pin defined.",
                                (const wchar_t *)this + 92);
              v10 = PinProperties;
              if ( PinProperties < 0 )
              {
                if ( g_wppLevels )
                {
                  v11 = 103;
                  goto LABEL_67;
                }
              }
            }
          }
        }
        else
        {
LABEL_65:
          if ( !*((_DWORD *)this + 22) || !*((_DWORD *)this + 28) )
          {
            if ( byte_18008D62F )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 37),
                100,
                &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
                (char *)this + 184);
            PinProperties = MFTraceValidation(
                              *((_QWORD *)this + 92),
                              1,
                              2147942487LL,
                              "profile %S must have a preview & capture pin defined.",
                              (const wchar_t *)this + 92);
            v10 = PinProperties;
            if ( PinProperties < 0 )
            {
              if ( g_wppLevels )
              {
                v11 = 101;
                goto LABEL_67;
              }
            }
          }
        }
      }
      else if ( g_wppLevels )
      {
        v11 = 99;
        goto LABEL_67;
      }
    }
    else
    {
      if ( (unsigned __int8)byte_18008D62F >= 0x10u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          98,
          &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
          (char *)this + 184);
      MFTraceValidation(*((_QWORD *)this + 92), 1, 0, "profile %S is marked as disabled", (const wchar_t *)this + 92);
    }
    return v10;
  }
  if ( byte_18008D62F )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      96,
      &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
      (char *)this + 184);
  if ( v13 > 0 )
    v13 = (unsigned __int16)v13 | 0x80070000;
  PinProperties = MFTraceValidation(
                    *((_QWORD *)this + 92),
                    1,
                    (unsigned int)v13,
                    "profile %S does not have a valid OEMINF key",
                    (const wchar_t *)this + 92);
  v10 = PinProperties;
  if ( PinProperties >= 0 )
  {
    v14 = (HKEY *)((char *)this + 704);
    goto LABEL_14;
  }
  if ( g_wppLevels )
  {
    v11 = 97;
    goto LABEL_67;
  }
  return v10;
}

```

## disassembly

```asm
0x1800419a0  push    rbx
0x1800419a2  push    rbp
0x1800419a3  push    rsi
0x1800419a4  push    rdi
0x1800419a5  push    r12
0x1800419a7  push    r13
0x1800419a9  push    r14
0x1800419ab  push    r15
0x1800419ad  sub     rsp, 48h
0x1800419b1  mov     rbx, r8
0x1800419b4  mov     [rsp+88h+var_58], 0
0x1800419bc  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1800419c4  mov     rbp, rdx
0x1800419c7  mov     rdx, r9; struct _GUID *
0x1800419ca  mov     r14, r9
0x1800419cd  mov     rdi, rcx
0x1800419d0  call    ?SetProfileId@ProfileEntry@@UEAAJAEBU_GUID@@I@Z; ProfileEntry::SetProfileId(_GUID const &,uint)
0x1800419d5  mov     esi, eax
0x1800419d7  test    eax, eax
0x1800419d9  jns     short loc_1800419FB
0x1800419db  mov     ebx, 1
0x1800419e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800419e6  jb      loc_180041DF1
0x1800419ec  lea     edx, [rbx+5Eh]
0x1800419ef  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x1800419f6  jmp     loc_180041DDA
0x1800419fb  lea     r15, [rdi+0B8h]
0x180041a02  mov     r8, rbx; unsigned __int16 *
0x180041a05  mov     rcx, r15; unsigned __int16 *
0x180041a08  mov     edx, 104h; unsigned __int64
0x180041a0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041a12  lea     r13, [rdi+2C0h]
0x180041a19  mov     r9d, 20019h; samDesired
0x180041a1f  xor     r8d, r8d; ulOptions
0x180041a22  mov     [rsp+88h+phkResult], r13; phkResult
0x180041a27  mov     rdx, r15; lpSubKey
0x180041a2a  mov     rcx, rbp; hKey
0x180041a2d  call    cs:__imp_RegOpenKeyExW
0x180041a33  mov     ebx, 1
0x180041a38  lea     rbp, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180041a3f  mov     r12d, eax
0x180041a42  test    eax, eax
0x180041a44  jz      short loc_180041ABC
0x180041a46  cmp     cs:byte_18008D62F, bl
0x180041a4c  jb      short loc_180041A6A
0x180041a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a55  lea     edx, [rbx+5Fh]
0x180041a58  mov     r9, r15
0x180041a5b  mov     r8, rbp
0x180041a5e  mov     rcx, [rcx+128h]
0x180041a65  call    WPP_SF_S
0x180041a6a  test    r12d, r12d
0x180041a6d  jle     short loc_180041A7A
0x180041a6f  movzx   r12d, r12w
0x180041a73  or      r12d, 80070000h
0x180041a7a  mov     rcx, [rdi+2E0h]
0x180041a81  lea     r9, aProfileSDoesNo; "profile %S does not have a valid OEMINF"...
0x180041a88  mov     r8d, r12d
0x180041a8b  mov     [rsp+88h+phkResult], r15
0x180041a90  mov     edx, ebx
0x180041a92  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041a97  mov     esi, eax
0x180041a99  test    eax, eax
0x180041a9b  jns     short loc_180041AB3
0x180041a9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041aa3  jb      loc_180041DF1
0x180041aa9  mov     edx, 61h ; 'a'
0x180041aae  jmp     loc_180041DD7
0x180041ab3  lea     r12, [rdi+2C0h]
0x180041aba  jmp     short loc_180041ABF
0x180041abc  mov     r12, r13
0x180041abf  mov     rcx, [r13+0]; HKEY
0x180041ac3  lea     r8, [rsp+88h+var_58]; unsigned int *
0x180041ac8  lea     rdx, aDisabled; "Disabled"
0x180041acf  call    ?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAKK@Z; ProfileRegReadValue(HKEY__ *,ushort const *,ulong *,ulong)
0x180041ad4  cmp     [rsp+88h+var_58], 0
0x180041ad9  setz    al
0x180041adc  mov     [rdi+0B0h], al
0x180041ae2  test    al, al
0x180041ae4  jnz     short loc_180041B2F
0x180041ae6  cmp     cs:byte_18008D62F, 10h
0x180041aed  jb      short loc_180041B0D
0x180041aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180041af6  mov     edx, 62h ; 'b'
0x180041afb  mov     r9, r15
0x180041afe  mov     r8, rbp
0x180041b01  mov     rcx, [rcx+128h]
0x180041b08  call    WPP_SF_S
0x180041b0d  mov     rcx, [rdi+2E0h]
0x180041b14  lea     r9, aProfileSIsMark; "profile %S is marked as disabled"
0x180041b1b  xor     r8d, r8d
0x180041b1e  mov     [rsp+88h+phkResult], r15
0x180041b23  mov     edx, ebx
0x180041b25  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041b2a  jmp     loc_180041DF1
0x180041b2f  mov     rdx, [r12]; HKEY
0x180041b33  mov     rcx, rdi; this
0x180041b36  call    ?GetPinProperties@ProfileEntryInf@@IEAAJPEAUHKEY__@@@Z; ProfileEntryInf::GetPinProperties(HKEY__ *)
0x180041b3b  mov     esi, eax
0x180041b3d  test    eax, eax
0x180041b3f  jns     short loc_180041B57
0x180041b41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041b47  jb      loc_180041DF1
0x180041b4d  mov     edx, 63h ; 'c'
0x180041b52  jmp     loc_180041DD7
0x180041b57  mov     rax, [r14]
0x180041b5a  sub     rax, qword ptr cs:_GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data1
0x180041b61  jnz     short loc_180041B6E
0x180041b63  mov     rax, [r14+8]
0x180041b67  sub     rax, qword ptr cs:_GUID_a0e517e8_8f8c_4f6f_9a57_46fc2f647ec0.Data4
0x180041b6e  test    rax, rax
0x180041b71  jz      loc_180041D74
0x180041b77  mov     rax, [r14]
0x180041b7a  sub     rax, qword ptr cs:_GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data1
0x180041b81  jnz     short loc_180041B8E
0x180041b83  mov     rax, [r14+8]
0x180041b87  sub     rax, qword ptr cs:_GUID_c5444a88_e1bf_4597_b2dd_9e1ead864bb8.Data4
0x180041b8e  test    rax, rax
0x180041b91  jz      loc_180041D74
0x180041b97  mov     rax, [r14]
0x180041b9a  sub     rax, qword ptr cs:_GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data1
0x180041ba1  jnz     short loc_180041BAE
0x180041ba3  mov     rax, [r14+8]
0x180041ba7  sub     rax, qword ptr cs:_GUID_32440725_961b_4ca3_b5b2_854e719d9e1b.Data4
0x180041bae  test    rax, rax
0x180041bb1  jz      loc_180041D00
0x180041bb7  mov     rax, [r14]
0x180041bba  sub     rax, qword ptr cs:_GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data1
0x180041bc1  jnz     short loc_180041BCE
0x180041bc3  mov     rax, [r14+8]
0x180041bc7  sub     rax, qword ptr cs:_GUID_02399d9d_4ee8_49ba_bc07_5ff156531413.Data4
0x180041bce  test    rax, rax
0x180041bd1  jz      loc_180041D00
0x180041bd7  mov     rax, [r14]
0x180041bda  sub     rax, qword ptr cs:_GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data1
0x180041be1  jnz     short loc_180041BEE
0x180041be3  mov     rax, [r14+8]
0x180041be7  sub     rax, qword ptr cs:_GUID_6b52b017_42c7_4a21_bfe3_23f009149887.Data4
0x180041bee  test    rax, rax
0x180041bf1  jnz     short loc_180041C6A
0x180041bf3  cmp     [rdi+70h], ebx
0x180041bf6  jb      short loc_180041C04
0x180041bf8  cmp     [rdi+88h], ebx
0x180041bfe  jnb     loc_180041DF1
0x180041c04  cmp     cs:byte_18008D62F, bl
0x180041c0a  jb      short loc_180041C2A
0x180041c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c13  mov     edx, 68h ; 'h'
0x180041c18  mov     r9, r15
0x180041c1b  mov     r8, rbp
0x180041c1e  mov     rcx, [rcx+128h]
0x180041c25  call    WPP_SF_S
0x180041c2a  mov     rcx, [rdi+2E0h]
0x180041c31  lea     r9, aProfileSMustHa_2; "profile %S must have a capture & image "...
0x180041c38  mov     r8d, 80070057h
0x180041c3e  mov     [rsp+88h+phkResult], r15
0x180041c43  mov     edx, ebx
0x180041c45  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041c4a  mov     esi, eax
0x180041c4c  test    eax, eax
0x180041c4e  jns     loc_180041DF1
0x180041c54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041c5a  jb      loc_180041DF1
0x180041c60  mov     edx, 69h ; 'i'
0x180041c65  jmp     loc_180041DD7
0x180041c6a  mov     rax, [r14]
0x180041c6d  sub     rax, qword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1
0x180041c74  jnz     short loc_180041C81
0x180041c76  mov     rax, [r14+8]
0x180041c7a  sub     rax, qword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data4
0x180041c81  test    rax, rax
0x180041c84  jnz     loc_180041DF1
0x180041c8a  cmp     [rdi+58h], ebx
0x180041c8d  jnb     loc_180041DF1
0x180041c93  cmp     [rdi+70h], ebx
0x180041c96  jnb     loc_180041DF1
0x180041c9c  cmp     cs:byte_18008D62F, bl
0x180041ca2  jb      short loc_180041CC0
0x180041ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x180041cab  lea     edx, [rax+6Ah]
0x180041cae  mov     r9, r15
0x180041cb1  mov     r8, rbp
0x180041cb4  mov     rcx, [rcx+128h]
0x180041cbb  call    WPP_SF_S
0x180041cc0  mov     rcx, [rdi+2E0h]
0x180041cc7  lea     r9, aProfileSMustHa_1; "profile %S must have a preview or captu"...
0x180041cce  mov     r8d, 80070057h
0x180041cd4  mov     [rsp+88h+phkResult], r15
0x180041cd9  mov     edx, ebx
0x180041cdb  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041ce0  mov     esi, eax
0x180041ce2  test    eax, eax
0x180041ce4  jns     loc_180041DF1
0x180041cea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041cf0  jb      loc_180041DF1
0x180041cf6  mov     edx, 6Bh ; 'k'
0x180041cfb  jmp     loc_180041DD7
0x180041d00  cmp     [rdi+58h], ebx
0x180041d03  jb      short loc_180041D11
0x180041d05  cmp     [rdi+88h], ebx
0x180041d0b  jnb     loc_180041DF1
0x180041d11  cmp     cs:byte_18008D62F, bl
0x180041d17  jb      short loc_180041D37
0x180041d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d20  mov     edx, 66h ; 'f'
0x180041d25  mov     r9, r15
0x180041d28  mov     r8, rbp
0x180041d2b  mov     rcx, [rcx+128h]
0x180041d32  call    WPP_SF_S
0x180041d37  mov     rcx, [rdi+2E0h]
0x180041d3e  lea     r9, aProfileSMustHa_0; "profile %S must have a preview & image "...
0x180041d45  mov     r8d, 80070057h
0x180041d4b  mov     [rsp+88h+phkResult], r15
0x180041d50  mov     edx, ebx
0x180041d52  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041d57  mov     esi, eax
0x180041d59  test    eax, eax
0x180041d5b  jns     loc_180041DF1
0x180041d61  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041d67  jb      loc_180041DF1
0x180041d6d  mov     edx, 67h ; 'g'
0x180041d72  jmp     short loc_180041DD7
0x180041d74  cmp     [rdi+58h], ebx
0x180041d77  jb      short loc_180041D7E
0x180041d79  cmp     [rdi+70h], ebx
0x180041d7c  jnb     short loc_180041DF1
0x180041d7e  cmp     cs:byte_18008D62F, bl
0x180041d84  jb      short loc_180041DA4
0x180041d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d8d  mov     edx, 64h ; 'd'
0x180041d92  mov     r9, r15
0x180041d95  mov     r8, rbp
0x180041d98  mov     rcx, [rcx+128h]
0x180041d9f  call    WPP_SF_S
0x180041da4  mov     rcx, [rdi+2E0h]
0x180041dab  lea     r9, aProfileSMustHa; "profile %S must have a preview & captur"...
0x180041db2  mov     r8d, 80070057h
0x180041db8  mov     [rsp+88h+phkResult], r15
0x180041dbd  mov     edx, ebx
0x180041dbf  call    ?MFTraceValidation@@YAJPEAUIMFCameraProfileValidation@@W4MF_CAMERA_PROFILE_VALIDATIONSTATE@@JPEBDZZ; MFTraceValidation(IMFCameraProfileValidation *,MF_CAMERA_PROFILE_VALIDATIONSTATE,long,char const *,...)
0x180041dc4  mov     esi, eax
0x180041dc6  test    eax, eax
0x180041dc8  jns     short loc_180041DF1
0x180041dca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180041dd0  jb      short loc_180041DF1
0x180041dd2  mov     edx, 65h ; 'e'
0x180041dd7  mov     r8, rbp
0x180041dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180041de1  mov     r9, rdi
0x180041de4  mov     dword ptr [rsp+88h+phkResult], eax
0x180041de8  mov     rcx, [rcx+10h]
0x180041dec  call    WPP_SF_qD
0x180041df1  mov     eax, esi
0x180041df3  add     rsp, 48h
0x180041df7  pop     r15
0x180041df9  pop     r14
0x180041dfb  pop     r13
0x180041dfd  pop     r12
0x180041dff  pop     rdi
0x180041e00  pop     rsi
0x180041e01  pop     rbp
0x180041e02  pop     rbx
0x180041e03  retn
```
