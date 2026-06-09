# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x1802ae0d0`
- end: `0x1802ae273`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18001aca4`
- `0x180057570`
- `0x180201e50`
- `0x1802ada68`
- `0x1802ae0d0`
- `0x1802b1340`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae1b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae23f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae113`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae15a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae1b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802ae23f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ae16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802ae16e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(
        __int64 a1,
        struct IInspectable **a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HSTRING *v11; // r8
  int ResourceStringById; // edi
  HSTRING v13; // rbx
  HSTRING string; // [rsp+20h] [rbp-238h] BYREF
  HSTRING v15; // [rsp+28h] [rbp-230h] BYREF
  unsigned __int16 v16[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a2 = 0;
  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = StringCchPrintfW(v16, 0x104u, L"%ws_ActionDescription", StringRawBuffer);
    v10 = v9;
    if ( v9 >= 0 )
    {
      *a2 = 0;
      WindowsDeleteString(0);
      v15 = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v16, &v15, v11);
      v13 = v15;
      if ( ResourceStringById >= 0 )
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v15, a2);
      WindowsDeleteString(v13);
      if ( ResourceStringById >= 0 )
      {
        WindowsDeleteString(string);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x828,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)ResourceStringById,
          (int)string);
        WindowsDeleteString(string);
        return (unsigned int)ResourceStringById;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x827,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        (const char *)(unsigned int)v9,
        (int)string);
      WindowsDeleteString(string);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x821,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
      (const char *)(unsigned int)v5,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x1802ae0d0  mov     [rsp+arg_10], rbx
0x1802ae0d5  mov     [rsp+arg_18], rsi
0x1802ae0da  push    rdi
0x1802ae0db  sub     rsp, 250h
0x1802ae0e2  mov     rax, cs:__security_cookie
0x1802ae0e9  xor     rax, rsp
0x1802ae0ec  mov     [rsp+258h+var_18], rax
0x1802ae0f4  mov     rsi, rdx
0x1802ae0f7  mov     rdi, rcx
0x1802ae0fa  mov     qword ptr [rdx], 0
0x1802ae101  mov     [rsp+258h+string], 0
0x1802ae10a  mov     rax, [rcx]
0x1802ae10d  mov     rbx, [rax+30h]
0x1802ae111  xor     ecx, ecx; string
0x1802ae113  call    cs:__imp_WindowsDeleteString
0x1802ae119  mov     [rsp+258h+string], 0; int
0x1802ae122  lea     rdx, [rsp+258h+string]
0x1802ae127  mov     rcx, rdi
0x1802ae12a  mov     rax, rbx
0x1802ae12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802ae132  mov     ebx, eax
0x1802ae134  test    eax, eax
0x1802ae136  jns     short loc_1802AE167
0x1802ae138  mov     rcx, [rsp+258h]; this
0x1802ae140  mov     r9d, eax; char *
0x1802ae143  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802ae14a  mov     edx, 821h; void *
0x1802ae14f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ae154  nop
0x1802ae155  mov     rcx, [rsp+258h+string]; string
0x1802ae15a  call    cs:__imp_WindowsDeleteString
0x1802ae160  mov     eax, ebx
0x1802ae162  jmp     loc_1802AE24D
0x1802ae167  xor     edx, edx; length
0x1802ae169  mov     rcx, [rsp+258h+string]; string
0x1802ae16e  call    cs:__imp_WindowsGetStringRawBuffer
0x1802ae174  mov     r9, rax
0x1802ae177  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x1802ae17e  mov     edx, 104h; unsigned __int64
0x1802ae183  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1802ae188  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802ae18d  mov     ebx, eax
0x1802ae18f  test    eax, eax
0x1802ae191  jns     short loc_1802AE1C2
0x1802ae193  mov     rcx, [rsp+258h]; this
0x1802ae19b  mov     r9d, eax; char *
0x1802ae19e  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802ae1a5  mov     edx, 827h; void *
0x1802ae1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ae1af  nop
0x1802ae1b0  mov     rcx, [rsp+258h+string]; string
0x1802ae1b5  call    cs:__imp_WindowsDeleteString
0x1802ae1bb  mov     eax, ebx
0x1802ae1bd  jmp     loc_1802AE24D
0x1802ae1c2  mov     qword ptr [rsi], 0
0x1802ae1c9  xor     ecx, ecx; string
0x1802ae1cb  call    cs:__imp_WindowsDeleteString
0x1802ae1d1  mov     [rsp+258h+var_230], 0
0x1802ae1da  lea     rdx, [rsp+258h+var_230]; HSTRING *
0x1802ae1df  lea     rcx, [rsp+258h+var_228]; this
0x1802ae1e4  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1802ae1e9  mov     edi, eax
0x1802ae1eb  mov     rbx, [rsp+258h+var_230]
0x1802ae1f0  test    eax, eax
0x1802ae1f2  js      short loc_1802AE201
0x1802ae1f4  mov     rdx, rsi; struct IInspectable **
0x1802ae1f7  mov     rcx, rbx; HSTRING
0x1802ae1fa  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1802ae1ff  mov     edi, eax
0x1802ae201  mov     rcx, rbx; string
0x1802ae204  call    cs:__imp_WindowsDeleteString
0x1802ae20a  test    edi, edi
0x1802ae20c  jns     short loc_1802AE23A
0x1802ae20e  mov     rcx, [rsp+258h]; this
0x1802ae216  mov     r9d, edi; char *
0x1802ae219  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802ae220  mov     edx, 828h; void *
0x1802ae225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ae22a  nop
0x1802ae22b  mov     rcx, [rsp+258h+string]; string
0x1802ae230  call    cs:__imp_WindowsDeleteString
0x1802ae236  mov     eax, edi
0x1802ae238  jmp     short loc_1802AE24D
0x1802ae23a  mov     rcx, [rsp+258h+string]; string
0x1802ae23f  call    cs:__imp_WindowsDeleteString
0x1802ae245  xor     eax, eax
0x1802ae247  jmp     short loc_1802AE24D
0x1802ae249  mov     eax, dword ptr [rsp+258h+string]
0x1802ae24d  mov     rcx, [rsp+258h+var_18]
0x1802ae255  xor     rcx, rsp; StackCookie
0x1802ae258  call    __security_check_cookie
0x1802ae25d  lea     r11, [rsp+258h+var_8]
0x1802ae265  mov     rbx, [r11+20h]
0x1802ae269  mov     rsi, [r11+28h]
0x1802ae26d  mov     rsp, r11
0x1802ae270  pop     rdi
0x1802ae271  retn
```
