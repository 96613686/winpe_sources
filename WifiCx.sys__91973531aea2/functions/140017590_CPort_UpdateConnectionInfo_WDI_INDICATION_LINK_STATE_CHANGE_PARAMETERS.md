# CPort::UpdateConnectionInfo(_WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS &)

- ea: `0x140017590`
- end: `0x140017a90`
- name: `?UpdateConnectionInfo@CPort@@QEAAKAEAU_WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS@@@Z`
- size: `1280`
- prototype: `unsigned int __fastcall(CPort *__hidden this, struct _WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x1400198b4`

## callees

- `0x14000d054`
- `0x14000e3f0`
- `0x140017590`
- `0x140017a90`
- `0x14001c4ec`
- `0x14001c540`
- `0x140029180`
- `0x1400291fc`
- `0x14002a9f8`
- `0x14002ed50`
- `0x140050574`
- `0x14008abd0`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CPort::UpdateConnectionInfo(CPort *this, struct _WDI_INDICATION_LINK_STATE_CHANGE_PARAMETERS *a2)
{
  struct DOT11_CONNECTION_INFO *v4; // rsi
  int v5; // ecx
  int v6; // edx
  __int64 v8; // rdx
  unsigned int v9; // r12d
  __int64 v10; // r9
  __int64 v11; // rbp
  __int64 v12; // r8
  char *v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rcx
  char v16; // r15
  __int64 v17; // rax
  __int64 v18; // rsi
  __int64 v19; // rcx
  int v20; // r12d
  int v21; // r15d
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  CBSSListManager *v26; // r15
  bool v27; // zf
  int v28; // ecx
  int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // edx
  __int64 v33; // rdi
  int v34; // edx
  int v35; // edx
  int v36; // r9d
  char v37; // [rsp+38h] [rbp-60h]
  char v38; // [rsp+38h] [rbp-60h]
  int v39; // [rsp+40h] [rbp-58h]
  unsigned int v40; // [rsp+44h] [rbp-54h]
  struct DOT11_CONNECTION_INFO *CurrentConnectionInfo; // [rsp+48h] [rbp-50h]
  __int64 v42; // [rsp+50h] [rbp-48h]
  char v43; // [rsp+B0h] [rbp+18h]
  int v44; // [rsp+B8h] [rbp+20h]

  CurrentConnectionInfo = CPort::GetCurrentConnectionInfo(this, 1);
  v4 = CurrentConnectionInfo;
  if ( !CurrentConnectionInfo )
    return 0;
  v5 = *((unsigned __int8 *)a2 + 16);
  if ( (unsigned __int8)(v5 - 1) <= 0x63u )
    *((_DWORD *)CurrentConnectionInfo + 22) = v5;
  if ( (unsigned int)Feature_Bugfix_58594056__private_IsEnabledDeviceUsageNoInline() && !*((_DWORD *)a2 + 6) )
  {
    if ( CPort::SetCurrentConnectionInfo(this, CurrentConnectionInfo) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          1,
          79,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
      }
    }
    return 0;
  }
  v8 = 0;
  v9 = 0;
  v39 = 0;
  v44 = 0;
  if ( !*((_DWORD *)CurrentConnectionInfo + 26) )
    goto LABEL_55;
  v10 = 1336;
  do
  {
    v11 = 0;
    v12 = (unsigned int)v8;
    v43 = 0;
    v42 = (unsigned int)v8;
    if ( !*((_DWORD *)a2 + 6) )
      goto LABEL_48;
    v13 = (char *)v4 + 48 * v8;
    do
    {
      v14 = 40 * v11;
      if ( (unsigned __int8)v13[116] != *(_DWORD *)(40 * v11 + *((_QWORD *)a2 + 4)) )
      {
        v16 = v43;
        goto LABEL_40;
      }
      v15 = 1736;
      v16 = 1;
      if ( *((_DWORD *)this + 38) != 8 )
        v15 = v10;
      v43 = 1;
      v17 = (**(__int64 (__fastcall ***)(__int64, __int64, __int64, __int64))(*((_QWORD *)this + 17) + v15))(
              *((_QWORD *)this + 17) + v15,
              (__int64)(v13 + 123),
              v12,
              v10);
      v18 = v17;
      if ( v17 )
      {
        v19 = *((_QWORD *)a2 + 4);
        v20 = *(_DWORD *)(v17 + 792);
        v21 = *(_DWORD *)(v14 + v19 + 20);
        if ( v21 )
        {
          v40 = *(_DWORD *)(v14 + v19 + 16);
          if ( v40 )
          {
            v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL) + 8LL))(*((_QWORD *)this + 17) + 8LL);
            CBSSEntry::SetChannelAndPhyID(v18, (*((_DWORD *)this + 38) & 0x11) != 0, v22, v40, v21);
          }
        }
        v23 = 1736;
        v24 = *((unsigned __int8 *)a2 + 16);
        v10 = 1336;
        v25 = *((_QWORD *)this + 17);
        if ( *((_DWORD *)this + 38) != 8 )
          v23 = 1336;
        *(_DWORD *)(v18 + 596) = v24;
        if ( (unsigned __int8)v24 > 0x1Eu )
        {
          v26 = (CBSSListManager *)(v23 + v25);
          if ( *(_WORD *)(v18 + 640) )
          {
            *(_QWORD *)(v18 + 672) = CSystem::get_CurrentTime();
            goto LABEL_28;
          }
          if ( *(_WORD *)(v18 + 600) )
          {
            *(_QWORD *)(v18 + 632) = CSystem::get_CurrentTime();
LABEL_28:
            CBSSListManager::MoveBSSEntryToHeadOfList(v26, (struct CBSSEntry *)v18);
            v10 = 1336;
          }
        }
        v12 = v42;
        v16 = 1;
        *((_DWORD *)CurrentConnectionInfo + 12 * v42 + 36) = *(_DWORD *)(v18 + 792);
        v27 = *(_DWORD *)(v18 + 792) == v20;
        v9 = v39;
        if ( !v27 )
          v9 = ++v39;
        goto LABEL_32;
      }
      v12 = v42;
      v10 = 1336;
LABEL_32:
      v28 = *(_DWORD *)(v14 + *((_QWORD *)a2 + 4) + 24);
      if ( v28 >= 0 )
        v28 = *((_DWORD *)v13 + 37);
      *((_DWORD *)v13 + 37) = v28;
      v29 = *(_DWORD *)(v14 + *((_QWORD *)a2 + 4) + 28);
      if ( !v29 )
        v29 = *((_DWORD *)v13 + 38);
      *((_DWORD *)v13 + 38) = v29;
      v30 = *((_QWORD *)a2 + 4);
      v31 = *(unsigned int *)(v14 + v30 + 20);
      if ( (_DWORD)v31 && *(_DWORD *)(v14 + v30 + 16) )
      {
        *((_DWORD *)v13 + 34) = CWabiToDot11Converter::MapBandID(v31);
        *((_DWORD *)v13 + 35) = *(_DWORD *)(v14 + *((_QWORD *)a2 + 4) + 16);
      }
LABEL_40:
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (unsigned int)v11 < *((_DWORD *)a2 + 6) );
    if ( v16 )
    {
      if ( *((_DWORD *)v13 + 33) )
      {
        v39 = ++v9;
        v4 = CurrentConnectionInfo;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v32 = *((_DWORD *)CurrentConnectionInfo + 27);
          v37 = v32 + 1;
          LOBYTE(v32) = 4;
          WPP_RECORDER_SF_dDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v32,
            v12,
            80,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            v13[116],
            *((_DWORD *)CurrentConnectionInfo + 27),
            v37);
          v10 = 1336;
        }
        LODWORD(v8) = v44;
        if ( *((_DWORD *)CurrentConnectionInfo + 27) < *((_DWORD *)CurrentConnectionInfo + 26) )
        {
          *((_DWORD *)v13 + 33) = 0;
          ++*((_DWORD *)CurrentConnectionInfo + 27);
        }
      }
      else
      {
        v4 = CurrentConnectionInfo;
        LODWORD(v8) = v44;
      }
      goto LABEL_54;
    }
    v4 = CurrentConnectionInfo;
    LODWORD(v8) = v44;
LABEL_48:
    v33 = 6 * v12;
    if ( !*((_DWORD *)v4 + 12 * v12 + 33) )
    {
      v39 = ++v9;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v34 = *((_DWORD *)v4 + 27);
        v38 = v34 - 1;
        LOBYTE(v34) = 4;
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v34,
          v12,
          81,
          (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
          *((_BYTE *)v4 + 48 * v12 + 116),
          *((_DWORD *)v4 + 27),
          v38);
        LODWORD(v8) = v44;
        v10 = 1336;
      }
      if ( *((_DWORD *)v4 + 27) )
      {
        *((_DWORD *)v4 + 2 * v33 + 33) = 1;
        --*((_DWORD *)v4 + 27);
      }
    }
LABEL_54:
    v8 = (unsigned int)(v8 + 1);
    v44 = v8;
  }
  while ( (unsigned int)v8 < *((_DWORD *)v4 + 26) );
LABEL_55:
  if ( (unsigned int)Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( CPort::SetCurrentConnectionInfo(this, v4) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v36 = 82;
LABEL_62:
      LOBYTE(v35) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v35,
        1,
        v36,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
    }
  }
  else if ( (unsigned int)CPropertyCache::SetPropertyBuffer(
                            (CPort *)((char *)this + 480),
                            0x28u,
                            *(_DWORD *)v4,
                            (const unsigned __int8 *)v4)
         && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v36 = 83;
    goto LABEL_62;
  }
  return v9;
}

```

## disassembly

```asm
0x140017590  push    rbx
0x140017592  push    rsi
0x140017593  push    r13
0x140017595  sub     rsp, 80h
0x14001759c  mov     rbx, rdx
0x14001759f  mov     r13, rcx
0x1400175a2  mov     dl, 1; bool
0x1400175a4  call    ?GetCurrentConnectionInfo@CPort@@QEAAPEAUDOT11_CONNECTION_INFO@@_N@Z; CPort::GetCurrentConnectionInfo(bool)
0x1400175a9  mov     [rsp+98h+var_50], rax
0x1400175ae  mov     rsi, rax
0x1400175b1  test    rax, rax
0x1400175b4  jz      short loc_14001761C
0x1400175b6  movzx   ecx, byte ptr [rbx+10h]
0x1400175ba  lea     eax, [rcx-1]
0x1400175bd  cmp     al, 63h ; 'c'
0x1400175bf  ja      short loc_1400175C4
0x1400175c1  mov     [rsi+58h], ecx
0x1400175c4  call    Feature_Bugfix_58594056__private_IsEnabledDeviceUsageNoInline
0x1400175c9  test    eax, eax
0x1400175cb  jz      short loc_14001762B
0x1400175cd  cmp     dword ptr [rbx+18h], 0
0x1400175d1  jnz     short loc_14001762B
0x1400175d3  mov     rdx, rsi; struct DOT11_CONNECTION_INFO *
0x1400175d6  mov     rcx, r13; this
0x1400175d9  call    ?SetCurrentConnectionInfo@CPort@@QEAAHPEAUDOT11_CONNECTION_INFO@@@Z; CPort::SetCurrentConnectionInfo(DOT11_CONNECTION_INFO *)
0x1400175de  test    eax, eax
0x1400175e0  jz      short loc_14001761C
0x1400175e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400175e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400175f0  jz      short loc_14001761C
0x1400175f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175f9  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140017600  mov     r9d, 4Fh ; 'O'
0x140017606  mov     [rsp+98h+var_78], rax
0x14001760b  mov     r8d, 1
0x140017611  mov     dl, 4
0x140017613  mov     rcx, [rcx+40h]
0x140017617  call    WPP_RECORDER_SF_
0x14001761c  xor     eax, eax
0x14001761e  add     rsp, 80h
0x140017625  pop     r13
0x140017627  pop     rsi
0x140017628  pop     rbx
0x140017629  retn
0x14001762b  mov     [rsp+98h+var_28], r12
0x140017630  xor     edx, edx
0x140017632  xor     r12d, r12d
0x140017635  mov     [rsp+98h+var_30], r14
0x14001763a  lea     r14, WPP_RECORDER_INITIALIZED
0x140017641  mov     [rsp+98h+var_38], r15
0x140017646  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14001764d  mov     [rsp+98h+var_58], r12d
0x140017652  mov     [rsp+98h+arg_18], edx
0x140017659  cmp     [rsi+68h], edx
0x14001765c  jbe     loc_1400179F9
0x140017662  mov     [rsp+98h+arg_0], rbp
0x14001766a  mov     r9d, 538h
0x140017670  mov     [rsp+98h+var_20], rdi
0x140017675  xor     ebp, ebp
0x140017677  mov     r8d, edx
0x14001767a  mov     [rsp+98h+arg_10], 0
0x140017682  mov     [rsp+98h+var_48], r8
0x140017687  cmp     [rbx+18h], ebp
0x14001768a  jbe     loc_140017943
0x140017690  lea     r14, [rdx+rdx*2]
0x140017694  shl     r14, 4
0x140017698  add     r14, rsi
0x14001769b  nop     dword ptr [rax+rax+00h]
0x1400176a0  movzx   eax, byte ptr [r14+74h]
0x1400176a5  lea     rcx, ds:0[rbp*4]
0x1400176ad  add     rcx, rbp
0x1400176b0  lea     rdi, ds:0[rcx*8]
0x1400176b8  mov     rcx, [rbx+20h]
0x1400176bc  cmp     eax, [rdi+rcx]
0x1400176bf  jnz     loc_14001787A
0x1400176c5  cmp     dword ptr [r13+98h], 8
0x1400176cd  lea     rdx, [r14+7Bh]
0x1400176d1  mov     ecx, 6C8h
0x1400176d6  mov     r15b, 1
0x1400176d9  cmovnz  rcx, r9
0x1400176dd  mov     [rsp+98h+arg_10], r15b
0x1400176e5  add     rcx, [r13+88h]
0x1400176ec  mov     rax, [rcx]
0x1400176ef  mov     rax, [rax]
0x1400176f2  call    _guard_dispatch_icall
0x1400176f7  mov     rsi, rax
0x1400176fa  test    rax, rax
0x1400176fd  jz      loc_14001780B
0x140017703  mov     rcx, [rbx+20h]
0x140017707  mov     r12d, [rax+318h]
0x14001770e  mov     r15d, [rdi+rcx+14h]
0x140017713  test    r15d, r15d
0x140017716  jz      short loc_14001775D
0x140017718  mov     eax, [rdi+rcx+10h]
0x14001771c  mov     [rsp+98h+var_54], eax
0x140017720  test    eax, eax
0x140017722  jz      short loc_14001775D
0x140017724  mov     rcx, [r13+88h]
0x14001772b  add     rcx, 8
0x14001772f  mov     rax, [rcx]
0x140017732  mov     rax, [rax+8]
0x140017736  call    _guard_dispatch_icall
0x14001773b  mov     ecx, [r13+98h]
0x140017742  mov     r8, rax
0x140017745  mov     r9d, [rsp+98h+var_54]
0x14001774a  test    cl, 11h
0x14001774d  mov     rcx, rsi
0x140017750  mov     dword ptr [rsp+98h+var_78], r15d
0x140017755  setnz   dl
0x140017758  call    ?SetChannelAndPhyID@CBSSEntry@@QEAAX_NPEAVCAdapterPropertyCache@@IW4_WDI_BAND_ID@@@Z; CBSSEntry::SetChannelAndPhyID(bool,CAdapterPropertyCache *,uint,_WDI_BAND_ID)
0x14001775d  cmp     dword ptr [r13+98h], 8
0x140017765  mov     ecx, 6C8h
0x14001776a  movzx   eax, byte ptr [rbx+10h]
0x14001776e  mov     r9d, 538h
0x140017774  mov     rdx, [r13+88h]
0x14001777b  cmovnz  ecx, r9d
0x14001777f  mov     [rsi+254h], eax
0x140017785  cmp     al, 1Eh
0x140017787  jbe     short loc_1400177CC
0x140017789  cmp     word ptr [rsi+280h], 0
0x140017791  lea     r15, [rcx+rdx]
0x140017795  jbe     short loc_1400177A5
0x140017797  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x14001779c  mov     [rsi+2A0h], rax
0x1400177a3  jmp     short loc_1400177BB
0x1400177a5  cmp     word ptr [rsi+258h], 0
0x1400177ad  jbe     short loc_1400177CC
0x1400177af  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400177b4  mov     [rsi+278h], rax
0x1400177bb  mov     rdx, rsi; struct CBSSEntry *
0x1400177be  mov     rcx, r15; this
0x1400177c1  call    ?MoveBSSEntryToHeadOfList@CBSSListManager@@QEAAXPEAVCBSSEntry@@@Z; CBSSListManager::MoveBSSEntryToHeadOfList(CBSSEntry *)
0x1400177c6  mov     r9d, 538h
0x1400177cc  mov     r8, [rsp+98h+var_48]
0x1400177d1  mov     rdx, [rsp+98h+var_50]
0x1400177d6  mov     eax, [rsi+318h]
0x1400177dc  movzx   r15d, [rsp+98h+arg_10]
0x1400177e5  lea     rcx, [r8+3]
0x1400177e9  lea     rcx, [rcx+rcx*2]
0x1400177ed  add     rcx, rcx
0x1400177f0  mov     [rdx+rcx*8], eax
0x1400177f3  cmp     [rsi+318h], r12d
0x1400177fa  mov     r12d, [rsp+98h+var_58]
0x1400177ff  jz      short loc_140017816
0x140017801  inc     r12d
0x140017804  mov     [rsp+98h+var_58], r12d
0x140017809  jmp     short loc_140017816
0x14001780b  mov     r8, [rsp+98h+var_48]
0x140017810  mov     r9d, 538h
0x140017816  mov     rax, [rbx+20h]
0x14001781a  mov     ecx, [rdi+rax+18h]
0x14001781e  test    ecx, ecx
0x140017820  js      short loc_140017829
0x140017822  mov     ecx, [r14+94h]
0x140017829  mov     [r14+94h], ecx
0x140017830  mov     rax, [rbx+20h]
0x140017834  mov     ecx, [rdi+rax+1Ch]
0x140017838  test    ecx, ecx
0x14001783a  jnz     short loc_140017843
0x14001783c  mov     ecx, [r14+98h]
0x140017843  mov     [r14+98h], ecx
0x14001784a  mov     rax, [rbx+20h]
0x14001784e  mov     ecx, [rdi+rax+14h]
0x140017852  test    ecx, ecx
0x140017854  jz      short loc_140017883
0x140017856  cmp     dword ptr [rdi+rax+10h], 0
0x14001785b  jbe     short loc_140017883
0x14001785d  call    ?MapBandID@CWabiToDot11Converter@@SA?AW4_DOT11_BAND_ID@@W4_WDI_BAND_ID@@@Z; CWabiToDot11Converter::MapBandID(_WDI_BAND_ID)
0x140017862  mov     [r14+88h], eax
0x140017869  mov     rax, [rbx+20h]
0x14001786d  mov     ecx, [rdi+rax+10h]
0x140017871  mov     [r14+8Ch], ecx
0x140017878  jmp     short loc_140017883
0x14001787a  movzx   r15d, [rsp+98h+arg_10]
0x140017883  inc     ebp
0x140017885  cmp     ebp, [rbx+18h]
0x140017888  jb      loc_1400176A0
0x14001788e  test    r15b, r15b
0x140017891  jz      loc_140017929
0x140017897  cmp     dword ptr [r14+84h], 0
0x14001789f  jz      loc_1400179C0
0x1400178a5  inc     r12d
0x1400178a8  mov     [rsp+98h+var_58], r12d
0x1400178ad  mov     rsi, [rsp+98h+var_50]
0x1400178b2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400178b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400178c0  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400178c7  jz      short loc_140017903
0x1400178c9  mov     edx, [rsi+6Ch]
0x1400178cc  mov     r9d, 50h ; 'P'
0x1400178d2  movzx   ecx, byte ptr [r14+74h]
0x1400178d7  lea     eax, [rdx+1]
0x1400178da  mov     dword ptr [rsp+98h+var_60], eax
0x1400178de  mov     [rsp+98h+var_68], edx
0x1400178e2  mov     dl, 4
0x1400178e4  mov     [rsp+98h+var_70], ecx
0x1400178e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178ef  mov     [rsp+98h+var_78], r15
0x1400178f4  mov     rcx, [rcx+40h]
0x1400178f8  call    WPP_RECORDER_SF_dDd
0x1400178fd  mov     r9d, 538h
0x140017903  mov     eax, [rsi+68h]
0x140017906  mov     edx, [rsp+98h+arg_18]
0x14001790d  cmp     [rsi+6Ch], eax
0x140017910  jnb     loc_1400179D3
0x140017916  mov     dword ptr [r14+84h], 0
0x140017921  inc     dword ptr [rsi+6Ch]
0x140017924  jmp     loc_1400179D3
0x140017929  mov     rsi, [rsp+98h+var_50]
0x14001792e  lea     r14, WPP_RECORDER_INITIALIZED
0x140017935  mov     edx, [rsp+98h+arg_18]
0x14001793c  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140017943  lea     rdi, [r8+r8*2]
0x140017947  add     rdi, rdi
0x14001794a  cmp     dword ptr [rsi+rdi*8+84h], 0
0x140017952  jnz     loc_1400179DA
0x140017958  inc     r12d
0x14001795b  mov     [rsp+98h+var_58], r12d
0x140017960  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140017967  jz      short loc_1400179AA
0x140017969  mov     edx, [rsi+6Ch]
0x14001796c  mov     r9d, 51h ; 'Q'
0x140017972  movzx   ecx, byte ptr [rsi+rdi*8+74h]
0x140017977  lea     eax, [rdx-1]
0x14001797a  mov     dword ptr [rsp+98h+var_60], eax
0x14001797e  mov     [rsp+98h+var_68], edx
0x140017982  mov     dl, 4
0x140017984  mov     [rsp+98h+var_70], ecx
0x140017988  mov     rcx, cs:WPP_GLOBAL_Control
0x14001798f  mov     [rsp+98h+var_78], r15
0x140017994  mov     rcx, [rcx+40h]
0x140017998  call    WPP_RECORDER_SF_dDd
0x14001799d  mov     edx, [rsp+98h+arg_18]
0x1400179a4  mov     r9d, 538h
0x1400179aa  cmp     dword ptr [rsi+6Ch], 0
0x1400179ae  jbe     short loc_1400179DA
0x1400179b0  mov     dword ptr [rsi+rdi*8+84h], 1
0x1400179bb  dec     dword ptr [rsi+6Ch]
0x1400179be  jmp     short loc_1400179DA
0x1400179c0  mov     rsi, [rsp+98h+var_50]
0x1400179c5  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x1400179cc  mov     edx, [rsp+98h+arg_18]
0x1400179d3  lea     r14, WPP_RECORDER_INITIALIZED
0x1400179da  inc     edx
0x1400179dc  mov     [rsp+98h+arg_18], edx
0x1400179e3  cmp     edx, [rsi+68h]
0x1400179e6  jb      loc_140017675
0x1400179ec  mov     rdi, [rsp+98h+var_20]
0x1400179f1  mov     rbp, [rsp+98h+arg_0]
0x1400179f9  call    Feature_Bugfix_54405666__private_IsEnabledDeviceUsageNoInline
0x1400179fe  test    eax, eax
0x140017a00  jnz     short loc_140017A2E
0x140017a02  mov     r8d, [rsi]; unsigned int
0x140017a05  lea     rcx, [r13+1E0h]; this
0x140017a0c  mov     r9, rsi; unsigned __int8 *
0x140017a0f  mov     edx, 28h ; '('; unsigned int
0x140017a14  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x140017a19  test    eax, eax
0x140017a1b  jz      short loc_140017A69
0x140017a1d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140017a24  jz      short loc_140017A69
0x140017a26  mov     r9d, 53h ; 'S'
0x140017a2c  jmp     short loc_140017A4C
0x140017a2e  mov     rdx, rsi; struct DOT11_CONNECTION_INFO *
0x140017a31  mov     rcx, r13; this
0x140017a34  call    ?SetCurrentConnectionInfo@CPort@@QEAAHPEAUDOT11_CONNECTION_INFO@@@Z; CPort::SetCurrentConnectionInfo(DOT11_CONNECTION_INFO *)
0x140017a39  test    eax, eax
0x140017a3b  jz      short loc_140017A69
0x140017a3d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140017a44  jz      short loc_140017A69
0x140017a46  mov     r9d, 52h ; 'R'
0x140017a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a53  mov     r8d, 1
0x140017a59  mov     dl, 4
0x140017a5b  mov     [rsp+98h+var_78], r15
0x140017a60  mov     rcx, [rcx+40h]
0x140017a64  call    WPP_RECORDER_SF_
0x140017a69  mov     r15, [rsp+98h+var_38]
0x140017a6e  mov     eax, r12d
0x140017a71  mov     r12, [rsp+98h+var_28]
0x140017a76  mov     r14, [rsp+98h+var_30]
0x140017a7b  add     rsp, 80h
0x140017a82  pop     r13
0x140017a84  pop     rsi
0x140017a85  pop     rbx
0x140017a86  retn
```
