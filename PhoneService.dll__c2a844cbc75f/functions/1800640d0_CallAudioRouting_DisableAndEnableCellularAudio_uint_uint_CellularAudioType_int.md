# CallAudioRouting::_DisableAndEnableCellularAudio(uint,uint,CellularAudioType,int)

- ea: `0x1800640d0`
- end: `0x180064263`
- name: `?_DisableAndEnableCellularAudio@CallAudioRouting@@AEAAXIIW4CellularAudioType@@H@Z`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011fc`
- `0x18005f9b4`
- `0x1800640d0`
- `0x180064350`
- `0x18007f9ec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800641c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800641f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800641f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064120`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064103`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064120`

## string_xrefs

- `0x180064114`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_DisableAndEnableCellularAudio(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  __int64 v9; // rcx
  int v10; // r15d
  unsigned __int64 v11; // rbx
  int v12; // [rsp+30h] [rbp-81h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-7Dh] BYREF
  unsigned int v14; // [rsp+38h] [rbp-79h] BYREF
  unsigned int v15; // [rsp+3Ch] [rbp-75h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+40h] [rbp-71h] BYREF
  const char *v17; // [rsp+60h] [rbp-51h]
  __int64 v18; // [rsp+68h] [rbp-49h]
  unsigned int *v19; // [rsp+70h] [rbp-41h]
  __int64 v20; // [rsp+78h] [rbp-39h]
  unsigned int *v21; // [rsp+80h] [rbp-31h]
  __int64 v22; // [rsp+88h] [rbp-29h]
  unsigned int *v23; // [rsp+90h] [rbp-21h]
  __int64 v24; // [rsp+98h] [rbp-19h]
  int *v25; // [rsp+A0h] [rbp-11h]
  __int64 v26; // [rsp+A8h] [rbp-9h]

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 1463);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v10 = 0;
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v26 = 4;
    v25 = &v12;
    v24 = 4;
    v23 = &v13;
    v22 = 4;
    v21 = &v14;
    v20 = 4;
    v19 = &v15;
    v12 = a5;
    v17 = "CallAudioRouting:Disable and enable cellular audio.";
    v13 = a4;
    v14 = a3;
    v15 = a2;
    v18 = 52;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&dword_1800A9EDC, 0, 0, 7u, &v16);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v11 = 0xDF5B0F768CE2CABDuLL * ((__int64)(*(_QWORD *)(a1 + 160) - *(_QWORD *)(a1 + 152)) >> 3);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( v11 > 1 )
    CallAudioRouting::_EnableCellularAudio(a1, a2, 0, 0, 0, 0);
  LOBYTE(v10) = v11 > 1;
  CallAudioRouting::_EnableCellularAudio(a1, a3, a4, a5, 0, v10);
}

```

## disassembly

```asm
0x1800640d0  push    rbp
0x1800640d2  push    rbx
0x1800640d3  push    rsi
0x1800640d4  push    rdi
0x1800640d5  push    r12
0x1800640d7  push    r13
0x1800640d9  push    r14
0x1800640db  push    r15
0x1800640dd  lea     rbp, [rsp-17h]
0x1800640e2  sub     rsp, 0C8h
0x1800640e9  mov     rax, cs:__security_cookie
0x1800640f0  xor     rax, rsp
0x1800640f3  mov     [rbp+4Fh+var_50], rax
0x1800640f7  mov     r13d, r9d
0x1800640fa  mov     r12d, r8d
0x1800640fd  mov     r14d, edx
0x180064100  mov     rdi, rcx
0x180064103  call    cs:__imp_GetCurrentThreadId
0x180064109  cmp     [rdi+68h], eax
0x18006410c  jnz     short loc_180064130
0x18006410e  mov     r8d, 5B7h
0x180064114  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006411b  call    Log_AssertionEvent_9
0x180064120  call    cs:__imp_GetCurrentThreadId
0x180064126  cmp     [rdi+68h], eax
0x180064129  jnz     short loc_180064130
0x18006412b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064130  mov     eax, cs:dword_1800B3200
0x180064136  xor     r15d, r15d
0x180064139  mov     esi, [rbp+4Fh+arg_20]
0x18006413c  lea     ecx, [r15+4]
0x180064140  cmp     eax, ecx
0x180064142  jbe     short loc_1800641C2
0x180064144  lea     rax, [rsp+100h+var_D0]
0x180064149  mov     [rbp+4Fh+var_58], rcx
0x18006414d  mov     [rbp+4Fh+var_60], rax
0x180064151  lea     rdx, dword_1800A9EDC; int
0x180064158  lea     rax, [rbp+4Fh+var_CC]
0x18006415c  mov     [rbp+4Fh+var_68], rcx
0x180064160  mov     [rbp+4Fh+var_70], rax
0x180064164  xor     r9d, r9d; int
0x180064167  lea     rax, [rbp+4Fh+var_C8]
0x18006416b  mov     [rbp+4Fh+var_78], rcx
0x18006416f  mov     [rbp+4Fh+var_80], rax
0x180064173  xor     r8d, r8d; int
0x180064176  lea     rax, [rbp+4Fh+var_C4]
0x18006417a  mov     [rbp+4Fh+var_88], rcx
0x18006417e  mov     [rbp+4Fh+var_90], rax
0x180064182  lea     rcx, dword_1800B3200; int
0x180064189  lea     rax, aCallaudiorouti_6; "CallAudioRouting:Disable and enable cel"...
0x180064190  mov     [rsp+100h+var_D0], esi
0x180064194  mov     [rbp+4Fh+var_A0], rax
0x180064198  lea     rax, [rbp+4Fh+var_C0]
0x18006419c  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1800641a1  mov     [rsp+100h+var_E0], 7; ULONG
0x1800641a9  mov     [rbp+4Fh+var_CC], r13d
0x1800641ad  mov     [rbp+4Fh+var_C8], r12d
0x1800641b1  mov     [rbp+4Fh+var_C4], r14d
0x1800641b5  mov     [rbp+4Fh+var_98], 34h ; '4'
0x1800641bd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800641c2  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800641c6  call    cs:__imp_EnterCriticalSection
0x1800641cc  mov     rbx, [rdi+0A0h]
0x1800641d3  lea     rcx, [rdi+58h]; lpCriticalSection
0x1800641d7  sub     rbx, [rdi+98h]
0x1800641de  mov     rax, 0DF5B0F768CE2CABDh
0x1800641e8  sar     rbx, 3
0x1800641ec  imul    rbx, rax
0x1800641f0  cmp     rbx, 1
0x1800641f4  setnbe  r15b
0x1800641f8  call    cs:__imp_LeaveCriticalSection
0x1800641fe  cmp     rbx, 1
0x180064202  jbe     short loc_180064225
0x180064204  mov     dword ptr [rsp+100h+var_D8], 0
0x18006420c  xor     r9d, r9d
0x18006420f  xor     r8d, r8d
0x180064212  mov     [rsp+100h+var_E0], 0
0x18006421a  mov     edx, r14d
0x18006421d  mov     rcx, rdi
0x180064220  call    ?_EnableCellularAudio@CallAudioRouting@@AEAAXIW4CellularAudioType@@HHH@Z; CallAudioRouting::_EnableCellularAudio(uint,CellularAudioType,int,int,int)
0x180064225  mov     dword ptr [rsp+100h+var_D8], r15d
0x18006422a  mov     r9d, esi
0x18006422d  mov     r8d, r13d
0x180064230  mov     [rsp+100h+var_E0], 0
0x180064238  mov     edx, r12d
0x18006423b  mov     rcx, rdi
0x18006423e  call    ?_EnableCellularAudio@CallAudioRouting@@AEAAXIW4CellularAudioType@@HHH@Z; CallAudioRouting::_EnableCellularAudio(uint,CellularAudioType,int,int,int)
0x180064243  mov     rcx, [rbp+4Fh+var_50]
0x180064247  xor     rcx, rsp; StackCookie
0x18006424a  call    __security_check_cookie
0x18006424f  add     rsp, 0C8h
0x180064256  pop     r15
0x180064258  pop     r14
0x18006425a  pop     r13
0x18006425c  pop     r12
0x18006425e  pop     rdi
0x18006425f  pop     rsi
0x180064260  pop     rbx
0x180064261  pop     rbp
0x180064262  retn
```
