# CScheduler::WaitForWork(IMessageLoopExtensions *)

- ea: `0x180110540`
- end: `0x180110a9a`
- name: `?WaitForWork@CScheduler@@QEAAXPEAUIMessageLoopExtensions@@@Z`
- size: `1370`
- prototype: `void __fastcall(CScheduler *__hidden this, struct IMessageLoopExtensions *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010efa0`

## callees

- `0x1800096c4`
- `0x1800098f8`
- `0x180042de0`
- `0x180110480`
- `0x180110540`
- `0x180110aa0`
- `0x180186918`
- `0x180204100`
- `0x18020e30c`
- `0x180228490`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18011077c`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18011077c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180110719`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180110719`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801105ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801105ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110855`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180110a61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18011081b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18011081b`
- `ext-ms-win-ntuser-private-l1-1-1!DwmGetRemoteSessionOcclusionEvent` at `0x180110a6c`
- `ext-ms-win-ntuser-private-l1-1-1!DwmGetRemoteSessionOcclusionEvent` at `0x180110a6c`

## pseudocode

```c
void __fastcall CScheduler::WaitForWork(CScheduler *this, struct IMessageLoopExtensions *a2)
{
  __int64 v3; // rcx
  char *EventW; // rdi
  unsigned int v6; // r14d
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rbx
  DWORD v13; // eax
  bool v14; // r12
  unsigned __int8 v15; // r15
  unsigned __int8 v16; // r14
  unsigned __int8 v17; // di
  unsigned __int8 v18; // bl
  CDisplayManager *v19; // rcx
  __int64 v20; // r8
  int v21; // eax
  signed int LastError; // eax
  __int64 RemoteSessionOcclusionEvent; // rax
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  BOOL v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  ULONGLONG *v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+84h] [rbp-7Ch]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+90h] [rbp-70h] BYREF
  int *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  BOOL *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int *v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  int *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  void *retaddr; // [rsp+138h] [rbp+38h]

  *((_QWORD *)this + 6) = qword_1803BB0C8;
  v3 = qword_1803BB0D0;
  if ( (unsigned __int64)(qword_1803BB0D0 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( qword_1803BB0B8 )
    {
      if ( byte_1803BB0E2 )
      {
        RemoteSessionOcclusionEvent = DwmGetRemoteSessionOcclusionEvent();
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &qword_1803BB0D0,
          RemoteSessionOcclusionEvent);
      }
      else
      {
        EventW = (char *)CreateEventW(0, 0, 0, 0);
        v30 = (__int64)EventW;
        if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
          && (*(int (__fastcall **)(CDisplayManager *, char *, char *))(*(_QWORD *)qword_1803BB0B8 + 176LL))(
               qword_1803BB0B8,
               EventW,
               (char *)&qword_1803BB0D8 + 4) >= 0 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
            &qword_1803BB0D0,
            &v30);
          EventW = (char *)v30;
        }
        if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(EventW);
      }
      v3 = qword_1803BB0D0;
    }
    else
    {
      v3 = 0;
    }
  }
  *((_QWORD *)this + 7) = v3;
  v6 = (v3 != 0) + 4;
  CRenderThreadWaitTick::CRenderThreadWaitTick((CRenderThreadWaitTick *)&v29, (volatile unsigned __int64 *)a2);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_SCHEDULE_WFW_Start,
      v7,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&v30);
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Dwm_Compositor_Context,
      &WaitForWork_Start,
      v7,
      1u,
      (PEVENT_DATA_DESCRIPTOR)&v30);
  v24 = 0;
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(struct IMessageLoopExtensions *, _QWORD, char *, __int64, _DWORD, int *))(*(_QWORD *)a2 + 32LL))(
           a2,
           v6,
           (char *)this + 24,
           0xFFFFFFFFLL,
           0,
           &v24);
    if ( v8 >= 0 )
    {
      v9 = v24;
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x82u, 0);
      v9 = -1;
      v24 = -1;
    }
    if ( v9 < v6 )
      break;
    v10 = (*(__int64 (__fastcall **)(struct IMessageLoopExtensions *, __int64))(*(_QWORD *)a2 + 24LL))(a2, 3);
    if ( v10 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x91u, 0);
  }
  v30 = 0x10200000102LL;
  v11 = 0;
  v31 = 258;
  v32 = 258;
  do
  {
    v12 = v11;
    v13 = WaitForSingleObject(*((HANDLE *)this + v11++ + 3), 0);
    *((_DWORD *)&v30 + v12) = v13;
  }
  while ( v11 < v6 );
  v14 = !v24 || !(_DWORD)v30;
  v15 = v24 == 1 || !HIDWORD(v30);
  v16 = v24 == 2 || !v31;
  v17 = v24 == 3 || !(_DWORD)v32;
  v18 = v24 == 4 || !HIDWORD(v32);
  if ( !CancelWaitableTimer(*((HANDLE *)this + 1)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2003304445;
    ModuleFailFastForHRESULT(LastError, retaddr);
  }
  *((_DWORD *)this + 4) = -1;
  if ( v17 )
    CDisplayManager::IsCurrent(v19, 1);
  if ( v18 )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        &EVTDESC_SCHEDULE_DXGI_OCCLUSION_EVENT,
        v20,
        1u,
        (PEVENT_DATA_DESCRIPTOR)&v30);
    *(_BYTE *)(*((_QWORD *)g_pComposition + 77) + 754LL) = 1;
  }
  if ( (Microsoft_Windows_Dwm_CompositorEnableBits & 1) != 0 )
    McTemplateU0qttttt_EventWriteTransfer(v17, v16, v24, v14, v15, v16, v17, v18);
  v21 = dword_1803BB2F4;
  if ( v14 )
  {
    v21 = dword_1803BB2F4 | 8;
    dword_1803BB2F4 |= 8u;
  }
  if ( v14 & 2 | (2 * v15) & 2 )
  {
    v21 |= 0x10u;
    dword_1803BB2F4 = v21;
  }
  if ( v14 & 4 | ((unsigned __int8)(2 * v15) | (unsigned __int8)(4 * v16)) & 4 )
  {
    v21 |= 2u;
    dword_1803BB2F4 = v21;
  }
  if ( ((v14 | (unsigned __int8)((8 * v18) | (2 * v15) | (4 * v16))) & 8) != 0 )
    dword_1803BB2F4 = v21 | 4;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 4) != 0 )
  {
    v28 = v16;
    v27 = v15;
    v26 = v14;
    v25 = v24;
    v34 = &v25;
    v36 = &v26;
    v38 = &v27;
    v40 = &v28;
    v42 = &v30;
    LODWORD(v30) = v18;
    v35 = 4;
    v37 = 4;
    v39 = 4;
    v41 = 4;
    v43 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_SCHEDULE_WFW_Stop,
      v20,
      6u,
      &v33);
  }
  *v29 = GetTickCount64();
}

```

## disassembly

```asm
0x180110540  push    rbp
0x180110542  push    rbx
0x180110543  push    rsi
0x180110544  push    rdi
0x180110545  push    r13
0x180110547  push    r14
0x180110549  lea     rbp, [rsp-8]
0x18011054e  sub     rsp, 108h
0x180110555  mov     rax, cs:__security_cookie
0x18011055c  xor     rax, rsp
0x18011055f  mov     [rbp+30h+var_40], rax
0x180110563  mov     rax, cs:qword_1803BB0C8
0x18011056a  mov     rsi, rcx
0x18011056d  mov     [rcx+30h], rax
0x180110571  xor     r13d, r13d
0x180110574  mov     rcx, cs:qword_1803BB0D0
0x18011057b  mov     rbx, rdx
0x18011057e  lea     rax, [rcx-1]
0x180110582  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180110586  jbe     short loc_1801105DC
0x180110588  cmp     cs:qword_1803BB0B8, r13
0x18011058f  jz      loc_180110A86
0x180110595  cmp     cs:byte_1803BB0E2, r13b
0x18011059c  jnz     loc_180110A6C
0x1801105a2  xor     r9d, r9d; lpName
0x1801105a5  xor     r8d, r8d; bInitialState
0x1801105a8  xor     edx, edx; bManualReset
0x1801105aa  xor     ecx, ecx; lpEventAttributes
0x1801105ac  call    cs:__imp_CreateEventW
0x1801105b2  mov     rdi, rax
0x1801105b5  mov     [rsp+130h+var_B8], rax
0x1801105ba  dec     rax
0x1801105bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801105c1  jbe     loc_180110A1B
0x1801105c7  lea     rax, [rdi-1]
0x1801105cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801105cf  jbe     loc_180110A5E
0x1801105d5  mov     rcx, cs:qword_1803BB0D0
0x1801105dc  test    rcx, rcx
0x1801105df  mov     [rsi+38h], rcx
0x1801105e3  mov     r14d, r13d
0x1801105e6  lea     rcx, [rsp+130h+var_C8]; this
0x1801105eb  setnz   r14b
0x1801105ef  add     r14d, 4
0x1801105f3  call    ??0CRenderThreadWaitTick@@QEAA@PEC_K@Z; CRenderThreadWaitTick::CRenderThreadWaitTick(unsigned __int64 volatile *)
0x1801105f8  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 4
0x1801105ff  jnz     loc_1801106B3
0x180110605  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 1
0x18011060c  jnz     loc_1801109C0
0x180110612  mov     [rsp+130h+var_F0], r13d
0x180110617  mov     rax, [rbx]
0x18011061a  lea     rcx, [rsp+130h+var_F0]
0x18011061f  mov     [rsp+130h+var_108], rcx
0x180110624  lea     r8, [rsi+18h]
0x180110628  mov     r9d, 0FFFFFFFFh
0x18011062e  mov     [rsp+130h+var_110], r13d
0x180110633  mov     edx, r14d
0x180110636  mov     rcx, rbx
0x180110639  mov     rax, [rax+20h]
0x18011063d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110642  test    eax, eax
0x180110644  jns     loc_1801106DB
0x18011064a  mov     [rsp+130h+var_108], r13; void *
0x18011064f  mov     r9d, eax; int
0x180110652  xor     r8d, r8d; unsigned int
0x180110655  mov     [rsp+130h+var_110], 82h; unsigned int
0x18011065d  xor     edx, edx; int *
0x18011065f  mov     ecx, 14h; unsigned int
0x180110664  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180110669  mov     eax, 0FFFFFFFFh
0x18011066e  mov     [rsp+130h+var_F0], eax
0x180110672  cmp     eax, r14d
0x180110675  jb      short loc_1801106E1
0x180110677  mov     rax, [rbx]
0x18011067a  mov     edx, 3
0x18011067f  mov     rcx, rbx
0x180110682  mov     rax, [rax+18h]
0x180110686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011068b  test    eax, eax
0x18011068d  jns     short loc_180110617
0x18011068f  mov     [rsp+130h+var_108], r13; void *
0x180110694  mov     r9d, eax; int
0x180110697  xor     r8d, r8d; unsigned int
0x18011069a  mov     [rsp+130h+var_110], 91h; unsigned int
0x1801106a2  xor     edx, edx; int *
0x1801106a4  mov     ecx, 14h; unsigned int
0x1801106a9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801106ae  jmp     loc_180110617
0x1801106b3  lea     rax, [rsp+130h+var_B8]
0x1801106b8  mov     r9d, 1
0x1801106be  lea     rdx, EVTDESC_SCHEDULE_WFW_Start
0x1801106c5  mov     qword ptr [rsp+130h+var_110], rax
0x1801106ca  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801106d1  call    McGenEventWrite_EventWriteTransfer
0x1801106d6  jmp     loc_180110605
0x1801106db  mov     eax, [rsp+130h+var_F0]
0x1801106df  jmp     short loc_180110672
0x1801106e1  mov     dword ptr [rsp+130h+var_B8], 102h
0x1801106e9  mov     edi, r13d
0x1801106ec  mov     dword ptr [rsp+130h+var_B8+4], 102h
0x1801106f4  mov     [rbp+30h+var_B0], 102h
0x1801106fb  mov     [rbp+30h+var_AC], 102h
0x180110703  nop     dword ptr [rax+00h]
0x180110707  nop     word ptr [rax+rax+00000000h]
0x180110710  mov     ebx, edi
0x180110712  xor     edx, edx; dwMilliseconds
0x180110714  mov     rcx, [rsi+rbx*8+18h]; hHandle
0x180110719  call    cs:__imp_WaitForSingleObject
0x18011071f  inc     edi
0x180110721  mov     dword ptr [rsp+rbx*4+130h+var_B8], eax
0x180110725  cmp     edi, r14d
0x180110728  jb      short loc_180110710
0x18011072a  mov     eax, [rsp+130h+var_F0]
0x18011072e  mov     [rsp+130h+arg_10], r12
0x180110736  test    eax, eax
0x180110738  jnz     loc_1801108C5
0x18011073e  mov     r12b, 1
0x180110741  mov     [rsp+130h+var_30], r15
0x180110749  cmp     eax, 1
0x18011074c  jnz     loc_1801108B2
0x180110752  mov     r15b, 1
0x180110755  cmp     eax, 2
0x180110758  jnz     loc_1801108A0
0x18011075e  mov     r14b, 1
0x180110761  cmp     eax, 3
0x180110764  jnz     loc_18011087D
0x18011076a  mov     dil, 1
0x18011076d  cmp     eax, 4
0x180110770  jnz     loc_18011088F
0x180110776  mov     bl, 1
0x180110778  mov     rcx, [rsi+8]; hTimer
0x18011077c  call    cs:__imp_CancelWaitableTimer
0x180110782  test    eax, eax
0x180110784  jz      loc_180110855
0x18011078a  mov     dword ptr [rsi+10h], 0FFFFFFFFh
0x180110791  test    dil, dil
0x180110794  jnz     loc_180110A8E
0x18011079a  test    bl, bl
0x18011079c  jnz     loc_180110978
0x1801107a2  test    byte ptr cs:Microsoft_Windows_Dwm_CompositorEnableBits, 1
0x1801107a9  jnz     loc_1801109E8
0x1801107af  movzx   edx, bl
0x1801107b2  movzx   ecx, r14b
0x1801107b6  shl     ecx, 2
0x1801107b9  movzx   eax, r15b
0x1801107bd  add     eax, eax
0x1801107bf  or      ecx, eax
0x1801107c1  lea     eax, ds:0[rdx*8]
0x1801107c8  or      ecx, eax
0x1801107ca  movzx   eax, r12b
0x1801107ce  or      ecx, eax
0x1801107d0  mov     eax, cs:dword_1803BB2F4
0x1801107d6  test    cl, 1
0x1801107d9  jz      short loc_1801107E4
0x1801107db  or      eax, 8
0x1801107de  mov     cs:dword_1803BB2F4, eax
0x1801107e4  test    cl, 2
0x1801107e7  jz      short loc_1801107F2
0x1801107e9  or      eax, 10h
0x1801107ec  mov     cs:dword_1803BB2F4, eax
0x1801107f2  test    cl, 4
0x1801107f5  jz      short loc_180110800
0x1801107f7  or      eax, 2
0x1801107fa  mov     cs:dword_1803BB2F4, eax
0x180110800  test    cl, 8
0x180110803  jz      short loc_18011080E
0x180110805  or      eax, 4
0x180110808  mov     cs:dword_1803BB2F4, eax
0x18011080e  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 4
0x180110815  jnz     loc_1801108D8
0x18011081b  call    cs:__imp_GetTickCount64
0x180110821  mov     rcx, [rsp+130h+var_C8]
0x180110826  mov     r15, [rsp+130h+var_30]
0x18011082e  mov     r12, [rsp+130h+arg_10]
0x180110836  mov     [rcx], rax
0x180110839  mov     rcx, [rbp+30h+var_40]
0x18011083d  xor     rcx, rsp; StackCookie
0x180110840  call    __security_check_cookie
0x180110845  add     rsp, 108h
0x18011084c  pop     r14
0x18011084e  pop     r13
0x180110850  pop     rdi
0x180110851  pop     rsi
0x180110852  pop     rbx
0x180110853  pop     rbp
0x180110854  retn
0x180110855  call    cs:__imp_GetLastError
0x18011085b  test    eax, eax
0x18011085d  jle     short loc_180110867
0x18011085f  movzx   eax, ax
0x180110862  or      eax, 80070000h
0x180110867  mov     rdx, [rbp+38h]; void *
0x18011086b  mov     ecx, 88980003h
0x180110870  test    eax, eax
0x180110872  cmovns  eax, ecx
0x180110875  mov     ecx, eax; int
0x180110877  call    ModuleFailFastForHRESULT
0x18011087d  cmp     dword ptr [rbp+30h+var_AC], r13d
0x180110881  jz      loc_18011076A
0x180110887  xor     dil, dil
0x18011088a  jmp     loc_18011076D
0x18011088f  cmp     dword ptr [rbp+30h+var_AC+4], r13d
0x180110893  jz      loc_180110776
0x180110899  xor     bl, bl
0x18011089b  jmp     loc_180110778
0x1801108a0  cmp     [rbp+30h+var_B0], r13d
0x1801108a4  jz      loc_18011075E
0x1801108aa  xor     r14b, r14b
0x1801108ad  jmp     loc_180110761
0x1801108b2  cmp     dword ptr [rsp+130h+var_B8+4], r13d
0x1801108b7  jz      loc_180110752
0x1801108bd  xor     r15b, r15b
0x1801108c0  jmp     loc_180110755
0x1801108c5  cmp     dword ptr [rsp+130h+var_B8], r13d
0x1801108ca  jz      loc_18011073E
0x1801108d0  xor     r12b, r12b
0x1801108d3  jmp     loc_180110741
0x1801108d8  movzx   eax, r14b
0x1801108dc  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801108e3  mov     [rsp+130h+var_D0], eax
0x1801108e7  mov     r9d, 6
0x1801108ed  movzx   eax, r15b
0x1801108f1  mov     [rsp+130h+var_D8], eax
0x1801108f5  movzx   eax, r12b
0x1801108f9  mov     [rsp+130h+var_E0], eax
0x1801108fd  mov     eax, [rsp+130h+var_F0]
0x180110901  mov     [rsp+130h+var_E8], eax
0x180110905  lea     rax, [rsp+130h+var_E8]
0x18011090a  mov     [rbp+30h+var_90], rax
0x18011090e  lea     rax, [rsp+130h+var_E0]
0x180110913  mov     [rbp+30h+var_80], rax
0x180110917  lea     rax, [rsp+130h+var_D8]
0x18011091c  mov     [rbp+30h+var_70], rax
0x180110920  lea     rax, [rsp+130h+var_D0]
0x180110925  mov     [rbp+30h+var_60], rax
0x180110929  lea     rax, [rsp+130h+var_B8]
0x18011092e  mov     [rbp+30h+var_50], rax
0x180110932  lea     rax, [rbp+30h+var_A0]
0x180110936  mov     dword ptr [rsp+130h+var_B8], edx
0x18011093a  lea     rdx, EVTDESC_SCHEDULE_WFW_Stop
0x180110941  mov     qword ptr [rsp+130h+var_110], rax
0x180110946  mov     [rbp+30h+var_88], 4
0x18011094e  mov     [rbp+30h+var_78], 4
0x180110956  mov     [rbp+30h+var_68], 4
0x18011095e  mov     [rbp+30h+var_58], 4
0x180110966  mov     [rbp+30h+var_48], 4
0x18011096e  call    McGenEventWrite_EventWriteTransfer
0x180110973  jmp     loc_18011081B
0x180110978  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x18011097f  jnz     short loc_18011099B
0x180110981  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180110988  mov     rcx, [rax+268h]
0x18011098f  mov     byte ptr [rcx+2F2h], 1
0x180110996  jmp     loc_1801107A2
0x18011099b  lea     rax, [rsp+130h+var_B8]
0x1801109a0  mov     r9d, 1
0x1801109a6  lea     rdx, EVTDESC_SCHEDULE_DXGI_OCCLUSION_EVENT
0x1801109ad  mov     qword ptr [rsp+130h+var_110], rax
0x1801109b2  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801109b9  call    McGenEventWrite_EventWriteTransfer
0x1801109be  jmp     short loc_180110981
0x1801109c0  lea     rax, [rsp+130h+var_B8]
0x1801109c5  mov     r9d, 1
0x1801109cb  lea     rdx, WaitForWork_Start
0x1801109d2  mov     qword ptr [rsp+130h+var_110], rax
0x1801109d7  lea     rcx, Microsoft_Windows_Dwm_Compositor_Context
0x1801109de  call    McGenEventWrite_EventWriteTransfer
0x1801109e3  jmp     loc_180110612
0x1801109e8  movzx   r8d, r15b
0x1801109ec  movzx   eax, bl
0x1801109ef  mov     [rsp+130h+var_F8], eax
0x1801109f3  movzx   ecx, dil
0x1801109f7  mov     [rsp+130h+var_100], ecx
0x1801109fb  movzx   edx, r14b
0x1801109ff  mov     dword ptr [rsp+130h+var_108], edx
0x180110a03  mov     [rsp+130h+var_110], r8d
0x180110a08  mov     r8d, [rsp+130h+var_F0]
0x180110a0d  movzx   r9d, r12b
0x180110a11  call    McTemplateU0qttttt_EventWriteTransfer
0x180110a16  jmp     loc_1801107AF
0x180110a1b  mov     rcx, cs:qword_1803BB0B8
0x180110a22  lea     r8, qword_1803BB0D8+4
0x180110a29  mov     rdx, rdi
0x180110a2c  mov     rax, [rcx]
0x180110a2f  mov     rax, [rax+0B0h]
0x180110a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110a3b  test    eax, eax
0x180110a3d  js      loc_1801105C7
0x180110a43  lea     rdx, [rsp+130h+var_B8]
0x180110a48  lea     rcx, qword_1803BB0D0
0x180110a4f  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180110a54  mov     rdi, [rsp+130h+var_B8]
0x180110a59  jmp     loc_1801105C7
0x180110a5e  mov     rcx, rdi; hObject
0x180110a61  call    cs:__imp_CloseHandle
0x180110a67  jmp     loc_1801105D5
0x180110a6c  call    cs:__imp_DwmGetRemoteSessionOcclusionEvent
0x180110a72  mov     rdx, rax
0x180110a75  lea     rcx, qword_1803BB0D0
0x180110a7c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
  ... truncated ...
```
