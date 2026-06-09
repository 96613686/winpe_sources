# MbbUtilSendMbimError(ulong,_MBB_ERROR,_MINIPORT_ADAPTER_CONTEXT *,_GUID,_MBB_COMMAND *)

- ea: `0x14001fcf4`
- end: `0x14001ff9d`
- name: `?MbbUtilSendMbimError@@YAXKW4_MBB_ERROR@@PEAU_MINIPORT_ADAPTER_CONTEXT@@U_GUID@@PEAU_MBB_COMMAND@@@Z`
- size: `681`
- prototype: `void __fastcall(int, int, __int64, const GUID *, struct _MBB_COMMAND *Source1)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400138d0`
- `0x1400193bc`
- `0x14001b348`

## callees

- `0x1400051ac`
- `0x14000d890`
- `0x14000f0c0`
- `0x14001fcf4`
- `0x140024338`
- `0x14003e100`
- `0x140041664`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001fd2f`
- `ntoskrnl!ExAllocatePool2` at `0x14001fd2f`

## pseudocode

```c
void __fastcall MbbUtilSendMbimError(int a1, int a2, __int64 a3, const GUID *a4, struct _MBB_COMMAND *Source1)
{
  _DWORD *Pool2; // rax
  int v6; // edx
  __int64 v7; // rdi
  _DWORD *v8; // r15
  _DWORD *v9; // r12
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  char (near **CommandString)[32]; // r8
  __int64 v16; // rax
  int v17; // [rsp+80h] [rbp-21h] BYREF
  int v18; // [rsp+88h] [rbp-19h] BYREF
  __int64 v19; // [rsp+90h] [rbp-11h] BYREF
  LPCGUID ActivityId; // [rsp+98h] [rbp-9h]
  __int64 v21; // [rsp+A0h] [rbp-1h]
  __int64 v22; // [rsp+A8h] [rbp+7h]

  v21 = a3;
  v17 = a1;
  v18 = a2;
  ActivityId = a4;
  Pool2 = (_DWORD *)ExAllocatePool2(64, 16, 1683505741);
  v7 = (__int64)Pool2;
  if ( Pool2 )
  {
    *Pool2 = 4;
    v8 = Pool2 + 1;
    Pool2[1] = 16;
    v9 = Pool2 + 2;
    Pool2[2] = v17;
    Pool2[3] = v18;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        9,
        25,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        v17,
        v18);
    }
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
            WdfDriverGlobals,
            *(_QWORD *)(v21 + 1160),
            off_14005DF70);
    v19 = 0;
    v11 = *(_QWORD *)(v10 + 8);
    v22 = v10;
    v12 = MbxRequest::_CreateInner(v11, 1, 4, v7, v7, 16, (__int128 *)ActivityId, &v19);
    if ( v12 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        26,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        (__int64)L"MbbUtilSendMbimError",
        v12);
    if ( v19 )
    {
      MbbWriteEventOpn(&MBIM_UINT32_PAYLOAD_MSG, ActivityId, 0, 4u, v7, 4, v8, 4, v9, 4, v7 + 12, 4);
      (*(void (__fastcall **)(_QWORD, __int64))(v22 + 32))(*(_QWORD *)(v22 + 8), v19);
      CommandString = MbbUtilGetCommandString(Source1);
      v16 = -1;
      do
        ++v16;
      while ( *((_BYTE *)CommandString + v16) );
      MbbWriteEvent(
        &MBIM_HOST_ERROR_EVENT,
        0,
        0,
        6u,
        v21 + 32,
        4,
        &v18,
        4,
        &v17,
        4,
        Source1,
        16,
        (char *)Source1 + 16,
        4,
        CommandString,
        v16 + 1);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      9,
      24,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      v17,
      v18);
  }
}

```

## disassembly

```asm
0x14001fcf4  push    rbp
0x14001fcf6  push    rbx
0x14001fcf7  push    rsi
0x14001fcf8  push    rdi
0x14001fcf9  push    r12
0x14001fcfb  push    r13
0x14001fcfd  push    r14
0x14001fcff  push    r15
0x14001fd01  lea     rbp, [rsp-17h]
0x14001fd06  sub     rsp, 0B8h
0x14001fd0d  mov     r14, [rbp+4Fh+Source1]
0x14001fd11  mov     ebx, 10h
0x14001fd16  mov     [rbp+4Fh+var_50], r8
0x14001fd1a  mov     r8d, 6458424Dh
0x14001fd20  mov     [rbp+4Fh+var_70], ecx
0x14001fd23  mov     [rbp+4Fh+var_68], edx
0x14001fd26  mov     edx, ebx
0x14001fd28  lea     ecx, [rbx+30h]
0x14001fd2b  mov     [rbp+4Fh+ActivityId], r9
0x14001fd2f  call    cs:__imp_ExAllocatePool2
0x14001fd36  nop     dword ptr [rax+rax+00h]
0x14001fd3b  mov     rdi, rax
0x14001fd3e  test    rax, rax
0x14001fd41  jnz     short loc_14001FD90
0x14001fd43  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001fd4a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001fd51  jz      loc_14001FF88
0x14001fd57  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd5e  lea     r9d, [rax+18h]
0x14001fd62  mov     eax, [rbp+4Fh+var_68]
0x14001fd65  lea     rsi, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001fd6c  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001fd70  lea     r8d, [rdi+9]
0x14001fd74  mov     eax, [rbp+4Fh+var_70]
0x14001fd77  mov     dl, 2
0x14001fd79  mov     rcx, [rcx+40h]
0x14001fd7d  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14001fd81  mov     [rsp+0F0h+var_D0], rsi
0x14001fd86  call    WPP_RECORDER_SF_DD
0x14001fd8b  jmp     loc_14001FF88
0x14001fd90  mov     dword ptr [rax], 4
0x14001fd96  lea     r15, [rax+4]
0x14001fd9a  mov     [r15], ebx
0x14001fd9d  lea     r12, [rax+8]
0x14001fda1  mov     eax, [rbp+4Fh+var_70]
0x14001fda4  lea     r13, [rdi+0Ch]
0x14001fda8  mov     [r12], eax
0x14001fdac  mov     eax, [rbp+4Fh+var_68]
0x14001fdaf  mov     [r13+0], eax
0x14001fdb3  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001fdba  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001fdc1  lea     rsi, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001fdc8  jz      short loc_14001FDF9
0x14001fdca  mov     eax, [rbp+4Fh+var_68]
0x14001fdcd  mov     r9d, 19h
0x14001fdd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fdda  mov     dl, 2
0x14001fddc  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001fde0  mov     eax, [rbp+4Fh+var_70]
0x14001fde3  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14001fde7  lea     r8d, [r9-10h]
0x14001fdeb  mov     rcx, [rcx+40h]
0x14001fdef  mov     [rsp+0F0h+var_D0], rsi
0x14001fdf4  call    WPP_RECORDER_SF_DD
0x14001fdf9  mov     rcx, [rbp+4Fh+var_50]
0x14001fdfd  mov     rax, cs:WdfFunctions_01031
0x14001fe04  mov     r8, cs:off_14005DF70
0x14001fe0b  mov     rdx, [rcx+488h]
0x14001fe12  mov     rcx, cs:WdfDriverGlobals
0x14001fe19  mov     rax, [rax+650h]
0x14001fe20  call    _guard_dispatch_icall
0x14001fe25  lea     rcx, [rbp+4Fh+var_60]
0x14001fe29  mov     [rbp+4Fh+var_60], 0
0x14001fe31  mov     [rsp+0F0h+var_B8], rcx
0x14001fe36  mov     edx, 1
0x14001fe3b  mov     rcx, [rbp+4Fh+ActivityId]
0x14001fe3f  mov     r9, rdi
0x14001fe42  mov     [rsp+0F0h+var_C0], rcx
0x14001fe47  mov     rcx, [rax+8]
0x14001fe4b  mov     [rsp+0F0h+var_C8], 10h
0x14001fe54  lea     r8d, [rdx+3]
0x14001fe58  mov     [rsp+0F0h+var_D0], rdi
0x14001fe5d  mov     [rbp+4Fh+var_48], rax
0x14001fe61  call    ?_CreateInner@MbxRequest@@CAJPEAUWDFDEVICE__@@W4RequestType@1@W4MessageType@1@PEAX3_KPEBU_GUID@@PEAPEAUMBBREQUEST__@@@Z; MbxRequest::_CreateInner(WDFDEVICE__ *,MbxRequest::RequestType,MbxRequest::MessageType,void *,void *,unsigned __int64,_GUID const *,MBBREQUEST__ * *)
0x14001fe66  test    eax, eax
0x14001fe68  jns     short loc_14001FE9E
0x14001fe6a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001fe71  jz      short loc_14001FE9E
0x14001fe73  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe7a  mov     r9d, 1Ah
0x14001fe80  mov     dword ptr [rsp+0F0h+var_C0], eax
0x14001fe84  lea     rax, aMbbutilsendmbi; "MbbUtilSendMbimError"
0x14001fe8b  mov     [rsp+0F0h+var_C8], rax
0x14001fe90  mov     [rsp+0F0h+var_D0], rsi
0x14001fe95  mov     rcx, [rcx+40h]
0x14001fe99  call    WPP_RECORDER_SF_Sd
0x14001fe9e  cmp     [rbp+4Fh+var_60], 0
0x14001fea3  jz      loc_14001FF88
0x14001fea9  mov     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x14001fead  lea     rcx, MBIM_UINT32_PAYLOAD_MSG; EventDescriptor
0x14001feb4  mov     ebx, 4
0x14001feb9  xor     r8d, r8d; RelatedActivityId
0x14001febc  mov     [rsp+0F0h+var_98], rbx
0x14001fec1  mov     r9d, ebx; unsigned __int16
0x14001fec4  mov     [rsp+0F0h+var_A0], r13
0x14001fec9  mov     [rsp+0F0h+var_A8], rbx
0x14001fece  mov     [rsp+0F0h+var_B0], r12
0x14001fed3  mov     [rsp+0F0h+var_B8], rbx
0x14001fed8  mov     [rsp+0F0h+var_C0], r15
0x14001fedd  mov     [rsp+0F0h+var_C8], rbx
0x14001fee2  mov     [rsp+0F0h+var_D0], rdi
0x14001fee7  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14001feec  mov     rcx, [rbp+4Fh+var_48]
0x14001fef0  mov     rdx, [rbp+4Fh+var_60]
0x14001fef4  mov     rax, [rcx+20h]
0x14001fef8  mov     rcx, [rcx+8]
0x14001fefc  call    _guard_dispatch_icall
0x14001ff01  mov     rcx, r14; Source1
0x14001ff04  call    ?MbbUtilGetCommandString@@YAPEADPEAU_MBB_COMMAND@@@Z; MbbUtilGetCommandString(_MBB_COMMAND *)
0x14001ff09  mov     r8, rax
0x14001ff0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001ff10  inc     rax
0x14001ff13  cmp     byte ptr [r8+rax], 0
0x14001ff18  jnz     short loc_14001FF10
0x14001ff1a  mov     rdx, [rbp+4Fh+var_50]
0x14001ff1e  lea     rcx, [r14+10h]
0x14001ff22  inc     rax
0x14001ff25  add     rdx, 20h ; ' '
0x14001ff29  mov     [rsp+0F0h+var_78], rax
0x14001ff2e  mov     r9d, 6; unsigned __int16
0x14001ff34  mov     [rsp+0F0h+var_80], r8
0x14001ff39  lea     rax, [rbp+4Fh+var_70]
0x14001ff3d  mov     [rsp+0F0h+var_88], rbx
0x14001ff42  xor     r8d, r8d; RelatedActivityId
0x14001ff45  mov     [rsp+0F0h+var_90], rcx
0x14001ff4a  lea     rcx, MBIM_HOST_ERROR_EVENT; EventDescriptor
0x14001ff51  mov     [rsp+0F0h+var_98], 10h
0x14001ff5a  mov     [rsp+0F0h+var_A0], r14
0x14001ff5f  mov     [rsp+0F0h+var_A8], rbx
0x14001ff64  mov     [rsp+0F0h+var_B0], rax
0x14001ff69  lea     rax, [rbp+4Fh+var_68]
0x14001ff6d  mov     [rsp+0F0h+var_B8], rbx
0x14001ff72  mov     [rsp+0F0h+var_C0], rax
0x14001ff77  mov     [rsp+0F0h+var_C8], rbx
0x14001ff7c  mov     [rsp+0F0h+var_D0], rdx
0x14001ff81  xor     edx, edx; ActivityId
0x14001ff83  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14001ff88  add     rsp, 0B8h
0x14001ff8f  pop     r15
0x14001ff91  pop     r14
0x14001ff93  pop     r13
0x14001ff95  pop     r12
0x14001ff97  pop     rdi
0x14001ff98  pop     rsi
0x14001ff99  pop     rbx
0x14001ff9a  pop     rbp
0x14001ff9b  retn
```
