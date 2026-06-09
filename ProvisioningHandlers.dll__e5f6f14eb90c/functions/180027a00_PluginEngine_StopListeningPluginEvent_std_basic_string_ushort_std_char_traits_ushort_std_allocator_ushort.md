# PluginEngine::StopListeningPluginEvent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180027a00`
- end: `0x180027b59`
- name: `?StopListeningPluginEvent@PluginEngine@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x18000f4fc`
- `0x18001fbfc`
- `0x180027a00`
- `0x180027da0`
- `0x180028860`
- `0x18002c010`

## string_xrefs

- `0x180027a62`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027aad`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027af2`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PluginEngine::StopListeningPluginEvent(_QWORD *a1, __int64 a2)
{
  __int64 (__fastcall *v4)(_QWORD *, __int64, int *); // rdi
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v10; // rdx
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // edi
  __int64 v15; // rdx
  int v16[4]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v17[5]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v17[4] = a2;
  v16[0] = 0;
  v4 = *(__int64 (__fastcall **)(_QWORD *, __int64, int *))(*a1 + 80LL);
  v5 = std::wstring::wstring(v17);
  v6 = v4(a1, v5, v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( (unsigned int)v16[0] <= (unsigned __int64)((__int64)(a1[2] - a1[1]) >> 3) )
    {
      v11 = (_QWORD *)std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(a1 + 1);
      v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 48LL))(*v11);
      v14 = v12;
      if ( v12 >= 0 )
      {
        LOBYTE(v13) = 1;
        std::wstring::_Tidy(a2, v13, 0);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
          (const char *)(unsigned int)v12,
          v16[0]);
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(a2, v15, 0);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)0x8000FFFFLL,
        v16[0]);
      LOBYTE(v10) = 1;
      std::wstring::_Tidy(a2, v10, 0);
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v6,
      v16[0]);
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(a2, v8, 0);
    return v7;
  }
}

```

## disassembly

```asm
0x180027a00  mov     r11, rsp
0x180027a03  mov     [r11+18h], rbx
0x180027a07  mov     [r11+20h], rsi
0x180027a0b  push    rdi
0x180027a0c  sub     rsp, 60h
0x180027a10  mov     rax, cs:__security_cookie
0x180027a17  xor     rax, rsp
0x180027a1a  mov     [rsp+68h+var_10], rax
0x180027a1f  mov     rbx, rdx
0x180027a22  mov     rsi, rcx
0x180027a25  mov     [r11-18h], rdx
0x180027a29  mov     [rsp+68h+var_48], 0; int
0x180027a31  mov     rax, [rcx]
0x180027a34  mov     rdi, [rax+50h]
0x180027a38  lea     rcx, [r11-38h]
0x180027a3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180027a41  lea     r8, [rsp+68h+var_48]
0x180027a46  mov     rdx, rax
0x180027a49  mov     rcx, rsi
0x180027a4c  mov     rax, rdi
0x180027a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a54  mov     edi, eax
0x180027a56  test    eax, eax
0x180027a58  jns     short loc_180027A88
0x180027a5a  mov     rcx, [rsp+68h]; this
0x180027a5f  mov     r9d, eax; char *
0x180027a62  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027a69  mov     edx, 1CAh; void *
0x180027a6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a73  nop
0x180027a74  xor     r8d, r8d
0x180027a77  mov     dl, 1
0x180027a79  mov     rcx, rbx
0x180027a7c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027a81  mov     eax, edi
0x180027a83  jmp     loc_180027B39
0x180027a88  lea     rcx, [rsi+8]
0x180027a8c  mov     edx, [rsp+68h+var_48]
0x180027a90  mov     rax, [rcx+8]
0x180027a94  sub     rax, [rcx]
0x180027a97  sar     rax, 3
0x180027a9b  cmp     rdx, rax
0x180027a9e  jbe     short loc_180027AD0
0x180027aa0  mov     rcx, [rsp+68h]; this
0x180027aa5  mov     edi, 8000FFFFh
0x180027aaa  mov     r9d, edi; char *
0x180027aad  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027ab4  mov     edx, 1CCh; void *
0x180027ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027abe  nop
0x180027abf  xor     r8d, r8d
0x180027ac2  mov     dl, 1
0x180027ac4  mov     rcx, rbx
0x180027ac7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027acc  mov     eax, edi
0x180027ace  jmp     short loc_180027B39
0x180027ad0  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x180027ad5  mov     rcx, [rax]
0x180027ad8  mov     rax, [rcx]
0x180027adb  mov     rax, [rax+30h]
0x180027adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ae4  mov     edi, eax
0x180027ae6  test    eax, eax
0x180027ae8  jns     short loc_180027B15
0x180027aea  mov     rcx, [rsp+68h]; this
0x180027aef  mov     r9d, eax; char *
0x180027af2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027af9  mov     edx, 1CEh; void *
0x180027afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b03  nop
0x180027b04  xor     r8d, r8d
0x180027b07  mov     dl, 1
0x180027b09  mov     rcx, rbx
0x180027b0c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027b11  mov     eax, edi
0x180027b13  jmp     short loc_180027B39
0x180027b15  xor     r8d, r8d
0x180027b18  mov     dl, 1
0x180027b1a  mov     rcx, rbx
0x180027b1d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027b22  xor     eax, eax
0x180027b24  jmp     short loc_180027B39
0x180027b26  xor     r8d, r8d
0x180027b29  mov     dl, 1
0x180027b2b  mov     rcx, [rsp+68h+var_18]
0x180027b30  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027b35  mov     eax, [rsp+68h+var_48]
0x180027b39  mov     rcx, [rsp+68h+var_10]
0x180027b3e  xor     rcx, rsp; StackCookie
0x180027b41  call    __security_check_cookie
0x180027b46  lea     r11, [rsp+68h+var_8]
0x180027b4b  mov     rbx, [r11+20h]
0x180027b4f  mov     rsi, [r11+28h]
0x180027b53  mov     rsp, r11
0x180027b56  pop     rdi
0x180027b57  retn
```
