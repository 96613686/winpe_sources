# CommonUtil::CServiceHandler::Dispatch(void)

- ea: `0x140015950`
- end: `0x140015b1d`
- name: `?Dispatch@CServiceHandler@CommonUtil@@UEAAJXZ`
- size: `461`
- prototype: `__int64 __fastcall(CommonUtil::CServiceHandler *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400144dc`
- `0x140015528`
- `0x140015950`
- `0x140017738`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x140085d94`
- `0x140166250`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x140015ac3`
- `KERNEL32!UnregisterWaitEx` at `0x140015ac3`
- `KERNEL32!TerminateProcess` at `0x140015a92`
- `KERNEL32!TerminateProcess` at `0x140015a92`
- `KERNEL32!GetCurrentProcess` at `0x140015a84`
- `KERNEL32!GetCurrentProcess` at `0x140015a84`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400159da`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400159da`

## pseudocode

```c
__int64 __fastcall CommonUtil::CServiceHandler::Dispatch(
        CommonUtil::CServiceHandler *this,
        __int64 a2,
        const wchar_t *a3)
{
  wchar_t **v3; // rdx
  const struct std::nothrow_t *v5; // rdx
  int LastFailure; // esi
  void *v7; // rcx
  void *v9; // rbx
  unsigned int v10; // r8d
  HANDLE CurrentProcess; // rax
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // r8d
  CommonUtil *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rcx
  void *v17; // [rsp+30h] [rbp-38h] BYREF
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+38h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-20h]
  __int64 v20; // [rsp+50h] [rbp-18h]

  v3 = (wchar_t **)*((_QWORD *)this + 2);
  v17 = 0;
  LastFailure = CommonUtil::HrDuplicateStringW((CommonUtil *)&v17, v3, a3);
  if ( LastFailure < 0 )
  {
    v7 = v17;
    if ( !v17 )
      return (unsigned int)LastFailure;
LABEL_3:
    operator delete(v7, v5);
    return (unsigned int)LastFailure;
  }
  v9 = v17;
  ServiceStartTable.lpServiceName = (LPWSTR)v17;
  ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)CommonUtil::CServiceHandler::ServiceDispatcherCallback;
  v19 = 0;
  v20 = 0;
  qword_1401E3EA0 = this;
  if ( StartServiceCtrlDispatcherW(&ServiceStartTable) )
  {
    if ( !*((_QWORD *)this + 12) && *((_DWORD *)this + 17) != 1 )
      LastFailure = -2147024882;
  }
  else
  {
    LastFailure = HrGetLastFailure();
  }
  if ( LastFailure < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        *((_QWORD *)this + 2),
        LastFailure);
    if ( !v9 )
      return (unsigned int)LastFailure;
    v7 = v9;
    goto LABEL_3;
  }
  if ( *((_DWORD *)this + 17) != 1 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 2u);
  }
  CommonUtil::UtilWaitForSingleObject(*((CommonUtil **)this + 4), (void *)0xFFFFFFFFLL, v10);
  v14 = (CommonUtil *)*((_QWORD *)this + 7);
  if ( v14 )
    CommonUtil::UtilWaitForSingleObject(v14, (void *)0xFFFFFFFFLL, v13);
  v15 = (void *)*((_QWORD *)this + 5);
  if ( v15 )
  {
    UnregisterWaitEx(v15, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 5) = 0;
  }
  v16 = *((_QWORD *)this + 6);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    *((_QWORD *)this + 6) = 0;
  }
  if ( v9 )
    operator delete(v9, v12);
  return 0;
}

```

## disassembly

```asm
0x140015950  mov     r11, rsp
0x140015953  mov     [r11+10h], rbx
0x140015957  mov     [r11+18h], rsi
0x14001595b  push    rdi
0x14001595c  sub     rsp, 60h
0x140015960  mov     rax, cs:__security_cookie
0x140015967  xor     rax, rsp
0x14001596a  mov     [rsp+68h+var_10], rax
0x14001596f  mov     rdx, [rcx+10h]; wchar_t **
0x140015973  mov     rdi, rcx
0x140015976  lea     rcx, [r11-38h]; this
0x14001597a  mov     qword ptr [r11-38h], 0
0x140015982  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::HrDuplicateStringW(wchar_t * *,wchar_t const *)
0x140015987  mov     esi, eax
0x140015989  shr     eax, 1Fh
0x14001598c  test    al, al
0x14001598e  jz      short loc_1400159A6
0x140015990  mov     rcx, [rsp+68h+var_38]; void *
0x140015995  test    rcx, rcx
0x140015998  jz      short loc_14001599F
0x14001599a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001599f  mov     eax, esi
0x1400159a1  jmp     loc_140015AFE
0x1400159a6  mov     rbx, [rsp+68h+var_38]
0x1400159ab  lea     rax, ?ServiceDispatcherCallback@CServiceHandler@CommonUtil@@CAXKPEAPEA_W@Z; CommonUtil::CServiceHandler::ServiceDispatcherCallback(ulong,wchar_t * *)
0x1400159b2  lea     rcx, [rsp+68h+ServiceStartTable]; lpServiceStartTable
0x1400159b7  mov     [rsp+68h+ServiceStartTable.lpServiceName], rbx
0x1400159bc  mov     [rsp+68h+ServiceStartTable.lpServiceProc], rax
0x1400159c1  mov     [rsp+68h+var_20], 0
0x1400159ca  mov     [rsp+68h+var_18], 0
0x1400159d3  mov     cs:qword_1401E3EA0, rdi
0x1400159da  call    cs:__imp_StartServiceCtrlDispatcherW
0x1400159e0  test    eax, eax
0x1400159e2  jnz     short loc_1400159ED
0x1400159e4  call    HrGetLastFailure
0x1400159e9  mov     esi, eax
0x1400159eb  jmp     short loc_140015A00
0x1400159ed  cmp     qword ptr [rdi+60h], 0
0x1400159f2  jnz     short loc_140015A00
0x1400159f4  cmp     dword ptr [rdi+44h], 1
0x1400159f8  mov     eax, 8007000Eh
0x1400159fd  cmovnz  esi, eax
0x140015a00  mov     eax, esi
0x140015a02  shr     eax, 1Fh
0x140015a05  test    al, al
0x140015a07  jz      short loc_140015A50
0x140015a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a10  lea     rax, WPP_GLOBAL_Control
0x140015a17  cmp     rcx, rax
0x140015a1a  jz      short loc_140015A3F
0x140015a1c  test    byte ptr [rcx+1Ch], 1
0x140015a20  jz      short loc_140015A3F
0x140015a22  mov     r9, [rdi+10h]
0x140015a26  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140015a2d  mov     rcx, [rcx+10h]
0x140015a31  mov     edx, 27h ; '''
0x140015a36  mov     [rsp+68h+var_48], esi
0x140015a3a  call    WPP_SF_Sd
0x140015a3f  test    rbx, rbx
0x140015a42  jz      loc_14001599F
0x140015a48  mov     rcx, rbx
0x140015a4b  jmp     loc_14001599A
0x140015a50  cmp     dword ptr [rdi+44h], 1
0x140015a54  jz      short loc_140015A98
0x140015a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a5d  lea     rax, WPP_GLOBAL_Control
0x140015a64  cmp     rcx, rax
0x140015a67  jz      short loc_140015A84
0x140015a69  test    byte ptr [rcx+1Ch], 1
0x140015a6d  jz      short loc_140015A84
0x140015a6f  mov     rcx, [rcx+10h]
0x140015a73  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140015a7a  mov     edx, 28h ; '('
0x140015a7f  call    WPP_SF_
0x140015a84  call    cs:__imp_GetCurrentProcess
0x140015a8a  mov     rcx, rax; hProcess
0x140015a8d  mov     edx, 2; uExitCode
0x140015a92  call    cs:__imp_TerminateProcess
0x140015a98  mov     rcx, [rdi+20h]; this
0x140015a9c  or      esi, 0FFFFFFFFh
0x140015a9f  mov     edx, esi; void *
0x140015aa1  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x140015aa6  mov     rcx, [rdi+38h]; this
0x140015aaa  test    rcx, rcx
0x140015aad  jz      short loc_140015AB6
0x140015aaf  mov     edx, esi; void *
0x140015ab1  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x140015ab6  mov     rcx, [rdi+28h]; WaitHandle
0x140015aba  test    rcx, rcx
0x140015abd  jz      short loc_140015AD1
0x140015abf  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140015ac3  call    cs:__imp_UnregisterWaitEx
0x140015ac9  mov     qword ptr [rdi+28h], 0
0x140015ad1  mov     rcx, [rdi+30h]
0x140015ad5  test    rcx, rcx
0x140015ad8  jz      short loc_140015AEF
0x140015ada  mov     rax, [rcx]
0x140015add  mov     rax, [rax+8]
0x140015ae1  call    cs:__guard_dispatch_icall_fptr
0x140015ae7  mov     qword ptr [rdi+30h], 0
0x140015aef  test    rbx, rbx
0x140015af2  jz      short loc_140015AFC
0x140015af4  mov     rcx, rbx; void *
0x140015af7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015afc  xor     eax, eax
0x140015afe  mov     rcx, [rsp+68h+var_10]
0x140015b03  xor     rcx, rsp; StackCookie
0x140015b06  call    __security_check_cookie
0x140015b0b  lea     r11, [rsp+68h+var_8]
0x140015b10  mov     rbx, [r11+18h]
0x140015b14  mov     rsi, [r11+20h]
0x140015b18  mov     rsp, r11
0x140015b1b  pop     rdi
0x140015b1c  retn
```
