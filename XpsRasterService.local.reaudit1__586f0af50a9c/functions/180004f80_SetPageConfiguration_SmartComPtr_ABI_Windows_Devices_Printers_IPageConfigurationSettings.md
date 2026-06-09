# SetPageConfiguration(SmartComPtr<ABI::Windows::Devices::Printers::IPageConfigurationSettings> &)

- ea: `0x180004f80`
- end: `0x1800050e4`
- name: `?SetPageConfiguration@@YAJAEAV?$SmartComPtr@UIPageConfigurationSettings@Printers@Devices@Windows@ABI@@@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005110`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x180004f80`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000502c`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000502c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180005047`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180005047`

## string_xrefs

- `0x180004fbd`: `Windows.Devices.Printers.PageConfigurationSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetPageConfiguration(_QWORD *a1)
{
  const WCHAR *v2; // rcx
  WCHAR *v3; // rcx
  int v4; // ebx
  PCNZWCH sourceString[2]; // [rsp+20h] [rbp-48h] BYREF
  UINT32 length[4]; // [rsp+30h] [rbp-38h]
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF

  string = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = 0;
  std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Windows.Devices.Printers.PageConfigurationSettings");
  string = 0;
  v2 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] >= 8u )
    v2 = sourceString[0];
  WindowsCreateString_0(v2, length[0], &string);
  if ( *(_QWORD *)&length[2] >= 8u )
  {
    v3 = (WCHAR *)sourceString[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
    {
      v3 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
      if ( (unsigned __int64)((char *)sourceString[0] - (char *)v3 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v3, 2LL * *(_QWORD *)&length[2] + 41);
        __debugbreak();
      }
    }
    operator delete(v3);
  }
  v8 = 0;
  v4 = RoActivateInstance(string, &v8);
  if ( v4 >= 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v8)(v8, &GUID_b6fc1e02_5331_54ff_95a0_1fcb76bb97a9, a1);
    if ( v4 >= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 56LL))(*a1, 0);
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 72LL))(*a1, 0);
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v8 = 0;
  WindowsDeleteString_0(string);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004f80  mov     [rsp+arg_8], rbx
0x180004f85  mov     [rsp+arg_10], rsi
0x180004f8a  push    rdi
0x180004f8b  sub     rsp, 60h
0x180004f8f  mov     rax, cs:__security_cookie
0x180004f96  xor     rax, rsp
0x180004f99  mov     [rsp+68h+var_18], rax
0x180004f9e  mov     rdi, rcx
0x180004fa1  xor     esi, esi
0x180004fa3  mov     [rsp+68h+string], rsi
0x180004fa8  xorps   xmm0, xmm0
0x180004fab  movups  xmmword ptr [rsp+68h+sourceString], xmm0
0x180004fb0  xorps   xmm1, xmm1
0x180004fb3  movdqu  xmmword ptr [rsp+68h+length], xmm1
0x180004fb9  lea     r8d, [rsi+32h]
0x180004fbd  lea     rdx, ?RuntimeClass_Windows_Devices_Printers_PageConfigurationSettings@@3QB_WB; "Windows.Devices.Printers.PageConfigurat"...
0x180004fc4  lea     rcx, [rsp+68h+sourceString]
0x180004fc9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180004fce  mov     [rsp+68h+string], rsi
0x180004fd3  lea     rcx, [rsp+68h+sourceString]
0x180004fd8  cmp     qword ptr [rsp+68h+length+8], 8
0x180004fde  cmovnb  rcx, [rsp+68h+sourceString]; sourceString
0x180004fe4  lea     r8, [rsp+68h+string]; string
0x180004fe9  mov     edx, [rsp+68h+length]; length
0x180004fed  call    WindowsCreateString_0
0x180004ff2  nop
0x180004ff3  mov     rdx, qword ptr [rsp+68h+length+8]
0x180004ff8  cmp     rdx, 8
0x180004ffc  jb      short loc_180005038
0x180004ffe  lea     rdx, ds:2[rdx*2]
0x180005006  mov     rcx, [rsp+68h+sourceString]; Block
0x18000500b  mov     rax, rcx
0x18000500e  cmp     rdx, 1000h
0x180005015  jb      short loc_180005033
0x180005017  add     rdx, 27h ; '''
0x18000501b  mov     rcx, [rcx-8]
0x18000501f  sub     rax, rcx
0x180005022  add     rax, 0FFFFFFFFFFFFFFF8h
0x180005026  cmp     rax, 1Fh
0x18000502a  jbe     short loc_180005033
0x18000502c  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005032  int     3; Trap to Debugger
0x180005033  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005038  mov     [rsp+68h+var_28], rsi
0x18000503d  lea     rdx, [rsp+68h+var_28]
0x180005042  mov     rcx, [rsp+68h+string]
0x180005047  call    cs:__imp_RoActivateInstance
0x18000504d  mov     ebx, eax
0x18000504f  test    eax, eax
0x180005051  js      short loc_18000509C
0x180005053  mov     rcx, [rsp+68h+var_28]
0x180005058  mov     rax, [rcx]
0x18000505b  mov     r8, rdi
0x18000505e  lea     rdx, _GUID_b6fc1e02_5331_54ff_95a0_1fcb76bb97a9
0x180005065  mov     rax, [rax]
0x180005068  call    cs:__guard_dispatch_icall_fptr
0x18000506e  mov     ebx, eax
0x180005070  test    eax, eax
0x180005072  js      short loc_18000509C
0x180005074  lfence
0x180005077  mov     rcx, [rdi]
0x18000507a  mov     rax, [rcx]
0x18000507d  xor     edx, edx
0x18000507f  mov     rax, [rax+38h]
0x180005083  call    cs:__guard_dispatch_icall_fptr
0x180005089  mov     rcx, [rdi]
0x18000508c  mov     rax, [rcx]
0x18000508f  xor     edx, edx
0x180005091  mov     rax, [rax+48h]
0x180005095  call    cs:__guard_dispatch_icall_fptr
0x18000509b  nop
0x18000509c  mov     rcx, [rsp+68h+var_28]
0x1800050a1  test    rcx, rcx
0x1800050a4  jz      short loc_1800050B3
0x1800050a6  mov     rax, [rcx]
0x1800050a9  mov     rax, [rax+10h]
0x1800050ad  call    cs:__guard_dispatch_icall_fptr
0x1800050b3  mov     [rsp+68h+var_28], rsi
0x1800050b8  mov     rcx, [rsp+68h+string]; string
0x1800050bd  call    WindowsDeleteString_0
0x1800050c2  mov     eax, ebx
0x1800050c4  mov     rcx, [rsp+68h+var_18]
0x1800050c9  xor     rcx, rsp; StackCookie
0x1800050cc  call    __security_check_cookie
0x1800050d1  mov     rbx, [rsp+68h+arg_8]
0x1800050d6  mov     rsi, [rsp+68h+arg_10]
0x1800050de  add     rsp, 60h
0x1800050e2  pop     rdi
0x1800050e3  retn
```
