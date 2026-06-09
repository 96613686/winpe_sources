# PhoneController::_CreateDialQueue(PhoneLine *,ushort const *,ushort const *,ulong)

- ea: `0x180036ce4`
- end: `0x180036e81`
- name: `?_CreateDialQueue@PhoneController@@AEAAJPEAVPhoneLine@@PEBG1K@Z`
- size: `413`
- prototype: `__int64 __usercall@<rax>(PhoneController *__hidden this@<rcx>, struct PhoneLine *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037804`

## callees

- `0x180006e94`
- `0x180023f54`
- `0x18002c574`
- `0x18002c580`
- `0x180036ce4`
- `0x180046ce4`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036d1c`

## string_xrefs

- `0x180036d10`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036ded`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036e27`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180036e59`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_CreateDialQueue(
        PhoneController *this,
        struct PhoneLine *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int16 a5)
{
  __int64 v8; // rcx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 (__fastcall *v10)(PhoneController *, struct PhoneLine *, unsigned __int64, const unsigned __int16 *, _QWORD, int, int, char *); // r14
  BackTraceCollection *v11; // rcx
  int v12; // esi
  int Instance; // eax
  __int64 v14; // rbx
  int v15; // eax
  _QWORD v17[9]; // [rsp+50h] [rbp-48h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v8, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5535);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  PhoneController::_ReleaseDialQueue(this);
  v9 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 27);
  v10 = *(__int64 (__fastcall **)(PhoneController *, struct PhoneLine *, unsigned __int64, const unsigned __int16 *, _QWORD, int, int, char *))(*(_QWORD *)this + 848LL);
  if ( v9 )
    (**v9)(v9, 1);
  *((_QWORD *)this + 27) = 0;
  v12 = v10(
          this,
          a2,
          -(__int64)(this != 0) & ((unsigned __int64)this + 8),
          a3,
          *((_QWORD *)this + 61),
          a5 & 0x100,
          a5 & 0x1000,
          (char *)this + 216);
  if ( v12 == -2147024891 )
  {
    if ( (a5 & 1) == 0 )
    {
      v17[0] = 0;
      Instance = DialingErrorMessage::CreateInstance(0, v17);
      if ( Instance < 0 )
        Log_HREvent_7(
          (unsigned int)Instance,
          0,
          "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
          5554);
      v14 = v17[0];
      if ( v17[0] )
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 26) + 40LL))(
                *((_QWORD *)this + 26),
                v17[0]);
        if ( v15 < 0 )
          Log_HREvent_7(
            (unsigned int)v15,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            5558);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    goto LABEL_15;
  }
  if ( v12 < 0 )
  {
LABEL_15:
    BackTraceCollection::Capture(v11, v12);
    Log_HREvent_7((unsigned int)v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 5562);
    return (unsigned int)v12;
  }
  return 0;
}

```

## disassembly

```asm
0x180036ce4  push    rbx
0x180036ce6  push    rbp
0x180036ce7  push    rsi
0x180036ce8  push    rdi
0x180036ce9  push    r12
0x180036ceb  push    r14
0x180036ced  push    r15
0x180036cef  sub     rsp, 60h
0x180036cf3  mov     r12, r8
0x180036cf6  mov     r15, rdx
0x180036cf9  mov     rdi, rcx
0x180036cfc  call    cs:__imp_GetCurrentThreadId
0x180036d02  cmp     [rdi+0F0h], eax
0x180036d08  jz      short loc_180036D2F
0x180036d0a  mov     r8d, 159Fh
0x180036d10  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036d17  call    Log_AssertionEvent_3
0x180036d1c  call    cs:__imp_GetCurrentThreadId
0x180036d22  cmp     [rdi+0F0h], eax
0x180036d28  jz      short loc_180036D2F
0x180036d2a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180036d2f  mov     rcx, rdi; this
0x180036d32  call    ?_ReleaseDialQueue@PhoneController@@IEAAXXZ; PhoneController::_ReleaseDialQueue(void)
0x180036d37  mov     rax, [rdi]
0x180036d3a  lea     rsi, [rdi+0D8h]
0x180036d41  mov     rcx, [rsi]
0x180036d44  mov     r14, [rax+350h]
0x180036d4b  test    rcx, rcx
0x180036d4e  jz      short loc_180036D60
0x180036d50  mov     rax, [rcx]
0x180036d53  mov     edx, 1
0x180036d58  mov     rax, [rax]
0x180036d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d60  mov     ebp, [rsp+98h+arg_20]
0x180036d67  lea     r8, [rdi+8]
0x180036d6b  mov     [rsp+98h+var_60], rsi
0x180036d70  mov     r11d, ebp
0x180036d73  and     r11d, 100h
0x180036d7a  mov     qword ptr [rsi], 0
0x180036d81  mov     ebx, ebp
0x180036d83  mov     rcx, rdi
0x180036d86  and     ebx, 1000h
0x180036d8c  mov     r9, r12
0x180036d8f  neg     rcx
0x180036d92  mov     [rsp+98h+var_68], ebx
0x180036d96  mov     rcx, [rdi+1E8h]
0x180036d9d  mov     rdx, r15
0x180036da0  sbb     r10, r10
0x180036da3  mov     [rsp+98h+var_70], r11d
0x180036da8  mov     [rsp+98h+var_78], rcx
0x180036dad  and     r8, r10
0x180036db0  mov     rcx, rdi
0x180036db3  mov     rax, r14
0x180036db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036dbb  mov     esi, eax
0x180036dbd  cmp     eax, 80070005h
0x180036dc2  jnz     loc_180036E48
0x180036dc8  test    bpl, 1
0x180036dcc  jnz     short loc_180036E4C
0x180036dce  lea     rdx, [rsp+98h+var_48]
0x180036dd3  mov     [rsp+98h+var_48], 0
0x180036ddc  xor     ecx, ecx
0x180036dde  call    ?CreateInstance@DialingErrorMessage@@SAJW4DIALINGERROR@@PEAPEAV1@@Z; DialingErrorMessage::CreateInstance(DIALINGERROR,DialingErrorMessage * *)
0x180036de3  test    eax, eax
0x180036de5  jns     short loc_180036DFD
0x180036de7  mov     r9d, 15B2h
0x180036ded  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036df4  xor     edx, edx
0x180036df6  mov     ecx, eax
0x180036df8  call    Log_HREvent_7
0x180036dfd  mov     rbx, [rsp+98h+var_48]
0x180036e02  test    rbx, rbx
0x180036e05  jz      short loc_180036E4C
0x180036e07  mov     rcx, [rdi+0D0h]
0x180036e0e  mov     rdx, rbx
0x180036e11  mov     rax, [rcx]
0x180036e14  mov     rax, [rax+28h]
0x180036e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e1d  test    eax, eax
0x180036e1f  jns     short loc_180036E37
0x180036e21  mov     r9d, 15B6h
0x180036e27  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036e2e  xor     edx, edx
0x180036e30  mov     ecx, eax
0x180036e32  call    Log_HREvent_7
0x180036e37  mov     rax, [rbx]
0x180036e3a  mov     rcx, rbx
0x180036e3d  mov     rax, [rax+10h]
0x180036e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e46  jmp     short loc_180036E4C
0x180036e48  test    esi, esi
0x180036e4a  jns     short loc_180036E70
0x180036e4c  mov     edx, esi; int
0x180036e4e  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180036e53  mov     r9d, 15BAh
0x180036e59  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180036e60  mov     edx, 1
0x180036e65  mov     ecx, esi
0x180036e67  call    Log_HREvent_7
0x180036e6c  mov     eax, esi
0x180036e6e  jmp     short loc_180036E72
0x180036e70  xor     eax, eax
0x180036e72  add     rsp, 60h
0x180036e76  pop     r15
0x180036e78  pop     r14
0x180036e7a  pop     r12
0x180036e7c  pop     rdi
0x180036e7d  pop     rsi
0x180036e7e  pop     rbp
0x180036e7f  pop     rbx
0x180036e80  retn
```
