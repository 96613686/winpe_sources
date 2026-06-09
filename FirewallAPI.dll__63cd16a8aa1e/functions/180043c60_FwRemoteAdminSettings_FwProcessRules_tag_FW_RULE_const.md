# FwRemoteAdminSettings::FwProcessRules(_tag_FW_RULE * const)

- ea: `0x180043c60`
- end: `0x180043e0a`
- name: `?FwProcessRules@FwRemoteAdminSettings@@AEAAJQEAU_tag_FW_RULE@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this, struct _tag_FW_RULE *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180043fc8`

## callees

- `0x1800277b0`
- `0x180043c60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d4b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d5d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d75`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043d8d`
- `fwbase!FwBaseFree` at `0x180043dbe`
- `fwbase!FwBaseFree` at `0x180043dc8`
- `fwbase!FwBaseFree` at `0x180043dd2`
- `fwbase!FwBaseFree` at `0x180043dbe`
- `fwbase!FwBaseFree` at `0x180043dc8`
- `fwbase!FwBaseFree` at `0x180043dd2`
- `fwbase!FwBuildIndirectString` at `0x180043caa`
- `fwbase!FwBuildIndirectString` at `0x180043cde`
- `fwbase!FwBuildIndirectString` at `0x180043d0b`
- `fwbase!FwBuildIndirectString` at `0x180043caa`
- `fwbase!FwBuildIndirectString` at `0x180043cde`
- `fwbase!FwBuildIndirectString` at `0x180043d0b`
- `fwbase!FwResolveIndirectString` at `0x180043cc5`
- `fwbase!FwResolveIndirectString` at `0x180043cf2`
- `fwbase!FwResolveIndirectString` at `0x180043d1f`
- `fwbase!FwResolveIndirectString` at `0x180043cc5`
- `fwbase!FwResolveIndirectString` at `0x180043cf2`
- `fwbase!FwResolveIndirectString` at `0x180043d1f`
- `fwbase!FwReportReturnError` at `0x180043db4`
- `fwbase!FwReportReturnError` at `0x180043de1`
- `fwbase!FwReportReturnError` at `0x180043db4`
- `fwbase!FwReportReturnError` at `0x180043de1`
- `FWPolicyIOMgr!FwCopyRule` at `0x180043d9e`
- `FWPolicyIOMgr!FwCopyRule` at `0x180043d9e`

## string_xrefs

- `0x180043d44`: `@FirewallAPI.dll,-29752`

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
0x180043c60  mov     [rsp-18h+arg_10], rbx
0x180043c65  mov     [rsp-18h+arg_18], rsi
0x180043c6a  push    rbp
0x180043c6b  push    rdi
0x180043c6c  push    r15
0x180043c6e  mov     rbp, rsp
0x180043c71  sub     rsp, 40h
0x180043c75  mov     rax, cs:__security_cookie
0x180043c7c  xor     rax, rsp
0x180043c7f  mov     [rbp+var_8], rax
0x180043c83  mov     rdi, rdx
0x180043c86  mov     [rbp+var_20], 0
0x180043c8e  mov     rsi, rcx
0x180043c91  mov     [rbp+var_18], 0
0x180043c99  lea     rdx, [rbp+var_20]
0x180043c9d  mov     [rbp+var_10], 0
0x180043ca5  mov     ecx, 7439h
0x180043caa  call    cs:__imp_FwBuildIndirectString
0x180043cb0  lea     r15, aFwremoteadmins_15; "FwRemoteAdminSettings::FwProcessRules"
0x180043cb7  mov     ebx, eax
0x180043cb9  test    eax, eax
0x180043cbb  js      loc_180043DAF
0x180043cc1  lea     rcx, [rbp+var_20]
0x180043cc5  call    cs:__imp_FwResolveIndirectString
0x180043ccb  mov     ebx, eax
0x180043ccd  test    eax, eax
0x180043ccf  js      loc_180043DAF
0x180043cd5  lea     rdx, [rbp+var_18]
0x180043cd9  mov     ecx, 7445h
0x180043cde  call    cs:__imp_FwBuildIndirectString
0x180043ce4  mov     ebx, eax
0x180043ce6  test    eax, eax
0x180043ce8  js      loc_180043DAF
0x180043cee  lea     rcx, [rbp+var_18]
0x180043cf2  call    cs:__imp_FwResolveIndirectString
0x180043cf8  mov     ebx, eax
0x180043cfa  test    eax, eax
0x180043cfc  js      loc_180043DAF
0x180043d02  lea     rdx, [rbp+var_10]
0x180043d06  mov     ecx, 743Dh
0x180043d0b  call    cs:__imp_FwBuildIndirectString
0x180043d11  mov     ebx, eax
0x180043d13  test    eax, eax
0x180043d15  js      loc_180043DAF
0x180043d1b  lea     rcx, [rbp+var_10]
0x180043d1f  call    cs:__imp_FwResolveIndirectString
0x180043d25  mov     ebx, eax
0x180043d27  test    eax, eax
0x180043d29  js      loc_180043DAF
0x180043d2f  test    rdi, rdi
0x180043d32  jz      loc_180043DBA
0x180043d38  mov     rcx, [rdi+138h]
0x180043d3f  test    rcx, rcx
0x180043d42  jz      short loc_180043DAA
0x180043d44  lea     rdx, aFirewallapiDll_5; "@FirewallAPI.dll,-29752"
0x180043d4b  call    cs:__imp__o__wcsicmp
0x180043d51  test    eax, eax
0x180043d53  jnz     short loc_180043DAA
0x180043d55  mov     rdx, [rbp+var_20]
0x180043d59  mov     rcx, [rdi+18h]
0x180043d5d  call    cs:__imp__o__wcsicmp
0x180043d63  test    eax, eax
0x180043d65  jnz     short loc_180043D6D
0x180043d67  lea     rdx, [rsi+50h]
0x180043d6b  jmp     short loc_180043D9B
0x180043d6d  mov     rdx, [rbp+var_18]
0x180043d71  mov     rcx, [rdi+18h]
0x180043d75  call    cs:__imp__o__wcsicmp
0x180043d7b  test    eax, eax
0x180043d7d  jnz     short loc_180043D85
0x180043d7f  lea     rdx, [rsi+58h]
0x180043d83  jmp     short loc_180043D9B
0x180043d85  mov     rdx, [rbp+var_10]
0x180043d89  mov     rcx, [rdi+18h]
0x180043d8d  call    cs:__imp__o__wcsicmp
0x180043d93  test    eax, eax
0x180043d95  jnz     short loc_180043DAA
0x180043d97  lea     rdx, [rsi+60h]
0x180043d9b  mov     rcx, rdi
0x180043d9e  call    cs:__imp_FwCopyRule
0x180043da4  mov     ebx, eax
0x180043da6  test    eax, eax
0x180043da8  js      short loc_180043DAF
0x180043daa  mov     rdi, [rdi]
0x180043dad  jmp     short loc_180043D2F
0x180043daf  mov     edx, eax
0x180043db1  mov     rcx, r15
0x180043db4  call    cs:__imp_FwReportReturnError
0x180043dba  mov     rcx, [rbp+var_20]
0x180043dbe  call    cs:__imp_FwBaseFree
0x180043dc4  mov     rcx, [rbp+var_18]
0x180043dc8  call    cs:__imp_FwBaseFree
0x180043dce  mov     rcx, [rbp+var_10]
0x180043dd2  call    cs:__imp_FwBaseFree
0x180043dd8  test    ebx, ebx
0x180043dda  jns     short loc_180043DE9
0x180043ddc  mov     edx, ebx
0x180043dde  mov     rcx, r15
0x180043de1  call    cs:__imp_FwReportReturnError
0x180043de7  mov     ebx, eax
0x180043de9  mov     eax, ebx
0x180043deb  mov     rcx, [rbp+var_8]
0x180043def  xor     rcx, rsp; StackCookie
0x180043df2  call    __security_check_cookie
0x180043df7  mov     rbx, [rsp+40h+arg_10]
0x180043dfc  mov     rsi, [rsp+40h+arg_18]
0x180043e01  add     rsp, 40h
0x180043e05  pop     r15
0x180043e07  pop     rdi
0x180043e08  pop     rbp
0x180043e09  retn
```
