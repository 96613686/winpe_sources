# CDsmDeviceTree::_GetOEMDriverPath(ushort const *,ushort * *)

- ea: `0x180036cd8`
- end: `0x180036f1a`
- name: `?_GetOEMDriverPath@CDsmDeviceTree@@AEAAJPEBGPEAPEAG@Z`
- size: `578`
- prototype: `__int64 __fastcall(CDsmDeviceTree *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180002ef0`

## callees

- `0x180005100`
- `0x1800080f0`
- `0x18000e3cc`
- `0x1800112a4`
- `0x1800112c8`
- `0x180021790`
- `0x180027ba8`
- `0x180036cd8`

## import_xrefs

- `drvstore!DriverStoreGetObjectPropertyW` at `0x180036e58`
- `drvstore!DriverStoreGetObjectPropertyW` at `0x180036e58`

## string_xrefs

- `0x180036df0`: `onecoreuap\base\devices\setup\dsm\service\devicetree.cpp`
- `0x180036e66`: `onecoreuap\base\devices\setup\dsm\service\devicetree.cpp`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTree::_GetOEMDriverPath(
        CDsmDeviceTree *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int DeviceObjectStringProperty; // ebx
  const char *v6; // r9
  unsigned __int16 *v7; // r9
  int v9; // [rsp+50h] [rbp-20h] BYREF
  int v10[2]; // [rsp+58h] [rbp-18h] BYREF
  void *v11[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  CDsmDeviceTree *v13; // [rsp+A0h] [rbp+30h] BYREF
  int v14; // [rsp+B8h] [rbp+48h] BYREF

  v13 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, a2);
  v11[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v11,
    0);
  if ( (int)GetDeviceObjectStringProperty(3, (__int64)a2, (__int128 *)&DEVPKEY_Device_DriverDesc, 0) >= 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, v11[0]);
  }
  *(_QWORD *)v10 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    (void **)v10,
    0);
  DeviceObjectStringProperty = GetDeviceObjectStringProperty(
                                 3,
                                 (__int64)a2,
                                 (__int128 *)&DEVPKEY_Device_DriverInfPath,
                                 0);
  if ( DeviceObjectStringProperty == -2147023728 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, a2);
    goto LABEL_13;
  }
  if ( DeviceObjectStringProperty < 0 )
  {
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetree.cpp",
      (const char *)(unsigned int)DeviceObjectStringProperty,
      (int)v10);
    goto LABEL_28;
  }
  LOBYTE(v13) = 0;
  v14 = 0;
  v9 = 0;
  if ( (unsigned int)DriverStoreGetObjectPropertyW(
                       0,
                       2,
                       *(_QWORD *)v10,
                       &DEVPKEY_DriverPackage_Inbox,
                       &v14,
                       &v13,
                       1,
                       &v9,
                       0) )
  {
    if ( v14 == 17 && v9 == 1 )
    {
      if ( (_BYTE)v13 == 0xFF )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids);
        DeviceObjectStringProperty = -2147467259;
      }
      else
      {
        v7 = *(unsigned __int16 **)v10;
        *a3 = *(unsigned __int16 **)v10;
        *(_QWORD *)v10 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_70ed05df840b3b152097d566b29f6267_Traceguids, v7);
        DeviceObjectStringProperty = 0;
      }
    }
    else
    {
      DeviceObjectStringProperty = -2147024883;
    }
  }
  else
  {
    DeviceObjectStringProperty = wil::details::in1diag3::Return_GetLastError(
                                   retaddr,
                                   (void *)0x189,
                                   (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\devicetree.cpp",
                                   v6);
  }
LABEL_28:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)v10);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v11);
  return (unsigned int)DeviceObjectStringProperty;
}

```

## disassembly

```asm
0x180036cd8  mov     [rsp-28h+arg_8], rbx
0x180036cdd  mov     [rsp-28h+arg_0], rcx
0x180036ce2  push    rbp
0x180036ce3  push    rsi
0x180036ce4  push    rdi
0x180036ce5  push    r12
0x180036ce7  push    r13
0x180036ce9  mov     rbp, rsp
0x180036cec  sub     rsp, 70h
0x180036cf0  mov     rsi, r8
0x180036cf3  mov     rdi, rdx
0x180036cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036cfd  lea     r12, WPP_GLOBAL_Control
0x180036d04  lea     r13, WPP_70ed05df840b3b152097d566b29f6267_Traceguids
0x180036d0b  cmp     rcx, r12
0x180036d0e  jz      short loc_180036D2A
0x180036d10  test    byte ptr [rcx+1Ch], 1
0x180036d14  jz      short loc_180036D2A
0x180036d16  mov     rcx, [rcx+10h]
0x180036d1a  mov     edx, 21h ; '!'
0x180036d1f  mov     r9, rdi
0x180036d22  mov     r8, r13
0x180036d25  call    WPP_SF_S
0x180036d2a  xor     edx, edx
0x180036d2c  mov     [rbp+var_10], 0
0x180036d34  lea     rcx, [rbp+var_10]
0x180036d38  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180036d3d  xor     r9d, r9d
0x180036d40  lea     rax, [rbp+var_10]
0x180036d44  lea     r8, DEVPKEY_Device_DriverDesc
0x180036d4b  mov     qword ptr [rsp+70h+var_50], rax
0x180036d50  mov     rdx, rdi
0x180036d53  lea     ebx, [r9+3]
0x180036d57  mov     ecx, ebx
0x180036d59  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x180036d5e  test    eax, eax
0x180036d60  js      short loc_180036D87
0x180036d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d69  cmp     rcx, r12
0x180036d6c  jz      short loc_180036D87
0x180036d6e  test    byte ptr [rcx+1Ch], 1
0x180036d72  jz      short loc_180036D87
0x180036d74  mov     r9, [rbp+var_10]
0x180036d78  lea     edx, [rbx+1Fh]
0x180036d7b  mov     rcx, [rcx+10h]
0x180036d7f  mov     r8, r13
0x180036d82  call    WPP_SF_S
0x180036d87  xor     edx, edx
0x180036d89  mov     qword ptr [rbp+var_18], 0
0x180036d91  lea     rcx, [rbp+var_18]
0x180036d95  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180036d9a  lea     rax, [rbp+var_18]
0x180036d9e  xor     r9d, r9d
0x180036da1  lea     r8, DEVPKEY_Device_DriverInfPath
0x180036da8  mov     qword ptr [rsp+70h+var_50], rax; int
0x180036dad  mov     rdx, rdi
0x180036db0  mov     ecx, ebx
0x180036db2  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x180036db7  mov     ebx, eax
0x180036db9  cmp     eax, 80070490h
0x180036dbe  jnz     short loc_180036DE8
0x180036dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180036dc7  cmp     rcx, r12
0x180036dca  jz      short loc_180036DEC
0x180036dcc  test    byte ptr [rcx+1Ch], 2
0x180036dd0  jz      short loc_180036DEC
0x180036dd2  mov     rcx, [rcx+10h]
0x180036dd6  mov     edx, 23h ; '#'
0x180036ddb  mov     r9, rdi
0x180036dde  mov     r8, r13
0x180036de1  call    WPP_SF_S
0x180036de6  jmp     short loc_180036DEC
0x180036de8  test    ebx, ebx
0x180036dea  jns     short loc_180036E09
0x180036dec  mov     rcx, [rbp+28h]; this
0x180036df0  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036df7  mov     r9d, ebx; char *
0x180036dfa  mov     edx, 17Ah; void *
0x180036dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e04  jmp     loc_180036EF2
0x180036e09  mov     r8, qword ptr [rbp+var_18]
0x180036e0d  lea     rax, [rbp+var_20]
0x180036e11  mov     [rsp+70h+var_30], 0
0x180036e19  lea     r9, DEVPKEY_DriverPackage_Inbox
0x180036e20  mov     [rsp+70h+var_38], rax
0x180036e25  mov     edx, 2
0x180036e2a  lea     rax, [rbp+arg_0]
0x180036e2e  mov     [rsp+70h+var_40], 1
0x180036e36  mov     [rsp+70h+var_48], rax
0x180036e3b  xor     ecx, ecx
0x180036e3d  lea     rax, [rbp+arg_18]
0x180036e41  mov     byte ptr [rbp+arg_0], 0
0x180036e45  mov     qword ptr [rsp+70h+var_50], rax
0x180036e4a  mov     [rbp+arg_18], 0
0x180036e51  mov     [rbp+var_20], 0
0x180036e58  call    cs:__imp_DriverStoreGetObjectPropertyW
0x180036e5e  test    eax, eax
0x180036e60  jnz     short loc_180036E7B
0x180036e62  mov     rcx, [rbp+28h]; this
0x180036e66  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180036e6d  mov     edx, 189h; void *
0x180036e72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036e77  mov     ebx, eax
0x180036e79  jmp     short loc_180036EF2
0x180036e7b  cmp     [rbp+arg_18], 11h
0x180036e7f  jnz     short loc_180036EED
0x180036e81  cmp     [rbp+var_20], 1
0x180036e85  jnz     short loc_180036EED
0x180036e87  cmp     byte ptr [rbp+arg_0], 0FFh
0x180036e8b  jnz     short loc_180036EB7
0x180036e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e94  cmp     rcx, r12
0x180036e97  jz      short loc_180036EB0
0x180036e99  test    byte ptr [rcx+1Ch], 1
0x180036e9d  jz      short loc_180036EB0
0x180036e9f  mov     rcx, [rcx+10h]
0x180036ea3  mov     edx, 24h ; '$'
0x180036ea8  mov     r8, r13
0x180036eab  call    WPP_SF_
0x180036eb0  mov     ebx, 80004005h
0x180036eb5  jmp     short loc_180036EF2
0x180036eb7  mov     r9, qword ptr [rbp+var_18]
0x180036ebb  mov     [rsi], r9
0x180036ebe  mov     qword ptr [rbp+var_18], 0
0x180036ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ecd  cmp     rcx, r12
0x180036ed0  jz      short loc_180036EE9
0x180036ed2  test    byte ptr [rcx+1Ch], 1
0x180036ed6  jz      short loc_180036EE9
0x180036ed8  mov     rcx, [rcx+10h]
0x180036edc  mov     edx, 25h ; '%'
0x180036ee1  mov     r8, r13
0x180036ee4  call    WPP_SF_S
0x180036ee9  xor     ebx, ebx
0x180036eeb  jmp     short loc_180036EF2
0x180036eed  mov     ebx, 8007000Dh
0x180036ef2  lea     rcx, [rbp+var_18]
0x180036ef6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180036efb  lea     rcx, [rbp+var_10]
0x180036eff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180036f04  mov     eax, ebx
0x180036f06  mov     rbx, [rsp+70h+arg_8]
0x180036f0e  add     rsp, 70h
0x180036f12  pop     r13
0x180036f14  pop     r12
0x180036f16  pop     rdi
0x180036f17  pop     rsi
0x180036f18  pop     rbp
0x180036f19  retn
```
