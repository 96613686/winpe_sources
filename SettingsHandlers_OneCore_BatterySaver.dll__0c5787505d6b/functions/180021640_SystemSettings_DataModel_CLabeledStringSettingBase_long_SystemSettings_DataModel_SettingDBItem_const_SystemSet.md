# SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x180021640`
- end: `0x180021768`
- name: `?GetValue@?$CLabeledStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18000eacc`
- `0x18001d140`
- `0x180021640`
- `0x180023fb0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002167f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800216c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021715`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002167f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800216c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021706`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021715`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
        __int64 *a1,
        SystemSettings::DataModel *a2,
        unsigned __int16 *a3)
{
  bool IsHstringEqual; // al
  __int64 v7; // r14
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *(_QWORD *)a3 = 0;
  IsHstringEqual = SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180057650, a3);
  try
  {
    v7 = *a1;
    if ( IsHstringEqual )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v8 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v7 + 264))(a1, &string);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC22,
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v8,
          v16);
        WindowsDeleteString(string);
        return v9;
      }
      v12 = SystemSettings::DataModel::PropValueHelper::CreateString(string, (struct IInspectable **)a3);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC23,
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v12,
          v16);
        WindowsDeleteString(string);
        return v13;
      }
      WindowsDeleteString(string);
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(__int64 *, SystemSettings::DataModel *, unsigned __int16 *))(v7 + 240))(
              a1,
              a2,
              a3);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC27,
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v14,
          v16);
        return v15;
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC2C,
                           (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180021640  push    rbx
0x180021642  push    rsi
0x180021643  push    rdi
0x180021644  push    r14
0x180021646  sub     rsp, 28h
0x18002164a  mov     rdi, r8
0x18002164d  mov     rsi, rdx
0x180021650  mov     rbx, rcx
0x180021653  mov     qword ptr [r8], 0
0x18002165a  lea     rdx, stru_180057650; HSTRING
0x180021661  mov     rcx, rsi; this
0x180021664  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180021669  mov     r14, [rbx]
0x18002166c  test    al, al
0x18002166e  jz      loc_18002171D
0x180021674  mov     [rsp+48h+string], 0
0x18002167d  xor     ecx, ecx; string
0x18002167f  call    cs:__imp_WindowsDeleteString
0x180021685  mov     [rsp+48h+string], 0
0x18002168e  lea     rdx, [rsp+48h+string]
0x180021693  mov     rcx, rbx
0x180021696  mov     rax, [r14+108h]
0x18002169d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216a2  mov     ebx, eax
0x1800216a4  test    eax, eax
0x1800216a6  jns     short loc_1800216D4
0x1800216a8  mov     rcx, [rsp+48h]; this
0x1800216ad  mov     r9d, eax; char *
0x1800216b0  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x1800216b7  mov     edx, 0C22h; void *
0x1800216bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800216c1  nop
0x1800216c2  mov     rcx, [rsp+48h+string]; string
0x1800216c7  call    cs:__imp_WindowsDeleteString
0x1800216cd  mov     eax, ebx
0x1800216cf  jmp     loc_18002175D
0x1800216d4  mov     rdx, rdi; struct IInspectable **
0x1800216d7  mov     rcx, [rsp+48h+string]; HSTRING
0x1800216dc  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800216e1  mov     ebx, eax
0x1800216e3  test    eax, eax
0x1800216e5  jns     short loc_180021710
0x1800216e7  mov     rcx, [rsp+48h]; this
0x1800216ec  mov     r9d, eax; char *
0x1800216ef  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x1800216f6  mov     edx, 0C23h; void *
0x1800216fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021700  nop
0x180021701  mov     rcx, [rsp+48h+string]; string
0x180021706  call    cs:__imp_WindowsDeleteString
0x18002170c  mov     eax, ebx
0x18002170e  jmp     short loc_18002175D
0x180021710  mov     rcx, [rsp+48h+string]; string
0x180021715  call    cs:__imp_WindowsDeleteString
0x18002171b  jmp     short loc_180021755
0x18002171d  mov     r8, rdi
0x180021720  mov     rdx, rsi
0x180021723  mov     rcx, rbx
0x180021726  mov     rax, [r14+0F0h]
0x18002172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021732  mov     ebx, eax
0x180021734  test    eax, eax
0x180021736  jns     short loc_180021755
0x180021738  mov     rcx, [rsp+48h]; this
0x18002173d  mov     r9d, eax; char *
0x180021740  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x180021747  mov     edx, 0C27h; void *
0x18002174c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021751  mov     eax, ebx
0x180021753  jmp     short loc_18002175D
0x180021755  xor     eax, eax
0x180021757  jmp     short loc_18002175D
0x180021759  mov     eax, dword ptr [rsp+48h+string]
0x18002175d  add     rsp, 28h
0x180021761  pop     r14
0x180021763  pop     rdi
0x180021764  pop     rsi
0x180021765  pop     rbx
0x180021766  retn
```
