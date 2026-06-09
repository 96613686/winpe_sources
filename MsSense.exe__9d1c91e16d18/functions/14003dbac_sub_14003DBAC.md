# sub_14003DBAC

- ea: `0x14003dbac`
- end: `0x14003e017`
- name: `sub_14003DBAC`
- size: `1131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x14003792c`

## callees

- `0x140001158`
- `0x140018340`
- `0x140034998`
- `0x14003dbac`
- `0x14003e1bc`
- `0x14003ed20`
- `0x140051ba0`
- `0x14006c4a0`
- `0x1400802f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003dc23`
- `KERNEL32!GetLastError` at `0x14003dc53`
- `KERNEL32!GetLastError` at `0x14003ddfd`
- `KERNEL32!GetLastError` at `0x14003de9d`
- `KERNEL32!GetLastError` at `0x14003df16`
- `KERNEL32!GetLastError` at `0x14003df67`
- `KERNEL32!GetLastError` at `0x14003dc23`
- `KERNEL32!GetLastError` at `0x14003dc53`
- `KERNEL32!GetLastError` at `0x14003ddfd`
- `KERNEL32!GetLastError` at `0x14003de9d`
- `KERNEL32!GetLastError` at `0x14003df16`
- `KERNEL32!GetLastError` at `0x14003df67`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x14003dd1c`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x14003dd1c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dca4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dfc2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dfd9`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dca4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dfc2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14003dfd9`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x14003dda7`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x14003dda7`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x14003dc08`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x14003dc08`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x14003dd5c`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x14003dd5c`

## string_xrefs

- `0x14003de07`: `GetRemovableMediaDevicePath failed`
- `0x14003dea7`: `FindSerialIdForTargetPath() failed`

## pseudocode

```c
__int64 __fastcall sub_14003DBAC(DWORD a1, _BYTE *a2)
{
  int v3; // r13d
  char *ClassDevsW; // rbx
  signed int v5; // eax
  unsigned int v6; // edi
  _DWORD *v7; // rsi
  char v9; // si
  DWORD i; // r12d
  DWORD v11; // r14d
  int v12; // r15d
  _DWORD *v13; // r13
  int v14; // esi
  _DWORD *Ptr; // r15
  signed int v16; // eax
  unsigned int v17; // edi
  _DWORD *v18; // rsi
  _BYTE v19[4]; // [rsp+40h] [rbp-8C8h] BYREF
  DWORD v20; // [rsp+44h] [rbp-8C4h] BYREF
  DWORD LastError; // [rsp+48h] [rbp-8C0h] BYREF
  _DWORD v22[3]; // [rsp+4Ch] [rbp-8BCh] BYREF
  __int64 v23; // [rsp+58h] [rbp-8B0h] BYREF
  __int64 v24[2]; // [rsp+60h] [rbp-8A8h] BYREF
  DWORD RequiredSize; // [rsp+70h] [rbp-898h] BYREF
  DWORD PropertyRegDataType; // [rsp+74h] [rbp-894h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+78h] [rbp-890h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-870h] BYREF
  _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+A8h] [rbp-860h] BYREF
  BYTE PropertyBuffer[2048]; // [rsp+D0h] [rbp-838h] BYREF

  v3 = a1;
  v20 = a1;
  if ( a2[16] )
  {
    unknown_libname_18(a2);
    a2[16] = 0;
  }
  ClassDevsW = (char *)SetupDiGetClassDevsW(&InterfaceClassGuid, 0, 0, 0x12u);
  v24[1] = (__int64)ClassDevsW;
  if ( (unsigned __int64)(ClassDevsW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
    DeviceInterfaceData.cbSize = 32;
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    sub_1400802F0(PropertyBuffer, 0, 2048);
    RequiredSize = 0;
    PropertyRegDataType = 0;
    v9 = 0;
    v19[0] = 0;
    for ( i = 0; SetupDiEnumDeviceInfo(ClassDevsW, i, &DeviceInfoData); ++i )
    {
      SetupDiGetDeviceRegistryPropertyW(
        ClassDevsW,
        &DeviceInfoData,
        0x16u,
        &PropertyRegDataType,
        PropertyBuffer,
        0x400u,
        &RequiredSize);
      if ( !(unsigned int)sub_14006C4A0(PropertyBuffer, L"USBSTOR") )
      {
        v11 = 0;
        while ( SetupDiEnumDeviceInterfaces(ClassDevsW, &DeviceInfoData, &InterfaceClassGuid, v11, &DeviceInterfaceData) )
        {
          DestinationString = 0;
          v12 = sub_14003ED20(ClassDevsW, &DeviceInterfaceData, &DestinationString);
          if ( v12 >= 0 )
          {
            _mm_lfence();
            v14 = sub_14003E1BC(
                    (__int64)ClassDevsW,
                    (__int64)&DeviceInfoData,
                    (__int64)&DestinationString,
                    v3,
                    (__int64)a2,
                    (__int64)v19);
            if ( v14 >= 0 )
            {
              v9 = v19[0];
              if ( v19[0] )
                goto LABEL_25;
              ++v11;
            }
            else
            {
              Ptr = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
              if ( *Ptr > 2u )
              {
                v22[0] = GetLastError();
                v23 = (__int64)L"FindSerialIdForTargetPath() failed";
                v22[1] = v14;
                sub_140001158((int)Ptr, (int)&byte_1400AE547, 0, 0, (__int64)&v22[1], (__int64)&v23, (__int64)v22);
              }
              v9 = 0;
              v19[0] = 0;
            }
          }
          else
          {
            v13 = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
            if ( *v13 > 2u )
            {
              LastError = GetLastError();
              v23 = (__int64)L"GetRemovableMediaDevicePath failed";
              LODWORD(v24[0]) = v12;
              sub_140001158((int)v13, (int)&byte_1400AE50D, 0, 0, (__int64)v24, (__int64)&v23, (__int64)&LastError);
            }
            v3 = v20;
          }
        }
      }
    }
LABEL_25:
    v16 = GetLastError();
    v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      v17 = v16;
    if ( v17 == -2147023648 || v17 == -2147024637 || v9 )
    {
      if ( (unsigned __int64)(ClassDevsW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        SetupDiDestroyDeviceInfoList(ClassDevsW);
      return v17;
    }
    else
    {
      v18 = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
      if ( *v18 > 2u )
      {
        v22[1] = GetLastError();
        v23 = (__int64)L"SetupDiEnumDeviceInterfaces failed";
        v22[0] = v17;
        sub_140001158((int)v18, (int)&byte_1400AE581, 0, 0, (__int64)v22, (__int64)&v23, (__int64)&v22[1]);
      }
      if ( (unsigned __int64)(ClassDevsW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        SetupDiDestroyDeviceInfoList(ClassDevsW);
      return v17;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      v6 = v5;
    v7 = sub_140018340(&stru_1400C1280, sub_140015AD0)[1].Ptr;
    if ( *v7 > 2u )
    {
      v20 = GetLastError();
      *(_QWORD *)&v22[1] = L"SetupDiGetClassDevs failed";
      LastError = v6;
      sub_140001158((int)v7, (int)&byte_1400AE4D3, 0, 0, (__int64)&LastError, (__int64)&v22[1], (__int64)&v20);
    }
    SetupDiDestroyDeviceInfoList(ClassDevsW);
    return v6;
  }
}

```

## disassembly

```asm
0x14003dbac  mov     [rsp+arg_0], rbx
0x14003dbb1  mov     [rsp+arg_10], rsi
0x14003dbb6  push    rdi
0x14003dbb7  push    r12
0x14003dbb9  push    r13
0x14003dbbb  push    r14
0x14003dbbd  push    r15
0x14003dbbf  sub     rsp, 8E0h
0x14003dbc6  mov     rax, cs:__security_cookie
0x14003dbcd  xor     rax, rsp
0x14003dbd0  mov     [rsp+908h+var_38], rax
0x14003dbd8  mov     rdi, rdx
0x14003dbdb  mov     r13d, ecx
0x14003dbde  mov     dword ptr [rsp+908h+var_8C4], ecx
0x14003dbe2  cmp     byte ptr [rdx+10h], 0
0x14003dbe6  jz      short loc_14003DBF6
0x14003dbe8  xor     edx, edx
0x14003dbea  mov     rcx, rdi; Block
0x14003dbed  call    unknown_libname_18; Microsoft VisualC v14 64bit runtime
0x14003dbf2  mov     byte ptr [rdi+10h], 0
0x14003dbf6  mov     r9d, 12h; Flags
0x14003dbfc  xor     r8d, r8d; hwndParent
0x14003dbff  xor     edx, edx; Enumerator
0x14003dc01  lea     rcx, InterfaceClassGuid; ClassGuid
0x14003dc08  call    cs:SetupDiGetClassDevsW
0x14003dc0e  mov     rbx, rax
0x14003dc11  mov     [rsp+908h+var_8A0], rax
0x14003dc16  dec     rax
0x14003dc19  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003dc1d  ja      loc_14003DCB1
0x14003dc23  call    cs:GetLastError
0x14003dc29  movzx   edi, ax
0x14003dc2c  or      edi, 80070000h
0x14003dc32  test    eax, eax
0x14003dc34  cmovle  edi, eax
0x14003dc37  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003dc3e  lea     rcx, stru_1400C1280; lpInitOnce
0x14003dc45  call    sub_140018340
0x14003dc4a  mov     rsi, [rax+8]
0x14003dc4e  cmp     dword ptr [rsi], 2
0x14003dc51  jbe     short loc_14003DCA1
0x14003dc53  call    cs:GetLastError
0x14003dc59  mov     dword ptr [rsp+908h+var_8C4], eax
0x14003dc5d  lea     rax, aSetupdigetclas; "SetupDiGetClassDevs failed"
0x14003dc64  mov     qword ptr [rsp+908h+var_8BC+4], rax
0x14003dc69  mov     dword ptr [rsp+908h+var_8C4+4], edi
0x14003dc6d  lea     rax, [rsp+908h+var_8C4]
0x14003dc72  mov     [rsp+908h+RequiredSize], rax; __int64
0x14003dc77  lea     rax, [rsp+908h+var_8BC+4]
0x14003dc7c  mov     qword ptr [rsp+908h+PropertyBufferSize], rax; __int64
0x14003dc81  lea     rax, [rsp+908h+var_8C4+4]
0x14003dc86  mov     [rsp+908h+PropertyBuffer], rax; __int64
0x14003dc8b  xor     r9d, r9d; int
0x14003dc8e  xor     r8d, r8d; int
0x14003dc91  lea     rdx, byte_1400AE4D3; int
0x14003dc98  mov     rcx, rsi; int
0x14003dc9b  call    sub_140001158
0x14003dca0  nop
0x14003dca1  mov     rcx, rbx; DeviceInfoSet
0x14003dca4  call    cs:SetupDiDestroyDeviceInfoList
0x14003dcaa  mov     eax, edi
0x14003dcac  jmp     loc_14003DFE9
0x14003dcb1  xorps   xmm0, xmm0
0x14003dcb4  movups  xmmword ptr [rsp+908h+DeviceInterfaceData.cbSize], xmm0
0x14003dcbc  movups  xmmword ptr [rsp+908h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x14003dcc4  mov     eax, 20h ; ' '
0x14003dcc9  mov     [rsp+908h+DeviceInterfaceData.cbSize], eax
0x14003dcd0  movups  xmmword ptr [rsp+908h+DeviceInfoData.cbSize], xmm0
0x14003dcd5  movups  xmmword ptr [rsp+908h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x14003dcdd  mov     [rsp+908h+DeviceInfoData.cbSize], eax
0x14003dce1  xor     edx, edx
0x14003dce3  mov     r8d, 800h
0x14003dce9  lea     rcx, [rsp+908h+var_838]
0x14003dcf1  call    sub_1400802F0
0x14003dcf6  mov     [rsp+908h+var_898], 0
0x14003dcfe  mov     [rsp+908h+PropertyRegDataType], 0
0x14003dd06  xor     sil, sil
0x14003dd09  mov     [rsp+908h+var_8C8], sil
0x14003dd0e  xor     r12d, r12d
0x14003dd11  lea     r8, [rsp+908h+DeviceInfoData]; DeviceInfoData
0x14003dd16  mov     edx, r12d; MemberIndex
0x14003dd19  mov     rcx, rbx; DeviceInfoSet
0x14003dd1c  call    cs:SetupDiEnumDeviceInfo
0x14003dd22  test    eax, eax
0x14003dd24  jz      loc_14003DF16
0x14003dd2a  lea     rax, [rsp+908h+var_898]
0x14003dd2f  mov     [rsp+908h+RequiredSize], rax; RequiredSize
0x14003dd34  mov     [rsp+908h+PropertyBufferSize], 400h; PropertyBufferSize
0x14003dd3c  lea     rax, [rsp+908h+var_838]
0x14003dd44  mov     [rsp+908h+PropertyBuffer], rax; PropertyBuffer
0x14003dd49  lea     r9, [rsp+908h+PropertyRegDataType]; PropertyRegDataType
0x14003dd4e  mov     r8d, 16h; Property
0x14003dd54  lea     rdx, [rsp+908h+DeviceInfoData]; DeviceInfoData
0x14003dd59  mov     rcx, rbx; DeviceInfoSet
0x14003dd5c  call    cs:SetupDiGetDeviceRegistryPropertyW
0x14003dd62  lea     rdx, aUsbstor; "USBSTOR"
0x14003dd69  lea     rcx, [rsp+908h+var_838]
0x14003dd71  call    sub_14006C4A0
0x14003dd76  test    eax, eax
0x14003dd78  jnz     loc_14003DF0E
0x14003dd7e  xor     r14d, r14d
0x14003dd81  jmp     short loc_14003DD88
0x14003dd83  mov     r13d, dword ptr [rsp+908h+var_8C4]
0x14003dd88  lea     rax, [rsp+908h+DeviceInterfaceData]
0x14003dd90  mov     [rsp+908h+PropertyBuffer], rax; DeviceInterfaceData
0x14003dd95  mov     r9d, r14d; MemberIndex
0x14003dd98  lea     r8, InterfaceClassGuid; InterfaceClassGuid
0x14003dd9f  lea     rdx, [rsp+908h+DeviceInfoData]; DeviceInfoData
0x14003dda4  mov     rcx, rbx; DeviceInfoSet
0x14003dda7  call    cs:SetupDiEnumDeviceInterfaces
0x14003ddad  test    eax, eax
0x14003ddaf  jz      loc_14003DF09
0x14003ddb5  xorps   xmm0, xmm0
0x14003ddb8  movups  xmmword ptr [rsp+908h+DestinationString.Length], xmm0
0x14003ddc0  lea     r8, [rsp+908h+DestinationString]; DestinationString
0x14003ddc8  lea     rdx, [rsp+908h+DeviceInterfaceData]; DeviceInterfaceData
0x14003ddd0  mov     rcx, rbx; DeviceInfoSet
0x14003ddd3  call    sub_14003ED20
0x14003ddd8  mov     r15d, eax
0x14003dddb  test    eax, eax
0x14003dddd  jns     short loc_14003DE50
0x14003dddf  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003dde6  lea     rcx, stru_1400C1280; lpInitOnce
0x14003dded  call    sub_140018340
0x14003ddf2  mov     r13, [rax+8]
0x14003ddf6  cmp     dword ptr [r13+0], 2
0x14003ddfb  jbe     short loc_14003DD83
0x14003ddfd  call    cs:GetLastError
0x14003de03  mov     dword ptr [rsp+908h+var_8C4+4], eax
0x14003de07  lea     rax, aGetremovableme; "GetRemovableMediaDevicePath failed"
0x14003de0e  mov     [rsp+908h+var_8B0], rax
0x14003de13  mov     dword ptr [rsp+908h+var_8A8], r15d
0x14003de18  lea     rax, [rsp+908h+var_8C4+4]
0x14003de1d  mov     [rsp+908h+RequiredSize], rax; __int64
0x14003de22  lea     rax, [rsp+908h+var_8B0]
0x14003de27  mov     qword ptr [rsp+908h+PropertyBufferSize], rax; __int64
0x14003de2c  lea     rax, [rsp+908h+var_8A8]
0x14003de31  mov     [rsp+908h+PropertyBuffer], rax; __int64
0x14003de36  xor     r9d, r9d; int
0x14003de39  xor     r8d, r8d; int
0x14003de3c  lea     rdx, byte_1400AE50D; int
0x14003de43  mov     rcx, r13; int
0x14003de46  call    sub_140001158
0x14003de4b  jmp     loc_14003DD83
0x14003de50  lfence
0x14003de53  lea     rax, [rsp+908h+var_8C8]
0x14003de58  mov     qword ptr [rsp+908h+PropertyBufferSize], rax
0x14003de5d  mov     [rsp+908h+PropertyBuffer], rdi
0x14003de62  mov     r9d, r13d
0x14003de65  lea     r8, [rsp+908h+DestinationString]
0x14003de6d  lea     rdx, [rsp+908h+DeviceInfoData]
0x14003de72  mov     rcx, rbx
0x14003de75  call    sub_14003E1BC
0x14003de7a  mov     esi, eax
0x14003de7c  test    eax, eax
0x14003de7e  jns     short loc_14003DEF7
0x14003de80  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003de87  lea     rcx, stru_1400C1280; lpInitOnce
0x14003de8e  call    sub_140018340
0x14003de93  mov     r15, [rax+8]
0x14003de97  cmp     dword ptr [r15], 2
0x14003de9b  jbe     short loc_14003DEEA
0x14003de9d  call    cs:GetLastError
0x14003dea3  mov     dword ptr [rsp+908h+var_8BC], eax
0x14003dea7  lea     rax, aFindserialidfo; "FindSerialIdForTargetPath() failed"
0x14003deae  mov     [rsp+908h+var_8B0], rax
0x14003deb3  mov     dword ptr [rsp+908h+var_8BC+4], esi
0x14003deb7  lea     rax, [rsp+908h+var_8BC]
0x14003debc  mov     [rsp+908h+RequiredSize], rax; __int64
0x14003dec1  lea     rax, [rsp+908h+var_8B0]
0x14003dec6  mov     qword ptr [rsp+908h+PropertyBufferSize], rax; __int64
0x14003decb  lea     rax, [rsp+908h+var_8BC+4]
0x14003ded0  mov     [rsp+908h+PropertyBuffer], rax; __int64
0x14003ded5  xor     r9d, r9d; int
0x14003ded8  xor     r8d, r8d; int
0x14003dedb  lea     rdx, byte_1400AE547; int
0x14003dee2  mov     rcx, r15; int
0x14003dee5  call    sub_140001158
0x14003deea  xor     sil, sil
0x14003deed  mov     [rsp+908h+var_8C8], sil
0x14003def2  jmp     loc_14003DD88
0x14003def7  mov     sil, [rsp+908h+var_8C8]
0x14003defc  test    sil, sil
0x14003deff  jnz     short loc_14003DF16
0x14003df01  inc     r14d
0x14003df04  jmp     loc_14003DD88
0x14003df09  test    sil, sil
0x14003df0c  jnz     short loc_14003DF16
0x14003df0e  inc     r12d
0x14003df11  jmp     loc_14003DD11
0x14003df16  call    cs:GetLastError
0x14003df1c  movzx   edi, ax
0x14003df1f  or      edi, 80070000h
0x14003df25  test    eax, eax
0x14003df27  cmovle  edi, eax
0x14003df2a  cmp     edi, 800704E0h
0x14003df30  jz      loc_14003DFCC
0x14003df36  cmp     edi, 80070103h
0x14003df3c  jz      loc_14003DFCC
0x14003df42  test    sil, sil
0x14003df45  jnz     loc_14003DFCC
0x14003df4b  lea     rdx, sub_140015AD0; void (__cdecl *)()
0x14003df52  lea     rcx, stru_1400C1280; lpInitOnce
0x14003df59  call    sub_140018340
0x14003df5e  mov     rsi, [rax+8]
0x14003df62  cmp     dword ptr [rsi], 2
0x14003df65  jbe     short loc_14003DFB5
0x14003df67  call    cs:GetLastError
0x14003df6d  mov     dword ptr [rsp+908h+var_8BC+4], eax
0x14003df71  lea     rax, aSetupdienumdev; "SetupDiEnumDeviceInterfaces failed"
0x14003df78  mov     [rsp+908h+var_8B0], rax
0x14003df7d  mov     dword ptr [rsp+908h+var_8BC], edi
0x14003df81  lea     rax, [rsp+908h+var_8BC+4]
0x14003df86  mov     [rsp+908h+RequiredSize], rax; __int64
0x14003df8b  lea     rax, [rsp+908h+var_8B0]
0x14003df90  mov     qword ptr [rsp+908h+PropertyBufferSize], rax; __int64
0x14003df95  lea     rax, [rsp+908h+var_8BC]
0x14003df9a  mov     [rsp+908h+PropertyBuffer], rax; __int64
0x14003df9f  xor     r9d, r9d; int
0x14003dfa2  xor     r8d, r8d; int
0x14003dfa5  lea     rdx, byte_1400AE581; int
0x14003dfac  mov     rcx, rsi; int
0x14003dfaf  call    sub_140001158
0x14003dfb4  nop
0x14003dfb5  lea     rcx, [rbx-1]
0x14003dfb9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14003dfbd  ja      short loc_14003DFC8
0x14003dfbf  mov     rcx, rbx; DeviceInfoSet
0x14003dfc2  call    cs:SetupDiDestroyDeviceInfoList
0x14003dfc8  mov     eax, edi
0x14003dfca  jmp     short loc_14003DFE9
0x14003dfcc  lea     rax, [rbx-1]
0x14003dfd0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14003dfd4  ja      short loc_14003DFE0
0x14003dfd6  mov     rcx, rbx; DeviceInfoSet
0x14003dfd9  call    cs:SetupDiDestroyDeviceInfoList
0x14003dfdf  nop
0x14003dfe0  mov     eax, edi
0x14003dfe2  jmp     short loc_14003DFE9
0x14003dfe4  mov     eax, 80004005h
0x14003dfe9  mov     rcx, [rsp+908h+var_38]
0x14003dff1  xor     rcx, rsp; StackCookie
0x14003dff4  call    __security_check_cookie
0x14003dff9  lea     r11, [rsp+908h+var_28]
0x14003e001  mov     rbx, [r11+30h]
0x14003e005  mov     rsi, [r11+40h]
0x14003e009  mov     rsp, r11
0x14003e00c  pop     r15
0x14003e00e  pop     r14
0x14003e010  pop     r13
0x14003e012  pop     r12
0x14003e014  pop     rdi
0x14003e015  retn
```
