# SystemSettings::DataModel::Details::GetSettingImpl<41>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[41],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x180004f9c`
- end: `0x1800050fc`
- name: `??$GetSettingImpl@$0CJ@@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY0CJ@$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `352`
- prototype: `__int64 __fastcall(HSTRING string, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x180004cfc`
- `0x180004f9c`
- `0x18000a160`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800050b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800050b8`

## string_xrefs

- `0x180005076`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`
- `0x1800050dc`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<41>(HSTRING string, __int64 a2, _QWORD *a3)
{
  PCWSTR StringRawBuffer; // r10
  __int64 *v6; // rdi
  __int64 v7; // r8
  _WORD *v8; // rcx
  _WORD *v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rax
  const char *v16; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 v18; // [rsp+58h] [rbp+10h] BYREF
  int v19; // [rsp+5Ch] [rbp+14h]
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = HIDWORD(a2);
  *a3 = 0;
  v18 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &v18);
  v6 = (__int64 *)&off_1800784D0;
  while ( 1 )
  {
    v7 = v6[1];
    if ( v18 == v7 )
      break;
LABEL_6:
    v6 += 3;
    if ( v6 == &qword_1800788A8 )
      goto LABEL_7;
  }
  v8 = &StringRawBuffer[v18];
  v9 = (_WORD *)(*v6 + 2 * v7);
  while ( v8 != StringRawBuffer )
  {
    if ( *--v8 != *--v9 )
      goto LABEL_6;
  }
LABEL_7:
  if ( v6 == &qword_1800788A8 )
  {
    v16 = (const char *)WindowsGetStringRawBuffer(string, 0);
    v12 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)0x80070057LL,
      (int)"%ls",
      v16);
  }
  else
  {
    v10 = v6[2];
    v20 = 0;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v10 + 40) + 8LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v12 = v11(v10, &v20);
    if ( v12 >= 0 )
    {
      v14 = v20;
      v20 = 0;
      *a3 = v14;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      return 0;
    }
    v13 = (const char *)WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)(unsigned int)v12,
      (int)"%ls",
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004f9c  mov     rax, rsp
0x180004f9f  mov     [rax+8], rbx
0x180004fa3  mov     [rax+10h], rdx
0x180004fa7  push    rbp
0x180004fa8  push    rsi
0x180004fa9  push    rdi
0x180004faa  sub     rsp, 30h
0x180004fae  mov     rsi, r8
0x180004fb1  mov     rbp, rcx
0x180004fb4  mov     qword ptr [r8], 0
0x180004fbb  mov     dword ptr [rax+10h], 0
0x180004fc2  lea     rdx, [rax+10h]; length
0x180004fc6  call    cs:__imp_WindowsGetStringRawBuffer
0x180004fcc  mov     r10, rax
0x180004fcf  lea     rdi, off_1800784D0; "SystemSettings_BatterySaver_BatteryGrap"...
0x180004fd6  mov     r9d, [rsp+48h+arg_8]
0x180004fdb  lea     r11, qword_1800788A8
0x180004fe2  mov     r8, [rdi+8]
0x180004fe6  cmp     r9, r8
0x180004fe9  jnz     short loc_18000500B
0x180004feb  lea     rcx, [r10+r9*2]
0x180004fef  mov     rdx, [rdi]
0x180004ff2  lea     rdx, [rdx+r8*2]
0x180004ff6  cmp     rcx, r10
0x180004ff9  jz      short loc_180005014
0x180004ffb  add     rdx, 0FFFFFFFFFFFFFFFEh
0x180004fff  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180005003  movzx   eax, word ptr [rdx]
0x180005006  cmp     [rcx], ax
0x180005009  jz      short loc_180004FF6
0x18000500b  add     rdi, 18h
0x18000500f  cmp     rdi, r11
0x180005012  jnz     short loc_180004FE2
0x180005014  cmp     rdi, r11
0x180005017  jz      loc_1800050B3
0x18000501d  mov     rdi, [rdi+10h]
0x180005021  mov     [rsp+48h+arg_10], 0
0x18000502a  mov     rax, [rdi+28h]
0x18000502e  mov     rbx, [rax+8]
0x180005032  lea     rcx, [rsp+48h+arg_10]
0x180005037  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000503c  lea     rdx, [rsp+48h+arg_10]
0x180005041  mov     rcx, rdi
0x180005044  mov     rax, rbx
0x180005047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504c  mov     ebx, eax
0x18000504e  test    eax, eax
0x180005050  jns     short loc_180005094
0x180005052  xor     edx, edx; length
0x180005054  mov     rcx, rbp; string
0x180005057  call    cs:__imp_WindowsGetStringRawBuffer
0x18000505d  mov     rcx, [rsp+48h]; this
0x180005062  mov     [rsp+48h+var_20], rax; char *
0x180005067  lea     rdx, aLs; "%ls"
0x18000506e  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180005073  mov     r9d, ebx; char *
0x180005076  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000507d  mov     edx, 0E1h; void *
0x180005082  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005087  nop
0x180005088  lea     rcx, [rsp+48h+arg_10]
0x18000508d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005092  jmp     short loc_1800050ED
0x180005094  mov     rax, [rsp+48h+arg_10]
0x180005099  mov     [rsp+48h+arg_10], 0
0x1800050a2  mov     [rsi], rax
0x1800050a5  lea     rcx, [rsp+48h+arg_10]
0x1800050aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800050af  xor     eax, eax
0x1800050b1  jmp     short loc_1800050EF
0x1800050b3  xor     edx, edx; length
0x1800050b5  mov     rcx, rbp; string
0x1800050b8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800050be  mov     rcx, [rsp+48h]; this
0x1800050c3  mov     [rsp+48h+var_20], rax; char *
0x1800050c8  lea     rdx, aLs; "%ls"
0x1800050cf  mov     qword ptr [rsp+48h+var_28], rdx; int
0x1800050d4  mov     ebx, 80070057h
0x1800050d9  mov     r9d, ebx; char *
0x1800050dc  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800050e3  mov     edx, 0DCh; void *
0x1800050e8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800050ed  mov     eax, ebx
0x1800050ef  mov     rbx, [rsp+48h+arg_0]
0x1800050f4  add     rsp, 30h
0x1800050f8  pop     rdi
0x1800050f9  pop     rsi
0x1800050fa  pop     rbp
0x1800050fb  retn
```
