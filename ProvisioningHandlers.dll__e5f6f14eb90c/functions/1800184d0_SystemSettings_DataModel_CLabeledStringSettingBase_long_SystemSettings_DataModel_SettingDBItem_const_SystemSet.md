# SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800184d0`
- end: `0x180018610`
- name: `?GetValue@?$CLabeledStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800087ec`
- `0x180013710`
- `0x1800184d0`
- `0x18001a1d0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001850f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001855d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001850f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001855d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185b7`

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
  IsHstringEqual = SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180035948, a3);
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
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
                           (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800184d0  push    rbx
0x1800184d2  push    rsi
0x1800184d3  push    rdi
0x1800184d4  push    r14
0x1800184d6  sub     rsp, 28h
0x1800184da  mov     rdi, r8
0x1800184dd  mov     rsi, rdx
0x1800184e0  mov     rbx, rcx
0x1800184e3  mov     qword ptr [r8], 0
0x1800184ea  lea     rdx, stru_180035948; HSTRING
0x1800184f1  mov     rcx, rsi; this
0x1800184f4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800184f9  mov     r14, [rbx]
0x1800184fc  test    al, al
0x1800184fe  jz      loc_1800185C5
0x180018504  mov     [rsp+48h+string], 0
0x18001850d  xor     ecx, ecx; string
0x18001850f  call    cs:__imp_WindowsDeleteString
0x180018516  nop     dword ptr [rax+rax+00h]
0x18001851b  mov     [rsp+48h+string], 0
0x180018524  lea     rdx, [rsp+48h+string]
0x180018529  mov     rcx, rbx
0x18001852c  mov     rax, [r14+108h]
0x180018533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018538  mov     ebx, eax
0x18001853a  test    eax, eax
0x18001853c  jns     short loc_180018570
0x18001853e  mov     rcx, [rsp+48h]; this
0x180018543  mov     r9d, eax; char *
0x180018546  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001854d  mov     edx, 0C22h; void *
0x180018552  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018557  nop
0x180018558  mov     rcx, [rsp+48h+string]; string
0x18001855d  call    cs:__imp_WindowsDeleteString
0x180018564  nop     dword ptr [rax+rax+00h]
0x180018569  mov     eax, ebx
0x18001856b  jmp     loc_180018605
0x180018570  mov     rdx, rdi; struct IInspectable **
0x180018573  mov     rcx, [rsp+48h+string]; HSTRING
0x180018578  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001857d  mov     ebx, eax
0x18001857f  test    eax, eax
0x180018581  jns     short loc_1800185B2
0x180018583  mov     rcx, [rsp+48h]; this
0x180018588  mov     r9d, eax; char *
0x18001858b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180018592  mov     edx, 0C23h; void *
0x180018597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001859c  nop
0x18001859d  mov     rcx, [rsp+48h+string]; string
0x1800185a2  call    cs:__imp_WindowsDeleteString
0x1800185a9  nop     dword ptr [rax+rax+00h]
0x1800185ae  mov     eax, ebx
0x1800185b0  jmp     short loc_180018605
0x1800185b2  mov     rcx, [rsp+48h+string]; string
0x1800185b7  call    cs:__imp_WindowsDeleteString
0x1800185be  nop     dword ptr [rax+rax+00h]
0x1800185c3  jmp     short loc_1800185FD
0x1800185c5  mov     r8, rdi
0x1800185c8  mov     rdx, rsi
0x1800185cb  mov     rcx, rbx
0x1800185ce  mov     rax, [r14+0F0h]
0x1800185d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185da  mov     ebx, eax
0x1800185dc  test    eax, eax
0x1800185de  jns     short loc_1800185FD
0x1800185e0  mov     rcx, [rsp+48h]; this
0x1800185e5  mov     r9d, eax; char *
0x1800185e8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800185ef  mov     edx, 0C27h; void *
0x1800185f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185f9  mov     eax, ebx
0x1800185fb  jmp     short loc_180018605
0x1800185fd  xor     eax, eax
0x1800185ff  jmp     short loc_180018605
0x180018601  mov     eax, dword ptr [rsp+48h+string]
0x180018605  add     rsp, 28h
0x180018609  pop     r14
0x18001860b  pop     rdi
0x18001860c  pop     rsi
0x18001860d  pop     rbx
0x18001860e  retn
```
