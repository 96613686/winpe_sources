# BfeVpnTriggerAddAppSids

- ea: `0x180071840`
- end: `0x18007196a`
- name: `BfeVpnTriggerAddAppSids`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180064100`

## callees

- `0x180010360`
- `0x18001236c`
- `0x180018b74`
- `0x180024a44`
- `0x180058b30`
- `0x180071840`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18007189a`
- `ntdll!RtlValidSid` at `0x18007189a`

## string_xrefs

- `0x180071921`: `BfeDriverAddVpnAppSids`
- `0x1800718ae`: `BfeVpnAppSidsValidate`
- `0x1800718c2`: `BfeVpnAppSidsValidate`
- `0x180071939`: `BfeVpnTriggerAddAppSids`

## pseudocode

```c
__int64 __fastcall BfeVpnTriggerAddAppSids(unsigned int a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  int v9; // [rsp+30h] [rbp-38h]

  v5 = BfeAccessCheck((char *)qword_1800F2668[55], 0x400u, 0);
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
0x180071840  mov     r11, rsp
0x180071843  mov     [r11+18h], rbx
0x180071847  mov     [r11+20h], rsi
0x18007184b  push    rdi
0x18007184c  sub     rsp, 60h
0x180071850  mov     rax, cs:__security_cookie
0x180071857  xor     rax, rsp
0x18007185a  mov     [rsp+68h+var_18], rax
0x18007185f  xor     eax, eax
0x180071861  mov     rsi, rdx
0x180071864  mov     edi, ecx
0x180071866  mov     [r11-24h], rax
0x18007186a  mov     rcx, cs:qword_1800F2668+1B8h; pSecurityDescriptor
0x180071871  xor     r8d, r8d
0x180071874  mov     edx, 400h
0x180071879  mov     [r11-28h], rax
0x18007187d  call    BfeAccessCheck
0x180071882  mov     rbx, rax
0x180071885  test    rax, rax
0x180071888  jnz     loc_180071934
0x18007188e  test    edi, edi
0x180071890  jz      short loc_1800718A8
0x180071892  cmp     ebx, edi
0x180071894  jnb     short loc_1800718D3
0x180071896  mov     rcx, [rsi+rbx*8]; Sid
0x18007189a  call    cs:__imp_RtlValidSid
0x1800718a0  test    al, al
0x1800718a2  jz      short loc_1800718A8
0x1800718a4  inc     ebx
0x1800718a6  jmp     short loc_180071892
0x1800718a8  mov     r8d, 80320035h
0x1800718ae  lea     rdx, aBfevpnappsidsv; "BfeVpnAppSidsValidate"
0x1800718b5  call    WfpReportSysErrorAsWinError
0x1800718ba  mov     rbx, rax
0x1800718bd  test    rax, rax
0x1800718c0  jz      short loc_1800718D3
0x1800718c2  lea     rdx, aBfevpnappsidsv; "BfeVpnAppSidsValidate"
0x1800718c9  mov     rcx, rax
0x1800718cc  call    WfpReportError
0x1800718d1  jmp     short loc_180071939
0x1800718d3  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x1800718da  mov     [rsp+68h+var_28], edi
0x1800718de  mov     [rsp+68h+var_20], rsi
0x1800718e3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800718e7  jz      short loc_180071932
0x1800718e9  mov     [rsp+68h+var_30], 0; __int64
0x1800718f2  lea     r9, [rsp+68h+var_28]
0x1800718f7  mov     [rsp+68h+var_40], 0; PVOID
0x180071900  lea     r8, WFP_DRIVER_ADD_VPN_TRIGGER_APP_SIDS_IOCTL_Encode
0x180071907  mov     edx, 128058h; IoControlCode
0x18007190c  mov     [rsp+68h+var_48], 0; ULONG
0x180071914  call    BfeDeviceIoControlMarshalIn
0x180071919  mov     rbx, rax
0x18007191c  test    rax, rax
0x18007191f  jz      short loc_180071934
0x180071921  lea     rdx, aBfedriveraddvp_0; "BfeDriverAddVpnAppSids"
0x180071928  mov     rcx, rax
0x18007192b  call    WfpReportError
0x180071930  jmp     short loc_180071934
0x180071932  xor     ebx, ebx
0x180071934  test    rbx, rbx
0x180071937  jz      short loc_180071948
0x180071939  lea     rdx, aBfevpntriggera_1; "BfeVpnTriggerAddAppSids"
0x180071940  mov     rcx, rbx
0x180071943  call    WfpReportError
0x180071948  mov     rax, rbx
0x18007194b  mov     rcx, [rsp+68h+var_18]
0x180071950  xor     rcx, rsp; StackCookie
0x180071953  call    __security_check_cookie
0x180071958  lea     r11, [rsp+68h+var_8]
0x18007195d  mov     rbx, [r11+20h]
0x180071961  mov     rsi, [r11+28h]
0x180071965  mov     rsp, r11
0x180071968  pop     rdi
0x180071969  retn
```
