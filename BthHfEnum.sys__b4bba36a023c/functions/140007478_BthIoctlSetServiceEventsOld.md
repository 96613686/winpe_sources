# BthIoctlSetServiceEventsOld

- ea: `0x140007478`
- end: `0x140007761`
- name: `BthIoctlSetServiceEventsOld`
- size: `745`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140007478`
- `0x14001ae00`
- `0x14002ae68`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x140007599`
- `ntoskrnl!ExEventObjectType` at `0x1400075db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400075b3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400075f6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400075b3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400075f6`
- `ntoskrnl!ObfDereferenceObject` at `0x140007555`
- `ntoskrnl!ObfDereferenceObject` at `0x140007574`
- `ntoskrnl!ObfDereferenceObject` at `0x140007614`
- `ntoskrnl!ObfDereferenceObject` at `0x140007555`
- `ntoskrnl!ObfDereferenceObject` at `0x140007574`
- `ntoskrnl!ObfDereferenceObject` at `0x140007614`
- `btampm!BtaMpmConnectionRequest` at `0x140007724`
- `btampm!BtaMpmConnectionRequest` at `0x140007724`

## pseudocode

```c
__int64 __fastcall BthIoctlSetServiceEventsOld(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  PVOID *Object; // rsi
  NTSTATUS v6; // edi
  __int64 v7; // r15
  PVOID v8; // rcx
  int v9; // edx
  _UNKNOWN **v10; // r8
  __int64 v11; // rsi
  __int64 v12; // rcx
  HANDLE *v14; // [rsp+90h] [rbp+18h] BYREF
  __int64 v15; // [rsp+98h] [rbp+20h] BYREF

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2216))(WdfDriverGlobals);
  Object = (PVOID *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      v4,
                      off_140022128);
  v15 = 0;
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, HANDLE **, __int64 *))(WdfFunctions_01015 + 2152))(
         WdfDriverGlobals,
         a2,
         16,
         &v14,
         &v15);
  if ( v6 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(WdfDriverGlobals, a2);
    if ( *Object )
    {
      ObfDereferenceObject(*Object);
      *Object = 0;
    }
    v8 = Object[1];
    if ( v8 )
    {
      ObfDereferenceObject(v8);
      Object[1] = 0;
    }
    v6 = ObReferenceObjectByHandle(*v14, 2u, (POBJECT_TYPE)ExEventObjectType, *(_BYTE *)(v7 + 64), Object, 0);
    if ( v6 >= 0 )
    {
      v6 = ObReferenceObjectByHandle(v14[1], 2u, (POBJECT_TYPE)ExEventObjectType, *(_BYTE *)(v7 + 64), Object + 1, 0);
      if ( v6 < 0 )
      {
        if ( *Object )
        {
          ObfDereferenceObject(*Object);
          *Object = 0;
        }
      }
    }
    if ( v6 >= 0 )
    {
      if ( (unsigned int)Bus_IsAutoConnectionDisabled() )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          LOBYTE(v9) = 0;
        }
        else
        {
          v9 = 1;
        }
        v10 = &WPP_RECORDER_INITIALIZED;
        if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v9,
            (_DWORD)v10,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            2,
            24,
            (__int64)WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids);
        }
      }
      else
      {
        v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                WdfDriverGlobals,
                a1,
                off_1400220B0);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
          WdfDriverGlobals,
          *(_QWORD *)(v11 + 328),
          0);
        v12 = *(_QWORD *)(v11 + 184);
        if ( v12 )
          BtaMpmConnectionRequest(v12, 1, 1);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(
          WdfDriverGlobals,
          *(_QWORD *)(v11 + 328));
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007478  mov     [rsp+arg_0], rcx
0x14000747d  push    rsi
0x14000747e  push    rdi
0x14000747f  push    r12
0x140007481  push    r14
0x140007483  push    r15
0x140007485  sub     rsp, 50h
0x140007489  mov     r14, rdx
0x14000748c  mov     r12, rcx
0x14000748f  mov     rax, cs:WdfFunctions_01015
0x140007496  mov     rax, [rax+8A8h]
0x14000749d  mov     rcx, cs:WdfDriverGlobals
0x1400074a4  call    _guard_dispatch_icall
0x1400074a9  mov     r8, cs:WdfFunctions_01015
0x1400074b0  mov     r9, [r8+650h]
0x1400074b7  mov     r8, cs:off_140022128
0x1400074be  mov     rdx, rax
0x1400074c1  mov     rcx, cs:WdfDriverGlobals
0x1400074c8  mov     rax, r9
0x1400074cb  call    _guard_dispatch_icall
0x1400074d0  mov     rsi, rax
0x1400074d3  mov     [rsp+78h+arg_18], 0
0x1400074df  mov     [rsp+78h+arg_10], 0
0x1400074eb  mov     rcx, cs:WdfFunctions_01015
0x1400074f2  mov     rax, [rcx+868h]
0x1400074f9  lea     rcx, [rsp+78h+arg_18]
0x140007501  mov     [rsp+78h+Object], rcx
0x140007506  lea     r9, [rsp+78h+arg_10]
0x14000750e  mov     r8d, 10h
0x140007514  mov     rdx, r14
0x140007517  mov     rcx, cs:WdfDriverGlobals
0x14000751e  call    _guard_dispatch_icall
0x140007523  mov     edi, eax
0x140007525  test    eax, eax
0x140007527  js      loc_140007751
0x14000752d  mov     rax, cs:WdfFunctions_01015
0x140007534  mov     rax, [rax+8E8h]
0x14000753b  mov     rdx, r14
0x14000753e  mov     rcx, cs:WdfDriverGlobals
0x140007545  call    _guard_dispatch_icall
0x14000754a  mov     r15, rax
0x14000754d  mov     rcx, [rsi]; Object
0x140007550  test    rcx, rcx
0x140007553  jz      short loc_140007568
0x140007555  call    cs:__imp_ObfDereferenceObject
0x14000755c  nop     dword ptr [rax+rax+00h]
0x140007561  mov     qword ptr [rsi], 0
0x140007568  lea     r14, [rsi+8]
0x14000756c  mov     rcx, [r14]; Object
0x14000756f  test    rcx, rcx
0x140007572  jz      short loc_140007587
0x140007574  call    cs:__imp_ObfDereferenceObject
0x14000757b  nop     dword ptr [rax+rax+00h]
0x140007580  mov     qword ptr [r14], 0
0x140007587  mov     [rsp+78h+HandleInformation], 0; HandleInformation
0x140007590  mov     [rsp+78h+Object], rsi; Object
0x140007595  mov     r9b, [r15+40h]; AccessMode
0x140007599  mov     r8, cs:ExEventObjectType
0x1400075a0  mov     r8, [r8]; ObjectType
0x1400075a3  mov     edx, 2; DesiredAccess
0x1400075a8  mov     rcx, [rsp+78h+arg_10]
0x1400075b0  mov     rcx, [rcx]; Handle
0x1400075b3  call    cs:__imp_ObReferenceObjectByHandle
0x1400075ba  nop     dword ptr [rax+rax+00h]
0x1400075bf  mov     edi, eax
0x1400075c1  mov     [rsp+78h+var_38], eax
0x1400075c5  test    eax, eax
0x1400075c7  js      short loc_140007627
0x1400075c9  mov     [rsp+78h+HandleInformation], 0; HandleInformation
0x1400075d2  mov     [rsp+78h+Object], r14; Object
0x1400075d7  mov     r9b, [r15+40h]; AccessMode
0x1400075db  mov     r8, cs:ExEventObjectType
0x1400075e2  mov     r8, [r8]; ObjectType
0x1400075e5  mov     edx, 2; DesiredAccess
0x1400075ea  mov     rcx, [rsp+78h+arg_10]
0x1400075f2  mov     rcx, [rcx+8]; Handle
0x1400075f6  call    cs:__imp_ObReferenceObjectByHandle
0x1400075fd  nop     dword ptr [rax+rax+00h]
0x140007602  mov     edi, eax
0x140007604  mov     [rsp+78h+var_38], eax
0x140007608  test    eax, eax
0x14000760a  jns     short loc_140007627
0x14000760c  mov     rcx, [rsi]; Object
0x14000760f  test    rcx, rcx
0x140007612  jz      short loc_140007627
0x140007614  call    cs:__imp_ObfDereferenceObject
0x14000761b  nop     dword ptr [rax+rax+00h]
0x140007620  mov     qword ptr [rsi], 0
0x140007627  jmp     short loc_14000763A
0x140007629  mov     edi, 0C000000Dh
0x14000762e  mov     [rsp+78h+var_38], edi
0x140007632  mov     r12, [rsp+78h+arg_0]
0x14000763a  test    edi, edi
0x14000763c  js      loc_140007751
0x140007642  call    Bus_IsAutoConnectionDisabled
0x140007647  test    eax, eax
0x140007649  jz      short loc_1400076C5
0x14000764b  lea     rax, WPP_GLOBAL_Control
0x140007652  mov     rcx, cs:WPP_GLOBAL_Control
0x140007659  cmp     rcx, rax
0x14000765c  jz      short loc_140007672
0x14000765e  mov     eax, [rcx+2Ch]
0x140007661  test    al, 2
0x140007663  jz      short loc_140007672
0x140007665  cmp     byte ptr [rcx+29h], 4
0x140007669  jb      short loc_140007672
0x14000766b  mov     edx, 1
0x140007670  jmp     short loc_140007674
0x140007672  xor     dl, dl
0x140007674  lea     r8, WPP_RECORDER_INITIALIZED
0x14000767b  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140007682  setnz   r8b
0x140007686  test    dl, dl
0x140007688  jnz     short loc_140007693
0x14000768a  test    r8b, r8b
0x14000768d  jz      loc_140007751
0x140007693  lea     rax, WPP_2421956a1eaf3f28bf0c34f972a8cf79_Traceguids
0x14000769a  mov     [rsp+78h+var_40], rax
0x14000769f  mov     [rsp+78h+var_48], 18h
0x1400076a6  mov     dword ptr [rsp+78h+HandleInformation], 2
0x1400076ae  mov     byte ptr [rsp+78h+Object], 4
0x1400076b3  mov     r9, [rcx+40h]
0x1400076b7  mov     rcx, [rcx+18h]
0x1400076bb  call    WPP_RECORDER_AND_TRACE_SF_
0x1400076c0  jmp     loc_140007751
0x1400076c5  mov     r8, cs:off_1400220B0
0x1400076cc  mov     rax, cs:WdfFunctions_01015
0x1400076d3  mov     rax, [rax+650h]
0x1400076da  mov     rdx, r12
0x1400076dd  mov     rcx, cs:WdfDriverGlobals
0x1400076e4  call    _guard_dispatch_icall
0x1400076e9  mov     rsi, rax
0x1400076ec  mov     rcx, cs:WdfFunctions_01015
0x1400076f3  mov     rax, [rcx+9C8h]
0x1400076fa  xor     r8d, r8d
0x1400076fd  mov     rdx, [rsi+148h]
0x140007704  mov     rcx, cs:WdfDriverGlobals
0x14000770b  call    _guard_dispatch_icall
0x140007710  mov     rcx, [rsi+0B8h]
0x140007717  test    rcx, rcx
0x14000771a  jz      short loc_140007730
0x14000771c  mov     edx, 1
0x140007721  mov     r8d, edx
0x140007724  call    cs:__imp_BtaMpmConnectionRequest
0x14000772b  nop     dword ptr [rax+rax+00h]
0x140007730  mov     rax, cs:WdfFunctions_01015
0x140007737  mov     rax, [rax+9D0h]
0x14000773e  mov     rdx, [rsi+148h]
0x140007745  mov     rcx, cs:WdfDriverGlobals
0x14000774c  call    _guard_dispatch_icall
0x140007751  mov     eax, edi
0x140007753  add     rsp, 50h
0x140007757  pop     r15
0x140007759  pop     r14
0x14000775b  pop     r12
0x14000775d  pop     rdi
0x14000775e  pop     rsi
0x14000775f  retn
```
