# FwRemoteAdminSettings::FwProcessRules(_tag_FW_RULE * const)

- ea: `0x1800470cc`
- end: `0x1800472de`
- name: `?FwProcessRules@FwRemoteAdminSettings@@AEAAJQEAU_tag_FW_RULE@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, struct _tag_FW_RULE *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800474c8`

## callees

- `0x1800294b0`
- `0x1800470cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800471df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800471f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047215`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047233`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800471df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800471f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047215`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047233`
- `fwbase!FwBaseFree` at `0x180047279`
- `fwbase!FwBaseFree` at `0x180047289`
- `fwbase!FwBaseFree` at `0x180047299`
- `fwbase!FwBaseFree` at `0x180047279`
- `fwbase!FwBaseFree` at `0x180047289`
- `fwbase!FwBaseFree` at `0x180047299`
- `fwbase!FwBuildIndirectString` at `0x180047116`
- `fwbase!FwBuildIndirectString` at `0x180047156`
- `fwbase!FwBuildIndirectString` at `0x18004718f`
- `fwbase!FwBuildIndirectString` at `0x180047116`
- `fwbase!FwBuildIndirectString` at `0x180047156`
- `fwbase!FwBuildIndirectString` at `0x18004718f`
- `fwbase!FwResolveIndirectString` at `0x180047137`
- `fwbase!FwResolveIndirectString` at `0x180047170`
- `fwbase!FwResolveIndirectString` at `0x1800471a9`
- `fwbase!FwResolveIndirectString` at `0x180047137`
- `fwbase!FwResolveIndirectString` at `0x180047170`
- `fwbase!FwResolveIndirectString` at `0x1800471a9`
- `fwbase!FwReportReturnError` at `0x180047269`
- `fwbase!FwReportReturnError` at `0x1800472ae`
- `fwbase!FwReportReturnError` at `0x180047269`
- `fwbase!FwReportReturnError` at `0x1800472ae`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004724a`
- `FWPolicyIOMgr!FwCopyRule` at `0x18004724a`

## string_xrefs

- `0x1800471d8`: `@FirewallAPI.dll,-29752`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::FwProcessRules(FwRemoteAdminSettings *this, struct _tag_FW_RULE *const a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  char *v7; // rdx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v4 = FwBuildIndirectString(29753, &v9);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = FwResolveIndirectString(&v9);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v4 = FwBuildIndirectString(29765, &v10);
      v5 = v4;
      if ( v4 >= 0 )
      {
        v4 = FwResolveIndirectString(&v10);
        v5 = v4;
        if ( v4 >= 0 )
        {
          v4 = FwBuildIndirectString(29757, &v11);
          v5 = v4;
          if ( v4 >= 0 )
          {
            v4 = FwResolveIndirectString(&v11);
            v5 = v4;
            if ( v4 >= 0 )
            {
              while ( 1 )
              {
                if ( !a2 )
                  goto LABEL_19;
                v6 = *((_QWORD *)a2 + 39);
                if ( v6 && !(unsigned int)_o__wcsicmp(v6, L"@FirewallAPI.dll,-29752") )
                {
                  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3), v9) )
                  {
                    if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3), v10) )
                    {
                      if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3), v11) )
                        goto LABEL_17;
                      v7 = (char *)this + 96;
                    }
                    else
                    {
                      v7 = (char *)this + 88;
                    }
                  }
                  else
                  {
                    v7 = (char *)this + 80;
                  }
                  v4 = FwCopyRule(a2, v7);
                  v5 = v4;
                  if ( v4 < 0 )
                    break;
                }
LABEL_17:
                a2 = *(struct _tag_FW_RULE *const *)a2;
              }
            }
          }
        }
      }
    }
  }
  FwReportReturnError("FwRemoteAdminSettings::FwProcessRules", (unsigned int)v4);
LABEL_19:
  FwBaseFree(v9);
  FwBaseFree(v10);
  FwBaseFree(v11);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::FwProcessRules", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800470cc  mov     [rsp-18h+arg_10], rbx
0x1800470d1  mov     [rsp-18h+arg_18], rsi
0x1800470d6  push    rbp
0x1800470d7  push    rdi
0x1800470d8  push    r15
0x1800470da  mov     rbp, rsp
0x1800470dd  sub     rsp, 40h
0x1800470e1  mov     rax, cs:__security_cookie
0x1800470e8  xor     rax, rsp
0x1800470eb  mov     [rbp+var_8], rax
0x1800470ef  mov     rdi, rdx
0x1800470f2  mov     [rbp+var_20], 0
0x1800470fa  mov     rsi, rcx
0x1800470fd  mov     [rbp+var_18], 0
0x180047105  lea     rdx, [rbp+var_20]
0x180047109  mov     [rbp+var_10], 0
0x180047111  mov     ecx, 7439h
0x180047116  call    cs:__imp_FwBuildIndirectString
0x18004711d  nop     dword ptr [rax+rax+00h]
0x180047122  lea     r15, aFwremoteadmins_15; "FwRemoteAdminSettings::FwProcessRules"
0x180047129  mov     ebx, eax
0x18004712b  test    eax, eax
0x18004712d  js      loc_180047264
0x180047133  lea     rcx, [rbp+var_20]
0x180047137  call    cs:__imp_FwResolveIndirectString
0x18004713e  nop     dword ptr [rax+rax+00h]
0x180047143  mov     ebx, eax
0x180047145  test    eax, eax
0x180047147  js      loc_180047264
0x18004714d  lea     rdx, [rbp+var_18]
0x180047151  mov     ecx, 7445h
0x180047156  call    cs:__imp_FwBuildIndirectString
0x18004715d  nop     dword ptr [rax+rax+00h]
0x180047162  mov     ebx, eax
0x180047164  test    eax, eax
0x180047166  js      loc_180047264
0x18004716c  lea     rcx, [rbp+var_18]
0x180047170  call    cs:__imp_FwResolveIndirectString
0x180047177  nop     dword ptr [rax+rax+00h]
0x18004717c  mov     ebx, eax
0x18004717e  test    eax, eax
0x180047180  js      loc_180047264
0x180047186  lea     rdx, [rbp+var_10]
0x18004718a  mov     ecx, 743Dh
0x18004718f  call    cs:__imp_FwBuildIndirectString
0x180047196  nop     dword ptr [rax+rax+00h]
0x18004719b  mov     ebx, eax
0x18004719d  test    eax, eax
0x18004719f  js      loc_180047264
0x1800471a5  lea     rcx, [rbp+var_10]
0x1800471a9  call    cs:__imp_FwResolveIndirectString
0x1800471b0  nop     dword ptr [rax+rax+00h]
0x1800471b5  mov     ebx, eax
0x1800471b7  test    eax, eax
0x1800471b9  js      loc_180047264
0x1800471bf  test    rdi, rdi
0x1800471c2  jz      loc_180047275
0x1800471c8  mov     rcx, [rdi+138h]
0x1800471cf  test    rcx, rcx
0x1800471d2  jz      loc_18004725C
0x1800471d8  lea     rdx, aFirewallapiDll_5; "@FirewallAPI.dll,-29752"
0x1800471df  call    cs:__imp__o__wcsicmp
0x1800471e6  nop     dword ptr [rax+rax+00h]
0x1800471eb  test    eax, eax
0x1800471ed  jnz     short loc_18004725C
0x1800471ef  mov     rdx, [rbp+var_20]
0x1800471f3  mov     rcx, [rdi+18h]
0x1800471f7  call    cs:__imp__o__wcsicmp
0x1800471fe  nop     dword ptr [rax+rax+00h]
0x180047203  test    eax, eax
0x180047205  jnz     short loc_18004720D
0x180047207  lea     rdx, [rsi+50h]
0x18004720b  jmp     short loc_180047247
0x18004720d  mov     rdx, [rbp+var_18]
0x180047211  mov     rcx, [rdi+18h]
0x180047215  call    cs:__imp__o__wcsicmp
0x18004721c  nop     dword ptr [rax+rax+00h]
0x180047221  test    eax, eax
0x180047223  jnz     short loc_18004722B
0x180047225  lea     rdx, [rsi+58h]
0x180047229  jmp     short loc_180047247
0x18004722b  mov     rdx, [rbp+var_10]
0x18004722f  mov     rcx, [rdi+18h]
0x180047233  call    cs:__imp__o__wcsicmp
0x18004723a  nop     dword ptr [rax+rax+00h]
0x18004723f  test    eax, eax
0x180047241  jnz     short loc_18004725C
0x180047243  lea     rdx, [rsi+60h]
0x180047247  mov     rcx, rdi
0x18004724a  call    cs:__imp_FwCopyRule
0x180047251  nop     dword ptr [rax+rax+00h]
0x180047256  mov     ebx, eax
0x180047258  test    eax, eax
0x18004725a  js      short loc_180047264
0x18004725c  mov     rdi, [rdi]
0x18004725f  jmp     loc_1800471BF
0x180047264  mov     edx, eax
0x180047266  mov     rcx, r15
0x180047269  call    cs:__imp_FwReportReturnError
0x180047270  nop     dword ptr [rax+rax+00h]
0x180047275  mov     rcx, [rbp+var_20]
0x180047279  call    cs:__imp_FwBaseFree
0x180047280  nop     dword ptr [rax+rax+00h]
0x180047285  mov     rcx, [rbp+var_18]
0x180047289  call    cs:__imp_FwBaseFree
0x180047290  nop     dword ptr [rax+rax+00h]
0x180047295  mov     rcx, [rbp+var_10]
0x180047299  call    cs:__imp_FwBaseFree
0x1800472a0  nop     dword ptr [rax+rax+00h]
0x1800472a5  test    ebx, ebx
0x1800472a7  jns     short loc_1800472BC
0x1800472a9  mov     edx, ebx
0x1800472ab  mov     rcx, r15
0x1800472ae  call    cs:__imp_FwReportReturnError
0x1800472b5  nop     dword ptr [rax+rax+00h]
0x1800472ba  mov     ebx, eax
0x1800472bc  mov     eax, ebx
0x1800472be  mov     rcx, [rbp+var_8]
0x1800472c2  xor     rcx, rsp; StackCookie
0x1800472c5  call    __security_check_cookie
0x1800472ca  mov     rbx, [rsp+40h+arg_10]
0x1800472cf  mov     rsi, [rsp+40h+arg_18]
0x1800472d4  add     rsp, 40h
0x1800472d8  pop     r15
0x1800472da  pop     rdi
0x1800472db  pop     rbp
0x1800472dc  retn
```
