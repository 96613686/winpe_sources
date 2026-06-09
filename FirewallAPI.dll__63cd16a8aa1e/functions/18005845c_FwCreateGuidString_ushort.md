# FwCreateGuidString(ushort * *)

- ea: `0x18005845c`
- end: `0x180058563`
- name: `?FwCreateGuidString@@YAJPEAPEAG@Z`
- size: `263`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005856c`

## callees

- `0x1800277b0`
- `0x18003104c`
- `0x18005845c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058529`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058529`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005850b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005850b`
- `fwbase!FwBaseAlloc` at `0x1800584b8`
- `fwbase!FwBaseAlloc` at `0x1800584b8`
- `fwbase!FwBaseFree` at `0x18005854a`
- `fwbase!FwBaseFree` at `0x18005854a`
- `fwbase!FwReportErrorAsWinError` at `0x1800584d8`
- `fwbase!FwReportErrorAsWinError` at `0x1800584d8`
- `fwbase!FwReportReturnError` at `0x180058541`
- `fwbase!FwReportReturnError` at `0x180058559`
- `fwbase!FwReportReturnError` at `0x180058541`
- `fwbase!FwReportReturnError` at `0x180058559`

## string_xrefs

- `0x1800584d1`: `FwCreateGuidString`
- `0x18005853a`: `FwCreateGuidString`
- `0x180058552`: `FwCreateGuidString`

## pseudocode

```c
__int64 __fastcall FwCreateGuidString(unsigned __int16 **a1)
{
  OLECHAR *v2; // rdi
  int v3; // ebx
  HRESULT v5; // eax
  __int64 v6; // rdx
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  pguid = 0;
  v2 = (OLECHAR *)FwBaseAlloc(78);
  if ( v2 )
  {
    v5 = CoCreateGuid(&pguid);
    v3 = v5;
    if ( v5 >= 0 )
    {
      if ( StringFromGUID2(&pguid, v2, 39) )
        goto LABEL_6;
      v3 = -2147024785;
      v6 = 2147942511LL;
    }
    else
    {
      v6 = (unsigned int)v5;
    }
    FwReportReturnError("FwCreateGuidString", v6);
LABEL_13:
    FwBaseFree(v2);
    return (unsigned int)FwReportReturnError("FwCreateGuidString", (unsigned int)v3);
  }
  v3 = FwReportErrorAsWinError("FwCreateGuidString", "FwAlloc", 8);
  if ( v3 < 0 )
    goto LABEL_13;
LABEL_6:
  *a1 = v2;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005845c  mov     [rsp+arg_8], rbx
0x180058461  mov     [rsp+arg_10], rsi
0x180058466  push    rdi
0x180058467  sub     rsp, 40h
0x18005846b  mov     rax, cs:__security_cookie
0x180058472  xor     rax, rsp
0x180058475  mov     [rsp+48h+var_18], rax
0x18005847a  mov     rsi, rcx
0x18005847d  mov     rcx, cs:WPP_GLOBAL_Control
0x180058484  lea     rax, WPP_GLOBAL_Control
0x18005848b  cmp     rcx, rax
0x18005848e  jz      short loc_1800584AB
0x180058490  test    byte ptr [rcx+1Ch], 8
0x180058494  jz      short loc_1800584AB
0x180058496  mov     rcx, [rcx+10h]
0x18005849a  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x1800584a1  mov     edx, 0Ah
0x1800584a6  call    WPP_SF_
0x1800584ab  xorps   xmm0, xmm0
0x1800584ae  mov     ecx, 4Eh ; 'N'
0x1800584b3  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x1800584b8  call    cs:__imp_FwBaseAlloc
0x1800584be  mov     rdi, rax
0x1800584c1  test    rax, rax
0x1800584c4  jnz     short loc_180058506
0x1800584c6  lea     r8d, [rax+8]
0x1800584ca  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800584d1  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x1800584d8  call    cs:__imp_FwReportErrorAsWinError
0x1800584de  mov     ebx, eax
0x1800584e0  test    eax, eax
0x1800584e2  js      short loc_180058547
0x1800584e4  mov     [rsi], rdi
0x1800584e7  mov     eax, ebx
0x1800584e9  mov     rcx, [rsp+48h+var_18]
0x1800584ee  xor     rcx, rsp; StackCookie
0x1800584f1  call    __security_check_cookie
0x1800584f6  mov     rbx, [rsp+48h+arg_8]
0x1800584fb  mov     rsi, [rsp+48h+arg_10]
0x180058500  add     rsp, 40h
0x180058504  pop     rdi
0x180058505  retn
0x180058506  lea     rcx, [rsp+48h+pguid]; pguid
0x18005850b  call    cs:__imp_CoCreateGuid
0x180058511  mov     ebx, eax
0x180058513  test    eax, eax
0x180058515  jns     short loc_18005851B
0x180058517  mov     edx, eax
0x180058519  jmp     short loc_18005853A
0x18005851b  mov     r8d, 27h ; '''; cchMax
0x180058521  lea     rcx, [rsp+48h+pguid]; rguid
0x180058526  mov     rdx, rdi; lpsz
0x180058529  call    cs:__imp_StringFromGUID2
0x18005852f  test    eax, eax
0x180058531  jnz     short loc_1800584E4
0x180058533  mov     ebx, 8007006Fh
0x180058538  mov     edx, ebx
0x18005853a  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x180058541  call    cs:__imp_FwReportReturnError
0x180058547  mov     rcx, rdi
0x18005854a  call    cs:__imp_FwBaseFree
0x180058550  mov     edx, ebx
0x180058552  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x180058559  call    cs:__imp_FwReportReturnError
0x18005855f  mov     ebx, eax
0x180058561  jmp     short loc_1800584E7
```
