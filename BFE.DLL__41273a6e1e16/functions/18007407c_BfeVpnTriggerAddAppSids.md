# BfeVpnTriggerAddAppSids

- ea: `0x18007407c`
- end: `0x1800741ad`
- name: `BfeVpnTriggerAddAppSids`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066460`

## callees

- `0x180010d60`
- `0x180012d8c`
- `0x1800197d0`
- `0x180020690`
- `0x18005aa60`
- `0x18007407c`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800740d6`
- `ntdll!RtlValidSid` at `0x1800740d6`

## string_xrefs

- `0x180074163`: `BfeDriverAddVpnAppSids`
- `0x1800740f0`: `BfeVpnAppSidsValidate`
- `0x180074104`: `BfeVpnAppSidsValidate`
- `0x18007417b`: `BfeVpnTriggerAddAppSids`

## pseudocode

```c
__int64 __fastcall BfeVpnTriggerAddAppSids(unsigned int a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+30h] [rbp-38h]

  v5 = BfeAccessCheck((char *)gBfeVpnTriggerEventController, 0x400u, 0);
  if ( !v5 )
  {
    if ( a1 )
    {
      while ( (unsigned int)v5 < a1 )
      {
        if ( !RtlValidSid(*(PSID *)(a2 + 8 * v5)) )
          goto LABEL_6;
        v5 = (unsigned int)(v5 + 1);
      }
    }
    else
    {
LABEL_6:
      v6 = WfpReportSysErrorAsWinError(v4, "BfeVpnAppSidsValidate", 2150760501LL);
      v5 = v6;
      if ( v6 )
      {
        WfpReportError(v6, "BfeVpnAppSidsValidate");
LABEL_13:
        WfpReportError(v5, "BfeVpnTriggerAddAppSids");
        return v5;
      }
    }
    if ( gBfeDriverControlComponent == (HANDLE)-1LL )
    {
      v5 = 0;
    }
    else
    {
      v7 = BfeDeviceIoControlMarshalIn(gBfeDriverControlComponent, 0x128058u, 0, 0, v9, 0);
      v5 = v7;
      if ( v7 )
        WfpReportError(v7, "BfeDriverAddVpnAppSids");
    }
  }
  if ( v5 )
    goto LABEL_13;
  return v5;
}

```

## disassembly

```asm
0x18007407c  mov     r11, rsp
0x18007407f  mov     [r11+18h], rbx
0x180074083  mov     [r11+20h], rsi
0x180074087  push    rdi
0x180074088  sub     rsp, 60h
0x18007408c  mov     rax, cs:__security_cookie
0x180074093  xor     rax, rsp
0x180074096  mov     [rsp+68h+var_18], rax
0x18007409b  xor     eax, eax
0x18007409d  mov     rsi, rdx
0x1800740a0  mov     edi, ecx
0x1800740a2  mov     [r11-24h], rax
0x1800740a6  mov     rcx, qword ptr cs:gBfeVpnTriggerEventController; pSecurityDescriptor
0x1800740ad  xor     r8d, r8d
0x1800740b0  mov     edx, 400h
0x1800740b5  mov     [r11-28h], rax
0x1800740b9  call    BfeAccessCheck
0x1800740be  mov     rbx, rax
0x1800740c1  test    rax, rax
0x1800740c4  jnz     loc_180074176
0x1800740ca  test    edi, edi
0x1800740cc  jz      short loc_1800740EA
0x1800740ce  cmp     ebx, edi
0x1800740d0  jnb     short loc_180074115
0x1800740d2  mov     rcx, [rsi+rbx*8]; Sid
0x1800740d6  call    cs:__imp_RtlValidSid
0x1800740dd  nop     dword ptr [rax+rax+00h]
0x1800740e2  test    al, al
0x1800740e4  jz      short loc_1800740EA
0x1800740e6  inc     ebx
0x1800740e8  jmp     short loc_1800740CE
0x1800740ea  mov     r8d, 80320035h
0x1800740f0  lea     rdx, aBfevpnappsidsv; "BfeVpnAppSidsValidate"
0x1800740f7  call    WfpReportSysErrorAsWinError
0x1800740fc  mov     rbx, rax
0x1800740ff  test    rax, rax
0x180074102  jz      short loc_180074115
0x180074104  lea     rdx, aBfevpnappsidsv; "BfeVpnAppSidsValidate"
0x18007410b  mov     rcx, rax
0x18007410e  call    WfpReportError
0x180074113  jmp     short loc_18007417B
0x180074115  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x18007411c  mov     [rsp+68h+var_28], edi
0x180074120  mov     [rsp+68h+var_20], rsi
0x180074125  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180074129  jz      short loc_180074174
0x18007412b  mov     [rsp+68h+var_30], 0; __int64
0x180074134  lea     r9, [rsp+68h+var_28]
0x180074139  mov     [rsp+68h+var_40], 0; PVOID
0x180074142  lea     r8, WFP_DRIVER_ADD_VPN_TRIGGER_APP_SIDS_IOCTL_Encode
0x180074149  mov     edx, 128058h; IoControlCode
0x18007414e  mov     [rsp+68h+var_48], 0; ULONG
0x180074156  call    BfeDeviceIoControlMarshalIn
0x18007415b  mov     rbx, rax
0x18007415e  test    rax, rax
0x180074161  jz      short loc_180074176
0x180074163  lea     rdx, aBfedriveraddvp_0; "BfeDriverAddVpnAppSids"
0x18007416a  mov     rcx, rax
0x18007416d  call    WfpReportError
0x180074172  jmp     short loc_180074176
0x180074174  xor     ebx, ebx
0x180074176  test    rbx, rbx
0x180074179  jz      short loc_18007418A
0x18007417b  lea     rdx, aBfevpntriggera_1; "BfeVpnTriggerAddAppSids"
0x180074182  mov     rcx, rbx
0x180074185  call    WfpReportError
0x18007418a  mov     rax, rbx
0x18007418d  mov     rcx, [rsp+68h+var_18]
0x180074192  xor     rcx, rsp; StackCookie
0x180074195  call    __security_check_cookie
0x18007419a  lea     r11, [rsp+68h+var_8]
0x18007419f  mov     rbx, [r11+20h]
0x1800741a3  mov     rsi, [r11+28h]
0x1800741a7  mov     rsp, r11
0x1800741aa  pop     rdi
0x1800741ab  retn
```
