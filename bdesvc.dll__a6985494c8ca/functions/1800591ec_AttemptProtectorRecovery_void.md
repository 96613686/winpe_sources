# AttemptProtectorRecovery(void)

- ea: `0x1800591ec`
- end: `0x1800594e5`
- name: `?AttemptProtectorRecovery@@YAJXZ`
- size: `761`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800429e0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x180034070`
- `0x180034d28`
- `0x18003a3d8`
- `0x1800591ec`
- `0x180059764`

## import_xrefs

- `FVEAPI!FveCommitChangesEx` at `0x18005938d`
- `FVEAPI!FveCommitChangesEx` at `0x18005946c`
- `FVEAPI!FveCommitChangesEx` at `0x18005938d`
- `FVEAPI!FveCommitChangesEx` at `0x18005946c`
- `FVEAPI!FveOpenVolumeW` at `0x1800592b2`
- `FVEAPI!FveOpenVolumeW` at `0x1800592b2`
- `FVEAPI!FveCloseVolume` at `0x1800593eb`
- `FVEAPI!FveCloseVolume` at `0x1800593eb`
- `FVEAPI!FveKeyManagement` at `0x180059301`
- `FVEAPI!FveKeyManagement` at `0x180059301`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 AttemptProtectorRecovery(void)
{
  unsigned int OSVolume; // eax
  int v1; // ebx
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  PVOID *v5; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // [rsp+20h] [rbp-E0h] BYREF
  int v10; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v11[528]; // [rsp+30h] [rbp-D0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids);
  v9 = -1;
  memset_0(v11, 0, 0x208u);
  v10 = 0;
  OSVolume = NgscbGetOSVolume(v11);
  v1 = OSVolume;
  if ( !OSVolume )
    goto LABEL_18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids, OSVolume);
  if ( v1 >= 0 )
  {
LABEL_18:
    v2 = FveOpenVolumeW(v11, 1, &v9);
    v1 = v2;
    if ( !v2 )
      goto LABEL_54;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids, v2);
    if ( v1 >= 0 )
    {
LABEL_54:
      v3 = FveKeyManagement(v9, 32, &v10);
      v1 = v3;
      if ( !v3 )
        goto LABEL_55;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids, v3);
      if ( v1 >= 0 )
      {
LABEL_55:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_KM_Public_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_KM_Public_Support>::GetImpl'::`2'::impl) )
        {
          if ( (v10 & 0x20) != 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids);
            v4 = FveCommitChangesEx(v9, 8);
            v1 = v4;
            if ( !v4 )
              goto LABEL_31;
            v5 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_29;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids, v4);
            goto LABEL_28;
          }
          v5 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v7 = 16;
LABEL_51:
            WPP_SF_(v5[2], v7, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids);
LABEL_28:
            v5 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_29;
          }
          goto LABEL_29;
        }
        v8 = FveCommitChangesEx(v9, 8);
        v1 = v8;
        if ( !v8 )
        {
          v5 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_48;
        }
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids, v8);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v1 >= 0 )
        {
LABEL_48:
          if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
          {
            v7 = 18;
            goto LABEL_51;
          }
LABEL_29:
          if ( v1 >= 0 )
            goto LABEL_32;
        }
      }
    }
  }
  BdeSvcLogFailedProtectorRecovery(v1);
LABEL_31:
  v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
  if ( v9 != -1 )
  {
    FveCloseVolume(v9);
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v9 = -1;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_(v5[2], 19, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800591ec  push    rbp
0x1800591ee  push    rbx
0x1800591ef  push    rsi
0x1800591f0  push    rdi
0x1800591f1  lea     rbp, [rsp-158h]
0x1800591f9  sub     rsp, 258h
0x180059200  mov     rax, cs:__security_cookie
0x180059207  xor     rax, rsp
0x18005920a  mov     [rbp+170h+var_30], rax
0x180059211  mov     rcx, cs:WPP_GLOBAL_Control
0x180059218  lea     rdi, WPP_GLOBAL_Control
0x18005921f  lea     rsi, WPP_d4142e1fd7613626e67ab3c93867b9b1_Traceguids
0x180059226  cmp     rcx, rdi
0x180059229  jz      short loc_180059242
0x18005922b  test    byte ptr [rcx+1Ch], 20h
0x18005922f  jz      short loc_180059242
0x180059231  mov     rcx, [rcx+10h]
0x180059235  mov     edx, 0Ah
0x18005923a  mov     r8, rsi
0x18005923d  call    WPP_SF_
0x180059242  xor     edx, edx; Val
0x180059244  mov     [rsp+270h+var_250], 0FFFFFFFFFFFFFFFFh
0x18005924d  mov     r8d, 208h; Size
0x180059253  lea     rcx, [rsp+270h+var_240]; void *
0x180059258  call    memset_0
0x18005925d  lea     rcx, [rsp+270h+var_240]
0x180059262  mov     [rsp+270h+var_248], 0
0x18005926a  call    NgscbGetOSVolume
0x18005926f  mov     ebx, eax
0x180059271  test    eax, eax
0x180059273  jz      short loc_1800592A3
0x180059275  mov     rcx, cs:WPP_GLOBAL_Control
0x18005927c  cmp     rcx, rdi
0x18005927f  jz      short loc_18005929B
0x180059281  test    byte ptr [rcx+1Ch], 40h
0x180059285  jz      short loc_18005929B
0x180059287  mov     rcx, [rcx+10h]
0x18005928b  mov     edx, 0Bh
0x180059290  mov     r9d, eax
0x180059293  mov     r8, rsi
0x180059296  call    WPP_SF_d
0x18005929b  test    ebx, ebx
0x18005929d  js      loc_1800593D0
0x1800592a3  lea     r8, [rsp+270h+var_250]
0x1800592a8  mov     edx, 1
0x1800592ad  lea     rcx, [rsp+270h+var_240]
0x1800592b2  call    cs:__imp_FveOpenVolumeW
0x1800592b9  nop     dword ptr [rax+rax+00h]
0x1800592be  mov     ebx, eax
0x1800592c0  test    eax, eax
0x1800592c2  jz      short loc_1800592F2
0x1800592c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592cb  cmp     rcx, rdi
0x1800592ce  jz      short loc_1800592EA
0x1800592d0  test    byte ptr [rcx+1Ch], 40h
0x1800592d4  jz      short loc_1800592EA
0x1800592d6  mov     rcx, [rcx+10h]
0x1800592da  mov     edx, 0Ch
0x1800592df  mov     r9d, eax
0x1800592e2  mov     r8, rsi
0x1800592e5  call    WPP_SF_d
0x1800592ea  test    ebx, ebx
0x1800592ec  js      loc_1800593D0
0x1800592f2  mov     rcx, [rsp+270h+var_250]
0x1800592f7  lea     r8, [rsp+270h+var_248]
0x1800592fc  mov     edx, 20h ; ' '
0x180059301  call    cs:__imp_FveKeyManagement
0x180059308  nop     dword ptr [rax+rax+00h]
0x18005930d  mov     ebx, eax
0x18005930f  test    eax, eax
0x180059311  jz      short loc_180059341
0x180059313  mov     rcx, cs:WPP_GLOBAL_Control
0x18005931a  cmp     rcx, rdi
0x18005931d  jz      short loc_180059339
0x18005931f  test    byte ptr [rcx+1Ch], 40h
0x180059323  jz      short loc_180059339
0x180059325  mov     rcx, [rcx+10h]
0x180059329  mov     edx, 0Dh
0x18005932e  mov     r9d, eax
0x180059331  mov     r8, rsi
0x180059334  call    WPP_SF_d
0x180059339  test    ebx, ebx
0x18005933b  js      loc_1800593D0
0x180059341  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_KM_Public_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_KM_Public_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_KM_Public_Support> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_KM_Public_Support>::GetImpl(void)'::`2'::impl
0x180059348  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_KM_Public_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_KM_Public_Support>::__private_IsEnabled(void)
0x18005934d  test    al, al
0x18005934f  jz      loc_180059462
0x180059355  test    byte ptr [rsp+270h+var_248], 20h
0x18005935a  jz      loc_180059441
0x180059360  mov     rcx, cs:WPP_GLOBAL_Control
0x180059367  cmp     rcx, rdi
0x18005936a  jz      short loc_180059383
0x18005936c  test    byte ptr [rcx+1Ch], 8
0x180059370  jz      short loc_180059383
0x180059372  mov     rcx, [rcx+10h]
0x180059376  mov     edx, 0Eh
0x18005937b  mov     r8, rsi
0x18005937e  call    WPP_SF_
0x180059383  mov     rcx, [rsp+270h+var_250]
0x180059388  mov     edx, 8
0x18005938d  call    cs:__imp_FveCommitChangesEx
0x180059394  nop     dword ptr [rax+rax+00h]
0x180059399  mov     ebx, eax
0x18005939b  test    eax, eax
0x18005939d  jz      short loc_1800593D7
0x18005939f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593a6  cmp     rcx, rdi
0x1800593a9  jz      short loc_1800593CC
0x1800593ab  test    byte ptr [rcx+1Ch], 40h
0x1800593af  jz      short loc_1800593CC
0x1800593b1  mov     rcx, [rcx+10h]
0x1800593b5  mov     edx, 0Fh
0x1800593ba  mov     r9d, eax
0x1800593bd  mov     r8, rsi
0x1800593c0  call    WPP_SF_d
0x1800593c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593cc  test    ebx, ebx
0x1800593ce  jns     short loc_1800593DE
0x1800593d0  mov     ecx, ebx; int
0x1800593d2  call    ?BdeSvcLogFailedProtectorRecovery@@YAXJ@Z; BdeSvcLogFailedProtectorRecovery(long)
0x1800593d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593de  cmp     [rsp+270h+var_250], 0FFFFFFFFFFFFFFFFh
0x1800593e4  jz      short loc_180059407
0x1800593e6  mov     rcx, [rsp+270h+var_250]
0x1800593eb  call    cs:__imp_FveCloseVolume
0x1800593f2  nop     dword ptr [rax+rax+00h]
0x1800593f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593fe  mov     [rsp+270h+var_250], 0FFFFFFFFFFFFFFFFh
0x180059407  cmp     rcx, rdi
0x18005940a  jz      short loc_180059423
0x18005940c  test    byte ptr [rcx+1Ch], 20h
0x180059410  jz      short loc_180059423
0x180059412  mov     rcx, [rcx+10h]
0x180059416  mov     edx, 13h
0x18005941b  mov     r8, rsi
0x18005941e  call    WPP_SF_
0x180059423  mov     eax, ebx
0x180059425  mov     rcx, [rbp+170h+var_30]
0x18005942c  xor     rcx, rsp; StackCookie
0x18005942f  call    __security_check_cookie
0x180059434  add     rsp, 258h
0x18005943b  pop     rdi
0x18005943c  pop     rsi
0x18005943d  pop     rbx
0x18005943e  pop     rbp
0x18005943f  retn
0x180059441  mov     rcx, cs:WPP_GLOBAL_Control
0x180059448  cmp     rcx, rdi
0x18005944b  jz      loc_1800593CC
0x180059451  test    byte ptr [rcx+1Ch], 8
0x180059455  jz      loc_1800593CC
0x18005945b  mov     edx, 10h
0x180059460  jmp     short loc_1800594D4
0x180059462  mov     rcx, [rsp+270h+var_250]
0x180059467  mov     edx, 8
0x18005946c  call    cs:__imp_FveCommitChangesEx
0x180059473  nop     dword ptr [rax+rax+00h]
0x180059478  mov     ebx, eax
0x18005947a  test    eax, eax
0x18005947c  jz      short loc_1800594B5
0x18005947e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059485  cmp     rcx, rdi
0x180059488  jz      short loc_1800594AB
0x18005948a  test    byte ptr [rcx+1Ch], 40h
0x18005948e  jz      short loc_1800594AB
0x180059490  mov     rcx, [rcx+10h]
0x180059494  mov     edx, 11h
0x180059499  mov     r9d, eax
0x18005949c  mov     r8, rsi
0x18005949f  call    WPP_SF_d
0x1800594a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800594ab  test    ebx, ebx
0x1800594ad  js      loc_1800593D0
0x1800594b3  jmp     short loc_1800594BC
0x1800594b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800594bc  cmp     rcx, rdi
0x1800594bf  jz      loc_1800593CC
0x1800594c5  test    byte ptr [rcx+1Ch], 8
0x1800594c9  jz      loc_1800593CC
0x1800594cf  mov     edx, 12h
0x1800594d4  mov     rcx, [rcx+10h]
0x1800594d8  mov     r8, rsi
0x1800594db  call    WPP_SF_
0x1800594e0  jmp     loc_1800593C5
```
