# CDlpTask::ExecuteActionsThreadProc(void *)

- ea: `0x140037a80`
- end: `0x1400380f8`
- name: `?ExecuteActionsThreadProc@CDlpTask@@SAKPEAX@Z`
- size: `1656`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002dc58`
- `0x140034ab4`
- `0x1400369c8`
- `0x140037a80`
- `0x140038e64`
- `0x14003c3c4`
- `0x140043b2c`
- `0x14004c2b0`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037c81`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037cc9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037de2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037eaa`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037c81`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037cc9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037de2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140037eaa`

## string_xrefs

- `0x140037d57`: `CDlpTask::ReportDiagTime`
- `0x140037e63`: `CDlpTask::ReportDiagTime`
- `0x140037f36`: `CDlpTask::ReportDiagTime`

## pseudocode

```c
__int64 __fastcall CDlpTask::ExecuteActionsThreadProc(_QWORD *Parameter)
{
  _QWORD *v2; // rbx
  int v3; // edi
  int NextActionIndex; // eax
  unsigned int v5; // r14d
  int v6; // eax
  __int64 v7; // rax
  char *v8; // r14
  __int64 v9; // rax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // r15d
  __int64 v14; // rax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r15d
  __int64 v18; // rax
  unsigned int v19; // ebx
  int v20; // eax
  enum WINDLP_INTERRUPT_REASON *v21; // rdx
  enum WINDLP_INTERRUPT_REASON *v22; // r8
  int v23; // ecx
  __int64 v25; // [rsp+28h] [rbp-59h]
  __int64 v26; // [rsp+28h] [rbp-59h]
  __int64 v27; // [rsp+28h] [rbp-59h]
  __int64 v28; // [rsp+30h] [rbp-51h]
  __int64 v29; // [rsp+30h] [rbp-51h]
  __int64 v30; // [rsp+30h] [rbp-51h]
  int v31; // [rsp+48h] [rbp-39h] BYREF
  struct IDlpAction *v32; // [rsp+50h] [rbp-31h] BYREF
  int v33; // [rsp+58h] [rbp-29h] BYREF
  unsigned int v34; // [rsp+5Ch] [rbp-25h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-21h] BYREF
  struct _FILETIME v36[2]; // [rsp+68h] [rbp-19h] BYREF
  int v37; // [rsp+78h] [rbp-9h] BYREF
  struct _FILETIME v38; // [rsp+80h] [rbp-1h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+7h] BYREF
  union _ULARGE_INTEGER v40; // [rsp+90h] [rbp+Fh]
  struct _FILETIME v41; // [rsp+98h] [rbp+17h] BYREF
  struct _FILETIME v42; // [rsp+A0h] [rbp+1Fh] BYREF
  __int128 v43; // [rsp+A8h] [rbp+27h] BYREF

  v32 = 0;
  v31 = 0;
  v2 = 0;
  v35 = 0;
  v34 = 0;
  v40.QuadPart = 0;
  SystemTimeAsFileTime = 0;
  v37 = 0;
  v33 = 0;
  v43 = 0;
  if ( !Parameter )
  {
    v3 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024809);
    goto LABEL_66;
  }
  (*(void (__fastcall **)(_QWORD *))(*Parameter + 8LL))(Parameter);
  NextActionIndex = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *))(*Parameter + 144LL))(Parameter, &v35);
  v3 = NextActionIndex;
  if ( NextActionIndex < 0
    || (NextActionIndex = CDlpState::Get((CDlpState *)(Parameter + 109), (enum WINDLP_STATE *)&v34),
        v3 = NextActionIndex,
        NextActionIndex < 0) )
  {
LABEL_63:
    v23 = NextActionIndex;
LABEL_64:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
LABEL_65:
    v2 = Parameter;
  }
  else
  {
    v5 = v34;
    v2 = Parameter;
    if ( v34 < v35 )
    {
      while ( 1 )
      {
        if ( v32 )
        {
          (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v32 + 16LL))(v32);
          v32 = 0;
        }
        NextActionIndex = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, struct IDlpAction **))(*Parameter + 120LL))(
                            Parameter,
                            v5,
                            &v32);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        NextActionIndex = (*(__int64 (__fastcall **)(struct IDlpAction *, __int128 *))(*(_QWORD *)v32 + 56LL))(
                            v32,
                            &v43);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        NextActionIndex = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v32 + 24LL))(v32, &v31);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        v6 = v31;
        if ( v31 == -21037378 )
        {
          NextActionIndex = (*(__int64 (__fastcall **)(char *, __int64, struct IDlpAction *))(Parameter[2] + 24LL))(
                              (char *)Parameter + 16,
                              131073,
                              v32);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          NextActionIndex = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)Parameter[163] + 280LL))(
                              Parameter[163],
                              0);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          NextActionIndex = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v32 + 24LL))(v32, &v31);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          v6 = v31;
          if ( v31 == -21037378 )
          {
            v3 = -1048575721;
LABEL_61:
            v23 = v3;
            goto LABEL_64;
          }
        }
        if ( v6 )
        {
          if ( v6 == 6 )
            goto LABEL_57;
          if ( v6 != 4 )
            goto LABEL_62;
        }
        NextActionIndex = CDlpTask::NotifyActionStateChanged((CDlpTask *)Parameter, &v33);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        if ( v33 )
          goto LABEL_50;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v40 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
        v7 = Parameter[148];
        if ( !v7 )
          v7 = 0;
        NextActionIndex = CULargeInteger::Set(
                            *(CULargeInteger **)(v7 + 8LL * (int)v5),
                            (union _ULARGE_INTEGER)SystemTimeAsFileTime);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        v36[0] = 0;
        GetSystemTimeAsFileTime(v36);
        v8 = (char *)(Parameter + 2);
        v41 = v36[0];
        Parameter[184] = v36[0];
        v3 = (*(__int64 (__fastcall **)(char *, __int64, __int64, struct _FILETIME *, __int128 *, _DWORD))Parameter[2])(
               (char *)Parameter + 16,
               8194,
               1,
               &v41,
               &v43,
               0);
        if ( v3 < 0 && (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176) )
        {
          v9 = (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176);
          v10 = 0;
          if ( v9 )
          {
            LODWORD(v28) = v3;
            LODWORD(v25) = 4061;
            v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v9,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpTask::ReportDiagTime",
                    v25,
                    v28);
            v10 = v11;
            if ( v11 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
        if ( v3 < 0 )
          goto LABEL_61;
        NextActionIndex = (*(__int64 (__fastcall **)(char *, __int64, struct IDlpAction *))(*(_QWORD *)v8 + 24LL))(
                            (char *)Parameter + 16,
                            131074,
                            v32);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        *(_OWORD *)&v36[0].dwLowDateTime = v43;
        v12 = CDlpTask::ExecuteAction((CDlpTask *)Parameter, v32, (struct _GUID *)v36);
        v36[0] = 0;
        v3 = v12;
        GetSystemTimeAsFileTime(v36);
        v42 = v36[0];
        v13 = (**(__int64 (__fastcall ***)(char *, __int64, __int64, struct _FILETIME *, __int128 *, _DWORD))v8)(
                (char *)Parameter + 16,
                8195,
                1,
                &v42,
                &v43,
                0);
        if ( v13 < 0 && (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176) )
        {
          v14 = (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176);
          v15 = 0;
          if ( v14 )
          {
            LODWORD(v29) = v13;
            LODWORD(v26) = 4070;
            v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v14,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpTask::ReportDiagTime",
                    v26,
                    v29);
            v15 = v16;
            if ( v16 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
        v36[0] = 0;
        GetSystemTimeAsFileTime(v36);
        v38 = v36[0];
        v38 = (struct _FILETIME)(*(_QWORD *)v36 - Parameter[184]);
        v17 = (**(__int64 (__fastcall ***)(char *, __int64, __int64, struct _FILETIME *, __int128 *, _DWORD))v8)(
                (char *)Parameter + 16,
                8193,
                1,
                &v38,
                &v43,
                0);
        if ( v17 < 0 && (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176) )
        {
          v18 = (*(__int64 (__fastcall **)(char *))(Parameter[22] + 16LL))((char *)Parameter + 176);
          v19 = 0;
          if ( v18 )
          {
            LODWORD(v30) = v17;
            LODWORD(v27) = 4090;
            v20 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v18,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpTask::ReportDiagTime",
                    v27,
                    v30);
            v19 = v20;
            if ( v20 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v17);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)Parameter[163] + 280LL))(Parameter[163], 0);
        if ( v3 < 0 )
          goto LABEL_61;
        NextActionIndex = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)v32 + 24LL))(v32, &v31);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        if ( v31 == 4 )
        {
          NextActionIndex = (*(__int64 (__fastcall **)(char *, __int64, struct IDlpAction *))(*(_QWORD *)v8 + 24LL))(
                              (char *)Parameter + 16,
                              131075,
                              v32);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          NextActionIndex = CDlpState::Get((CDlpState *)(Parameter + 155), (enum WINDLP_STATE *)&v37);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          if ( v37 == -1 )
          {
LABEL_50:
            v3 = 0;
            goto LABEL_65;
          }
        }
        else
        {
          if ( v31 != 6 )
          {
LABEL_62:
            v23 = -2147019873;
            v3 = -2147019873;
            goto LABEL_64;
          }
          NextActionIndex = (*(__int64 (__fastcall **)(char *, __int64, struct IDlpAction *))(*(_QWORD *)v8 + 24LL))(
                              (char *)Parameter + 16,
                              131077,
                              v32);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          if ( *((_DWORD *)Parameter + 353) )
            goto LABEL_50;
          NextActionIndex = CDlpTask::NotifyActionStateChanged((CDlpTask *)Parameter, &v33);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
          if ( v33 )
            goto LABEL_50;
          NextActionIndex = CDlpTask::CheckUserInterrupt((CDlpTask *)Parameter, v21, v22);
          v3 = NextActionIndex;
          if ( NextActionIndex < 0 )
            goto LABEL_63;
        }
LABEL_57:
        NextActionIndex = CDlpTask::GetNextActionIndex((CDlpTask *)Parameter, &v34);
        v3 = NextActionIndex;
        if ( NextActionIndex < 0 )
          goto LABEL_63;
        v5 = v34;
        if ( v34 >= v35 )
          goto LABEL_65;
      }
    }
  }
LABEL_66:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  if ( v32 )
  {
    (*(void (__fastcall **)(struct IDlpAction *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v2 )
    (*(void (__fastcall **)(_QWORD *))(*v2 + 16LL))(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140037a80  mov     rax, rsp
0x140037a83  mov     [rax+8], rbx
0x140037a87  mov     [rax+10h], rsi
0x140037a8b  mov     [rax+18h], rdi
0x140037a8f  mov     [rax+20h], r12
0x140037a93  push    rbp
0x140037a94  push    r14
0x140037a96  push    r15
0x140037a98  lea     rbp, [rax-5Fh]
0x140037a9c  sub     rsp, 0C0h
0x140037aa3  mov     rax, cs:__security_cookie
0x140037aaa  xor     rax, rsp
0x140037aad  mov     [rbp+57h+var_20], rax
0x140037ab1  xor     r12d, r12d
0x140037ab4  xorps   xmm0, xmm0
0x140037ab7  mov     [rbp+57h+var_88], r12
0x140037abb  mov     rsi, rcx
0x140037abe  mov     [rbp+57h+var_90], r12d
0x140037ac2  mov     ebx, r12d
0x140037ac5  mov     [rbp+57h+var_78], r12d
0x140037ac9  mov     [rbp+57h+var_7C], r12d
0x140037acd  mov     qword ptr [rbp+57h+var_48], r12
0x140037ad1  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x140037ad5  mov     [rbp+57h+var_60], r12d
0x140037ad9  mov     [rbp+57h+var_80], r12d
0x140037add  movups  [rbp+57h+var_30], xmm0
0x140037ae1  test    rcx, rcx
0x140037ae4  jnz     short loc_140037AF7
0x140037ae6  mov     edi, 80070057h
0x140037aeb  mov     ecx, edi
0x140037aed  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140037af2  jmp     loc_140038094
0x140037af7  mov     rax, [rcx]
0x140037afa  mov     rax, [rax+8]
0x140037afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b03  mov     rax, [rsi]
0x140037b06  lea     rdx, [rbp+57h+var_78]
0x140037b0a  mov     rcx, rsi
0x140037b0d  mov     rax, [rax+90h]
0x140037b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b19  mov     edi, eax
0x140037b1b  test    eax, eax
0x140037b1d  js      loc_14003808A
0x140037b23  lea     rcx, [rsi+368h]; this
0x140037b2a  lea     rdx, [rbp+57h+var_7C]; enum WINDLP_STATE *
0x140037b2e  call    ?Get@CDlpState@@QEAAJPEAW4WINDLP_STATE@@@Z; CDlpState::Get(WINDLP_STATE *)
0x140037b33  mov     edi, eax
0x140037b35  test    eax, eax
0x140037b37  js      loc_14003808A
0x140037b3d  mov     r14d, [rbp+57h+var_7C]
0x140037b41  mov     rbx, rsi
0x140037b44  cmp     r14d, [rbp+57h+var_78]
0x140037b48  jnb     loc_140038094
0x140037b4e  mov     rcx, [rbp+57h+var_88]
0x140037b52  test    rcx, rcx
0x140037b55  jz      short loc_140037B67
0x140037b57  mov     rax, [rcx]
0x140037b5a  mov     rax, [rax+10h]
0x140037b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b63  mov     [rbp+57h+var_88], r12
0x140037b67  mov     rax, [rsi]
0x140037b6a  lea     r8, [rbp+57h+var_88]
0x140037b6e  mov     edx, r14d
0x140037b71  mov     rcx, rsi
0x140037b74  mov     rax, [rax+78h]
0x140037b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b7d  mov     edi, eax
0x140037b7f  test    eax, eax
0x140037b81  js      loc_14003808A
0x140037b87  mov     rcx, [rbp+57h+var_88]
0x140037b8b  lea     rdx, [rbp+57h+var_30]
0x140037b8f  mov     rax, [rcx]
0x140037b92  mov     rax, [rax+38h]
0x140037b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037b9b  mov     edi, eax
0x140037b9d  test    eax, eax
0x140037b9f  js      loc_14003808A
0x140037ba5  mov     rcx, [rbp+57h+var_88]
0x140037ba9  lea     rdx, [rbp+57h+var_90]
0x140037bad  mov     rax, [rcx]
0x140037bb0  mov     rax, [rax+18h]
0x140037bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037bb9  mov     edi, eax
0x140037bbb  test    eax, eax
0x140037bbd  js      loc_14003808A
0x140037bc3  mov     eax, [rbp+57h+var_90]
0x140037bc6  cmp     eax, 0FEBEFEBEh
0x140037bcb  jnz     short loc_140037C3E
0x140037bcd  mov     r8, [rbp+57h+var_88]
0x140037bd1  lea     rcx, [rsi+10h]
0x140037bd5  mov     rax, [rcx]
0x140037bd8  mov     edx, 20001h
0x140037bdd  mov     rax, [rax+18h]
0x140037be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037be6  mov     edi, eax
0x140037be8  test    eax, eax
0x140037bea  js      loc_14003808A
0x140037bf0  mov     rcx, [rsi+518h]
0x140037bf7  xor     edx, edx
0x140037bf9  mov     rax, [rcx]
0x140037bfc  mov     rax, [rax+118h]
0x140037c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037c08  mov     edi, eax
0x140037c0a  test    eax, eax
0x140037c0c  js      loc_14003808A
0x140037c12  mov     rcx, [rbp+57h+var_88]
0x140037c16  lea     rdx, [rbp+57h+var_90]
0x140037c1a  mov     rax, [rcx]
0x140037c1d  mov     rax, [rax+18h]
0x140037c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037c26  mov     edi, eax
0x140037c28  test    eax, eax
0x140037c2a  js      loc_14003808A
0x140037c30  mov     eax, [rbp+57h+var_90]
0x140037c33  cmp     eax, 0FEBEFEBEh
0x140037c38  jz      loc_140038078
0x140037c3e  test    eax, eax
0x140037c40  jz      short loc_140037C54
0x140037c42  cmp     eax, 6
0x140037c45  jz      loc_140038056
0x140037c4b  cmp     eax, 4
0x140037c4e  jnz     loc_140038081
0x140037c54  cmp     eax, 6
0x140037c57  jz      loc_140038056
0x140037c5d  lea     rdx, [rbp+57h+var_80]; int *
0x140037c61  mov     rcx, rsi; this
0x140037c64  call    ?NotifyActionStateChanged@CDlpTask@@AEAAJPEAH@Z; CDlpTask::NotifyActionStateChanged(int *)
0x140037c69  mov     edi, eax
0x140037c6b  test    eax, eax
0x140037c6d  js      loc_14003808A
0x140037c73  cmp     [rbp+57h+var_80], r12d
0x140037c77  jnz     loc_140037FFB
0x140037c7d  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140037c81  call    cs:__imp_GetSystemTimeAsFileTime
0x140037c88  nop     dword ptr [rax+rax+00h]
0x140037c8d  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwHighDateTime]
0x140037c90  mov     dword ptr [rbp+57h+var_48+4], eax
0x140037c93  mov     eax, [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140037c96  mov     dword ptr [rbp+57h+var_48], eax
0x140037c99  mov     rax, [rsi+4A0h]
0x140037ca0  mov     rdx, qword ptr [rbp+57h+var_48]; union _ULARGE_INTEGER
0x140037ca4  test    rax, rax
0x140037ca7  movsxd  rcx, r14d
0x140037caa  cmovz   rax, r12
0x140037cae  mov     rcx, [rax+rcx*8]; this
0x140037cb2  call    ?Set@CULargeInteger@@QEAAJT_ULARGE_INTEGER@@@Z; CULargeInteger::Set(_ULARGE_INTEGER)
0x140037cb7  mov     edi, eax
0x140037cb9  test    eax, eax
0x140037cbb  js      loc_14003808A
0x140037cc1  lea     rcx, [rbp+57h+var_70]; lpSystemTimeAsFileTime
0x140037cc5  mov     qword ptr [rbp+57h+var_70.dwLowDateTime], r12
0x140037cc9  call    cs:__imp_GetSystemTimeAsFileTime
0x140037cd0  nop     dword ptr [rax+rax+00h]
0x140037cd5  mov     eax, [rbp+57h+var_70.dwHighDateTime]
0x140037cd8  lea     r14, [rsi+10h]
0x140037cdc  mov     dword ptr [rbp+57h+var_40+4], eax
0x140037cdf  lea     rcx, [rbp+57h+var_30]
0x140037ce3  mov     eax, [rbp+57h+var_70.dwLowDateTime]
0x140037ce6  lea     r9, [rbp+57h+var_40]
0x140037cea  mov     dword ptr [rbp+57h+var_40], eax
0x140037ced  mov     edx, 2002h
0x140037cf2  mov     rax, [rbp+57h+var_40]
0x140037cf6  mov     r8d, 1
0x140037cfc  mov     [rsi+5C0h], rax
0x140037d03  mov     rax, [r14]
0x140037d06  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x140037d0b  mov     [rsp+0D0h+var_B0], rcx
0x140037d10  mov     rcx, r14
0x140037d13  mov     rax, [rax]
0x140037d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d1b  mov     edi, eax
0x140037d1d  test    eax, eax
0x140037d1f  jns     short loc_140037D8E
0x140037d21  lea     rbx, [rsi+0B0h]
0x140037d28  mov     rax, [rbx]
0x140037d2b  mov     rcx, rbx
0x140037d2e  mov     rax, [rax+10h]
0x140037d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d37  test    rax, rax
0x140037d3a  jz      short loc_140037D8E
0x140037d3c  mov     rax, [rbx]
0x140037d3f  mov     rcx, rbx
0x140037d42  mov     rax, [rax+10h]
0x140037d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d4b  mov     ebx, r12d
0x140037d4e  test    rax, rax
0x140037d51  jz      short loc_140037D87
0x140037d53  mov     dword ptr [rsp+0D0h+var_A8], edi
0x140037d57  lea     r9, aCdlptaskReport_0; "CDlpTask::ReportDiagTime"
0x140037d5e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140037d65  mov     dword ptr [rsp+0D0h+var_B0], 0FDDh
0x140037d6d  mov     edx, 4
0x140037d72  mov     rcx, rax
0x140037d75  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140037d7a  mov     ebx, eax
0x140037d7c  test    eax, eax
0x140037d7e  jns     short loc_140037D87
0x140037d80  mov     ecx, eax
0x140037d82  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140037d87  mov     ecx, ebx
0x140037d89  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140037d8e  mov     ecx, edi
0x140037d90  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140037d95  test    edi, edi
0x140037d97  js      loc_14003807D
0x140037d9d  mov     rax, [r14]
0x140037da0  mov     edx, 20002h
0x140037da5  mov     r8, [rbp+57h+var_88]
0x140037da9  mov     rcx, r14
0x140037dac  mov     rax, [rax+18h]
0x140037db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037db5  mov     edi, eax
0x140037db7  test    eax, eax
0x140037db9  js      loc_14003808A
0x140037dbf  movaps  xmm0, [rbp+57h+var_30]
0x140037dc3  lea     r8, [rbp+57h+var_70]; struct _GUID
0x140037dc7  mov     rdx, [rbp+57h+var_88]; struct IDlpAction *
0x140037dcb  mov     rcx, rsi; this
0x140037dce  movdqa  xmmword ptr [rbp+57h+var_70.dwLowDateTime], xmm0
0x140037dd3  call    ?ExecuteAction@CDlpTask@@AEAAJPEAVIDlpAction@@U_GUID@@@Z; CDlpTask::ExecuteAction(IDlpAction *,_GUID)
0x140037dd8  lea     rcx, [rbp+57h+var_70]; lpSystemTimeAsFileTime
0x140037ddc  mov     qword ptr [rbp+57h+var_70.dwLowDateTime], r12
0x140037de0  mov     edi, eax
0x140037de2  call    cs:__imp_GetSystemTimeAsFileTime
0x140037de9  nop     dword ptr [rax+rax+00h]
0x140037dee  mov     eax, [rbp+57h+var_70.dwHighDateTime]
0x140037df1  lea     rcx, [rbp+57h+var_30]
0x140037df5  mov     dword ptr [rbp+57h+var_38+4], eax
0x140037df8  lea     r9, [rbp+57h+var_38]
0x140037dfc  mov     eax, [rbp+57h+var_70.dwLowDateTime]
0x140037dff  mov     edx, 2003h
0x140037e04  mov     dword ptr [rbp+57h+var_38], eax
0x140037e07  mov     r8d, 1
0x140037e0d  mov     rax, [r14]
0x140037e10  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x140037e15  mov     [rsp+0D0h+var_B0], rcx
0x140037e1a  mov     rcx, r14
0x140037e1d  mov     rax, [rax]
0x140037e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e25  mov     r15d, eax
0x140037e28  test    eax, eax
0x140037e2a  jns     short loc_140037E9A
0x140037e2c  lea     rbx, [rsi+0B0h]
0x140037e33  mov     rdx, [rbx]
0x140037e36  mov     rcx, rbx
0x140037e39  mov     rax, [rdx+10h]
0x140037e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e42  test    rax, rax
0x140037e45  jz      short loc_140037E9A
0x140037e47  mov     rax, [rbx]
0x140037e4a  mov     rcx, rbx
0x140037e4d  mov     rax, [rax+10h]
0x140037e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037e56  mov     ebx, r12d
0x140037e59  test    rax, rax
0x140037e5c  jz      short loc_140037E93
0x140037e5e  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x140037e63  lea     r9, aCdlptaskReport_0; "CDlpTask::ReportDiagTime"
0x140037e6a  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140037e71  mov     dword ptr [rsp+0D0h+var_B0], 0FE6h
0x140037e79  mov     edx, 4
0x140037e7e  mov     rcx, rax
0x140037e81  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140037e86  mov     ebx, eax
0x140037e88  test    eax, eax
0x140037e8a  jns     short loc_140037E93
0x140037e8c  mov     ecx, eax
0x140037e8e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140037e93  mov     ecx, ebx
0x140037e95  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140037e9a  mov     ecx, r15d
0x140037e9d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140037ea2  lea     rcx, [rbp+57h+var_70]; lpSystemTimeAsFileTime
0x140037ea6  mov     qword ptr [rbp+57h+var_70.dwLowDateTime], r12
0x140037eaa  call    cs:__imp_GetSystemTimeAsFileTime
0x140037eb1  nop     dword ptr [rax+rax+00h]
0x140037eb6  mov     eax, [rbp+57h+var_70.dwHighDateTime]
0x140037eb9  lea     rcx, [rbp+57h+var_30]
0x140037ebd  mov     dword ptr [rbp+57h+var_58+4], eax
0x140037ec0  lea     r9, [rbp+57h+var_58]
0x140037ec4  mov     eax, [rbp+57h+var_70.dwLowDateTime]
0x140037ec7  mov     edx, 2001h
0x140037ecc  mov     dword ptr [rbp+57h+var_58], eax
0x140037ecf  mov     r8d, 1
0x140037ed5  mov     rax, [rsi+5C0h]
0x140037edc  sub     [rbp+57h+var_58], rax
0x140037ee0  mov     rax, [r14]
0x140037ee3  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x140037ee8  mov     [rsp+0D0h+var_B0], rcx
0x140037eed  mov     rcx, r14
0x140037ef0  mov     rax, [rax]
0x140037ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ef8  mov     r15d, eax
0x140037efb  test    eax, eax
0x140037efd  jns     short loc_140037F6D
0x140037eff  lea     rbx, [rsi+0B0h]
0x140037f06  mov     rdx, [rbx]
0x140037f09  mov     rcx, rbx
0x140037f0c  mov     rax, [rdx+10h]
0x140037f10  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
