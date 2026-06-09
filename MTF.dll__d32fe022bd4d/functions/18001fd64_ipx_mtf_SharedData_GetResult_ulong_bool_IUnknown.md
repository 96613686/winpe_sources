# ipx::mtf::SharedData::GetResult(ulong,bool,IUnknown * *)

- ea: `0x18001fd64`
- end: `0x180020102`
- name: `?GetResult@SharedData@mtf@ipx@@QEAAJK_NPEAPEAUIUnknown@@@Z`
- size: `926`
- prototype: `__int64 __fastcall(ipx::mtf::SharedData *__hidden this, unsigned int, bool, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001f850`

## callees

- `0x180006074`
- `0x18001fd64`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fda3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fda3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fdbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800200df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fdbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800200df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fd8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fdc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fd8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001fdc4`
- `CoreMessaging!CoreUICreate` at `0x18001fde8`
- `CoreMessaging!CoreUICreate` at `0x18001fde8`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x18001ff2a`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x18001ff2a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18001ff7c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18001ff7c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001ff72`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001ff72`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18001ff5c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18001ff5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall ipx::mtf::SharedData::GetResult(RTL_SRWLOCK *this, int a2, char a3, struct IUnknown **a4)
{
  int TickCount64; // ebx
  struct IUnknown *Ptr; // rcx
  DWORD v10; // ebx
  int v11; // eax
  int v12; // esi
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  signed int result; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  DWORD dwFlags; // [rsp+20h] [rbp-60h]
  int v28; // [rsp+30h] [rbp-50h]
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  tagMSG Msg; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v33; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v34; // [rsp+D8h] [rbp+58h] BYREF

  *a4 = 0;
  TickCount64 = GetTickCount64();
  v28 = TickCount64;
  while ( 1 )
  {
    AcquireSRWLockExclusive(this + 2);
    Ptr = (struct IUnknown *)this[6].Ptr;
    if ( Ptr )
      break;
    if ( this != (RTL_SRWLOCK *)-16LL )
      ReleaseSRWLockExclusive(this + 2);
    v10 = a2 + TickCount64 - GetTickCount64();
    if ( (int)v10 <= 0 )
      return -2147024638;
    if ( a3 )
    {
      v33 = 0;
      v11 = CoreUICreate(&v33);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v11,
          dwFlags);
        v26 = v33;
        v33 = 0;
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        return v12;
      }
      v29 = v33;
      v13 = (*(__int64 (__fastcall **)(__int64, PVOID, __int64 (__fastcall *)(), __int64 *))(*(_QWORD *)v33 + 272LL))(
              v33,
              this[5].Ptr,
              ipx::mtf::SharedData::GetResult_::_14_::MessageLoopStopper::WaitCallback,
              &v29);
      v12 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v13,
          dwFlags);
        v25 = v33;
        v33 = 0;
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        return v12;
      }
      v30 = v33;
      v34 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int64 *, __int64 *))(*(_QWORD *)v33 + 144LL))(
              v33,
              ipx::mtf::SharedData::GetResult_::_14_::MessageLoopStopper::WaitCallback,
              &v30,
              &v34);
      v12 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v14,
          dwFlags);
        v23 = v34;
        v34 = 0;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v24 = v33;
        v33 = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        return v12;
      }
      if ( v10 > 0x64 )
        v10 = 100;
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v34 + 80LL))(
              v34,
              10000LL * (int)(v10 + 1),
              0);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v15,
          dwFlags);
        v20 = v34;
        v34 = 0;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v21 = v33;
        v33 = 0;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        return v16;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 232LL))(v33);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 96LL))(v34);
      (*(void (__fastcall **)(__int64, PVOID))(*(_QWORD *)v33 + 280LL))(v33, this[5].Ptr);
      v17 = v34;
      v34 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v18 = v33;
      v33 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_24:
      TickCount64 = v28;
    }
    else
    {
      if ( v10 > 0x64 )
        v10 = 100;
      v19 = MsgWaitForMultipleObjectsEx(1u, &this[5].Ptr, v10, 0x48u, 4u);
      if ( v19 != 1 )
      {
        if ( v19 == -1 )
        {
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
          return result;
        }
        goto LABEL_24;
      }
      memset(&Msg, 0, sizeof(Msg));
      TickCount64 = v28;
      if ( PeekMessageW(&Msg, 0, 0x400u, 0x408u, 0xD80003u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
        goto LABEL_24;
      }
    }
  }
  this[6].Ptr = 0;
  *a4 = Ptr;
  if ( this != (RTL_SRWLOCK *)-16LL )
    ReleaseSRWLockExclusive(this + 2);
  return 0;
}

```

## disassembly

```asm
0x18001fd64  mov     [rsp-38h+arg_8], rbx
0x18001fd69  push    rbp
0x18001fd6a  push    rsi
0x18001fd6b  push    rdi
0x18001fd6c  push    r12
0x18001fd6e  push    r13
0x18001fd70  push    r14
0x18001fd72  push    r15
0x18001fd74  mov     rbp, rsp
0x18001fd77  sub     rsp, 80h
0x18001fd7e  mov     r15, r9
0x18001fd81  mov     r12b, r8b
0x18001fd84  mov     r13d, edx
0x18001fd87  mov     r14, rcx
0x18001fd8a  xor     esi, esi
0x18001fd8c  mov     [r9], rsi
0x18001fd8f  call    cs:__imp_GetTickCount64
0x18001fd95  mov     rbx, rax
0x18001fd98  mov     [rbp+var_50], rax
0x18001fd9c  lea     rdi, [r14+10h]
0x18001fda0  mov     rcx, rdi; SRWLock
0x18001fda3  call    cs:__imp_AcquireSRWLockExclusive
0x18001fda9  mov     rcx, [r14+30h]
0x18001fdad  test    rcx, rcx
0x18001fdb0  jnz     loc_1800200D0
0x18001fdb6  test    rdi, rdi
0x18001fdb9  jz      short loc_18001FDC4
0x18001fdbb  mov     rcx, rdi; SRWLock
0x18001fdbe  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fdc4  call    cs:__imp_GetTickCount64
0x18001fdca  sub     ebx, eax
0x18001fdcc  add     ebx, r13d
0x18001fdcf  test    ebx, ebx
0x18001fdd1  jle     loc_1800200C9
0x18001fdd7  test    r12b, r12b
0x18001fdda  jz      loc_18001FF0A
0x18001fde0  mov     [rbp+arg_0], rsi
0x18001fde4  lea     rcx, [rbp+arg_0]
0x18001fde8  call    cs:__imp_CoreUICreate
0x18001fdee  mov     esi, eax
0x18001fdf0  test    eax, eax
0x18001fdf2  js      loc_18002007A
0x18001fdf8  mov     rcx, [rbp+arg_0]
0x18001fdfc  mov     [rbp+var_48], rcx
0x18001fe00  mov     rax, [rcx]
0x18001fe03  lea     r9, [rbp+var_48]
0x18001fe07  lea     r8, _ipx__mtf__SharedData__GetResult____14___MessageLoopStopper__WaitCallback
0x18001fe0e  mov     rdx, [r14+28h]
0x18001fe12  mov     rax, [rax+110h]
0x18001fe19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe1e  mov     esi, eax
0x18001fe20  test    eax, eax
0x18001fe22  js      loc_180020041
0x18001fe28  mov     rcx, [rbp+arg_0]
0x18001fe2c  mov     [rbp+var_40], rcx
0x18001fe30  mov     [rbp+arg_18], 0
0x18001fe38  mov     rax, [rcx]
0x18001fe3b  lea     r9, [rbp+arg_18]
0x18001fe3f  lea     r8, [rbp+var_40]
0x18001fe43  lea     rdx, _ipx__mtf__SharedData__GetResult____14___MessageLoopStopper__WaitCallback
0x18001fe4a  mov     rax, [rax+90h]
0x18001fe51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe56  mov     esi, eax
0x18001fe58  test    eax, eax
0x18001fe5a  js      loc_18001FFEA
0x18001fe60  mov     eax, 64h ; 'd'
0x18001fe65  cmp     ebx, eax
0x18001fe67  cmova   ebx, eax
0x18001fe6a  mov     rcx, [rbp+arg_18]
0x18001fe6e  mov     r8, [rcx]
0x18001fe71  lea     eax, [rbx+1]
0x18001fe74  movsxd  rdx, eax
0x18001fe77  imul    rdx, 2710h
0x18001fe7e  mov     rax, [r8+50h]
0x18001fe82  xor     r8d, r8d
0x18001fe85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe8a  mov     ebx, eax
0x18001fe8c  xor     esi, esi
0x18001fe8e  test    eax, eax
0x18001fe90  js      loc_18001FF96
0x18001fe96  mov     rcx, [rbp+arg_0]
0x18001fe9a  mov     rax, [rcx]
0x18001fe9d  mov     rax, [rax+0E8h]
0x18001fea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fea9  mov     rcx, [rbp+arg_18]
0x18001fead  mov     rax, [rcx]
0x18001feb0  mov     rax, [rax+60h]
0x18001feb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feb9  mov     rcx, [rbp+arg_0]
0x18001febd  mov     rax, [rcx]
0x18001fec0  mov     rdx, [r14+28h]
0x18001fec4  mov     rax, [rax+118h]
0x18001fecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed0  nop
0x18001fed1  mov     rcx, [rbp+arg_18]
0x18001fed5  mov     [rbp+arg_18], rsi
0x18001fed9  test    rcx, rcx
0x18001fedc  jz      short loc_18001FEEB
0x18001fede  mov     rax, [rcx]
0x18001fee1  mov     rax, [rax+10h]
0x18001fee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feea  nop
0x18001feeb  mov     rcx, [rbp+arg_0]
0x18001feef  mov     [rbp+arg_0], rsi
0x18001fef3  test    rcx, rcx
0x18001fef6  jz      short loc_18001FF05
0x18001fef8  mov     rax, [rcx]
0x18001fefb  mov     rax, [rax+10h]
0x18001feff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff04  nop
0x18001ff05  jmp     loc_18001FF8D
0x18001ff0a  mov     eax, 64h ; 'd'
0x18001ff0f  cmp     ebx, eax
0x18001ff11  cmova   ebx, eax
0x18001ff14  lea     rdx, [r14+28h]; pHandles
0x18001ff18  mov     [rsp+80h+dwFlags], 4; dwFlags
0x18001ff20  lea     r9d, [rax-1Ch]; dwWakeMask
0x18001ff24  mov     r8d, ebx; dwMilliseconds
0x18001ff27  lea     ecx, [rax-63h]; nCount
0x18001ff2a  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001ff30  cmp     eax, 1
0x18001ff33  jnz     short loc_18001FF84
0x18001ff35  xorps   xmm0, xmm0
0x18001ff38  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18001ff3c  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18001ff40  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18001ff44  mov     [rsp+80h+dwFlags], 0D80003h; wRemoveMsg
0x18001ff4c  xor     edx, edx; hWnd
0x18001ff4e  mov     r9d, 408h; wMsgFilterMax
0x18001ff54  lea     r8d, [r9-8]; wMsgFilterMin
0x18001ff58  lea     rcx, [rbp+Msg]; lpMsg
0x18001ff5c  call    cs:__imp_PeekMessageW
0x18001ff62  test    eax, eax
0x18001ff64  mov     rbx, [rbp+var_50]
0x18001ff68  jz      loc_18001FDA0
0x18001ff6e  lea     rcx, [rbp+Msg]; lpMsg
0x18001ff72  call    cs:__imp_TranslateMessage
0x18001ff78  lea     rcx, [rbp+Msg]; lpMsg
0x18001ff7c  call    cs:__imp_DispatchMessageW
0x18001ff82  jmp     short loc_18001FF8D
0x18001ff84  cmp     eax, 0FFFFFFFFh
0x18001ff87  jz      loc_1800200B5
0x18001ff8d  mov     rbx, [rbp+var_50]
0x18001ff91  jmp     loc_18001FDA0
0x18001ff96  mov     rcx, [rbp+38h]; this
0x18001ff9a  mov     r9d, ebx; char *
0x18001ff9d  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18001ffa4  mov     edx, 0F0h; void *
0x18001ffa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ffae  nop
0x18001ffaf  mov     rcx, [rbp+arg_18]
0x18001ffb3  mov     [rbp+arg_18], rsi
0x18001ffb7  test    rcx, rcx
0x18001ffba  jz      short loc_18001FFC9
0x18001ffbc  mov     rax, [rcx]
0x18001ffbf  mov     rax, [rax+10h]
0x18001ffc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffc8  nop
0x18001ffc9  mov     rcx, [rbp+arg_0]
0x18001ffcd  mov     [rbp+arg_0], rsi
0x18001ffd1  test    rcx, rcx
0x18001ffd4  jz      short loc_18001FFE3
0x18001ffd6  mov     rax, [rcx]
0x18001ffd9  mov     rax, [rax+10h]
0x18001ffdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffe2  nop
0x18001ffe3  mov     eax, ebx
0x18001ffe5  jmp     loc_1800200E7
0x18001ffea  mov     rcx, [rbp+38h]; this
0x18001ffee  mov     r9d, esi; char *
0x18001fff1  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18001fff8  mov     edx, 0ECh; void *
0x18001fffd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020002  nop
0x180020003  mov     rcx, [rbp+arg_18]
0x180020007  mov     [rbp+arg_18], 0
0x18002000f  test    rcx, rcx
0x180020012  jz      short loc_180020021
0x180020014  mov     rax, [rcx]
0x180020017  mov     rax, [rax+10h]
0x18002001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020020  nop
0x180020021  mov     rcx, [rbp+arg_0]
0x180020025  mov     [rbp+arg_0], 0
0x18002002d  test    rcx, rcx
0x180020030  jz      short loc_18002003F
0x180020032  mov     rax, [rcx]
0x180020035  mov     rax, [rax+10h]
0x180020039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002003e  nop
0x18002003f  jmp     short loc_1800200B1
0x180020041  mov     rcx, [rbp+38h]; this
0x180020045  mov     r9d, esi; char *
0x180020048  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002004f  mov     edx, 0E6h; void *
0x180020054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020059  nop
0x18002005a  mov     rcx, [rbp+arg_0]
0x18002005e  mov     [rbp+arg_0], 0
0x180020066  test    rcx, rcx
0x180020069  jz      short loc_180020078
0x18002006b  mov     rax, [rcx]
0x18002006e  mov     rax, [rax+10h]
0x180020072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020077  nop
0x180020078  jmp     short loc_1800200B1
0x18002007a  mov     rcx, [rbp+38h]; this
0x18002007e  mov     r9d, esi; char *
0x180020081  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180020088  mov     edx, 0E1h; void *
0x18002008d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020092  nop
0x180020093  mov     rcx, [rbp+arg_0]
0x180020097  mov     [rbp+arg_0], 0
0x18002009f  test    rcx, rcx
0x1800200a2  jz      short loc_1800200B1
0x1800200a4  mov     rax, [rcx]
0x1800200a7  mov     rax, [rax+10h]
0x1800200ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200b0  nop
0x1800200b1  mov     eax, esi
0x1800200b3  jmp     short loc_1800200E7
0x1800200b5  call    cs:__imp_GetLastError
0x1800200bb  test    eax, eax
0x1800200bd  jle     short loc_1800200E7
0x1800200bf  movzx   eax, ax
0x1800200c2  or      eax, 80070000h
0x1800200c7  jmp     short loc_1800200E7
0x1800200c9  mov     eax, 80070102h
0x1800200ce  jmp     short loc_1800200E7
0x1800200d0  mov     [r14+30h], rsi
0x1800200d4  mov     [r15], rcx
0x1800200d7  test    rdi, rdi
0x1800200da  jz      short loc_1800200E5
0x1800200dc  mov     rcx, rdi; SRWLock
0x1800200df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800200e5  xor     eax, eax
0x1800200e7  mov     rbx, [rsp+80h+arg_8]
0x1800200ef  add     rsp, 80h
0x1800200f6  pop     r15
0x1800200f8  pop     r14
0x1800200fa  pop     r13
0x1800200fc  pop     r12
0x1800200fe  pop     rdi
0x1800200ff  pop     rsi
0x180020100  pop     rbp
0x180020101  retn
```
