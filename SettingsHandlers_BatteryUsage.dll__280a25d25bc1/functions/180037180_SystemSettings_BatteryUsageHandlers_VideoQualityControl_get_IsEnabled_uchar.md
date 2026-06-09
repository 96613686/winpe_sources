# SystemSettings::BatteryUsageHandlers::VideoQualityControl::get_IsEnabled(uchar *)

- ea: `0x180037180`
- end: `0x180037254`
- name: `?get_IsEnabled@VideoQualityControl@BatteryUsageHandlers@SystemSettings@@UEAAJPEAE@Z`
- size: `212`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::VideoQualityControl *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1800228bc`
- `0x180037180`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003723c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003723c`
- `POWRPROF!PowerGetActiveScheme` at `0x1800371c5`
- `POWRPROF!PowerGetActiveScheme` at `0x1800371c5`
- `POWRPROF!PowerReadDCValue` at `0x180037211`
- `POWRPROF!PowerReadDCValue` at `0x180037211`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::VideoQualityControl::get_IsEnabled(
        SystemSettings::BatteryUsageHandlers::VideoQualityControl *this,
        unsigned __int8 *a2)
{
  DWORD ActiveScheme; // ebx
  GUID *v4; // rcx
  DWORD v5; // eax
  GUID *SchemeGuid; // [rsp+40h] [rbp-20h] BYREF
  GUID **p_SchemeGuid; // [rsp+48h] [rbp-18h] BYREF
  GUID *ActivePolicyGuid; // [rsp+50h] [rbp-10h] BYREF
  char v10; // [rsp+58h] [rbp-8h]
  DWORD BufferSize; // [rsp+80h] [rbp+20h] BYREF
  int Buffer; // [rsp+88h] [rbp+28h] BYREF

  SchemeGuid = 0;
  Buffer = 0;
  p_SchemeGuid = &SchemeGuid;
  BufferSize = 4;
  ActivePolicyGuid = 0;
  v10 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_SchemeGuid);
  v4 = SchemeGuid;
  if ( ActiveScheme || !SchemeGuid )
  {
    SchemeGuid = 0;
  }
  else
  {
    v5 = PowerReadDCValue(
           0,
           SchemeGuid,
           &GUID_MULTIMEDIA_SUBGROUP,
           &GUID_VIDEO_PLAYBACK_QUALITY_BIAS,
           0,
           (PUCHAR)&Buffer,
           &BufferSize);
    v4 = SchemeGuid;
    SchemeGuid = 0;
    if ( !v5 )
    {
      *a2 = 1;
      goto LABEL_7;
    }
  }
  *a2 = 0;
LABEL_7:
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x180037180  mov     [rsp-8+arg_0], rbx
0x180037185  mov     [rsp-8+arg_8], rdi
0x18003718a  push    rbp
0x18003718b  mov     rbp, rsp
0x18003718e  sub     rsp, 60h
0x180037192  mov     rdi, rdx
0x180037195  mov     [rbp+SchemeGuid], 0
0x18003719d  lea     rax, [rbp+SchemeGuid]
0x1800371a1  mov     [rbp+arg_18], 0
0x1800371a8  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x1800371ac  mov     [rbp+var_18], rax
0x1800371b0  xor     ecx, ecx; UserRootPowerKey
0x1800371b2  mov     [rbp+arg_10], 4
0x1800371b9  mov     [rbp+ActivePolicyGuid], 0
0x1800371c1  mov     [rbp+var_8], 1
0x1800371c5  call    cs:__imp_PowerGetActiveScheme
0x1800371cb  lea     rcx, [rbp+var_18]
0x1800371cf  mov     ebx, eax
0x1800371d1  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800371d6  mov     rcx, [rbp+SchemeGuid]; hMem
0x1800371da  test    ebx, ebx
0x1800371dc  jnz     short loc_18003722C
0x1800371de  test    rcx, rcx
0x1800371e1  jz      short loc_18003722C
0x1800371e3  lea     rax, [rbp+arg_10]
0x1800371e7  mov     rdx, rcx; SchemeGuid
0x1800371ea  mov     [rsp+60h+BufferSize], rax; BufferSize
0x1800371ef  lea     r9, GUID_VIDEO_PLAYBACK_QUALITY_BIAS; PowerSettingGuid
0x1800371f6  lea     rax, [rbp+arg_18]
0x1800371fa  xor     ecx, ecx; RootPowerKey
0x1800371fc  mov     [rsp+60h+Buffer], rax; Buffer
0x180037201  lea     r8, GUID_MULTIMEDIA_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180037208  mov     [rsp+60h+Type], 0; Type
0x180037211  call    cs:__imp_PowerReadDCValue
0x180037217  mov     rcx, [rbp+SchemeGuid]
0x18003721b  mov     [rbp+SchemeGuid], 0
0x180037223  test    eax, eax
0x180037225  jnz     short loc_180037234
0x180037227  mov     byte ptr [rdi], 1
0x18003722a  jmp     short loc_180037237
0x18003722c  mov     [rbp+SchemeGuid], 0
0x180037234  mov     byte ptr [rdi], 0
0x180037237  test    rcx, rcx
0x18003723a  jz      short loc_180037242
0x18003723c  call    cs:__imp_LocalFree
0x180037242  mov     rbx, [rsp+60h+arg_0]
0x180037247  xor     eax, eax
0x180037249  mov     rdi, [rsp+60h+arg_8]
0x18003724e  add     rsp, 60h
0x180037252  pop     rbp
0x180037253  retn
```
