# Streaming::StrmInstanceTeardownStart(_FLT_RELATED_OBJECTS const *,ulong)

- ea: `0x1400078a0`
- end: `0x14000796b`
- name: `?StrmInstanceTeardownStart@Streaming@@YAXPEBU_FLT_RELATED_OBJECTS@@K@Z`
- size: `203`
- prototype: `void __fastcall(Streaming *__hidden this, const struct _FLT_RELATED_OBJECTS *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400048a8`
- `0x140005e3c`
- `0x1400073b8`
- `0x1400078a0`

## import_xrefs

- `FLTMGR!FltCbdqDisable` at `0x1400078ce`
- `FLTMGR!FltCbdqDisable` at `0x1400078ce`
- `FLTMGR!FltReleaseContext` at `0x140007958`
- `FLTMGR!FltReleaseContext` at `0x140007958`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000793d`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x14000793d`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000792b`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14000792b`

## pseudocode

```c
void __fastcall Streaming::StrmInstanceTeardownStart(Streaming *this, const struct _FLT_RELATED_OBJECTS *a2)
{
  struct _FLT_INSTANCE *v2; // rdx
  int v3; // eax
  PFLT_CONTEXT v4; // rcx
  __int64 v5; // rbx
  char *v6; // rbx
  PFLT_CALLBACK_DATA v7; // rax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _FLT_INSTANCE *)*((_QWORD *)this + 3);
  Context = 0;
  v3 = Streaming::InstanceContextFactory::GetContext(this, v2, (struct Streaming::InstanceContext *)&Context);
  v4 = Context;
  if ( v3 >= 0 )
  {
    FltCbdqDisable((PFLT_CALLBACK_DATA_QUEUE)((char *)Context + 104));
    v5 = *((_QWORD *)Context + 31);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(v5);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(v5 + 216);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(*((_QWORD *)Context + 32));
    v6 = (char *)Context;
    while ( 1 )
    {
      v7 = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(v6 + 104), 0);
      if ( !v7 )
        break;
      v7->IoStatus.Status = -1073741536;
      v7->IoStatus.Information = 0;
      FltCompletePendedPreOperation(v7, FLT_PREOP_COMPLETE, 0);
    }
    v4 = Context;
  }
  if ( v4 )
    FltReleaseContext(v4);
}

```

## disassembly

```asm
0x1400078a0  push    rbx
0x1400078a2  sub     rsp, 20h
0x1400078a6  mov     rdx, [rcx+18h]; struct _FLT_INSTANCE *
0x1400078aa  lea     r8, [rsp+28h+Context]; struct Streaming::InstanceContext *
0x1400078af  mov     [rsp+28h+Context], 0
0x1400078b8  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x1400078bd  mov     rcx, [rsp+28h+Context]
0x1400078c2  test    eax, eax
0x1400078c4  js      loc_140007953
0x1400078ca  add     rcx, 68h ; 'h'; Cbdq
0x1400078ce  call    cs:__imp_FltCbdqDisable
0x1400078d5  nop     dword ptr [rax+rax+00h]
0x1400078da  mov     rax, [rsp+28h+Context]
0x1400078df  mov     rbx, [rax+0F8h]
0x1400078e6  mov     rcx, rbx
0x1400078e9  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x1400078ee  lea     rcx, [rbx+0D8h]
0x1400078f5  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x1400078fa  mov     rcx, [rsp+28h+Context]
0x1400078ff  mov     rcx, [rcx+100h]
0x140007906  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x14000790b  mov     rbx, [rsp+28h+Context]
0x140007910  jmp     short loc_140007937
0x140007912  xor     r8d, r8d; Context
0x140007915  mov     dword ptr [rax+18h], 0C0000120h
0x14000791c  mov     rcx, rax; CallbackData
0x14000791f  mov     qword ptr [rax+20h], 0
0x140007927  lea     edx, [r8+4]; CallbackStatus
0x14000792b  call    cs:__imp_FltCompletePendedPreOperation
0x140007932  nop     dword ptr [rax+rax+00h]
0x140007937  xor     edx, edx; PeekContext
0x140007939  lea     rcx, [rbx+68h]; Cbdq
0x14000793d  call    cs:__imp_FltCbdqRemoveNextIo
0x140007944  nop     dword ptr [rax+rax+00h]
0x140007949  test    rax, rax
0x14000794c  jnz     short loc_140007912
0x14000794e  mov     rcx, [rsp+28h+Context]; Context
0x140007953  test    rcx, rcx
0x140007956  jz      short loc_140007964
0x140007958  call    cs:__imp_FltReleaseContext
0x14000795f  nop     dword ptr [rax+rax+00h]
0x140007964  add     rsp, 20h
0x140007968  pop     rbx
0x140007969  retn
```
