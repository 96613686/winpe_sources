# SetScoState

- ea: `0x1400112c4`
- end: `0x14001147c`
- name: `SetScoState`
- size: `440`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1400014c4`
- `0x14000d76c`
- `0x14000e510`
- `0x14000e87c`
- `0x14000ecc4`
- `0x14000f700`
- `0x14000fa40`
- `0x14000fff0`
- `0x140012100`
- `0x140013148`

## callees

- `0x14000ce50`
- `0x14001117c`
- `0x1400112c4`
- `0x140014c60`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400113d1`
- `ntoskrnl!KeSetEvent` at `0x1400113d1`
- `ntoskrnl!KeClearEvent` at `0x1400113a8`
- `ntoskrnl!KeClearEvent` at `0x1400113a8`

## pseudocode

```c
__int64 __fastcall SetScoState(__int64 a1, int a2)
{
  char v4; // bp
  int v5; // edx
  __int64 v6; // r8
  int v7; // edi
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 ServiceScoStatusRequestForIndication; // rax
  int v17; // [rsp+20h] [rbp-68h]
  _BYTE v18[56]; // [rsp+50h] [rbp-38h] BYREF

  v4 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *(_QWORD *)(a1 + 368));
  v7 = 4;
  LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE(
      WPP_GLOBAL_Control->AttachedDevice,
      v5,
      v6,
      WPP_GLOBAL_Control->DeviceExtension,
      v17);
  *(_DWORD *)(a1 + 376) = a2;
  if ( !a2 )
  {
    KeSetEvent((PRKEVENT)(a1 + 336), 0, 0);
    v7 = 0;
    goto LABEL_23;
  }
  v8 = a2 - 2;
  if ( !v8 )
  {
LABEL_21:
    v4 = 1;
    goto LABEL_23;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v7 = 5;
    goto LABEL_21;
  }
  v7 = 3;
  v10 = v9 - 3;
  if ( !v10 )
  {
    KeClearEvent((PRKEVENT)(a1 + 336));
    v7 = 6;
    goto LABEL_21;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 != 1 )
      {
        v13 = 0;
        v14 = 0;
        goto LABEL_25;
      }
    }
    else
    {
      v7 = 2;
    }
  }
  else
  {
    v7 = 1;
  }
LABEL_23:
  ServiceScoStatusRequestForIndication = RetrieveServiceScoStatusRequestForIndication((__int64)v18, a1, v7);
  v13 = *(_DWORD *)ServiceScoStatusRequestForIndication;
  v14 = *(_QWORD *)(ServiceScoStatusRequestForIndication + 8);
  if ( v4 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
      WdfDriverGlobals,
      *(_QWORD *)(a1 + 480),
      -50000000);
LABEL_25:
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2536))(
    WdfDriverGlobals,
    *(_QWORD *)(a1 + 368),
    v6);
  if ( v14 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
      WdfDriverGlobals,
      v14,
      v13);
  ScoUpdateAvdtpSuspension(a1);
  return v13;
}

```

## disassembly

```asm
0x1400112c4  push    rbx
0x1400112c6  push    rbp
0x1400112c7  push    rsi
0x1400112c8  push    rdi
0x1400112c9  sub     rsp, 68h
0x1400112cd  mov     rax, cs:WdfFunctions_01015
0x1400112d4  mov     ebx, edx
0x1400112d6  mov     rdx, [rcx+170h]
0x1400112dd  mov     rsi, rcx
0x1400112e0  mov     rcx, cs:WdfDriverGlobals
0x1400112e7  xor     bpl, bpl
0x1400112ea  mov     rax, [rax+9E0h]
0x1400112f1  call    _guard_dispatch_icall
0x1400112f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112fd  lea     rax, WPP_GLOBAL_Control
0x140011304  mov     edi, 4
0x140011309  cmp     rcx, rax
0x14001130c  jz      short loc_14001131F
0x14001130e  mov     eax, [rcx+2Ch]
0x140011311  test    al, 10h
0x140011313  jz      short loc_14001131F
0x140011315  cmp     [rcx+29h], dil
0x140011319  jb      short loc_14001131F
0x14001131b  mov     dl, 1
0x14001131d  jmp     short loc_140011321
0x14001131f  xor     dl, dl
0x140011321  lea     rax, WPP_RECORDER_INITIALIZED
0x140011328  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001132f  setnz   r8b
0x140011333  test    dl, dl
0x140011335  jnz     short loc_14001133C
0x140011337  test    r8b, r8b
0x14001133a  jz      short loc_14001135E
0x14001133c  mov     eax, [rsi+178h]
0x140011342  mov     r9, [rcx+40h]
0x140011346  mov     rcx, [rcx+18h]
0x14001134a  mov     [rsp+88h+var_40], ebx
0x14001134e  mov     [rsp+88h+var_48], eax
0x140011352  mov     [rsp+88h+var_58], 72h ; 'r'
0x140011359  call    WPP_RECORDER_AND_TRACE_SF_SCOSTATESCOSTATE
0x14001135e  mov     [rsi+178h], ebx
0x140011364  test    ebx, ebx
0x140011366  jz      short loc_1400113C5
0x140011368  sub     ebx, 2
0x14001136b  jz      short loc_1400113C0
0x14001136d  sub     ebx, 1
0x140011370  jz      short loc_1400113BB
0x140011372  mov     edi, 3
0x140011377  sub     ebx, edi
0x140011379  jz      short loc_1400113A1
0x14001137b  sub     ebx, 1
0x14001137e  jz      short loc_14001139A
0x140011380  sub     ebx, 1
0x140011383  jz      short loc_140011393
0x140011385  cmp     ebx, 1
0x140011388  jz      short loc_1400113DF
0x14001138a  xor     ebx, ebx
0x14001138c  xor     edi, edi
0x14001138e  jmp     loc_140011422
0x140011393  mov     edi, 2
0x140011398  jmp     short loc_1400113DF
0x14001139a  mov     edi, 1
0x14001139f  jmp     short loc_1400113DF
0x1400113a1  lea     rcx, [rsi+150h]; Event
0x1400113a8  call    cs:__imp_KeClearEvent
0x1400113af  nop     dword ptr [rax+rax+00h]
0x1400113b4  mov     edi, 6
0x1400113b9  jmp     short loc_1400113C0
0x1400113bb  mov     edi, 5
0x1400113c0  mov     bpl, 1
0x1400113c3  jmp     short loc_1400113DF
0x1400113c5  lea     rcx, [rsi+150h]; Event
0x1400113cc  xor     r8d, r8d; Wait
0x1400113cf  xor     edx, edx; Increment
0x1400113d1  call    cs:__imp_KeSetEvent
0x1400113d8  nop     dword ptr [rax+rax+00h]
0x1400113dd  xor     edi, edi
0x1400113df  mov     r8d, edi
0x1400113e2  lea     rcx, [rsp+88h+var_38]
0x1400113e7  mov     rdx, rsi
0x1400113ea  call    ?RetrieveServiceScoStatusRequestForIndication@@YA?AU?$pair@JPEAUWDFREQUEST__@@@utl@@PEAU_SCOCONTEXT@@W4_BTHHF_SCO_STATUS_INDICATION@@@Z; RetrieveServiceScoStatusRequestForIndication(_SCOCONTEXT *,_BTHHF_SCO_STATUS_INDICATION)
0x1400113ef  mov     ebx, [rax]
0x1400113f1  mov     rdi, [rax+8]
0x1400113f5  test    bpl, bpl
0x1400113f8  jz      short loc_140011422
0x1400113fa  mov     rax, cs:WdfFunctions_01015
0x140011401  mov     r8, 0FFFFFFFFFD050F80h
0x140011408  mov     rdx, [rsi+1E0h]
0x14001140f  mov     rcx, cs:WdfDriverGlobals
0x140011416  mov     rax, [rax+9F8h]
0x14001141d  call    _guard_dispatch_icall
0x140011422  mov     rax, cs:WdfFunctions_01015
0x140011429  mov     rdx, [rsi+170h]
0x140011430  mov     rcx, cs:WdfDriverGlobals
0x140011437  mov     rax, [rax+9E8h]
0x14001143e  call    _guard_dispatch_icall
0x140011443  test    rdi, rdi
0x140011446  jz      short loc_140011468
0x140011448  mov     rcx, cs:WdfFunctions_01015
0x14001144f  mov     r8d, ebx
0x140011452  mov     rdx, rdi
0x140011455  mov     rax, [rcx+838h]
0x14001145c  mov     rcx, cs:WdfDriverGlobals
0x140011463  call    _guard_dispatch_icall
0x140011468  mov     rcx, rsi
0x14001146b  call    ScoUpdateAvdtpSuspension
0x140011470  mov     eax, ebx
0x140011472  add     rsp, 68h
0x140011476  pop     rdi
0x140011477  pop     rsi
0x140011478  pop     rbp
0x140011479  pop     rbx
0x14001147a  retn
```
