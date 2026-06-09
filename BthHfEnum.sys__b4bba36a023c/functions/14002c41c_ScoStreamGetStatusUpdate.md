# ScoStreamGetStatusUpdate

- ea: `0x14002c41c`
- end: `0x14002c5b0`
- name: `ScoStreamGetStatusUpdate`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140029170`

## callees

- `0x1400041d0`
- `0x14000ae30`
- `0x14000b0ac`
- `0x14001ae00`
- `0x14002c41c`

## pseudocode

```c
__int64 __fastcall ScoStreamGetStatusUpdate(__int64 a1, __int64 a2)
{
  int v3; // edx
  __int64 v4; // rbx
  int v5; // r8d
  char v6; // si
  int v8; // edx
  int v9; // r8d

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
      81,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  if ( (int)WdfIoQueueFindIoctlRequest(*(_QWORD *)(v4 + 96), 0, 2228267, 0) >= 0
    || (int)WdfIoQueueFindIoctlRequest(*(_QWORD *)(v4 + 96), 0, 2228271, 0) >= 0 )
  {
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a2,
             3221225488LL);
  }
  if ( !*(_DWORD *)(v4 + 108) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v6;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        3,
        5,
        82,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a2,
             3221225488LL);
  }
  return WdfRequestCompleteOrForwardStatusIoctlRequest(
           a2,
           *(_QWORD *)(v4 + 96),
           0x220033u,
           (_DWORD *)(v4 + 120),
           (_DWORD *)(v4 + 124));
}

```

## disassembly

```asm
0x14002c41c  push    rbx
0x14002c41e  push    rbp
0x14002c41f  push    rsi
0x14002c420  push    rdi
0x14002c421  push    r12
0x14002c423  push    r15
0x14002c425  sub     rsp, 48h
0x14002c429  mov     rax, cs:WdfFunctions_01015
0x14002c430  mov     rdi, rdx
0x14002c433  mov     r8, cs:off_140022150
0x14002c43a  mov     rdx, rcx
0x14002c43d  mov     rcx, cs:WdfDriverGlobals
0x14002c444  mov     rax, [rax+650h]
0x14002c44b  call    _guard_dispatch_icall
0x14002c450  mov     rbx, rax
0x14002c453  mov     rax, cs:WPP_GLOBAL_Control
0x14002c45a  lea     r12, WPP_GLOBAL_Control
0x14002c461  mov     sil, 1
0x14002c464  cmp     rax, r12
0x14002c467  jz      short loc_14002C47C
0x14002c469  mov     ecx, [rax+2Ch]
0x14002c46c  test    cl, 10h
0x14002c46f  jz      short loc_14002C47C
0x14002c471  cmp     byte ptr [rax+29h], 4
0x14002c475  jb      short loc_14002C47C
0x14002c477  mov     dl, sil
0x14002c47a  jmp     short loc_14002C47E
0x14002c47c  xor     dl, dl
0x14002c47e  lea     rbp, WPP_RECORDER_INITIALIZED
0x14002c485  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14002c48c  lea     r15, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14002c493  setnz   r8b
0x14002c497  test    dl, dl
0x14002c499  jnz     short loc_14002C4A0
0x14002c49b  test    r8b, r8b
0x14002c49e  jz      short loc_14002C4C6
0x14002c4a0  mov     r9, [rax+40h]
0x14002c4a4  mov     rcx, [rax+18h]
0x14002c4a8  mov     [rsp+78h+var_40], r15
0x14002c4ad  mov     [rsp+78h+var_48], 51h ; 'Q'
0x14002c4b4  mov     [rsp+78h+var_50], 5
0x14002c4bc  mov     byte ptr [rsp+78h+var_58], 4
0x14002c4c1  call    WPP_RECORDER_AND_TRACE_SF_
0x14002c4c6  mov     rcx, [rbx+60h]
0x14002c4ca  xor     r9d, r9d
0x14002c4cd  xor     edx, edx
0x14002c4cf  mov     r8d, 22002Bh
0x14002c4d5  call    WdfIoQueueFindIoctlRequest
0x14002c4da  test    eax, eax
0x14002c4dc  js      short loc_14002C506
0x14002c4de  mov     rax, cs:WdfFunctions_01015
0x14002c4e5  mov     r8d, 0C0000010h
0x14002c4eb  mov     rcx, cs:WdfDriverGlobals
0x14002c4f2  mov     rdx, rdi
0x14002c4f5  mov     rax, [rax+838h]
0x14002c4fc  call    _guard_dispatch_icall
0x14002c501  jmp     loc_14002C5A2
0x14002c506  mov     rcx, [rbx+60h]
0x14002c50a  xor     r9d, r9d
0x14002c50d  xor     edx, edx
0x14002c50f  mov     r8d, 22002Fh
0x14002c515  call    WdfIoQueueFindIoctlRequest
0x14002c51a  test    eax, eax
0x14002c51c  jns     short loc_14002C4DE
0x14002c51e  cmp     dword ptr [rbx+6Ch], 0
0x14002c522  jnz     short loc_14002C583
0x14002c524  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c52b  cmp     rcx, r12
0x14002c52e  jz      short loc_14002C53D
0x14002c530  mov     eax, [rcx+2Ch]
0x14002c533  test    al, 10h
0x14002c535  jz      short loc_14002C53D
0x14002c537  cmp     byte ptr [rcx+29h], 3
0x14002c53b  jnb     short loc_14002C540
0x14002c53d  xor     sil, sil
0x14002c540  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14002c547  setnz   r8b
0x14002c54b  test    sil, sil
0x14002c54e  jnz     short loc_14002C555
0x14002c550  test    r8b, r8b
0x14002c553  jz      short loc_14002C4DE
0x14002c555  mov     r9, [rcx+40h]
0x14002c559  mov     dl, sil
0x14002c55c  mov     rcx, [rcx+18h]
0x14002c560  mov     [rsp+78h+var_40], r15
0x14002c565  mov     [rsp+78h+var_48], 52h ; 'R'
0x14002c56c  mov     [rsp+78h+var_50], 5
0x14002c574  mov     byte ptr [rsp+78h+var_58], 3
0x14002c579  call    WPP_RECORDER_AND_TRACE_SF_
0x14002c57e  jmp     loc_14002C4DE
0x14002c583  mov     rdx, [rbx+60h]
0x14002c587  lea     rax, [rbx+7Ch]
0x14002c58b  lea     r9, [rbx+78h]
0x14002c58f  mov     [rsp+78h+var_58], rax
0x14002c594  mov     r8d, 220033h
0x14002c59a  mov     rcx, rdi
0x14002c59d  call    WdfRequestCompleteOrForwardStatusIoctlRequest
0x14002c5a2  add     rsp, 48h
0x14002c5a6  pop     r15
0x14002c5a8  pop     r12
0x14002c5aa  pop     rdi
0x14002c5ab  pop     rsi
0x14002c5ac  pop     rbp
0x14002c5ad  pop     rbx
0x14002c5ae  retn
```
