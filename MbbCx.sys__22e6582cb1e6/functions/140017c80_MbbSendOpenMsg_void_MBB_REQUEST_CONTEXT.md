# MbbSendOpenMsg(void *,_MBB_REQUEST_CONTEXT *)

- ea: `0x140017c80`
- end: `0x140017e74`
- name: `?MbbSendOpenMsg@@YAHPEAXPEAU_MBB_REQUEST_CONTEXT@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(void *, struct _MBB_REQUEST_CONTEXT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140001db8`
- `0x14000f0c0`
- `0x140017c80`
- `0x14001dff0`
- `0x140024338`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140017cf1`
- `ntoskrnl!ExAllocatePool2` at `0x140017cf1`

## pseudocode

```c
__int64 __fastcall MbbSendOpenMsg(_QWORD *a1, struct _MBB_REQUEST_CONTEXT *a2)
{
  __int64 v4; // rbp
  int v5; // r13d
  _OWORD *Pool2; // rax
  _DWORD *v7; // rdi
  unsigned int v8; // ebx
  signed __int32 v9; // eax
  int v10; // edx
  __int64 v12; // [rsp+28h] [rbp-90h]
  __int64 v13; // [rsp+60h] [rbp-58h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-50h] BYREF

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         a1[145],
         off_14005DF70);
  v5 = *(_DWORD *)(v4 + 148);
  Pool2 = (_OWORD *)ExAllocatePool2(64, 16, 1683505741);
  v7 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
LABEL_7:
    *((_DWORD *)a2 + 160) = v8;
    return v8;
  }
  *((_QWORD *)a2 + 70) = Pool2;
  *Pool2 = 0;
  v9 = _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.Queue);
  *v7 = 1;
  *((_DWORD *)a2 + 5) = v9;
  v7[1] = 16;
  v7[3] = v5;
  v7[2] = v9;
  v13 = 0;
  ActivityId = 0;
  MbbEventActivityIdCtl(&ActivityId);
  v8 = MbxRequest::_CreateInner(a1[145], 1, 1, (__int64)a2, (__int64)v7, 16, (__int128 *)&ActivityId, &v13);
  if ( !v8 )
  {
    MbbWriteEventOpn(&MBIM_UINT32_PAYLOAD_MSG, &ActivityId, 0, 4u, v7, 4, v7 + 1, 4, v7 + 2, 4, v7 + 3, 4);
    (*(void (__fastcall **)(_QWORD, __int64))(v4 + 32))(*(_QWORD *)(v4 + 8), v13);
    return 259;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v12) = v8;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      168,
      (__int64)WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids,
      v12);
  }
  if ( v8 != 259 )
    goto LABEL_7;
  return v8;
}

```

## disassembly

```asm
0x140017c80  mov     [rsp+arg_10], rbx
0x140017c85  push    rbp
0x140017c86  push    rsi
0x140017c87  push    rdi
0x140017c88  push    r12
0x140017c8a  push    r13
0x140017c8c  push    r14
0x140017c8e  push    r15
0x140017c90  sub     rsp, 80h
0x140017c97  mov     rax, cs:__security_cookie
0x140017c9e  xor     rax, rsp
0x140017ca1  mov     [rsp+0B8h+var_40], rax
0x140017ca6  mov     rax, cs:WdfFunctions_01031
0x140017cad  mov     rsi, rdx
0x140017cb0  mov     rdx, [rcx+488h]
0x140017cb7  mov     rbx, rcx
0x140017cba  mov     r8, cs:off_14005DF70
0x140017cc1  mov     rcx, cs:WdfDriverGlobals
0x140017cc8  mov     rax, [rax+650h]
0x140017ccf  call    _guard_dispatch_icall
0x140017cd4  mov     r15d, 10h
0x140017cda  mov     r8d, 6458424Dh
0x140017ce0  mov     edx, r15d
0x140017ce3  mov     rbp, rax
0x140017ce6  mov     r13d, [rax+94h]
0x140017ced  lea     ecx, [r15+30h]
0x140017cf1  call    cs:__imp_ExAllocatePool2
0x140017cf8  nop     dword ptr [rax+rax+00h]
0x140017cfd  mov     rdi, rax
0x140017d00  test    rax, rax
0x140017d03  jnz     short loc_140017D0F
0x140017d05  mov     ebx, 0C000009Ah
0x140017d0a  jmp     loc_140017DE6
0x140017d0f  xorps   xmm0, xmm0
0x140017d12  mov     [rsi+230h], rdi
0x140017d19  mov     ecx, 1
0x140017d1e  movups  xmmword ptr [rax], xmm0
0x140017d21  mov     eax, ecx
0x140017d23  lock xadd dword ptr cs:WPP_MAIN_CB.Queue, eax
0x140017d2b  add     eax, ecx
0x140017d2d  mov     [rdi], ecx
0x140017d2f  lea     r14, [rdi+4]
0x140017d33  mov     [rsi+14h], eax
0x140017d36  mov     [r14], r15d
0x140017d39  lea     r12, [rdi+0Ch]
0x140017d3d  lea     r15, [rdi+8]
0x140017d41  mov     [r12], r13d
0x140017d45  lea     rcx, [rsp+0B8h+ActivityId]; ActivityId
0x140017d4a  mov     [r15], eax
0x140017d4d  mov     [rsp+0B8h+var_58], 0
0x140017d56  movups  xmmword ptr [rsp+0B8h+ActivityId.Data1], xmm0
0x140017d5b  call    ?MbbEventActivityIdCtl@@YAJPEAU_GUID@@@Z; MbbEventActivityIdCtl(_GUID *)
0x140017d60  mov     rcx, [rbx+488h]
0x140017d67  lea     rax, [rsp+0B8h+var_58]
0x140017d6c  mov     [rsp+0B8h+var_80], rax
0x140017d71  mov     r13d, 1
0x140017d77  lea     rax, [rsp+0B8h+ActivityId]
0x140017d7c  mov     r9, rsi
0x140017d7f  mov     [rsp+0B8h+var_88], rax
0x140017d84  mov     r8d, r13d
0x140017d87  mov     [rsp+0B8h+var_90], 10h
0x140017d90  mov     edx, r13d
0x140017d93  mov     [rsp+0B8h+var_98], rdi
0x140017d98  call    ?_CreateInner@MbxRequest@@CAJPEAUWDFDEVICE__@@W4RequestType@1@W4MessageType@1@PEAX3_KPEBU_GUID@@PEAPEAUMBBREQUEST__@@@Z; MbxRequest::_CreateInner(WDFDEVICE__ *,MbxRequest::RequestType,MbxRequest::MessageType,void *,void *,unsigned __int64,_GUID const *,MBBREQUEST__ * *)
0x140017d9d  mov     ebx, eax
0x140017d9f  test    eax, eax
0x140017da1  jz      short loc_140017DEE
0x140017da3  lea     rax, WPP_RECORDER_INITIALIZED
0x140017daa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017db1  jz      short loc_140017DDE
0x140017db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017dba  lea     rax, WPP_1cca14fdf6d03e1f3dcfafafd25c5fb2_Traceguids
0x140017dc1  mov     r9d, 0A8h
0x140017dc7  mov     dword ptr [rsp+0B8h+var_90], ebx
0x140017dcb  mov     r8d, r13d
0x140017dce  mov     [rsp+0B8h+var_98], rax
0x140017dd3  mov     dl, 2
0x140017dd5  mov     rcx, [rcx+40h]
0x140017dd9  call    WPP_RECORDER_SF_d
0x140017dde  cmp     ebx, 103h
0x140017de4  jz      short loc_140017E49
0x140017de6  mov     [rsi+280h], ebx
0x140017dec  jmp     short loc_140017E49
0x140017dee  mov     eax, 4
0x140017df3  lea     rdx, [rsp+0B8h+ActivityId]; ActivityId
0x140017df8  mov     [rsp+0B8h+var_60], rax
0x140017dfd  lea     rcx, MBIM_UINT32_PAYLOAD_MSG; EventDescriptor
0x140017e04  mov     [rsp+0B8h+var_68], r12
0x140017e09  mov     r9d, eax; unsigned __int16
0x140017e0c  mov     [rsp+0B8h+var_70], rax
0x140017e11  xor     r8d, r8d; RelatedActivityId
0x140017e14  mov     [rsp+0B8h+var_78], r15
0x140017e19  mov     [rsp+0B8h+var_80], rax
0x140017e1e  mov     [rsp+0B8h+var_88], r14
0x140017e23  mov     [rsp+0B8h+var_90], rax
0x140017e28  mov     [rsp+0B8h+var_98], rdi
0x140017e2d  call    ?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x140017e32  mov     rax, [rbp+20h]
0x140017e36  mov     rdx, [rsp+0B8h+var_58]
0x140017e3b  mov     rcx, [rbp+8]
0x140017e3f  call    _guard_dispatch_icall
0x140017e44  mov     ebx, 103h
0x140017e49  mov     eax, ebx
0x140017e4b  mov     rcx, [rsp+0B8h+var_40]
0x140017e50  xor     rcx, rsp; StackCookie
0x140017e53  call    __security_check_cookie
0x140017e58  mov     rbx, [rsp+0B8h+arg_10]
0x140017e60  add     rsp, 80h
0x140017e67  pop     r15
0x140017e69  pop     r14
0x140017e6b  pop     r13
0x140017e6d  pop     r12
0x140017e6f  pop     rdi
0x140017e70  pop     rsi
0x140017e71  pop     rbp
0x140017e72  retn
```
