# CsDispatchQueue::Initialize(utl::function<void (_IRP *)> &&)

- ea: `0x140089240`
- end: `0x1400894af`
- name: `?Initialize@CsDispatchQueue@@UEAAJ$$QEAV?$function@$$A6AXPEAU_IRP@@@Z@utl@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(char *StartContext, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x14000e690`
- `0x140059fb8`
- `0x14005bc6c`
- `0x14005c7d0`
- `0x140089240`
- `0x1400894c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14008947e`
- `ntoskrnl!ZwClose` at `0x14008947e`
- `ntoskrnl!KeInitializeSemaphore` at `0x140089276`
- `ntoskrnl!KeInitializeSemaphore` at `0x140089276`
- `ntoskrnl!PsCreateSystemThread` at `0x140089359`
- `ntoskrnl!PsCreateSystemThread` at `0x140089359`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400893f4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400893f4`

## pseudocode

```c
__int64 __fastcall CsDispatchQueue::Initialize(char *StartContext, __int64 a2)
{
  NTSTATUS v4; // edi
  int v5; // edx
  int v6; // r8d
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  void *ThreadHandle; // [rsp+50h] [rbp-38h] BYREF
  _QWORD v13[4]; // [rsp+58h] [rbp-30h] BYREF

  KeInitializeSemaphore((PRKSEMAPHORE)(StartContext + 168), 0, 0x7FFFFFFF);
  v13[0] = &utl::_FuncEmpty<void,_IRP *>::`vftable';
  v4 = CsQueue::Initialize(StartContext, v13);
  utl::function<void (_IRP *)>::~function<void (_IRP *)>(v13);
  if ( v4 < 0 )
  {
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        25,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
        v4);
    }
    return (unsigned int)v4;
  }
  ThreadHandle = 0;
  v4 = PsCreateSystemThread(&ThreadHandle, 0x1FFFFFu, 0, 0, 0, CsDispatchQueue::CsqIrpDispatcherThread, StartContext);
  if ( v4 < 0 )
  {
    LOBYTE(v8) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        26,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
        v4);
    }
    return (unsigned int)v4;
  }
  v4 = ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, (PVOID *)StartContext + 17, 0);
  if ( v4 < 0 )
  {
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        27,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
        v4);
    }
    return (unsigned int)v4;
  }
  utl::function<void (_IRP *)>::assign(StartContext + 256, a2);
  ZwClose(ThreadHandle);
  return 0;
}

```

## disassembly

```asm
0x140089240  mov     [rsp+arg_10], rbx
0x140089245  mov     [rsp+arg_18], rsi
0x14008924a  push    rdi
0x14008924b  sub     rsp, 80h
0x140089252  mov     rax, cs:__security_cookie
0x140089259  xor     rax, rsp
0x14008925c  mov     [rsp+88h+var_10], rax
0x140089261  mov     rsi, rdx
0x140089264  mov     rbx, rcx
0x140089267  add     rcx, 0A8h; Semaphore
0x14008926e  xor     edx, edx; Count
0x140089270  mov     r8d, 7FFFFFFFh; Limit
0x140089276  call    cs:__imp_KeInitializeSemaphore
0x14008927d  nop     dword ptr [rax+rax+00h]
0x140089282  lea     rax, ??_7?$_FuncEmpty@XPEAU_IRP@@@utl@@6B@; const utl::_FuncEmpty<void,_IRP *>::`vftable'
0x140089289  mov     rcx, rbx
0x14008928c  lea     rdx, [rsp+88h+var_30]
0x140089291  mov     [rsp+88h+var_30], rax
0x140089296  call    ?Initialize@CsQueue@@UEAAJ$$QEAV?$function@$$A6AXPEAU_IRP@@@Z@utl@@@Z; CsQueue::Initialize(utl::function<void (_IRP *)> &&)
0x14008929b  lea     rcx, [rsp+88h+var_30]
0x1400892a0  mov     edi, eax
0x1400892a2  call    ??1?$function@$$A6AXPEAU_IRP@@@Z@utl@@QEAA@XZ; utl::function<void (_IRP *)>::~function<void (_IRP *)>(void)
0x1400892a7  test    edi, edi
0x1400892a9  jns     short loc_140089326
0x1400892ab  mov     r10, cs:WPP_GLOBAL_Control
0x1400892b2  lea     rcx, WPP_GLOBAL_Control
0x1400892b9  cmp     r10, rcx
0x1400892bc  jz      short loc_1400892D1
0x1400892be  mov     eax, [r10+2Ch]
0x1400892c2  test    al, 2
0x1400892c4  jz      short loc_1400892D1
0x1400892c6  cmp     byte ptr [r10+29h], 2
0x1400892cb  jb      short loc_1400892D1
0x1400892cd  mov     dl, 1
0x1400892cf  jmp     short loc_1400892D3
0x1400892d1  xor     dl, dl
0x1400892d3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400892da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400892e1  setnz   r8b
0x1400892e5  test    dl, dl
0x1400892e7  jnz     short loc_1400892EE
0x1400892e9  test    r8b, r8b
0x1400892ec  jz      short loc_14008931F
0x1400892ee  mov     [rsp+88h+var_48], edi
0x1400892f2  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x1400892f9  mov     [rsp+88h+var_50], rax
0x1400892fe  mov     word ptr [rsp+88h+StartContext], 19h
0x140089305  mov     r9, [r10+40h]
0x140089309  mov     rcx, [r10+18h]
0x14008930d  mov     dword ptr [rsp+88h+StartRoutine], 2
0x140089315  mov     byte ptr [rsp+88h+ClientId], 2
0x14008931a  call    WPP_RECORDER_AND_TRACE_SF_d
0x14008931f  mov     eax, edi
0x140089321  jmp     loc_14008948C
0x140089326  lea     rax, ?CsqIrpDispatcherThread@CsDispatchQueue@@CAXPEAX@Z; CsDispatchQueue::CsqIrpDispatcherThread(void *)
0x14008932d  mov     [rsp+88h+StartContext], rbx; StartContext
0x140089332  mov     [rsp+88h+StartRoutine], rax; StartRoutine
0x140089337  lea     rcx, [rsp+88h+ThreadHandle]; ThreadHandle
0x14008933c  xor     r9d, r9d; ProcessHandle
0x14008933f  mov     [rsp+88h+ClientId], 0; ClientId
0x140089348  xor     r8d, r8d; ObjectAttributes
0x14008934b  mov     [rsp+88h+ThreadHandle], 0
0x140089354  mov     edx, 1FFFFFh; DesiredAccess
0x140089359  call    cs:__imp_PsCreateSystemThread
0x140089360  nop     dword ptr [rax+rax+00h]
0x140089365  mov     edi, eax
0x140089367  test    eax, eax
0x140089369  jns     short loc_1400893CF
0x14008936b  mov     r10, cs:WPP_GLOBAL_Control
0x140089372  lea     rcx, WPP_GLOBAL_Control
0x140089379  cmp     r10, rcx
0x14008937c  jz      short loc_140089392
0x14008937e  mov     ecx, [r10+2Ch]
0x140089382  test    cl, 2
0x140089385  jz      short loc_140089392
0x140089387  cmp     byte ptr [r10+29h], 2
0x14008938c  jb      short loc_140089392
0x14008938e  mov     dl, 1
0x140089390  jmp     short loc_140089394
0x140089392  xor     dl, dl
0x140089394  lea     rax, WPP_RECORDER_INITIALIZED
0x14008939b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400893a2  setnz   r8b
0x1400893a6  test    dl, dl
0x1400893a8  jnz     short loc_1400893B3
0x1400893aa  test    r8b, r8b
0x1400893ad  jz      loc_14008931F
0x1400893b3  mov     [rsp+88h+var_48], edi
0x1400893b7  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x1400893be  mov     [rsp+88h+var_50], rax
0x1400893c3  mov     word ptr [rsp+88h+StartContext], 1Ah
0x1400893ca  jmp     loc_140089305
0x1400893cf  mov     rcx, [rsp+88h+ThreadHandle]; Handle
0x1400893d4  lea     rax, [rbx+88h]
0x1400893db  mov     [rsp+88h+StartRoutine], 0; HandleInformation
0x1400893e4  xor     r9d, r9d; AccessMode
0x1400893e7  xor     r8d, r8d; ObjectType
0x1400893ea  mov     [rsp+88h+ClientId], rax; Object
0x1400893ef  mov     edx, 1FFFFFh; DesiredAccess
0x1400893f4  call    cs:__imp_ObReferenceObjectByHandle
0x1400893fb  nop     dword ptr [rax+rax+00h]
0x140089400  mov     edi, eax
0x140089402  test    eax, eax
0x140089404  jns     short loc_14008946A
0x140089406  mov     r10, cs:WPP_GLOBAL_Control
0x14008940d  lea     rcx, WPP_GLOBAL_Control
0x140089414  cmp     r10, rcx
0x140089417  jz      short loc_14008942D
0x140089419  mov     ecx, [r10+2Ch]
0x14008941d  test    cl, 2
0x140089420  jz      short loc_14008942D
0x140089422  cmp     byte ptr [r10+29h], 2
0x140089427  jb      short loc_14008942D
0x140089429  mov     dl, 1
0x14008942b  jmp     short loc_14008942F
0x14008942d  xor     dl, dl
0x14008942f  lea     rax, WPP_RECORDER_INITIALIZED
0x140089436  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008943d  setnz   r8b
0x140089441  test    dl, dl
0x140089443  jnz     short loc_14008944E
0x140089445  test    r8b, r8b
0x140089448  jz      loc_14008931F
0x14008944e  mov     [rsp+88h+var_48], edi
0x140089452  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x140089459  mov     [rsp+88h+var_50], rax
0x14008945e  mov     word ptr [rsp+88h+StartContext], 1Bh
0x140089465  jmp     loc_140089305
0x14008946a  lea     rcx, [rbx+100h]
0x140089471  mov     rdx, rsi
0x140089474  call    ?assign@?$function@$$A6AXPEAU_IRP@@@Z@utl@@QEAA_N$$QEAV12@@Z; utl::function<void (_IRP *)>::assign(utl::function<void (_IRP *)> &&)
0x140089479  mov     rcx, [rsp+88h+ThreadHandle]; Handle
0x14008947e  call    cs:__imp_ZwClose
0x140089485  nop     dword ptr [rax+rax+00h]
0x14008948a  xor     eax, eax
0x14008948c  mov     rcx, [rsp+88h+var_10]
0x140089491  xor     rcx, rsp; StackCookie
0x140089494  call    __security_check_cookie
0x140089499  lea     r11, [rsp+88h+var_8]
0x1400894a1  mov     rbx, [r11+20h]
0x1400894a5  mov     rsi, [r11+28h]
0x1400894a9  mov     rsp, r11
0x1400894ac  pop     rdi
0x1400894ad  retn
```
