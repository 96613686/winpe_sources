# CWinTaskClassFactoryT<PrintJobCleanupTask,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003b10`
- end: `0x180003bde`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VPrintJobCleanupTask@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180002044`
- `0x180003b10`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PrintJobCleanupTask,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rbx

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
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &PrintJobCleanupTask::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))PrintJobCleanupTask::`vftable')(v7, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
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
0x180003b10  mov     [rsp+arg_0], rbx
0x180003b15  mov     [rsp+arg_8], rsi
0x180003b1a  push    rdi
0x180003b1b  sub     rsp, 20h
0x180003b1f  mov     rdi, r9
0x180003b22  mov     rsi, r8
0x180003b25  test    r9, r9
0x180003b28  jnz     short loc_180003B34
0x180003b2a  mov     edi, 80070057h
0x180003b2f  jmp     loc_180003BCC
0x180003b34  mov     qword ptr [r9], 0
0x180003b3b  test    rdx, rdx
0x180003b3e  jz      short loc_180003B4A
0x180003b40  mov     edi, 80040110h
0x180003b45  jmp     loc_180003BCC
0x180003b4a  mov     ecx, 38h ; '8'; Size
0x180003b4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003b54  mov     ecx, 1
0x180003b59  mov     [rsp+28h+arg_18], rax
0x180003b5e  mov     rbx, rax
0x180003b61  mov     qword ptr [rax+8], 0
0x180003b69  mov     dword ptr [rax+10h], 0
0x180003b70  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003b78  mov     [rax+20h], ecx
0x180003b7b  mov     dword ptr [rax+24h], 0
0x180003b82  mov     qword ptr [rax+28h], 0
0x180003b8a  mov     qword ptr [rax+30h], 0
0x180003b92  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180003b99  lea     rax, ??_7PrintJobCleanupTask@@6B@; const PrintJobCleanupTask::`vftable'
0x180003ba0  mov     r8, rdi
0x180003ba3  mov     [rbx], rax
0x180003ba6  mov     rdx, rsi
0x180003ba9  mov     [rbx+10h], ecx
0x180003bac  mov     rcx, rbx
0x180003baf  mov     rax, cs:??_7PrintJobCleanupTask@@6B@; const PrintJobCleanupTask::`vftable'
0x180003bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbb  mov     edi, eax
0x180003bbd  mov     rcx, [rbx]
0x180003bc0  mov     rax, [rcx+10h]
0x180003bc4  mov     rcx, rbx
0x180003bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcc  mov     rbx, [rsp+28h+arg_0]
0x180003bd1  mov     eax, edi
0x180003bd3  mov     rsi, [rsp+28h+arg_8]
0x180003bd8  add     rsp, 20h
0x180003bdc  pop     rdi
0x180003bdd  retn
```
