# FwGetConfig

- ea: `0x180002c50`
- end: `0x180002edb`
- name: `FwGetConfig`
- size: `651`
- prototype: `__int64 __usercall@<rax>(struct _tag_WF_POLICY_STORE *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002bf6c`

## callees

- `0x18000203c`
- `0x180002c50`
- `0x180003b94`
- `0x1800042c4`
- `0x180004958`
- `0x180014280`
- `0x180014570`
- `0x18001e670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002da5`

## string_xrefs

- `0x180002d25`: `FwGetConfig`

## pseudocode

```c
__int64 __fastcall FwGetConfig(struct _tag_WF_POLICY_STORE *a1, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  unsigned int v6; // r15d
  int v7; // r13d
  LPCOLESTR v9; // rcx
  __int64 v10; // rbp
  unsigned int Config_Internal; // ebx
  int v13; // r15d
  unsigned int i; // esi
  int refreshed; // eax
  signed int LastError; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // [rsp+90h] [rbp+18h]

  v19 = a3;
  v6 = a3;
  v7 = a2;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = 0;
  if ( !a1 || v7 >= 19 || !a5 )
  {
    Config_Internal = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return Config_Internal;
    if ( (v9[14] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v9 + 2), 128, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, 2147942487LL);
      v9 = WPP_GLOBAL_Control;
    }
    goto LABEL_22;
  }
  v13 = *a5;
  if ( !a4 && v13 )
  {
    v17 = 2147942487LL;
    Config_Internal = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return Config_Internal;
    if ( (v9[14] & 1) == 0 )
      goto LABEL_21;
    v18 = 129;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v9 + 2), v18, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v17);
    v9 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  Config_Internal = 0;
  if ( !*((_QWORD *)a1 + 5) )
  {
    refreshed = FwRefreshPolicyStore(a1);
    Config_Internal = refreshed;
    if ( refreshed < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_21;
      v18 = 130;
LABEL_34:
      v17 = (unsigned int)refreshed;
      goto LABEL_35;
    }
  }
  if ( *((_DWORD *)a1 + 2) != 1 || (v10 = FWGPLock(v9, a2, a3)) != 0 )
  {
    for ( i = 0; i < 5; ++i )
    {
      *a5 = v13;
      Config_Internal = FwGetConfig_Internal((__int64)a1, (unsigned int)v7, v19, a4, (__int64)a5);
      if ( Config_Internal != -2147023878 )
        break;
      refreshed = FwRefreshPolicyStore(a1);
      Config_Internal = refreshed;
      if ( refreshed < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v18 = 132;
          goto LABEL_34;
        }
        goto LABEL_21;
      }
    }
    goto LABEL_14;
  }
  LastError = GetLastError();
  Config_Internal = LastError;
  if ( LastError > 0 )
    Config_Internal = (unsigned __int16)LastError | 0x80070000;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, Config_Internal);
LABEL_14:
    v9 = WPP_GLOBAL_Control;
  }
  if ( (Config_Internal & 0x80000000) != 0 )
  {
LABEL_21:
    v6 = v19;
LABEL_22:
    if ( v9 != (LPCOLESTR)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
      WPP_SF_ddd(*((_QWORD *)v9 + 2), 133, a3, (unsigned int)v7, v6, Config_Internal);
  }
  if ( v10 )
    FWGPUnlockEx(v10, "FwGetConfig");
  return Config_Internal;
}

```

## disassembly

```asm
0x180002c50  mov     [rsp+arg_10], r8d
0x180002c55  push    rbx
0x180002c56  push    rbp
0x180002c57  push    rsi
0x180002c58  push    rdi
0x180002c59  push    r12
0x180002c5b  push    r13
0x180002c5d  push    r14
0x180002c5f  push    r15
0x180002c61  sub     rsp, 38h
0x180002c65  mov     r12, r9
0x180002c68  mov     r15d, r8d
0x180002c6b  mov     r13d, edx
0x180002c6e  mov     rdi, rcx
0x180002c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c78  lea     rsi, WPP_GLOBAL_Control
0x180002c7f  cmp     rcx, rsi
0x180002c82  jz      short loc_180002CA6
0x180002c84  test    byte ptr [rcx+1Ch], 8
0x180002c88  jz      short loc_180002CA6
0x180002c8a  mov     rcx, [rcx+10h]
0x180002c8e  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002c95  mov     edx, 7Fh
0x180002c9a  call    WPP_SF_
0x180002c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ca6  xor     ebp, ebp
0x180002ca8  test    rdi, rdi
0x180002cab  jnz     short loc_180002CD2
0x180002cad  mov     r9d, 80070057h
0x180002cb3  mov     ebx, r9d
0x180002cb6  cmp     rcx, rsi
0x180002cb9  jnz     loc_180002EB0
0x180002cbf  mov     eax, ebx
0x180002cc1  add     rsp, 38h
0x180002cc5  pop     r15
0x180002cc7  pop     r14
0x180002cc9  pop     r13
0x180002ccb  pop     r12
0x180002ccd  pop     rdi
0x180002cce  pop     rsi
0x180002ccf  pop     rbp
0x180002cd0  pop     rbx
0x180002cd1  retn
0x180002cd2  cmp     r13d, 13h
0x180002cd6  jge     short loc_180002CAD
0x180002cd8  mov     r14, [rsp+78h+arg_20]
0x180002ce0  test    r14, r14
0x180002ce3  jz      short loc_180002CAD
0x180002ce5  mov     r15d, [r14]
0x180002ce8  test    r12, r12
0x180002ceb  jz      loc_180002DF1
0x180002cf1  xor     ebx, ebx
0x180002cf3  cmp     [rdi+28h], rbx
0x180002cf7  jz      loc_180002E41
0x180002cfd  cmp     dword ptr [rdi+8], 1
0x180002d01  jz      loc_180002E6F
0x180002d07  xor     esi, esi
0x180002d09  cmp     esi, 5
0x180002d0c  jb      short loc_180002D36
0x180002d0e  lea     rsi, WPP_GLOBAL_Control
0x180002d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1c  test    ebx, ebx
0x180002d1e  js      short loc_180002D73
0x180002d20  test    rbp, rbp
0x180002d23  jz      short loc_180002CBF
0x180002d25  lea     rdx, aFwgetconfig_0; "FwGetConfig"
0x180002d2c  mov     rcx, rbp
0x180002d2f  call    FWGPUnlockEx
0x180002d34  jmp     short loc_180002CBF
0x180002d36  mov     r8d, [rsp+78h+arg_10]
0x180002d3e  mov     r9, r12
0x180002d41  mov     edx, r13d
0x180002d44  mov     [r14], r15d
0x180002d47  mov     rcx, rdi
0x180002d4a  mov     [rsp+78h+var_58], r14
0x180002d4f  call    ?FwGetConfig_Internal@@YAJPEAXW4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@0PEAK@Z; FwGetConfig_Internal(void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,void *,ulong *)
0x180002d54  mov     ebx, eax
0x180002d56  cmp     eax, 800703FAh
0x180002d5b  jnz     short loc_180002D0E
0x180002d5d  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x180002d60  call    ?FwRefreshPolicyStore@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; FwRefreshPolicyStore(_tag_WF_POLICY_STORE *)
0x180002d65  mov     ebx, eax
0x180002d67  test    eax, eax
0x180002d69  js      loc_180002E85
0x180002d6f  inc     esi
0x180002d71  jmp     short loc_180002D09
0x180002d73  mov     r15d, [rsp+78h+arg_10]
0x180002d7b  cmp     rcx, rsi
0x180002d7e  jz      short loc_180002D20
0x180002d80  test    byte ptr [rcx+1Ch], 1
0x180002d84  jz      short loc_180002D20
0x180002d86  mov     rcx, [rcx+10h]
0x180002d8a  mov     edx, 85h
0x180002d8f  mov     [rsp+78h+var_50], ebx
0x180002d93  mov     r9d, r13d
0x180002d96  mov     dword ptr [rsp+78h+var_58], r15d
0x180002d9b  call    WPP_SF_ddd
0x180002da0  jmp     loc_180002D20
0x180002da5  call    cs:__imp_GetLastError
0x180002dab  mov     ebx, eax
0x180002dad  test    eax, eax
0x180002daf  jle     short loc_180002DBA
0x180002db1  movzx   ebx, ax
0x180002db4  or      ebx, 80070000h
0x180002dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc1  cmp     rcx, rsi
0x180002dc4  jz      loc_180002D1C
0x180002dca  test    byte ptr [rcx+1Ch], 1
0x180002dce  jz      loc_180002D1C
0x180002dd4  mov     rcx, [rcx+10h]
0x180002dd8  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002ddf  mov     edx, 83h
0x180002de4  mov     r9d, ebx
0x180002de7  call    WPP_SF_d
0x180002dec  jmp     loc_180002D15
0x180002df1  test    r15d, r15d
0x180002df4  jz      loc_180002CF1
0x180002dfa  mov     r9d, 80070057h
0x180002e00  mov     ebx, r9d
0x180002e03  cmp     rcx, rsi
0x180002e06  jz      loc_180002CBF
0x180002e0c  test    byte ptr [rcx+1Ch], 1
0x180002e10  jz      loc_180002D73
0x180002e16  mov     edx, 81h
0x180002e1b  jmp     short loc_180002E25
0x180002e1d  mov     edx, 82h
0x180002e22  mov     r9d, eax
0x180002e25  mov     rcx, [rcx+10h]
0x180002e29  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002e30  call    WPP_SF_d
0x180002e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3c  jmp     loc_180002D73
0x180002e41  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x180002e44  call    ?FwRefreshPolicyStore@@YAJPEAU_tag_WF_POLICY_STORE@@@Z; FwRefreshPolicyStore(_tag_WF_POLICY_STORE *)
0x180002e49  mov     ebx, eax
0x180002e4b  test    eax, eax
0x180002e4d  jns     loc_180002CFD
0x180002e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e5a  cmp     rcx, rsi
0x180002e5d  jz      loc_180002D73
0x180002e63  test    byte ptr [rcx+1Ch], 1
0x180002e67  jz      loc_180002D73
0x180002e6d  jmp     short loc_180002E1D
0x180002e6f  call    FWGPLock
0x180002e74  mov     rbp, rax
0x180002e77  test    rax, rax
0x180002e7a  jnz     loc_180002D07
0x180002e80  jmp     loc_180002DA5
0x180002e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e8c  lea     rsi, WPP_GLOBAL_Control
0x180002e93  cmp     rcx, rsi
0x180002e96  jz      loc_180002D73
0x180002e9c  test    byte ptr [rcx+1Ch], 1
0x180002ea0  jz      loc_180002D73
0x180002ea6  mov     edx, 84h
0x180002eab  jmp     loc_180002E22
0x180002eb0  test    byte ptr [rcx+1Ch], 1
0x180002eb4  jz      loc_180002D7B
0x180002eba  mov     rcx, [rcx+10h]
0x180002ebe  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180002ec5  mov     edx, 80h
0x180002eca  call    WPP_SF_d
0x180002ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed6  jmp     loc_180002D7B
```
