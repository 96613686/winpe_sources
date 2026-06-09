# SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::GetValue(void)

- ea: `0x180035d70`
- end: `0x180035e45`
- name: `?GetValue@BrightnessDimmingControl@BatteryUsageHandlers@SystemSettings@@UEAA_NXZ`
- size: `213`
- prototype: `bool __fastcall(SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800228bc`
- `0x180035d70`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035e32`
- `POWRPROF!PowerGetActiveScheme` at `0x180035dad`
- `POWRPROF!PowerGetActiveScheme` at `0x180035dad`
- `POWRPROF!PowerReadDCValue` at `0x180035df9`
- `POWRPROF!PowerReadDCValue` at `0x180035df9`

## pseudocode

```c
bool __fastcall SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl::GetValue(
        SystemSettings::BatteryUsageHandlers::BrightnessDimmingControl *this)
{
  DWORD ActiveScheme; // ebx
  GUID *v2; // rcx
  DWORD v3; // eax
  bool v4; // bl
  GUID **p_SchemeGuid; // [rsp+40h] [rbp-20h] BYREF
  GUID *ActivePolicyGuid; // [rsp+48h] [rbp-18h] BYREF
  char v8; // [rsp+50h] [rbp-10h]
  unsigned int Buffer; // [rsp+78h] [rbp+18h] BYREF
  DWORD BufferSize; // [rsp+80h] [rbp+20h] BYREF
  GUID *SchemeGuid; // [rsp+88h] [rbp+28h] BYREF

  SchemeGuid = 0;
  p_SchemeGuid = &SchemeGuid;
  Buffer = 0;
  BufferSize = 4;
  ActivePolicyGuid = 0;
  v8 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_SchemeGuid);
  v2 = SchemeGuid;
  if ( ActiveScheme || !SchemeGuid )
  {
    SchemeGuid = 0;
  }
  else
  {
    v3 = PowerReadDCValue(
           0,
           SchemeGuid,
           &GUID_ENERGY_SAVER_SUBGROUP,
           &GUID_ENERGY_SAVER_BRIGHTNESS,
           0,
           (PUCHAR)&Buffer,
           &BufferSize);
    v2 = SchemeGuid;
    SchemeGuid = 0;
    if ( !v3 )
    {
      v4 = Buffer < 0x64;
      if ( v2 )
        LocalFree(v2);
      return v4;
    }
  }
  if ( v2 )
    LocalFree(v2);
  return 0;
}

```

## disassembly

```asm
0x180035d70  mov     [rsp-8+arg_0], rbx
0x180035d75  push    rbp
0x180035d76  mov     rbp, rsp
0x180035d79  sub     rsp, 60h
0x180035d7d  lea     rax, [rbp+SchemeGuid]
0x180035d81  mov     [rbp+SchemeGuid], 0
0x180035d89  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x180035d8d  mov     [rbp+var_20], rax
0x180035d91  xor     ecx, ecx; UserRootPowerKey
0x180035d93  mov     [rbp+arg_8], 0
0x180035d9a  mov     [rbp+arg_10], 4
0x180035da1  mov     [rbp+ActivePolicyGuid], 0
0x180035da9  mov     [rbp+var_10], 1
0x180035dad  call    cs:__imp_PowerGetActiveScheme
0x180035db3  lea     rcx, [rbp+var_20]
0x180035db7  mov     ebx, eax
0x180035db9  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180035dbe  mov     rcx, [rbp+SchemeGuid]; hMem
0x180035dc2  test    ebx, ebx
0x180035dc4  jnz     short loc_180035E25
0x180035dc6  test    rcx, rcx
0x180035dc9  jz      short loc_180035E25
0x180035dcb  lea     rax, [rbp+arg_10]
0x180035dcf  mov     rdx, rcx; SchemeGuid
0x180035dd2  mov     [rsp+60h+BufferSize], rax; BufferSize
0x180035dd7  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x180035dde  lea     rax, [rbp+arg_8]
0x180035de2  xor     ecx, ecx; RootPowerKey
0x180035de4  mov     [rsp+60h+Buffer], rax; Buffer
0x180035de9  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180035df0  mov     [rsp+60h+Type], 0; Type
0x180035df9  call    cs:__imp_PowerReadDCValue
0x180035dff  mov     rcx, [rbp+SchemeGuid]; hMem
0x180035e03  mov     [rbp+SchemeGuid], 0
0x180035e0b  test    eax, eax
0x180035e0d  jnz     short loc_180035E2D
0x180035e0f  cmp     [rbp+arg_8], 64h ; 'd'
0x180035e13  setb    bl
0x180035e16  test    rcx, rcx
0x180035e19  jz      short loc_180035E21
0x180035e1b  call    cs:__imp_LocalFree
0x180035e21  mov     al, bl
0x180035e23  jmp     short loc_180035E3A
0x180035e25  mov     [rbp+SchemeGuid], 0
0x180035e2d  test    rcx, rcx
0x180035e30  jz      short loc_180035E38
0x180035e32  call    cs:__imp_LocalFree
0x180035e38  xor     al, al
0x180035e3a  mov     rbx, [rsp+60h+arg_0]
0x180035e3f  add     rsp, 60h
0x180035e43  pop     rbp
0x180035e44  retn
```
