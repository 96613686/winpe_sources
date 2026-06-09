# DeviceCommandScheduler::CancelTask(DeviceCommand *)

- ea: `0x140061b6c`
- end: `0x140061d0b`
- name: `?CancelTask@DeviceCommandScheduler@@QEAAXPEAVDeviceCommand@@@Z`
- size: `415`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, struct DeviceCommand *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400623b8`
- `0x140062cb8`

## callees

- `0x140009420`
- `0x14000c778`
- `0x140022ab0`
- `0x140022db4`
- `0x140024428`
- `0x1400592e8`
- `0x140061750`
- `0x140061b6c`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::CancelTask(struct CAdapter **this, struct DeviceCommand *a2)
{
  struct DeviceCommand *v2; // rbp
  int v4; // r9d
  DeviceCommand *v5; // rcx
  _QWORD *v6; // rcx
  int v7; // eax
  int v8; // r8d
  int started; // eax
  __int64 v10; // [rsp+28h] [rbp-30h]
  struct DeviceCommand *v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = 0;
  v2 = a2;
  if ( a2 )
  {
    v5 = (DeviceCommand *)operator new(0xF8u);
    if ( v5 )
    {
      DeviceCommand::DeviceCommand(v5, *((_DWORD *)v2 + 2));
      *v6 = &CancelDeviceCommand::`vftable';
    }
    else
    {
      v6 = 0;
    }
    wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(&v11, v6);
    if ( !v11 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v4 = 15;
      LODWORD(v10) = -1073741670;
      goto LABEL_4;
    }
    v7 = CancelDeviceCommand::Initialize(v11, v2, this[22]);
    if ( v7 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_20;
      v4 = 16;
      LODWORD(v10) = v7;
      goto LABEL_4;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 4;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        v8,
        17,
        (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
        (char)v2);
    }
    started = DeviceCommandScheduler::StartCommand(
                (DeviceCommandScheduler *)this,
                v11,
                (struct IOperationCompletionCallback *)((unsigned __int64)(this + 1) & -(__int64)(this != 0)),
                *((struct CJobBase **)v2 + 21));
    if ( !started )
    {
      v11 = 0;
      goto LABEL_20;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v4 = 18;
      LODWORD(v10) = started;
      goto LABEL_4;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v4 = 14;
    LODWORD(v10) = -1073741811;
LABEL_4:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      v4,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
      v10);
  }
LABEL_20:
  wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(&v11, 0);
}

```

## disassembly

```asm
0x140061b6c  push    rbp
0x140061b6e  push    rsi
0x140061b6f  push    rdi
0x140061b70  push    r14
0x140061b72  sub     rsp, 38h
0x140061b76  mov     [rsp+58h+arg_8], 0
0x140061b7f  mov     rbp, rdx
0x140061b82  mov     r14, rcx
0x140061b85  test    rdx, rdx
0x140061b88  jnz     short loc_140061BD3
0x140061b8a  lea     rdi, WPP_RECORDER_INITIALIZED
0x140061b91  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140061b98  jz      loc_140061CF4
0x140061b9e  lea     r9d, [rdx+0Eh]
0x140061ba2  mov     dword ptr [rsp+58h+var_30], 0C000000Dh
0x140061baa  lea     rsi, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140061bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140061bb8  mov     r8d, 1
0x140061bbe  mov     dl, 2
0x140061bc0  mov     [rsp+58h+var_38], rsi
0x140061bc5  mov     rcx, [rcx+40h]
0x140061bc9  call    WPP_RECORDER_SF_d
0x140061bce  jmp     loc_140061CF4
0x140061bd3  mov     ecx, 0F8h; unsigned __int64
0x140061bd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140061bdd  mov     rcx, rax; this
0x140061be0  test    rax, rax
0x140061be3  jz      short loc_140061BF9
0x140061be5  mov     edx, [rbp+8]; unsigned int
0x140061be8  call    ??0DeviceCommand@@QEAA@K@Z; DeviceCommand::DeviceCommand(ulong)
0x140061bed  lea     r10, ??_7CancelDeviceCommand@@6B@; const CancelDeviceCommand::`vftable'
0x140061bf4  mov     [rcx], r10
0x140061bf7  jmp     short loc_140061BFB
0x140061bf9  xor     ecx, ecx
0x140061bfb  mov     rdx, rcx
0x140061bfe  lea     rcx, [rsp+58h+arg_8]
0x140061c03  call    ?reset@?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@QEAAXPEAVIEventContext@@@Z; wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(IEventContext *)
0x140061c08  cmp     [rsp+58h+arg_8], 0
0x140061c0e  jnz     short loc_140061C37
0x140061c10  lea     rdi, WPP_RECORDER_INITIALIZED
0x140061c17  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140061c1e  jz      loc_140061CF4
0x140061c24  mov     r9d, 0Fh
0x140061c2a  mov     dword ptr [rsp+58h+var_30], 0C000009Ah
0x140061c32  jmp     loc_140061BAA
0x140061c37  mov     r8, [r14+0B0h]; struct CAdapter *
0x140061c3e  mov     rdx, rbp; struct DeviceCommand *
0x140061c41  mov     rcx, [rsp+58h+arg_8]; this
0x140061c46  call    ?Initialize@CancelDeviceCommand@@QEAAHPEAVDeviceCommand@@PEAVCAdapter@@@Z; CancelDeviceCommand::Initialize(DeviceCommand *,CAdapter *)
0x140061c4b  test    eax, eax
0x140061c4d  jz      short loc_140061C72
0x140061c4f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140061c56  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140061c5d  jz      loc_140061CF4
0x140061c63  mov     r9d, 10h
0x140061c69  mov     dword ptr [rsp+58h+var_30], eax
0x140061c6d  jmp     loc_140061BAA
0x140061c72  lea     rdi, WPP_RECORDER_INITIALIZED
0x140061c79  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140061c80  lea     rsi, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x140061c87  jz      short loc_140061CAB
0x140061c89  mov     rcx, cs:WPP_GLOBAL_Control
0x140061c90  mov     r9d, 11h
0x140061c96  mov     [rsp+58h+var_30], rbp
0x140061c9b  mov     dl, 4
0x140061c9d  mov     [rsp+58h+var_38], rsi
0x140061ca2  mov     rcx, [rcx+40h]
0x140061ca6  call    WPP_RECORDER_SF_q
0x140061cab  mov     r9, [rbp+0A8h]; struct CJobBase *
0x140061cb2  lea     rcx, [r14+8]
0x140061cb6  mov     rdx, [rsp+58h+arg_8]; struct DeviceCommand *
0x140061cbb  mov     rax, r14
0x140061cbe  neg     rax
0x140061cc1  sbb     r8, r8
0x140061cc4  and     r8, rcx; struct IOperationCompletionCallback *
0x140061cc7  mov     rcx, r14; this
0x140061cca  call    ?StartCommand@DeviceCommandScheduler@@QEAAHPEAVDeviceCommand@@PEAVIOperationCompletionCallback@@PEAVCJobBase@@@Z; DeviceCommandScheduler::StartCommand(DeviceCommand *,IOperationCompletionCallback *,CJobBase *)
0x140061ccf  test    eax, eax
0x140061cd1  jz      short loc_140061CEB
0x140061cd3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140061cda  jz      short loc_140061CF4
0x140061cdc  mov     r9d, 12h
0x140061ce2  mov     dword ptr [rsp+58h+var_30], eax
0x140061ce6  jmp     loc_140061BB1
0x140061ceb  mov     [rsp+58h+arg_8], 0
0x140061cf4  xor     edx, edx
0x140061cf6  lea     rcx, [rsp+58h+arg_8]
0x140061cfb  call    ?reset@?$unique_ptr@VIEventContext@@U?$default_delete@VIEventContext@@@wistd@@@wistd@@QEAAXPEAVIEventContext@@@Z; wistd::unique_ptr<IEventContext,wistd::default_delete<IEventContext>>::reset(IEventContext *)
0x140061d00  add     rsp, 38h
0x140061d04  pop     r14
0x140061d06  pop     rdi
0x140061d07  pop     rsi
0x140061d08  pop     rbp
0x140061d09  retn
```
