# CPort::OnLinkStateChange(ulong,uchar *)

- ea: `0x1400198b4`
- end: `0x140019c72`
- name: `?OnLinkStateChange@CPort@@QEAAXKPEAE@Z`
- size: `958`
- prototype: `void __fastcall(CPort *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update`

## callers

- `0x140026010`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140016d00`
- `0x140017590`
- `0x1400198b4`
- `0x140019c78`
- `0x14001ce70`
- `0x14001eed0`
- `0x14001f3e4`
- `0x1400291fc`
- `0x14002aaec`
- `0x14002be44`
- `0x14004144c`
- `0x140067394`
- `0x140068474`
- `0x140089b84`
- `0x14008c3a4`
- `0x14008c430`
- `0x1400dfd00`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CPort::OnLinkStateChange(CPort *this, int a2, unsigned __int8 *a3)
{
  int v4; // ebx
  char v6; // r12
  __int64 v7; // r8
  int v8; // edx
  int v9; // r8d
  int v10; // ebx
  int v11; // edx
  char v12; // r15
  unsigned int v13; // r14d
  unsigned int updated; // r13d
  const char *v15; // rdi
  const char *v16; // r8
  __int64 v17; // rax
  struct CConnectedPeer *v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // rcx
  CBSSEntry *v21; // rax
  int v22; // [rsp+20h] [rbp-89h]
  __int64 v23; // [rsp+28h] [rbp-81h]
  unsigned __int8 v24[4]; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v25; // [rsp+84h] [rbp-25h] BYREF
  unsigned int v26; // [rsp+88h] [rbp-21h] BYREF
  int v27; // [rsp+8Ch] [rbp-1Dh]
  unsigned int v28[4]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-9h]
  int v30; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v31; // [rsp+B0h] [rbp+7h]
  char v32; // [rsp+B8h] [rbp+Fh]

  v4 = a2;
  v6 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      84,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v7 = *((_QWORD *)this + 17);
  v30 = 0;
  v31 = 0;
  v29 = 0;
  v32 = 0;
  *(_OWORD *)v28 = 0;
  v27 = ParseWdiIndicationLinkStateChangeFromIhv((unsigned int)(v4 - 48), a3 + 48, v7 + 5384, v28);
  v10 = v27;
  if ( v27 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v9,
      85,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      (char)this,
      *((_WORD *)this + 74));
  }
  else
  {
    v26 = 0;
    if ( (unsigned int)CPropertyCache::GetPropertyULong((CPort *)((char *)this + 480), 2u, &v26)
      || (v12 = 0, v28[2] != v26) )
    {
      CPropertyCache::SetPropertyULong((CPort *)((char *)this + 480), 2u, v28[2]);
      v12 = 1;
    }
    v25 = 0;
    if ( (unsigned int)CPropertyCache::GetPropertyULong((CPort *)((char *)this + 480), 3u, &v25) || v28[3] != v25 )
    {
      CPropertyCache::SetPropertyULong((CPort *)((char *)this + 480), 3u, v28[3]);
      v12 = 1;
    }
    v13 = (unsigned __int8)v29;
    v24[0] = 0;
    if ( (unsigned int)CPropertyCache::GetPropertyUchar((CPort *)((char *)this + 480), 4u, v24) || (_BYTE)v13 != v24[0] )
    {
      CPropertyCache::SetPropertyUchar((CPort *)((char *)this + 480), 4u, v13);
      v6 = 1;
    }
    Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline();
    updated = CPort::UpdateConnectionInfo(this, (struct _WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS *)v28);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = " ";
      v16 = " ";
      if ( !v12 )
        v16 = "not ";
      if ( !v6 )
        v15 = "not ";
      WPP_RECORDER_SF_qDsddsiiii(
        WPP_GLOBAL_Control->DeviceExtension,
        v24[0],
        (_DWORD)v16,
        v28[3],
        v22,
        (char)this,
        *((_WORD *)this + 74),
        (__int64)v15,
        v24[0],
        v13,
        (__int64)v16,
        v26,
        v28[2],
        v25,
        v28[3]);
    }
    if ( v12 )
      CPort::UpdateLinkState(this);
    if ( LOBYTE(v28[0]) == 0xFF && *(unsigned int *)((char *)v28 + 1) == -1 && BYTE1(v28[1]) == 0xFF )
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 59) + 24LL))(*((_QWORD *)this + 59), 3);
    else
      v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 59) + 16LL))(
              *((_QWORD *)this + 59),
              v28);
    v18 = (struct CConnectedPeer *)v17;
    if ( v17 )
    {
      if ( !v30 )
      {
        v19 = 1736;
        v20 = 1736;
        if ( *((_DWORD *)this + 38) != 8 )
          v20 = 1336;
        v21 = (CBSSEntry *)(**(__int64 (__fastcall ***)(__int64, __int64))(*((_QWORD *)this + 17) + v20))(
                             *((_QWORD *)this + 17) + v20,
                             v17 + 1);
        if ( v21 )
        {
          if ( *((_DWORD *)this + 38) != 8 )
            v19 = 1336;
          CBSSEntry::OnLinkQualityUpdate(v21, v13, (struct CBSSListManager *)(*((_QWORD *)this + 17) + v19));
        }
      }
      if ( v6 || updated )
      {
        *((_BYTE *)v18 + 12) = v13;
        CPort::UpdateLinkQuality(this, v18);
        CPort::CheckAndNotifyLinkDegradedStatus(this, v13);
        CPort::RoamIfSwitchToBetterAPNeeded(this, v18);
      }
    }
    v10 = v27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v23) = v10;
    LOBYTE(v11) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      1,
      87,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v23);
  }
LABEL_46:
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v30);
}

```

## disassembly

```asm
0x1400198b4  mov     [rsp-8+arg_18], rbx
0x1400198b9  push    rbp
0x1400198ba  push    rsi
0x1400198bb  push    rdi
0x1400198bc  push    r12
0x1400198be  push    r13
0x1400198c0  push    r14
0x1400198c2  push    r15
0x1400198c4  lea     rbp, [rsp-27h]
0x1400198c9  sub     rsp, 0D0h
0x1400198d0  mov     rax, cs:__security_cookie
0x1400198d7  xor     rax, rsp
0x1400198da  mov     [rbp+57h+var_40], rax
0x1400198de  mov     rdi, r8
0x1400198e1  mov     ebx, edx
0x1400198e3  mov     rsi, rcx
0x1400198e6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400198ed  xor     r12d, r12d
0x1400198f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400198f7  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400198fe  jz      short loc_14001992E
0x140019900  mov     rcx, cs:WPP_GLOBAL_Control
0x140019907  cmp     byte ptr [rcx+29h], 5
0x14001990b  jnb     short loc_140019914
0x14001990d  cmp     [rcx+48h], r12w
0x140019912  jz      short loc_14001992E
0x140019914  mov     rcx, [rcx+40h]
0x140019918  mov     r9d, 54h ; 'T'
0x14001991e  mov     dl, 5
0x140019920  mov     [rsp+100h+var_E0], r14
0x140019925  lea     r8d, [r9-53h]
0x140019929  call    WPP_RECORDER_SF_
0x14001992e  mov     r8, [rsi+88h]
0x140019935  lea     rdx, [rdi+30h]
0x140019939  xorps   xmm0, xmm0
0x14001993c  mov     [rbp+57h+var_58], r12d
0x140019940  xor     eax, eax
0x140019942  mov     [rbp+57h+var_50], r12
0x140019946  add     r8, 1508h
0x14001994d  mov     [rbp+57h+var_60], rax
0x140019951  lea     ecx, [rbx-30h]
0x140019954  mov     [rbp+57h+var_48], r12b
0x140019958  lea     r9, [rbp+57h+var_70]
0x14001995c  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x140019960  call    ParseWdiIndicationLinkStateChangeFromIhv
0x140019965  mov     [rbp+57h+var_74], eax
0x140019968  mov     ebx, eax
0x14001996a  test    eax, eax
0x14001996c  jz      short loc_1400199B4
0x14001996e  lea     rax, WPP_RECORDER_INITIALIZED
0x140019975  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001997c  jz      loc_140019C41
0x140019982  movzx   ecx, word ptr [rsi+94h]
0x140019989  mov     r9d, 55h ; 'U'
0x14001998f  mov     [rsp+100h+var_D0], ecx
0x140019993  mov     dl, 2
0x140019995  mov     rcx, cs:WPP_GLOBAL_Control
0x14001999c  mov     [rsp+100h+var_D8], rsi
0x1400199a1  mov     [rsp+100h+var_E0], r14
0x1400199a6  mov     rcx, [rcx+40h]
0x1400199aa  call    WPP_RECORDER_SF_qD
0x1400199af  jmp     loc_140019BFF
0x1400199b4  lea     rbx, [rsi+1E0h]
0x1400199bb  mov     [rbp+57h+var_78], r12d
0x1400199bf  mov     rcx, rbx; this
0x1400199c2  lea     r8, [rbp+57h+var_78]; unsigned int *
0x1400199c6  mov     edx, 2; unsigned int
0x1400199cb  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x1400199d0  mov     r8d, [rbp+57h+var_70+8]; unsigned int
0x1400199d4  test    eax, eax
0x1400199d6  jnz     short loc_1400199E1
0x1400199d8  mov     r15b, r12b
0x1400199db  cmp     r8d, [rbp+57h+var_78]
0x1400199df  jz      short loc_1400199F1
0x1400199e1  mov     edx, 2; unsigned int
0x1400199e6  mov     rcx, rbx; this
0x1400199e9  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x1400199ee  mov     r15b, 1
0x1400199f1  mov     edi, 3
0x1400199f6  mov     [rbp+57h+var_7C], r12d
0x1400199fa  mov     edx, edi; unsigned int
0x1400199fc  lea     r8, [rbp+57h+var_7C]; unsigned int *
0x140019a00  mov     rcx, rbx; this
0x140019a03  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x140019a08  mov     r8d, [rbp+57h+var_70+0Ch]; unsigned int
0x140019a0c  test    eax, eax
0x140019a0e  jnz     short loc_140019A16
0x140019a10  cmp     r8d, [rbp+57h+var_7C]
0x140019a14  jz      short loc_140019A23
0x140019a16  mov     edx, edi; unsigned int
0x140019a18  mov     rcx, rbx; this
0x140019a1b  call    ?SetPropertyULong@CPropertyCache@@QEAAHKK@Z; CPropertyCache::SetPropertyULong(ulong,ulong)
0x140019a20  mov     r15b, 1
0x140019a23  movzx   r14d, byte ptr [rbp+57h+var_60]
0x140019a28  lea     r8, [rbp+57h+var_80]; unsigned __int8 *
0x140019a2c  mov     edi, 4
0x140019a31  mov     [rbp+57h+var_80], r12b
0x140019a35  mov     edx, edi; unsigned int
0x140019a37  mov     rcx, rbx; this
0x140019a3a  call    ?GetPropertyUchar@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyUchar(ulong,uchar *)
0x140019a3f  test    eax, eax
0x140019a41  jnz     short loc_140019A49
0x140019a43  cmp     r14b, [rbp+57h+var_80]
0x140019a47  jz      short loc_140019A59
0x140019a49  mov     r8b, r14b; unsigned __int8
0x140019a4c  mov     edx, edi; unsigned int
0x140019a4e  mov     rcx, rbx; this
0x140019a51  call    ?SetPropertyUchar@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyUchar(ulong,uchar)
0x140019a56  mov     r12b, 1
0x140019a59  call    Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline
0x140019a5e  lea     rdx, [rbp+57h+var_70]; struct _WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS *
0x140019a62  mov     rcx, rsi; this
0x140019a65  call    ?UpdateConnectionInfo@CPort@@QEAAKAEAU_WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS@@@Z; CPort::UpdateConnectionInfo(_WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS &)
0x140019a6a  mov     r13d, eax
0x140019a6d  lea     rax, WPP_RECORDER_INITIALIZED
0x140019a74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019a7b  jz      short loc_140019AF6
0x140019a7d  mov     r9d, [rbp+57h+var_70+0Ch]
0x140019a81  lea     rax, aNot; "not "
0x140019a88  mov     r10d, [rbp+57h+var_7C]
0x140019a8c  lea     rdi, asc_1400FEC80; " "
0x140019a93  mov     r11d, [rbp+57h+var_70+8]
0x140019a97  test    r15b, r15b
0x140019a9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019aa1  mov     r8, rdi
0x140019aa4  movzx   edx, [rbp+57h+var_80]
0x140019aa8  cmovz   r8, rax
0x140019aac  mov     ebx, [rbp+57h+var_78]
0x140019aaf  test    r12b, r12b
0x140019ab2  mov     [rsp+100h+var_90], r9
0x140019ab7  mov     rcx, [rcx+40h]
0x140019abb  cmovz   rdi, rax
0x140019abf  movzx   eax, word ptr [rsi+94h]
0x140019ac6  mov     [rsp+100h+var_98], r10
0x140019acb  mov     [rsp+100h+var_A0], r11
0x140019ad0  mov     [rsp+100h+var_A8], rbx
0x140019ad5  mov     [rsp+100h+var_B0], r8
0x140019ada  mov     [rsp+100h+var_B8], r14d
0x140019adf  mov     [rsp+100h+var_C0], edx
0x140019ae3  mov     [rsp+100h+var_C8], rdi
0x140019ae8  mov     [rsp+100h+var_D0], eax
0x140019aec  mov     [rsp+100h+var_D8], rsi
0x140019af1  call    WPP_RECORDER_SF_qDsddsiiii
0x140019af6  test    r15b, r15b
0x140019af9  jz      short loc_140019B03
0x140019afb  mov     rcx, rsi; this
0x140019afe  call    ?UpdateLinkState@CPort@@QEAAXXZ; CPort::UpdateLinkState(void)
0x140019b03  mov     al, 0FFh
0x140019b05  cmp     byte ptr [rbp+57h+var_70], al
0x140019b08  jnz     short loc_140019B3D
0x140019b0a  cmp     byte ptr [rbp+57h+var_70+1], al
0x140019b0d  jnz     short loc_140019B3D
0x140019b0f  cmp     byte ptr [rbp+57h+var_70+2], al
0x140019b12  jnz     short loc_140019B3D
0x140019b14  cmp     byte ptr [rbp+57h+var_70+3], al
0x140019b17  jnz     short loc_140019B3D
0x140019b19  cmp     byte ptr [rbp+57h+var_70+4], al
0x140019b1c  jnz     short loc_140019B3D
0x140019b1e  cmp     byte ptr [rbp+57h+var_70+5], al
0x140019b21  jnz     short loc_140019B3D
0x140019b23  mov     rcx, [rsi+1D8h]
0x140019b2a  mov     edx, 3
0x140019b2f  mov     rax, [rcx]
0x140019b32  mov     rax, [rax+18h]
0x140019b36  call    _guard_dispatch_icall
0x140019b3b  jmp     short loc_140019B54
0x140019b3d  mov     rcx, [rsi+1D8h]
0x140019b44  lea     rdx, [rbp+57h+var_70]
0x140019b48  mov     rax, [rcx]
0x140019b4b  mov     rax, [rax+10h]
0x140019b4f  call    _guard_dispatch_icall
0x140019b54  mov     rbx, rax
0x140019b57  test    rax, rax
0x140019b5a  jz      loc_140019BF2
0x140019b60  cmp     [rbp+57h+var_58], 0
0x140019b64  jnz     short loc_140019BB9
0x140019b66  cmp     dword ptr [rsi+98h], 8
0x140019b6d  lea     rdx, [rbx+1]
0x140019b71  mov     edi, 6C8h
0x140019b76  mov     r15d, 538h
0x140019b7c  mov     ecx, edi
0x140019b7e  cmovnz  ecx, r15d
0x140019b82  add     rcx, [rsi+88h]
0x140019b89  mov     rax, [rcx]
0x140019b8c  mov     rax, [rax]
0x140019b8f  call    _guard_dispatch_icall
0x140019b94  test    rax, rax
0x140019b97  jz      short loc_140019BB9
0x140019b99  cmp     dword ptr [rsi+98h], 8
0x140019ba0  mov     dl, r14b; unsigned __int8
0x140019ba3  mov     rcx, rax; this
0x140019ba6  cmovnz  edi, r15d
0x140019baa  add     rdi, [rsi+88h]
0x140019bb1  mov     r8, rdi; struct CBSSListManager *
0x140019bb4  call    ?OnLinkQualityUpdate@CBSSEntry@@QEAAXEPEAVCBSSListManager@@@Z; CBSSEntry::OnLinkQualityUpdate(uchar,CBSSListManager *)
0x140019bb9  test    r12b, r12b
0x140019bbc  jnz     short loc_140019BC8
0x140019bbe  xor     r12d, r12d
0x140019bc1  test    r13d, r13d
0x140019bc4  jnz     short loc_140019BCB
0x140019bc6  jmp     short loc_140019BF5
0x140019bc8  xor     r12d, r12d
0x140019bcb  mov     rdx, rbx; struct CConnectedPeer *
0x140019bce  mov     [rbx+0Ch], r14b
0x140019bd2  mov     rcx, rsi; this
0x140019bd5  call    ?UpdateLinkQuality@CPort@@QEAAXPEAVCConnectedPeer@@@Z; CPort::UpdateLinkQuality(CConnectedPeer *)
0x140019bda  mov     edx, r14d; unsigned int
0x140019bdd  mov     rcx, rsi; this
0x140019be0  call    ?CheckAndNotifyLinkDegradedStatus@CPort@@QEAAXK@Z; CPort::CheckAndNotifyLinkDegradedStatus(ulong)
0x140019be5  mov     rdx, rbx; struct CConnectedPeer *
0x140019be8  mov     rcx, rsi; this
0x140019beb  call    ?RoamIfSwitchToBetterAPNeeded@CPort@@QEAA_NPEAVCConnectedPeer@@@Z; CPort::RoamIfSwitchToBetterAPNeeded(CConnectedPeer *)
0x140019bf0  jmp     short loc_140019BF5
0x140019bf2  xor     r12d, r12d
0x140019bf5  mov     ebx, [rbp+57h+var_74]
0x140019bf8  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140019bff  lea     rax, WPP_RECORDER_INITIALIZED
0x140019c06  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019c0d  jz      short loc_140019C41
0x140019c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c16  cmp     byte ptr [rcx+29h], 5
0x140019c1a  jnb     short loc_140019C23
0x140019c1c  cmp     [rcx+48h], r12w
0x140019c21  jz      short loc_140019C41
0x140019c23  mov     rcx, [rcx+40h]
0x140019c27  mov     r9d, 57h ; 'W'
0x140019c2d  mov     dword ptr [rsp+100h+var_D8], ebx
0x140019c31  mov     dl, 5
0x140019c33  mov     [rsp+100h+var_E0], r14
0x140019c38  lea     r8d, [r9-56h]
0x140019c3c  call    WPP_RECORDER_SF_d
0x140019c41  lea     rcx, [rbp+57h+var_58]
0x140019c45  call    ?Cleanup@?$ArrayOfElements@U_WDI_PHY_STATISTICS_PARAMETERS@@@@QEAAXXZ; ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(void)
0x140019c4a  mov     rcx, [rbp+57h+var_40]
0x140019c4e  xor     rcx, rsp; StackCookie
0x140019c51  call    __security_check_cookie
0x140019c56  mov     rbx, [rsp+100h+arg_18]
0x140019c5e  add     rsp, 0D0h
0x140019c65  pop     r15
0x140019c67  pop     r14
0x140019c69  pop     r13
0x140019c6b  pop     r12
0x140019c6d  pop     rdi
0x140019c6e  pop     rsi
0x140019c6f  pop     rbp
0x140019c70  retn
```
