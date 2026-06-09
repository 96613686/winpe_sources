# PhoneController::_ExecuteVerb(PhoneLine *,uint const &,CallVerbs,VerbParameters *,int)

- ea: `0x18003a14c`
- end: `0x18003a71f`
- name: `?_ExecuteVerb@PhoneController@@IEAAJPEAVPhoneLine@@AEBIW4CallVerbs@@PEAVVerbParameters@@H@Z`
- size: `1491`
- prototype: `int __high(struct PhoneLine *, const unsigned int *, enum CallVerbs, struct VerbParameters *, int)`
- caller_count: `5`
- callee_count: `36`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022f70`
- `0x1800243e0`
- `0x180026770`
- `0x18003a048`
- `0x180046a20`

## callees

- `0x1800011fc`
- `0x180005660`
- `0x180005c54`
- `0x180006e94`
- `0x18001d764`
- `0x18002c574`
- `0x18002c580`
- `0x18003a14c`
- `0x180043f90`
- `0x18006d8b8`
- `0x18006d9b0`
- `0x18006da94`
- `0x18006dc70`
- `0x18006e27c`
- `0x18006f494`
- `0x18006f5ac`
- `0x18006f744`
- `0x18006f828`
- `0x18006f9d8`
- `0x18006fb70`
- `0x18006fd08`
- `0x180071698`
- `0x180074be8`
- `0x180074fc8`
- `0x1800750b4`
- `0x1800754e0`
- `0x1800755cc`
- `0x180075928`
- `0x180075ac8`
- `0x180075bb4`
- `0x180075ce8`
- `0x180076028`
- `0x180076438`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a18a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a1ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a18a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a1ab`

## string_xrefs

- `0x18003a19f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003a4bc`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003a603`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003a684`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003a6ba`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003a6e8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_ExecuteVerb(
        __int64 a1,
        PhoneLine *a2,
        const unsigned int *a3,
        int a4,
        __int64 a5,
        int a6)
{
  __int64 v10; // rcx
  unsigned __int64 v11; // rsi
  PhoneLine **v12; // rax
  BackTraceCollection *v13; // rcx
  PhoneLine **v14; // r12
  unsigned int v15; // r13d
  _QWORD *v16; // rax
  BackTraceCollection *v17; // rcx
  PhoneController *v18; // r13
  _QWORD *v19; // rcx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  int v24; // ebx
  int active; // eax
  unsigned int v26; // ebx
  int v28; // eax
  BackTraceCollection *v29; // rcx
  __int64 v30; // r9
  __int64 v31; // rdx
  PhoneController *v32; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-71h] BYREF
  __int128 v34; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+60h] [rbp-59h] BYREF
  const char *v36; // [rsp+80h] [rbp-39h]
  __int64 v37; // [rsp+88h] [rbp-31h]
  __int128 *v38; // [rsp+90h] [rbp-29h]
  __int64 v39; // [rsp+98h] [rbp-21h]
  PhoneController **v40; // [rsp+A0h] [rbp-19h]
  __int64 v41; // [rsp+A8h] [rbp-11h]
  unsigned __int64 *v42; // [rsp+B0h] [rbp-9h]
  __int64 v43; // [rsp+B8h] [rbp-1h]

  v32 = (PhoneController *)a1;
  if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v10, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3359);
    if ( *(_DWORD *)(a1 + 240) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v11 = *(_QWORD *)(a1 + 160);
  *(_QWORD *)(a1 + 160) = v11 + 1;
  v12 = (PhoneLine **)operator new(0x28u);
  v14 = v12;
  if ( !v12 )
  {
    v26 = -2147024882;
    BackTraceCollection::Capture(v13, -2147024882);
    v30 = 3368;
    v31 = 0;
LABEL_75:
    Log_HREvent_7(v26, v31, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v30);
    return v26;
  }
  v15 = *a3;
  *v12 = a2;
  if ( a2 )
    (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)v14 + 8) = a6;
  v14[1] = (PhoneLine *)v11;
  *((_DWORD *)v14 + 4) = v15;
  *((_DWORD *)v14 + 5) = a4;
  v14[3] = 0;
  v16 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v16 )
  {
    v18 = v32;
    v16[2] = v14;
    v19 = (_QWORD *)*((_QWORD *)v18 + 14);
    v16[1] = v19;
    *v16 = (char *)v18 + 104;
    *v19 = v16;
    *((_QWORD *)v18 + 14) = v16;
    ++*((_QWORD *)v18 + 15);
    v34 = *(_OWORD *)((char *)a2 + 88);
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      v33 = v11;
      v42 = &v33;
      LODWORD(v32) = a4;
      v40 = &v32;
      v43 = 8;
      v38 = &v34;
      v41 = 4;
      v36 = "PhoneController: Controller request to provider";
      v39 = 16;
      v37 = 48;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&word_1800A835A, 0, 0, 6u, &v35);
    }
    if ( a4 > 0x2000 )
    {
      if ( a4 > 0x200000 )
      {
        switch ( a4 )
        {
          case 0x2000000:
            v26 = -2147020579;
            goto LABEL_70;
          case 0x4000000:
            active = PhoneLine::SendRealTimeTextData(a2, a3, *(const unsigned __int16 **)(a5 + 32), v11);
            goto LABEL_67;
          case 0x8000000:
            active = PhoneLine::AcceptUpgradingRealTimeTextCall(a2, a3, v11);
            goto LABEL_67;
          case 0x10000000:
            active = PhoneLine::UpgradeToRealTimeTextCall(a2, a3, v11);
            goto LABEL_67;
          case 0x20000000:
            active = PhoneLine::DowngradeFromRealTimeTextCall(a2, a3, v11);
            goto LABEL_67;
        }
      }
      else
      {
        switch ( a4 )
        {
          case 0x200000:
            active = PhoneLine::SetVideoPaused(a2, a3, *(_DWORD *)(a5 + 276), v11);
            goto LABEL_67;
          case 0x8000:
            active = PhoneLine::DisableLocalVideo(a2, a3, v11);
            goto LABEL_67;
          case 0x10000:
            active = PhoneLine::EnableLocalVideo(a2, a3, v11);
            goto LABEL_67;
          case 0x20000:
            active = PhoneLine::AddVideo(a2, a3, v11);
            goto LABEL_67;
          case 0x40000:
            active = PhoneLine::DropVideo(a2, a3, v11);
            goto LABEL_67;
          case 0x80000:
            active = PhoneLine::AcceptVideo(a2, a3, v11);
            goto LABEL_67;
          case 0x100000:
            active = PhoneLine::RejectVideo(a2, a3, v11);
            goto LABEL_67;
        }
      }
    }
    else
    {
      if ( a4 == 0x2000 )
      {
        active = PhoneLine::StopDtmf(a2, a3, *(_WORD *)(a5 + 64), v11);
        goto LABEL_67;
      }
      if ( a4 <= 64 )
      {
        if ( a4 == 64 )
        {
          active = PhoneLine::Private(a2, a3, v11);
        }
        else
        {
          v20 = a4 - 1;
          if ( v20 )
          {
            v21 = v20 - 1;
            if ( v21 )
            {
              v22 = v21 - 2;
              if ( v22 )
              {
                v23 = v22 - 4;
                if ( v23 )
                {
                  v24 = v23 - 8;
                  if ( v24 )
                  {
                    if ( v24 == 16 )
                    {
                      active = PhoneLine::Swap(
                                 a2,
                                 (const unsigned int *)(a5 + 216),
                                 (const unsigned int *)(a5 + 220),
                                 v11);
                      goto LABEL_67;
                    }
                    goto LABEL_62;
                  }
                  active = PhoneLine::Unhold(a2, a3, v11);
                }
                else
                {
                  active = PhoneLine::Hold(a2, a3, v11);
                }
              }
              else
              {
                active = PhoneLine::DropActiveAcceptHeld(a2, a5 + 224, a5 + 228, *(unsigned int *)(a5 + 236), v11);
              }
            }
            else
            {
              active = PhoneLine::End(a2, a3, *(_DWORD *)(a5 + 232), v11);
            }
          }
          else
          {
            active = PhoneLine::Dial(
                       a2,
                       a3,
                       *(unsigned int *)(a5 + 212),
                       *(_QWORD *)(a5 + 112),
                       *(_DWORD *)(a5 + 208),
                       *(_QWORD *)(a5 + 144),
                       v11);
          }
        }
LABEL_67:
        v26 = active;
        if ( active >= 0 )
          return 0;
        goto LABEL_70;
      }
      switch ( a4 )
      {
        case 128:
          if ( !a5 )
          {
            Log_AssertionEvent_3(v19, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3395);
            __int2c();
          }
          active = PhoneLine::Conference(a2, (const unsigned int *)(a5 + 104), (const unsigned int *)(a5 + 108), v11);
          goto LABEL_67;
        case 256:
          v26 = -2147467262;
LABEL_70:
          v28 = PhoneController::_OnOperationCompleteMessage(v18, v11, v26);
          if ( v28 < 0 )
            Log_HREvent_7(
              (unsigned int)v28,
              0,
              "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
              3513);
          BackTraceCollection::Capture(v29, v26);
          v30 = 3515;
          v31 = 1;
          goto LABEL_75;
        case 512:
          active = PhoneLine::RejectIncoming(a2, a3, *(unsigned int *)(a5 + 272), v11);
          goto LABEL_67;
        case 1024:
          active = PhoneLine::AcceptIncoming((_DWORD)a2, (_DWORD)a3, *(_DWORD *)(a5 + 236), (int)a5 + 240, v11);
          goto LABEL_67;
        case 2048:
          active = PhoneLine::SendDtmf(a2, a3, *(const unsigned __int16 **)a5, v11);
          goto LABEL_67;
        case 4096:
          active = PhoneLine::StartDtmf(a2, a3, *(_WORD *)(a5 + 64), v11);
          goto LABEL_67;
      }
    }
LABEL_62:
    Log_AssertionEvent_3(v19, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3505);
    __int2c();
    v26 = -2147467259;
    goto LABEL_70;
  }
  v26 = -2147024882;
  BackTraceCollection::Capture(v17, -2147024882);
  Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3369);
  tlx::_delete<PhoneController::RequestInfo>((__int64 *)v14);
  return v26;
}

```

## disassembly

```asm
0x18003a14c  mov     [rsp-8+arg_18], rbx
0x18003a151  push    rbp
0x18003a152  push    rsi
0x18003a153  push    rdi
0x18003a154  push    r12
0x18003a156  push    r13
0x18003a158  push    r14
0x18003a15a  push    r15
0x18003a15c  lea     rbp, [rsp-17h]
0x18003a161  sub     rsp, 0D0h
0x18003a168  mov     rax, cs:__security_cookie
0x18003a16f  xor     rax, rsp
0x18003a172  mov     [rbp+47h+var_40], rax
0x18003a176  mov     r15, [rbp+47h+arg_20]
0x18003a17a  mov     ebx, r9d
0x18003a17d  mov     r14, r8
0x18003a180  mov     [rbp+47h+var_C0], rcx
0x18003a184  mov     rdi, rdx
0x18003a187  mov     r13, rcx
0x18003a18a  call    cs:__imp_GetCurrentThreadId
0x18003a190  cmp     [r13+0F0h], eax
0x18003a197  jz      short loc_18003A1BF
0x18003a199  mov     r8d, 0D1Fh
0x18003a19f  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003a1a6  call    Log_AssertionEvent_3
0x18003a1ab  call    cs:__imp_GetCurrentThreadId
0x18003a1b1  cmp     [r13+0F0h], eax
0x18003a1b8  jz      short loc_18003A1BF
0x18003a1ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a1bf  mov     rsi, [r13+0A0h]
0x18003a1c6  mov     ecx, 28h ; '('; Size
0x18003a1cb  lea     rax, [rsi+1]
0x18003a1cf  mov     [r13+0A0h], rax
0x18003a1d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a1db  mov     r12, rax
0x18003a1de  test    rax, rax
0x18003a1e1  jz      loc_18003A6D4
0x18003a1e7  mov     r13d, [r14]
0x18003a1ea  mov     [rax], rdi
0x18003a1ed  test    rdi, rdi
0x18003a1f0  jz      short loc_18003A201
0x18003a1f2  mov     rcx, [rdi]
0x18003a1f5  mov     rax, [rcx+8]
0x18003a1f9  mov     rcx, rdi
0x18003a1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a201  mov     eax, [rbp+47h+arg_28]
0x18003a204  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a20b  mov     ecx, 18h; unsigned __int64
0x18003a210  mov     [r12+20h], eax
0x18003a215  mov     [r12+8], rsi
0x18003a21a  mov     [r12+10h], r13d
0x18003a21f  mov     [r12+14h], ebx
0x18003a224  mov     qword ptr [r12+18h], 0
0x18003a22d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a232  test    rax, rax
0x18003a235  jz      loc_18003A6A8
0x18003a23b  mov     r13, [rbp+47h+var_C0]
0x18003a23f  mov     [rax+10h], r12
0x18003a243  lea     rdx, [r13+68h]
0x18003a247  mov     rcx, [rdx+8]
0x18003a24b  mov     [rax+8], rcx
0x18003a24f  mov     [rax], rdx
0x18003a252  mov     [rcx], rax
0x18003a255  mov     [rdx+8], rax
0x18003a259  inc     qword ptr [rdx+10h]
0x18003a25d  movups  xmm0, xmmword ptr [rdi+58h]
0x18003a261  mov     eax, cs:dword_1800B3200
0x18003a267  movdqu  [rbp+47h+var_B0], xmm0
0x18003a26c  cmp     eax, 4
0x18003a26f  jbe     short loc_18003A2E5
0x18003a271  lea     rax, [rbp+47h+var_B8]
0x18003a275  mov     [rbp+47h+var_B8], rsi
0x18003a279  mov     [rbp+47h+var_50], rax
0x18003a27d  lea     rdx, word_1800A835A; int
0x18003a284  lea     rax, [rbp+47h+var_C0]
0x18003a288  mov     dword ptr [rbp+47h+var_C0], ebx
0x18003a28b  mov     [rbp+47h+var_60], rax
0x18003a28f  lea     rcx, dword_1800B3200; int
0x18003a296  lea     rax, [rbp+47h+var_B0]
0x18003a29a  mov     [rbp+47h+var_48], 8
0x18003a2a2  mov     [rbp+47h+var_70], rax
0x18003a2a6  xor     r9d, r9d; int
0x18003a2a9  lea     rax, aPhonecontrolle_83; "PhoneController: Controller request to "...
0x18003a2b0  mov     [rbp+47h+var_58], 4
0x18003a2b8  mov     [rbp+47h+var_80], rax
0x18003a2bc  xor     r8d, r8d; int
0x18003a2bf  lea     rax, [rbp+47h+var_A0]
0x18003a2c3  mov     [rbp+47h+var_68], 10h
0x18003a2cb  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x18003a2d0  mov     [rsp+100h+var_E0], 6; ULONG
0x18003a2d8  mov     [rbp+47h+var_78], 30h ; '0'
0x18003a2e0  call    _tlgWriteTransfer_EventWriteTransfer
0x18003a2e5  mov     eax, 2000h
0x18003a2ea  cmp     ebx, eax
0x18003a2ec  jg      loc_18003A4FA
0x18003a2f2  jz      loc_18003A4E2
0x18003a2f8  cmp     ebx, 40h ; '@'
0x18003a2fb  jg      loc_18003A400
0x18003a301  jz      loc_18003A3ED
0x18003a307  sub     ebx, 1
0x18003a30a  jz      loc_18003A3B6
0x18003a310  sub     ebx, 1
0x18003a313  jz      loc_18003A39C
0x18003a319  sub     ebx, 2
0x18003a31c  jz      short loc_18003A375
0x18003a31e  sub     ebx, 4
0x18003a321  jz      short loc_18003A362
0x18003a323  sub     ebx, 8
0x18003a326  jz      short loc_18003A34F
0x18003a328  cmp     ebx, 10h
0x18003a32b  jnz     loc_18003A5FD
0x18003a331  lea     r8, [r15+0DCh]; unsigned int *
0x18003a338  mov     r9, rsi; unsigned __int64
0x18003a33b  lea     rdx, [r15+0D8h]; unsigned int *
0x18003a342  mov     rcx, rdi; this
0x18003a345  call    ?Swap@PhoneLine@@QEAAJAEBI0_K@Z; PhoneLine::Swap(uint const &,uint const &,unsigned __int64)
0x18003a34a  jmp     loc_18003A65A
0x18003a34f  mov     r8, rsi; unsigned __int64
0x18003a352  mov     rdx, r14; unsigned int *
0x18003a355  mov     rcx, rdi; this
0x18003a358  call    ?Unhold@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::Unhold(uint const &,unsigned __int64)
0x18003a35d  jmp     loc_18003A65A
0x18003a362  mov     r8, rsi; unsigned __int64
0x18003a365  mov     rdx, r14; unsigned int *
0x18003a368  mov     rcx, rdi; this
0x18003a36b  call    ?Hold@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::Hold(uint const &,unsigned __int64)
0x18003a370  jmp     loc_18003A65A
0x18003a375  mov     r9d, [r15+0ECh]
0x18003a37c  lea     r8, [r15+0E4h]
0x18003a383  lea     rdx, [r15+0E0h]
0x18003a38a  mov     qword ptr [rsp+100h+var_E0], rsi
0x18003a38f  mov     rcx, rdi
0x18003a392  call    ?DropActiveAcceptHeld@PhoneLine@@QEAAJAEBI0W4PhoneCallType@@_K@Z; PhoneLine::DropActiveAcceptHeld(uint const &,uint const &,PhoneCallType,unsigned __int64)
0x18003a397  jmp     loc_18003A65A
0x18003a39c  mov     r8d, [r15+0E8h]; int
0x18003a3a3  mov     r9, rsi; unsigned __int64
0x18003a3a6  mov     rdx, r14; unsigned int *
0x18003a3a9  mov     rcx, rdi; this
0x18003a3ac  call    ?End@PhoneLine@@QEAAJAEBIH_K@Z; PhoneLine::End(uint const &,int,unsigned __int64)
0x18003a3b1  jmp     loc_18003A65A
0x18003a3b6  mov     rax, [r15+90h]
0x18003a3bd  mov     rdx, r14
0x18003a3c0  mov     r9, [r15+70h]
0x18003a3c4  mov     rcx, rdi
0x18003a3c7  mov     r8d, [r15+0D4h]
0x18003a3ce  mov     [rsp+100h+var_D0], rsi
0x18003a3d3  mov     [rsp+100h+var_D8], rax
0x18003a3d8  mov     eax, [r15+0D0h]
0x18003a3df  mov     [rsp+100h+var_E0], eax
0x18003a3e3  call    ?Dial@PhoneLine@@QEAAJAEBIW4PhoneCallType@@PEBGW4CallerIdOption@@2_K@Z; PhoneLine::Dial(uint const &,PhoneCallType,ushort const *,CallerIdOption,ushort const *,unsigned __int64)
0x18003a3e8  jmp     loc_18003A65A
0x18003a3ed  mov     r8, rsi; unsigned __int64
0x18003a3f0  mov     rdx, r14; unsigned int *
0x18003a3f3  mov     rcx, rdi; this
0x18003a3f6  call    ?Private@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::Private(uint const &,unsigned __int64)
0x18003a3fb  jmp     loc_18003A65A
0x18003a400  cmp     ebx, 80h
0x18003a406  jz      loc_18003A4B1
0x18003a40c  cmp     ebx, 100h
0x18003a412  jz      loc_18003A4A7
0x18003a418  cmp     ebx, 200h
0x18003a41e  jz      short loc_18003A48D
0x18003a420  cmp     ebx, 400h
0x18003a426  jz      short loc_18003A46A
0x18003a428  cmp     ebx, 800h
0x18003a42e  jz      short loc_18003A454
0x18003a430  cmp     ebx, 1000h
0x18003a436  jnz     loc_18003A5FD
0x18003a43c  movzx   r8d, word ptr [r15+40h]; unsigned __int16
0x18003a441  mov     r9, rsi; unsigned __int64
0x18003a444  mov     rdx, r14; unsigned int *
0x18003a447  mov     rcx, rdi; this
0x18003a44a  call    ?StartDtmf@PhoneLine@@QEAAJAEBIG_K@Z; PhoneLine::StartDtmf(uint const &,ushort,unsigned __int64)
0x18003a44f  jmp     loc_18003A65A
0x18003a454  mov     r8, [r15]; unsigned __int16 *
0x18003a457  mov     r9, rsi; unsigned __int64
0x18003a45a  mov     rdx, r14; unsigned int *
0x18003a45d  mov     rcx, rdi; this
0x18003a460  call    ?SendDtmf@PhoneLine@@QEAAJAEBIPEBG_K@Z; PhoneLine::SendDtmf(uint const &,ushort const *,unsigned __int64)
0x18003a465  jmp     loc_18003A65A
0x18003a46a  mov     r8d, [r15+0ECh]
0x18003a471  lea     r9, [r15+0F0h]
0x18003a478  mov     rdx, r14
0x18003a47b  mov     qword ptr [rsp+100h+var_E0], rsi
0x18003a480  mov     rcx, rdi
0x18003a483  call    ?AcceptIncoming@PhoneLine@@QEAAJAEBIW4PhoneCallType@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_K@Z; PhoneLine::AcceptIncoming(uint const &,PhoneCallType,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,unsigned __int64)
0x18003a488  jmp     loc_18003A65A
0x18003a48d  mov     r8d, [r15+110h]
0x18003a494  mov     r9, rsi
0x18003a497  mov     rdx, r14
0x18003a49a  mov     rcx, rdi
0x18003a49d  call    ?RejectIncoming@PhoneLine@@QEAAJAEBIW4RejectIncomingReason@@_K@Z; PhoneLine::RejectIncoming(uint const &,RejectIncomingReason,unsigned __int64)
0x18003a4a2  jmp     loc_18003A65A
0x18003a4a7  mov     ebx, 80004002h
0x18003a4ac  jmp     loc_18003A66C
0x18003a4b1  test    r15, r15
0x18003a4b4  jnz     short loc_18003A4CA
0x18003a4b6  mov     r8d, 0D43h
0x18003a4bc  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003a4c3  call    Log_AssertionEvent_3
0x18003a4c8  int     2Ch; Windows NT - assertion failure
0x18003a4ca  lea     r8, [r15+6Ch]; unsigned int *
0x18003a4ce  mov     r9, rsi; unsigned __int64
0x18003a4d1  lea     rdx, [r15+68h]; unsigned int *
0x18003a4d5  mov     rcx, rdi; this
0x18003a4d8  call    ?Conference@PhoneLine@@QEAAJAEBI0_K@Z; PhoneLine::Conference(uint const &,uint const &,unsigned __int64)
0x18003a4dd  jmp     loc_18003A65A
0x18003a4e2  movzx   r8d, word ptr [r15+40h]; unsigned __int16
0x18003a4e7  mov     r9, rsi; unsigned __int64
0x18003a4ea  mov     rdx, r14; unsigned int *
0x18003a4ed  mov     rcx, rdi; this
0x18003a4f0  call    ?StopDtmf@PhoneLine@@QEAAJAEBIG_K@Z; PhoneLine::StopDtmf(uint const &,ushort,unsigned __int64)
0x18003a4f5  jmp     loc_18003A65A
0x18003a4fa  mov     eax, 200000h
0x18003a4ff  cmp     ebx, eax
0x18003a501  jg      loc_18003A5D1
0x18003a507  jz      loc_18003A5B7
0x18003a50d  cmp     ebx, 8000h
0x18003a513  jz      loc_18003A5A4
0x18003a519  cmp     ebx, 10000h
0x18003a51f  jz      short loc_18003A591
0x18003a521  cmp     ebx, 20000h
0x18003a527  jz      short loc_18003A57E
0x18003a529  cmp     ebx, 40000h
0x18003a52f  jz      short loc_18003A56B
0x18003a531  cmp     ebx, 80000h
0x18003a537  jz      short loc_18003A558
0x18003a539  cmp     ebx, 100000h
0x18003a53f  jnz     loc_18003A5FD
0x18003a545  mov     r8, rsi; unsigned __int64
0x18003a548  mov     rdx, r14; unsigned int *
0x18003a54b  mov     rcx, rdi; this
0x18003a54e  call    ?RejectVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::RejectVideo(uint const &,unsigned __int64)
0x18003a553  jmp     loc_18003A65A
0x18003a558  mov     r8, rsi; unsigned __int64
0x18003a55b  mov     rdx, r14; unsigned int *
0x18003a55e  mov     rcx, rdi; this
0x18003a561  call    ?AcceptVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::AcceptVideo(uint const &,unsigned __int64)
0x18003a566  jmp     loc_18003A65A
0x18003a56b  mov     r8, rsi; unsigned __int64
0x18003a56e  mov     rdx, r14; unsigned int *
0x18003a571  mov     rcx, rdi; this
0x18003a574  call    ?DropVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::DropVideo(uint const &,unsigned __int64)
0x18003a579  jmp     loc_18003A65A
0x18003a57e  mov     r8, rsi; unsigned __int64
0x18003a581  mov     rdx, r14; unsigned int *
0x18003a584  mov     rcx, rdi; this
0x18003a587  call    ?AddVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::AddVideo(uint const &,unsigned __int64)
0x18003a58c  jmp     loc_18003A65A
0x18003a591  mov     r8, rsi; unsigned __int64
0x18003a594  mov     rdx, r14; unsigned int *
0x18003a597  mov     rcx, rdi; this
0x18003a59a  call    ?EnableLocalVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::EnableLocalVideo(uint const &,unsigned __int64)
0x18003a59f  jmp     loc_18003A65A
0x18003a5a4  mov     r8, rsi; unsigned __int64
0x18003a5a7  mov     rdx, r14; unsigned int *
0x18003a5aa  mov     rcx, rdi; this
0x18003a5ad  call    ?DisableLocalVideo@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::DisableLocalVideo(uint const &,unsigned __int64)
0x18003a5b2  jmp     loc_18003A65A
0x18003a5b7  mov     r8d, [r15+114h]; int
0x18003a5be  mov     r9, rsi; unsigned __int64
0x18003a5c1  mov     rdx, r14; unsigned int *
0x18003a5c4  mov     rcx, rdi; this
0x18003a5c7  call    ?SetVideoPaused@PhoneLine@@QEAAJAEBIH_K@Z; PhoneLine::SetVideoPaused(uint const &,int,unsigned __int64)
0x18003a5cc  jmp     loc_18003A65A
0x18003a5d1  cmp     ebx, 2000000h
0x18003a5d7  jz      loc_18003A667
0x18003a5dd  cmp     ebx, 4000000h
0x18003a5e3  jz      short loc_18003A648
0x18003a5e5  cmp     ebx, 8000000h
0x18003a5eb  jz      short loc_18003A638
0x18003a5ed  cmp     ebx, 10000000h
0x18003a5f3  jz      short loc_18003A628
0x18003a5f5  cmp     ebx, 20000000h
0x18003a5fb  jz      short loc_18003A618
0x18003a5fd  mov     r8d, 0DB1h
0x18003a603  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003a60a  call    Log_AssertionEvent_3
0x18003a60f  int     2Ch; Windows NT - assertion failure
0x18003a611  mov     ebx, 80004005h
0x18003a616  jmp     short loc_18003A66C
0x18003a618  mov     r8, rsi; unsigned __int64
0x18003a61b  mov     rdx, r14; unsigned int *
0x18003a61e  mov     rcx, rdi; this
0x18003a621  call    ?DowngradeFromRealTimeTextCall@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::DowngradeFromRealTimeTextCall(uint const &,unsigned __int64)
0x18003a626  jmp     short loc_18003A65A
0x18003a628  mov     r8, rsi; unsigned __int64
0x18003a62b  mov     rdx, r14; unsigned int *
0x18003a62e  mov     rcx, rdi; this
0x18003a631  call    ?UpgradeToRealTimeTextCall@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::UpgradeToRealTimeTextCall(uint const &,unsigned __int64)
0x18003a636  jmp     short loc_18003A65A
0x18003a638  mov     r8, rsi; unsigned __int64
0x18003a63b  mov     rdx, r14; unsigned int *
0x18003a63e  mov     rcx, rdi; this
0x18003a641  call    ?AcceptUpgradingRealTimeTextCall@PhoneLine@@QEAAJAEBI_K@Z; PhoneLine::AcceptUpgradingRealTimeTextCall(uint const &,unsigned __int64)
0x18003a646  jmp     short loc_18003A65A
0x18003a648  mov     r8, [r15+20h]; unsigned __int16 *
0x18003a64c  mov     r9, rsi; unsigned __int64
0x18003a64f  mov     rdx, r14; unsigned int *
0x18003a652  mov     rcx, rdi; this
  ... truncated ...
```
