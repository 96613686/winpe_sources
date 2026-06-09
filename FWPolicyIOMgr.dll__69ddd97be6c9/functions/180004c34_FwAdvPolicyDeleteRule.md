# FwAdvPolicyDeleteRule

- ea: `0x180004c34`
- end: `0x180004dfb`
- name: `FwAdvPolicyDeleteRule`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800044f0`

## callees

- `0x1800042c4`
- `0x180004874`
- `0x180004c34`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x180004c91`
- `fwbase!FwRegOpenKey` at `0x180004c91`
- `fwbase!FwRegCloseKey` at `0x180004cee`
- `fwbase!FwRegCloseKey` at `0x180004cee`
- `fwbase!FwRegDeleteValue` at `0x180004cd9`
- `fwbase!FwRegDeleteValue` at `0x180004cd9`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyDeleteRule(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h] BYREF
  int v14; // [rsp+40h] [rbp-28h] BYREF

  v13 = 0;
  v12 = 0;
  v14 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v6 = FwRegOpenKey(a1, a2, 3, &v13, &v14);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_8;
    v10 = 63;
LABEL_24:
    v11 = (unsigned int)v6;
    goto LABEL_25;
  }
  if ( !v14 )
  {
    v11 = 2147942402LL;
    v7 = -2147024894;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_8;
    v10 = 64;
LABEL_25:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v11);
    goto LABEL_8;
  }
  v6 = FwAdvPolicyLookForRuleID(v13, a3, &v12);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_8;
    v10 = 65;
    goto LABEL_24;
  }
  if ( !v12 )
  {
    v11 = 2147942402LL;
    v7 = -2147024894;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_8;
    v10 = 66;
    goto LABEL_25;
  }
  v6 = FwRegDeleteValue(v13, 0, a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 67;
      goto LABEL_24;
    }
  }
LABEL_8:
  FwRegCloseKey(v13);
  return v7;
}

```

## disassembly

```asm
0x180004c34  push    rbx
0x180004c36  push    rsi
0x180004c37  push    rdi
0x180004c38  sub     rsp, 50h
0x180004c3c  mov     rax, cs:__security_cookie
0x180004c43  xor     rax, rsp
0x180004c46  mov     [rsp+68h+var_20], rax
0x180004c4b  mov     [rsp+68h+var_30], 0
0x180004c54  mov     rdi, r8
0x180004c57  mov     [rsp+68h+var_38], 0
0x180004c5f  mov     rsi, rdx
0x180004c62  mov     [rsp+68h+var_28], 0
0x180004c6a  mov     rbx, rcx
0x180004c6d  test    rcx, rcx
0x180004c70  jz      loc_180004D2E
0x180004c76  lea     rax, [rsp+68h+var_28]
0x180004c7b  mov     r8d, 3
0x180004c81  lea     r9, [rsp+68h+var_30]
0x180004c86  mov     [rsp+68h+var_48], rax
0x180004c8b  mov     rdx, rsi
0x180004c8e  mov     rcx, rbx
0x180004c91  call    cs:__imp_FwRegOpenKey
0x180004c97  mov     ebx, eax
0x180004c99  test    eax, eax
0x180004c9b  js      short loc_180004D0B
0x180004c9d  cmp     [rsp+68h+var_28], 0
0x180004ca2  jz      loc_180004D38
0x180004ca8  mov     rcx, [rsp+68h+var_30]
0x180004cad  lea     r8, [rsp+68h+var_38]
0x180004cb2  mov     rdx, rdi
0x180004cb5  call    FwAdvPolicyLookForRuleID
0x180004cba  mov     ebx, eax
0x180004cbc  test    eax, eax
0x180004cbe  js      loc_180004D64
0x180004cc4  cmp     [rsp+68h+var_38], 0
0x180004cc9  jz      loc_180004D8C
0x180004ccf  mov     rcx, [rsp+68h+var_30]
0x180004cd4  mov     r8, rdi
0x180004cd7  xor     edx, edx
0x180004cd9  call    cs:__imp_FwRegDeleteValue
0x180004cdf  mov     ebx, eax
0x180004ce1  test    eax, eax
0x180004ce3  js      loc_180004DBD
0x180004ce9  mov     rcx, [rsp+68h+var_30]
0x180004cee  call    cs:__imp_FwRegCloseKey
0x180004cf4  mov     eax, ebx
0x180004cf6  mov     rcx, [rsp+68h+var_20]
0x180004cfb  xor     rcx, rsp; StackCookie
0x180004cfe  call    __security_check_cookie
0x180004d03  add     rsp, 50h
0x180004d07  pop     rdi
0x180004d08  pop     rsi
0x180004d09  pop     rbx
0x180004d0a  retn
0x180004d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d12  lea     rdx, WPP_GLOBAL_Control
0x180004d19  cmp     rcx, rdx
0x180004d1c  jz      short loc_180004CE9
0x180004d1e  test    byte ptr [rcx+1Ch], 1
0x180004d22  jz      short loc_180004CE9
0x180004d24  mov     edx, 3Fh ; '?'
0x180004d29  jmp     loc_180004DE3
0x180004d2e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180004d33  jmp     loc_180004C76
0x180004d38  mov     r9d, 80070002h
0x180004d3e  mov     ebx, r9d
0x180004d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d48  lea     rdx, WPP_GLOBAL_Control
0x180004d4f  cmp     rcx, rdx
0x180004d52  jz      short loc_180004CE9
0x180004d54  test    byte ptr [rcx+1Ch], 1
0x180004d58  jz      short loc_180004CE9
0x180004d5a  mov     edx, 40h ; '@'
0x180004d5f  jmp     loc_180004DE6
0x180004d64  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d6b  lea     rdx, WPP_GLOBAL_Control
0x180004d72  cmp     rcx, rdx
0x180004d75  jz      loc_180004CE9
0x180004d7b  test    byte ptr [rcx+1Ch], 1
0x180004d7f  jz      loc_180004CE9
0x180004d85  mov     edx, 41h ; 'A'
0x180004d8a  jmp     short loc_180004DE3
0x180004d8c  mov     r9d, 80070002h
0x180004d92  mov     ebx, r9d
0x180004d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d9c  lea     rdx, WPP_GLOBAL_Control
0x180004da3  cmp     rcx, rdx
0x180004da6  jz      loc_180004CE9
0x180004dac  test    byte ptr [rcx+1Ch], 1
0x180004db0  jz      loc_180004CE9
0x180004db6  mov     edx, 42h ; 'B'
0x180004dbb  jmp     short loc_180004DE6
0x180004dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dc4  lea     rdx, WPP_GLOBAL_Control
0x180004dcb  cmp     rcx, rdx
0x180004dce  jz      loc_180004CE9
0x180004dd4  test    byte ptr [rcx+1Ch], 1
0x180004dd8  jz      loc_180004CE9
0x180004dde  mov     edx, 43h ; 'C'
0x180004de3  mov     r9d, eax
0x180004de6  mov     rcx, [rcx+10h]
0x180004dea  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x180004df1  call    WPP_SF_d
0x180004df6  jmp     loc_180004CE9
```
