# JobHelper::GetJobRegPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140019750`
- end: `0x140019844`
- name: `?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `11`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140018b40`
- `0x140018d08`
- `0x140019054`
- `0x140019c6c`
- `0x140019d68`
- `0x140019e94`
- `0x140019fcc`
- `0x14001a0c4`
- `0x14001a244`
- `0x14001a418`
- `0x14001a550`

## callees

- `0x140006480`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x140011c90`
- `0x140011d58`
- `0x140019750`
- `0x14001a8d0`

## string_xrefs

- `0x1400197f4`: `\MSI\`
- `0x1400197ab`: `Failed to construct job registry path for job %1. Error = 0x%2!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::GetJobRegPath(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  _QWORD v10[4]; // [rsp+20h] [rbp-48h] BYREF

  v5 = a1;
  v10[3] = 7;
  v6 = 0;
  v10[2] = 0;
  LOWORD(v10[0]) = 0;
  if ( a1[2] && a2[2] )
  {
    v7 = std::char_traits<unsigned short>::length(L"SOFTWARE\\Microsoft\\EnterpriseDesktopAppManagement");
    std::wstring::assign(a3, v8, v7);
    std::wstring::append((__int64)a3, (__int64)L"\\");
    std::wstring::append(a3, a2, 0, 0xFFFFFFFFFFFFFFFFuLL);
    std::wstring::append((__int64)a3, (__int64)L"\\MSI\\");
    std::wstring::append(a3, v5, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    v6 = -2147024809;
    if ( a1[3] >= 8u )
      v5 = (_QWORD *)*a1;
    LogError(L"Failed to construct job registry path for job %1. Error = 0x%2!x!.", v5);
  }
  std::wstring::_Tidy(v10, 1, 0);
  return v6;
}

```

## disassembly

```asm
0x140019750  mov     [rsp+arg_18], rbx
0x140019755  push    rbp
0x140019756  push    rsi
0x140019757  push    rdi
0x140019758  sub     rsp, 50h
0x14001975c  mov     rax, cs:__security_cookie
0x140019763  xor     rax, rsp
0x140019766  mov     [rsp+68h+var_28], rax
0x14001976b  mov     rbp, r8
0x14001976e  mov     rsi, rdx
0x140019771  mov     rbx, rcx
0x140019774  mov     [rsp+68h+var_30], 7
0x14001977d  xor     edi, edi
0x14001977f  mov     [rsp+68h+var_38], rdi
0x140019784  mov     [rsp+68h+var_48], di
0x140019789  cmp     [rcx+10h], rdi
0x14001978d  jz      short loc_140019795
0x14001978f  cmp     [rdx+10h], rdi
0x140019793  jnz     short loc_1400197B9
0x140019795  mov     r8d, 80070057h
0x14001979b  mov     edi, r8d
0x14001979e  cmp     qword ptr [rcx+18h], 8
0x1400197a3  jb      short loc_1400197A8
0x1400197a5  mov     rbx, [rcx]
0x1400197a8  mov     rdx, rbx
0x1400197ab  lea     rcx, aFailedToConstr; "Failed to construct job registry path f"...
0x1400197b2  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400197b7  jmp     short loc_140019816
0x1400197b9  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\EnterpriseDesktopA"...
0x1400197c0  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1400197c5  mov     r8, rax
0x1400197c8  mov     rdx, rcx
0x1400197cb  mov     rcx, rbp
0x1400197ce  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1400197d3  lea     rdx, asc_140020C3C; "\\"
0x1400197da  mov     rcx, rbp
0x1400197dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400197e2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400197e6  xor     r8d, r8d
0x1400197e9  mov     rdx, rsi
0x1400197ec  mov     rcx, rbp
0x1400197ef  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400197f4  lea     rdx, aMsi_0; "\\MSI\\"
0x1400197fb  mov     rcx, rbp
0x1400197fe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140019803  or      r9, 0FFFFFFFFFFFFFFFFh
0x140019807  xor     r8d, r8d
0x14001980a  mov     rdx, rbx
0x14001980d  mov     rcx, rbp
0x140019810  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x140019815  nop
0x140019816  xor     r8d, r8d
0x140019819  mov     dl, 1
0x14001981b  lea     rcx, [rsp+68h+var_48]
0x140019820  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019825  mov     eax, edi
0x140019827  mov     rcx, [rsp+68h+var_28]
0x14001982c  xor     rcx, rsp; StackCookie
0x14001982f  call    __security_check_cookie
0x140019834  mov     rbx, [rsp+68h+arg_18]
0x14001983c  add     rsp, 50h
0x140019840  pop     rdi
0x140019841  pop     rsi
0x140019842  pop     rbp
0x140019843  retn
```
