# ShieldProvider::DashboardEx::GetPillarStatusEx(ulong,PillarStatusEx *)

- ea: `0x180069000`
- end: `0x180069282`
- name: `?GetPillarStatusEx@DashboardEx@ShieldProvider@@UEAAJKPEAUPillarStatusEx@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(ShieldProvider::DashboardEx *__hidden this, unsigned int, struct PillarStatusEx *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180068a38`
- `0x180069000`
- `0x1800696c4`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800690e5`
- `ole32!CoTaskMemFree` at `0x1800690f8`
- `ole32!CoTaskMemFree` at `0x180069105`
- `ole32!CoTaskMemFree` at `0x18006923e`
- `ole32!CoTaskMemFree` at `0x180069251`
- `ole32!CoTaskMemFree` at `0x18006925e`
- `ole32!CoTaskMemFree` at `0x1800690e5`
- `ole32!CoTaskMemFree` at `0x1800690f8`
- `ole32!CoTaskMemFree` at `0x180069105`
- `ole32!CoTaskMemFree` at `0x18006923e`
- `ole32!CoTaskMemFree` at `0x180069251`
- `ole32!CoTaskMemFree` at `0x18006925e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DashboardEx::GetPillarStatusEx(
        ShieldProvider::DashboardEx *this,
        int a2,
        struct PillarStatusEx *a3)
{
  int v7; // ebx
  int v8; // edi
  _QWORD *v9; // rbx
  void *v10; // rcx
  void *v11; // rcx
  int NetworkProtectionPillarStatus; // edi
  unsigned __int16 *v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  LPVOID v16; // rbx
  unsigned __int16 **v17; // rdx
  unsigned __int16 **v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  LPVOID pv; // [rsp+60h] [rbp+40h] BYREF
  __int64 v22; // [rsp+68h] [rbp+48h] BYREF

  if ( !a3 )
    return 2147942487LL;
  *((_DWORD *)a3 + 1) = 1;
  *(_DWORD *)a3 = 23;
  v22 = 0;
  v7 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v22);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_9a072a55361f3902b023016d7eb82632_Traceguids,
        (unsigned int)v7);
    goto LABEL_49;
  }
  pv = 0;
  v8 = a2 - 1;
  if ( v8 )
  {
    if ( v8 != 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9a072a55361f3902b023016d7eb82632_Traceguids, 2147942487LL);
        v9 = pv;
        if ( pv )
        {
          v10 = (void *)*((_QWORD *)pv + 1);
          if ( v10 )
          {
            CoTaskMemFree(v10);
            v9[1] = 0;
          }
          v11 = (void *)v9[2];
          if ( v11 )
          {
            CoTaskMemFree(v11);
            v9[2] = 0;
          }
          CoTaskMemFree(v9);
        }
      }
      v7 = -2147024809;
      goto LABEL_49;
    }
    NetworkProtectionPillarStatus = ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatusEx(this, &pv);
    if ( NetworkProtectionPillarStatus < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v15 = 40;
LABEL_22:
      WPP_SF_d(
        v14[2],
        v15,
        WPP_9a072a55361f3902b023016d7eb82632_Traceguids,
        (unsigned int)NetworkProtectionPillarStatus);
LABEL_23:
      v16 = pv;
      goto LABEL_42;
    }
  }
  else
  {
    NetworkProtectionPillarStatus = ShieldProvider::DashboardEx::GetThreatPillarStatusEx(
                                      this,
                                      (struct PillarStatusEx **)&pv);
    if ( NetworkProtectionPillarStatus < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      v15 = 39;
      goto LABEL_22;
    }
  }
  v16 = pv;
  if ( pv )
  {
    v17 = (unsigned __int16 **)*((_QWORD *)pv + 2);
    if ( v17 )
    {
      NetworkProtectionPillarStatus = CommonUtil::UtilCoDuplicateString(
                                        (struct PillarStatusEx *)((char *)a3 + 16),
                                        v17,
                                        v13);
      if ( NetworkProtectionPillarStatus < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_23;
        v15 = 42;
        goto LABEL_22;
      }
      v16 = pv;
    }
    v18 = (unsigned __int16 **)*((_QWORD *)v16 + 1);
    if ( v18 )
    {
      NetworkProtectionPillarStatus = CommonUtil::UtilCoDuplicateString(
                                        (struct PillarStatusEx *)((char *)a3 + 8),
                                        v18,
                                        v13);
      if ( NetworkProtectionPillarStatus < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_23;
        v15 = 43;
        goto LABEL_22;
      }
      v16 = pv;
    }
    *((_DWORD *)a3 + 1) = *((_DWORD *)v16 + 1);
    *(_DWORD *)a3 = *(_DWORD *)v16;
LABEL_42:
    if ( v16 )
    {
      v19 = (void *)*((_QWORD *)v16 + 1);
      if ( v19 )
      {
        CoTaskMemFree(v19);
        *((_QWORD *)v16 + 1) = 0;
      }
      v20 = (void *)*((_QWORD *)v16 + 2);
      if ( v20 )
      {
        CoTaskMemFree(v20);
        *((_QWORD *)v16 + 2) = 0;
      }
      CoTaskMemFree(v16);
    }
  }
  v7 = NetworkProtectionPillarStatus;
LABEL_49:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180069000  mov     [rsp-28h+arg_0], rbx
0x180069005  push    rbp
0x180069006  push    rsi
0x180069007  push    rdi
0x180069008  push    r14
0x18006900a  push    r15
0x18006900c  mov     rbp, rsp
0x18006900f  sub     rsp, 20h
0x180069013  xor     r15d, r15d
0x180069016  mov     rsi, r8
0x180069019  mov     edi, edx
0x18006901b  mov     r14, rcx
0x18006901e  test    r8, r8
0x180069021  jnz     short loc_18006902D
0x180069023  mov     eax, 80070057h
0x180069028  jmp     loc_180069271
0x18006902d  lea     rcx, [rbp+arg_18]
0x180069031  mov     dword ptr [r8+4], 1
0x180069039  mov     dword ptr [r8], 17h
0x180069040  mov     [rbp+arg_18], r15
0x180069044  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180069049  mov     ebx, eax
0x18006904b  test    eax, eax
0x18006904d  jns     short loc_18006908D
0x18006904f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069056  lea     rax, WPP_GLOBAL_Control
0x18006905d  cmp     rcx, rax
0x180069060  jz      loc_180069266
0x180069066  test    byte ptr [rcx+1Ch], 1
0x18006906a  jz      loc_180069266
0x180069070  mov     rcx, [rcx+10h]
0x180069074  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x18006907b  mov     edx, 26h ; '&'
0x180069080  mov     r9d, ebx
0x180069083  call    WPP_SF_d
0x180069088  jmp     loc_180069266
0x18006908d  mov     [rbp+pv], r15
0x180069091  sub     edi, 1
0x180069094  jz      loc_180069161
0x18006909a  cmp     edi, 3
0x18006909d  jz      short loc_180069115
0x18006909f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800690a6  lea     rax, WPP_GLOBAL_Control
0x1800690ad  cmp     rcx, rax
0x1800690b0  jz      short loc_18006910B
0x1800690b2  test    byte ptr [rcx+1Ch], 1
0x1800690b6  jz      short loc_18006910B
0x1800690b8  mov     rcx, [rcx+10h]
0x1800690bc  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x1800690c3  mov     edx, 29h ; ')'
0x1800690c8  mov     r9d, 80070057h
0x1800690ce  call    WPP_SF_d
0x1800690d3  mov     rbx, [rbp+pv]
0x1800690d7  test    rbx, rbx
0x1800690da  jz      short loc_18006910B
0x1800690dc  mov     rcx, [rbx+8]; pv
0x1800690e0  test    rcx, rcx
0x1800690e3  jz      short loc_1800690EF
0x1800690e5  call    cs:__imp_CoTaskMemFree
0x1800690eb  mov     [rbx+8], r15
0x1800690ef  mov     rcx, [rbx+10h]; pv
0x1800690f3  test    rcx, rcx
0x1800690f6  jz      short loc_180069102
0x1800690f8  call    cs:__imp_CoTaskMemFree
0x1800690fe  mov     [rbx+10h], r15
0x180069102  mov     rcx, rbx; pv
0x180069105  call    cs:__imp_CoTaskMemFree
0x18006910b  mov     ebx, 80070057h
0x180069110  jmp     loc_180069266
0x180069115  lea     rdx, [rbp+pv]; struct PillarStatusEx **
0x180069119  mov     rcx, r14; this
0x18006911c  call    ?GetNetworkProtectionPillarStatusEx@DashboardEx@ShieldProvider@@AEAAJPEAPEAUPillarStatusEx@@@Z; ShieldProvider::DashboardEx::GetNetworkProtectionPillarStatusEx(PillarStatusEx * *)
0x180069121  mov     edi, eax
0x180069123  test    eax, eax
0x180069125  jns     short loc_180069193
0x180069127  mov     rcx, cs:WPP_GLOBAL_Control
0x18006912e  lea     rax, WPP_GLOBAL_Control
0x180069135  cmp     rcx, rax
0x180069138  jz      short loc_180069158
0x18006913a  test    byte ptr [rcx+1Ch], 1
0x18006913e  jz      short loc_180069158
0x180069140  mov     edx, 28h ; '('
0x180069145  mov     rcx, [rcx+10h]
0x180069149  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x180069150  mov     r9d, edi
0x180069153  call    WPP_SF_d
0x180069158  mov     rbx, [rbp+pv]
0x18006915c  jmp     loc_180069230
0x180069161  lea     rdx, [rbp+pv]; struct PillarStatusEx **
0x180069165  mov     rcx, r14; this
0x180069168  call    ?GetThreatPillarStatusEx@DashboardEx@ShieldProvider@@AEAAJPEAPEAUPillarStatusEx@@@Z; ShieldProvider::DashboardEx::GetThreatPillarStatusEx(PillarStatusEx * *)
0x18006916d  mov     edi, eax
0x18006916f  test    eax, eax
0x180069171  jns     short loc_180069193
0x180069173  mov     rcx, cs:WPP_GLOBAL_Control
0x18006917a  lea     rax, WPP_GLOBAL_Control
0x180069181  cmp     rcx, rax
0x180069184  jz      short loc_180069158
0x180069186  test    byte ptr [rcx+1Ch], 1
0x18006918a  jz      short loc_180069158
0x18006918c  mov     edx, 27h ; '''
0x180069191  jmp     short loc_180069145
0x180069193  mov     rbx, [rbp+pv]
0x180069197  test    rbx, rbx
0x18006919a  jz      loc_180069264
0x1800691a0  mov     rdx, [rbx+10h]; unsigned __int16 **
0x1800691a4  test    rdx, rdx
0x1800691a7  jz      short loc_1800691DF
0x1800691a9  lea     rcx, [rsi+10h]; this
0x1800691ad  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800691b2  mov     edi, eax
0x1800691b4  test    eax, eax
0x1800691b6  jns     short loc_1800691DB
0x1800691b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691bf  lea     rax, WPP_GLOBAL_Control
0x1800691c6  cmp     rcx, rax
0x1800691c9  jz      short loc_180069158
0x1800691cb  test    byte ptr [rcx+1Ch], 1
0x1800691cf  jz      short loc_180069158
0x1800691d1  mov     edx, 2Ah ; '*'
0x1800691d6  jmp     loc_180069145
0x1800691db  mov     rbx, [rbp+pv]
0x1800691df  mov     rdx, [rbx+8]; unsigned __int16 **
0x1800691e3  test    rdx, rdx
0x1800691e6  jz      short loc_180069226
0x1800691e8  lea     rcx, [rsi+8]; this
0x1800691ec  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800691f1  mov     edi, eax
0x1800691f3  test    eax, eax
0x1800691f5  jns     short loc_180069222
0x1800691f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691fe  lea     rax, WPP_GLOBAL_Control
0x180069205  cmp     rcx, rax
0x180069208  jz      loc_180069158
0x18006920e  test    byte ptr [rcx+1Ch], 1
0x180069212  jz      loc_180069158
0x180069218  mov     edx, 2Bh ; '+'
0x18006921d  jmp     loc_180069145
0x180069222  mov     rbx, [rbp+pv]
0x180069226  mov     eax, [rbx+4]
0x180069229  mov     [rsi+4], eax
0x18006922c  mov     eax, [rbx]
0x18006922e  mov     [rsi], eax
0x180069230  test    rbx, rbx
0x180069233  jz      short loc_180069264
0x180069235  mov     rcx, [rbx+8]; pv
0x180069239  test    rcx, rcx
0x18006923c  jz      short loc_180069248
0x18006923e  call    cs:__imp_CoTaskMemFree
0x180069244  mov     [rbx+8], r15
0x180069248  mov     rcx, [rbx+10h]; pv
0x18006924c  test    rcx, rcx
0x18006924f  jz      short loc_18006925B
0x180069251  call    cs:__imp_CoTaskMemFree
0x180069257  mov     [rbx+10h], r15
0x18006925b  mov     rcx, rbx; pv
0x18006925e  call    cs:__imp_CoTaskMemFree
0x180069264  mov     ebx, edi
0x180069266  lea     rcx, [rbp+arg_18]
0x18006926a  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18006926f  mov     eax, ebx
0x180069271  mov     rbx, [rsp+20h+arg_0]
0x180069276  add     rsp, 20h
0x18006927a  pop     r15
0x18006927c  pop     r14
0x18006927e  pop     rdi
0x18006927f  pop     rsi
0x180069280  pop     rbp
0x180069281  retn
```
