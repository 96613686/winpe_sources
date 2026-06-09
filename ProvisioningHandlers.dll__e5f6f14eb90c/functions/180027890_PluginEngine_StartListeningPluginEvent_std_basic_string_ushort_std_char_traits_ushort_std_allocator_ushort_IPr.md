# PluginEngine::StartListeningPluginEvent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,IProvisionPluginEventHandler *)

- ea: `0x180027890`
- end: `0x1800279ed`
- name: `?StartListeningPluginEvent@PluginEngine@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIProvisionPluginEventHandler@@@Z`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x18000f4fc`
- `0x18001fbfc`
- `0x180027890`
- `0x180027da0`
- `0x180028860`
- `0x18002c010`

## string_xrefs

- `0x1800278f4`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002793f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027987`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall PluginEngine::StartListeningPluginEvent(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v6)(_QWORD *, __int64, int *); // rdi
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // edi
  __int64 v17; // rdx
  int v18[4]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v19[32]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v20 = a2;
  v18[0] = 0;
  v6 = *(__int64 (__fastcall **)(_QWORD *, __int64, int *))(*a1 + 80LL);
  v7 = std::wstring::wstring(v19);
  v8 = v6(a1, v7, v18);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (unsigned int)v18[0] <= (unsigned __int64)((__int64)(a1[2] - a1[1]) >> 3) )
    {
      v13 = (_QWORD *)std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(a1 + 1);
      v14 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v13 + 40LL))(*v13, a3);
      v16 = v14;
      if ( v14 >= 0 )
      {
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(a2, v15, 0);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
          (const char *)(unsigned int)v14,
          v18[0]);
        LOBYTE(v17) = 1;
        std::wstring::_Tidy(a2, v17, 0);
        return v16;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)0x8000FFFFLL,
        v18[0]);
      LOBYTE(v12) = 1;
      std::wstring::_Tidy(a2, v12, 0);
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(a2, v10, 0);
    return v9;
  }
}

```

## disassembly

```asm
0x180027890  mov     [rsp+arg_18], rbx
0x180027895  push    rsi
0x180027896  push    rdi
0x180027897  push    r14
0x180027899  sub     rsp, 60h
0x18002789d  mov     rax, cs:__security_cookie
0x1800278a4  xor     rax, rsp
0x1800278a7  mov     [rsp+78h+var_20], rax
0x1800278ac  mov     r14, r8
0x1800278af  mov     rbx, rdx
0x1800278b2  mov     rsi, rcx
0x1800278b5  mov     [rsp+78h+var_28], rdx
0x1800278ba  mov     [rsp+78h+var_58], 0; int
0x1800278c2  mov     rax, [rcx]
0x1800278c5  mov     rdi, [rax+50h]
0x1800278c9  lea     rcx, [rsp+78h+var_48]
0x1800278ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800278d3  lea     r8, [rsp+78h+var_58]
0x1800278d8  mov     rdx, rax
0x1800278db  mov     rcx, rsi
0x1800278de  mov     rax, rdi
0x1800278e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e6  mov     edi, eax
0x1800278e8  test    eax, eax
0x1800278ea  jns     short loc_18002791A
0x1800278ec  mov     rcx, [rsp+78h]; this
0x1800278f1  mov     r9d, eax; char *
0x1800278f4  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800278fb  mov     edx, 1BAh; void *
0x180027900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027905  nop
0x180027906  xor     r8d, r8d
0x180027909  mov     dl, 1
0x18002790b  mov     rcx, rbx
0x18002790e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027913  mov     eax, edi
0x180027915  jmp     loc_1800279CE
0x18002791a  lea     rcx, [rsi+8]
0x18002791e  mov     edx, [rsp+78h+var_58]
0x180027922  mov     rax, [rcx+8]
0x180027926  sub     rax, [rcx]
0x180027929  sar     rax, 3
0x18002792d  cmp     rdx, rax
0x180027930  jbe     short loc_180027962
0x180027932  mov     rcx, [rsp+78h]; this
0x180027937  mov     edi, 8000FFFFh
0x18002793c  mov     r9d, edi; char *
0x18002793f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027946  mov     edx, 1BCh; void *
0x18002794b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027950  nop
0x180027951  xor     r8d, r8d
0x180027954  mov     dl, 1
0x180027956  mov     rcx, rbx
0x180027959  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002795e  mov     eax, edi
0x180027960  jmp     short loc_1800279CE
0x180027962  call    ?at@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::at(unsigned __int64)
0x180027967  mov     rcx, [rax]
0x18002796a  mov     rax, [rcx]
0x18002796d  mov     rdx, r14
0x180027970  mov     rax, [rax+28h]
0x180027974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027979  mov     edi, eax
0x18002797b  test    eax, eax
0x18002797d  jns     short loc_1800279AA
0x18002797f  mov     rcx, [rsp+78h]; this
0x180027984  mov     r9d, eax; char *
0x180027987  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x18002798e  mov     edx, 1BEh; void *
0x180027993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027998  nop
0x180027999  xor     r8d, r8d
0x18002799c  mov     dl, 1
0x18002799e  mov     rcx, rbx
0x1800279a1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800279a6  mov     eax, edi
0x1800279a8  jmp     short loc_1800279CE
0x1800279aa  xor     r8d, r8d
0x1800279ad  mov     dl, 1
0x1800279af  mov     rcx, rbx
0x1800279b2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800279b7  xor     eax, eax
0x1800279b9  jmp     short loc_1800279CE
0x1800279bb  xor     r8d, r8d
0x1800279be  mov     dl, 1
0x1800279c0  mov     rcx, [rsp+78h+var_28]
0x1800279c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800279ca  mov     eax, [rsp+78h+var_58]
0x1800279ce  mov     rcx, [rsp+78h+var_20]
0x1800279d3  xor     rcx, rsp; StackCookie
0x1800279d6  call    __security_check_cookie
0x1800279db  mov     rbx, [rsp+78h+arg_18]
0x1800279e3  add     rsp, 60h
0x1800279e7  pop     r14
0x1800279e9  pop     rdi
0x1800279ea  pop     rsi
0x1800279eb  retn
```
