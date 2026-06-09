# CBridgeWindow::SetHostedWindow(HWND__ *)

- ea: `0x18003ed70`
- end: `0x18003ef6f`
- name: `?SetHostedWindow@CBridgeWindow@@UEAAJPEAUHWND__@@@Z`
- size: `511`
- prototype: `int(CBridgeWindow *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013244`
- `0x18003ed70`
- `0x18003ef78`
- `0x18005659c`
- `0x18005943c`
- `0x18005b474`
- `0x18005b51c`
- `0x18005bcd4`
- `0x18005c000`
- `0x18005c56c`
- `0x18005c610`
- `0x18005d4e4`
- `0x1800d7c1c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ee18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ee18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee9e`
- `USER32!GetWindowThreadProcessId` at `0x18003ee12`
- `USER32!GetWindowThreadProcessId` at `0x18003ee12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eeb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eeb6`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::SetHostedWindow(CBridgeWindow *this, CallerIdentity *a2)
{
  CBridgeWindow *v2; // r14
  int started; // ebx
  __int64 v6; // rcx
  HWND v7; // rdx
  int v8; // eax
  bool v9; // al
  unsigned __int16 **v10; // r8
  __int64 v11; // rcx
  unsigned __int16 **v12; // r8
  __int64 v13; // rbx
  struct CCrashDetector::CHandler *v14; // rax
  DWORD dwProcessId; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  v2 = (CBridgeWindow *)((char *)this - 48);
  if ( *((_QWORD *)this + 8) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
    }
    v6 = *((_QWORD *)this + 37);
    v7 = (HWND)*((_QWORD *)this + 8);
    if ( v6 )
      v8 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v6 + 40LL))(v6, v7);
    else
      v8 = _SetOwnerWindow((HWND)a2, v7);
    started = v8;
    if ( v8 >= 0 )
    {
      dwProcessId = 0;
      GetWindowThreadProcessId((HWND)a2, &dwProcessId);
      v9 = dwProcessId != GetCurrentProcessId();
      *((_BYTE *)this + 99) = v9;
      if ( v9 )
        CBridgeWindow::_AttachOrDetachInputQueues(v2, 0, (HWND)a2, 0);
      started = CBridgeWindow::_EnsureRegisteredPLMExemption(v2, (HWND)a2);
      if ( started >= 0 )
      {
        started = 0;
        hMem = 0;
        if ( !*((_QWORD *)this + 34) )
        {
          LocalFree(0);
          if ( CallerIdentity::GetPsmKeyFromWindow(a2, (HWND)&hMem, v10) >= 0 )
          {
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease((char *)this + 272);
            started = CBridgeWindow::_BeginTaskCompletion(v11, (HWND)a2, 0x100000u, (_QWORD *)this + 34);
          }
        }
        LocalFree(hMem);
        if ( started >= 0 )
        {
          CoTaskMemFree(*((LPVOID *)this + 19));
          CallerIdentity::GetImmersiveAppIdFromWindow(a2, (HWND)this + 38, v12);
          hMem = 0;
          if ( *((_QWORD *)this + 32)
            && (int)WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(
                      (char *)this + 256,
                      &hMem) >= 0
            && hMem )
          {
            (*(void (__fastcall **)(HLOCAL, CallerIdentity *))(*(_QWORD *)hMem + 24LL))(hMem, a2);
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
          v13 = *((_QWORD *)this + 8);
          v14 = (struct CCrashDetector::CHandler *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v14 )
          {
            *((_QWORD *)v14 + 1) = v13;
            *(_QWORD *)v14 = off_1800E8C90;
          }
          started = CCrashDetector::_StartMonitoringThreadOfWindow((char *)this + 304, (HWND)a2, v14);
          if ( started >= 0 )
          {
            *((_QWORD *)this + 18) = a2;
            CBridgeWindow::_SyncWindowPosition(v2);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18003ed70  mov     [rsp+arg_8], rbx
0x18003ed75  push    rbp
0x18003ed76  push    rsi
0x18003ed77  push    rdi
0x18003ed78  push    r14
0x18003ed7a  push    r15
0x18003ed7c  sub     rsp, 30h
0x18003ed80  lea     r14, [rcx-30h]
0x18003ed84  mov     rdi, rdx
0x18003ed87  mov     r9, [r14+70h]
0x18003ed8b  mov     rsi, rcx
0x18003ed8e  test    r9, r9
0x18003ed91  jnz     short loc_18003ED9D
0x18003ed93  mov     ebx, 8000FFFFh
0x18003ed98  jmp     loc_18003EF5C
0x18003ed9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eda4  lea     rax, WPP_GLOBAL_Control
0x18003edab  cmp     rcx, rax
0x18003edae  jz      short loc_18003EDCF
0x18003edb0  test    byte ptr [rcx+1Ch], 1
0x18003edb4  jz      short loc_18003EDCF
0x18003edb6  cmp     byte ptr [rcx+19h], 4
0x18003edba  jb      short loc_18003EDCF
0x18003edbc  mov     rcx, [rcx+10h]
0x18003edc0  mov     edx, 0Bh
0x18003edc5  mov     [rsp+58h+var_38], rdi
0x18003edca  call    WPP_SF_qq
0x18003edcf  mov     rcx, [rsi+128h]
0x18003edd6  lea     r15, [rsi+40h]
0x18003edda  mov     rdx, [r15]; hWnd
0x18003eddd  test    rcx, rcx
0x18003ede0  jnz     short loc_18003EDEC
0x18003ede2  mov     rcx, rdi; hWndInsertAfter
0x18003ede5  call    ?_SetOwnerWindow@@YAJPEAUHWND__@@0@Z; _SetOwnerWindow(HWND__ *,HWND__ *)
0x18003edea  jmp     short loc_18003EDF8
0x18003edec  mov     rax, [rcx]
0x18003edef  mov     rax, [rax+28h]
0x18003edf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edf8  mov     ebx, eax
0x18003edfa  test    eax, eax
0x18003edfc  js      loc_18003EF5C
0x18003ee02  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x18003ee07  mov     [rsp+58h+dwProcessId], 0
0x18003ee0f  mov     rcx, rdi; hWnd
0x18003ee12  call    cs:__imp_GetWindowThreadProcessId
0x18003ee18  call    cs:__imp_GetCurrentProcessId
0x18003ee1e  cmp     [rsp+58h+dwProcessId], eax
0x18003ee22  setnz   al
0x18003ee25  mov     [rsi+63h], al
0x18003ee28  test    al, al
0x18003ee2a  jz      short loc_18003EE3C
0x18003ee2c  xor     r9d, r9d; bool
0x18003ee2f  mov     r8, rdi; HWND
0x18003ee32  xor     edx, edx; bool
0x18003ee34  mov     rcx, r14; this
0x18003ee37  call    ?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z; CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)
0x18003ee3c  mov     rdx, rdi; HWND
0x18003ee3f  mov     rcx, r14; this
0x18003ee42  call    ?_EnsureRegisteredPLMExemption@CBridgeWindow@@AEAAJPEAUHWND__@@@Z; CBridgeWindow::_EnsureRegisteredPLMExemption(HWND__ *)
0x18003ee47  mov     ebx, eax
0x18003ee49  test    eax, eax
0x18003ee4b  js      loc_18003EF5C
0x18003ee51  xor     ebx, ebx
0x18003ee53  lea     rbp, [rsi+110h]
0x18003ee5a  mov     [rsp+58h+hMem], rbx
0x18003ee5f  cmp     [rbp+0], rbx
0x18003ee63  jnz     short loc_18003EE99
0x18003ee65  xor     ecx, ecx; hMem
0x18003ee67  call    cs:__imp_LocalFree
0x18003ee6d  lea     rdx, [rsp+58h+hMem]; HWND
0x18003ee72  mov     rcx, rdi; this
0x18003ee75  call    ?GetPsmKeyFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetPsmKeyFromWindow(HWND__ *,ushort * *)
0x18003ee7a  test    eax, eax
0x18003ee7c  js      short loc_18003EE99
0x18003ee7e  mov     rcx, rbp
0x18003ee81  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18003ee86  mov     r9, rbp
0x18003ee89  mov     r8d, 100000h
0x18003ee8f  mov     rdx, rdi
0x18003ee92  call    ?_BeginTaskCompletion@CBridgeWindow@@AEAAJPEAUHWND__@@W4PLM_TASKCOMPLETION_CATEGORY_FLAGS@@PEAPEAUIOSTaskCompletion@@@Z; CBridgeWindow::_BeginTaskCompletion(HWND__ *,PLM_TASKCOMPLETION_CATEGORY_FLAGS,IOSTaskCompletion * *)
0x18003ee97  mov     ebx, eax
0x18003ee99  mov     rcx, [rsp+58h+hMem]; hMem
0x18003ee9e  call    cs:__imp_LocalFree
0x18003eea4  test    ebx, ebx
0x18003eea6  js      loc_18003EF5C
0x18003eeac  lea     rbx, [rsi+98h]
0x18003eeb3  mov     rcx, [rbx]; pv
0x18003eeb6  call    cs:__imp_CoTaskMemFree
0x18003eebc  mov     rdx, rbx; HWND
0x18003eebf  mov     rcx, rdi; this
0x18003eec2  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x18003eec7  lea     rcx, [rsi+100h]
0x18003eece  mov     [rsp+58h+hMem], 0
0x18003eed7  cmp     qword ptr [rcx], 0
0x18003eedb  jz      short loc_18003EF04
0x18003eedd  lea     rdx, [rsp+58h+hMem]
0x18003eee2  call    ??$WeakRefAs@V?$ComPtrRef@V?$ComPtr@UIHostedApplicationEventSink@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@@YAJAEBVWeakRef@WRL@Microsoft@@V?$ComPtrRef@V?$ComPtr@UIHostedApplicationEventSink@@@WRL@Microsoft@@@Details@12@@Z; WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(Microsoft::WRL::WeakRef const &,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>)
0x18003eee7  test    eax, eax
0x18003eee9  js      short loc_18003EF04
0x18003eeeb  mov     rcx, [rsp+58h+hMem]
0x18003eef0  test    rcx, rcx
0x18003eef3  jz      short loc_18003EF04
0x18003eef5  mov     rax, [rcx]
0x18003eef8  mov     rdx, rdi
0x18003eefb  mov     rax, [rax+18h]
0x18003eeff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef04  lea     rcx, [rsp+58h+hMem]
0x18003ef09  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18003ef0e  mov     rbx, [r15]
0x18003ef11  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ef18  mov     ecx, 10h; unsigned __int64
0x18003ef1d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ef22  test    rax, rax
0x18003ef25  jz      short loc_18003EF35
0x18003ef27  lea     rcx, off_1800E8C90
0x18003ef2e  mov     [rax+8], rbx
0x18003ef32  mov     [rax], rcx
0x18003ef35  mov     r8, rax; struct CCrashDetector::CHandler *
0x18003ef38  lea     rcx, [rsi+130h]; pv
0x18003ef3f  mov     rdx, rdi; hWnd
0x18003ef42  call    ?_StartMonitoringThreadOfWindow@CCrashDetector@@AEAAJPEAUHWND__@@PEAVCHandler@1@@Z; CCrashDetector::_StartMonitoringThreadOfWindow(HWND__ *,CCrashDetector::CHandler *)
0x18003ef47  mov     ebx, eax
0x18003ef49  test    eax, eax
0x18003ef4b  js      short loc_18003EF5C
0x18003ef4d  mov     rcx, r14; this
0x18003ef50  mov     [rsi+90h], rdi
0x18003ef57  call    ?_SyncWindowPosition@CBridgeWindow@@AEAAXXZ; CBridgeWindow::_SyncWindowPosition(void)
0x18003ef5c  mov     eax, ebx
0x18003ef5e  mov     rbx, [rsp+58h+arg_8]
0x18003ef63  add     rsp, 30h
0x18003ef67  pop     r15
0x18003ef69  pop     r14
0x18003ef6b  pop     rdi
0x18003ef6c  pop     rsi
0x18003ef6d  pop     rbp
0x18003ef6e  retn
```
