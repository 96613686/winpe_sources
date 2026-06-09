# CWinTaskClassFactoryT<PrinterCleanupTask,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003bf0`
- end: `0x180003cbe`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180002044`
- `0x180003bf0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PrinterCleanupTask,1>::CreateInstance(
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
      *v7 = &PrinterCleanupTask::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))PrinterCleanupTask::`vftable')(v7, a3, a4);
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
0x180003bf0  mov     [rsp+arg_0], rbx
0x180003bf5  mov     [rsp+arg_8], rsi
0x180003bfa  push    rdi
0x180003bfb  sub     rsp, 20h
0x180003bff  mov     rdi, r9
0x180003c02  mov     rsi, r8
0x180003c05  test    r9, r9
0x180003c08  jnz     short loc_180003C14
0x180003c0a  mov     edi, 80070057h
0x180003c0f  jmp     loc_180003CAC
0x180003c14  mov     qword ptr [r9], 0
0x180003c1b  test    rdx, rdx
0x180003c1e  jz      short loc_180003C2A
0x180003c20  mov     edi, 80040110h
0x180003c25  jmp     loc_180003CAC
0x180003c2a  mov     ecx, 38h ; '8'; Size
0x180003c2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c34  mov     ecx, 1
0x180003c39  mov     [rsp+28h+arg_18], rax
0x180003c3e  mov     rbx, rax
0x180003c41  mov     qword ptr [rax+8], 0
0x180003c49  mov     dword ptr [rax+10h], 0
0x180003c50  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003c58  mov     [rax+20h], ecx
0x180003c5b  mov     dword ptr [rax+24h], 0
0x180003c62  mov     qword ptr [rax+28h], 0
0x180003c6a  mov     qword ptr [rax+30h], 0
0x180003c72  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180003c79  lea     rax, ??_7PrinterCleanupTask@@6B@; const PrinterCleanupTask::`vftable'
0x180003c80  mov     r8, rdi
0x180003c83  mov     [rbx], rax
0x180003c86  mov     rdx, rsi
0x180003c89  mov     [rbx+10h], ecx
0x180003c8c  mov     rcx, rbx
0x180003c8f  mov     rax, cs:??_7PrinterCleanupTask@@6B@; const PrinterCleanupTask::`vftable'
0x180003c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c9b  mov     edi, eax
0x180003c9d  mov     rcx, [rbx]
0x180003ca0  mov     rax, [rcx+10h]
0x180003ca4  mov     rcx, rbx
0x180003ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cac  mov     rbx, [rsp+28h+arg_0]
0x180003cb1  mov     eax, edi
0x180003cb3  mov     rsi, [rsp+28h+arg_8]
0x180003cb8  add     rsp, 20h
0x180003cbc  pop     rdi
0x180003cbd  retn
```
