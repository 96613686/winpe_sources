# ScoHandleStreamFailure(long,WDFDEVICE__ *)

- ea: `0x14000f700`
- end: `0x14000f87b`
- name: `?ScoHandleStreamFailure@@YAXJPEAUWDFDEVICE__@@@Z`
- size: `379`
- prototype: `void __fastcall(int, struct WDFDEVICE__ *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001790`
- `0x14000fa40`
- `0x1400110c0`
- `0x140013148`

## callees

- `0x1400041d0`
- `0x140004810`
- `0x14000a914`
- `0x14000aac0`
- `0x14000f700`
- `0x14001117c`
- `0x1400112c4`
- `0x14001ae00`

## pseudocode

```c
void __fastcall ScoHandleStreamFailure(unsigned int a1, struct WDFDEVICE__ *a2)
{
  int v3; // edx
  __int64 v4; // rdi
  int v5; // r8d
  char v6; // bl
  __int64 v7; // rdx
  int v8; // r8d
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // [rsp+28h] [rbp-60h]

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a2,
         off_140022150);
  v6 = 1;
  LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      5,
      12,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids,
      a1);
  }
  SetScoState(v4, 0);
  if ( *(_DWORD *)(v4 + 108) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v6;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        13,
        (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
    }
    v9 = *(_QWORD *)(v4 + 96);
    *(_DWORD *)(v4 + 120) = a1;
    WdfIoQueueFindAndCompleteStatusIoctlRequest(v9, 0, 0x220033u, (_DWORD *)(v4 + 120), (_DWORD *)(v4 + 124), v13);
  }
  v10 = WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v4 + 96), v7, 0x22002Bu, a1);
  v12 = WdfIoQueueFindAndCompleteIoctlRequest(*(_QWORD *)(v4 + 96), v11, 0x2A0018u, a1);
  if ( v10 >= 0 || v12 >= 0 )
  {
    *(_DWORD *)(v4 + 108) = 0;
    ScoUpdateAvdtpSuspension(v4);
  }
}

```

## disassembly

```asm
0x14000f700  push    rbx
0x14000f702  push    rbp
0x14000f703  push    rsi
0x14000f704  push    rdi
0x14000f705  push    r12
0x14000f707  push    r15
0x14000f709  sub     rsp, 58h
0x14000f70d  mov     rax, cs:WdfFunctions_01015
0x14000f714  mov     esi, ecx
0x14000f716  mov     r8, cs:off_140022150
0x14000f71d  mov     rcx, cs:WdfDriverGlobals
0x14000f724  mov     rax, [rax+650h]
0x14000f72b  call    _guard_dispatch_icall
0x14000f730  mov     rdi, rax
0x14000f733  mov     rax, cs:WPP_GLOBAL_Control
0x14000f73a  lea     r12, WPP_GLOBAL_Control
0x14000f741  mov     bl, 1
0x14000f743  cmp     rax, r12
0x14000f746  jz      short loc_14000F75A
0x14000f748  mov     ecx, [rax+2Ch]
0x14000f74b  test    cl, 10h
0x14000f74e  jz      short loc_14000F75A
0x14000f750  cmp     byte ptr [rax+29h], 2
0x14000f754  jb      short loc_14000F75A
0x14000f756  mov     dl, bl
0x14000f758  jmp     short loc_14000F75C
0x14000f75a  xor     dl, dl
0x14000f75c  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000f763  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000f76a  lea     r15, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000f771  setnz   r8b
0x14000f775  test    dl, dl
0x14000f777  jnz     short loc_14000F77E
0x14000f779  test    r8b, r8b
0x14000f77c  jz      short loc_14000F7A8
0x14000f77e  mov     r9, [rax+40h]
0x14000f782  mov     rcx, [rax+18h]
0x14000f786  mov     [rsp+88h+var_48], esi
0x14000f78a  mov     [rsp+88h+var_50], r15
0x14000f78f  mov     [rsp+88h+var_58], 0Ch
0x14000f796  mov     dword ptr [rsp+88h+var_60], 5
0x14000f79e  mov     byte ptr [rsp+88h+var_68], 2
0x14000f7a3  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x14000f7a8  xor     edx, edx
0x14000f7aa  mov     rcx, rdi
0x14000f7ad  call    SetScoState
0x14000f7b2  cmp     dword ptr [rdi+6Ch], 0
0x14000f7b6  jz      short loc_14000F830
0x14000f7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7bf  cmp     rcx, r12
0x14000f7c2  jz      short loc_14000F7D1
0x14000f7c4  mov     eax, [rcx+2Ch]
0x14000f7c7  test    al, 10h
0x14000f7c9  jz      short loc_14000F7D1
0x14000f7cb  cmp     byte ptr [rcx+29h], 2
0x14000f7cf  jnb     short loc_14000F7D3
0x14000f7d1  xor     bl, bl
0x14000f7d3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000f7da  setnz   r8b
0x14000f7de  test    bl, bl
0x14000f7e0  jnz     short loc_14000F7E7
0x14000f7e2  test    r8b, r8b
0x14000f7e5  jz      short loc_14000F80F
0x14000f7e7  mov     r9, [rcx+40h]
0x14000f7eb  mov     dl, bl
0x14000f7ed  mov     rcx, [rcx+18h]
0x14000f7f1  mov     [rsp+88h+var_50], r15
0x14000f7f6  mov     [rsp+88h+var_58], 0Dh
0x14000f7fd  mov     dword ptr [rsp+88h+var_60], 5
0x14000f805  mov     byte ptr [rsp+88h+var_68], 2
0x14000f80a  call    WPP_RECORDER_AND_TRACE_SF_
0x14000f80f  mov     rcx, [rdi+60h]
0x14000f813  lea     r9, [rdi+78h]
0x14000f817  lea     rax, [rdi+7Ch]
0x14000f81b  mov     [r9], esi
0x14000f81e  xor     edx, edx
0x14000f820  mov     [rsp+88h+var_68], rax
0x14000f825  mov     r8d, 220033h
0x14000f82b  call    WdfIoQueueFindAndCompleteStatusIoctlRequest
0x14000f830  mov     rcx, [rdi+60h]
0x14000f834  mov     r9d, esi
0x14000f837  mov     r8d, 22002Bh
0x14000f83d  call    WdfIoQueueFindAndCompleteIoctlRequest
0x14000f842  mov     rcx, [rdi+60h]
0x14000f846  mov     r9d, esi
0x14000f849  mov     r8d, 2A0018h
0x14000f84f  mov     ebx, eax
0x14000f851  call    WdfIoQueueFindAndCompleteIoctlRequest
0x14000f856  test    ebx, ebx
0x14000f858  jns     short loc_14000F85E
0x14000f85a  test    eax, eax
0x14000f85c  js      short loc_14000F86D
0x14000f85e  mov     rcx, rdi
0x14000f861  mov     dword ptr [rdi+6Ch], 0
0x14000f868  call    ScoUpdateAvdtpSuspension
0x14000f86d  add     rsp, 58h
0x14000f871  pop     r15
0x14000f873  pop     r12
0x14000f875  pop     rdi
0x14000f876  pop     rsi
0x14000f877  pop     rbp
0x14000f878  pop     rbx
0x14000f879  retn
```
