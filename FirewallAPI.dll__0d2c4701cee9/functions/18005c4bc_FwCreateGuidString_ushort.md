# FwCreateGuidString(ushort * *)

- ea: `0x18005c4bc`
- end: `0x18005c5f1`
- name: `?FwCreateGuidString@@YAJPEAPEAG@Z`
- size: `309`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c5f8`

## callees

- `0x1800294b0`
- `0x18003336c`
- `0x18005c4bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005c59c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005c59c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005c578`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005c578`
- `fwbase!FwBaseAlloc` at `0x18005c518`
- `fwbase!FwBaseAlloc` at `0x18005c518`
- `fwbase!FwBaseFree` at `0x18005c5c9`
- `fwbase!FwBaseFree` at `0x18005c5c9`
- `fwbase!FwReportErrorAsWinError` at `0x18005c53e`
- `fwbase!FwReportErrorAsWinError` at `0x18005c53e`
- `fwbase!FwReportReturnError` at `0x18005c5ba`
- `fwbase!FwReportReturnError` at `0x18005c5de`
- `fwbase!FwReportReturnError` at `0x18005c5ba`
- `fwbase!FwReportReturnError` at `0x18005c5de`

## string_xrefs

- `0x18005c537`: `FwCreateGuidString`
- `0x18005c5b3`: `FwCreateGuidString`
- `0x18005c5d7`: `FwCreateGuidString`

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
0x18005c4bc  mov     [rsp+arg_8], rbx
0x18005c4c1  mov     [rsp+arg_10], rsi
0x18005c4c6  push    rdi
0x18005c4c7  sub     rsp, 40h
0x18005c4cb  mov     rax, cs:__security_cookie
0x18005c4d2  xor     rax, rsp
0x18005c4d5  mov     [rsp+48h+var_18], rax
0x18005c4da  mov     rsi, rcx
0x18005c4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4e4  lea     rax, WPP_GLOBAL_Control
0x18005c4eb  cmp     rcx, rax
0x18005c4ee  jz      short loc_18005C50B
0x18005c4f0  test    byte ptr [rcx+1Ch], 8
0x18005c4f4  jz      short loc_18005C50B
0x18005c4f6  mov     rcx, [rcx+10h]
0x18005c4fa  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x18005c501  mov     edx, 0Ah
0x18005c506  call    WPP_SF_
0x18005c50b  xorps   xmm0, xmm0
0x18005c50e  mov     ecx, 4Eh ; 'N'
0x18005c513  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x18005c518  call    cs:__imp_FwBaseAlloc
0x18005c51f  nop     dword ptr [rax+rax+00h]
0x18005c524  mov     rdi, rax
0x18005c527  test    rax, rax
0x18005c52a  jnz     short loc_18005C573
0x18005c52c  lea     r8d, [rax+8]
0x18005c530  lea     rdx, aFwalloc_0; "FwAlloc"
0x18005c537  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x18005c53e  call    cs:__imp_FwReportErrorAsWinError
0x18005c545  nop     dword ptr [rax+rax+00h]
0x18005c54a  mov     ebx, eax
0x18005c54c  test    eax, eax
0x18005c54e  js      short loc_18005C5C6
0x18005c550  mov     [rsi], rdi
0x18005c553  mov     eax, ebx
0x18005c555  mov     rcx, [rsp+48h+var_18]
0x18005c55a  xor     rcx, rsp; StackCookie
0x18005c55d  call    __security_check_cookie
0x18005c562  mov     rbx, [rsp+48h+arg_8]
0x18005c567  mov     rsi, [rsp+48h+arg_10]
0x18005c56c  add     rsp, 40h
0x18005c570  pop     rdi
0x18005c571  retn
0x18005c573  lea     rcx, [rsp+48h+pguid]; pguid
0x18005c578  call    cs:__imp_CoCreateGuid
0x18005c57f  nop     dword ptr [rax+rax+00h]
0x18005c584  mov     ebx, eax
0x18005c586  test    eax, eax
0x18005c588  jns     short loc_18005C58E
0x18005c58a  mov     edx, eax
0x18005c58c  jmp     short loc_18005C5B3
0x18005c58e  mov     r8d, 27h ; '''; cchMax
0x18005c594  lea     rcx, [rsp+48h+pguid]; rguid
0x18005c599  mov     rdx, rdi; lpsz
0x18005c59c  call    cs:__imp_StringFromGUID2
0x18005c5a3  nop     dword ptr [rax+rax+00h]
0x18005c5a8  test    eax, eax
0x18005c5aa  jnz     short loc_18005C550
0x18005c5ac  mov     ebx, 8007006Fh
0x18005c5b1  mov     edx, ebx
0x18005c5b3  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x18005c5ba  call    cs:__imp_FwReportReturnError
0x18005c5c1  nop     dword ptr [rax+rax+00h]
0x18005c5c6  mov     rcx, rdi
0x18005c5c9  call    cs:__imp_FwBaseFree
0x18005c5d0  nop     dword ptr [rax+rax+00h]
0x18005c5d5  mov     edx, ebx
0x18005c5d7  lea     rcx, aFwcreateguidst; "FwCreateGuidString"
0x18005c5de  call    cs:__imp_FwReportReturnError
0x18005c5e5  nop     dword ptr [rax+rax+00h]
0x18005c5ea  mov     ebx, eax
0x18005c5ec  jmp     loc_18005C553
```
