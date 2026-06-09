# CSessionObject::MaintainItInUpState(void)

- ea: `0x180003150`
- end: `0x180003994`
- name: `?MaintainItInUpState@CSessionObject@@AEAAXXZ`
- size: `2116`
- prototype: `void __fastcall(CSessionObject *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000290c`

## callees

- `0x180003150`
- `0x180003cf0`
- `0x180003d60`
- `0x18000f674`
- `0x18001234c`
- `0x1800123a8`
- `0x18002f534`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800033b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800036e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800033b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800036e3`

## string_xrefs

- `0x1800031e4`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x180003307`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800034a2`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800035c5`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x18000368b`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800037a9`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800037f4`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x18000386b`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800031c5`: `CSO: Maintain session; Received E_CM_SERVER_NOT_READY`
- `0x180003575`: `CSO: Maintain session; Received E_CM_SERVER_NOT_READY`
- `0x18000363f`: `ProcId = 0x%x CSO: Maintain session; Received E_CM_SERVER_NOT_READY. \n`

## pseudocode

```c
void __fastcall CSessionObject::MaintainItInUpState(CSessionObject *this)
{
  bool v2; // zf
  int v3; // edi
  int v4; // ebp
  unsigned int v5; // esi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  char *v10; // r14
  DWORD v11; // edx
  int v12; // [rsp+30h] [rbp-278h]
  int v13; // [rsp+30h] [rbp-278h]
  __int64 v14; // [rsp+38h] [rbp-270h]
  __int64 v15; // [rsp+40h] [rbp-268h]
  int v16; // [rsp+50h] [rbp-258h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-254h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-250h] BYREF
  int v19; // [rsp+60h] [rbp-248h] BYREF
  __int64 v20; // [rsp+68h] [rbp-240h] BYREF
  char v21[256]; // [rsp+70h] [rbp-238h] BYREF
  char v22[256]; // [rsp+170h] [rbp-138h] BYREF

  v2 = *((_DWORD *)this + 26) == 7;
  v3 = 0;
  v16 = 0;
  v4 = 0;
  v5 = 0;
  v18 = 0;
  v17 = 0;
  v20 = 0;
  if ( v2 )
  {
    do
    {
      if ( *((_DWORD *)this + 25) || v5 > 0xA )
        break;
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2435,
        L"CSessionObject::MaintainItInUpState",
        0,
        L"STATUS : In State UP\n");
      *((_DWORD *)this + 164) = 0;
      if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 86) + 88LL))((char *)this + 688)
        || (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 90) + 88LL))((char *)this + 720)
        || (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 102) + 88LL))((char *)this + 816) )
      {
        *((_DWORD *)this + 165) = 0;
      }
      else if ( ++*((_DWORD *)this + 165) > *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 81) + 136LL) + 12LL) )
      {
        *((_DWORD *)this + 2) = 0;
        TraceStringInline(
          1,
          3,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
          2459,
          L"CSessionObject::MaintainItInUpState",
          0,
          L"Session idle timeout over, tearing down the session");
      }
      if ( *((_DWORD *)this + 6) == 1 )
        *((_DWORD *)this + 2) = 0;
      if ( *((_DWORD *)this + 2) )
      {
        if ( *((_DWORD *)this + 25) != 1 )
          goto LABEL_10;
        v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 80) + 24LL))(
               *((_QWORD *)this + 80),
               *((unsigned int *)this + 24),
               2);
        v9 = 6;
      }
      else
      {
        CSessionObject::SetStatus(this, 3);
        v9 = 8;
      }
      CSessionObject::SetState(this, v9);
LABEL_10:
      *((_DWORD *)this + 3) = 0;
      if ( !*((_DWORD *)this + 25) )
        v3 = CSessionObject::NegotiateResources(this);
      if ( v3 == -2147483279 )
      {
        v10 = (char *)this + 1040;
        (**((void (__fastcall ***)(char *))this + 130))((char *)this + 1040);
        if ( *((_DWORD *)this + 26) == 7 )
          *((_DWORD *)this + 26) = 6;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this + 1040);
        (**(void (__fastcall ***)(char *))v10)((char *)this + 1040);
        if ( !*((_DWORD *)this + 25) )
          *((_DWORD *)this + 25) = 1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this + 1040);
        continue;
      }
      if ( v3 )
      {
        v19 = v3;
        DtcWriteToEventLoggerA(
          4u,
          3u,
          0x4000103Cu,
          4u,
          &v19,
          "INFORMATIONAL: Negotiate Resources returned OUT OF RESOURCES IN SSTATE_UP",
          v12);
        TraceStringInline(
          1,
          3,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
          2521,
          L"CSessionObject::MaintainItInUpState",
          0,
          L"INFORMATIONAL: Negotiate Resources returned OUT OF RESOURCES IN SSTATE_UP");
      }
      if ( !v4 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21), 1);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 64LL))(*((_QWORD *)this + 21));
        v6 = *((_QWORD *)this + 21);
        *((_DWORD *)this + 7) = 0;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
      }
      v7 = *((_DWORD *)this + 25);
      if ( v7 )
      {
        if ( v7 != 3 )
        {
          v3 = -2147467259;
          TraceStringInline(
            1,
            3,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2594,
            L"CSessionObject::MaintainItInUpState",
            0,
            L"Session Status was not UP");
LABEL_54:
          StringCchPrintfA(
            v22,
            0xFCu,
            "INFORMATIONAL : CSO::Maintain_SSTATE_UP session Failed Error =0x%x RpcStatus = %ld ",
            v3,
            v16);
          DtcWriteToEventLoggerA(4u, 3u, 0x4000103Cu, 0, 0, v22, v13);
          LODWORD(v15) = v16;
          LODWORD(v14) = v3;
          TraceStringInline(
            1,
            3,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2778,
            L"CSessionObject::MaintainItInUpState",
            0,
            L"INFORMATIONAL : CSO::Maintain_SSTATE_UP session Failed Error =0x%x RpcStatus = %ld ",
            v14,
            v15);
LABEL_55:
          CSessionObject::SetState(this, 6);
          CSessionObject::SetStatus(this, 1);
LABEL_56:
          v4 = 0;
          v5 = 0;
          continue;
        }
        v3 = 0;
      }
      else
      {
        if ( !v4 )
          (*(void (__fastcall **)(_QWORD, unsigned int *, unsigned int *, __int64 *))(**((_QWORD **)this + 21) + 40LL))(
            *((_QWORD *)this + 21),
            &v18,
            &v17,
            &v20);
        TraceStringInline(
          1,
          240,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
          2570,
          L"CSessionObject::MaintainItInUpState",
          0,
          L"Shipping box car");
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int *))(**((_QWORD **)this + 80) + 40LL))(
               *((_QWORD *)this + 80),
               v18,
               v17,
               v20,
               &v16);
        v3 = v8;
        if ( v8 )
        {
          switch ( v8 )
          {
            case -2147483391:
              if ( v5 < 0xA )
              {
                v11 = 15000 * (v5 % 3) / 3;
LABEL_45:
                WaitForSingleObject(*((HANDLE *)this + 16), v11);
LABEL_46:
                v4 = 1;
                ++v5;
              }
              else
              {
                StringCchPrintfA(
                  v21,
                  0xFBu,
                  "ProcId = 0x%x CSO: Maintain session: Received E_S_UNAVAILABLE_OR_BUSY and reached max retry limit. Giving up.\n",
                  **(_DWORD **)(*((_QWORD *)this + 81) + 136LL));
                DtcWriteToEventLoggerA(4u, 3u, 0x4000103Cu, 0, 0, v21, v13);
                TraceStringInline(
                  1,
                  3,
                  L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                  2744,
                  L"CSessionObject::MaintainItInUpState",
                  0,
                  L"CSO: Maintain session: Received E_S_UNAVAILABLE_OR_BUSY and reached max retry limit. Giving up.");
                ++v5;
                v4 = 1;
              }
              break;
            case -2147483367:
              *((_DWORD *)this + 2) = 0;
              CSessionObject::SetStatus(this, 3);
              CSessionObject::SetState(this, 8);
              goto LABEL_56;
            case -2147483357:
              StringCchPrintfA(
                v21,
                0xFBu,
                "ProcId = 0x%x CSO: Maintain session; Received E_CM_SERVER_NOT_READY. \n",
                **(_DWORD **)(*((_QWORD *)this + 81) + 136LL));
              DtcWriteToEventLoggerA(4u, 3u, 0x4000103Cu, 0, 0, v21, v13);
              TraceStringInline(
                1,
                3,
                L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
                2678,
                L"CSessionObject::MaintainItInUpState",
                0,
                L"CSO: Maintain session; Received E_CM_SERVER_NOT_READY");
              if ( v5 <= 2 )
                goto LABEL_46;
              v11 = -1;
              goto LABEL_45;
            case -2147483354:
              v5 = 10;
              DtcWriteToEventLoggerA(4u, 3u, 0x4000103Cu, 0, 0, "Received E_CM_S_OUTOFRESOURCES on Send", v13);
              continue;
            case -2147483279:
              CSessionObject::SetState(this, 6);
              CSessionObject::SetStatus(this, 1);
              continue;
            case -2147483276:
              goto LABEL_55;
            default:
              goto LABEL_54;
          }
          continue;
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 21) + 48LL))(*((_QWORD *)this + 21), 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 72LL))(*((_QWORD *)this + 21));
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 21) + 56LL))(*((_QWORD *)this + 21), 0);
      v4 = 0;
      v5 = 0;
      if ( *((_DWORD *)this + 7) != 1 )
        WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF);
    }
    while ( *((_DWORD *)this + 26) == 7 );
  }
  if ( *((_DWORD *)this + 25) == 1 )
  {
    (**((void (__fastcall ***)(char *))this + 130))((char *)this + 1040);
    if ( *((_DWORD *)this + 26) == 7 )
      *((_DWORD *)this + 26) = 6;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 130) + 8LL))((char *)this + 1040);
  }
  else if ( v5 > 0xA )
  {
    CSessionObject::SetState(this, 6);
    CSessionObject::SetStatus(this, 1);
  }
}

```

## disassembly

```asm
0x180003150  mov     r11, rsp
0x180003153  push    rbx
0x180003154  push    rsi
0x180003155  push    rdi
0x180003156  sub     rsp, 290h
0x18000315d  mov     rax, cs:__security_cookie
0x180003164  xor     rax, rsp
0x180003167  mov     [rsp+2A8h+var_38], rax
0x18000316f  mov     [r11+10h], rbp
0x180003173  mov     rbx, rcx
0x180003176  mov     [r11-28h], r15
0x18000317a  xor     r15d, r15d
0x18000317d  cmp     dword ptr [rcx+68h], 7
0x180003181  mov     edi, r15d
0x180003184  mov     [rsp+2A8h+var_258], r15d
0x180003189  mov     ebp, r15d
0x18000318c  mov     esi, r15d
0x18000318f  mov     [rsp+2A8h+var_250], r15d
0x180003194  mov     [rsp+2A8h+var_254], r15d
0x180003199  mov     [rsp+2A8h+var_240], r15
0x18000319e  jnz     loc_1800033E0
0x1800031a4  mov     [r11+18h], r12
0x1800031a8  lea     rax, aStatusInStateU; "STATUS : In State UP\n"
0x1800031af  mov     [r11+20h], r13
0x1800031b3  lea     r12, aCsessionobject_1; "CSessionObject::MaintainItInUpState"
0x1800031ba  mov     [r11-20h], r14
0x1800031be  lea     r13, aReceivedECmSOu; "Received E_CM_S_OUTOFRESOURCES on Send"
0x1800031c5  lea     r14, aCsoMaintainSes; "CSO: Maintain session; Received E_CM_SE"...
0x1800031cc  cmp     [rbx+64h], r15d
0x1800031d0  jnz     loc_1800033C8
0x1800031d6  cmp     esi, 0Ah
0x1800031d9  ja      loc_1800033C8
0x1800031df  mov     qword ptr [rsp+2A8h+var_278], rax; int
0x1800031e4  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x1800031eb  mov     [rsp+2A8h+var_280], r15
0x1800031f0  mov     r9d, 983h
0x1800031f6  mov     edx, 0F0h
0x1800031fb  mov     [rsp+2A8h+var_288], r12
0x180003200  mov     ecx, 1
0x180003205  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000320a  lea     rcx, [rbx+2B0h]
0x180003211  mov     [rbx+290h], r15d
0x180003218  mov     rax, [rcx]
0x18000321b  mov     rax, [rax+58h]
0x18000321f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003224  test    eax, eax
0x180003226  jz      loc_180003439
0x18000322c  mov     [rbx+294h], r15d
0x180003233  cmp     dword ptr [rbx+18h], 1
0x180003237  jz      loc_1800034CD
0x18000323d  cmp     [rbx+8], r15d
0x180003241  jz      loc_1800034D6
0x180003247  cmp     dword ptr [rbx+64h], 1
0x18000324b  jz      loc_1800034EA
0x180003251  mov     [rbx+0Ch], r15d
0x180003255  cmp     [rbx+64h], r15d
0x180003259  jnz     short loc_180003265
0x18000325b  mov     rcx, rbx; this
0x18000325e  call    ?NegotiateResources@CSessionObject@@QEAAJXZ; CSessionObject::NegotiateResources(void)
0x180003263  mov     edi, eax
0x180003265  cmp     edi, 80000171h
0x18000326b  jz      loc_18000351A
0x180003271  test    edi, edi
0x180003273  jnz     loc_180003581
0x180003279  test    ebp, ebp
0x18000327b  jnz     short loc_1800032C4
0x18000327d  mov     rcx, [rbx+0A8h]
0x180003284  mov     edx, 1
0x180003289  mov     rax, [rcx]
0x18000328c  mov     rax, [rax+30h]
0x180003290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003295  mov     rcx, [rbx+0A8h]
0x18000329c  mov     rax, [rcx]
0x18000329f  mov     rax, [rax+40h]
0x1800032a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a8  mov     rcx, [rbx+0A8h]
0x1800032af  mov     edx, 1
0x1800032b4  mov     [rbx+1Ch], r15d
0x1800032b8  mov     rax, [rcx]
0x1800032bb  mov     rax, [rax+38h]
0x1800032bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c4  mov     eax, [rbx+64h]
0x1800032c7  test    eax, eax
0x1800032c9  jnz     loc_1800037D5
0x1800032cf  test    ebp, ebp
0x1800032d1  jnz     short loc_1800032F5
0x1800032d3  mov     rcx, [rbx+0A8h]
0x1800032da  lea     r9, [rsp+2A8h+var_240]
0x1800032df  lea     r8, [rsp+2A8h+var_254]
0x1800032e4  lea     rdx, [rsp+2A8h+var_250]
0x1800032e9  mov     rax, [rcx]
0x1800032ec  mov     rax, [rax+28h]
0x1800032f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f5  lea     rax, aShippingBoxCar; "Shipping box car"
0x1800032fc  mov     r9d, 0A0Ah
0x180003302  mov     qword ptr [rsp+2A8h+var_278], rax; int
0x180003307  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x18000330e  mov     [rsp+2A8h+var_280], r15
0x180003313  mov     edx, 0F0h
0x180003318  mov     ecx, 1
0x18000331d  mov     [rsp+2A8h+var_288], r12
0x180003322  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180003327  mov     rcx, [rbx+280h]
0x18000332e  lea     rdx, [rsp+2A8h+var_258]
0x180003333  mov     r9, [rsp+2A8h+var_240]
0x180003338  mov     r8d, [rsp+2A8h+var_254]
0x18000333d  mov     [rsp+2A8h+var_288], rdx
0x180003342  mov     rax, [rcx]
0x180003345  mov     edx, [rsp+2A8h+var_250]
0x180003349  mov     rax, [rax+28h]
0x18000334d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003352  mov     edi, eax
0x180003354  test    eax, eax
0x180003356  jnz     loc_1800035EA
0x18000335c  mov     rcx, [rbx+0A8h]
0x180003363  xor     edx, edx
0x180003365  mov     rax, [rcx]
0x180003368  mov     rax, [rax+30h]
0x18000336c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003371  mov     rcx, [rbx+0A8h]
0x180003378  mov     rax, [rcx]
0x18000337b  mov     rax, [rax+48h]
0x18000337f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003384  mov     rcx, [rbx+0A8h]
0x18000338b  xor     edx, edx
0x18000338d  mov     rax, [rcx]
0x180003390  mov     rax, [rax+38h]
0x180003394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003399  cmp     dword ptr [rbx+1Ch], 1
0x18000339d  mov     ebp, r15d
0x1800033a0  mov     esi, r15d
0x1800033a3  jz      short loc_1800033B7
0x1800033a5  mov     rcx, [rbx+80h]; hHandle
0x1800033ac  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800033b1  call    cs:__imp_WaitForSingleObject
0x1800033b7  cmp     dword ptr [rbx+68h], 7
0x1800033bb  lea     rax, aStatusInStateU; "STATUS : In State UP\n"
0x1800033c2  jz      loc_1800031CC
0x1800033c8  mov     r13, [rsp+2A8h+arg_18]
0x1800033d0  mov     r12, [rsp+2A8h+arg_10]
0x1800033d8  mov     r14, [rsp+2A8h+var_20]
0x1800033e0  cmp     dword ptr [rbx+64h], 1
0x1800033e4  mov     r15, [rsp+2A8h+var_28]
0x1800033ec  mov     rbp, [rsp+2A8h+arg_8]
0x1800033f4  jnz     loc_1800038CA
0x1800033fa  mov     rax, [rbx+410h]
0x180003401  lea     rcx, [rbx+410h]
0x180003408  mov     rax, [rax]
0x18000340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003410  cmp     dword ptr [rbx+68h], 7
0x180003414  jnz     short loc_18000341D
0x180003416  mov     dword ptr [rbx+68h], 6
0x18000341d  mov     rax, [rbx+410h]
0x180003424  lea     rcx, [rbx+410h]
0x18000342b  mov     rax, [rax+8]
0x18000342f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003434  jmp     loc_1800038E9
0x180003439  lea     rcx, [rbx+2D0h]
0x180003440  mov     rax, [rcx]
0x180003443  mov     rax, [rax+58h]
0x180003447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344c  test    eax, eax
0x18000344e  jnz     loc_18000322C
0x180003454  lea     rcx, [rbx+330h]
0x18000345b  mov     rax, [rcx]
0x18000345e  mov     rax, [rax+58h]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  test    eax, eax
0x180003469  jnz     loc_18000322C
0x18000346f  inc     dword ptr [rbx+294h]
0x180003475  mov     rax, [rbx+288h]
0x18000347c  mov     edx, [rbx+294h]
0x180003482  mov     rcx, [rax+88h]
0x180003489  cmp     edx, [rcx+0Ch]
0x18000348c  jbe     loc_180003233
0x180003492  lea     rax, aSessionIdleTim; "Session idle timeout over, tearing down"...
0x180003499  mov     [rbx+8], r15d
0x18000349d  mov     qword ptr [rsp+2A8h+var_278], rax
0x1800034a2  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x1800034a9  mov     [rsp+2A8h+var_280], r15
0x1800034ae  mov     r9d, 99Bh
0x1800034b4  mov     edx, 3
0x1800034b9  mov     [rsp+2A8h+var_288], r12
0x1800034be  mov     ecx, 1
0x1800034c3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800034c8  jmp     loc_180003233
0x1800034cd  mov     [rbx+8], r15d
0x1800034d1  jmp     loc_18000323D
0x1800034d6  mov     edx, 3
0x1800034db  mov     rcx, rbx
0x1800034de  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x1800034e3  mov     edx, 8
0x1800034e8  jmp     short loc_18000350D
0x1800034ea  mov     rcx, [rbx+280h]
0x1800034f1  mov     r8d, 2
0x1800034f7  mov     edx, [rbx+60h]
0x1800034fa  mov     rax, [rcx]
0x1800034fd  mov     rax, [rax+18h]
0x180003501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003506  mov     edi, eax
0x180003508  mov     edx, 6
0x18000350d  mov     rcx, rbx
0x180003510  call    ?SetState@CSessionObject@@QEAAXW4_SessionState@@@Z; CSessionObject::SetState(_SessionState)
0x180003515  jmp     loc_180003251
0x18000351a  lea     r14, [rbx+410h]
0x180003521  mov     rax, [r14]
0x180003524  mov     rcx, r14
0x180003527  mov     rax, [rax]
0x18000352a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352f  cmp     dword ptr [rbx+68h], 7
0x180003533  jnz     short loc_18000353C
0x180003535  mov     dword ptr [rbx+68h], 6
0x18000353c  mov     rax, [r14]
0x18000353f  mov     rcx, r14
0x180003542  mov     rax, [rax+8]
0x180003546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354b  mov     rax, [r14]
0x18000354e  mov     rcx, r14
0x180003551  mov     rax, [rax]
0x180003554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003559  cmp     [rbx+64h], r15d
0x18000355d  jnz     short loc_180003566
0x18000355f  mov     dword ptr [rbx+64h], 1
0x180003566  mov     rax, [r14]
0x180003569  mov     rcx, r14
0x18000356c  mov     rax, [rax+8]
0x180003570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003575  lea     r14, aCsoMaintainSes; "CSO: Maintain session; Received E_CM_SE"...
0x18000357c  jmp     loc_1800033B7
0x180003581  lea     rax, aInformationalN; "INFORMATIONAL: Negotiate Resources retu"...
0x180003588  mov     [rsp+2A8h+var_248], edi
0x18000358c  mov     [rsp+2A8h+var_280], rax; char *
0x180003591  mov     ecx, 4; unsigned int
0x180003596  lea     rax, [rsp+2A8h+var_248]
0x18000359b  mov     edx, 3; unsigned int
0x1800035a0  mov     r9d, ecx; unsigned int
0x1800035a3  mov     [rsp+2A8h+var_288], rax; void *
0x1800035a8  mov     r8d, 4000103Ch; unsigned int
0x1800035ae  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x1800035b3  lea     rax, aInformationalN_0; "INFORMATIONAL: Negotiate Resources retu"...
0x1800035ba  mov     r9d, 9D9h
0x1800035c0  mov     qword ptr [rsp+2A8h+var_278], rax
0x1800035c5  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x1800035cc  mov     [rsp+2A8h+var_280], r15
0x1800035d1  mov     edx, 3
0x1800035d6  mov     ecx, 1
0x1800035db  mov     [rsp+2A8h+var_288], r12
0x1800035e0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800035e5  jmp     loc_180003279
0x1800035ea  add     eax, 7FFFFEFFh; switch 116 cases
0x1800035ef  cmp     eax, 73h
0x1800035f2  ja      def_180003613; jumptable 0000000180003613 default case, cases -2147483390--2147483368,-2147483366--2147483358,-2147483356,-2147483355,-2147483353--2147483280,-2147483278,-2147483277
0x1800035f8  lea     rdx, __ImageBase
0x1800035ff  cdqe
0x180003601  movzx   eax, ds:(byte_180003920 - 180000000h)[rdx+rax]
0x180003609  mov     ecx, ds:(jpt_180003613 - 180000000h)[rdx+rax*4]
0x180003610  add     rcx, rdx
0x180003613  jmp     rcx; switch jump
0x180003615  mov     edx, 3; jumptable 0000000180003613 case -2147483367
0x18000361a  mov     [rbx+8], r15d
0x18000361e  mov     rcx, rbx
0x180003621  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180003626  mov     edx, 8
0x18000362b  mov     rcx, rbx
0x18000362e  call    ?SetState@CSessionObject@@QEAAXW4_SessionState@@@Z; CSessionObject::SetState(_SessionState)
0x180003633  jmp     loc_1800038BF
0x180003638  mov     rax, [rbx+288h]; jumptable 0000000180003613 case -2147483357
0x18000363f  lea     r8, aProcid0xXCsoMa; "ProcId = 0x%x CSO: Maintain session; Re"...
0x180003646  mov     edx, 0FBh; unsigned __int64
0x18000364b  lea     rcx, [rsp+2A8h+var_238]; char *
0x180003650  mov     r9, [rax+88h]
0x180003657  mov     r9d, [r9]
0x18000365a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000365f  lea     rax, [rsp+2A8h+var_238]
0x180003664  xor     r9d, r9d; unsigned int
0x180003667  mov     [rsp+2A8h+var_280], rax; char *
0x18000366c  mov     edx, 3; unsigned int
0x180003671  mov     ecx, 4; unsigned int
0x180003676  mov     [rsp+2A8h+var_288], r15; void *
0x18000367b  mov     r8d, 4000103Ch; unsigned int
0x180003681  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x180003686  mov     qword ptr [rsp+2A8h+var_278], r14
0x18000368b  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180003692  mov     [rsp+2A8h+var_280], r15
0x180003697  mov     r9d, 0A76h
0x18000369d  mov     edx, 3
0x1800036a2  mov     [rsp+2A8h+var_288], r12
0x1800036a7  mov     ecx, 1
0x1800036ac  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800036b1  cmp     esi, 2
0x1800036b4  jbe     short loc_1800036E9
0x1800036b6  mov     edx, 0FFFFFFFFh
0x1800036bb  jmp     short loc_1800036DC
0x1800036bd  mov     eax, 0AAAAAAABh
0x1800036c2  mov     ecx, esi
0x1800036c4  mul     esi
0x1800036c6  shr     edx, 1
0x1800036c8  lea     eax, [rdx+rdx*2]
0x1800036cb  sub     ecx, eax
0x1800036cd  mov     eax, 0AAAAAAABh
  ... truncated ...
```
