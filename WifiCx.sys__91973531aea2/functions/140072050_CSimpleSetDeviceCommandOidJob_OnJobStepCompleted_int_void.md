# CSimpleSetDeviceCommandOidJob::OnJobStepCompleted(int,void *)

- ea: `0x140072050`
- end: `0x1400722fb`
- name: `?OnJobStepCompleted@CSimpleSetDeviceCommandOidJob@@UEAAXHPEAX@Z`
- size: `683`
- prototype: `void __fastcall(CSimpleSetDeviceCommandOidJob *__hidden this, int, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140012f80`
- `0x140013390`
- `0x140013510`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14001f938`
- `0x14002073c`
- `0x14002bd34`
- `0x140072050`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall CSimpleSetDeviceCommandOidJob::OnJobStepCompleted(
        CSimpleSetDeviceCommandOidJob *this,
        unsigned int a2,
        void *a3)
{
  unsigned int CommandResult; // edi
  int v5; // edx
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // esi
  unsigned int v11; // eax
  __int64 v12; // r8
  int v13; // r9d
  unsigned int v14; // [rsp+38h] [rbp-18h]
  unsigned int v15; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int8 *v17; // [rsp+88h] [rbp+38h] BYREF

  v16 = 0;
  CommandResult = a2;
  v15 = 0;
  v17 = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        74,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v14);
    }
    goto LABEL_25;
  }
  CommandResult = DeviceCommand::get_CommandResult(*((DeviceCommand **)this + 77), &v15, &v17);
  if ( CommandResult )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v6,
        75,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    goto LABEL_25;
  }
  if ( v15 < 0x30 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v6,
        76,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    CommandResult = -1073741823;
    goto LABEL_25;
  }
  if ( *((_BYTE *)this + 596) )
  {
    CommandResult = CMessageHelper::GetStatusFromTaskOutput(
                      (CSimpleSetDeviceCommandOidJob *)((char *)this + 624),
                      (unsigned int *)&v16);
    if ( CommandResult )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_25;
      v9 = 77;
LABEL_15:
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        v9,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_DWORD *)v17,
        CommandResult);
      goto LABEL_25;
    }
  }
  else
  {
    CommandResult = CMessageHelper::GetStatusFromCommandResult(
                      *((struct DeviceCommand **)this + 77),
                      (unsigned int *)&v16);
    if ( CommandResult )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_25;
      v9 = 78;
      goto LABEL_15;
    }
  }
  v10 = v16;
  if ( v16 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v8,
        79,
        (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_DWORD *)v17,
        v16);
    }
    CommandResult = v10;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qDL(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      80,
      (__int64)WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      *(_DWORD *)v17);
  }
LABEL_25:
  v11 = (*(__int64 (__fastcall **)(CSimpleSetDeviceCommandOidJob *, _QWORD, _QWORD, unsigned __int8 *))(*(_QWORD *)this + 80LL))(
          this,
          CommandResult,
          v15,
          v17);
  CJobBase::CompleteJob(this, v11, v12, v13);
}

```

## disassembly

```asm
0x140072050  mov     [rsp-18h+arg_10], rbx
0x140072055  push    rbp
0x140072056  push    rsi
0x140072057  push    rdi
0x140072058  mov     rbp, rsp
0x14007205b  sub     rsp, 50h
0x14007205f  mov     [rbp+arg_8], 0
0x140072066  mov     edi, edx
0x140072068  mov     [rbp+arg_0], 0
0x14007206f  mov     rbx, rcx
0x140072072  mov     [rbp+arg_18], 0
0x14007207a  test    edx, edx
0x14007207c  jz      short loc_1400720CB
0x14007207e  lea     rax, WPP_RECORDER_INITIALIZED
0x140072085  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007208c  jz      loc_1400722C7
0x140072092  mov     eax, [rcx+10h]
0x140072095  mov     r9d, 4Ah ; 'J'
0x14007209b  mov     [rsp+50h+var_18], edx
0x14007209f  mov     dl, 2
0x1400720a1  mov     [rsp+50h+var_20], eax
0x1400720a5  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x1400720ac  mov     [rsp+50h+var_28], rcx
0x1400720b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400720b8  mov     [rsp+50h+var_30], rax
0x1400720bd  mov     rcx, [rcx+40h]
0x1400720c1  call    WPP_RECORDER_SF_qDD
0x1400720c6  jmp     loc_1400722C7
0x1400720cb  mov     rcx, [rcx+268h]; this
0x1400720d2  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x1400720d6  lea     rdx, [rbp+arg_0]; unsigned int *
0x1400720da  call    ?get_CommandResult@DeviceCommand@@QEAAHPEAKPEAPEAE@Z; DeviceCommand::get_CommandResult(ulong *,uchar * *)
0x1400720df  mov     edi, eax
0x1400720e1  test    eax, eax
0x1400720e3  jz      short loc_14007212E
0x1400720e5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400720ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400720f3  jz      loc_1400722C7
0x1400720f9  mov     eax, [rbx+10h]
0x1400720fc  mov     r9d, 4Bh ; 'K'
0x140072102  mov     rcx, cs:WPP_GLOBAL_Control
0x140072109  mov     dl, 2
0x14007210b  mov     [rsp+50h+var_20], eax
0x14007210f  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x140072116  mov     [rsp+50h+var_28], rbx
0x14007211b  mov     [rsp+50h+var_30], rax
0x140072120  mov     rcx, [rcx+40h]
0x140072124  call    WPP_RECORDER_SF_qD
0x140072129  jmp     loc_1400722C7
0x14007212e  cmp     [rbp+arg_0], 30h ; '0'
0x140072132  jnb     short loc_14007217E
0x140072134  lea     rax, WPP_RECORDER_INITIALIZED
0x14007213b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140072142  jz      short loc_140072174
0x140072144  mov     eax, [rbx+10h]
0x140072147  mov     r9d, 4Ch ; 'L'
0x14007214d  mov     rcx, cs:WPP_GLOBAL_Control
0x140072154  mov     dl, 2
0x140072156  mov     [rsp+50h+var_20], eax
0x14007215a  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x140072161  mov     [rsp+50h+var_28], rbx
0x140072166  mov     [rsp+50h+var_30], rax
0x14007216b  mov     rcx, [rcx+40h]
0x14007216f  call    WPP_RECORDER_SF_qD
0x140072174  mov     edi, 0C0000001h
0x140072179  jmp     loc_1400722C7
0x14007217e  cmp     byte ptr [rbx+254h], 0
0x140072185  lea     rdx, [rbp+arg_8]; int *
0x140072189  jz      short loc_1400721F8
0x14007218b  lea     rcx, [rbx+270h]; struct Task *
0x140072192  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x140072197  mov     edi, eax
0x140072199  test    eax, eax
0x14007219b  jz      loc_140072226
0x1400721a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400721a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400721af  jz      loc_1400722C7
0x1400721b5  mov     r9d, 4Dh ; 'M'
0x1400721bb  mov     rax, [rbp+arg_18]
0x1400721bf  mov     dl, 2
0x1400721c1  mov     [rsp+50h+var_10], edi
0x1400721c5  mov     ecx, [rax]
0x1400721c7  mov     eax, [rbx+10h]
0x1400721ca  mov     [rsp+50h+var_18], ecx
0x1400721ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400721d5  mov     [rsp+50h+var_20], eax
0x1400721d9  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x1400721e0  mov     [rsp+50h+var_28], rbx
0x1400721e5  mov     [rsp+50h+var_30], rax
0x1400721ea  mov     rcx, [rcx+40h]
0x1400721ee  call    WPP_RECORDER_SF_qDdd
0x1400721f3  jmp     loc_1400722C7
0x1400721f8  mov     rcx, [rbx+268h]; struct DeviceCommand *
0x1400721ff  call    ?GetStatusFromCommandResult@CMessageHelper@@SAHPEAVDeviceCommand@@PEAH@Z; CMessageHelper::GetStatusFromCommandResult(DeviceCommand *,int *)
0x140072204  mov     edi, eax
0x140072206  test    eax, eax
0x140072208  jz      short loc_140072226
0x14007220a  lea     rax, WPP_RECORDER_INITIALIZED
0x140072211  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140072218  jz      loc_1400722C7
0x14007221e  mov     r9d, 4Eh ; 'N'
0x140072224  jmp     short loc_1400721BB
0x140072226  mov     esi, [rbp+arg_8]
0x140072229  test    esi, esi
0x14007222b  jz      short loc_14007227F
0x14007222d  lea     rax, WPP_RECORDER_INITIALIZED
0x140072234  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007223b  jz      short loc_14007227B
0x14007223d  mov     rax, [rbp+arg_18]
0x140072241  mov     r9d, 4Fh ; 'O'
0x140072247  mov     [rsp+50h+var_10], esi
0x14007224b  mov     dl, 4
0x14007224d  mov     ecx, [rax]
0x14007224f  mov     eax, [rbx+10h]
0x140072252  mov     [rsp+50h+var_18], ecx
0x140072256  mov     rcx, cs:WPP_GLOBAL_Control
0x14007225d  mov     [rsp+50h+var_20], eax
0x140072261  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x140072268  mov     [rsp+50h+var_28], rbx
0x14007226d  mov     [rsp+50h+var_30], rax
0x140072272  mov     rcx, [rcx+40h]
0x140072276  call    WPP_RECORDER_SF_qDdd
0x14007227b  mov     edi, esi
0x14007227d  jmp     short loc_1400722C7
0x14007227f  lea     rax, WPP_RECORDER_INITIALIZED
0x140072286  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007228d  jz      short loc_1400722C7
0x14007228f  mov     rax, [rbp+arg_18]
0x140072293  mov     r9d, 50h ; 'P'
0x140072299  mov     ecx, [rax]
0x14007229b  mov     eax, [rbx+10h]
0x14007229e  mov     [rsp+50h+var_18], ecx
0x1400722a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400722a9  mov     [rsp+50h+var_20], eax
0x1400722ad  lea     rax, WPP_c1ae99ddfe8433641ed2df3567579b10_Traceguids
0x1400722b4  mov     [rsp+50h+var_28], rbx
0x1400722b9  mov     [rsp+50h+var_30], rax
0x1400722be  mov     rcx, [rcx+40h]
0x1400722c2  call    WPP_RECORDER_SF_qDL
0x1400722c7  mov     rax, [rbx]
0x1400722ca  mov     edx, edi
0x1400722cc  mov     r9, [rbp+arg_18]
0x1400722d0  mov     rcx, rbx
0x1400722d3  mov     r8d, [rbp+arg_0]
0x1400722d7  mov     rax, [rax+50h]
0x1400722db  call    _guard_dispatch_icall
0x1400722e0  mov     edx, eax; int
0x1400722e2  mov     rcx, rbx; this
0x1400722e5  call    ?CompleteJob@CJobBase@@IEAAHH@Z; CJobBase::CompleteJob(int)
0x1400722ea  mov     rbx, [rsp+50h+arg_10]
0x1400722f2  add     rsp, 50h
0x1400722f6  pop     rdi
0x1400722f7  pop     rsi
0x1400722f8  pop     rbp
0x1400722f9  retn
```
