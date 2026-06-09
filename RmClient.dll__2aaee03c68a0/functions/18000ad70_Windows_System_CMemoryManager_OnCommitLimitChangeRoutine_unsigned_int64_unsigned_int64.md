# Windows::System::CMemoryManager::OnCommitLimitChangeRoutine(unsigned __int64,unsigned __int64)

- ea: `0x18000ad70`
- end: `0x18000add0`
- name: `?OnCommitLimitChangeRoutine@CMemoryManager@System@Windows@@CAX_K0@Z`
- size: `96`
- prototype: `void __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ad70`
- `0x18000add8`
- `0x180013ce8`
- `0x180017b94`
- `0x18001c010`

## pseudocode

```c
void __fastcall Windows::System::CMemoryManager::OnCommitLimitChangeRoutine(unsigned __int64 a1, unsigned __int64 a2)
{
  Windows::System::AppMemoryUsageLimitChangingEventArgs *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rbx

  v4 = (Windows::System::AppMemoryUsageLimitChangingEventArgs *)operator new(
                                                                  0x50u,
                                                                  (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    v5 = Windows::System::AppMemoryUsageLimitChangingEventArgs::AppMemoryUsageLimitChangingEventArgs(v4, a1, a2);
    v8 = v5;
    if ( v5 )
    {
      Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>(
        v7,
        v6,
        v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
}

```

## disassembly

```asm
0x18000ad70  mov     [rsp+arg_0], rbx
0x18000ad75  push    rdi
0x18000ad76  sub     rsp, 20h
0x18000ad7a  mov     rbx, rdx
0x18000ad7d  mov     rdi, rcx
0x18000ad80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad87  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000ad8c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad91  test    rax, rax
0x18000ad94  jz      short loc_18000ADAC
0x18000ad96  mov     r8, rbx; unsigned __int64
0x18000ad99  mov     rdx, rdi; unsigned __int64
0x18000ad9c  mov     rcx, rax; this
0x18000ad9f  call    ??0AppMemoryUsageLimitChangingEventArgs@System@Windows@@QEAA@_K0@Z; Windows::System::AppMemoryUsageLimitChangingEventArgs::AppMemoryUsageLimitChangingEventArgs(unsigned __int64,unsigned __int64)
0x18000ada4  mov     rbx, rax
0x18000ada7  test    rax, rax
0x18000adaa  jnz     short loc_18000ADB7
0x18000adac  mov     rbx, [rsp+28h+arg_0]
0x18000adb1  add     rsp, 20h
0x18000adb5  pop     rdi
0x18000adb6  retn
0x18000adb7  mov     r8, rbx
0x18000adba  call    ??$InvokeAll@$$TPEAUIAppMemoryUsageLimitChangingEventArgs@System@Windows@@@?$EventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJ$$TPEAUIAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<std::nullptr_t,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>(std::nullptr_t,Windows::System::IAppMemoryUsageLimitChangingEventArgs *)
0x18000adbf  mov     rax, [rbx]
0x18000adc2  mov     rcx, rbx
0x18000adc5  mov     rax, [rax+10h]
0x18000adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adce  jmp     short loc_18000ADAC
```
