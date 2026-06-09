# PolicyManager::ReadDeviceLockPolicy

- ea: `0x180052c84`
- end: `0x180053241`
- name: `PolicyManager::ReadDeviceLockPolicy`
- size: `1469`
- prototype: `__int64 __fastcall(NgcPolicy *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9e4`

## callees

- `0x180002348`
- `0x180018194`
- `0x1800215ec`
- `0x180029b94`
- `0x18002daf4`
- `0x180052c84`
- `0x18005ed68`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x180052d44`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x180052d44`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength` at `0x180052dac`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength` at `0x180052dac`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired` at `0x180052e4c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired` at `0x180052e4c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters` at `0x180052eb9`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters` at `0x180052eb9`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory` at `0x180052f56`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory` at `0x180052f56`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration` at `0x180053020`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration` at `0x180053020`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword` at `0x1800530b7`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword` at `0x1800530b7`

## pseudocode

```c
__int64 __fastcall PolicyManager::ReadDeviceLockPolicy(NgcPolicy *this, _OWORD *a2)
{
  int v4; // r13d
  unsigned int v5; // r12d
  int DeviceLockPolicy_DevicePasswordEnabled; // eax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // edi
  __int64 result; // rax
  int DeviceLockPolicy_MinDevicePasswordLength; // eax
  const unsigned __int16 *v11; // rdx
  int DeviceLockPolicy_AlphanumericDevicePasswordRequired; // eax
  int v13; // esi
  int v14; // r14d
  int DeviceLockPolicy_MinDevicePasswordComplexCharacters; // eax
  int v16; // edi
  int DeviceLockPolicy_DevicePasswordHistory; // eax
  __int64 v18; // rdx
  int DeviceLockPolicy_DevicePasswordExpiration; // eax
  __int64 v20; // rdx
  int DeviceLockPolicy_AllowSimpleDevicePassword; // eax
  unsigned __int8 *v22; // rdx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  int v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+54h] [rbp-65h] BYREF
  unsigned int DefaultPinMinLength; // [rsp+58h] [rbp-61h] BYREF
  int v29; // [rsp+5Ch] [rbp-5Dh] BYREF
  int v30; // [rsp+60h] [rbp-59h] BYREF
  int v31; // [rsp+64h] [rbp-55h] BYREF
  __int128 v32; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v33[44]; // [rsp+78h] [rbp-41h]
  _BYTE v34[4]; // [rsp+A8h] [rbp-11h] BYREF
  int v35; // [rsp+ACh] [rbp-Dh]
  int v36; // [rsp+B0h] [rbp-9h]
  __int128 v37; // [rsp+B4h] [rbp-5h]
  int v38; // [rsp+C4h] [rbp+Bh]
  __int64 v39; // [rsp+C8h] [rbp+Fh]
  int v40; // [rsp+D0h] [rbp+17h]
  unsigned int v41; // [rsp+130h] [rbp+77h] BYREF
  unsigned int v42; // [rsp+138h] [rbp+7Fh] BYREF

  v4 = 0;
  if ( (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent()
    && (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent() )
  {
    LOBYTE(v32) = 0;
    DWORD1(v32) = 1;
    v5 = 2;
    *((_QWORD *)&v32 + 1) = 1;
    *(_DWORD *)&v33[28] = 2;
    *(_OWORD *)&v33[12] = 0;
    *(_QWORD *)&v33[32] = 1;
    v29 = 1;
    v33[0] = 0;
    *(_QWORD *)&v33[4] = 0x7F00000008LL;
    *(_DWORD *)&v33[40] = 0;
    DeviceLockPolicy_DevicePasswordEnabled = PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled(&v29);
    v8 = DeviceLockPolicy_DevicePasswordEnabled;
    if ( DeviceLockPolicy_DevicePasswordEnabled < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 4 )
      {
        v27 = DeviceLockPolicy_DevicePasswordEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800AD371,
          0,
          0,
          (__int64)&v27);
      }
      return v8;
    }
    if ( v29 )
      return 2148073489LL;
    DefaultPinMinLength = NgcPolicy::GetDefaultPinMinLength(this, v7);
    DeviceLockPolicy_MinDevicePasswordLength = PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength(&DefaultPinMinLength);
    v11 = (const unsigned __int16 *)(unsigned int)DeviceLockPolicy_MinDevicePasswordLength;
    if ( DeviceLockPolicy_MinDevicePasswordLength >= 0 )
    {
      if ( DefaultPinMinLength - 4 > 0x7B )
      {
        if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          v27 = DefaultPinMinLength;
          v26 = DeviceLockPolicy_MinDevicePasswordLength;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (__int64)byte_1800AD3E9,
            0,
            0,
            (__int64)&v26,
            (__int64)&v27);
        }
        DefaultPinMinLength = NgcPolicy::GetDefaultPinMinLength(this, v11);
      }
    }
    else if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v27 = DeviceLockPolicy_MinDevicePasswordLength;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AD434,
        0,
        0,
        (__int64)&v27);
    }
    v30 = 2;
    DeviceLockPolicy_AlphanumericDevicePasswordRequired = PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired(
                                                            &v30,
                                                            v11);
    if ( DeviceLockPolicy_AlphanumericDevicePasswordRequired < 0 && (unsigned int)dword_1800BE0B8 > 4 )
    {
      v26 = DeviceLockPolicy_AlphanumericDevicePasswordRequired;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AD293,
        0,
        0,
        (__int64)&v26);
    }
    if ( v30 == 1 )
    {
      v13 = 1;
      v14 = 2;
      v4 = 2;
    }
    else
    {
      v13 = 0;
      v14 = 0;
      v5 = 0;
      if ( !v30 )
      {
        v27 = 1;
        DeviceLockPolicy_MinDevicePasswordComplexCharacters = PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters(&v27);
        v16 = DeviceLockPolicy_MinDevicePasswordComplexCharacters;
        if ( DeviceLockPolicy_MinDevicePasswordComplexCharacters < 0 && (unsigned int)dword_1800BE0B8 > 4 )
        {
          v26 = DeviceLockPolicy_MinDevicePasswordComplexCharacters;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)byte_1800AD325,
            0,
            0,
            (__int64)&v26);
        }
        if ( v27 != 1 )
        {
          switch ( v27 )
          {
            case 2:
              v13 = 1;
              v14 = 1;
              break;
            case 3:
              v13 = 1;
              v14 = 1;
              v5 = 1;
              break;
            case 4:
              v13 = 1;
              v14 = 1;
              v5 = 1;
              v4 = 1;
              break;
            default:
              if ( (unsigned int)dword_1800BE0B8 > 3 )
              {
                v26 = v16;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_1800BE0B8,
                  (unsigned __int8 *)byte_1800AD2DF,
                  0,
                  0,
                  (__int64)&v26);
              }
              break;
          }
        }
      }
    }
    v42 = 0;
    DeviceLockPolicy_DevicePasswordHistory = PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory(&v42);
    v18 = (unsigned int)DeviceLockPolicy_DevicePasswordHistory;
    if ( DeviceLockPolicy_DevicePasswordHistory >= 0 )
    {
      if ( v42 > 0x32 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          v26 = v42;
          v27 = DeviceLockPolicy_DevicePasswordHistory;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (__int64)&byte_1800AD25F,
            0,
            0,
            (__int64)&v27,
            (__int64)&v26);
        }
        v42 = 0;
      }
    }
    else if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v26 = DeviceLockPolicy_DevicePasswordHistory;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800AD1DE,
        0,
        0,
        (__int64)&v26);
    }
    v41 = 0;
    DeviceLockPolicy_DevicePasswordExpiration = PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration(&v41, v18);
    v20 = (unsigned int)DeviceLockPolicy_DevicePasswordExpiration;
    if ( DeviceLockPolicy_DevicePasswordExpiration >= 0 )
    {
      if ( v41 > 0x2DA )
      {
        if ( (unsigned int)dword_1800BE0B8 > 3 )
        {
          v26 = v41;
          v27 = DeviceLockPolicy_DevicePasswordExpiration;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (__int64)&unk_1800AD130,
            0,
            0,
            (__int64)&v27,
            (__int64)&v26);
        }
        v41 = 0;
      }
    }
    else if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v26 = DeviceLockPolicy_DevicePasswordExpiration;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AD21D,
        0,
        0,
        (__int64)&v26);
    }
    v31 = 1;
    DeviceLockPolicy_AllowSimpleDevicePassword = PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword(&v31, v20);
    if ( DeviceLockPolicy_AllowSimpleDevicePassword < 0 && (unsigned int)dword_1800BE0B8 > 4 )
    {
      v26 = DeviceLockPolicy_AllowSimpleDevicePassword;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AD19B,
        0,
        0,
        (__int64)&v26);
    }
    v34[0] = 0;
    v35 = 8;
    v36 = 127;
    v37 = 0;
    v38 = 2;
    v39 = 1;
    v40 = 0;
    v8 = NgcPolicy::NgcPinPolicy::Initialize(v34, DefaultPinMinLength, 127, v5, v14, v13, v4, v31, v42, v41);
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 <= 2 )
        return v8;
      v22 = (unsigned __int8 *)word_1800AD16A;
LABEL_59:
      v26 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        v22,
        0,
        0,
        (__int64)&v26);
      return v8;
    }
    result = NgcPolicy::NgcPolicy::Initialize(&v32, 1, 1, 0, v34);
    v8 = result;
    if ( (int)result < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 <= 2 )
        return v8;
      v22 = (unsigned __int8 *)&unk_1800AD088;
      goto LABEL_59;
    }
    v23 = *(_OWORD *)v33;
    *a2 = v32;
    v24 = *(_OWORD *)&v33[16];
    a2[1] = v23;
    v25 = *(_OWORD *)&v33[28];
    a2[2] = v24;
    *(_OWORD *)((char *)a2 + 44) = v25;
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      v26 = -2146893783;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&unk_1800AD3B0,
        0,
        0,
        (__int64)&v26);
    }
    return 2148073513LL;
  }
  return result;
}

```

## disassembly

```asm
0x180052c84  mov     [rsp-8+arg_0], rbx
0x180052c89  push    rbp
0x180052c8a  push    rsi
0x180052c8b  push    rdi
0x180052c8c  push    r12
0x180052c8e  push    r13
0x180052c90  push    r14
0x180052c92  push    r15
0x180052c94  lea     rbp, [rsp-27h]
0x180052c99  sub     rsp, 0E0h
0x180052ca0  mov     r15, rdx
0x180052ca3  mov     rsi, rcx
0x180052ca6  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cab  xor     r13d, r13d
0x180052cae  test    al, al
0x180052cb0  jz      loc_1800531EC
0x180052cb6  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cbb  test    al, al
0x180052cbd  jz      loc_1800531EC
0x180052cc3  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cc8  test    al, al
0x180052cca  jz      loc_1800531EC
0x180052cd0  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cd5  test    al, al
0x180052cd7  jz      loc_1800531EC
0x180052cdd  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052ce2  test    al, al
0x180052ce4  jz      loc_1800531EC
0x180052cea  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cef  test    al, al
0x180052cf1  jz      loc_1800531EC
0x180052cf7  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x180052cfc  test    al, al
0x180052cfe  jz      loc_1800531EC
0x180052d04  lea     edx, [r13+1]
0x180052d08  mov     byte ptr [rbp+57h+var_A8], r13b
0x180052d0c  xorps   xmm0, xmm0
0x180052d0f  mov     dword ptr [rbp+57h+var_A8+4], edx
0x180052d12  lea     r12d, [r13+2]
0x180052d16  mov     qword ptr [rbp+57h+var_A8+8], rdx
0x180052d1a  lea     rcx, [rbp+57h+var_B4]
0x180052d1e  mov     dword ptr [rbp+57h+var_7C], r12d
0x180052d22  movdqu  [rbp+57h+var_98+0Ch], xmm0
0x180052d27  mov     qword ptr [rbp+57h+var_7C+4], rdx
0x180052d2b  mov     [rbp+57h+var_B4], edx
0x180052d2e  mov     byte ptr [rbp+57h+var_98], r13b
0x180052d32  mov     dword ptr [rbp+57h+var_98+4], 8
0x180052d39  mov     dword ptr [rbp+57h+var_98+8], 7Fh
0x180052d40  mov     dword ptr [rbp+57h+var_7C+0Ch], r13d
0x180052d44  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled
0x180052d4b  nop     dword ptr [rax+rax+00h]
0x180052d50  mov     edi, eax
0x180052d52  test    eax, eax
0x180052d54  jns     short loc_180052D8D
0x180052d56  mov     ecx, cs:dword_1800BE0B8
0x180052d5c  cmp     ecx, 4
0x180052d5f  jbe     short loc_180052D86
0x180052d61  mov     [rbp+57h+var_BC], eax
0x180052d64  lea     rdx, byte_1800AD371
0x180052d6b  lea     rax, [rbp+57h+var_BC]
0x180052d6f  xor     r9d, r9d
0x180052d72  mov     [rsp+110h+var_F0], rax
0x180052d77  lea     rcx, dword_1800BE0B8
0x180052d7e  xor     r8d, r8d
0x180052d81  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052d86  mov     eax, edi
0x180052d88  jmp     loc_180053225
0x180052d8d  cmp     [rbp+57h+var_B4], r13d
0x180052d91  jz      short loc_180052D9D
0x180052d93  mov     eax, 80090011h
0x180052d98  jmp     loc_180053225
0x180052d9d  mov     rcx, rsi; this
0x180052da0  call    ?GetDefaultPinMinLength@NgcPolicy@@YAKPEBG@Z; NgcPolicy::GetDefaultPinMinLength(ushort const *)
0x180052da5  lea     rcx, [rbp+57h+var_B8]
0x180052da9  mov     [rbp+57h+var_B8], eax
0x180052dac  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordLength
0x180052db3  nop     dword ptr [rax+rax+00h]
0x180052db8  lea     rbx, dword_1800BE0B8
0x180052dbf  mov     edx, eax
0x180052dc1  test    eax, eax
0x180052dc3  jns     short loc_180052DF3
0x180052dc5  mov     ecx, cs:dword_1800BE0B8
0x180052dcb  cmp     ecx, 4
0x180052dce  jbe     short loc_180052E44
0x180052dd0  mov     [rbp+57h+var_BC], eax
0x180052dd3  lea     rdx, dword_1800AD434
0x180052dda  lea     rax, [rbp+57h+var_BC]
0x180052dde  xor     r9d, r9d
0x180052de1  xor     r8d, r8d
0x180052de4  mov     [rsp+110h+var_F0], rax
0x180052de9  mov     rcx, rbx
0x180052dec  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052df1  jmp     short loc_180052E44
0x180052df3  mov     eax, [rbp+57h+var_B8]
0x180052df6  add     eax, 0FFFFFFFCh
0x180052df9  cmp     eax, 7Bh ; '{'
0x180052dfc  jbe     short loc_180052E44
0x180052dfe  mov     eax, cs:dword_1800BE0B8
0x180052e04  cmp     eax, 3
0x180052e07  jbe     short loc_180052E39
0x180052e09  mov     eax, [rbp+57h+var_B8]
0x180052e0c  xor     r9d, r9d
0x180052e0f  mov     [rbp+57h+var_BC], eax
0x180052e12  xor     r8d, r8d
0x180052e15  lea     rax, [rbp+57h+var_BC]
0x180052e19  mov     [rbp+57h+var_C0], edx
0x180052e1c  mov     [rsp+110h+var_E8], rax
0x180052e21  lea     rdx, byte_1800AD3E9
0x180052e28  lea     rax, [rbp+57h+var_C0]
0x180052e2c  mov     rcx, rbx
0x180052e2f  mov     [rsp+110h+var_F0], rax
0x180052e34  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180052e39  mov     rcx, rsi; this
0x180052e3c  call    ?GetDefaultPinMinLength@NgcPolicy@@YAKPEBG@Z; NgcPolicy::GetDefaultPinMinLength(ushort const *)
0x180052e41  mov     [rbp+57h+var_B8], eax
0x180052e44  lea     rcx, [rbp+57h+var_B0]
0x180052e48  mov     [rbp+57h+var_B0], r12d
0x180052e4c  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequired
0x180052e53  nop     dword ptr [rax+rax+00h]
0x180052e58  test    eax, eax
0x180052e5a  jns     short loc_180052E88
0x180052e5c  mov     ecx, cs:dword_1800BE0B8
0x180052e62  cmp     ecx, 4
0x180052e65  jbe     short loc_180052E88
0x180052e67  mov     [rbp+57h+var_C0], eax
0x180052e6a  lea     rdx, byte_1800AD293
0x180052e71  lea     rax, [rbp+57h+var_C0]
0x180052e75  xor     r9d, r9d
0x180052e78  xor     r8d, r8d
0x180052e7b  mov     [rsp+110h+var_F0], rax
0x180052e80  mov     rcx, rbx
0x180052e83  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052e88  mov     eax, [rbp+57h+var_B0]
0x180052e8b  mov     edi, 1
0x180052e90  cmp     eax, edi
0x180052e92  jnz     short loc_180052EA1
0x180052e94  mov     esi, edi
0x180052e96  mov     r14d, r12d
0x180052e99  mov     r13d, r12d
0x180052e9c  jmp     loc_180052F4B
0x180052ea1  mov     esi, r13d
0x180052ea4  mov     r14d, r13d
0x180052ea7  mov     r12d, r13d
0x180052eaa  test    eax, eax
0x180052eac  jnz     loc_180052F4B
0x180052eb2  lea     rcx, [rbp+57h+var_BC]
0x180052eb6  mov     [rbp+57h+var_BC], edi
0x180052eb9  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_MinDevicePasswordComplexCharacters
0x180052ec0  nop     dword ptr [rax+rax+00h]
0x180052ec5  mov     edi, eax
0x180052ec7  test    eax, eax
0x180052ec9  jns     short loc_180052EF7
0x180052ecb  mov     ecx, cs:dword_1800BE0B8
0x180052ed1  cmp     ecx, 4
0x180052ed4  jbe     short loc_180052EF7
0x180052ed6  mov     [rbp+57h+var_C0], eax
0x180052ed9  lea     rdx, byte_1800AD325
0x180052ee0  lea     rax, [rbp+57h+var_C0]
0x180052ee4  xor     r9d, r9d
0x180052ee7  xor     r8d, r8d
0x180052eea  mov     [rsp+110h+var_F0], rax
0x180052eef  mov     rcx, rbx
0x180052ef2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052ef7  mov     ecx, [rbp+57h+var_BC]
0x180052efa  sub     ecx, 1
0x180052efd  jz      short loc_180052F46
0x180052eff  sub     ecx, 1
0x180052f02  jz      loc_180052FBB
0x180052f08  sub     ecx, 1
0x180052f0b  jz      loc_180052FAC
0x180052f11  cmp     ecx, 1
0x180052f14  jz      loc_180052F9A
0x180052f1a  mov     eax, cs:dword_1800BE0B8
0x180052f20  cmp     eax, 3
0x180052f23  jbe     short loc_180052F46
0x180052f25  lea     rax, [rbp+57h+var_C0]
0x180052f29  mov     [rbp+57h+var_C0], edi
0x180052f2c  xor     r9d, r9d
0x180052f2f  mov     [rsp+110h+var_F0], rax
0x180052f34  xor     r8d, r8d
0x180052f37  lea     rdx, byte_1800AD2DF
0x180052f3e  mov     rcx, rbx
0x180052f41  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052f46  mov     edi, 1
0x180052f4b  lea     rcx, [rbp+57h+arg_18]
0x180052f4f  mov     [rbp+57h+arg_18], 0
0x180052f56  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordHistory
0x180052f5d  nop     dword ptr [rax+rax+00h]
0x180052f62  mov     edx, eax
0x180052f64  test    eax, eax
0x180052f66  jns     short loc_180052FC7
0x180052f68  mov     ecx, cs:dword_1800BE0B8
0x180052f6e  cmp     ecx, 4
0x180052f71  jbe     loc_180053015
0x180052f77  mov     [rbp+57h+var_C0], eax
0x180052f7a  lea     rdx, word_1800AD1DE
0x180052f81  lea     rax, [rbp+57h+var_C0]
0x180052f85  xor     r9d, r9d
0x180052f88  xor     r8d, r8d
0x180052f8b  mov     [rsp+110h+var_F0], rax
0x180052f90  mov     rcx, rbx
0x180052f93  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052f98  jmp     short loc_180053015
0x180052f9a  mov     edi, 1
0x180052f9f  mov     esi, edi
0x180052fa1  mov     r14d, edi
0x180052fa4  mov     r12d, edi
0x180052fa7  mov     r13d, edi
0x180052faa  jmp     short loc_180052F4B
0x180052fac  mov     edi, 1
0x180052fb1  mov     esi, edi
0x180052fb3  mov     r14d, edi
0x180052fb6  mov     r12d, edi
0x180052fb9  jmp     short loc_180052F4B
0x180052fbb  mov     edi, 1
0x180052fc0  mov     esi, edi
0x180052fc2  mov     r14d, edi
0x180052fc5  jmp     short loc_180052F4B
0x180052fc7  mov     eax, [rbp+57h+arg_18]
0x180052fca  test    eax, eax
0x180052fcc  js      short loc_180052FD3
0x180052fce  cmp     eax, 32h ; '2'
0x180052fd1  jbe     short loc_180053015
0x180052fd3  mov     eax, cs:dword_1800BE0B8
0x180052fd9  cmp     eax, 3
0x180052fdc  jbe     short loc_18005300E
0x180052fde  mov     eax, [rbp+57h+arg_18]
0x180052fe1  xor     r9d, r9d
0x180052fe4  mov     [rbp+57h+var_C0], eax
0x180052fe7  xor     r8d, r8d
0x180052fea  lea     rax, [rbp+57h+var_C0]
0x180052fee  mov     [rbp+57h+var_BC], edx
0x180052ff1  mov     [rsp+110h+var_E8], rax
0x180052ff6  lea     rdx, byte_1800AD25F
0x180052ffd  lea     rax, [rbp+57h+var_BC]
0x180053001  mov     rcx, rbx
0x180053004  mov     [rsp+110h+var_F0], rax
0x180053009  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005300e  mov     [rbp+57h+arg_18], 0
0x180053015  lea     rcx, [rbp+57h+arg_10]
0x180053019  mov     [rbp+57h+arg_10], 0
0x180053020  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordExpiration
0x180053027  nop     dword ptr [rax+rax+00h]
0x18005302c  mov     edx, eax
0x18005302e  test    eax, eax
0x180053030  jns     short loc_180053060
0x180053032  mov     ecx, cs:dword_1800BE0B8
0x180053038  cmp     ecx, 4
0x18005303b  jbe     short loc_1800530B0
0x18005303d  mov     [rbp+57h+var_C0], eax
0x180053040  lea     rdx, byte_1800AD21D
0x180053047  lea     rax, [rbp+57h+var_C0]
0x18005304b  xor     r9d, r9d
0x18005304e  xor     r8d, r8d
0x180053051  mov     [rsp+110h+var_F0], rax
0x180053056  mov     rcx, rbx
0x180053059  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005305e  jmp     short loc_1800530B0
0x180053060  mov     eax, [rbp+57h+arg_10]
0x180053063  test    eax, eax
0x180053065  js      short loc_18005306E
0x180053067  cmp     eax, 2DAh
0x18005306c  jbe     short loc_1800530B0
0x18005306e  mov     eax, cs:dword_1800BE0B8
0x180053074  cmp     eax, 3
0x180053077  jbe     short loc_1800530A9
0x180053079  mov     eax, [rbp+57h+arg_10]
0x18005307c  xor     r9d, r9d
0x18005307f  mov     [rbp+57h+var_C0], eax
0x180053082  xor     r8d, r8d
0x180053085  lea     rax, [rbp+57h+var_C0]
0x180053089  mov     [rbp+57h+var_BC], edx
0x18005308c  mov     [rsp+110h+var_E8], rax
0x180053091  lea     rdx, unk_1800AD130
0x180053098  lea     rax, [rbp+57h+var_BC]
0x18005309c  mov     rcx, rbx
0x18005309f  mov     [rsp+110h+var_F0], rax
0x1800530a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800530a9  mov     [rbp+57h+arg_10], 0
0x1800530b0  lea     rcx, [rbp+57h+var_AC]
0x1800530b4  mov     [rbp+57h+var_AC], edi
0x1800530b7  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_AllowSimpleDevicePassword
0x1800530be  nop     dword ptr [rax+rax+00h]
0x1800530c3  test    eax, eax
0x1800530c5  jns     short loc_1800530F3
0x1800530c7  mov     ecx, cs:dword_1800BE0B8
0x1800530cd  cmp     ecx, 4
0x1800530d0  jbe     short loc_1800530F3
0x1800530d2  mov     [rbp+57h+var_C0], eax
0x1800530d5  lea     rdx, byte_1800AD19B
0x1800530dc  lea     rax, [rbp+57h+var_C0]
0x1800530e0  xor     r9d, r9d
0x1800530e3  xor     r8d, r8d
0x1800530e6  mov     [rsp+110h+var_F0], rax
0x1800530eb  mov     rcx, rbx
0x1800530ee  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800530f3  mov     eax, [rbp+57h+arg_10]
0x1800530f6  lea     rcx, [rbp+57h+var_68]
0x1800530fa  mov     edx, [rbp+57h+var_B8]
0x1800530fd  mov     r8d, 7Fh
  ... truncated ...
```
