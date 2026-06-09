# CAdapter::SendCreateWifiCxAdapterRequests(_DOT11_WIFICX_ADAPTER_TYPE,bool)

- ea: `0x14002d660`
- end: `0x14002d92e`
- name: `?SendCreateWifiCxAdapterRequests@CAdapter@@QEAAJW4_DOT11_WIFICX_ADAPTER_TYPE@@_N@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400cded4`

## callees

- `0x140006fec`
- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x14001a1e0`
- `0x14002b148`
- `0x14002b1f4`
- `0x14002d660`
- `0x1400520a8`
- `0x140069198`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CAdapter::SendCreateWifiCxAdapterRequests(__int64 a1)
{
  struct IEventContext *v2; // rdi
  int v3; // edx
  COidJobBase *v4; // r14
  unsigned int NextActivityId; // eax
  int v6; // edx
  int v7; // ebx
  int v8; // r9d
  _QWORD *v9; // rax
  int v10; // edx
  struct IOperationCompletionCallback *v11; // r15
  int v12; // eax
  int v13; // edx
  void (__fastcall **v14)(_QWORD, _QWORD); // rax
  int v15; // edx
  struct IOperationCompletionCallback *v17[2]; // [rsp+30h] [rbp-10h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  struct IEventContext *v19; // [rsp+88h] [rbp+48h] BYREF

  v18 = 0;
  v2 = 0;
  v17[0] = 0;
  v19 = 0;
  v4 = (COidJobBase *)operator new(0x340u);
  if ( v4 )
  {
    NextActivityId = IActivityId::get_NextActivityId();
    COidJobBase::COidJobBase(v4, NextActivityId);
    *((_BYTE *)v4 + 580) = 0;
    *(_QWORD *)v4 = &CCreateAdapterOidJob::`vftable'{for `IOperationCompletionCallback'};
    *((_QWORD *)v4 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
    v7 = CCreateAdapterOidJob::InitializeForOid(v4, a1);
    if ( v7 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_22;
      v8 = 165;
    }
    else
    {
      *((_BYTE *)v4 + 507) = 0;
      v9 = operator new(0x18u);
      if ( v9 )
      {
        v9[1] = 0;
        *v9 = &CJobCompleteNotifier::`vftable';
        v9[2] = 0;
      }
      wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset((_QWORD **)v17, v9);
      v11 = v17[0];
      if ( !v17[0] )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            1,
            166,
            (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
        }
        v7 = -1073741670;
        goto LABEL_22;
      }
      v12 = IEventContext::CreateInstance(&v19);
      v7 = v12;
      if ( v12 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            167,
            (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
            v12);
        }
        v2 = v19;
        goto LABEL_22;
      }
      v2 = v19;
      *((_QWORD *)v11 + 1) = v19;
      *((_QWORD *)v11 + 2) = &v18;
      v7 = SerializedJobList::QueueSerializedJob((EventQueue **)(a1 + 848), v4, v11);
      if ( !v7 )
      {
        v14 = *(void (__fastcall ***)(_QWORD, _QWORD))v2;
        v17[0] = 0;
        ((void (__fastcall *)(struct IEventContext *))v14[3])(v2);
        v7 = v18;
        if ( v18 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            1,
            170,
            (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids,
            v18);
        }
        goto LABEL_22;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_22:
        (*(void (__fastcall **)(COidJobBase *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
        if ( v2 )
          (**(void (__fastcall ***)(struct IEventContext *, __int64))v2)(v2, 1);
        goto LABEL_27;
      }
      v8 = 169;
    }
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      v8,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
    goto LABEL_22;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      1,
      164,
      (__int64)WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids);
  }
  v7 = -1073741670;
LABEL_27:
  wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset((_QWORD **)v17, 0);
  return v7 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x14002d660  mov     [rsp-28h+arg_0], rbx
0x14002d665  mov     [rsp-28h+arg_8], rsi
0x14002d66a  mov     byte ptr [rsp-28h+arg_10], r8b
0x14002d66f  push    rbp
0x14002d670  push    rdi
0x14002d671  push    r13
0x14002d673  push    r14
0x14002d675  push    r15
0x14002d677  mov     rbp, rsp
0x14002d67a  sub     rsp, 40h
0x14002d67e  mov     r13, rcx
0x14002d681  mov     [rbp+arg_10], 0
0x14002d688  xor     edi, edi
0x14002d68a  mov     [rbp+var_10], 0
0x14002d692  mov     ecx, 340h; unsigned __int64
0x14002d697  mov     [rbp+arg_18], rdi
0x14002d69b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002d6a0  mov     r14, rax
0x14002d6a3  test    rax, rax
0x14002d6a6  jz      loc_14002D8C0
0x14002d6ac  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14002d6b1  mov     edx, eax; unsigned int
0x14002d6b3  mov     rcx, r14; this
0x14002d6b6  call    ??0COidJobBase@@QEAA@K@Z; COidJobBase::COidJobBase(ulong)
0x14002d6bb  lea     rcx, ??_7CCreateAdapterOidJob@@6BIOperationCompletionCallback@@@; const CCreateAdapterOidJob::`vftable'{for `IOperationCompletionCallback'}
0x14002d6c2  mov     [r14+244h], dil
0x14002d6c9  mov     [r14], rcx
0x14002d6cc  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x14002d6d3  mov     rcx, r14
0x14002d6d6  mov     [r14+8], rax
0x14002d6da  mov     rdx, r13
0x14002d6dd  call    ?InitializeForOid@CCreateAdapterOidJob@@QEAAHPEAVCAdapter@@W4_DOT11_WIFICX_ADAPTER_TYPE@@@Z; CCreateAdapterOidJob::InitializeForOid(CAdapter *,_DOT11_WIFICX_ADAPTER_TYPE)
0x14002d6e2  lea     esi, [rdi+1]
0x14002d6e5  mov     ebx, eax
0x14002d6e7  test    eax, eax
0x14002d6e9  jz      short loc_14002D72B
0x14002d6eb  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d6f2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d6f9  jz      loc_14002D898
0x14002d6ff  mov     r9d, 0A5h
0x14002d705  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d70c  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14002d713  mov     r8d, esi
0x14002d716  mov     [rsp+40h+var_20], rax
0x14002d71b  mov     dl, 2
0x14002d71d  mov     rcx, [rcx+40h]
0x14002d721  call    WPP_RECORDER_SF_
0x14002d726  jmp     loc_14002D898
0x14002d72b  mov     ecx, 18h; unsigned __int64
0x14002d730  mov     [r14+1FBh], dil
0x14002d737  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002d73c  test    rax, rax
0x14002d73f  jz      short loc_14002D753
0x14002d741  lea     rcx, ??_7CJobCompleteNotifier@@6B@; const CJobCompleteNotifier::`vftable'
0x14002d748  mov     [rax+8], rdi
0x14002d74c  mov     [rax], rcx
0x14002d74f  mov     [rax+10h], rdi
0x14002d753  mov     rdx, rax
0x14002d756  lea     rcx, [rbp+var_10]
0x14002d75a  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x14002d75f  mov     r15, [rbp+var_10]
0x14002d763  test    r15, r15
0x14002d766  jnz     short loc_14002D7A9
0x14002d768  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d76f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d776  jz      short loc_14002D79F
0x14002d778  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d77f  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14002d786  mov     r9d, 0A6h
0x14002d78c  mov     [rsp+40h+var_20], rax
0x14002d791  mov     r8d, esi
0x14002d794  mov     dl, 2
0x14002d796  mov     rcx, [rcx+40h]
0x14002d79a  call    WPP_RECORDER_SF_
0x14002d79f  mov     ebx, 0C000009Ah
0x14002d7a4  jmp     loc_14002D898
0x14002d7a9  lea     rcx, [rbp+arg_18]; struct IEventContext **
0x14002d7ad  call    ?CreateInstance@IEventContext@@SAHPEAPEAV1@@Z; IEventContext::CreateInstance(IEventContext * *)
0x14002d7b2  mov     ebx, eax
0x14002d7b4  test    eax, eax
0x14002d7b6  jz      short loc_14002D7FC
0x14002d7b8  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d7bf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d7c6  jz      short loc_14002D7F3
0x14002d7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d7cf  mov     r9d, 0A7h
0x14002d7d5  mov     [rsp+40h+var_18], eax
0x14002d7d9  mov     r8d, esi
0x14002d7dc  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14002d7e3  mov     dl, 2
0x14002d7e5  mov     [rsp+40h+var_20], rax
0x14002d7ea  mov     rcx, [rcx+40h]
0x14002d7ee  call    WPP_RECORDER_SF_d
0x14002d7f3  mov     rdi, [rbp+arg_18]
0x14002d7f7  jmp     loc_14002D898
0x14002d7fc  mov     rdi, [rbp+arg_18]
0x14002d800  lea     rax, [rbp+arg_10]
0x14002d804  lea     rcx, [r13+350h]; this
0x14002d80b  mov     [r15+8], rdi
0x14002d80f  mov     r8, r15; struct IOperationCompletionCallback *
0x14002d812  mov     [r15+10h], rax
0x14002d816  mov     rdx, r14; struct CJobBase *
0x14002d819  call    ?QueueSerializedJob@SerializedJobList@@QEAAHPEAVCJobBase@@PEAVIOperationCompletionCallback@@@Z; SerializedJobList::QueueSerializedJob(CJobBase *,IOperationCompletionCallback *)
0x14002d81e  mov     ebx, eax
0x14002d820  test    eax, eax
0x14002d822  jz      short loc_14002D83F
0x14002d824  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d82b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d832  jz      short loc_14002D898
0x14002d834  mov     r9d, 0A9h
0x14002d83a  jmp     loc_14002D705
0x14002d83f  mov     rax, [rdi]
0x14002d842  mov     rcx, rdi
0x14002d845  mov     [rbp+var_10], 0
0x14002d84d  mov     rax, [rax+18h]
0x14002d851  call    _guard_dispatch_icall
0x14002d856  mov     ebx, [rbp+arg_10]
0x14002d859  test    ebx, ebx
0x14002d85b  jz      short loc_14002D898
0x14002d85d  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d864  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d86b  jz      short loc_14002D898
0x14002d86d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d874  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14002d87b  mov     r9d, 0AAh
0x14002d881  mov     [rsp+40h+var_18], ebx
0x14002d885  mov     r8d, esi
0x14002d888  mov     [rsp+40h+var_20], rax
0x14002d88d  mov     dl, 2
0x14002d88f  mov     rcx, [rcx+40h]
0x14002d893  call    WPP_RECORDER_SF_d
0x14002d898  mov     rax, [r14]
0x14002d89b  mov     edx, esi
0x14002d89d  mov     rcx, r14
0x14002d8a0  mov     rax, [rax+28h]
0x14002d8a4  call    _guard_dispatch_icall
0x14002d8a9  test    rdi, rdi
0x14002d8ac  jz      short loc_14002D8FF
0x14002d8ae  mov     rax, [rdi]
0x14002d8b1  mov     edx, esi
0x14002d8b3  mov     rcx, rdi
0x14002d8b6  mov     rax, [rax]
0x14002d8b9  call    _guard_dispatch_icall
0x14002d8be  jmp     short loc_14002D8FF
0x14002d8c0  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002d8c7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002d8ce  jz      short loc_14002D8FA
0x14002d8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d8d7  lea     rax, WPP_3c173e8d5cac37f2f7d07fc338dd93ef_Traceguids
0x14002d8de  mov     r9d, 0A4h
0x14002d8e4  mov     [rsp+40h+var_20], rax
0x14002d8e9  mov     r8d, 1
0x14002d8ef  mov     dl, 2
0x14002d8f1  mov     rcx, [rcx+40h]
0x14002d8f5  call    WPP_RECORDER_SF_
0x14002d8fa  mov     ebx, 0C000009Ah
0x14002d8ff  neg     ebx
0x14002d901  lea     rcx, [rbp+var_10]
0x14002d905  sbb     ebx, ebx
0x14002d907  xor     edx, edx
0x14002d909  and     ebx, 0C0000001h
0x14002d90f  call    ?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z; wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)
0x14002d914  mov     rsi, [rsp+40h+arg_8]
0x14002d919  mov     eax, ebx
0x14002d91b  mov     rbx, [rsp+40h+arg_0]
0x14002d920  add     rsp, 40h
0x14002d924  pop     r15
0x14002d926  pop     r14
0x14002d928  pop     r13
0x14002d92a  pop     rdi
0x14002d92b  pop     rbp
0x14002d92c  retn
```
