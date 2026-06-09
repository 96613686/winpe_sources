# JobHelper::DoUnInstall(_SwJob)

- ea: `0x18000dcb4`
- end: `0x18000e067`
- name: `?DoUnInstall@JobHelper@@AEAAJU_SwJob@@@Z`
- size: `947`
- prototype: `int __high(struct _SwJob)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180010700`

## callees

- `0x180002a50`
- `0x18000702c`
- `0x18000707c`
- `0x1800070e4`
- `0x18000a3c0`
- `0x18000b368`
- `0x18000b51c`
- `0x18000b588`
- `0x18000b7d8`
- `0x18000bbf8`
- `0x18000bd00`
- `0x18000dcb4`
- `0x18000e980`
- `0x180011a44`
- `0x180012338`
- `0x180017aac`
- `0x1800187f4`
- `0x18001a2c8`
- `0x18001a4f8`
- `0x18001ab3c`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall JobHelper::DoUnInstall(__int64 a1, __int64 *a2)
{
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // r9
  unsigned __int16 *v7; // rdi
  unsigned int v8; // ebx
  _QWORD *v9; // rax
  unsigned int v10; // r12d
  unsigned int v11; // ebx
  __int64 v12; // rax
  int updated; // r15d
  unsigned __int16 *v14; // rbx
  _QWORD *v15; // rax
  _DeployJob *v16; // rax
  _QWORD *v17; // rax
  unsigned __int16 *v18; // rsi
  _SwJob *v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // ebx
  int v22; // edi
  _QWORD *v23; // rax
  JobHelper *v24; // rcx
  _QWORD *v25; // r9
  unsigned __int16 *v26; // rsi
  unsigned int v27; // ebx
  int v28; // edi
  _QWORD *v29; // rax
  _QWORD v31[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v33[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v34[128]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[320]; // [rsp+108h] [rbp+8h] BYREF
  __int64 *v36; // [rsp+248h] [rbp+148h]
  _BYTE v37[32]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v38[64]; // [rsp+270h] [rbp+170h] BYREF
  int v39; // [rsp+2B0h] [rbp+1B0h]
  int v40; // [rsp+2C8h] [rbp+1C8h]

  v36 = a2;
  v4 = *(_DWORD *)(a1 + 104);
  v5 = *((_DWORD *)a2 + 56);
  if ( v5 < v4 )
  {
    v11 = v5 + 1;
    *((_DWORD *)a2 + 56) = v11;
    v12 = std::wstring::wstring(v32, a2);
    updated = JobHelper::UpdateDeployRetry(a1, v12, v11);
    if ( updated >= 0 )
    {
      v31[0] = v32;
      v14 = (unsigned __int16 *)std::wstring::wstring(v32, &dword_180022F6C);
      v15 = (_QWORD *)std::wstring::wstring(v33, a2);
      JobHelper::UpdateProgress(a1, v15, 80, 0, 0, v14);
      switch ( *((_DWORD *)a2 + 17) )
      {
        case 1:
          _DeployJob::_DeployJob((_DeployJob *)v37);
          std::wstring::operator=(v37, a2);
          std::wstring::operator=(v38, a2 + 4);
          v39 = 2;
          v40 = *(_DWORD *)(a1 + 108);
          v16 = _DeployJob::_DeployJob((_DeployJob *)v34, (const struct _DeployJob *)v37);
          updated = CInstallService::AddJob(a1 + 72, v16);
          _DeployJob::~_DeployJob((_DeployJob *)v37);
          goto LABEL_22;
        case 2:
          v17 = (_QWORD *)std::wstring::wstring(v32, a2 + 4);
          updated = WebAppUtil::DeleteWebApp(v17);
          *((_DWORD *)a2 + 24) = ((updated >> 31) & 0xFFFFFFF6) + 100;
          v31[0] = v32;
          v18 = (unsigned __int16 *)std::wstring::wstring(v32, a2 + 14);
LABEL_21:
          v21 = *((_DWORD *)a2 + 26);
          v22 = *((_DWORD *)a2 + 24);
          v23 = (_QWORD *)std::wstring::wstring(v33, a2);
          JobHelper::UpdateProgress(a1, v23, v22, 0, v21, v18);
LABEL_22:
          if ( updated < 0 )
          {
            v24 = (JobHelper *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            {
              v25 = a2 + 4;
              if ( (unsigned __int64)a2[7] >= 8 )
                v25 = (_QWORD *)*v25;
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                186,
                (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
                (_DWORD)v25,
                updated);
            }
            a2[12] = 90;
            *((_DWORD *)a2 + 26) = updated;
            JobHelper::GetErrorMessage(v24, (struct _SwJob *)a2);
            v31[0] = v32;
            v26 = (unsigned __int16 *)std::wstring::wstring(v32, a2 + 14);
            v27 = *((_DWORD *)a2 + 26);
            v28 = *((_DWORD *)a2 + 24);
            v29 = (_QWORD *)std::wstring::wstring(v33, a2);
            JobHelper::UpdateProgress(a1, v29, v28, 0, v27, v26);
          }
          break;
        case 3:
          v19 = _SwJob::_SwJob((_SwJob *)v35, (const struct _SwJob *)a2);
          updated = RemoteAppUtil::UninstallRemoteApp(v19);
          if ( updated >= 0 )
          {
            std::list<std::wstring>::list<std::wstring>(v31);
            updated = AppRegistry::GetApps(v20, (__int64)v31);
            if ( updated >= 0 && !v31[1] )
              RemoteAppUtil::UnsubscribeRemoteWorkspace();
            std::list<std::wstring>::~list<std::wstring>(v31);
          }
          *((_DWORD *)a2 + 24) = ((updated >> 31) & 0xFFFFFFF6) + 100;
          v31[0] = v32;
          v18 = (unsigned __int16 *)std::wstring::wstring(v32, a2 + 14);
          goto LABEL_21;
      }
    }
    v10 = updated;
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    if ( (unsigned __int64)a2[3] < 8 )
      LODWORD(v6) = (_DWORD)a2;
    else
      v6 = *a2;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      185,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      v6,
      v4);
  }
  v31[2] = v33;
  v7 = (unsigned __int16 *)std::wstring::wstring(v33, a2 + 14);
  v8 = *((_DWORD *)a2 + 26);
  v9 = (_QWORD *)std::wstring::wstring(v32, a2);
  JobHelper::UpdateProgress(a1, v9, 90, 0, v8, v7);
  v10 = 0;
LABEL_30:
  _SwJob::~_SwJob((_SwJob *)a2);
  return v10;
}

```

## disassembly

```asm
0x18000dcb4  mov     [rsp-8+arg_10], rbx
0x18000dcb9  push    rbp
0x18000dcba  push    rsi
0x18000dcbb  push    rdi
0x18000dcbc  push    r12
0x18000dcbe  push    r13
0x18000dcc0  push    r14
0x18000dcc2  push    r15
0x18000dcc4  lea     rbp, [rsp-1E0h]
0x18000dccc  sub     rsp, 2E0h
0x18000dcd3  mov     rax, cs:__security_cookie
0x18000dcda  xor     rax, rsp
0x18000dcdd  mov     [rbp+210h+var_40], rax
0x18000dce4  mov     r14, rdx
0x18000dce7  mov     r13, rcx
0x18000dcea  mov     [rbp+210h+var_C8], rdx
0x18000dcf1  mov     r8d, [rcx+68h]
0x18000dcf5  mov     ebx, [rdx+0E0h]
0x18000dcfb  cmp     ebx, r8d
0x18000dcfe  jb      loc_18000DD96
0x18000dd04  lea     rax, WPP_GLOBAL_Control
0x18000dd0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd12  cmp     rcx, rax
0x18000dd15  jz      short loc_18000DD46
0x18000dd17  test    byte ptr [rcx+1Ch], 1
0x18000dd1b  jz      short loc_18000DD46
0x18000dd1d  cmp     qword ptr [rdx+18h], 8
0x18000dd22  jb      short loc_18000DD29
0x18000dd24  mov     r9, [rdx]
0x18000dd27  jmp     short loc_18000DD2C
0x18000dd29  mov     r9, r14
0x18000dd2c  mov     edx, 0B9h
0x18000dd31  mov     [rsp+310h+var_2F0], r8d
0x18000dd36  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000dd3d  mov     rcx, [rcx+10h]
0x18000dd41  call    WPP_SF_Sd
0x18000dd46  lea     rax, [rsp+310h+var_2A8]
0x18000dd4b  mov     [rsp+310h+var_2D0], rax
0x18000dd50  lea     rdx, [r14+70h]
0x18000dd54  lea     rcx, [rsp+310h+var_2A8]
0x18000dd59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dd5e  mov     rdi, rax
0x18000dd61  mov     ebx, [r14+68h]
0x18000dd65  mov     rdx, r14
0x18000dd68  lea     rcx, [rsp+310h+var_2C8]
0x18000dd6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dd72  nop
0x18000dd73  mov     [rsp+310h+var_2E8], rdi
0x18000dd78  mov     [rsp+310h+var_2F0], ebx
0x18000dd7c  xor     r9d, r9d
0x18000dd7f  lea     r8d, [r9+5Ah]
0x18000dd83  mov     rdx, rax
0x18000dd86  mov     rcx, r13
0x18000dd89  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000dd8e  xor     r12d, r12d
0x18000dd91  jmp     loc_18000E031
0x18000dd96  inc     ebx
0x18000dd98  mov     [rdx+0E0h], ebx
0x18000dd9e  lea     rcx, [rsp+310h+var_2C8]
0x18000dda3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dda8  mov     r8d, ebx
0x18000ddab  mov     rdx, rax
0x18000ddae  mov     rcx, r13
0x18000ddb1  call    ?UpdateDeployRetry@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; JobHelper::UpdateDeployRetry(std::wstring,ulong)
0x18000ddb6  mov     r15d, eax
0x18000ddb9  xor     r12d, r12d
0x18000ddbc  test    eax, eax
0x18000ddbe  js      loc_18000E02E
0x18000ddc4  lea     rax, [rsp+310h+var_2C8]
0x18000ddc9  mov     [rsp+310h+var_2E0], rax
0x18000ddce  lea     rdx, dword_180022F6C
0x18000ddd5  lea     rcx, [rsp+310h+var_2C8]
0x18000ddda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000dddf  mov     rbx, rax
0x18000dde2  mov     rdx, r14
0x18000dde5  lea     rcx, [rsp+310h+var_2A8]
0x18000ddea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ddef  nop
0x18000ddf0  mov     [rsp+310h+var_2E8], rbx
0x18000ddf5  mov     [rsp+310h+var_2F0], r12d
0x18000ddfa  xor     r9d, r9d
0x18000ddfd  lea     r8d, [r12+50h]
0x18000de02  mov     rdx, rax
0x18000de05  mov     rcx, r13
0x18000de08  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000de0d  cmp     dword ptr [r14+44h], 1
0x18000de12  jnz     short loc_18000DE84
0x18000de14  lea     rcx, [rbp+210h+var_C0]; this
0x18000de1b  call    ??0_DeployJob@@QEAA@XZ; _DeployJob::_DeployJob(void)
0x18000de20  nop
0x18000de21  mov     rdx, r14
0x18000de24  lea     rcx, [rbp+210h+var_C0]
0x18000de2b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000de30  lea     rdx, [r14+20h]
0x18000de34  lea     rcx, [rbp+210h+var_A0]
0x18000de3b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000de40  mov     [rbp+210h+var_60], 2
0x18000de4a  mov     eax, [r13+6Ch]
0x18000de4e  mov     [rbp+210h+var_48], eax
0x18000de54  lea     rdx, [rbp+210h+var_C0]; struct _DeployJob *
0x18000de5b  lea     rcx, [rbp+210h+var_288]; this
0x18000de5f  call    ??0_DeployJob@@QEAA@AEBU0@@Z; _DeployJob::_DeployJob(_DeployJob const &)
0x18000de64  lea     rcx, [r13+48h]
0x18000de68  mov     rdx, rax
0x18000de6b  call    ?AddJob@CInstallService@@QEAAJU_DeployJob@@@Z; CInstallService::AddJob(_DeployJob)
0x18000de70  mov     r15d, eax
0x18000de73  lea     rcx, [rbp+210h+var_C0]; this
0x18000de7a  call    ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
0x18000de7f  jmp     loc_18000DF85
0x18000de84  cmp     dword ptr [r14+44h], 2
0x18000de89  jnz     short loc_18000DED1
0x18000de8b  lea     rdx, [r14+20h]
0x18000de8f  lea     rcx, [rsp+310h+var_2C8]
0x18000de94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000de99  mov     rcx, rax
0x18000de9c  call    ?DeleteWebApp@WebAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebAppUtil::DeleteWebApp(std::wstring)
0x18000dea1  mov     r15d, eax
0x18000dea4  sar     eax, 1Fh
0x18000dea7  and     eax, 0FFFFFFF6h
0x18000deaa  add     eax, 64h ; 'd'
0x18000dead  mov     [r14+60h], eax
0x18000deb1  lea     rax, [rsp+310h+var_2C8]
0x18000deb6  mov     [rsp+310h+var_2E0], rax
0x18000debb  lea     rdx, [r14+70h]
0x18000debf  lea     rcx, [rsp+310h+var_2C8]
0x18000dec4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dec9  mov     rsi, rax
0x18000decc  jmp     loc_18000DF55
0x18000ded1  cmp     dword ptr [r14+44h], 3
0x18000ded6  jnz     loc_18000E02E
0x18000dedc  mov     rdx, r14; struct _SwJob *
0x18000dedf  lea     rcx, [rbp+210h+var_208]; this
0x18000dee3  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x18000dee8  mov     rcx, rax
0x18000deeb  call    ?UninstallRemoteApp@RemoteAppUtil@@SAJU_SwJob@@@Z; RemoteAppUtil::UninstallRemoteApp(_SwJob)
0x18000def0  mov     r15d, eax
0x18000def3  test    eax, eax
0x18000def5  js      short loc_18000DF2A
0x18000def7  lea     rcx, [rsp+310h+var_2E0]
0x18000defc  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18000df01  nop
0x18000df02  lea     rdx, [rsp+310h+var_2E0]
0x18000df07  call    ?GetApps@AppRegistry@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@W4PackageApplicationType@@@Z; AppRegistry::GetApps(std::list<std::wstring> &,PackageApplicationType)
0x18000df0c  mov     r15d, eax
0x18000df0f  test    eax, eax
0x18000df11  js      short loc_18000DF20
0x18000df13  cmp     [rsp+310h+var_2D8], r12
0x18000df18  jnz     short loc_18000DF20
0x18000df1a  call    ?UnsubscribeRemoteWorkspace@RemoteAppUtil@@SAJXZ; RemoteAppUtil::UnsubscribeRemoteWorkspace(void)
0x18000df1f  nop
0x18000df20  lea     rcx, [rsp+310h+var_2E0]
0x18000df25  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x18000df2a  mov     eax, r15d
0x18000df2d  sar     eax, 1Fh
0x18000df30  and     eax, 0FFFFFFF6h
0x18000df33  add     eax, 64h ; 'd'
0x18000df36  mov     [r14+60h], eax
0x18000df3a  lea     rax, [rsp+310h+var_2C8]
0x18000df3f  mov     [rsp+310h+var_2E0], rax
0x18000df44  lea     rdx, [r14+70h]
0x18000df48  lea     rcx, [rsp+310h+var_2C8]
0x18000df4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000df52  mov     rsi, rax
0x18000df55  mov     ebx, [r14+68h]
0x18000df59  mov     edi, [r14+60h]
0x18000df5d  mov     rdx, r14
0x18000df60  lea     rcx, [rsp+310h+var_2A8]
0x18000df65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000df6a  nop
0x18000df6b  mov     [rsp+310h+var_2E8], rsi
0x18000df70  mov     [rsp+310h+var_2F0], ebx
0x18000df74  xor     r9d, r9d
0x18000df77  mov     r8d, edi
0x18000df7a  mov     rdx, rax
0x18000df7d  mov     rcx, r13
0x18000df80  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000df85  test    r15d, r15d
0x18000df88  jns     loc_18000E02E
0x18000df8e  lea     rax, WPP_GLOBAL_Control
0x18000df95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df9c  cmp     rcx, rax
0x18000df9f  jz      short loc_18000DFCF
0x18000dfa1  test    byte ptr [rcx+1Ch], 4
0x18000dfa5  jz      short loc_18000DFCF
0x18000dfa7  lea     r9, [r14+20h]
0x18000dfab  cmp     qword ptr [r9+18h], 8
0x18000dfb0  jb      short loc_18000DFB5
0x18000dfb2  mov     r9, [r9]
0x18000dfb5  mov     edx, 0BAh
0x18000dfba  mov     [rsp+310h+var_2F0], r15d
0x18000dfbf  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000dfc6  mov     rcx, [rcx+10h]
0x18000dfca  call    WPP_SF_Sd
0x18000dfcf  mov     qword ptr [r14+60h], 5Ah ; 'Z'
0x18000dfd7  mov     [r14+68h], r15d
0x18000dfdb  mov     rdx, r14; struct _SwJob *
0x18000dfde  call    ?GetErrorMessage@JobHelper@@AEAAXAEAU_SwJob@@@Z; JobHelper::GetErrorMessage(_SwJob &)
0x18000dfe3  lea     rax, [rsp+310h+var_2C8]
0x18000dfe8  mov     [rsp+310h+var_2E0], rax
0x18000dfed  lea     rdx, [r14+70h]
0x18000dff1  lea     rcx, [rsp+310h+var_2C8]
0x18000dff6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dffb  mov     rsi, rax
0x18000dffe  mov     ebx, [r14+68h]
0x18000e002  mov     edi, [r14+60h]
0x18000e006  mov     rdx, r14
0x18000e009  lea     rcx, [rsp+310h+var_2A8]
0x18000e00e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e013  nop
0x18000e014  mov     [rsp+310h+var_2E8], rsi
0x18000e019  mov     [rsp+310h+var_2F0], ebx
0x18000e01d  xor     r9d, r9d
0x18000e020  mov     r8d, edi
0x18000e023  mov     rdx, rax
0x18000e026  mov     rcx, r13
0x18000e029  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18000e02e  mov     r12d, r15d
0x18000e031  mov     rcx, r14; this
0x18000e034  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000e039  mov     eax, r12d
0x18000e03c  mov     rcx, [rbp+210h+var_40]
0x18000e043  xor     rcx, rsp; StackCookie
0x18000e046  call    __security_check_cookie
0x18000e04b  mov     rbx, [rsp+310h+arg_10]
0x18000e053  add     rsp, 2E0h
0x18000e05a  pop     r15
0x18000e05c  pop     r14
0x18000e05e  pop     r13
0x18000e060  pop     r12
0x18000e062  pop     rdi
0x18000e063  pop     rsi
0x18000e064  pop     rbp
0x18000e065  retn
```
