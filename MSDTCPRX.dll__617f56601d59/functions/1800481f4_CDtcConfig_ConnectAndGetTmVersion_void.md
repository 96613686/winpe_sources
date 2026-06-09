# CDtcConfig::ConnectAndGetTmVersion(void)

- ea: `0x1800481f4`
- end: `0x180048687`
- name: `?ConnectAndGetTmVersion@CDtcConfig@@AEAAJXZ`
- size: `1171`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049394`

## callees

- `0x180003cf0`
- `0x1800481f4`
- `0x180048d50`
- `0x180049010`
- `0x18007f7d8`
- `0x180085010`

## string_xrefs

- `0x18004823f`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180048296`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180048333`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180048381`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18004844d`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18004853e`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18004857b`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180048657`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x1800482fc`: `CSendReceive::CreateInstance2 failed.`
- `0x180048217`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x18004833a`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x180048388`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x180048484`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x1800484b2`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x180048516`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x180048545`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x180048582`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x1800485fd`: `CDtcConfig::ConnectAndGetTmVersion`
- `0x18004849e`: `Received TXUSER_GETSECURITYFLAGS_MTAG_FETCHED`

## pseudocode

```c
__int64 __fastcall CDtcConfig::ConnectAndGetTmVersion(CDtcConfig *this)
{
  struct CSendReceive *Instance2; // rdi
  int v3; // ebx
  const wchar_t *v4; // rax
  __int64 v5; // r9
  int ConnectionDispenser; // eax
  struct IConnectionDispenser *v7; // r12
  int PartnerNamedObject; // eax
  struct INameObject *v9; // r15
  const wchar_t *v10; // rax
  __int64 v11; // r9
  __int64 v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+28h] [rbp-40h]
  __int64 v15; // [rsp+38h] [rbp-30h]
  struct IConnectionDispenser *v16; // [rsp+50h] [rbp-18h] BYREF
  struct INameObject *v17; // [rsp+58h] [rbp-10h] BYREF
  int v18; // [rsp+B0h] [rbp+48h] BYREF
  int v19; // [rsp+B8h] [rbp+50h] BYREF
  int v20; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+60h] BYREF

  v19 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v21 = 0;
  Instance2 = 0;
  v20 = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    754,
    L"CDtcConfig::ConnectAndGetTmVersion",
    0,
    L"In");
  v3 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 336LL))(*((_QWORD *)this + 1), &v18);
  if ( v3 < 0 )
  {
    v4 = L"Could not query TmInstance for status.";
    v5 = 759;
LABEL_3:
    LODWORD(v13) = v3;
    TraceStringInline(
      15,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      v5,
      L"CDtcConfig::ConnectAndGetTmVersion",
      v13,
      v4);
    goto LABEL_36;
  }
  if ( !v18 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1), 1);
    if ( v3 < 0 )
    {
      v4 = L"Could not bring TmInstance online.";
      v5 = 767;
      goto LABEL_3;
    }
  }
  Instance2 = CSendReceive::CreateInstance2();
  if ( !Instance2 )
  {
    v3 = -2147024882;
    v4 = L"CSendReceive::CreateInstance2 failed.";
    v5 = 776;
    goto LABEL_3;
  }
  ConnectionDispenser = CDtcConfig::GetConnectionDispenser(this, &v16);
  v7 = v16;
  v3 = ConnectionDispenser;
  if ( ConnectionDispenser >= 0 )
  {
    PartnerNamedObject = CDtcConfig::GetPartnerNamedObject(this, &v17);
    v9 = v17;
    v3 = PartnerNamedObject;
    if ( PartnerNamedObject < 0 )
    {
      v10 = L"GetConnectionDispenser failed.";
      v11 = 790;
LABEL_13:
      LODWORD(v13) = v3;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        v11,
        L"CDtcConfig::ConnectAndGetTmVersion",
        v13,
        v10);
      goto LABEL_32;
    }
    v3 = (*(__int64 (__fastcall **)(struct CSendReceive *, struct IConnectionDispenser *, struct INameObject *, __int64, int))(*(_QWORD *)Instance2 + 248LL))(
           Instance2,
           v7,
           v17,
           1,
           53);
    if ( v3 < 0 )
    {
      v10 = L"Could not connect to TM.";
      v11 = 801;
      goto LABEL_13;
    }
    v3 = (*(__int64 (__fastcall **)(struct CSendReceive *, __int64, _QWORD, _QWORD, int *, __int64 *, _DWORD, int *))(*(_QWORD *)Instance2 + 96LL))(
           Instance2,
           21761,
           0,
           0,
           &v19,
           &v21,
           0,
           &v20);
    if ( v3 < 0 )
    {
      v10 = L"Could not send a message to TM.";
      v11 = 816;
      goto LABEL_13;
    }
    if ( v19 != 3 )
    {
      if ( v19 != 6 )
      {
        if ( v19 != 9 )
        {
          if ( v19 == 21762 )
          {
            TraceStringInline(
              15,
              4,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
              849,
              L"CDtcConfig::ConnectAndGetTmVersion",
              0,
              L"Received TXUSER_GETSECURITYFLAGS_MTAG_FETCHED");
            if ( v21 && v20 == 12 )
            {
              v3 = 0;
              _InterlockedCompareExchange(
                (volatile signed __int32 *)this + 26,
                (*(__int64 (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 128LL))(Instance2),
                0);
            }
            else
            {
              v3 = -2147024809;
            }
          }
          else
          {
            LODWORD(v15) = v19;
            v3 = -2147418113;
            LODWORD(v13) = -2147418113;
            TraceStringInline(
              15,
              1,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
              862,
              L"CDtcConfig::ConnectAndGetTmVersion",
              v13,
              L"Unexpected MTAG received %d",
              v15);
          }
LABEL_32:
          if ( v9 )
            (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v9 + 16LL))(v9);
          goto LABEL_34;
        }
        TraceStringInline(
          15,
          4,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
          823,
          L"CDtcConfig::ConnectAndGetTmVersion",
          0,
          L"Received MTAG_CONNECTION_DOWN");
      }
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        826,
        L"CDtcConfig::ConnectAndGetTmVersion",
        0,
        L"Received MTAG_CONNECTION_NOT_AVAILABLE");
      v3 = -2147168228;
      goto LABEL_32;
    }
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
      832,
      L"CDtcConfig::ConnectAndGetTmVersion",
      0,
      L"Received MTAG_CONNECTION_REQ_DENIED");
    if ( (*(unsigned int (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 128LL))(Instance2) >= 4 )
      v3 = (*(__int64 (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 152LL))(Instance2);
    else
      v3 = 0;
    goto LABEL_32;
  }
  LODWORD(v13) = ConnectionDispenser;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    783,
    L"CDtcConfig::ConnectAndGetTmVersion",
    v13,
    L"GetConnectionDispenser failed.");
LABEL_34:
  if ( v7 )
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_36:
  if ( v21 )
    (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 120LL))(Instance2);
  if ( Instance2 )
  {
    (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 272LL))(Instance2);
    (*(void (__fastcall **)(struct CSendReceive *))(*(_QWORD *)Instance2 + 168LL))(Instance2);
  }
  LODWORD(v14) = v3;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    883,
    L"CDtcConfig::ConnectAndGetTmVersion",
    v14,
    L"Out");
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800481f4  push    rbp
0x1800481f6  push    rbx
0x1800481f7  push    rsi
0x1800481f8  push    rdi
0x1800481f9  push    r12
0x1800481fb  push    r13
0x1800481fd  push    r14
0x1800481ff  push    r15
0x180048201  mov     rbp, rsp
0x180048204  sub     rsp, 68h
0x180048208  xor     r13d, r13d
0x18004820b  lea     rax, aIn_0; "In"
0x180048212  mov     [rsp+68h+var_38], rax
0x180048217  lea     r12, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x18004821e  mov     r14, rcx
0x180048221  mov     [rsp+68h+var_40], r13
0x180048226  mov     r9d, 2F2h
0x18004822c  mov     [rbp+arg_8], r13d
0x180048230  lea     r15d, [r13+0Fh]
0x180048234  mov     [rbp+var_18], r13
0x180048238  mov     ecx, r15d
0x18004823b  mov     [rbp+arg_0], r13d
0x18004823f  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048246  mov     [rbp+var_10], r13
0x18004824a  lea     edx, [r13+6]
0x18004824e  mov     [rbp+arg_18], r13
0x180048252  mov     edi, r13d
0x180048255  mov     [rbp+arg_10], r13d
0x180048259  mov     [rsp+68h+var_48], r12
0x18004825e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048263  mov     rcx, [r14+8]
0x180048267  lea     rdx, [rbp+arg_0]
0x18004826b  mov     rax, [rcx]
0x18004826e  mov     rax, [rax+150h]
0x180048275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004827a  mov     ebx, eax
0x18004827c  test    eax, eax
0x18004827e  jns     short loc_1800482B3
0x180048280  lea     rax, aCouldNotQueryT; "Could not query TmInstance for status."
0x180048287  mov     r9d, 2F7h
0x18004828d  lea     edx, [r13+1]
0x180048291  mov     [rsp+68h+var_38], rax
0x180048296  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004829d  mov     dword ptr [rsp+68h+var_40], ebx
0x1800482a1  mov     ecx, r15d
0x1800482a4  mov     [rsp+68h+var_48], r12
0x1800482a9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800482ae  jmp     loc_180048604
0x1800482b3  mov     esi, 1
0x1800482b8  cmp     [rbp+arg_0], r13d
0x1800482bc  jnz     short loc_1800482EA
0x1800482be  mov     rcx, [r14+8]
0x1800482c2  mov     edx, esi
0x1800482c4  mov     rax, [rcx]
0x1800482c7  mov     rax, [rax+140h]
0x1800482ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482d3  mov     ebx, eax
0x1800482d5  test    eax, eax
0x1800482d7  jns     short loc_1800482EA
0x1800482d9  lea     rax, aCouldNotBringT; "Could not bring TmInstance online."
0x1800482e0  mov     r9d, 2FFh
0x1800482e6  mov     edx, esi
0x1800482e8  jmp     short loc_180048291
0x1800482ea  call    ?CreateInstance2@CSendReceive@@SAPEAV1@XZ; CSendReceive::CreateInstance2(void)
0x1800482ef  mov     rdi, rax
0x1800482f2  test    rax, rax
0x1800482f5  jnz     short loc_18004830B
0x1800482f7  mov     ebx, 8007000Eh
0x1800482fc  lea     rax, aCsendreceiveCr; "CSendReceive::CreateInstance2 failed."
0x180048303  mov     r9d, 308h
0x180048309  jmp     short loc_1800482E6
0x18004830b  lea     rdx, [rbp+var_18]; struct IConnectionDispenser **
0x18004830f  mov     rcx, r14; this
0x180048312  call    ?GetConnectionDispenser@CDtcConfig@@QEAAJPEAPEAUIConnectionDispenser@@@Z; CDtcConfig::GetConnectionDispenser(IConnectionDispenser * *)
0x180048317  mov     r12, [rbp+var_18]
0x18004831b  mov     ebx, eax
0x18004831d  test    eax, eax
0x18004831f  jns     short loc_180048359
0x180048321  lea     rax, aGetconnectiond_0; "GetConnectionDispenser failed."
0x180048328  mov     r9d, 30Fh
0x18004832e  mov     [rsp+68h+var_38], rax
0x180048333  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004833a  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x180048341  mov     dword ptr [rsp+68h+var_40], ebx
0x180048345  mov     edx, esi
0x180048347  mov     [rsp+68h+var_48], rax
0x18004834c  mov     ecx, r15d
0x18004834f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048354  jmp     loc_1800485E8
0x180048359  lea     rdx, [rbp+var_10]; struct INameObject **
0x18004835d  mov     rcx, r14; this
0x180048360  call    ?GetPartnerNamedObject@CDtcConfig@@QEAAJPEAPEAUINameObject@@@Z; CDtcConfig::GetPartnerNamedObject(INameObject * *)
0x180048365  mov     r15, [rbp+var_10]
0x180048369  mov     ebx, eax
0x18004836b  test    eax, eax
0x18004836d  jns     short loc_1800483A9
0x18004836f  lea     rax, aGetconnectiond_0; "GetConnectionDispenser failed."
0x180048376  mov     r9d, 316h
0x18004837c  mov     [rsp+68h+var_38], rax
0x180048381  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048388  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x18004838f  mov     dword ptr [rsp+68h+var_40], ebx
0x180048393  mov     edx, esi
0x180048395  mov     [rsp+68h+var_48], rax
0x18004839a  mov     ecx, 0Fh
0x18004839f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800483a4  jmp     loc_1800485CE
0x1800483a9  mov     rax, [rdi]
0x1800483ac  mov     r9d, esi
0x1800483af  mov     r8, r15
0x1800483b2  mov     dword ptr [rsp+68h+var_48], 35h ; '5'
0x1800483ba  mov     rdx, r12
0x1800483bd  mov     rcx, rdi
0x1800483c0  mov     rax, [rax+0F8h]
0x1800483c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483cc  mov     ebx, eax
0x1800483ce  test    eax, eax
0x1800483d0  jns     short loc_1800483E1
0x1800483d2  lea     rax, aCouldNotConnec; "Could not connect to TM."
0x1800483d9  mov     r9d, 321h
0x1800483df  jmp     short loc_18004837C
0x1800483e1  mov     rax, [rdi]
0x1800483e4  lea     rcx, [rbp+arg_10]
0x1800483e8  mov     [rsp+68h+var_30], rcx
0x1800483ed  xor     r9d, r9d
0x1800483f0  lea     rcx, [rbp+arg_18]
0x1800483f4  mov     dword ptr [rsp+68h+var_38], r13d
0x1800483f9  mov     [rsp+68h+var_40], rcx
0x1800483fe  xor     r8d, r8d
0x180048401  mov     rax, [rax+60h]
0x180048405  lea     rcx, [rbp+arg_8]
0x180048409  mov     [rsp+68h+var_48], rcx
0x18004840e  mov     edx, 5501h
0x180048413  mov     rcx, rdi
0x180048416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004841b  mov     ebx, eax
0x18004841d  test    eax, eax
0x18004841f  jns     short loc_180048433
0x180048421  lea     rax, aCouldNotSendAM; "Could not send a message to TM."
0x180048428  mov     r9d, 330h
0x18004842e  jmp     loc_18004837C
0x180048433  mov     eax, [rbp+arg_8]
0x180048436  mov     ebx, 4
0x18004843b  cmp     eax, 3
0x18004843e  jz      loc_180048569
0x180048444  cmp     eax, 6
0x180048447  jz      loc_18004852C
0x18004844d  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048454  lea     ecx, [rbx+0Bh]
0x180048457  cmp     eax, 9
0x18004845a  jz      loc_180048502
0x180048460  cmp     eax, 5502h
0x180048465  jz      short loc_18004849E
0x180048467  mov     dword ptr [rsp+68h+var_30], eax
0x18004846b  mov     ebx, 8000FFFFh
0x180048470  lea     rax, aUnexpectedMtag; "Unexpected MTAG received %d"
0x180048477  mov     r9d, 35Eh
0x18004847d  mov     [rsp+68h+var_38], rax
0x180048482  mov     edx, esi
0x180048484  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x18004848b  mov     dword ptr [rsp+68h+var_40], ebx
0x18004848f  mov     [rsp+68h+var_48], rax
0x180048494  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048499  jmp     loc_1800485CE
0x18004849e  lea     rax, aReceivedTxuser; "Received TXUSER_GETSECURITYFLAGS_MTAG_F"...
0x1800484a5  mov     r9d, 351h
0x1800484ab  mov     [rsp+68h+var_38], rax
0x1800484b0  mov     edx, ebx
0x1800484b2  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x1800484b9  mov     [rsp+68h+var_40], r13
0x1800484be  mov     [rsp+68h+var_48], rax
0x1800484c3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800484c8  cmp     [rbp+arg_18], r13
0x1800484cc  jz      short loc_1800484F8
0x1800484ce  cmp     [rbp+arg_10], 0Ch
0x1800484d2  jnz     short loc_1800484F8
0x1800484d4  mov     rax, [rdi]
0x1800484d7  mov     rcx, rdi
0x1800484da  mov     ebx, r13d
0x1800484dd  mov     rax, [rax+80h]
0x1800484e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484e9  mov     ecx, eax
0x1800484eb  xor     eax, eax
0x1800484ed  lock cmpxchg [r14+68h], ecx
0x1800484f3  jmp     loc_1800485CE
0x1800484f8  mov     ebx, 80070057h
0x1800484fd  jmp     loc_1800485CE
0x180048502  lea     rax, aReceivedMtagCo; "Received MTAG_CONNECTION_DOWN"
0x180048509  mov     r9d, 337h
0x18004850f  mov     [rsp+68h+var_38], rax
0x180048514  mov     edx, ebx
0x180048516  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x18004851d  mov     [rsp+68h+var_40], r13
0x180048522  mov     [rsp+68h+var_48], rax
0x180048527  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004852c  lea     rax, aReceivedMtagCo_1; "Received MTAG_CONNECTION_NOT_AVAILABLE"
0x180048533  mov     r9d, 33Ah
0x180048539  mov     [rsp+68h+var_38], rax
0x18004853e  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048545  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x18004854c  mov     [rsp+68h+var_40], r13
0x180048551  mov     edx, ebx
0x180048553  mov     [rsp+68h+var_48], rax
0x180048558  mov     ecx, 0Fh
0x18004855d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048562  mov     ebx, 8004D01Ch
0x180048567  jmp     short loc_1800485CE
0x180048569  lea     rax, aReceivedMtagCo_0; "Received MTAG_CONNECTION_REQ_DENIED"
0x180048570  mov     r9d, 340h
0x180048576  mov     [rsp+68h+var_38], rax
0x18004857b  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180048582  lea     rax, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x180048589  mov     [rsp+68h+var_40], r13
0x18004858e  mov     edx, ebx
0x180048590  mov     [rsp+68h+var_48], rax
0x180048595  mov     ecx, 0Fh
0x18004859a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004859f  mov     rax, [rdi]
0x1800485a2  mov     rcx, rdi
0x1800485a5  mov     rax, [rax+80h]
0x1800485ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485b1  cmp     eax, ebx
0x1800485b3  jnb     short loc_1800485BA
0x1800485b5  mov     ebx, r13d
0x1800485b8  jmp     short loc_1800485CE
0x1800485ba  mov     rax, [rdi]
0x1800485bd  mov     rcx, rdi
0x1800485c0  mov     rax, [rax+98h]
0x1800485c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485cc  mov     ebx, eax
0x1800485ce  test    r15, r15
0x1800485d1  jz      short loc_1800485E2
0x1800485d3  mov     rax, [r15]
0x1800485d6  mov     rcx, r15
0x1800485d9  mov     rax, [rax+10h]
0x1800485dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485e2  mov     r15d, 0Fh
0x1800485e8  test    r12, r12
0x1800485eb  jz      short loc_1800485FD
0x1800485ed  mov     rax, [r12]
0x1800485f1  mov     rcx, r12
0x1800485f4  mov     rax, [rax+10h]
0x1800485f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485fd  lea     r12, aCdtcconfigConn; "CDtcConfig::ConnectAndGetTmVersion"
0x180048604  mov     rdx, [rbp+arg_18]
0x180048608  test    rdx, rdx
0x18004860b  jz      short loc_18004861C
0x18004860d  mov     rax, [rdi]
0x180048610  mov     rcx, rdi
0x180048613  mov     rax, [rax+78h]
0x180048617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004861c  test    rdi, rdi
0x18004861f  jz      short loc_180048645
0x180048621  mov     rax, [rdi]
0x180048624  mov     rcx, rdi
0x180048627  mov     rax, [rax+110h]
0x18004862e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048633  mov     rax, [rdi]
0x180048636  mov     rcx, rdi
0x180048639  mov     rax, [rax+0A8h]
0x180048640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048645  lea     rax, aOut; "Out"
0x18004864c  mov     r9d, 373h
0x180048652  mov     [rsp+68h+var_38], rax
0x180048657  lea     r8, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004865e  mov     dword ptr [rsp+68h+var_40], ebx
0x180048662  mov     edx, 6
0x180048667  mov     ecx, r15d
0x18004866a  mov     [rsp+68h+var_48], r12
0x18004866f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180048674  mov     eax, ebx
0x180048676  add     rsp, 68h
0x18004867a  pop     r15
0x18004867c  pop     r14
0x18004867e  pop     r13
0x180048680  pop     r12
0x180048682  pop     rdi
0x180048683  pop     rsi
0x180048684  pop     rbx
0x180048685  pop     rbp
0x180048686  retn
```
