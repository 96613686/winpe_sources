# FwAuthApp::CreateDefaultAuthAppRules(void)

- ea: `0x180001dd0`
- end: `0x180001e51`
- name: `?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ`
- size: `129`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800018d0`
- `0x180001b10`
- `0x180020170`
- `0x180040e00`
- `0x180040ea0`
- `0x180040f40`
- `0x1800411e0`
- `0x180041490`

## callees

- `0x180001dd0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180001e28`
- `fwbase!FwReportReturnError` at `0x180001e37`
- `fwbase!FwReportReturnError` at `0x180001e28`
- `fwbase!FwReportReturnError` at `0x180001e37`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001df4`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e13`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001df4`
- `FWPolicyIOMgr!CreateDefaultAuthAppRule` at `0x180001e13`

## string_xrefs

- `0x180001e21`: `FwAuthApp::CreateDefaultAuthAppRules`
- `0x180001e30`: `FwAuthApp::CreateDefaultAuthAppRules`

## pseudocode

```c
__int64 __fastcall FwAuthApp::CreateDefaultAuthAppRules(FwAuthApp *this)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  int DefaultAuthAppRule; // eax

  v2 = 0;
  v3 = (_QWORD *)((char *)this + 72);
  if ( !*v3
    && (DefaultAuthAppRule = CreateDefaultAuthAppRule(v3, 6, *((unsigned int *)this + 16)),
        v2 = DefaultAuthAppRule,
        DefaultAuthAppRule < 0)
    || !*((_QWORD *)this + 10)
    && (DefaultAuthAppRule = CreateDefaultAuthAppRule((char *)this + 80, 17, *((unsigned int *)this + 16)),
        v2 = DefaultAuthAppRule,
        DefaultAuthAppRule < 0) )
  {
    FwReportReturnError("FwAuthApp::CreateDefaultAuthAppRules", (unsigned int)DefaultAuthAppRule);
    return (unsigned int)FwReportReturnError("FwAuthApp::CreateDefaultAuthAppRules", v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180001dd0  mov     [rsp+arg_0], rbx
0x180001dd5  mov     [rsp+arg_8], rsi
0x180001dda  push    rdi
0x180001ddb  sub     rsp, 20h
0x180001ddf  mov     rsi, rcx
0x180001de2  xor     ebx, ebx
0x180001de4  add     rcx, 48h ; 'H'
0x180001de8  cmp     [rcx], rbx
0x180001deb  jnz     short loc_180001E00
0x180001ded  mov     r8d, [rsi+40h]
0x180001df1  lea     edx, [rbx+6]
0x180001df4  call    cs:__imp_?CreateDefaultAuthAppRule@@YAJPEAPEAU_tag_FW_RULE@@GW4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultAuthAppRule(_tag_FW_RULE * *,ushort,_tag_FW_PROFILE_TYPE)
0x180001dfa  mov     ebx, eax
0x180001dfc  test    eax, eax
0x180001dfe  js      short loc_180001E1F
0x180001e00  lea     rcx, [rsi+50h]
0x180001e04  cmp     qword ptr [rcx], 0
0x180001e08  jnz     short loc_180001E3F
0x180001e0a  mov     r8d, [rsi+40h]
0x180001e0e  mov     edx, 11h
0x180001e13  call    cs:__imp_?CreateDefaultAuthAppRule@@YAJPEAPEAU_tag_FW_RULE@@GW4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultAuthAppRule(_tag_FW_RULE * *,ushort,_tag_FW_PROFILE_TYPE)
0x180001e19  mov     ebx, eax
0x180001e1b  test    eax, eax
0x180001e1d  jns     short loc_180001E3F
0x180001e1f  mov     edx, eax
0x180001e21  lea     rcx, aFwauthappCreat_0; "FwAuthApp::CreateDefaultAuthAppRules"
0x180001e28  call    cs:__imp_FwReportReturnError
0x180001e2e  mov     edx, ebx
0x180001e30  lea     rcx, aFwauthappCreat_0; "FwAuthApp::CreateDefaultAuthAppRules"
0x180001e37  call    cs:__imp_FwReportReturnError
0x180001e3d  mov     ebx, eax
0x180001e3f  mov     rsi, [rsp+28h+arg_8]
0x180001e44  mov     eax, ebx
0x180001e46  mov     rbx, [rsp+28h+arg_0]
0x180001e4b  add     rsp, 20h
0x180001e4f  pop     rdi
0x180001e50  retn
```
