# UbpmTriggerConsumerControl

- ea: `0x180028b20`
- end: `0x180028ece`
- name: `UbpmTriggerConsumerControl`
- size: `942`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000dda4`
- `0x1800101a0`
- `0x180028b20`
- `0x180032e70`
- `0x18003504c`
- `0x1800350dc`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028e2a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028e2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180028c30`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180028c30`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180028c4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180028c4a`

## pseudocode

```c
__int64 __fastcall UbpmTriggerConsumerControl(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *a2,
        _QWORD *a3)
{
  _QWORD *v6; // r8
  unsigned int v7; // esi
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // eax
  DWORD v11; // ebx
  int v13; // edx
  int v14; // r9d
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // [rsp+20h] [rbp-F8h]
  _BYTE v18[144]; // [rsp+60h] [rbp-B8h] BYREF

  memset_0(v18, 0, 0x88u);
  UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v18);
  v7 = 87;
  if ( !a2 )
    goto LABEL_15;
  if ( a3 )
    *a3 = 0;
  v8 = *((_DWORD *)a2 + 1);
  if ( v8 && (v8 & 0x1F) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
        v8,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    goto LABEL_15;
  }
  if ( *(_DWORD *)a2 != 1 )
  {
    if ( *(_DWORD *)a2 != 2 )
      goto LABEL_15;
    if ( v8 || *((_DWORD *)a2 + 2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_LdS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
          (_DWORD)WPP_GLOBAL_Control,
          v8,
          *((_DWORD *)a2 + 2),
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
      goto LABEL_15;
    }
    v10 = UbpmpStopAllConsumerActions(a1, *((_QWORD *)a2 + 4), *((_QWORD *)a2 + 3));
LABEL_14:
    v7 = v10;
    goto LABEL_15;
  }
  if ( (v8 & 2) != 0 )
  {
    if ( *((_DWORD *)a2 + 2) == -1 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 11;
      goto LABEL_23;
    }
    if ( (v8 & 8) != 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 12;
      goto LABEL_23;
    }
  }
  else if ( *((_DWORD *)a2 + 2) != -1 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 13;
    goto LABEL_23;
  }
  v9 = *((_QWORD *)a2 + 3);
  if ( (v8 & 4) == 0 )
  {
    if ( !v9 )
    {
      if ( (v8 & 8) == 0 )
        goto LABEL_12;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 16;
LABEL_41:
      v14 = *((_DWORD *)a2 + 1);
LABEL_42:
      v15 = v16[2];
      goto LABEL_43;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 15;
LABEL_23:
    v14 = *((_DWORD *)a2 + 1);
    v15 = v6[2];
LABEL_43:
    WPP_SF_LS(v15, v13, (_DWORD)v6, v14, *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    goto LABEL_15;
  }
  if ( !v9 || !IsValidSid(*((PSID *)a2 + 3)) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 14;
    goto LABEL_41;
  }
LABEL_12:
  LODWORD(v6) = *((_DWORD *)a2 + 1);
  if ( ((unsigned __int8)v6 & 0x10) == 0 || ((unsigned __int8)v6 & 6) != 0 )
  {
    *((_DWORD *)a2 + 1) = (unsigned int)v6 | 0x10000;
    v10 = UbpmRunConsumerActions(a1, 0, 0, 0, v17, 0, 0xFFFFu, 0, 0, a2, a3);
    goto LABEL_14;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 17;
    v14 = *((_DWORD *)a2 + 1);
    goto LABEL_42;
  }
LABEL_15:
  v11 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v11, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x180028b20  mov     [rsp+arg_18], rbx
0x180028b25  push    rsi
0x180028b26  push    rdi
0x180028b27  push    r14
0x180028b29  sub     rsp, 100h
0x180028b30  mov     rax, cs:__security_cookie
0x180028b37  xor     rax, rsp
0x180028b3a  mov     [rsp+118h+var_28], rax
0x180028b42  mov     r14, r8
0x180028b45  mov     rbx, rdx
0x180028b48  mov     rdi, rcx
0x180028b4b  xor     edx, edx; Val
0x180028b4d  mov     r8d, 88h; Size
0x180028b53  lea     rcx, [rsp+118h+var_B8]; void *
0x180028b58  call    memset_0
0x180028b5d  lea     rcx, [rsp+118h+var_B8]; lpTlsValue
0x180028b62  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x180028b67  mov     esi, 57h ; 'W'
0x180028b6c  test    rbx, rbx
0x180028b6f  jz      loc_180028C23
0x180028b75  test    r14, r14
0x180028b78  jz      short loc_180028B81
0x180028b7a  mov     qword ptr [r14], 0
0x180028b81  mov     ecx, [rbx+4]
0x180028b84  test    ecx, ecx
0x180028b86  jz      short loc_180028B91
0x180028b88  test    cl, 1Fh
0x180028b8b  jz      loc_180028D36
0x180028b91  mov     edx, [rbx]
0x180028b93  sub     edx, 1
0x180028b96  jnz     loc_180028CA8
0x180028b9c  test    cl, 2
0x180028b9f  jnz     loc_180028CD7
0x180028ba5  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180028ba9  jnz     loc_180028D0A
0x180028baf  mov     rax, [rbx+18h]
0x180028bb3  test    cl, 4
0x180028bb6  jnz     loc_180028E22
0x180028bbc  test    rax, rax
0x180028bbf  jnz     loc_180028C7D
0x180028bc5  test    cl, 8
0x180028bc8  jnz     loc_180028E64
0x180028bce  mov     r8d, [rbx+4]
0x180028bd2  test    r8b, 10h
0x180028bd6  jnz     loc_180028E8F
0x180028bdc  mov     [rsp+118h+var_C8], r14; __int64
0x180028be1  bts     r8d, 10h
0x180028be6  mov     [rsp+118h+var_D0], rbx; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x180028beb  xor     r9d, r9d
0x180028bee  mov     [rsp+118h+var_D8], 0; __int64
0x180028bf7  xor     edx, edx
0x180028bf9  mov     [rsp+118h+var_E0], 0; unsigned int
0x180028c01  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180028c04  mov     [rbx+4], r8d
0x180028c08  xor     r8d, r8d
0x180028c0b  mov     [rsp+118h+var_E8], 0FFFFh; unsigned int
0x180028c13  mov     [rsp+118h+var_F0], 0; unsigned __int64
0x180028c1c  call    UbpmRunConsumerActions
0x180028c21  mov     esi, eax
0x180028c23  mov     ebx, cs:UbpmpLockTrackerId
0x180028c29  cmp     ebx, 0FFFFFFFFh
0x180028c2c  jz      short loc_180028C56
0x180028c2e  mov     ecx, ebx; dwTlsIndex
0x180028c30  call    cs:__imp_TlsGetValue
0x180028c37  nop     dword ptr [rax+rax+00h]
0x180028c3c  cmp     qword ptr [rax], 0
0x180028c40  jnz     loc_180028EC7
0x180028c46  xor     edx, edx; lpTlsValue
0x180028c48  mov     ecx, ebx; dwTlsIndex
0x180028c4a  call    cs:__imp_TlsSetValue
0x180028c51  nop     dword ptr [rax+rax+00h]
0x180028c56  mov     eax, esi
0x180028c58  mov     rcx, [rsp+118h+var_28]
0x180028c60  xor     rcx, rsp; StackCookie
0x180028c63  call    __security_check_cookie
0x180028c68  mov     rbx, [rsp+118h+arg_18]
0x180028c70  add     rsp, 100h
0x180028c77  pop     r14
0x180028c79  pop     rdi
0x180028c7a  pop     rsi
0x180028c7b  retn
0x180028c7d  mov     r8, cs:WPP_GLOBAL_Control
0x180028c84  lea     rax, WPP_GLOBAL_Control
0x180028c8b  cmp     r8, rax
0x180028c8e  jz      short loc_180028C23
0x180028c90  test    byte ptr [r8+1Ch], 1
0x180028c95  jz      short loc_180028C23
0x180028c97  mov     edx, 0Fh
0x180028c9c  mov     r9d, ecx
0x180028c9f  mov     rcx, [r8+10h]
0x180028ca3  jmp     loc_180028DD6
0x180028ca8  cmp     edx, 1
0x180028cab  jnz     loc_180028C23
0x180028cb1  test    ecx, ecx
0x180028cb3  jnz     loc_180028D82
0x180028cb9  cmp     [rbx+8], ecx
0x180028cbc  jnz     loc_180028D82
0x180028cc2  mov     r8, [rbx+18h]
0x180028cc6  mov     rcx, rdi
0x180028cc9  mov     rdx, [rbx+20h]
0x180028ccd  call    UbpmpStopAllConsumerActions
0x180028cd2  jmp     loc_180028C21
0x180028cd7  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180028cdb  jnz     loc_180028DED
0x180028ce1  mov     r8, cs:WPP_GLOBAL_Control
0x180028ce8  lea     rax, WPP_GLOBAL_Control
0x180028cef  cmp     r8, rax
0x180028cf2  jz      loc_180028C23
0x180028cf8  test    byte ptr [r8+1Ch], 1
0x180028cfd  jz      loc_180028C23
0x180028d03  mov     edx, 0Bh
0x180028d08  jmp     short loc_180028C9C
0x180028d0a  mov     r8, cs:WPP_GLOBAL_Control
0x180028d11  lea     rax, WPP_GLOBAL_Control
0x180028d18  cmp     r8, rax
0x180028d1b  jz      loc_180028C23
0x180028d21  test    byte ptr [r8+1Ch], 1
0x180028d26  jz      loc_180028C23
0x180028d2c  mov     edx, 0Dh
0x180028d31  jmp     loc_180028C9C
0x180028d36  mov     r10, cs:WPP_GLOBAL_Control
0x180028d3d  lea     rax, WPP_GLOBAL_Control
0x180028d44  cmp     r10, rax
0x180028d47  jz      loc_180028C23
0x180028d4d  test    byte ptr [r10+1Ch], 1
0x180028d52  jz      loc_180028C23
0x180028d58  mov     rax, [rdi+18h]
0x180028d5c  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180028d63  mov     r9d, ecx
0x180028d66  mov     edx, 0Ah
0x180028d6b  mov     rcx, [r10+10h]
0x180028d6f  mov     rax, [rax+8]
0x180028d73  mov     [rsp+118h+var_F8], rax
0x180028d78  call    WPP_SF_LSd
0x180028d7d  jmp     loc_180028C23
0x180028d82  mov     r8, cs:WPP_GLOBAL_Control
0x180028d89  lea     rax, WPP_GLOBAL_Control
0x180028d90  cmp     r8, rax
0x180028d93  jz      loc_180028C23
0x180028d99  test    byte ptr [r8+1Ch], 1
0x180028d9e  jz      loc_180028C23
0x180028da4  mov     rax, [rdi+18h]
0x180028da8  mov     r9d, ecx
0x180028dab  mov     rcx, [r8+10h]
0x180028daf  mov     rdx, [rax+8]
0x180028db3  mov     eax, [rbx+8]
0x180028db6  mov     [rsp+118h+var_F0], rdx
0x180028dbb  mov     dword ptr [rsp+118h+var_F8], eax
0x180028dbf  call    WPP_SF_LdS
0x180028dc4  jmp     loc_180028C23
0x180028dc9  mov     edx, 0Eh
0x180028dce  mov     r9d, [rbx+4]
0x180028dd2  mov     rcx, [rcx+10h]
0x180028dd6  mov     rax, [rdi+18h]
0x180028dda  mov     rax, [rax+8]
0x180028dde  mov     [rsp+118h+var_F8], rax
0x180028de3  call    WPP_SF_LS
0x180028de8  jmp     loc_180028C23
0x180028ded  test    cl, 8
0x180028df0  jz      loc_180028BAF
0x180028df6  mov     r8, cs:WPP_GLOBAL_Control
0x180028dfd  lea     rax, WPP_GLOBAL_Control
0x180028e04  cmp     r8, rax
0x180028e07  jz      loc_180028C23
0x180028e0d  test    byte ptr [r8+1Ch], 1
0x180028e12  jz      loc_180028C23
0x180028e18  mov     edx, 0Ch
0x180028e1d  jmp     loc_180028C9C
0x180028e22  test    rax, rax
0x180028e25  jz      short loc_180028E3E
0x180028e27  mov     rcx, rax; pSid
0x180028e2a  call    cs:__imp_IsValidSid
0x180028e31  nop     dword ptr [rax+rax+00h]
0x180028e36  test    eax, eax
0x180028e38  jnz     loc_180028BCE
0x180028e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e45  lea     rax, WPP_GLOBAL_Control
0x180028e4c  cmp     rcx, rax
0x180028e4f  jz      loc_180028C23
0x180028e55  test    byte ptr [rcx+1Ch], 1
0x180028e59  jz      loc_180028C23
0x180028e5f  jmp     loc_180028DC9
0x180028e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e6b  lea     rax, WPP_GLOBAL_Control
0x180028e72  cmp     rcx, rax
0x180028e75  jz      loc_180028C23
0x180028e7b  test    byte ptr [rcx+1Ch], 1
0x180028e7f  jz      loc_180028C23
0x180028e85  mov     edx, 10h
0x180028e8a  jmp     loc_180028DCE
0x180028e8f  test    r8b, 6
0x180028e93  jnz     loc_180028BDC
0x180028e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ea0  lea     rax, WPP_GLOBAL_Control
0x180028ea7  cmp     rcx, rax
0x180028eaa  jz      loc_180028C23
0x180028eb0  test    byte ptr [rcx+1Ch], 1
0x180028eb4  jz      loc_180028C23
0x180028eba  mov     edx, 11h
0x180028ebf  mov     r9d, r8d
0x180028ec2  jmp     loc_180028DD2
0x180028ec7  int     2Ch; Windows NT - assertion failure
0x180028ec9  jmp     loc_180028C46
```
