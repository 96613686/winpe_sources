# TryAutoUnlockVolumeWithSid(ushort const *,FveSidUnlockContext)

- ea: `0x180047b90`
- end: `0x180047e64`
- name: `?TryAutoUnlockVolumeWithSid@@YAJPEBGW4FveSidUnlockContext@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800050c4`
- `0x18000b570`

## callees

- `0x180009f60`
- `0x18002cac4`
- `0x180034070`
- `0x180047b90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047c8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047c8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047e1a`
- `FVEAPI!FveUnlockVolumeAuthMethodSid` at `0x180047d95`
- `FVEAPI!FveUnlockVolumeAuthMethodSid` at `0x180047d95`
- `FVEAPI!FveGetAuthMethodSidInformation` at `0x180047d64`
- `FVEAPI!FveGetAuthMethodSidInformation` at `0x180047d64`
- `FVEAPI!FveGetAuthMethodSid` at `0x180047c32`
- `FVEAPI!FveGetAuthMethodSid` at `0x180047ce9`
- `FVEAPI!FveGetAuthMethodSid` at `0x180047c32`
- `FVEAPI!FveGetAuthMethodSid` at `0x180047ce9`
- `FVEAPI!FveOpenVolumeW` at `0x180047bd7`
- `FVEAPI!FveOpenVolumeW` at `0x180047bd7`
- `FVEAPI!FveCloseVolume` at `0x180047e30`
- `FVEAPI!FveCloseVolume` at `0x180047e30`

## pseudocode

```c
__int64 __fastcall TryAutoUnlockVolumeWithSid(__int64 a1, int a2)
{
  int v3; // r12d
  unsigned int v4; // eax
  int AuthMethodSidInformation; // ebx
  unsigned int AuthMethodSid; // eax
  char *v7; // rax
  char *v8; // rsi
  unsigned int v9; // eax
  unsigned int i; // edi
  bool v11; // zf
  PVOID *v12; // rcx
  unsigned int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  __int16 v16[2]; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+44h] [rbp-Ch] BYREF

  v15 = -1;
  v16[0] = 0;
  v17 = 0;
  v14 = 0;
  v3 = a1;
  v4 = FveOpenVolumeW(a1, 0, &v15);
  AuthMethodSidInformation = v4;
  if ( !v4 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v4);
  if ( AuthMethodSidInformation >= 0 )
  {
LABEL_10:
    AuthMethodSid = FveGetAuthMethodSid(v15, 0, 0, &v14);
    AuthMethodSidInformation = AuthMethodSid;
    if ( !AuthMethodSid )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, AuthMethodSid);
    if ( AuthMethodSidInformation >= 0 )
    {
LABEL_11:
      if ( !v14 )
      {
        AuthMethodSidInformation = 1;
        goto LABEL_40;
      }
      v7 = (char *)LocalAlloc(0x40u, 16LL * v14);
      v8 = v7;
      if ( !v7 )
      {
        AuthMethodSidInformation = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            122,
            WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
            2147942414LL);
        goto LABEL_40;
      }
      v9 = FveGetAuthMethodSid(v15, 0, v7, &v14);
      AuthMethodSidInformation = v9;
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v9);
        if ( AuthMethodSidInformation < 0 )
        {
LABEL_39:
          LocalFree(v8);
          goto LABEL_40;
        }
      }
      for ( i = 0; ; ++i )
      {
        v11 = i == v14;
        if ( i >= v14 )
        {
LABEL_32:
          if ( v11 )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                124,
                (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                v3,
                a2);
              v12 = (PVOID *)WPP_GLOBAL_Control;
            }
            AuthMethodSidInformation = -2144272384;
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 )
              WPP_SF_d(v12[2], 125, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, 2150694912LL);
          }
          goto LABEL_39;
        }
        v16[0] = 0;
        v17 = 0;
        AuthMethodSidInformation = FveGetAuthMethodSidInformation(v15, &v8[16 * i], v16, 0, &v17);
        if ( AuthMethodSidInformation < 0 )
          goto LABEL_39;
        if ( a2 == 2 )
        {
          if ( (v16[0] & 1) == 0 )
            continue;
        }
        else if ( (v16[0] & 1) != 0 )
        {
          continue;
        }
        AuthMethodSidInformation = FveUnlockVolumeAuthMethodSid(v15, &v8[16 * i]);
        if ( AuthMethodSidInformation >= 0 )
        {
          v11 = i == v14;
          goto LABEL_32;
        }
      }
    }
  }
LABEL_40:
  if ( v15 != -1 )
    FveCloseVolume(v15);
  return (unsigned int)AuthMethodSidInformation;
}

```

## disassembly

```asm
0x180047b90  mov     [rsp-28h+arg_8], rbx
0x180047b95  mov     [rsp-28h+arg_10], rsi
0x180047b9a  push    rbp
0x180047b9b  push    rdi
0x180047b9c  push    r12
0x180047b9e  push    r14
0x180047ba0  push    r15
0x180047ba2  mov     rbp, rsp
0x180047ba5  sub     rsp, 50h
0x180047ba9  mov     rax, cs:__security_cookie
0x180047bb0  xor     rax, rsp
0x180047bb3  mov     [rbp+var_8], rax
0x180047bb7  xor     eax, eax
0x180047bb9  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x180047bc1  mov     r15d, edx
0x180047bc4  mov     [rbp+var_10], ax
0x180047bc8  xor     edx, edx
0x180047bca  mov     [rbp+var_C], eax
0x180047bcd  lea     r8, [rbp+var_18]
0x180047bd1  mov     [rbp+var_1C], eax
0x180047bd4  mov     r12, rcx
0x180047bd7  call    cs:__imp_FveOpenVolumeW
0x180047bde  nop     dword ptr [rax+rax+00h]
0x180047be3  lea     r14, WPP_GLOBAL_Control
0x180047bea  mov     edi, 40h ; '@'
0x180047bef  mov     ebx, eax
0x180047bf1  test    eax, eax
0x180047bf3  jz      short loc_180047C25
0x180047bf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bfc  cmp     rcx, r14
0x180047bff  jz      short loc_180047C1D
0x180047c01  test    [rcx+1Ch], dil
0x180047c05  jz      short loc_180047C1D
0x180047c07  mov     rcx, [rcx+10h]
0x180047c0b  lea     edx, [rdi+38h]
0x180047c0e  mov     r9d, eax
0x180047c11  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047c18  call    WPP_SF_d
0x180047c1d  test    ebx, ebx
0x180047c1f  js      loc_180047E26
0x180047c25  mov     rcx, [rbp+var_18]
0x180047c29  lea     r9, [rbp+var_1C]
0x180047c2d  xor     r8d, r8d
0x180047c30  xor     edx, edx
0x180047c32  call    cs:__imp_FveGetAuthMethodSid
0x180047c39  nop     dword ptr [rax+rax+00h]
0x180047c3e  mov     ebx, eax
0x180047c40  test    eax, eax
0x180047c42  jz      short loc_180047C76
0x180047c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c4b  cmp     rcx, r14
0x180047c4e  jz      short loc_180047C6E
0x180047c50  test    [rcx+1Ch], dil
0x180047c54  jz      short loc_180047C6E
0x180047c56  mov     rcx, [rcx+10h]
0x180047c5a  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047c61  mov     edx, 79h ; 'y'
0x180047c66  mov     r9d, eax
0x180047c69  call    WPP_SF_d
0x180047c6e  test    ebx, ebx
0x180047c70  js      loc_180047E26
0x180047c76  mov     eax, [rbp+var_1C]
0x180047c79  test    eax, eax
0x180047c7b  jnz     short loc_180047C85
0x180047c7d  lea     ebx, [rax+1]
0x180047c80  jmp     loc_180047E26
0x180047c85  mov     rdx, rax
0x180047c88  mov     ecx, edi; uFlags
0x180047c8a  shl     rdx, 4; uBytes
0x180047c8e  call    cs:__imp_LocalAlloc
0x180047c95  nop     dword ptr [rax+rax+00h]
0x180047c9a  mov     rsi, rax
0x180047c9d  test    rax, rax
0x180047ca0  jnz     short loc_180047CDC
0x180047ca2  mov     ebx, 8007000Eh
0x180047ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cae  cmp     rcx, r14
0x180047cb1  jz      loc_180047E26
0x180047cb7  test    [rcx+1Ch], dil
0x180047cbb  jz      loc_180047E26
0x180047cc1  mov     rcx, [rcx+10h]
0x180047cc5  lea     edx, [rax+7Ah]
0x180047cc8  mov     r9d, ebx
0x180047ccb  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047cd2  call    WPP_SF_d
0x180047cd7  jmp     loc_180047E26
0x180047cdc  mov     rcx, [rbp+var_18]
0x180047ce0  lea     r9, [rbp+var_1C]
0x180047ce4  mov     r8, rsi
0x180047ce7  xor     edx, edx
0x180047ce9  call    cs:__imp_FveGetAuthMethodSid
0x180047cf0  nop     dword ptr [rax+rax+00h]
0x180047cf5  mov     ebx, eax
0x180047cf7  test    eax, eax
0x180047cf9  jz      short loc_180047D2D
0x180047cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d02  cmp     rcx, r14
0x180047d05  jz      short loc_180047D25
0x180047d07  test    [rcx+1Ch], dil
0x180047d0b  jz      short loc_180047D25
0x180047d0d  mov     rcx, [rcx+10h]
0x180047d11  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047d18  mov     edx, 7Bh ; '{'
0x180047d1d  mov     r9d, eax
0x180047d20  call    WPP_SF_d
0x180047d25  test    ebx, ebx
0x180047d27  js      loc_180047E17
0x180047d2d  xor     edi, edi
0x180047d2f  mov     eax, [rbp+var_1C]
0x180047d32  cmp     edi, eax
0x180047d34  jnb     short loc_180047DB0
0x180047d36  mov     rcx, [rbp+var_18]
0x180047d3a  lea     r8, [rbp+var_10]
0x180047d3e  xor     eax, eax
0x180047d40  mov     r14d, edi
0x180047d43  mov     [rbp+var_10], ax
0x180047d47  xor     r9d, r9d
0x180047d4a  lea     rax, [rbp+var_C]
0x180047d4e  shl     r14, 4
0x180047d52  add     r14, rsi
0x180047d55  mov     [rbp+var_C], 0
0x180047d5c  mov     rdx, r14
0x180047d5f  mov     [rsp+50h+var_30], rax
0x180047d64  call    cs:__imp_FveGetAuthMethodSidInformation
0x180047d6b  nop     dword ptr [rax+rax+00h]
0x180047d70  mov     ebx, eax
0x180047d72  test    eax, eax
0x180047d74  js      loc_180047E17
0x180047d7a  cmp     r15d, 2
0x180047d7e  jnz     short loc_180047D88
0x180047d80  test    byte ptr [rbp+var_10], 1
0x180047d84  jz      short loc_180047DA7
0x180047d86  jmp     short loc_180047D8E
0x180047d88  test    byte ptr [rbp+var_10], 1
0x180047d8c  jnz     short loc_180047DA7
0x180047d8e  mov     rcx, [rbp+var_18]
0x180047d92  mov     rdx, r14
0x180047d95  call    cs:__imp_FveUnlockVolumeAuthMethodSid
0x180047d9c  nop     dword ptr [rax+rax+00h]
0x180047da1  mov     ebx, eax
0x180047da3  test    eax, eax
0x180047da5  jns     short loc_180047DAB
0x180047da7  inc     edi
0x180047da9  jmp     short loc_180047D2F
0x180047dab  mov     eax, [rbp+var_1C]
0x180047dae  cmp     edi, eax
0x180047db0  jnz     short loc_180047E17
0x180047db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180047db9  lea     r14, WPP_GLOBAL_Control
0x180047dc0  cmp     rcx, r14
0x180047dc3  jz      short loc_180047DEF
0x180047dc5  test    byte ptr [rcx+1Ch], 8
0x180047dc9  jz      short loc_180047DEF
0x180047dcb  mov     rcx, [rcx+10h]
0x180047dcf  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047dd6  mov     edx, 7Ch ; '|'
0x180047ddb  mov     dword ptr [rsp+50h+var_30], r15d
0x180047de0  mov     r9, r12
0x180047de3  call    WPP_SF_Sd
0x180047de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180047def  mov     ebx, 80310000h
0x180047df4  cmp     rcx, r14
0x180047df7  jz      short loc_180047E17
0x180047df9  test    byte ptr [rcx+1Ch], 40h
0x180047dfd  jz      short loc_180047E17
0x180047dff  mov     rcx, [rcx+10h]
0x180047e03  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180047e0a  mov     edx, 7Dh ; '}'
0x180047e0f  mov     r9d, ebx
0x180047e12  call    WPP_SF_d
0x180047e17  mov     rcx, rsi; hMem
0x180047e1a  call    cs:__imp_LocalFree
0x180047e21  nop     dword ptr [rax+rax+00h]
0x180047e26  mov     rcx, [rbp+var_18]
0x180047e2a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180047e2e  jz      short loc_180047E3C
0x180047e30  call    cs:__imp_FveCloseVolume
0x180047e37  nop     dword ptr [rax+rax+00h]
0x180047e3c  mov     eax, ebx
0x180047e3e  mov     rcx, [rbp+var_8]
0x180047e42  xor     rcx, rsp; StackCookie
0x180047e45  call    __security_check_cookie
0x180047e4a  lea     r11, [rsp+50h+var_s0]
0x180047e4f  mov     rbx, [r11+38h]
0x180047e53  mov     rsi, [r11+40h]
0x180047e57  mov     rsp, r11
0x180047e5a  pop     r15
0x180047e5c  pop     r14
0x180047e5e  pop     r12
0x180047e60  pop     rdi
0x180047e61  pop     rbp
0x180047e62  retn
```
