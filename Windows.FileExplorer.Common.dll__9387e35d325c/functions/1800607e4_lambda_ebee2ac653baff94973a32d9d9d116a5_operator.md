# _lambda_ebee2ac653baff94973a32d9d9d116a5_::operator()

- ea: `0x1800607e4`
- end: `0x1800608b5`
- name: `_lambda_ebee2ac653baff94973a32d9d9d116a5_::operator()`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005e9c0`

## callees

- `0x1800065d4`
- `0x180006b1c`
- `0x1800077c8`
- `0x18001d060`
- `0x180037780`
- `0x1800607e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006084d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006084d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006080e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060895`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006080e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060895`

## string_xrefs

- `0x18006086b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_ebee2ac653baff94973a32d9d9d116a5_::operator()(_QWORD *a1, StateRepoHelpers *a2)
{
  HSTRING *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  StateRepoHelpers *StringRawBuffer; // rax
  struct _GUID *v9; // r8
  HSTRING string; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 v12[8]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  WindowsDeleteString(0);
  string = 0;
  v5 = StateRepoHelpers::LookupStringInPropertySet(
         a2,
         (struct IInspectable *)&stru_1800913D0,
         (const unsigned __int16 *)&string,
         v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *(_OWORD *)v12 = 0;
    StringRawBuffer = (StateRepoHelpers *)WindowsGetStringRawBuffer(string, 0);
    v5 = StateRepoHelpers::ParseCLSID(StringRawBuffer, v12, v9);
    v6 = v5;
    if ( v5 >= 0 )
    {
      CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_Add<_GUID const &>(
        *a1,
        v12);
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 2729;
  }
  else
  {
    v7 = 2726;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v5,
    (int)string);
LABEL_7:
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x1800607e4  mov     [rsp+arg_10], rbx
0x1800607e9  push    rdi
0x1800607ea  sub     rsp, 40h
0x1800607ee  mov     rax, cs:__security_cookie
0x1800607f5  xor     rax, rsp
0x1800607f8  mov     [rsp+48h+var_10], rax
0x1800607fd  mov     rbx, rdx
0x180060800  mov     rdi, rcx
0x180060803  mov     [rsp+48h+string], 0
0x18006080c  xor     ecx, ecx; string
0x18006080e  call    cs:__imp_WindowsDeleteString
0x180060814  mov     [rsp+48h+string], 0; int
0x18006081d  lea     r8, [rsp+48h+string]; unsigned __int16 *
0x180060822  lea     rdx, stru_1800913D0; struct IInspectable *
0x180060829  mov     rcx, rbx; this
0x18006082c  call    ?LookupStringInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; StateRepoHelpers::LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x180060831  mov     ebx, eax
0x180060833  test    eax, eax
0x180060835  jns     short loc_18006083E
0x180060837  mov     edx, 0AA6h
0x18006083c  jmp     short loc_18006086B
0x18006083e  xorps   xmm0, xmm0
0x180060841  movups  xmmword ptr [rsp+48h+var_20], xmm0
0x180060846  xor     edx, edx; length
0x180060848  mov     rcx, [rsp+48h+string]; string
0x18006084d  call    cs:__imp_WindowsGetStringRawBuffer
0x180060853  lea     rdx, [rsp+48h+var_20]; unsigned __int16 *
0x180060858  mov     rcx, rax; this
0x18006085b  call    ?ParseCLSID@StateRepoHelpers@@YAJPEBGPEAU_GUID@@@Z; StateRepoHelpers::ParseCLSID(ushort const *,_GUID *)
0x180060860  mov     ebx, eax
0x180060862  test    eax, eax
0x180060864  jns     short loc_180060881
0x180060866  mov     edx, 0AA9h; void *
0x18006086b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180060872  mov     r9d, eax; char *
0x180060875  mov     rcx, [rsp+48h]; this
0x18006087a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006087f  jmp     short loc_180060890
0x180060881  lea     rdx, [rsp+48h+var_20]
0x180060886  mov     rcx, [rdi]
0x180060889  call    ??$_Add@AEBU_GUID@@@?$CTSimpleArray@U_GUID@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@U_GUID@@@@V?$CSimpleArrayStandardCompareHelper@U_GUID@@@@V?$CSimpleArrayStandardMergeHelper@U_GUID@@@@@@QEAAJAEBU_GUID@@PEA_K@Z; CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_Add<_GUID const &>(_GUID const &,unsigned __int64 *)
0x18006088e  xor     ebx, ebx
0x180060890  mov     rcx, [rsp+48h+string]; string
0x180060895  call    cs:__imp_WindowsDeleteString
0x18006089b  mov     eax, ebx
0x18006089d  mov     rcx, [rsp+48h+var_10]
0x1800608a2  xor     rcx, rsp; StackCookie
0x1800608a5  call    __security_check_cookie
0x1800608aa  mov     rbx, [rsp+48h+arg_10]
0x1800608af  add     rsp, 40h
0x1800608b3  pop     rdi
0x1800608b4  retn
```
