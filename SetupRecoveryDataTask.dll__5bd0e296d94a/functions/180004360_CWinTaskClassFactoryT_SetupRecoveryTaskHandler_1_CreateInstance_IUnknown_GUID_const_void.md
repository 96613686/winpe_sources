# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004360`
- end: `0x18000443b`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180001404`
- `0x180004360`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x38u);
      v8 = v7;
      if ( v7 )
      {
        v7[1] = 0;
        *((_DWORD *)v7 + 4) = 0;
        v7[3] = -1;
        v7[4] = 1;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        *v7 = &SetupRecoveryTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))SetupRecoveryTaskHandler::`vftable')(v7, a3, a4);
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180004360  mov     [rsp+arg_0], rbx
0x180004365  mov     [rsp+arg_8], rsi
0x18000436a  push    rdi
0x18000436b  sub     rsp, 20h
0x18000436f  mov     rdi, r9
0x180004372  mov     rsi, r8
0x180004375  test    r9, r9
0x180004378  jnz     short loc_180004384
0x18000437a  mov     edi, 80070057h
0x18000437f  jmp     loc_180004429
0x180004384  mov     qword ptr [r9], 0
0x18000438b  test    rdx, rdx
0x18000438e  jz      short loc_18000439A
0x180004390  mov     edi, 80040110h
0x180004395  jmp     loc_180004429
0x18000439a  mov     ecx, 38h ; '8'; Size
0x18000439f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800043a4  mov     [rsp+28h+arg_18], rax
0x1800043a9  mov     rbx, rax
0x1800043ac  test    rax, rax
0x1800043af  jz      short loc_180004424
0x1800043b1  mov     qword ptr [rax+8], 0
0x1800043b9  mov     ecx, 1
0x1800043be  mov     dword ptr [rax+10h], 0
0x1800043c5  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800043cd  mov     [rax+20h], ecx
0x1800043d0  mov     dword ptr [rax+24h], 0
0x1800043d7  mov     qword ptr [rax+28h], 0
0x1800043df  mov     qword ptr [rax+30h], 0
0x1800043e7  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800043ee  lea     rax, ??_7SetupRecoveryTaskHandler@@6B@; const SetupRecoveryTaskHandler::`vftable'
0x1800043f5  mov     [rbx], rax
0x1800043f8  test    rbx, rbx
0x1800043fb  jz      short loc_180004424
0x1800043fd  mov     rax, [rax]
0x180004400  mov     r8, rdi
0x180004403  mov     [rbx+10h], ecx
0x180004406  mov     rdx, rsi
0x180004409  mov     rcx, rbx
0x18000440c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004411  mov     rdx, [rbx]
0x180004414  mov     edi, eax
0x180004416  mov     rcx, rbx
0x180004419  mov     rax, [rdx+10h]
0x18000441d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004422  jmp     short loc_180004429
0x180004424  mov     edi, 8007000Eh
0x180004429  mov     rbx, [rsp+28h+arg_0]
0x18000442e  mov     eax, edi
0x180004430  mov     rsi, [rsp+28h+arg_8]
0x180004435  add     rsp, 20h
0x180004439  pop     rdi
0x18000443a  retn
```
