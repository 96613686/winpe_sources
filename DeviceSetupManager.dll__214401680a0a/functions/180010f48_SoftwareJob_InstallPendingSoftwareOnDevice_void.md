# SoftwareJob::_InstallPendingSoftwareOnDevice(void)

- ea: `0x180010f48`
- end: `0x18001129b`
- name: `?_InstallPendingSoftwareOnDevice@SoftwareJob@@AEAAJXZ`
- size: `851`
- prototype: `__int64 __fastcall(SoftwareJob *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180034180`

## callees

- `0x180005100`
- `0x1800080f0`
- `0x18000a504`
- `0x18000e3cc`
- `0x18000ee1c`
- `0x180010b24`
- `0x180010cec`
- `0x180010f48`
- `0x1800112a4`
- `0x180011fdc`
- `0x180018240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180011196`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800111b0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800111ca`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180011196`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800111b0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800111ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011260`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011260`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001127a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001127a`

## string_xrefs

- `0x180010fe7`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x180011047`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x18001109c`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x18001110d`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
__int64 __fastcall SoftwareJob::_InstallPendingSoftwareOnDevice(SoftwareJob *this)
{
  _QWORD *v2; // rax
  const unsigned __int16 *v3; // rbx
  char *v4; // rdx
  int v5; // eax
  unsigned int DeviceStringListProperty; // edi
  char *v7; // rdx
  int DeviceObjectStringProperty; // eax
  char *v9; // rdx
  int v10; // eax
  char *v11; // rdx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r9
  int v14; // eax
  const unsigned __int16 *v15; // rcx
  __int64 i; // r14
  const wchar_t *v17; // r12
  wchar_t *v18; // rax
  wchar_t *v19; // r15
  wchar_t *v20; // rax
  const unsigned __int16 *v21; // rdi
  int v23; // [rsp+20h] [rbp-40h]
  struct tagPROPVARIANT pvar; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 *v28; // [rsp+B0h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v2 = (_QWORD *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v2 = (_QWORD *)*v2;
    WPP_SF__guid_LS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
      (_DWORD)this + 8,
      *((_DWORD *)this + 7),
      (__int64)v2);
  }
  v3 = (const unsigned __int16 *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v4 = (char *)this + 40;
  else
    v4 = *(char **)v3;
  v5 = DeleteDeviceObjectProperty(3, v4, DEVPKEY_Device_DriverSoftwareLinks);
  DeviceStringListProperty = v5;
  if ( v5 >= 0 )
  {
    v28 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v28,
      0);
    if ( *((_QWORD *)this + 8) <= 7u )
      v7 = (char *)this + 40;
    else
      v7 = *(char **)v3;
    DeviceObjectStringProperty = GetDeviceObjectStringProperty(3, v7, &DEVPKEY_Device_DriverInfPath);
    DeviceStringListProperty = DeviceObjectStringProperty;
    if ( DeviceObjectStringProperty >= 0 )
    {
      pv = 0;
      if ( *((_QWORD *)this + 8) <= 7u )
        v9 = (char *)this + 40;
      else
        v9 = *(char **)v3;
      v10 = GetDeviceObjectStringProperty(3, v9, &DEVPKEY_Device_DriverInfSection);
      DeviceStringListProperty = v10;
      if ( v10 >= 0 )
      {
        v27 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v27,
          0);
        if ( *((_QWORD *)this + 8) <= 7u )
          v11 = (char *)this + 40;
        else
          v11 = *(char **)v3;
        if ( (int)GetDeviceObjectStringProperty(3, v11, &DEVPKEY_Device_DriverInfSectionExt) < 0
          || (v14 = CCoMemString::Append((CCoMemString *)&pv, v27, v12, v13), DeviceStringListProperty = v14, v14 >= 0) )
        {
          SoftwareJob::_InstallPendingSoftwarePerInfSection(this, v28, (const unsigned __int16 *)pv);
          memset(&pvar, 0, sizeof(pvar));
          if ( *((_QWORD *)this + 8) <= 7u )
            v15 = (const unsigned __int16 *)((char *)this + 40);
          else
            v15 = *(const unsigned __int16 **)v3;
          DeviceStringListProperty = GetDeviceStringListProperty(v15, &DEVPKEY_Device_ExtendedConfigurationIds, &pvar);
          if ( (int)(DeviceStringListProperty + 0x80000000) < 0 || DeviceStringListProperty == -2147023728 )
          {
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              if ( (unsigned int)i >= pvar.lVal )
              {
                DeviceStringListProperty = *((_DWORD *)this + 32);
                goto LABEL_48;
              }
              v17 = *(const wchar_t **)&pvar.bstrblobVal.pData[8 * i];
              v18 = wcschr(v17, 0x3Au);
              if ( !v18 )
                break;
              *v18 = 0;
              v19 = v18 + 1;
              v20 = wcschr(v18 + 1, 0x2Cu);
              v21 = v20;
              if ( v20 )
              {
                v21 = v20 + 1;
                v19 = wcschr(v20 + 1, 0x2Cu);
              }
              if ( !v19 )
                break;
              *v19 = 0;
              if ( !v21 )
                break;
              SoftwareJob::_InstallPendingSoftwarePerInfSection(this, v17, v21);
            }
            DeviceStringListProperty = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( *((_QWORD *)this + 8) > 7u )
                v3 = *(const unsigned __int16 **)v3;
              WPP_SF_d_guid_LS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                37,
                (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
                -2147467259,
                (__int64)this + 8,
                *((_DWORD *)this + 7),
                (__int64)v3);
            }
          }
LABEL_48:
          PropVariantClear((PROPVARIANT *)&pvar);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x326,
            (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
            (const char *)(unsigned int)v14,
            (int)&v27);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v27);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31B,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
          (const char *)(unsigned int)v10,
          (int)&pv);
      }
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x315,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
        (const char *)(unsigned int)DeviceObjectStringProperty,
        (int)&v28);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v28);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30D,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)v5,
      v23);
  }
  return DeviceStringListProperty;
}

```

## disassembly

```asm
0x180010f48  push    rbp
0x180010f4a  push    rbx
0x180010f4b  push    rsi
0x180010f4c  push    rdi
0x180010f4d  push    r12
0x180010f4f  push    r14
0x180010f51  push    r15
0x180010f53  mov     rbp, rsp
0x180010f56  sub     rsp, 60h
0x180010f5a  mov     rsi, rcx
0x180010f5d  lea     rax, WPP_GLOBAL_Control
0x180010f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f6b  cmp     rcx, rax
0x180010f6e  jz      short loc_180010FB2
0x180010f70  test    dword ptr [rcx+1Ch], 200h
0x180010f77  jz      short loc_180010FB2
0x180010f79  cmp     byte ptr [rcx+19h], 4
0x180010f7d  jb      short loc_180010FB2
0x180010f7f  lea     rax, [rsi+28h]
0x180010f83  cmp     qword ptr [rax+18h], 7
0x180010f88  jbe     short loc_180010F8D
0x180010f8a  mov     rax, [rax]
0x180010f8d  lea     r9, [rsi+8]
0x180010f91  mov     edx, 24h ; '$'
0x180010f96  mov     [rsp+60h+var_38], rax
0x180010f9b  mov     eax, [rsi+1Ch]
0x180010f9e  mov     [rsp+60h+var_40], eax; int
0x180010fa2  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x180010fa9  mov     rcx, [rcx+10h]
0x180010fad  call    WPP_SF__guid_LS
0x180010fb2  lea     rbx, [rsi+28h]
0x180010fb6  cmp     qword ptr [rbx+18h], 7
0x180010fbb  jbe     short loc_180010FC2
0x180010fbd  mov     rdx, [rbx]
0x180010fc0  jmp     short loc_180010FC5
0x180010fc2  mov     rdx, rbx
0x180010fc5  lea     r8, DEVPKEY_Device_DriverSoftwareLinks
0x180010fcc  mov     r14d, 3
0x180010fd2  mov     ecx, r14d
0x180010fd5  call    ?DeleteDeviceObjectProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@@Z; DeleteDeviceObjectProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &)
0x180010fda  mov     edi, eax
0x180010fdc  test    eax, eax
0x180010fde  jns     short loc_180010FFD
0x180010fe0  mov     rcx, [rbp+38h]; this
0x180010fe4  mov     r9d, eax; char *
0x180010fe7  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180010fee  mov     edx, 30Dh; void *
0x180010ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ff8  jmp     loc_18001128A
0x180010ffd  mov     [rbp+arg_10], 0
0x180011005  xor     edx, edx
0x180011007  lea     rcx, [rbp+arg_10]
0x18001100b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180011010  cmp     qword ptr [rbx+18h], 7
0x180011015  jbe     short loc_18001101C
0x180011017  mov     rdx, [rbx]
0x18001101a  jmp     short loc_18001101F
0x18001101c  mov     rdx, rbx
0x18001101f  lea     rax, [rbp+arg_10]
0x180011023  mov     qword ptr [rsp+60h+var_40], rax; int
0x180011028  xor     r9d, r9d
0x18001102b  lea     r8, DEVPKEY_Device_DriverInfPath
0x180011032  mov     ecx, r14d
0x180011035  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x18001103a  mov     edi, eax
0x18001103c  test    eax, eax
0x18001103e  jns     short loc_18001105D
0x180011040  mov     rcx, [rbp+38h]; this
0x180011044  mov     r9d, eax; char *
0x180011047  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001104e  mov     edx, 315h; void *
0x180011053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011058  jmp     loc_180011281
0x18001105d  mov     [rbp+pv], 0
0x180011065  cmp     qword ptr [rbx+18h], 7
0x18001106a  jbe     short loc_180011071
0x18001106c  mov     rdx, [rbx]
0x18001106f  jmp     short loc_180011074
0x180011071  mov     rdx, rbx
0x180011074  lea     rax, [rbp+pv]
0x180011078  mov     qword ptr [rsp+60h+var_40], rax; int
0x18001107d  xor     r9d, r9d
0x180011080  lea     r8, DEVPKEY_Device_DriverInfSection
0x180011087  mov     ecx, r14d
0x18001108a  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x18001108f  mov     edi, eax
0x180011091  test    eax, eax
0x180011093  jns     short loc_1800110B2
0x180011095  mov     rcx, [rbp+38h]; this
0x180011099  mov     r9d, eax; char *
0x18001109c  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800110a3  mov     edx, 31Bh; void *
0x1800110a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110ad  jmp     loc_180011271
0x1800110b2  mov     [rbp+arg_8], 0
0x1800110ba  xor     edx, edx
0x1800110bc  lea     rcx, [rbp+arg_8]
0x1800110c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800110c5  cmp     qword ptr [rbx+18h], 7
0x1800110ca  jbe     short loc_1800110D1
0x1800110cc  mov     rdx, [rbx]
0x1800110cf  jmp     short loc_1800110D4
0x1800110d1  mov     rdx, rbx
0x1800110d4  lea     rax, [rbp+arg_8]
0x1800110d8  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800110dd  xor     r9d, r9d
0x1800110e0  lea     r8, DEVPKEY_Device_DriverInfSectionExt
0x1800110e7  mov     ecx, r14d
0x1800110ea  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x1800110ef  test    eax, eax
0x1800110f1  js      short loc_180011123
0x1800110f3  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x1800110f7  lea     rcx, [rbp+pv]; this
0x1800110fb  call    ?Append@CCoMemString@@QEAAJPEBG00@Z; CCoMemString::Append(ushort const *,ushort const *,ushort const *)
0x180011100  mov     edi, eax
0x180011102  test    eax, eax
0x180011104  jns     short loc_180011123
0x180011106  mov     rcx, [rbp+38h]; this
0x18001110a  mov     r9d, eax; char *
0x18001110d  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180011114  mov     edx, 326h; void *
0x180011119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001111e  jmp     loc_180011267
0x180011123  mov     r8, [rbp+pv]; unsigned __int16 *
0x180011127  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18001112b  mov     rcx, rsi; this
0x18001112e  call    ?_InstallPendingSoftwarePerInfSection@SoftwareJob@@AEAAXPEBG0@Z; SoftwareJob::_InstallPendingSoftwarePerInfSection(ushort const *,ushort const *)
0x180011133  xorps   xmm0, xmm0
0x180011136  xor     eax, eax
0x180011138  movups  xmmword ptr [rbp+pvar], xmm0
0x18001113c  mov     [rbp+var_10], rax
0x180011140  cmp     qword ptr [rbx+18h], 7
0x180011145  jbe     short loc_18001114C
0x180011147  mov     rcx, [rbx]
0x18001114a  jmp     short loc_18001114F
0x18001114c  mov     rcx, rbx; unsigned __int16 *
0x18001114f  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180011153  lea     rdx, DEVPKEY_Device_ExtendedConfigurationIds; struct _DEVPROPKEY *
0x18001115a  call    ?GetDeviceStringListProperty@@YAJPEBGAEBU_DEVPROPKEY@@PEAUtagPROPVARIANT@@@Z; GetDeviceStringListProperty(ushort const *,_DEVPROPKEY const &,tagPROPVARIANT *)
0x18001115f  mov     edi, eax
0x180011161  mov     eax, 80000000h
0x180011166  lea     ecx, [rdi+rax]
0x180011169  test    eax, ecx
0x18001116b  jnz     short loc_180011179
0x18001116d  cmp     edi, 80070490h
0x180011173  jnz     loc_18001125C
0x180011179  xor     r14d, r14d
0x18001117c  cmp     r14d, dword ptr [rbp+pvar+8]
0x180011180  jnb     loc_180011256
0x180011186  mov     rax, [rbp+var_10]
0x18001118a  mov     r12, [rax+r14*8]
0x18001118e  mov     edx, 3Ah ; ':'; Ch
0x180011193  mov     rcx, r12; Str
0x180011196  call    cs:__imp_wcschr
0x18001119c  test    rax, rax
0x18001119f  jz      short loc_1800111F6
0x1800111a1  xor     ecx, ecx
0x1800111a3  mov     [rax], cx
0x1800111a6  lea     r15, [rax+2]
0x1800111aa  lea     edx, [rcx+2Ch]; Ch
0x1800111ad  mov     rcx, r15; Str
0x1800111b0  call    cs:__imp_wcschr
0x1800111b6  mov     rdi, rax
0x1800111b9  test    rax, rax
0x1800111bc  jz      short loc_1800111D3
0x1800111be  add     rdi, 2
0x1800111c2  mov     edx, 2Ch ; ','; Ch
0x1800111c7  mov     rcx, rdi; Str
0x1800111ca  call    cs:__imp_wcschr
0x1800111d0  mov     r15, rax
0x1800111d3  test    r15, r15
0x1800111d6  jz      short loc_1800111F6
0x1800111d8  xor     eax, eax
0x1800111da  mov     [r15], ax
0x1800111de  test    rdi, rdi
0x1800111e1  jz      short loc_1800111F6
0x1800111e3  mov     r8, rdi; unsigned __int16 *
0x1800111e6  mov     rdx, r12; unsigned __int16 *
0x1800111e9  mov     rcx, rsi; this
0x1800111ec  call    ?_InstallPendingSoftwarePerInfSection@SoftwareJob@@AEAAXPEBG0@Z; SoftwareJob::_InstallPendingSoftwarePerInfSection(ushort const *,ushort const *)
0x1800111f1  inc     r14d
0x1800111f4  jmp     short loc_18001117C
0x1800111f6  mov     edi, 80004005h
0x1800111fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011202  lea     rax, WPP_GLOBAL_Control
0x180011209  cmp     rcx, rax
0x18001120c  jz      short loc_18001125C
0x18001120e  test    dword ptr [rcx+1Ch], 200h
0x180011215  jz      short loc_18001125C
0x180011217  cmp     byte ptr [rcx+19h], 2
0x18001121b  jb      short loc_18001125C
0x18001121d  cmp     qword ptr [rbx+18h], 7
0x180011222  jbe     short loc_180011227
0x180011224  mov     rbx, [rbx]
0x180011227  lea     r9, [rsi+8]
0x18001122b  mov     edx, 25h ; '%'
0x180011230  mov     [rsp+60h+var_30], rbx
0x180011235  mov     eax, [rsi+1Ch]
0x180011238  mov     dword ptr [rsp+60h+var_38], eax
0x18001123c  mov     qword ptr [rsp+60h+var_40], r9
0x180011241  mov     r9d, edi
0x180011244  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x18001124b  mov     rcx, [rcx+10h]
0x18001124f  call    WPP_SF_d_guid_LS
0x180011254  jmp     short loc_18001125C
0x180011256  mov     edi, [rsi+80h]
0x18001125c  lea     rcx, [rbp+pvar]; pvar
0x180011260  call    cs:__imp_PropVariantClear
0x180011266  nop
0x180011267  lea     rcx, [rbp+arg_8]
0x18001126b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180011270  nop
0x180011271  mov     rcx, [rbp+pv]; pv
0x180011275  test    rcx, rcx
0x180011278  jz      short loc_180011281
0x18001127a  call    cs:__imp_CoTaskMemFree
0x180011280  nop
0x180011281  lea     rcx, [rbp+arg_10]
0x180011285  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18001128a  mov     eax, edi
0x18001128c  add     rsp, 60h
0x180011290  pop     r15
0x180011292  pop     r14
0x180011294  pop     r12
0x180011296  pop     rdi
0x180011297  pop     rsi
0x180011298  pop     rbx
0x180011299  pop     rbp
0x18001129a  retn
```
