# SystemSettings::WorkAccess::CAreasManagedHeader::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x1800339a0`
- end: `0x180033c63`
- name: `?GetProperty@CAreasManagedHeader@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `707`
- prototype: `int(SystemSettings::WorkAccess::CAreasManagedHeader *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180011a14`
- `0x180015000`
- `0x18001ce98`
- `0x180020584`
- `0x1800339a0`
- `0x1800476b8`
- `0x18004862c`

## string_xrefs

- `0x1800339e2`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033a4d`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033aab`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033af1`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180033c46`: `https://docs.microsoft.com/en-us/windows/client-management/mdm/dynamicmanagement-csp`

## pseudocode

```c
int __fastcall SystemSettings::WorkAccess::CAreasManagedHeader::GetProperty(
        SystemSettings::WorkAccess::CAreasManagedHeader *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v5; // r8
  int OmadmValue; // ebx
  __int64 v7; // rdx
  int v9; // eax
  unsigned __int16 **v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  unsigned __int16 *v16; // [rsp+20h] [rbp-38h] BYREF
  __int64 v17; // [rsp+28h] [rbp-30h]
  __int64 v18; // [rsp+30h] [rbp-28h]
  unsigned __int16 *v19; // [rsp+38h] [rbp-20h] BYREF
  __int64 v20; // [rsp+40h] [rbp-18h]
  __int64 v21; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005D738, (const unsigned __int16 *)a3) )
  {
    OmadmValue = SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs();
    if ( OmadmValue < 0 )
    {
      v7 = 1211;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
        (const char *)(unsigned int)OmadmValue,
        (int)v16);
      return OmadmValue;
    }
    OmadmValue = SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(4u);
    if ( OmadmValue < 0 )
    {
      v7 = 1212;
      goto LABEL_4;
    }
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value && *SystemSettings::WorkAccess::CEnrollmentHelper::_value )
    {
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
             &v16,
             &_ImageBase,
             107);
      OmadmValue = v9;
      if ( v9 >= 0 )
        OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(v16, a3);
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4CF,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
          (const char *)(unsigned int)v9,
          (int)v16);
      v10 = &v16;
      goto LABEL_23;
    }
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v19,
            &_ImageBase,
            109);
    OmadmValue = v11;
    if ( v11 < 0 )
    {
      v12 = 1218;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
        (const char *)(unsigned int)v11,
        (int)v16);
LABEL_22:
      v10 = &v19;
LABEL_23:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v10);
      return OmadmValue;
    }
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v16,
            &_ImageBase,
            107);
    OmadmValue = v13;
    if ( v13 < 0 )
    {
      v14 = 1223;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
        (const char *)(unsigned int)v13,
        (int)v16);
LABEL_21:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v16);
      goto LABEL_22;
    }
    goto LABEL_20;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005D760, v5) )
  {
    OmadmValue = SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs();
    if ( OmadmValue < 0 )
    {
      v7 = 1237;
      goto LABEL_4;
    }
    OmadmValue = SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(4u);
    if ( OmadmValue < 0 )
    {
      v7 = 1238;
      goto LABEL_4;
    }
    if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value && *SystemSettings::WorkAccess::CEnrollmentHelper::_value )
    {
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              &v19,
              &_ImageBase,
              108);
      OmadmValue = v11;
      if ( v11 >= 0 )
      {
        OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(v19, a3);
        goto LABEL_22;
      }
      v12 = 1256;
      goto LABEL_16;
    }
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v19,
            &_ImageBase,
            109);
    OmadmValue = v11;
    if ( v11 < 0 )
    {
      v12 = 1243;
      goto LABEL_16;
    }
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            &v16,
            &_ImageBase,
            108);
    OmadmValue = v13;
    if ( v13 < 0 )
    {
      v14 = 1248;
      goto LABEL_19;
    }
LABEL_20:
    OmadmValue = SystemSettings::DataModel::PropValueHelper::CreateString(v16, a3);
    goto LABEL_21;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005D518, v15) )
    return SystemSettings::DataModel::PropValueHelper::CreateString(
             L"https://docs.microsoft.com/en-us/windows/client-management/mdm/dynamicmanagement-csp",
             a3);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x1800339a0  push    rbp
0x1800339a2  push    rbx
0x1800339a3  push    rsi
0x1800339a4  push    rdi
0x1800339a5  mov     rbp, rsp
0x1800339a8  sub     rsp, 58h
0x1800339ac  mov     rbx, rdx
0x1800339af  xor     esi, esi
0x1800339b1  mov     rcx, rbx; this
0x1800339b4  mov     [r8], rsi
0x1800339b7  lea     rdx, stru_18005D738; HSTRING
0x1800339be  mov     rdi, r8
0x1800339c1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800339c6  test    al, al
0x1800339c8  jz      loc_180033B27
0x1800339ce  call    ?PopulateIDs@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ; SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)
0x1800339d3  mov     ebx, eax
0x1800339d5  test    eax, eax
0x1800339d7  jns     short loc_1800339F8
0x1800339d9  mov     edx, 4BBh; void *
0x1800339de  mov     rcx, [rbp+20h]; this
0x1800339e2  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x1800339e9  mov     r9d, ebx; char *
0x1800339ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339f1  mov     eax, ebx
0x1800339f3  jmp     loc_180033C59
0x1800339f8  mov     ecx, 4; unsigned int
0x1800339fd  call    ?GetOmadmValue@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJK@Z; SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(ulong)
0x180033a02  mov     ebx, eax
0x180033a04  test    eax, eax
0x180033a06  jns     short loc_180033A0F
0x180033a08  mov     edx, 4BCh
0x180033a0d  jmp     short loc_1800339DE
0x180033a0f  mov     r9, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180033a16  test    r9, r9
0x180033a19  jz      short loc_180033A7A
0x180033a1b  cmp     si, [r9]
0x180033a1f  jz      short loc_180033A7A
0x180033a21  mov     r8d, 6Bh ; 'k'
0x180033a27  mov     [rbp+var_38], rsi
0x180033a2b  lea     rdx, __ImageBase
0x180033a32  mov     [rbp+var_30], rsi
0x180033a36  lea     rcx, [rbp+var_38]
0x180033a3a  mov     [rbp+var_28], rsi
0x180033a3e  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033a43  mov     ebx, eax
0x180033a45  test    eax, eax
0x180033a47  jns     short loc_180033A63
0x180033a49  mov     rcx, [rbp+20h]; this
0x180033a4d  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033a54  mov     r9d, eax; char *
0x180033a57  mov     edx, 4CFh; void *
0x180033a5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a61  jmp     short loc_180033A71
0x180033a63  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180033a67  mov     rdx, rdi; struct IInspectable **
0x180033a6a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180033a6f  mov     ebx, eax
0x180033a71  lea     rcx, [rbp+var_38]
0x180033a75  jmp     loc_180033B1D
0x180033a7a  mov     r8d, 6Dh ; 'm'
0x180033a80  mov     [rbp+var_20], rsi
0x180033a84  lea     rdx, __ImageBase
0x180033a8b  mov     [rbp+var_18], rsi
0x180033a8f  lea     rcx, [rbp+var_20]
0x180033a93  mov     [rbp+var_10], rsi
0x180033a97  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033a9c  mov     ebx, eax
0x180033a9e  test    eax, eax
0x180033aa0  jns     short loc_180033ABC
0x180033aa2  mov     edx, 4C2h; void *
0x180033aa7  mov     rcx, [rbp+20h]; this
0x180033aab  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033ab2  mov     r9d, eax; char *
0x180033ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033aba  jmp     short loc_180033B19
0x180033abc  mov     r9, [rbp+var_20]
0x180033ac0  lea     rdx, __ImageBase
0x180033ac7  mov     r8d, 6Bh ; 'k'
0x180033acd  mov     [rbp+var_38], rsi
0x180033ad1  lea     rcx, [rbp+var_38]
0x180033ad5  mov     [rbp+var_30], rsi
0x180033ad9  mov     [rbp+var_28], rsi
0x180033add  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033ae2  mov     ebx, eax
0x180033ae4  test    eax, eax
0x180033ae6  jns     short loc_180033B02
0x180033ae8  mov     edx, 4C7h; void *
0x180033aed  mov     rcx, [rbp+20h]; this
0x180033af1  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180033af8  mov     r9d, eax; char *
0x180033afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b00  jmp     short loc_180033B10
0x180033b02  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180033b06  mov     rdx, rdi; struct IInspectable **
0x180033b09  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180033b0e  mov     ebx, eax
0x180033b10  lea     rcx, [rbp+var_38]
0x180033b14  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180033b19  lea     rcx, [rbp+var_20]
0x180033b1d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180033b22  jmp     loc_1800339F1
0x180033b27  lea     rdx, stru_18005D760; HSTRING
0x180033b2e  mov     rcx, rbx; this
0x180033b31  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180033b36  test    al, al
0x180033b38  jz      loc_180033C30
0x180033b3e  call    ?PopulateIDs@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJXZ; SystemSettings::WorkAccess::CEnrollmentHelper::PopulateIDs(void)
0x180033b43  mov     ebx, eax
0x180033b45  test    eax, eax
0x180033b47  jns     short loc_180033B53
0x180033b49  mov     edx, 4D5h
0x180033b4e  jmp     loc_1800339DE
0x180033b53  mov     ecx, 4; unsigned int
0x180033b58  call    ?GetOmadmValue@CEnrollmentHelper@WorkAccess@SystemSettings@@SAJK@Z; SystemSettings::WorkAccess::CEnrollmentHelper::GetOmadmValue(ulong)
0x180033b5d  mov     ebx, eax
0x180033b5f  test    eax, eax
0x180033b61  jns     short loc_180033B6D
0x180033b63  mov     edx, 4D6h
0x180033b68  jmp     loc_1800339DE
0x180033b6d  mov     r9, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180033b74  test    r9, r9
0x180033b77  jz      short loc_180033BC4
0x180033b79  cmp     si, [r9]
0x180033b7d  jz      short loc_180033BC4
0x180033b7f  mov     r8d, 6Ch ; 'l'
0x180033b85  mov     [rbp+var_20], rsi
0x180033b89  lea     rdx, __ImageBase
0x180033b90  mov     [rbp+var_18], rsi
0x180033b94  lea     rcx, [rbp+var_20]
0x180033b98  mov     [rbp+var_10], rsi
0x180033b9c  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033ba1  mov     ebx, eax
0x180033ba3  test    eax, eax
0x180033ba5  jns     short loc_180033BB1
0x180033ba7  mov     edx, 4E8h
0x180033bac  jmp     loc_180033AA7
0x180033bb1  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180033bb5  mov     rdx, rdi; struct IInspectable **
0x180033bb8  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180033bbd  mov     ebx, eax
0x180033bbf  jmp     loc_180033B19
0x180033bc4  mov     r8d, 6Dh ; 'm'
0x180033bca  mov     [rbp+var_20], rsi
0x180033bce  lea     rdx, __ImageBase
0x180033bd5  mov     [rbp+var_18], rsi
0x180033bd9  lea     rcx, [rbp+var_20]
0x180033bdd  mov     [rbp+var_10], rsi
0x180033be1  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033be6  mov     ebx, eax
0x180033be8  test    eax, eax
0x180033bea  jns     short loc_180033BF6
0x180033bec  mov     edx, 4DBh
0x180033bf1  jmp     loc_180033AA7
0x180033bf6  mov     r9, [rbp+var_20]
0x180033bfa  lea     rdx, __ImageBase
0x180033c01  mov     r8d, 6Ch ; 'l'
0x180033c07  mov     [rbp+var_38], rsi
0x180033c0b  lea     rcx, [rbp+var_38]
0x180033c0f  mov     [rbp+var_30], rsi
0x180033c13  mov     [rbp+var_28], rsi
0x180033c17  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180033c1c  mov     ebx, eax
0x180033c1e  test    eax, eax
0x180033c20  jns     loc_180033B02
0x180033c26  mov     edx, 4E0h
0x180033c2b  jmp     loc_180033AED
0x180033c30  lea     rdx, stru_18005D518; HSTRING
0x180033c37  mov     rcx, rbx; this
0x180033c3a  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180033c3f  test    al, al
0x180033c41  jz      short loc_180033C54
0x180033c43  mov     rdx, rdi; struct IInspectable **
0x180033c46  lea     rcx, aHttpsDocsMicro; "https://docs.microsoft.com/en-us/window"...
0x180033c4d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180033c52  jmp     short loc_180033C59
0x180033c54  mov     eax, 80070057h
0x180033c59  add     rsp, 58h
0x180033c5d  pop     rdi
0x180033c5e  pop     rsi
0x180033c5f  pop     rbx
0x180033c60  pop     rbp
0x180033c61  retn
```
