# Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>(void)

- ea: `0x1400082ec`
- end: `0x140008351`
- name: `??1?$Array@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140008524`

## callees

- `0x140003644`
- `0x1400082ec`
- `0x1400086ac`

## pseudocode

```c
void __fastcall Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::~Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 i; // rdi
  void *v4; // rsi
  unsigned __int64 v5; // rdx

  if ( *(_QWORD *)a1 )
  {
    if ( *(_BYTE *)(a1 + 24) )
    {
      for ( i = 0; i < *(_QWORD *)(a1 + 16); ++i )
      {
        v4 = *(void **)(*(_QWORD *)a1 + 8 * i);
        if ( v4 )
        {
          OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(
            *(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper **)(*(_QWORD *)a1 + 8 * i),
            0);
          operator delete(v4, v5);
        }
      }
    }
    operator delete(*(void **)a1, a2);
  }
}

```

## disassembly

```asm
0x1400082ec  mov     [rsp+arg_0], rbx
0x1400082f1  mov     [rsp+arg_8], rsi
0x1400082f6  push    rdi
0x1400082f7  sub     rsp, 20h
0x1400082fb  cmp     qword ptr [rcx], 0
0x1400082ff  mov     rbx, rcx
0x140008302  jz      short loc_140008341
0x140008304  cmp     byte ptr [rcx+18h], 0
0x140008308  jz      short loc_140008339
0x14000830a  xor     edi, edi
0x14000830c  cmp     [rcx+10h], rdi
0x140008310  jbe     short loc_140008339
0x140008312  mov     rax, [rbx]
0x140008315  mov     rsi, [rax+rdi*8]
0x140008319  test    rsi, rsi
0x14000831c  jz      short loc_140008330
0x14000831e  xor     edx, edx; unsigned int
0x140008320  mov     rcx, rsi; this
0x140008323  call    ??_GCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAPEAXI@Z; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::`scalar deleting destructor'(uint)
0x140008328  mov     rcx, rsi; void *
0x14000832b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008330  inc     rdi
0x140008333  cmp     rdi, [rbx+10h]
0x140008337  jb      short loc_140008312
0x140008339  mov     rcx, [rbx]; void *
0x14000833c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008341  mov     rbx, [rsp+28h+arg_0]
0x140008346  mov     rsi, [rsp+28h+arg_8]
0x14000834b  add     rsp, 20h
0x14000834f  pop     rdi
0x140008350  retn
```
