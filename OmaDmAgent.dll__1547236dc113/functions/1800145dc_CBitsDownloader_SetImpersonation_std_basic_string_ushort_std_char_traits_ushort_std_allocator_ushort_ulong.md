# CBitsDownloader::SetImpersonation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong)

- ea: `0x1800145dc`
- end: `0x18001467a`
- name: `?SetImpersonation@CBitsDownloader@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800110c0`

## callees

- `0x1800062ac`
- `0x1800070e4`
- `0x18000a290`
- `0x1800145dc`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBitsDownloader::SetImpersonation(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rbx
  unsigned int v6; // edi

  v4 = a2;
  v6 = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    std::wstring::operator=(a1 + 32, a2);
    *(_DWORD *)(a1 + 64) = a3;
    *(_BYTE *)(a1 + 24) = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids);
    v6 = -2147024809;
  }
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v4, a2, 0);
  return v6;
}

```

## disassembly

```asm
0x1800145dc  mov     [rsp+arg_10], rbx
0x1800145e1  push    rbp
0x1800145e2  push    rsi
0x1800145e3  push    rdi
0x1800145e4  sub     rsp, 30h
0x1800145e8  mov     rax, cs:__security_cookie
0x1800145ef  xor     rax, rsp
0x1800145f2  mov     [rsp+48h+var_20], rax
0x1800145f7  mov     ebp, r8d
0x1800145fa  mov     rbx, rdx
0x1800145fd  mov     rsi, rcx
0x180014600  mov     [rsp+48h+var_28], rdx
0x180014605  xor     edi, edi
0x180014607  cmp     [rdx+10h], rdi
0x18001460b  jnz     short loc_180014640
0x18001460d  lea     rax, WPP_GLOBAL_Control
0x180014614  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461b  cmp     rcx, rax
0x18001461e  jz      short loc_180014639
0x180014620  test    byte ptr [rcx+1Ch], 4
0x180014624  jz      short loc_180014639
0x180014626  lea     edx, [rdi+0Ah]
0x180014629  lea     r8, WPP_14cd5ff906c03b036d9c08ef2443ee7b_Traceguids
0x180014630  mov     rcx, [rcx+10h]
0x180014634  call    WPP_SF_
0x180014639  mov     edi, 80070057h
0x18001463e  jmp     short loc_180014650
0x180014640  add     rcx, 20h ; ' '
0x180014644  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014649  mov     [rsi+40h], ebp
0x18001464c  mov     byte ptr [rsi+18h], 1
0x180014650  xor     r8d, r8d
0x180014653  mov     dl, 1
0x180014655  mov     rcx, rbx
0x180014658  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001465d  mov     eax, edi
0x18001465f  mov     rcx, [rsp+48h+var_20]
0x180014664  xor     rcx, rsp; StackCookie
0x180014667  call    __security_check_cookie
0x18001466c  mov     rbx, [rsp+48h+arg_10]
0x180014671  add     rsp, 30h
0x180014675  pop     rdi
0x180014676  pop     rsi
0x180014677  pop     rbp
0x180014678  retn
```
