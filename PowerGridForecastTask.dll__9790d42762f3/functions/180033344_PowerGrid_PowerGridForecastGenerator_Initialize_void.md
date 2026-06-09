# PowerGrid::PowerGridForecastGenerator::Initialize(void)

- ea: `0x180033344`
- end: `0x180033449`
- name: `?Initialize@PowerGridForecastGenerator@PowerGrid@@QEAAJXZ`
- size: `261`
- prototype: `__int64 __fastcall(PowerGrid::PowerGridForecastGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fa90`

## callees

- `0x18002dcd4`
- `0x180033344`
- `0x180033450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800333a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800333fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800333a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800333fa`

## string_xrefs

- `0x18003336e`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x1800333ea`: `SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
- `0x18003341a`: `onecore\base\sustainability\tasks\deferredcharging\dll\powergridforecastoutputter.cpp`

## pseudocode

```c
__int64 __fastcall PowerGrid::PowerGridForecastGenerator::Initialize(PowerGrid::PowerGridForecastGenerator *this)
{
  int ValueW; // eax
  bool v3; // sf
  __int64 v4; // rdx
  bool v5; // sf
  int v6; // eax
  int v7; // ecx
  __int64 result; // rax
  int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF

  *((_DWORD *)this + 8) = PowerGrid::PowerGridForecastGenerator::InitializeCarbonForecast(this);
  pvData = 0;
  v13 = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
             L"ActiveHoursStart",
             0x18u,
             0,
             &pvData,
             &pcbData);
  v3 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v3 = ValueW < 0;
  }
  if ( v3 )
  {
    v4 = 159;
  }
  else
  {
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\WindowsUpdate\\UX\\Settings",
               L"ActiveHoursEnd",
               0x18u,
               0,
               &v13,
               &pcbData);
    v5 = ValueW < 0;
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v5 = ValueW < 0;
    }
    if ( !v5 )
    {
      v6 = pvData;
      v7 = v13;
      goto LABEL_11;
    }
    v4 = 170;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\powergridforecastoutputter.cpp",
    (const char *)(unsigned int)ValueW,
    pdwType);
  v6 = 8;
  v7 = 22;
LABEL_11:
  *((_DWORD *)this + 6) = v6;
  result = 0;
  *((_DWORD *)this + 7) = v7;
  return result;
}

```

## disassembly

```asm
0x180033344  push    rbx
0x180033346  sub     rsp, 40h
0x18003334a  mov     rbx, rcx
0x18003334d  call    ?InitializeCarbonForecast@PowerGridForecastGenerator@PowerGrid@@AEAAJXZ; PowerGrid::PowerGridForecastGenerator::InitializeCarbonForecast(void)
0x180033352  mov     [rbx+20h], eax
0x180033355  lea     r8, aActivehourssta; "ActiveHoursStart"
0x18003335c  lea     rax, [rsp+48h+arg_0]
0x180033361  mov     [rsp+48h+arg_8], 0
0x180033369  mov     [rsp+48h+pcbData], rax; pcbData
0x18003336e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x180033375  lea     rax, [rsp+48h+arg_8]
0x18003337a  mov     [rsp+48h+arg_10], 0
0x180033382  mov     [rsp+48h+pvData], rax; pvData
0x180033387  mov     r9d, 18h; dwFlags
0x18003338d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180033394  mov     [rsp+48h+pdwType], 0; pdwType
0x18003339d  mov     [rsp+48h+arg_0], 4
0x1800333a5  call    cs:__imp_RegGetValueW
0x1800333ab  test    eax, eax
0x1800333ad  jle     short loc_1800333B9
0x1800333af  movzx   eax, ax
0x1800333b2  or      eax, 80070000h
0x1800333b7  test    eax, eax
0x1800333b9  jns     short loc_1800333C2
0x1800333bb  mov     edx, 9Fh
0x1800333c0  jmp     short loc_180033415
0x1800333c2  lea     rax, [rsp+48h+arg_0]
0x1800333c7  mov     r9d, 18h; dwFlags
0x1800333cd  mov     [rsp+48h+pcbData], rax; pcbData
0x1800333d2  lea     r8, aActivehoursend; "ActiveHoursEnd"
0x1800333d9  lea     rax, [rsp+48h+arg_10]
0x1800333de  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800333e5  mov     [rsp+48h+pvData], rax; pvData
0x1800333ea  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WindowsUpdate\\UX"...
0x1800333f1  mov     [rsp+48h+pdwType], 0; int
0x1800333fa  call    cs:__imp_RegGetValueW
0x180033400  test    eax, eax
0x180033402  jle     short loc_18003340E
0x180033404  movzx   eax, ax
0x180033407  or      eax, 80070000h
0x18003340c  test    eax, eax
0x18003340e  jns     short loc_180033433
0x180033410  mov     edx, 0AAh; void *
0x180033415  mov     rcx, [rsp+48h]; this
0x18003341a  lea     r8, aOnecoreBaseSus_1; "onecore\\base\\sustainability\\tasks\\d"...
0x180033421  mov     r9d, eax; char *
0x180033424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033429  mov     eax, 8
0x18003342e  lea     ecx, [rax+0Eh]
0x180033431  jmp     short loc_18003343B
0x180033433  mov     eax, [rsp+48h+arg_8]
0x180033437  mov     ecx, [rsp+48h+arg_10]
0x18003343b  mov     [rbx+18h], eax
0x18003343e  xor     eax, eax
0x180033440  mov     [rbx+1Ch], ecx
0x180033443  add     rsp, 40h
0x180033447  pop     rbx
0x180033448  retn
```
