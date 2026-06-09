# FwConvertServiceSettingsToRules(ICF_AUTHBYPASS_SERVICES_,ulong,_tag_FW_RULE * *,ulong *)

- ea: `0x18002ad4c`
- end: `0x18002b02a`
- name: `?FwConvertServiceSettingsToRules@@YAJUICF_AUTHBYPASS_SERVICES_@@KPEAPEAU_tag_FW_RULE@@PEAK@Z`
- size: `734`
- prototype: `__int64 __fastcall(unsigned int *, int, struct _tag_FW_RULE **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18001ba5c`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180006f50`
- `0x18001eaf4`
- `0x18001f650`
- `0x1800210a8`
- `0x1800230c0`
- `0x18002ad4c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002afe5`
- `fwbase!FwArrayCopy` at `0x18002ae97`
- `fwbase!FwArrayCopy` at `0x18002ae97`
- `fwbase!FwStringCopy` at `0x18002aef9`
- `fwbase!FwStringCopy` at `0x18002aef9`
- `fwbase!FwReportReturnError` at `0x18002af7c`
- `fwbase!FwReportReturnError` at `0x18002af8d`
- `fwbase!FwReportReturnError` at `0x18002affc`
- `fwbase!FwReportReturnError` at `0x18002af7c`
- `fwbase!FwReportReturnError` at `0x18002af8d`
- `fwbase!FwReportReturnError` at `0x18002affc`
- `fwbase!FwGetService` at `0x18002adea`
- `fwbase!FwGetService` at `0x18002adea`

## string_xrefs

- `0x18002af75`: `FwConvertServiceSettingsToRules`
- `0x18002af86`: `FwConvertServiceSettingsToRules`
- `0x18002aff5`: `FwConvertServiceSettingsToRules`

## pseudocode

```c
__int64 __fastcall FwConvertServiceSettingsToRules(
        unsigned int *a1,
        int a2,
        struct _tag_FW_RULE **a3,
        unsigned int *a4)
{
  unsigned int v4; // eax
  __int64 v5; // r14
  unsigned int v6; // ebx
  struct _tag_FW_RULE *v7; // rdi
  unsigned int v8; // r15d
  unsigned __int64 v9; // rsi
  __int64 Service; // rdx
  unsigned int v11; // r12d
  unsigned int v12; // eax
  unsigned int v13; // r13d
  int OpenPortRuleFromBuiltInPort; // eax
  int v15; // eax
  int v16; // ecx
  unsigned int *v17; // r8
  struct _tag_FW_RULE **v18; // rdx
  unsigned int v20; // [rsp+30h] [rbp-40h]
  struct _tag_FW_RULE *v21; // [rsp+38h] [rbp-38h] BYREF
  int v22; // [rsp+40h] [rbp-30h]
  unsigned int v23; // [rsp+44h] [rbp-2Ch]
  unsigned int *v24; // [rsp+48h] [rbp-28h]
  struct _tag_FW_RULE **v25; // [rsp+50h] [rbp-20h]
  __int64 v26; // [rsp+58h] [rbp-18h]
  HLOCAL hMem; // [rsp+60h] [rbp-10h] BYREF

  v4 = *a1;
  v5 = *((_QWORD *)a1 + 1);
  v20 = *a1;
  v24 = a4;
  v25 = a3;
  v22 = a2;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v4 = v20;
  }
  v6 = 0;
  v7 = 0;
  hMem = 0;
  v8 = 0;
  v21 = 0;
  while ( v8 < v4 )
  {
    v9 = (unsigned __int64)v8 << 6;
    if ( *(_DWORD *)(v9 + v5 + 16) )
    {
      Service = FwGetService(*(unsigned int *)(v9 + v5 + 8));
      v26 = Service;
      v11 = 0;
LABEL_8:
      if ( v11 < *(_DWORD *)(Service + 16) )
      {
        v12 = *(_DWORD *)(v9 + v5 + 48);
        if ( !v12 )
          v12 = 1;
        v13 = 0;
        v23 = v12;
        while ( 1 )
        {
          if ( v13 >= v12 )
          {
            ++v11;
            goto LABEL_8;
          }
          OpenPortRuleFromBuiltInPort = CreateOpenPortRuleFromBuiltInPort(
                                          (unsigned int *)(*(_QWORD *)(Service + 24) + 32LL * v11),
                                          (void **)&v21);
          v6 = OpenPortRuleFromBuiltInPort;
          if ( OpenPortRuleFromBuiltInPort < 0 )
            break;
          v7 = v21;
          *((_DWORD *)v21 + 10) = v22;
          if ( *(_DWORD *)(v9 + v5 + 24) == 1 )
          {
            *((_DWORD *)v7 + 44) |= 1u;
            *((_DWORD *)v7 + 45) |= 1u;
          }
          else
          {
            *((_DWORD *)v7 + 44) &= ~1u;
            *((_DWORD *)v7 + 45) &= ~1u;
          }
          v15 = FwArrayCopy(
                  8,
                  FwCopyIPv4SubNet,
                  wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
                  v9 + v5 + 32,
                  (char *)v7 + 184);
          v6 = v15;
          if ( v15 < 0 )
          {
LABEL_27:
            FwReportReturnError("FwConvertServiceSettingsToRules", (unsigned int)v15);
            goto LABEL_31;
          }
          v16 = 3 - (*(_DWORD *)(v9 + v5 + 16) != 2);
          *((_DWORD *)v7 + 72) = v16;
          if ( *(_DWORD *)(v9 + v5 + 48) && v16 != 2 )
          {
            v15 = FwMigrateLegacyAuthenticatedBypassSddl(*(_QWORD *)(*(_QWORD *)(v9 + v5 + 56) + 16LL * v13), &hMem);
            v6 = v15;
            if ( v15 < 0 )
              goto LABEL_27;
            v15 = FwStringCopy(hMem, (char *)v7 + 296);
            v6 = v15;
            if ( v15 < 0 )
              goto LABEL_27;
            LocalFree(hMem);
            hMem = 0;
            *((_WORD *)v7 + 146) |= 2u;
          }
          v17 = v24;
          v18 = v25;
          *((_WORD *)v7 + 4) = 256;
          *((_WORD *)v7 + 146) |= 1u;
          AddRuleToList(v7, v18, v17);
          v12 = v23;
          v7 = 0;
          Service = v26;
          ++v13;
          v21 = 0;
        }
        FwReportReturnError("FwConvertServiceSettingsToRules", (unsigned int)OpenPortRuleFromBuiltInPort);
        v7 = v21;
        goto LABEL_31;
      }
      v4 = v20;
    }
    ++v8;
  }
  if ( (v6 & 0x80000000) == 0 )
    return v6;
LABEL_31:
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v6);
  FwFreeWFRule(v7);
  if ( hMem )
    LocalFree(hMem);
  hMem = 0;
  return (unsigned int)FwReportReturnError("FwConvertServiceSettingsToRules", v6);
}

```

## disassembly

```asm
0x18002ad4c  mov     [rsp-38h+arg_8], rbx
0x18002ad51  push    rbp
0x18002ad52  push    rsi
0x18002ad53  push    rdi
0x18002ad54  push    r12
0x18002ad56  push    r13
0x18002ad58  push    r14
0x18002ad5a  push    r15
0x18002ad5c  mov     rbp, rsp
0x18002ad5f  sub     rsp, 70h
0x18002ad63  mov     rax, cs:__security_cookie
0x18002ad6a  xor     rax, rsp
0x18002ad6d  mov     [rbp+var_8], rax
0x18002ad71  mov     eax, [rcx]
0x18002ad73  mov     r14, [rcx+8]
0x18002ad77  mov     [rbp+var_40], eax
0x18002ad7a  mov     [rbp+var_28], r9
0x18002ad7e  mov     [rbp+var_20], r8
0x18002ad82  mov     [rbp+var_30], edx
0x18002ad85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad8c  lea     rdx, WPP_GLOBAL_Control
0x18002ad93  cmp     rcx, rdx
0x18002ad96  jz      short loc_18002ADB6
0x18002ad98  test    byte ptr [rcx+1Ch], 8
0x18002ad9c  jz      short loc_18002ADB6
0x18002ad9e  mov     rcx, [rcx+10h]
0x18002ada2  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ada9  mov     edx, 2Eh ; '.'
0x18002adae  call    WPP_SF_
0x18002adb3  mov     eax, [rbp+var_40]
0x18002adb6  xor     ebx, ebx
0x18002adb8  xor     edi, edi
0x18002adba  mov     [rbp+hMem], rbx
0x18002adbe  xor     r15d, r15d
0x18002adc1  mov     [rbp+var_38], rdi
0x18002adc5  lea     r13d, [rbx+1]
0x18002adc9  cmp     r15d, eax
0x18002adcc  jnb     loc_18002AF9F
0x18002add2  mov     esi, r15d
0x18002add5  shl     rsi, 6
0x18002add9  cmp     dword ptr [rsi+r14+10h], 0
0x18002addf  jz      loc_18002AF6B
0x18002ade5  mov     ecx, [rsi+r14+8]
0x18002adea  call    cs:__imp_FwGetService
0x18002adf0  mov     rdx, rax
0x18002adf3  mov     [rbp+var_18], rax
0x18002adf7  xor     r12d, r12d
0x18002adfa  cmp     r12d, [rdx+10h]
0x18002adfe  jnb     loc_18002AF68
0x18002ae04  mov     eax, [rsi+r14+30h]
0x18002ae09  test    eax, eax
0x18002ae0b  cmovz   eax, r13d
0x18002ae0f  xor     r13d, r13d
0x18002ae12  mov     [rbp+var_2C], eax
0x18002ae15  cmp     r13d, eax
0x18002ae18  jnb     loc_18002AF5A
0x18002ae1e  mov     ecx, r12d
0x18002ae21  shl     rcx, 5
0x18002ae25  add     rcx, [rdx+18h]
0x18002ae29  lea     rdx, [rbp+var_38]
0x18002ae2d  call    ?CreateOpenPortRuleFromBuiltInPort@@YAJPEBUFW_BUILTIN_PORT_@@PEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateOpenPortRuleFromBuiltInPort(FW_BUILTIN_PORT_ const *,_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18002ae32  mov     ebx, eax
0x18002ae34  test    eax, eax
0x18002ae36  js      loc_18002AF84
0x18002ae3c  mov     eax, [rbp+var_30]
0x18002ae3f  mov     rdi, [rbp+var_38]
0x18002ae43  mov     [rdi+28h], eax
0x18002ae46  mov     eax, 1
0x18002ae4b  cmp     [rsi+r14+18h], eax
0x18002ae50  jnz     short loc_18002AE60
0x18002ae52  or      [rdi+0B0h], eax
0x18002ae58  or      [rdi+0B4h], eax
0x18002ae5e  jmp     short loc_18002AE71
0x18002ae60  mov     eax, 0FFFFFFFEh
0x18002ae65  and     [rdi+0B0h], eax
0x18002ae6b  and     [rdi+0B4h], eax
0x18002ae71  lea     rax, [rdi+0B8h]
0x18002ae78  mov     ecx, 8
0x18002ae7d  lea     r9, [r14+20h]
0x18002ae81  mov     [rsp+70h+var_50], rax
0x18002ae86  add     r9, rsi
0x18002ae89  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18002ae90  lea     rdx, FwCopyIPv4SubNet
0x18002ae97  call    cs:__imp_FwArrayCopy
0x18002ae9d  mov     ebx, eax
0x18002ae9f  test    eax, eax
0x18002aea1  js      loc_18002AF73
0x18002aea7  mov     edx, 2
0x18002aeac  mov     eax, edx
0x18002aeae  sub     eax, [rsi+r14+10h]
0x18002aeb3  neg     eax
0x18002aeb5  sbb     ecx, ecx
0x18002aeb7  add     ecx, 3
0x18002aeba  mov     [rdi+120h], ecx
0x18002aec0  cmp     dword ptr [rsi+r14+30h], 0
0x18002aec6  jz      short loc_18002AF23
0x18002aec8  cmp     ecx, edx
0x18002aeca  jz      short loc_18002AF23
0x18002aecc  mov     rcx, [rsi+r14+38h]
0x18002aed1  lea     rdx, [rbp+hMem]
0x18002aed5  mov     eax, r13d
0x18002aed8  add     rax, rax
0x18002aedb  mov     rcx, [rcx+rax*8]
0x18002aedf  call    FwMigrateLegacyAuthenticatedBypassSddl
0x18002aee4  mov     ebx, eax
0x18002aee6  test    eax, eax
0x18002aee8  js      loc_18002AF73
0x18002aeee  mov     rcx, [rbp+hMem]
0x18002aef2  lea     rdx, [rdi+128h]
0x18002aef9  call    cs:__imp_FwStringCopy
0x18002aeff  mov     ebx, eax
0x18002af01  test    eax, eax
0x18002af03  js      short loc_18002AF73
0x18002af05  mov     rcx, [rbp+hMem]; hMem
0x18002af09  call    cs:__imp_LocalFree
0x18002af0f  mov     ecx, 2
0x18002af14  mov     [rbp+hMem], 0
0x18002af1c  or      [rdi+124h], cx
0x18002af23  mov     r8, [rbp+var_28]; unsigned int *
0x18002af27  mov     eax, 1
0x18002af2c  mov     rdx, [rbp+var_20]; struct _tag_FW_RULE **
0x18002af30  mov     rcx, rdi; struct _tag_FW_RULE *
0x18002af33  mov     word ptr [rdi+8], 100h
0x18002af39  or      [rdi+124h], ax
0x18002af40  call    ?AddRuleToList@@YAXPEAU_tag_FW_RULE@@PEAPEAU1@PEAK@Z; AddRuleToList(_tag_FW_RULE *,_tag_FW_RULE * *,ulong *)
0x18002af45  mov     eax, [rbp+var_2C]
0x18002af48  xor     edi, edi
0x18002af4a  mov     rdx, [rbp+var_18]
0x18002af4e  inc     r13d
0x18002af51  mov     [rbp+var_38], rdi
0x18002af55  jmp     loc_18002AE15
0x18002af5a  mov     r13d, 1
0x18002af60  add     r12d, r13d
0x18002af63  jmp     loc_18002ADFA
0x18002af68  mov     eax, [rbp+var_40]
0x18002af6b  add     r15d, r13d
0x18002af6e  jmp     loc_18002ADC9
0x18002af73  mov     edx, eax
0x18002af75  lea     rcx, aFwconvertservi; "FwConvertServiceSettingsToRules"
0x18002af7c  call    cs:__imp_FwReportReturnError
0x18002af82  jmp     short loc_18002AF97
0x18002af84  mov     edx, eax
0x18002af86  lea     rcx, aFwconvertservi; "FwConvertServiceSettingsToRules"
0x18002af8d  call    cs:__imp_FwReportReturnError
0x18002af93  mov     rdi, [rbp+var_38]
0x18002af97  mov     r13d, 1
0x18002af9d  jmp     short loc_18002AFA3
0x18002af9f  test    ebx, ebx
0x18002afa1  jns     short loc_18002B004
0x18002afa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afaa  lea     rax, WPP_GLOBAL_Control
0x18002afb1  cmp     rcx, rax
0x18002afb4  jz      short loc_18002AFD4
0x18002afb6  test    [rcx+1Ch], r13b
0x18002afba  jz      short loc_18002AFD4
0x18002afbc  mov     rcx, [rcx+10h]
0x18002afc0  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002afc7  mov     edx, 2Fh ; '/'
0x18002afcc  mov     r9d, ebx
0x18002afcf  call    WPP_SF_d
0x18002afd4  mov     rcx, rdi; void *
0x18002afd7  call    FwFreeWFRule
0x18002afdc  mov     rcx, [rbp+hMem]; hMem
0x18002afe0  test    rcx, rcx
0x18002afe3  jz      short loc_18002AFEB
0x18002afe5  call    cs:__imp_LocalFree
0x18002afeb  mov     edx, ebx
0x18002afed  mov     [rbp+hMem], 0
0x18002aff5  lea     rcx, aFwconvertservi; "FwConvertServiceSettingsToRules"
0x18002affc  call    cs:__imp_FwReportReturnError
0x18002b002  mov     ebx, eax
0x18002b004  mov     eax, ebx
0x18002b006  mov     rcx, [rbp+var_8]
0x18002b00a  xor     rcx, rsp; StackCookie
0x18002b00d  call    __security_check_cookie
0x18002b012  mov     rbx, [rsp+70h+arg_8]
0x18002b01a  add     rsp, 70h
0x18002b01e  pop     r15
0x18002b020  pop     r14
0x18002b022  pop     r13
0x18002b024  pop     r12
0x18002b026  pop     rdi
0x18002b027  pop     rsi
0x18002b028  pop     rbp
0x18002b029  retn
```
