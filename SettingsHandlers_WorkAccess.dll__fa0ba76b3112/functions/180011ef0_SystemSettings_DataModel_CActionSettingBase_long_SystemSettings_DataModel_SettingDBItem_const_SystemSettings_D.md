# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x180011ef0`
- end: `0x1800120c3`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x1800119c0`
- `0x180011ef0`
- `0x1800136e8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011f9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011f9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011fe7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012003`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012089`

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
0x180011ef0  mov     [rsp+arg_10], rbx
0x180011ef5  mov     [rsp+arg_18], rsi
0x180011efa  push    rdi
0x180011efb  sub     rsp, 250h
0x180011f02  mov     rax, cs:__security_cookie
0x180011f09  xor     rax, rsp
0x180011f0c  mov     [rsp+258h+var_18], rax
0x180011f14  mov     rsi, rdx
0x180011f17  mov     rdi, rcx
0x180011f1a  mov     qword ptr [rdx], 0
0x180011f21  mov     [rsp+258h+string], 0
0x180011f2a  mov     rax, [rcx]
0x180011f2d  mov     rbx, [rax+30h]
0x180011f31  xor     ecx, ecx; string
0x180011f33  call    cs:__imp_WindowsDeleteString
0x180011f3a  nop     dword ptr [rax+rax+00h]
0x180011f3f  mov     [rsp+258h+string], 0; int
0x180011f48  lea     rdx, [rsp+258h+string]
0x180011f4d  mov     rcx, rdi
0x180011f50  mov     rax, rbx
0x180011f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f58  mov     ebx, eax
0x180011f5a  test    eax, eax
0x180011f5c  jns     short loc_180011F93
0x180011f5e  mov     rcx, [rsp+258h]; this
0x180011f66  mov     r9d, eax; char *
0x180011f69  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180011f70  mov     edx, 821h; void *
0x180011f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f7a  nop
0x180011f7b  mov     rcx, [rsp+258h+string]; string
0x180011f80  call    cs:__imp_WindowsDeleteString
0x180011f87  nop     dword ptr [rax+rax+00h]
0x180011f8c  mov     eax, ebx
0x180011f8e  jmp     loc_18001209D
0x180011f93  xor     edx, edx; length
0x180011f95  mov     rcx, [rsp+258h+string]; string
0x180011f9a  call    cs:__imp_WindowsGetStringRawBuffer
0x180011fa1  nop     dword ptr [rax+rax+00h]
0x180011fa6  mov     r9, rax
0x180011fa9  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x180011fb0  mov     edx, 104h; unsigned __int64
0x180011fb5  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x180011fba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011fbf  mov     ebx, eax
0x180011fc1  test    eax, eax
0x180011fc3  jns     short loc_180011FFA
0x180011fc5  mov     rcx, [rsp+258h]; this
0x180011fcd  mov     r9d, eax; char *
0x180011fd0  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180011fd7  mov     edx, 827h; void *
0x180011fdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011fe1  nop
0x180011fe2  mov     rcx, [rsp+258h+string]; string
0x180011fe7  call    cs:__imp_WindowsDeleteString
0x180011fee  nop     dword ptr [rax+rax+00h]
0x180011ff3  mov     eax, ebx
0x180011ff5  jmp     loc_18001209D
0x180011ffa  mov     qword ptr [rsi], 0
0x180012001  xor     ecx, ecx; string
0x180012003  call    cs:__imp_WindowsDeleteString
0x18001200a  nop     dword ptr [rax+rax+00h]
0x18001200f  mov     [rsp+258h+var_230], 0
0x180012018  lea     rdx, [rsp+258h+var_230]; HSTRING *
0x18001201d  lea     rcx, [rsp+258h+var_228]; this
0x180012022  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180012027  mov     edi, eax
0x180012029  mov     rbx, [rsp+258h+var_230]
0x18001202e  test    eax, eax
0x180012030  js      short loc_18001203F
0x180012032  mov     rdx, rsi; struct IInspectable **
0x180012035  mov     rcx, rbx; HSTRING
0x180012038  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001203d  mov     edi, eax
0x18001203f  mov     rcx, rbx; string
0x180012042  call    cs:__imp_WindowsDeleteString
0x180012049  nop     dword ptr [rax+rax+00h]
0x18001204e  test    edi, edi
0x180012050  jns     short loc_180012084
0x180012052  mov     rcx, [rsp+258h]; this
0x18001205a  mov     r9d, edi; char *
0x18001205d  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180012064  mov     edx, 828h; void *
0x180012069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001206e  nop
0x18001206f  mov     rcx, [rsp+258h+string]; string
0x180012074  call    cs:__imp_WindowsDeleteString
0x18001207b  nop     dword ptr [rax+rax+00h]
0x180012080  mov     eax, edi
0x180012082  jmp     short loc_18001209D
0x180012084  mov     rcx, [rsp+258h+string]; string
0x180012089  call    cs:__imp_WindowsDeleteString
0x180012090  nop     dword ptr [rax+rax+00h]
0x180012095  xor     eax, eax
0x180012097  jmp     short loc_18001209D
0x180012099  mov     eax, dword ptr [rsp+258h+string]
0x18001209d  mov     rcx, [rsp+258h+var_18]
0x1800120a5  xor     rcx, rsp; StackCookie
0x1800120a8  call    __security_check_cookie
0x1800120ad  lea     r11, [rsp+258h+var_8]
0x1800120b5  mov     rbx, [r11+20h]
0x1800120b9  mov     rsi, [r11+28h]
0x1800120bd  mov     rsp, r11
0x1800120c0  pop     rdi
0x1800120c1  retn
```
