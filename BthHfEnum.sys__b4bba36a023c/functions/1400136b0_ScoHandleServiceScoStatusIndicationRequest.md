# ScoHandleServiceScoStatusIndicationRequest

- ea: `0x1400136b0`
- end: `0x14001392a`
- name: `ScoHandleServiceScoStatusIndicationRequest`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000ce50`
- `0x1400136b0`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall ScoHandleServiceScoStatusIndicationRequest(__int64 a1, __int64 a2)
{
  int v3; // edx
  __int64 v4; // rbx
  int v5; // r8d
  char v6; // di
  int v7; // r8d
  int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 result; // rax
  __int64 ServiceScoStatusRequestForIndication; // rax
  unsigned int v13; // esi
  __int64 v14; // rdi
  _BYTE v15[56]; // [rsp+50h] [rbp-38h] BYREF
  int v16; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+20h] BYREF

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_140022150);
  v6 = 1;
  LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      115,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  v16 = 0;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, int *, _QWORD))(WdfFunctions_01015 + 1224))(
    WdfDriverGlobals,
    *(_QWORD *)(v4 + 384),
    &v16,
    0);
  v8 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v6;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        4,
        116,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
        v16);
    }
    goto LABEL_17;
  }
  v17 = 0;
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64 *, _QWORD))(WdfFunctions_01015 + 2160))(
         WdfDriverGlobals,
         a2,
         4,
         &v17,
         0) < 0
    || (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2248))(
         WdfDriverGlobals,
         a2,
         *(_QWORD *)(v4 + 384)) < 0 )
  {
LABEL_17:
    v9 = 3221225488LL;
    v10 = a2;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             v10,
             v9);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2528))(
    WdfDriverGlobals,
    *(_QWORD *)(v4 + 368));
  if ( *(_DWORD *)(v4 + 396) )
  {
    ServiceScoStatusRequestForIndication = RetrieveServiceScoStatusRequestForIndication(
                                             (__int64)v15,
                                             v4,
                                             *(_DWORD *)(v4 + 392));
    v13 = *(_DWORD *)ServiceScoStatusRequestForIndication;
    v14 = *(_QWORD *)(ServiceScoStatusRequestForIndication + 8);
  }
  else
  {
    v13 = 0;
    v14 = 0;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2536))(
             WdfDriverGlobals,
             *(_QWORD *)(v4 + 368));
  if ( v14 )
  {
    v9 = v13;
    v10 = v14;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             v10,
             v9);
  }
  return result;
}

```

## disassembly

```asm
0x1400136b0  mov     [rsp+arg_0], rbx
0x1400136b5  push    rsi
0x1400136b6  push    rdi
0x1400136b7  push    r12
0x1400136b9  push    r13
0x1400136bb  push    r15
0x1400136bd  sub     rsp, 60h
0x1400136c1  mov     rax, cs:WdfFunctions_01015
0x1400136c8  mov     rsi, rdx
0x1400136cb  mov     r8, cs:off_140022150
0x1400136d2  mov     rdx, rcx
0x1400136d5  mov     rcx, cs:WdfDriverGlobals
0x1400136dc  mov     rax, [rax+650h]
0x1400136e3  call    _guard_dispatch_icall
0x1400136e8  mov     rbx, rax
0x1400136eb  mov     rax, cs:WPP_GLOBAL_Control
0x1400136f2  lea     r13, WPP_GLOBAL_Control
0x1400136f9  mov     dil, 1
0x1400136fc  cmp     rax, r13
0x1400136ff  jz      short loc_140013714
0x140013701  mov     ecx, [rax+2Ch]
0x140013704  test    cl, 10h
0x140013707  jz      short loc_140013714
0x140013709  cmp     byte ptr [rax+29h], 4
0x14001370d  jb      short loc_140013714
0x14001370f  mov     dl, dil
0x140013712  jmp     short loc_140013716
0x140013714  xor     dl, dl
0x140013716  lea     r15, WPP_RECORDER_INITIALIZED
0x14001371d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013724  lea     r12, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14001372b  setnz   r8b
0x14001372f  test    dl, dl
0x140013731  jnz     short loc_140013738
0x140013733  test    r8b, r8b
0x140013736  jz      short loc_14001375E
0x140013738  mov     r9, [rax+40h]
0x14001373c  mov     rcx, [rax+18h]
0x140013740  mov     [rsp+88h+var_50], r12
0x140013745  mov     [rsp+88h+var_58], 73h ; 's'
0x14001374c  mov     [rsp+88h+var_60], 5
0x140013754  mov     byte ptr [rsp+88h+var_68], 4
0x140013759  call    WPP_RECORDER_AND_TRACE_SF_
0x14001375e  mov     rax, cs:WdfFunctions_01015
0x140013765  lea     r8, [rsp+88h+arg_10]
0x14001376d  mov     rcx, cs:WdfDriverGlobals
0x140013774  xor     r9d, r9d
0x140013777  mov     [rsp+88h+arg_10], 0
0x140013782  mov     rdx, [rbx+180h]
0x140013789  mov     rax, [rax+4C8h]
0x140013790  call    _guard_dispatch_icall
0x140013795  mov     edx, [rsp+88h+arg_10]
0x14001379c  test    edx, edx
0x14001379e  jz      loc_14001383B
0x1400137a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137ab  cmp     rcx, r13
0x1400137ae  jz      short loc_1400137BD
0x1400137b0  mov     eax, [rcx+2Ch]
0x1400137b3  test    al, 8
0x1400137b5  jz      short loc_1400137BD
0x1400137b7  cmp     byte ptr [rcx+29h], 3
0x1400137bb  jnb     short loc_1400137C0
0x1400137bd  xor     dil, dil
0x1400137c0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400137c7  setnz   r8b
0x1400137cb  test    dil, dil
0x1400137ce  jnz     short loc_1400137D5
0x1400137d0  test    r8b, r8b
0x1400137d3  jz      short loc_140013802
0x1400137d5  mov     r9, [rcx+40h]
0x1400137d9  mov     rcx, [rcx+18h]
0x1400137dd  mov     [rsp+88h+var_48], edx
0x1400137e1  mov     dl, dil
0x1400137e4  mov     [rsp+88h+var_50], r12
0x1400137e9  mov     [rsp+88h+var_58], 74h ; 't'
0x1400137f0  mov     [rsp+88h+var_60], 4
0x1400137f8  mov     byte ptr [rsp+88h+var_68], 3
0x1400137fd  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140013802  mov     r8d, 0C0000010h
0x140013808  mov     rdx, rsi
0x14001380b  mov     rax, cs:WdfFunctions_01015
0x140013812  mov     rcx, cs:WdfDriverGlobals
0x140013819  mov     rax, [rax+838h]
0x140013820  call    _guard_dispatch_icall
0x140013825  mov     rbx, [rsp+88h+arg_0]
0x14001382d  add     rsp, 60h
0x140013831  pop     r15
0x140013833  pop     r13
0x140013835  pop     r12
0x140013837  pop     rdi
0x140013838  pop     rsi
0x140013839  retn
0x14001383b  mov     rax, cs:WdfFunctions_01015
0x140013842  lea     r9, [rsp+88h+arg_18]
0x14001384a  mov     rcx, cs:WdfDriverGlobals
0x140013851  mov     r8d, 4
0x140013857  mov     [rsp+88h+arg_18], 0
0x140013863  mov     rdx, rsi
0x140013866  mov     [rsp+88h+var_68], 0
0x14001386f  mov     rax, [rax+870h]
0x140013876  call    _guard_dispatch_icall
0x14001387b  test    eax, eax
0x14001387d  js      short loc_140013802
0x14001387f  mov     rax, cs:WdfFunctions_01015
0x140013886  mov     rdx, rsi
0x140013889  mov     r8, [rbx+180h]
0x140013890  mov     rcx, cs:WdfDriverGlobals
0x140013897  mov     rax, [rax+8C8h]
0x14001389e  call    _guard_dispatch_icall
0x1400138a3  test    eax, eax
0x1400138a5  js      loc_140013802
0x1400138ab  mov     rax, cs:WdfFunctions_01015
0x1400138b2  mov     rdx, [rbx+170h]
0x1400138b9  mov     rcx, cs:WdfDriverGlobals
0x1400138c0  mov     rax, [rax+9E0h]
0x1400138c7  call    _guard_dispatch_icall
0x1400138cc  cmp     dword ptr [rbx+18Ch], 0
0x1400138d3  jz      short loc_1400138F1
0x1400138d5  mov     r8d, [rbx+188h]
0x1400138dc  lea     rcx, [rsp+88h+var_38]
0x1400138e1  mov     rdx, rbx
0x1400138e4  call    ?RetrieveServiceScoStatusRequestForIndication@@YA?AU?$pair@JPEAUWDFREQUEST__@@@utl@@PEAU_SCOCONTEXT@@W4_BTHHF_SCO_STATUS_INDICATION@@@Z; RetrieveServiceScoStatusRequestForIndication(_SCOCONTEXT *,_BTHHF_SCO_STATUS_INDICATION)
0x1400138e9  mov     esi, [rax]
0x1400138eb  mov     rdi, [rax+8]
0x1400138ef  jmp     short loc_1400138F5
0x1400138f1  xor     esi, esi
0x1400138f3  xor     edi, edi
0x1400138f5  mov     rax, cs:WdfFunctions_01015
0x1400138fc  mov     rdx, [rbx+170h]
0x140013903  mov     rcx, cs:WdfDriverGlobals
0x14001390a  mov     rax, [rax+9E8h]
0x140013911  call    _guard_dispatch_icall
0x140013916  test    rdi, rdi
0x140013919  jz      loc_140013825
0x14001391f  mov     r8d, esi
0x140013922  mov     rdx, rdi
0x140013925  jmp     loc_14001380B
```
