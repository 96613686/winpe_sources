# CDlpTask::ResetActionProgress(IDlpAction *)

- ea: `0x1400477d0`
- end: `0x140047e30`
- name: `?ResetActionProgress@CDlpTask@@UEAAJPEAVIDlpAction@@@Z`
- size: `1632`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002db30`
- `0x140034ab4`
- `0x140038e64`
- `0x140043b2c`
- `0x1400477d0`
- `0x14004c214`
- `0x14004c2b0`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140047d28`
- `KERNEL32!GetTickCount` at `0x140047d28`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140047c3a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140047c3a`
- `KERNEL32!LeaveCriticalSection` at `0x140047d72`
- `KERNEL32!LeaveCriticalSection` at `0x140047e0d`
- `KERNEL32!LeaveCriticalSection` at `0x140047d72`
- `KERNEL32!LeaveCriticalSection` at `0x140047e0d`
- `KERNEL32!EnterCriticalSection` at `0x140047800`
- `KERNEL32!EnterCriticalSection` at `0x140047800`

## string_xrefs

- `0x140047dc8`: `CDlpTask::ResetActionProgress`
- `0x14004792b`: `DlpTask: Skipping action progress reset due to task cancellation request.`
- `0x140047a56`: `DlpTask: Skipping action progress reset due to action cancellation request.`
- `0x140047bb4`: `DlpTask: Resetting action [%d] progress start time.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::ResetActionProgress(CDlpTask *this, struct IDlpAction *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // edi
  __int64 v6; // rax
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 LowPart; // r12
  char *v12; // rsi
  __int64 (__fastcall *v13)(char *); // rax
  bool v14; // zf
  char *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  union _ULARGE_INTEGER v19; // rcx
  ULONGLONG v20; // rax
  int v21; // eax
  int v23; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+28h] [rbp-50h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v26[4]; // [rsp+38h] [rbp-40h] BYREF
  int v27; // [rsp+58h] [rbp-20h]
  int v28; // [rsp+C0h] [rbp+48h] BYREF
  union _ULARGE_INTEGER v29; // [rsp+C8h] [rbp+50h] BYREF
  struct _RTL_CRITICAL_SECTION *v30; // [rsp+D0h] [rbp+58h]
  union _ULARGE_INTEGER v31; // [rsp+D8h] [rbp+60h] BYREF

  v26[1] = -2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 752);
  v30 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 752);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  v27 = 1;
  v28 = 0;
  v29.LowPart = 0;
  SystemTimeAsFileTime = 0;
  v31.QuadPart = 0;
  v26[0] = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = -2147024809;
    v23 = 2453;
    goto LABEL_65;
  }
  v5 = CDlpTask::CheckInitialized((CDlpTask *)((char *)this - 16), (enum WINDLP_STATE *)&v28);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = v5;
    v23 = 2457;
    goto LABEL_65;
  }
  if ( v28 == -1073741824 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
    {
      v8 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v8,
        3,
        L"DlpTask: Skipping action progress reset due to task cancellation request.");
    }
LABEL_12:
    v5 = 0;
    goto LABEL_69;
  }
  if ( (unsigned int)(v28 - 3) > 2 )
  {
    v5 = -2147019873;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = -2147019873;
    v23 = 2471;
    goto LABEL_65;
  }
  v5 = (*(__int64 (__fastcall **)(struct IDlpAction *, int *))(*(_QWORD *)a2 + 24LL))(a2, &v28);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = v5;
    v23 = 2475;
    goto LABEL_65;
  }
  if ( v28 == -1073741824 )
  {
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
    {
      v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v9,
        3,
        L"DlpTask: Skipping action progress reset due to action cancellation request.");
    }
    goto LABEL_12;
  }
  if ( (unsigned int)(v28 - 3) > 2 )
  {
    v5 = -2147019873;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = -2147019873;
    v23 = 2489;
    goto LABEL_65;
  }
  v5 = CDlpState::Get((CDlpTask *)((char *)this + 856), (enum WINDLP_STATE *)&v29);
  if ( v5 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160) )
      goto LABEL_69;
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL))((char *)this + 160);
    v7 = 0;
    if ( !v6 )
      goto LABEL_67;
    v24 = v5;
    v23 = 2493;
    goto LABEL_65;
  }
  v10 = *((_QWORD *)this + 46);
  if ( !v10 )
    v10 = 0;
  LowPart = (int)v29.LowPart;
  v12 = (char *)this + 160;
  v13 = *(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 20) + 16LL);
  v14 = a2 == *(struct IDlpAction **)(v10 + 8LL * (int)v29.LowPart);
  v15 = (char *)this + 160;
  if ( v14 )
  {
    if ( v13(v15) )
    {
      v16 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
      CDlpLogT<CEmptyType>::DlpLogFormat(v16, 2, L"DlpTask: Resetting action [%d] progress start time.", v29.LowPart);
    }
    v5 = (*(__int64 (__fastcall **)(struct IDlpAction *, _QWORD *, union _ULARGE_INTEGER *, _QWORD))(*(_QWORD *)a2 + 72LL))(
           a2,
           v26,
           &v31,
           0);
    if ( v5 >= 0 )
    {
      *((union _ULARGE_INTEGER *)this + 179) = v31;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v29 = (union _ULARGE_INTEGER)SystemTimeAsFileTime;
      v17 = *((_QWORD *)this + 146);
      if ( !v17 )
        v17 = 0;
      v5 = CULargeInteger::Set(*(CULargeInteger **)(v17 + 8 * LowPart), v29);
      if ( v5 >= 0 )
      {
        v18 = CProgressData::Set((CDlpTask *)((char *)this + 920), v29, v31, 0);
        v5 = v18;
        if ( v18 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
        if ( v5 >= 0 )
        {
          *((_DWORD *)this + 357) = GetTickCount();
          v19 = v31;
          if ( v26[0] )
            v20 = 100 * v31.QuadPart / v26[0];
          else
            v20 = 0;
          *((_QWORD *)this + 181) = v20;
          *((union _ULARGE_INTEGER *)this + 180) = v19;
          if ( v27 )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
            v27 = 0;
          }
          v5 = CDlpTask::NotifyActionStateChanged((CDlpTask *)((char *)this - 16), 0);
          if ( v5 >= 0 || !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
            goto LABEL_68;
          v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
          v7 = 0;
          if ( !v6 )
            goto LABEL_67;
          v24 = v5;
          v23 = 2523;
          goto LABEL_65;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
          goto LABEL_68;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        v7 = 0;
        if ( !v6 )
          goto LABEL_67;
        v24 = v5;
        v23 = 2512;
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
          goto LABEL_68;
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
        v7 = 0;
        if ( !v6 )
          goto LABEL_67;
        v24 = v5;
        v23 = 2511;
      }
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160) )
        goto LABEL_68;
      v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
      v7 = 0;
      if ( !v6 )
        goto LABEL_67;
      v24 = v5;
      v23 = 2504;
    }
LABEL_65:
    v21 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v6,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::ResetActionProgress",
            v23,
            v24);
    v7 = v21;
    if ( v21 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v21);
    goto LABEL_67;
  }
  v5 = -2147024883;
  if ( v13(v15) )
  {
    v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))((char *)this + 160);
    v7 = 0;
    if ( v6 )
    {
      v24 = -2147024883;
      v23 = 2498;
      goto LABEL_65;
    }
LABEL_67:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  }
LABEL_68:
  v4 = v30;
LABEL_69:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v27 )
  {
    LeaveCriticalSection(v4);
    v27 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400477d0  push    rbp
0x1400477d2  push    rbx
0x1400477d3  push    rsi
0x1400477d4  push    rdi
0x1400477d5  push    r12
0x1400477d7  push    r13
0x1400477d9  push    r14
0x1400477db  push    r15
0x1400477dd  mov     rbp, rsp
0x1400477e0  sub     rsp, 78h
0x1400477e4  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x1400477ec  mov     r15, rdx
0x1400477ef  mov     r14, rcx
0x1400477f2  lea     rsi, [rcx+2F0h]
0x1400477f9  mov     [rbp+arg_10], rsi
0x1400477fd  mov     rcx, rsi; lpCriticalSection
0x140047800  call    cs:__imp_EnterCriticalSection
0x140047807  nop     dword ptr [rax+rax+00h]
0x14004780c  mov     [rbp+var_20], 1
0x140047813  xor     ebx, ebx
0x140047815  mov     [rbp+arg_0], ebx
0x140047818  mov     dword ptr [rbp+arg_8], ebx
0x14004781b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rbx
0x14004781f  mov     qword ptr [rbp+arg_18], rbx
0x140047823  mov     [rbp+var_40], rbx
0x140047827  test    r15, r15
0x14004782a  jnz     short loc_140047884
0x14004782c  mov     edi, 80070057h
0x140047831  mov     rax, [r14+0A0h]
0x140047838  lea     rcx, [r14+0A0h]
0x14004783f  mov     rax, [rax+10h]
0x140047843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047848  test    rax, rax
0x14004784b  jz      loc_140047DFB
0x140047851  mov     rax, [r14+0A0h]
0x140047858  lea     rcx, [r14+0A0h]
0x14004785f  mov     rax, [rax+10h]
0x140047863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047868  mov     esi, ebx
0x14004786a  test    rax, rax
0x14004786d  jz      loc_140047DF0
0x140047873  mov     [rsp+78h+var_50], edi
0x140047877  mov     [rsp+78h+var_58], 995h
0x14004787f  jmp     loc_140047DC8
0x140047884  lea     rdx, [rbp+arg_0]; enum WINDLP_STATE *
0x140047888  lea     rcx, [r14-10h]; this
0x14004788c  call    ?CheckInitialized@CDlpTask@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpTask::CheckInitialized(WINDLP_STATE *)
0x140047891  mov     edi, eax
0x140047893  test    eax, eax
0x140047895  jns     short loc_1400478EA
0x140047897  mov     rdx, [r14+0A0h]
0x14004789e  lea     rcx, [r14+0A0h]
0x1400478a5  mov     rax, [rdx+10h]
0x1400478a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400478ae  test    rax, rax
0x1400478b1  jz      loc_140047DFB
0x1400478b7  mov     rax, [r14+0A0h]
0x1400478be  lea     rcx, [r14+0A0h]
0x1400478c5  mov     rax, [rax+10h]
0x1400478c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400478ce  mov     esi, ebx
0x1400478d0  test    rax, rax
0x1400478d3  jz      loc_140047DF0
0x1400478d9  mov     [rsp+78h+var_50], edi
0x1400478dd  mov     [rsp+78h+var_58], 999h
0x1400478e5  jmp     loc_140047DC8
0x1400478ea  mov     eax, [rbp+arg_0]
0x1400478ed  mov     r12d, 0C0000000h
0x1400478f3  cmp     eax, r12d
0x1400478f6  jnz     short loc_140047946
0x1400478f8  mov     rax, [r14+0A0h]
0x1400478ff  lea     rcx, [r14+0A0h]
0x140047906  mov     rax, [rax+10h]
0x14004790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004790f  test    rax, rax
0x140047912  jz      short loc_14004793F
0x140047914  mov     rax, [r14+0A0h]
0x14004791b  lea     rcx, [r14+0A0h]
0x140047922  mov     rax, [rax+10h]
0x140047926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004792b  lea     r8, aDlptaskSkippin_0; "DlpTask: Skipping action progress reset"...
0x140047932  mov     rcx, rax
0x140047935  mov     edx, 3
0x14004793a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14004793f  mov     edi, ebx
0x140047941  jmp     loc_140047DFB
0x140047946  add     eax, 0FFFFFFFDh
0x140047949  cmp     eax, 2
0x14004794c  jbe     short loc_1400479AB
0x14004794e  mov     r15d, 8007139Fh
0x140047954  mov     edi, r15d
0x140047957  mov     rax, [r14+0A0h]
0x14004795e  lea     rcx, [r14+0A0h]
0x140047965  mov     rax, [rax+10h]
0x140047969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004796e  test    rax, rax
0x140047971  jz      loc_140047DFB
0x140047977  mov     rax, [r14+0A0h]
0x14004797e  lea     rcx, [r14+0A0h]
0x140047985  mov     rax, [rax+10h]
0x140047989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004798e  mov     esi, ebx
0x140047990  test    rax, rax
0x140047993  jz      loc_140047DF0
0x140047999  mov     [rsp+78h+var_50], r15d
0x14004799e  mov     [rsp+78h+var_58], 9A7h
0x1400479a6  jmp     loc_140047DC8
0x1400479ab  mov     rax, [r15]
0x1400479ae  lea     rdx, [rbp+arg_0]
0x1400479b2  mov     rcx, r15
0x1400479b5  mov     rax, [rax+18h]
0x1400479b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479be  mov     edi, eax
0x1400479c0  test    eax, eax
0x1400479c2  jns     short loc_140047A17
0x1400479c4  mov     rax, [r14+0A0h]
0x1400479cb  lea     rcx, [r14+0A0h]
0x1400479d2  mov     rax, [rax+10h]
0x1400479d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479db  test    rax, rax
0x1400479de  jz      loc_140047DFB
0x1400479e4  mov     rax, [r14+0A0h]
0x1400479eb  lea     rcx, [r14+0A0h]
0x1400479f2  mov     rax, [rax+10h]
0x1400479f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479fb  mov     esi, ebx
0x1400479fd  test    rax, rax
0x140047a00  jz      loc_140047DF0
0x140047a06  mov     [rsp+78h+var_50], edi
0x140047a0a  mov     [rsp+78h+var_58], 9ABh
0x140047a12  jmp     loc_140047DC8
0x140047a17  mov     eax, [rbp+arg_0]
0x140047a1a  cmp     eax, r12d
0x140047a1d  jnz     short loc_140047A62
0x140047a1f  mov     rax, [r14+0A0h]
0x140047a26  lea     rcx, [r14+0A0h]
0x140047a2d  mov     rax, [rax+10h]
0x140047a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047a36  test    rax, rax
0x140047a39  jz      loc_14004793F
0x140047a3f  mov     rax, [r14+0A0h]
0x140047a46  lea     rcx, [r14+0A0h]
0x140047a4d  mov     rax, [rax+10h]
0x140047a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047a56  lea     r8, aDlptaskSkippin; "DlpTask: Skipping action progress reset"...
0x140047a5d  jmp     loc_140047932
0x140047a62  add     eax, 0FFFFFFFDh
0x140047a65  cmp     eax, 2
0x140047a68  jbe     short loc_140047AC7
0x140047a6a  mov     r15d, 8007139Fh
0x140047a70  mov     edi, r15d
0x140047a73  mov     rax, [r14+0A0h]
0x140047a7a  lea     rcx, [r14+0A0h]
0x140047a81  mov     rax, [rax+10h]
0x140047a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047a8a  test    rax, rax
0x140047a8d  jz      loc_140047DFB
0x140047a93  mov     rax, [r14+0A0h]
0x140047a9a  lea     rcx, [r14+0A0h]
0x140047aa1  mov     rax, [rax+10h]
0x140047aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047aaa  mov     esi, ebx
0x140047aac  test    rax, rax
0x140047aaf  jz      loc_140047DF0
0x140047ab5  mov     [rsp+78h+var_50], r15d
0x140047aba  mov     [rsp+78h+var_58], 9B9h
0x140047ac2  jmp     loc_140047DC8
0x140047ac7  lea     rcx, [r14+358h]; this
0x140047ace  lea     rdx, [rbp+arg_8]; enum WINDLP_STATE *
0x140047ad2  call    ?Get@CDlpState@@QEAAJPEAW4WINDLP_STATE@@@Z; CDlpState::Get(WINDLP_STATE *)
0x140047ad7  mov     edi, eax
0x140047ad9  test    eax, eax
0x140047adb  jns     short loc_140047B30
0x140047add  mov     rax, [r14+0A0h]
0x140047ae4  lea     rcx, [r14+0A0h]
0x140047aeb  mov     rax, [rax+10h]
0x140047aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047af4  test    rax, rax
0x140047af7  jz      loc_140047DFB
0x140047afd  mov     rax, [r14+0A0h]
0x140047b04  lea     rcx, [r14+0A0h]
0x140047b0b  mov     rax, [rax+10h]
0x140047b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b14  mov     esi, ebx
0x140047b16  test    rax, rax
0x140047b19  jz      loc_140047DF0
0x140047b1f  mov     [rsp+78h+var_50], edi
0x140047b23  mov     [rsp+78h+var_58], 9BDh
0x140047b2b  jmp     loc_140047DC8
0x140047b30  mov     rcx, [r14+170h]
0x140047b37  test    rcx, rcx
0x140047b3a  cmovz   rcx, rbx
0x140047b3e  movsxd  r12, dword ptr [rbp+arg_8]
0x140047b42  lea     rsi, [r14+0A0h]
0x140047b49  mov     rax, [rsi]
0x140047b4c  mov     rax, [rax+10h]
0x140047b50  cmp     r15, [rcx+r12*8]
0x140047b54  mov     rcx, rsi
0x140047b57  jz      short loc_140047B97
0x140047b59  mov     edi, 8007000Dh
0x140047b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b63  test    rax, rax
0x140047b66  jz      loc_140047DF7
0x140047b6c  mov     rax, [rsi]
0x140047b6f  mov     rcx, rsi
0x140047b72  mov     rax, [rax+10h]
0x140047b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b7b  mov     esi, ebx
0x140047b7d  test    rax, rax
0x140047b80  jz      loc_140047DF0
0x140047b86  mov     [rsp+78h+var_50], edi
0x140047b8a  mov     [rsp+78h+var_58], 9C2h
0x140047b92  jmp     loc_140047DC8
0x140047b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b9c  test    rax, rax
0x140047b9f  jz      short loc_140047BC8
0x140047ba1  mov     rax, [rsi]
0x140047ba4  mov     rcx, rsi
0x140047ba7  mov     rax, [rax+10h]
0x140047bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047bb0  mov     r9d, dword ptr [rbp+arg_8]
0x140047bb4  lea     r8, aDlptaskResetti_0; "DlpTask: Resetting action [%d] progress"...
0x140047bbb  mov     edx, 2
0x140047bc0  mov     rcx, rax
0x140047bc3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140047bc8  mov     rax, [r15]
0x140047bcb  xor     r9d, r9d
0x140047bce  lea     r8, [rbp+arg_18]
0x140047bd2  lea     rdx, [rbp+var_40]
0x140047bd6  mov     rcx, r15
0x140047bd9  mov     rax, [rax+48h]
0x140047bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047be2  mov     edi, eax
0x140047be4  test    eax, eax
0x140047be6  jns     short loc_140047C2B
0x140047be8  mov     rax, [rsi]
0x140047beb  mov     rcx, rsi
0x140047bee  mov     rax, [rax+10h]
0x140047bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047bf7  test    rax, rax
0x140047bfa  jz      loc_140047DF7
0x140047c00  mov     rax, [rsi]
0x140047c03  mov     rcx, rsi
0x140047c06  mov     rax, [rax+10h]
0x140047c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047c0f  mov     esi, ebx
0x140047c11  test    rax, rax
0x140047c14  jz      loc_140047DF0
0x140047c1a  mov     [rsp+78h+var_50], edi
0x140047c1e  mov     [rsp+78h+var_58], 9C8h
0x140047c26  jmp     loc_140047DC8
0x140047c2b  mov     rax, qword ptr [rbp+arg_18]
0x140047c2f  mov     [r14+598h], rax
0x140047c36  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140047c3a  call    cs:__imp_GetSystemTimeAsFileTime
0x140047c41  nop     dword ptr [rax+rax+00h]
0x140047c46  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x140047c49  mov     dword ptr [rbp+arg_8+4], eax
0x140047c4c  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140047c4f  mov     dword ptr [rbp+arg_8], eax
0x140047c52  mov     rcx, [r14+490h]
0x140047c59  test    rcx, rcx
0x140047c5c  cmovz   rcx, rbx
0x140047c60  mov     rdx, qword ptr [rbp+arg_8]; union _ULARGE_INTEGER
0x140047c64  mov     rcx, [rcx+r12*8]; this
0x140047c68  call    ?Set@CULargeInteger@@QEAAJT_ULARGE_INTEGER@@@Z; CULargeInteger::Set(_ULARGE_INTEGER)
0x140047c6d  mov     edi, eax
0x140047c6f  test    eax, eax
0x140047c71  jns     short loc_140047CB6
0x140047c73  mov     rax, [rsi]
0x140047c76  mov     rcx, rsi
0x140047c79  mov     rax, [rax+10h]
0x140047c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047c82  test    rax, rax
0x140047c85  jz      loc_140047DF7
0x140047c8b  mov     rax, [rsi]
0x140047c8e  mov     rcx, rsi
0x140047c91  mov     rax, [rax+10h]
0x140047c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047c9a  mov     esi, ebx
0x140047c9c  test    rax, rax
0x140047c9f  jz      loc_140047DF0
0x140047ca5  mov     [rsp+78h+var_50], edi
0x140047ca9  mov     [rsp+78h+var_58], 9CFh
0x140047cb1  jmp     loc_140047DC8
0x140047cb6  lea     rcx, [r14+398h]; this
0x140047cbd  mov     r9, rbx; union _ULARGE_INTEGER
0x140047cc0  mov     r8, qword ptr [rbp+arg_18]; union _ULARGE_INTEGER
0x140047cc4  mov     rdx, qword ptr [rbp+arg_8]; union _ULARGE_INTEGER
0x140047cc8  call    ?Set@CProgressData@@QEAAJT_ULARGE_INTEGER@@00@Z; CProgressData::Set(_ULARGE_INTEGER,_ULARGE_INTEGER,_ULARGE_INTEGER)
0x140047ccd  mov     edi, eax
0x140047ccf  test    eax, eax
0x140047cd1  jns     short loc_140047CDA
0x140047cd3  mov     ecx, eax
0x140047cd5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140047cda  mov     ecx, edi
0x140047cdc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140047ce1  test    edi, edi
0x140047ce3  jns     short loc_140047D28
0x140047ce5  mov     rax, [rsi]
  ... truncated ...
```
