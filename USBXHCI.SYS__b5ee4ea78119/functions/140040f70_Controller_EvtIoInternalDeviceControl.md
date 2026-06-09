# Controller_EvtIoInternalDeviceControl

- ea: `0x140040f70`
- end: `0x140041070`
- name: `Controller_EvtIoInternalDeviceControl`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14001ac48`
- `0x14002b2c0`
- `0x140040f70`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140041051`
- `ntoskrnl!IofCompleteRequest` at `0x140041051`

## pseudocode

```c
__int64 __fastcall Controller_EvtIoInternalDeviceControl(__int64 a1, IRP *a2)
{
  unsigned int LowPart; // ebx
  __int64 v5; // rax
  int v6; // edx
  unsigned int v7; // ebx
  __int64 v8; // rbx

  LowPart = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006C2C0);
  if ( LowPart == 2232247 )
  {
    v8 = *(_QWORD *)(v5 + 8);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(v8 + 72), v6, 4, 229, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids);
    }
    Controller_ReportFatalError(v8, 2, 4159, 0, 0, 0, 0);
    a2->IoStatus.Status = 0;
    v7 = 0;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01033 + 272))(
             WdfDriverGlobals,
             a1,
             a2);
  }
  return v7;
}

```

## disassembly

```asm
0x140040f70  mov     [rsp+arg_0], rbx
0x140040f75  mov     [rsp+arg_8], rsi
0x140040f7a  push    rdi
0x140040f7b  sub     rsp, 40h
0x140040f7f  mov     rax, [rdx+0B8h]
0x140040f86  mov     rdi, rdx
0x140040f89  mov     r8, cs:off_14006C2C0
0x140040f90  mov     rsi, rcx
0x140040f93  mov     rdx, rcx
0x140040f96  mov     rcx, cs:WdfDriverGlobals
0x140040f9d  mov     ebx, [rax+18h]
0x140040fa0  mov     rax, cs:WdfFunctions_01033
0x140040fa7  mov     rax, [rax+650h]
0x140040fae  call    _guard_dispatch_icall
0x140040fb3  cmp     ebx, 220FB7h
0x140040fb9  jz      short loc_140040FEA
0x140040fbb  inc     byte ptr [rdi+43h]
0x140040fbe  mov     r8, rdi
0x140040fc1  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140040fc9  mov     rdx, rsi
0x140040fcc  mov     rax, cs:WdfFunctions_01033
0x140040fd3  mov     rcx, cs:WdfDriverGlobals
0x140040fda  mov     rax, [rax+110h]
0x140040fe1  call    _guard_dispatch_icall
0x140040fe6  mov     ebx, eax
0x140040fe8  jmp     short loc_14004105D
0x140040fea  mov     rbx, [rax+8]; __annotation("TMF:",
0x140040fee  lea     rax, WPP_RECORDER_INITIALIZED
0x140040ff5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040ffc  jz      short loc_140041022
0x140040ffe  mov     rcx, [rbx+48h]
0x140041002  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x140041009  mov     r8d, 4
0x14004100f  mov     [rsp+48h+var_28], rax
0x140041014  mov     dl, r8b
0x140041017  mov     r9d, 0E5h
0x14004101d  call    WPP_RECORDER_SF_
0x140041022  xor     esi, esi
0x140041024  xor     r9d, r9d
0x140041027  mov     [rsp+48h+var_18], rsi
0x14004102c  mov     r8d, 103Fh
0x140041032  mov     [rsp+48h+var_20], rsi
0x140041037  mov     rcx, rbx
0x14004103a  mov     [rsp+48h+var_28], rsi
0x14004103f  lea     edx, [rsi+2]
0x140041042  call    Controller_ReportFatalError
0x140041047  xor     edx, edx; PriorityBoost
0x140041049  mov     [rdi+30h], esi
0x14004104c  mov     rcx, rdi; Irp
0x14004104f  mov     ebx, esi
0x140041051  call    cs:__imp_IofCompleteRequest
0x140041058  nop     dword ptr [rax+rax+00h]
0x14004105d  mov     rsi, [rsp+48h+arg_8]
0x140041062  mov     eax, ebx
0x140041064  mov     rbx, [rsp+48h+arg_0]
0x140041069  add     rsp, 40h
0x14004106d  pop     rdi
0x14004106e  retn
```
