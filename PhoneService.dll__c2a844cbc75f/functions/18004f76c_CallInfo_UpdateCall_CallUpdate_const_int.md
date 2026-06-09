# CallInfo::UpdateCall(CallUpdate const *,int)

- ea: `0x18004f76c`
- end: `0x18004faac`
- name: `?UpdateCall@CallInfo@@QEAAJPEBUCallUpdate@@H@Z`
- size: `832`
- prototype: `__int64 __fastcall(CallInfo *__hidden this, const struct CallUpdate *, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180040a8c`
- `0x180041858`
- `0x18004a258`
- `0x18004f158`

## callees

- `0x1800011fc`
- `0x18002c574`
- `0x18004de18`
- `0x18004f300`
- `0x18004f30c`
- `0x18004f76c`
- `0x18004fab4`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f8d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f8d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f84c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f86c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f84c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f86c`

## string_xrefs

- `0x18004f8c5`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall CallInfo::UpdateCall(CallInfo *this, const struct CallUpdate *a2, int a3)
{
  int v3; // r15d
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // edi
  int v12; // r14d
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rsi
  unsigned int v16; // eax
  unsigned __int8 v17; // cf
  int v18; // eax
  const unsigned __int16 *v19; // rdi
  CallInfo *v20; // rcx
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  int v26; // [rsp+30h] [rbp-69h] BYREF
  int v27; // [rsp+34h] [rbp-65h] BYREF
  int v28; // [rsp+38h] [rbp-61h] BYREF
  int v29; // [rsp+3Ch] [rbp-5Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v30; // [rsp+40h] [rbp-59h] BYREF
  const char *v31; // [rsp+60h] [rbp-39h]
  __int64 v32; // [rsp+68h] [rbp-31h]
  int *v33; // [rsp+70h] [rbp-29h]
  __int64 v34; // [rsp+78h] [rbp-21h]
  const unsigned __int16 *v35; // [rsp+80h] [rbp-19h]
  int v36; // [rsp+88h] [rbp-11h]
  int v37; // [rsp+8Ch] [rbp-Dh]
  const unsigned __int16 *v38; // [rsp+90h] [rbp-9h]
  int v39; // [rsp+98h] [rbp-1h]
  int v40; // [rsp+9Ch] [rbp+3h]
  int *v41; // [rsp+A0h] [rbp+7h]
  __int64 v42; // [rsp+A8h] [rbp+Fh]

  v3 = *((_DWORD *)this + 760);
  v27 = v3;
  v7 = CallInfo::ApplyCallUpdateInfo(this, a2);
  if ( v7 < 0 )
    Log_HREvent_9((unsigned int)v7, 0, v10, 413);
  v11 = *((_DWORD *)this + 760);
  v12 = 2;
  v26 = v11;
  if ( *((_DWORD *)this + 817) == 2 )
  {
    if ( v11 != *((_DWORD *)a2 + 190) )
    {
      Log_AssertionEvent_5(v9, v8, 360);
      if ( v11 != *((_DWORD *)a2 + 190) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v13 = 4;
    if ( v11 != 3 )
      v13 = *((_DWORD *)a2 + 969);
  }
  else
  {
    v13 = 0;
  }
  v14 = 6612;
  *((_DWORD *)this + 1653) = *((_DWORD *)this + 1654);
  *((_DWORD *)this + 1654) = v13;
  if ( !*((_DWORD *)this + 752) )
  {
    v14 = (__int64)this + 3004;
    if ( !*((_DWORD *)this + 751) && (((v11 - 1) & 0xFFFFFFFA) != 0 || v11 == 6) )
      GetSystemTimeAsFileTime((LPFILETIME)v14);
  }
  if ( v11 == 5 && !*((_DWORD *)this + 754) )
  {
    v14 = (__int64)this + 3012;
    if ( !*((_DWORD *)this + 753) )
      GetSystemTimeAsFileTime((LPFILETIME)v14);
  }
  if ( v3 != v11 || a3 )
  {
    if ( v11 == 5 )
    {
      *((_DWORD *)this + 1673) = 0;
      if ( *((_DWORD *)this + 761) )
        *((_DWORD *)this + 1666) = 1;
      if ( *((_WORD *)this + 3344) )
      {
        v15 = *((_QWORD *)this + 831);
        if ( *(_DWORD *)(v15 + 240) != GetCurrentThreadId() )
        {
          Log_AssertionEvent_3(v14, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7364);
          if ( *(_DWORD *)(v15 + 240) != GetCurrentThreadId() )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        *((_WORD *)this + 3344) = 0;
      }
    }
    if ( (a3 || ((v3 - 1) & 0xFFFFFFFA) == 0 && v3 != 6) && (((v11 - 1) & 0xFFFFFFFA) != 0 || v11 == 6) )
      *((_DWORD *)this + 1668) = 1;
  }
  if ( v11 == 5 )
  {
    v16 = *((_DWORD *)this + 761);
    if ( v16 > 0x17 || (v14 = 8389122, v17 = _bittest((const int *)&v14, v16), v18 = 1, !v17) )
      v18 = 0;
    if ( v18 )
    {
      *((_DWORD *)this + 1656) = 2;
      *((_DWORD *)this + 763) = 2;
    }
    else
    {
      *((_DWORD *)this + 1656) = 0;
      *((_DWORD *)this + 763) = 0;
    }
  }
  if ( v3 != v11 && (unsigned int)dword_1800B3200 > 4 )
  {
    v28 = a3;
    v19 = CallInfo::_MapCallStateToString((CallInfo *)v14, (const enum PH_CALLSTATE *)&v26);
    v21 = CallInfo::_MapCallStateToString(v20, (const enum PH_CALLSTATE *)&v27);
    v29 = *((_DWORD *)this + 767);
    v22 = -1;
    v41 = &v28;
    v42 = 4;
    if ( v19 )
    {
      v23 = -1;
      do
        ++v23;
      while ( v19[v23] );
      v24 = 2 * v23 + 2;
    }
    else
    {
      v19 = &qword_18009A460;
      v24 = 2;
    }
    v38 = v19;
    v39 = v24;
    v40 = 0;
    if ( v21 )
    {
      do
        ++v22;
      while ( v21[v22] );
      v12 = 2 * v22 + 2;
    }
    else
    {
      v21 = &qword_18009A460;
    }
    v35 = v21;
    v33 = &v29;
    v36 = v12;
    v31 = "CallInfo: CallState Change";
    v37 = 0;
    v34 = 4;
    v32 = 27;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&unk_1800A90D8, 0, 0, 7u, &v30);
  }
  if ( a3 )
    *((_DWORD *)this + 1708) = *((_DWORD *)this + 817) == 1;
  if ( !*((_DWORD *)this + 1707) && *((_DWORD *)this + 817) == 1 )
    *((_DWORD *)this + 1707) = 1;
  return 0;
}

```

## disassembly

```asm
0x18004f76c  mov     [rsp-8+arg_10], rbx
0x18004f771  push    rbp
0x18004f772  push    rsi
0x18004f773  push    rdi
0x18004f774  push    r12
0x18004f776  push    r13
0x18004f778  push    r14
0x18004f77a  push    r15
0x18004f77c  lea     rbp, [rsp-27h]
0x18004f781  sub     rsp, 0C0h
0x18004f788  mov     rax, cs:__security_cookie
0x18004f78f  xor     rax, rsp
0x18004f792  mov     [rbp+57h+var_40], rax
0x18004f796  mov     r15d, [rcx+0BE0h]
0x18004f79d  mov     r12d, r8d
0x18004f7a0  mov     [rbp+57h+var_BC], r15d
0x18004f7a4  mov     rsi, rdx
0x18004f7a7  mov     rbx, rcx
0x18004f7aa  call    ?ApplyCallUpdateInfo@CallInfo@@QEAAJPEBUCallUpdate@@@Z; CallInfo::ApplyCallUpdateInfo(CallUpdate const *)
0x18004f7af  xor     r13d, r13d
0x18004f7b2  test    eax, eax
0x18004f7b4  jns     short loc_18004F7C5
0x18004f7b6  xor     edx, edx
0x18004f7b8  mov     r9d, 19Dh
0x18004f7be  mov     ecx, eax
0x18004f7c0  call    Log_HREvent_9
0x18004f7c5  mov     edi, [rbx+0BE0h]
0x18004f7cb  mov     r14d, 2
0x18004f7d1  mov     [rbp+57h+var_C0], edi
0x18004f7d4  cmp     [rbx+0CC4h], r14d
0x18004f7db  jz      short loc_18004F7E2
0x18004f7dd  mov     r8d, r13d
0x18004f7e0  jmp     short loc_18004F814
0x18004f7e2  cmp     edi, [rsi+2F8h]
0x18004f7e8  jz      short loc_18004F802
0x18004f7ea  mov     r8d, 168h
0x18004f7f0  call    Log_AssertionEvent_5
0x18004f7f5  cmp     edi, [rsi+2F8h]
0x18004f7fb  jz      short loc_18004F802
0x18004f7fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004f802  mov     r8d, 4
0x18004f808  cmp     edi, 3
0x18004f80b  jz      short loc_18004F814
0x18004f80d  mov     r8d, [rsi+0F24h]
0x18004f814  mov     ecx, 19D4h
0x18004f819  mov     rdx, rbx
0x18004f81c  mov     eax, [rbx+rcx+4]
0x18004f820  mov     [rbx+rcx], eax
0x18004f823  mov     [rbx+rcx+4], r8d
0x18004f828  cmp     [rbx+0BC0h], r13d
0x18004f82f  jnz     short loc_18004F852
0x18004f831  lea     rcx, [rbx+0BBCh]; lpSystemTimeAsFileTime
0x18004f838  cmp     [rcx], r13d
0x18004f83b  jnz     short loc_18004F852
0x18004f83d  lea     eax, [rdi-1]
0x18004f840  test    eax, 0FFFFFFFAh
0x18004f845  jnz     short loc_18004F84C
0x18004f847  cmp     edi, 6
0x18004f84a  jnz     short loc_18004F852
0x18004f84c  call    cs:__imp_GetSystemTimeAsFileTime
0x18004f852  cmp     edi, 5
0x18004f855  jnz     short loc_18004F872
0x18004f857  cmp     [rbx+0BC8h], r13d
0x18004f85e  jnz     short loc_18004F872
0x18004f860  lea     rcx, [rbx+0BC4h]; lpSystemTimeAsFileTime
0x18004f867  cmp     [rcx], r13d
0x18004f86a  jnz     short loc_18004F872
0x18004f86c  call    cs:__imp_GetSystemTimeAsFileTime
0x18004f872  mov     esi, 1
0x18004f877  cmp     r15d, edi
0x18004f87a  jnz     short loc_18004F885
0x18004f87c  test    r12d, r12d
0x18004f87f  jz      loc_18004F91C
0x18004f885  cmp     edi, 5
0x18004f888  jnz     short loc_18004F8F1
0x18004f88a  mov     [rbx+1A24h], r13d
0x18004f891  cmp     [rbx+0BE4h], r13d
0x18004f898  jz      short loc_18004F8A0
0x18004f89a  mov     [rbx+1A08h], esi
0x18004f8a0  cmp     r13w, [rbx+1A20h]
0x18004f8a8  jz      short loc_18004F8F1
0x18004f8aa  mov     rsi, [rbx+19F8h]
0x18004f8b1  call    cs:__imp_GetCurrentThreadId
0x18004f8b7  cmp     [rsi+0F0h], eax
0x18004f8bd  jz      short loc_18004F8E4
0x18004f8bf  mov     r8d, 1CC4h
0x18004f8c5  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004f8cc  call    Log_AssertionEvent_3
0x18004f8d1  call    cs:__imp_GetCurrentThreadId
0x18004f8d7  cmp     [rsi+0F0h], eax
0x18004f8dd  jz      short loc_18004F8E4
0x18004f8df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004f8e4  mov     [rbx+1A20h], r13w
0x18004f8ec  mov     esi, 1
0x18004f8f1  test    r12d, r12d
0x18004f8f4  jnz     short loc_18004F907
0x18004f8f6  lea     eax, [r15-1]
0x18004f8fa  test    eax, 0FFFFFFFAh
0x18004f8ff  jnz     short loc_18004F91C
0x18004f901  cmp     r15d, 6
0x18004f905  jz      short loc_18004F91C
0x18004f907  lea     eax, [rdi-1]
0x18004f90a  test    eax, 0FFFFFFFAh
0x18004f90f  jnz     short loc_18004F916
0x18004f911  cmp     edi, 6
0x18004f914  jnz     short loc_18004F91C
0x18004f916  mov     [rbx+1A10h], esi
0x18004f91c  cmp     edi, 5
0x18004f91f  jnz     short loc_18004F95D
0x18004f921  mov     eax, [rbx+0BE4h]
0x18004f927  cmp     eax, 17h
0x18004f92a  ja      short loc_18004F938
0x18004f92c  mov     ecx, 800202h; this
0x18004f931  bt      ecx, eax
0x18004f934  mov     eax, esi
0x18004f936  jb      short loc_18004F93B
0x18004f938  mov     eax, r13d
0x18004f93b  test    eax, eax
0x18004f93d  jz      short loc_18004F94F
0x18004f93f  mov     [rbx+19E0h], r14d
0x18004f946  mov     [rbx+0BECh], r14d
0x18004f94d  jmp     short loc_18004F95D
0x18004f94f  mov     [rbx+19E0h], r13d
0x18004f956  mov     [rbx+0BECh], r13d
0x18004f95d  cmp     r15d, edi
0x18004f960  jz      loc_18004FA55
0x18004f966  mov     eax, cs:dword_1800B3200
0x18004f96c  mov     r15d, 4
0x18004f972  cmp     eax, r15d
0x18004f975  jbe     loc_18004FA55
0x18004f97b  lea     rdx, [rbp+57h+var_C0]; enum PH_CALLSTATE *
0x18004f97f  mov     [rbp+57h+var_B8], r12d
0x18004f983  call    ?_MapCallStateToString@CallInfo@@AEAAPEBGAEBW4PH_CALLSTATE@@@Z; CallInfo::_MapCallStateToString(PH_CALLSTATE const &)
0x18004f988  lea     rdx, [rbp+57h+var_BC]; enum PH_CALLSTATE *
0x18004f98c  mov     rdi, rax
0x18004f98f  call    ?_MapCallStateToString@CallInfo@@AEAAPEBGAEBW4PH_CALLSTATE@@@Z; CallInfo::_MapCallStateToString(PH_CALLSTATE const &)
0x18004f994  mov     ecx, [rbx+0BFCh]
0x18004f99a  mov     rdx, rax
0x18004f99d  mov     [rbp+57h+var_B4], ecx
0x18004f9a0  lea     rax, [rbp+57h+var_B8]
0x18004f9a4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004f9a8  mov     [rbp+57h+var_50], rax
0x18004f9ac  mov     [rbp+57h+var_48], r15
0x18004f9b0  test    rdi, rdi
0x18004f9b3  jz      short loc_18004F9CB
0x18004f9b5  mov     rax, rcx
0x18004f9b8  inc     rax
0x18004f9bb  cmp     [rdi+rax*2], r13w
0x18004f9c0  jnz     short loc_18004F9B8
0x18004f9c2  lea     eax, ds:2[rax*2]
0x18004f9c9  jmp     short loc_18004F9D5
0x18004f9cb  lea     rdi, qword_18009A460
0x18004f9d2  mov     eax, r14d
0x18004f9d5  mov     [rbp+57h+var_60], rdi
0x18004f9d9  mov     [rbp+57h+var_58], eax
0x18004f9dc  mov     [rbp+57h+var_54], r13d
0x18004f9e0  test    rdx, rdx
0x18004f9e3  jz      short loc_18004F9F9
0x18004f9e5  inc     rcx
0x18004f9e8  cmp     [rdx+rcx*2], r13w
0x18004f9ed  jnz     short loc_18004F9E5
0x18004f9ef  lea     r14d, ds:2[rcx*2]
0x18004f9f7  jmp     short loc_18004FA00
0x18004f9f9  lea     rdx, qword_18009A460
0x18004fa00  lea     rax, [rbp+57h+var_B4]
0x18004fa04  mov     [rbp+57h+var_70], rdx
0x18004fa08  mov     [rbp+57h+var_80], rax
0x18004fa0c  lea     rdx, unk_1800A90D8; int
0x18004fa13  lea     rax, aCallinfoCallst; "CallInfo: CallState Change"
0x18004fa1a  mov     [rbp+57h+var_68], r14d
0x18004fa1e  mov     [rbp+57h+var_90], rax
0x18004fa22  lea     rcx, dword_1800B3200; int
0x18004fa29  lea     rax, [rbp+57h+var_B0]
0x18004fa2d  mov     [rbp+57h+var_64], r13d
0x18004fa31  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x18004fa36  xor     r9d, r9d; int
0x18004fa39  xor     r8d, r8d; int
0x18004fa3c  mov     [rsp+0F0h+var_D0], 7; ULONG
0x18004fa44  mov     [rbp+57h+var_78], r15
0x18004fa48  mov     [rbp+57h+var_88], 1Bh
0x18004fa50  call    _tlgWriteTransfer_EventWriteTransfer
0x18004fa55  test    r12d, r12d
0x18004fa58  jz      short loc_18004FA6C
0x18004fa5a  cmp     [rbx+0CC4h], esi
0x18004fa60  mov     eax, r13d
0x18004fa63  setz    al
0x18004fa66  mov     [rbx+1AB0h], eax
0x18004fa6c  cmp     [rbx+1AACh], r13d
0x18004fa73  jnz     short loc_18004FA83
0x18004fa75  cmp     [rbx+0CC4h], esi
0x18004fa7b  jnz     short loc_18004FA83
0x18004fa7d  mov     [rbx+1AACh], esi
0x18004fa83  xor     eax, eax
0x18004fa85  mov     rcx, [rbp+57h+var_40]
0x18004fa89  xor     rcx, rsp; StackCookie
0x18004fa8c  call    __security_check_cookie
0x18004fa91  mov     rbx, [rsp+0F0h+arg_10]
0x18004fa99  add     rsp, 0C0h
0x18004faa0  pop     r15
0x18004faa2  pop     r14
0x18004faa4  pop     r13
0x18004faa6  pop     r12
0x18004faa8  pop     rdi
0x18004faa9  pop     rsi
0x18004faaa  pop     rbp
0x18004faab  retn
```
