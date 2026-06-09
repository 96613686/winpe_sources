# WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(bool)

- ea: `0x180024270`
- end: `0x180024420`
- name: `?ControlProgressHandler_Update@CControlManager@WindowsPerformanceRecorder@@QEAAJ_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, bool)`
- caller_count: `9`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800236b0`
- `0x180032adc`
- `0x18003a1f0`
- `0x1800490f8`
- `0x180058800`
- `0x180059060`
- `0x18005c560`
- `0x18005deb0`
- `0x18005f068`

## callees

- `0x18000829c`
- `0x18000a154`
- `0x18001e6e0`
- `0x180024270`
- `0x18004a2dc`
- `0x18004ece0`
- `0x18008c010`

## string_xrefs

- `0x180024362`: `ControlProgressHandler_Update`
- `0x1800243d5`: `ControlProgressHandler_Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(
        WindowsPerformanceRecorder::CControlManager *this,
        char a2,
        __int64 a3)
{
  __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  unsigned __int64 v9; // r8
  unsigned int v10; // ebx
  char *v11; // [rsp+28h] [rbp-40h]
  _QWORD v12[2]; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-28h] BYREF

  v12[1] = -2;
  if ( a2 )
  {
    if ( ++*((_QWORD *)this + 52) > *((_QWORD *)this + 53) )
    {
      LODWORD(v11) = *((_DWORD *)this + 104) - *((_DWORD *)this + 106);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        "ControlProgressHandler_Update",
        (const char *)0x967,
        0,
        "Buffer count estimation difference =  %u\n",
        v11);
      *((_QWORD *)this + 52) = *((_QWORD *)this + 53);
    }
  }
  v5 = *((_QWORD *)this + 47);
  if ( !v5 )
    return 0;
  v12[0] = &off_18008FAB0;
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 4) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&WindowsPerformanceRecorderControlProvider_Context,
      (const EVENT_DESCRIPTOR *)Perf_ControlProgressHandlerUpdate_Begin,
      a3,
      1u,
      &v13);
    v5 = *((_QWORD *)this + 47);
  }
  if ( a2 && (v9 = *((_QWORD *)this + 53)) != 0 )
    v6 = 100LL * *((_QWORD *)this + 52) / v9;
  else
    v6 = 0;
  if ( !(*(unsigned int (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v5 + 64LL))(v5, v6) )
  {
    if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&WindowsPerformanceRecorderControlProvider_Context,
        (const EVENT_DESCRIPTOR *)Perf_ControlProgressHandlerUpdate_End,
        v7,
        1u,
        &v13);
    return 0;
  }
  v10 = ATL::AtlHresultFromWin32(0x4C7u);
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)2,
    "ControlProgressHandler_Update",
    (const char *)0x974,
    v10,
    (char *)&byte_1800986EF,
    v11);
  WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update_::_11_::CPerfEventMacro::_CPerfEventMacro(v12);
  return v10;
}

```

## disassembly

```asm
0x180024270  push    rdi
0x180024272  sub     rsp, 60h
0x180024276  mov     [rsp+68h+var_30], 0FFFFFFFFFFFFFFFEh
0x18002427f  mov     [rsp+68h+arg_8], rbx
0x180024284  mov     rax, cs:__security_cookie
0x18002428b  xor     rax, rsp
0x18002428e  mov     [rsp+68h+var_18], rax
0x180024293  mov     dil, dl
0x180024296  mov     rbx, rcx
0x180024299  test    dl, dl
0x18002429b  jz      short loc_1800242B8
0x18002429d  inc     qword ptr [rcx+1A0h]
0x1800242a4  mov     rax, [rcx+1A0h]
0x1800242ab  cmp     rax, [rcx+1A8h]
0x1800242b2  ja      loc_18002433D
0x1800242b8  mov     rcx, [rbx+178h]
0x1800242bf  test    rcx, rcx
0x1800242c2  jz      short loc_180024305
0x1800242c4  lea     rax, off_18008FAB0
0x1800242cb  mov     [rsp+68h+var_38], rax
0x1800242d0  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 4
0x1800242d7  jnz     loc_180024385
0x1800242dd  test    dil, dil
0x1800242e0  jnz     short loc_18002431F
0x1800242e2  xor     edx, edx
0x1800242e4  mov     rax, [rcx]
0x1800242e7  mov     rax, [rax+40h]
0x1800242eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242f0  test    eax, eax
0x1800242f2  jnz     loc_1800243B4
0x1800242f8  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 4
0x1800242ff  jnz     loc_1800243F8
0x180024305  xor     eax, eax
0x180024307  mov     rcx, [rsp+68h+var_18]
0x18002430c  xor     rcx, rsp; StackCookie
0x18002430f  call    __security_check_cookie
0x180024314  mov     rbx, [rsp+68h+arg_8]
0x180024319  add     rsp, 60h
0x18002431d  pop     rdi
0x18002431e  retn
0x18002431f  mov     r8, [rbx+1A8h]
0x180024326  test    r8, r8
0x180024329  jz      short loc_1800242E2
0x18002432b  imul    rax, [rbx+1A0h], 64h ; 'd'
0x180024333  xor     edx, edx
0x180024335  div     r8
0x180024338  mov     rdx, rax
0x18002433b  jmp     short loc_1800242E4
0x18002433d  mov     eax, [rcx+1A0h]
0x180024343  sub     eax, [rcx+1A8h]
0x180024349  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18002434d  lea     rax, aBufferCountEst; "Buffer count estimation difference =  %"...
0x180024354  mov     [rsp+68h+Format], rax; Format
0x180024359  xor     r9d, r9d; unsigned int
0x18002435c  mov     r8d, 967h; char *
0x180024362  lea     rdx, aControlprogres_0; "ControlProgressHandler_Update"
0x180024369  lea     ecx, [r9+3]; this
0x18002436d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180024372  mov     rax, [rbx+1A8h]
0x180024379  mov     [rbx+1A0h], rax
0x180024380  jmp     loc_1800242B8
0x180024385  lea     rax, [rsp+68h+var_28]
0x18002438a  mov     [rsp+68h+Format], rax
0x18002438f  mov     r9d, 1
0x180024395  lea     rdx, Perf_ControlProgressHandlerUpdate_Begin
0x18002439c  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x1800243a3  call    McGenEventWrite_EventWriteTransfer
0x1800243a8  mov     rcx, [rbx+178h]
0x1800243af  jmp     loc_1800242DD
0x1800243b4  mov     ecx, 4C7h; unsigned int
0x1800243b9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800243be  mov     ebx, eax
0x1800243c0  lea     rax, byte_1800986EF
0x1800243c7  mov     [rsp+68h+Format], rax; Format
0x1800243cc  mov     r9d, ebx; unsigned int
0x1800243cf  mov     r8d, 974h; char *
0x1800243d5  lea     rdx, aControlprogres_0; "ControlProgressHandler_Update"
0x1800243dc  mov     ecx, 2; this
0x1800243e1  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800243e6  nop
0x1800243e7  lea     rcx, [rsp+68h+var_38]
0x1800243ec  call    _WindowsPerformanceRecorder__CControlManager__ControlProgressHandler_Update____11___CPerfEventMacro___CPerfEventMacro
0x1800243f1  mov     eax, ebx
0x1800243f3  jmp     loc_180024307
0x1800243f8  lea     rax, [rsp+68h+var_28]
0x1800243fd  mov     [rsp+68h+Format], rax
0x180024402  mov     r9d, 1
0x180024408  lea     rdx, Perf_ControlProgressHandlerUpdate_End
0x18002440f  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x180024416  call    McGenEventWrite_EventWriteTransfer
0x18002441b  jmp     loc_180024305
```
