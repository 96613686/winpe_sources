# SystemSettings::BatterySaverOneCoreDataModel::CBatteryPowerOverlaySliderControl::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x18001f7c0`
- end: `0x18001f88c`
- name: `?GetNamedValue@CBatteryPowerOverlaySliderControl@BatterySaverOneCoreDataModel@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `204`
- prototype: `int(SystemSettings::BatterySaverOneCoreDataModel::CBatteryPowerOverlaySliderControl *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d140`
- `0x18001f7c0`
- `0x180023fb0`
- `0x1800280c0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f874`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatteryPowerOverlaySliderControl::GetNamedValue(
        SystemSettings::BatterySaverOneCoreDataModel::CBatteryPowerOverlaySliderControl *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  const unsigned __int16 *v8; // rdx
  UINT32 v9; // r8d
  HSTRING v10; // rcx
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  string = 0;
  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180056708, (const unsigned __int16 *)a3) )
  {
    v6 = (*(__int64 (__fastcall **)(SystemSettings::BatterySaverOneCoreDataModel::CBatteryPowerOverlaySliderControl *))(*(_QWORD *)this + 264LL))(this)
       - 100;
    if ( v6 )
    {
      v7 = v6 - 100;
      if ( v7 )
      {
        if ( v7 == 100 )
        {
          v8 = L"SystemSettings_PowerAndSleep_OverlaySlider_Label_BestPerformance";
          v9 = 64;
        }
        else
        {
          v8 = &word_180054D68;
          v9 = 0;
        }
      }
      else
      {
        v8 = L"SystemSettings_PowerAndSleep_OverlaySlider_Label_BetterPerformance";
        v9 = 66;
      }
    }
    else
    {
      v8 = L"SystemSettings_PowerAndSleep_OverlaySlider_Label_Balanced";
      v9 = 57;
    }
    Microsoft::WRL::Wrappers::HString::Set(&string, v8, v9);
    v10 = string;
    string = 0;
    v5 = SystemSettings::DataModel::PropValueHelper::CreateString(v10, a3);
  }
  WindowsDeleteString(string);
  return v5;
}

```

## disassembly

```asm
0x18001f7c0  mov     [rsp+arg_0], rbx
0x18001f7c5  mov     [rsp+arg_8], rsi
0x18001f7ca  push    rdi
0x18001f7cb  sub     rsp, 20h
0x18001f7cf  mov     rsi, r8
0x18001f7d2  mov     rax, rdx
0x18001f7d5  mov     rdi, rcx
0x18001f7d8  xor     ebx, ebx
0x18001f7da  mov     [rsp+28h+string], rbx
0x18001f7df  mov     [r8], rbx
0x18001f7e2  lea     rdx, stru_180056708; HSTRING
0x18001f7e9  mov     rcx, rax; this
0x18001f7ec  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18001f7f1  test    al, al
0x18001f7f3  jz      short loc_18001F86F
0x18001f7f5  mov     rax, [rdi]
0x18001f7f8  mov     rcx, rdi
0x18001f7fb  mov     rax, [rax+108h]
0x18001f802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f807  sub     eax, 64h ; 'd'
0x18001f80a  jz      short loc_18001F840
0x18001f80c  sub     eax, 64h ; 'd'
0x18001f80f  jz      short loc_18001F831
0x18001f811  cmp     eax, 64h ; 'd'
0x18001f814  jz      short loc_18001F822
0x18001f816  lea     rdx, word_180054D68
0x18001f81d  xor     r8d, r8d
0x18001f820  jmp     short loc_18001F84D
0x18001f822  lea     rdx, aSystemsettings_23; "SystemSettings_PowerAndSleep_OverlaySli"...
0x18001f829  mov     r8d, 40h ; '@'
0x18001f82f  jmp     short loc_18001F84D
0x18001f831  lea     rdx, aSystemsettings_1; "SystemSettings_PowerAndSleep_OverlaySli"...
0x18001f838  mov     r8d, 42h ; 'B'
0x18001f83e  jmp     short loc_18001F84D
0x18001f840  lea     rdx, aSystemsettings_11; "SystemSettings_PowerAndSleep_OverlaySli"...
0x18001f847  mov     r8d, 39h ; '9'; unsigned int
0x18001f84d  lea     rcx, [rsp+28h+string]; this
0x18001f852  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001f857  mov     rcx, [rsp+28h+string]; HSTRING
0x18001f85c  mov     [rsp+28h+string], 0
0x18001f865  mov     rdx, rsi; struct IInspectable **
0x18001f868  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001f86d  mov     ebx, eax
0x18001f86f  mov     rcx, [rsp+28h+string]; string
0x18001f874  call    cs:__imp_WindowsDeleteString
0x18001f87a  mov     eax, ebx
0x18001f87c  mov     rbx, [rsp+28h+arg_0]
0x18001f881  mov     rsi, [rsp+28h+arg_8]
0x18001f886  add     rsp, 20h
0x18001f88a  pop     rdi
0x18001f88b  retn
```
