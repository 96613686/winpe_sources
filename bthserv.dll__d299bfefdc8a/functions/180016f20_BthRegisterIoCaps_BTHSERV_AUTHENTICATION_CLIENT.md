# BthRegisterIoCaps(BTHSERV_AUTHENTICATION_CLIENT *)

- ea: `0x180016f20`
- end: `0x1800171ea`
- name: `?BthRegisterIoCaps@@YAHPEAUBTHSERV_AUTHENTICATION_CLIENT@@@Z`
- size: `714`
- prototype: `__int64 __fastcall(struct BTHSERV_AUTHENTICATION_CLIENT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ab58`
- `0x1800171f0`

## callees

- `0x180001790`
- `0x18000f2e8`
- `0x180011194`
- `0x180011250`
- `0x180016f20`
- `0x180018aa4`
- `0x1800329fc`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016f6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017069`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800170c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800170c0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001705f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001705f`

## pseudocode

```c
__int64 __fastcall BthRegisterIoCaps(struct BTHSERV_AUTHENTICATION_CLIENT *a1)
{
  struct _OVERLAPPED *lpOverlapped; // rdi
  HANDLE EventW; // rax
  int v4; // edx
  __int64 v5; // r8
  char v6; // si
  __int64 v7; // rdx
  __int64 v8; // r8
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v11; // rdi
  int lpOutBuffer; // [rsp+20h] [rbp-59h]
  int lpOutBuffera; // [rsp+20h] [rbp-59h]
  DWORD nOutBufferSize; // [rsp+28h] [rbp-51h]
  DWORD nOutBufferSizea; // [rsp+28h] [rbp-51h]
  HANDLE *v16; // [rsp+70h] [rbp-9h] BYREF
  volatile signed __int32 *v17; // [rsp+78h] [rbp-1h]
  __int128 InBuffer; // [rsp+80h] [rbp+7h] BYREF
  int v19; // [rsp+90h] [rbp+17h]

  lpOverlapped = (struct _OVERLAPPED *)((char *)a1 + 96);
  InBuffer = 0;
  v19 = 0;
  if ( *((_QWORD *)a1 + 15) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 15) = EventW;
  if ( !EventW )
    return 0;
  v6 = 1;
  LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sDDiD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, *((_QWORD *)WPP_GLOBAL_Control + 5));
  *(_QWORD *)&InBuffer = *((_QWORD *)a1 + 10);
  *((_QWORD *)&InBuffer + 1) = *((_QWORD *)a1 + 6);
  v19 = *((_DWORD *)a1 + 23);
  BthServGlobals::GetSafeRadioHandle(&Globals, &v16, v5);
  if ( !v16 || (char *)*v16 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v6 = 0;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v6;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        lpOutBuffer,
        nOutBufferSize,
        13,
        (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
    }
    goto LABEL_32;
  }
  if ( DeviceIoControl(*v16, 0x4111CCu, &InBuffer, 0x14u, 0, 0, 0, lpOverlapped) || GetLastError() != 997 )
  {
    CloseHandle(*((HANDLE *)a1 + 15));
    *((_QWORD *)a1 + 15) = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v6 = 0;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v6;
      WPP_RECORDER_AND_TRACE_SF_sDDi(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        lpOutBuffera,
        nOutBufferSizea,
        12,
        (__int64)WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids);
    }
LABEL_32:
    v11 = v17;
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v11)(v11, v7, v8);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    return 0;
  }
  v9 = v17;
  if ( v17 && _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  return 1;
}

```

## disassembly

```asm
0x180016f20  push    rbp
0x180016f22  push    rbx
0x180016f23  push    rsi
0x180016f24  push    rdi
0x180016f25  push    r12
0x180016f27  push    r15
0x180016f29  lea     rbp, [rsp-2Fh]
0x180016f2e  sub     rsp, 0A8h
0x180016f35  mov     rax, cs:__security_cookie
0x180016f3c  xor     rax, rsp
0x180016f3f  mov     [rbp+57h+var_38], rax
0x180016f43  xor     eax, eax
0x180016f45  lea     rdi, [rcx+60h]
0x180016f49  xorps   xmm0, xmm0
0x180016f4c  mov     rbx, rcx
0x180016f4f  movups  [rbp+57h+InBuffer], xmm0
0x180016f53  mov     [rbp+57h+var_40], eax
0x180016f56  cmp     [rdi+18h], rax
0x180016f5a  jz      short loc_180016F61
0x180016f5c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180016f61  xor     r9d, r9d; lpName
0x180016f64  xor     r8d, r8d; bInitialState
0x180016f67  xor     edx, edx; bManualReset
0x180016f69  xor     ecx, ecx; lpEventAttributes
0x180016f6b  call    cs:__imp_CreateEventW
0x180016f71  mov     [rbx+78h], rax
0x180016f75  test    rax, rax
0x180016f78  jz      loc_1800171CC
0x180016f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f85  lea     r15, WPP_GLOBAL_Control
0x180016f8c  mov     esi, 1
0x180016f91  cmp     rcx, r15
0x180016f94  jz      short loc_180016FA1
0x180016f96  cmp     byte ptr [rcx+19h], 5
0x180016f9a  jb      short loc_180016FA1
0x180016f9c  mov     dl, sil
0x180016f9f  jmp     short loc_180016FA3
0x180016fa1  xor     dl, dl
0x180016fa3  lea     r12, WPP_RECORDER_INITIALIZED
0x180016faa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180016fb1  setnz   r8b
0x180016fb5  test    dl, dl
0x180016fb7  jnz     short loc_180016FBE
0x180016fb9  test    r8b, r8b
0x180016fbc  jz      short loc_180016FE9
0x180016fbe  mov     eax, [rbx+5Ch]
0x180016fc1  mov     r9, [rcx+28h]
0x180016fc5  mov     rcx, [rcx+10h]
0x180016fc9  mov     [rsp+0D0h+var_70], eax
0x180016fcd  mov     rax, [rbx+30h]
0x180016fd1  mov     [rsp+0D0h+var_78], rax
0x180016fd6  mov     eax, [rbx+50h]
0x180016fd9  mov     [rsp+0D0h+var_80], eax
0x180016fdd  mov     eax, [rbx+54h]
0x180016fe0  mov     [rsp+0D0h+var_88], eax
0x180016fe4  call    WPP_RECORDER_AND_TRACE_SF_sDDiD
0x180016fe9  mov     eax, [rbx+50h]
0x180016fec  lea     rdx, [rbp+57h+var_60]
0x180016ff0  mov     dword ptr [rbp+57h+InBuffer], eax
0x180016ff3  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x180016ffa  mov     eax, [rbx+54h]
0x180016ffd  mov     dword ptr [rbp+57h+InBuffer+4], eax
0x180017000  mov     rax, [rbx+30h]
0x180017004  mov     qword ptr [rbp+57h+InBuffer+8], rax
0x180017008  mov     eax, [rbx+5Ch]
0x18001700b  mov     [rbp+57h+var_40], eax
0x18001700e  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x180017013  mov     rcx, [rbp+57h+var_60]
0x180017017  test    rcx, rcx
0x18001701a  jz      loc_180017138
0x180017020  mov     rcx, [rcx]; hDevice
0x180017023  lea     rax, [rcx-1]
0x180017027  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001702b  ja      loc_180017138
0x180017031  mov     [rsp+0D0h+lpOverlapped], rdi; lpOverlapped
0x180017036  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18001703a  mov     [rsp+0D0h+lpBytesReturned], 0; lpBytesReturned
0x180017043  mov     r9d, 14h; nInBufferSize
0x180017049  mov     [rsp+0D0h+nOutBufferSize], 0; nOutBufferSize
0x180017051  mov     edx, 4111CCh; dwIoControlCode
0x180017056  mov     [rsp+0D0h+lpOutBuffer], 0; lpOutBuffer
0x18001705f  call    cs:__imp_DeviceIoControl
0x180017065  test    eax, eax
0x180017067  jnz     short loc_1800170BC
0x180017069  call    cs:__imp_GetLastError
0x18001706f  cmp     eax, 3E5h
0x180017074  jnz     short loc_1800170BC
0x180017076  mov     rdi, [rbp+57h+var_58]
0x18001707a  test    rdi, rdi
0x18001707d  jz      short loc_1800170B5
0x18001707f  or      ebx, 0FFFFFFFFh
0x180017082  mov     eax, ebx
0x180017084  lock xadd [rdi+8], eax
0x180017089  add     eax, ebx
0x18001708b  jnz     short loc_1800170B5
0x18001708d  mov     rax, [rdi]
0x180017090  mov     rcx, rdi
0x180017093  mov     rax, [rax]
0x180017096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001709b  mov     edx, ebx
0x18001709d  lock xadd [rdi+0Ch], edx
0x1800170a2  add     edx, ebx
0x1800170a4  jnz     short loc_1800170B5
0x1800170a6  mov     rdx, [rdi]
0x1800170a9  mov     rcx, rdi
0x1800170ac  mov     rax, [rdx+8]
0x1800170b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b5  mov     eax, esi
0x1800170b7  jmp     loc_1800171CE
0x1800170bc  mov     rcx, [rbx+78h]; hObject
0x1800170c0  call    cs:__imp_CloseHandle
0x1800170c6  mov     qword ptr [rbx+78h], 0
0x1800170ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170d5  cmp     rcx, r15
0x1800170d8  jz      short loc_1800170E0
0x1800170da  cmp     byte ptr [rcx+19h], 2
0x1800170de  jnb     short loc_1800170E3
0x1800170e0  xor     sil, sil
0x1800170e3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800170ea  setnz   r8b
0x1800170ee  test    sil, sil
0x1800170f1  jnz     short loc_1800170FC
0x1800170f3  test    r8b, r8b
0x1800170f6  jz      loc_18001718D
0x1800170fc  mov     rax, [rbx+30h]
0x180017100  mov     dl, sil
0x180017103  mov     r9, [rcx+28h]
0x180017107  mov     rcx, [rcx+10h]
0x18001710b  mov     [rsp+0D0h+var_78], rax
0x180017110  mov     eax, [rbx+50h]
0x180017113  mov     [rsp+0D0h+var_80], eax
0x180017117  mov     eax, [rbx+54h]
0x18001711a  mov     [rsp+0D0h+var_88], eax
0x18001711e  lea     rax, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180017125  mov     [rsp+0D0h+lpOverlapped], rax
0x18001712a  mov     word ptr [rsp+0D0h+lpBytesReturned], 0Ch
0x180017131  call    WPP_RECORDER_AND_TRACE_SF_sDDi
0x180017136  jmp     short loc_18001718D
0x180017138  mov     rcx, cs:WPP_GLOBAL_Control
0x18001713f  cmp     rcx, r15
0x180017142  jz      short loc_18001714A
0x180017144  cmp     byte ptr [rcx+19h], 3
0x180017148  jnb     short loc_18001714D
0x18001714a  xor     sil, sil
0x18001714d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180017154  setnz   r8b
0x180017158  test    sil, sil
0x18001715b  jnz     short loc_180017162
0x18001715d  test    r8b, r8b
0x180017160  jz      short loc_18001718D
0x180017162  mov     r9, [rcx+28h]
0x180017166  lea     rax, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x18001716d  mov     rcx, [rcx+10h]
0x180017171  mov     dl, sil
0x180017174  mov     [rsp+0D0h+var_88], 6
0x18001717c  mov     [rsp+0D0h+lpOverlapped], rax
0x180017181  mov     word ptr [rsp+0D0h+lpBytesReturned], 0Dh
0x180017188  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001718d  mov     rdi, [rbp+57h+var_58]
0x180017191  test    rdi, rdi
0x180017194  jz      short loc_1800171CC
0x180017196  or      ebx, 0FFFFFFFFh
0x180017199  mov     eax, ebx
0x18001719b  lock xadd [rdi+8], eax
0x1800171a0  add     eax, ebx
0x1800171a2  jnz     short loc_1800171CC
0x1800171a4  mov     rax, [rdi]
0x1800171a7  mov     rcx, rdi
0x1800171aa  mov     rax, [rax]
0x1800171ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b2  mov     eax, ebx
0x1800171b4  lock xadd [rdi+0Ch], eax
0x1800171b9  add     eax, ebx
0x1800171bb  jnz     short loc_1800171CC
0x1800171bd  mov     rax, [rdi]
0x1800171c0  mov     rcx, rdi
0x1800171c3  mov     rax, [rax+8]
0x1800171c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171cc  xor     eax, eax
0x1800171ce  mov     rcx, [rbp+57h+var_38]
0x1800171d2  xor     rcx, rsp; StackCookie
0x1800171d5  call    __security_check_cookie
0x1800171da  add     rsp, 0A8h
0x1800171e1  pop     r15
0x1800171e3  pop     r12
0x1800171e5  pop     rdi
0x1800171e6  pop     rsi
0x1800171e7  pop     rbx
0x1800171e8  pop     rbp
0x1800171e9  retn
```
