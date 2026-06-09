# PolicyManager::GetDeviceWipeAttemptLimit(ulong *)

- ea: `0x180070c14`
- end: `0x180070d16`
- name: `?GetDeviceWipeAttemptLimit@PolicyManager@@YAJPEAK@Z`
- size: `258`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800466d0`
- `0x180046c04`

## callees

- `0x180002654`
- `0x180008b90`
- `0x180070c14`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x180070c22`
- `ntdll!RtlIsMultiSessionSku` at `0x180070c22`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttempts` at `0x180070cb2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttempts` at `0x180070cb2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x180070c6b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled` at `0x180070c6b`

## pseudocode

```c
__int64 __fastcall PolicyManager::GetDeviceWipeAttemptLimit(PolicyManager *this, unsigned int *a2)
{
  int v3; // r8d
  int v4; // r9d
  int v5; // ecx
  char *v6; // rdx
  __int64 result; // rax
  int v8; // r8d
  int v9; // r9d
  unsigned int DeviceLockPolicy_MaxDevicePasswordFailedAttempts; // ebx
  int v11; // ecx
  char *v12; // rdx
  int v13; // [rsp+58h] [rbp+28h] BYREF
  int v14; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+38h] BYREF

  if ( (unsigned __int8)RtlIsMultiSessionSku(this, a2) )
  {
    v5 = g_logProvider;
    if ( *(_DWORD *)g_logProvider > 4u )
    {
      v6 = byte_1800B3929;
LABEL_18:
      v15 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v5,
        (_DWORD)v6,
        v3,
        v4,
        (__int64)&v15);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttemptsPresent()
    || !(unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttemptsPresent() )
  {
    v5 = g_logProvider;
    if ( *(_DWORD *)g_logProvider > 4u )
    {
      v6 = &byte_1800B38F7;
      goto LABEL_18;
    }
LABEL_19:
    result = 0;
    goto LABEL_20;
  }
  v13 = 0;
  result = PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled(&v13);
  DeviceLockPolicy_MaxDevicePasswordFailedAttempts = result;
  if ( (int)result < 0 )
  {
    v11 = g_logProvider;
    if ( *(_DWORD *)g_logProvider > 2u )
    {
      v12 = (char *)&unk_1800B38A8;
LABEL_9:
      v15 = DeviceLockPolicy_MaxDevicePasswordFailedAttempts;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v11,
        (_DWORD)v12,
        v8,
        v9,
        (__int64)&v15);
      return DeviceLockPolicy_MaxDevicePasswordFailedAttempts;
    }
    return DeviceLockPolicy_MaxDevicePasswordFailedAttempts;
  }
  if ( !v13 )
  {
    v14 = 0;
    DeviceLockPolicy_MaxDevicePasswordFailedAttempts = PolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttempts(&v14);
    if ( (DeviceLockPolicy_MaxDevicePasswordFailedAttempts & 0x80000000) == 0 )
    {
      *(_DWORD *)this = v14;
      return DeviceLockPolicy_MaxDevicePasswordFailedAttempts;
    }
    v11 = g_logProvider;
    if ( *(_DWORD *)g_logProvider > 2u )
    {
      v12 = &byte_1800B384F;
      goto LABEL_9;
    }
    return DeviceLockPolicy_MaxDevicePasswordFailedAttempts;
  }
LABEL_20:
  *(_DWORD *)this = 0;
  return result;
}

```

## disassembly

```asm
0x180070c14  push    rbp
0x180070c16  push    rbx
0x180070c17  push    rdi
0x180070c18  mov     rbp, rsp
0x180070c1b  sub     rsp, 30h
0x180070c1f  mov     rdi, rcx
0x180070c22  call    cs:__imp_RtlIsMultiSessionSku
0x180070c28  test    al, al
0x180070c2a  jz      short loc_180070C4A
0x180070c2c  mov     rcx, cs:g_logProvider
0x180070c33  mov     eax, [rcx]
0x180070c35  cmp     eax, 4
0x180070c38  jbe     loc_180070D06
0x180070c3e  lea     rdx, byte_1800B3929
0x180070c45  jmp     loc_180070CF1
0x180070c4a  call    IsPolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttemptsPresent
0x180070c4f  test    al, al
0x180070c51  jz      loc_180070CDC
0x180070c57  call    IsPolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttemptsPresent
0x180070c5c  test    al, al
0x180070c5e  jz      short loc_180070CDC
0x180070c60  lea     rcx, [rbp+arg_8]
0x180070c64  mov     [rbp+arg_8], 0
0x180070c6b  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_DevicePasswordEnabled
0x180070c71  mov     ebx, eax
0x180070c73  test    eax, eax
0x180070c75  jns     short loc_180070CA1
0x180070c77  mov     rcx, cs:g_logProvider
0x180070c7e  mov     edx, [rcx]
0x180070c80  cmp     edx, 2
0x180070c83  jbe     short loc_180070C9D
0x180070c85  lea     rdx, unk_1800B38A8
0x180070c8c  lea     rax, [rbp+arg_18]
0x180070c90  mov     [rsp+30h+var_10], rax
0x180070c95  mov     [rbp+arg_18], ebx
0x180070c98  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180070c9d  mov     eax, ebx
0x180070c9f  jmp     short loc_180070D0E
0x180070ca1  cmp     [rbp+arg_8], 0
0x180070ca5  jnz     short loc_180070D08
0x180070ca7  lea     rcx, [rbp+arg_10]
0x180070cab  mov     [rbp+arg_10], 0
0x180070cb2  call    cs:__imp_PolicyManager_GetDeviceLockPolicy_MaxDevicePasswordFailedAttempts
0x180070cb8  mov     ebx, eax
0x180070cba  test    eax, eax
0x180070cbc  jns     short loc_180070CD5
0x180070cbe  mov     rcx, cs:g_logProvider
0x180070cc5  mov     edx, [rcx]
0x180070cc7  cmp     edx, 2
0x180070cca  jbe     short loc_180070C9D
0x180070ccc  lea     rdx, byte_1800B384F
0x180070cd3  jmp     short loc_180070C8C
0x180070cd5  mov     eax, [rbp+arg_10]
0x180070cd8  mov     [rdi], eax
0x180070cda  jmp     short loc_180070C9D
0x180070cdc  mov     rcx, cs:g_logProvider
0x180070ce3  mov     eax, [rcx]
0x180070ce5  cmp     eax, 4
0x180070ce8  jbe     short loc_180070D06
0x180070cea  lea     rdx, byte_1800B38F7
0x180070cf1  lea     rax, [rbp+arg_18]
0x180070cf5  mov     [rsp+30h+var_10], rax
0x180070cfa  mov     [rbp+arg_18], 0
0x180070d01  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180070d06  xor     eax, eax
0x180070d08  mov     dword ptr [rdi], 0
0x180070d0e  add     rsp, 30h
0x180070d12  pop     rdi
0x180070d13  pop     rbx
0x180070d14  pop     rbp
0x180070d15  retn
```
