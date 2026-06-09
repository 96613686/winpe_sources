# JobHelper::SetImpersonation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x1800110c0`
- end: `0x18001115a`
- name: `?SetImpersonation@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180004950`
- `0x180006df0`

## callees

- `0x1800062ac`
- `0x18000702c`
- `0x18000a2c0`
- `0x1800110c0`
- `0x1800145dc`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobHelper::SetImpersonation(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  _BYTE v10[32]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v11; // [rsp+48h] [rbp-30h]

  v11 = a2;
  v6 = std::wstring::wstring(v10, a2);
  v8 = CBitsDownloader::SetImpersonation(a1, v6, a3);
  if ( v8 < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (unsigned int)v8);
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(a2, v7, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800110c0  push    rbx
0x1800110c2  push    rsi
0x1800110c3  push    rdi
0x1800110c4  sub     rsp, 60h
0x1800110c8  mov     rax, cs:__security_cookie
0x1800110cf  xor     rax, rsp
0x1800110d2  mov     [rsp+78h+var_28], rax
0x1800110d7  mov     edi, r8d
0x1800110da  mov     rsi, rdx
0x1800110dd  mov     rbx, rcx
0x1800110e0  mov     [rsp+78h+var_30], rdx
0x1800110e5  lea     rcx, [rsp+78h+var_50]
0x1800110ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800110ef  mov     r8d, edi
0x1800110f2  mov     rdx, rax
0x1800110f5  mov     rcx, rbx
0x1800110f8  call    ?SetImpersonation@CBitsDownloader@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; CBitsDownloader::SetImpersonation(std::wstring,ulong)
0x1800110fd  mov     ebx, eax
0x1800110ff  test    eax, eax
0x180011101  jns     short loc_180011135
0x180011103  lea     rax, WPP_GLOBAL_Control
0x18001110a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011111  cmp     rcx, rax
0x180011114  jz      short loc_180011135
0x180011116  test    byte ptr [rcx+1Ch], 4
0x18001111a  jz      short loc_180011135
0x18001111c  mov     edx, 0Ah
0x180011121  mov     r9d, ebx
0x180011124  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18001112b  mov     rcx, [rcx+10h]
0x18001112f  call    WPP_SF_d
0x180011134  nop
0x180011135  xor     r8d, r8d
0x180011138  mov     dl, 1
0x18001113a  mov     rcx, rsi
0x18001113d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180011142  mov     eax, ebx
0x180011144  mov     rcx, [rsp+78h+var_28]
0x180011149  xor     rcx, rsp; StackCookie
0x18001114c  call    __security_check_cookie
0x180011151  add     rsp, 60h
0x180011155  pop     rdi
0x180011156  pop     rsi
0x180011157  pop     rbx
0x180011158  retn
```
