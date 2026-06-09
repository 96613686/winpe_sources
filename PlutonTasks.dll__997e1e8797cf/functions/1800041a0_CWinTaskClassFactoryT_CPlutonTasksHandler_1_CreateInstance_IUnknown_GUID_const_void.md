# CWinTaskClassFactoryT<CPlutonTasksHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800041a0`
- end: `0x18000426e`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001e24`
- `0x1800041a0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPlutonTasksHandler,1>::CreateInstance(
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
      *v7 = &CPlutonTasksHandler::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CPlutonTasksHandler::`vftable')(v7, a3, a4);
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
0x1800041a0  mov     [rsp+arg_0], rbx
0x1800041a5  mov     [rsp+arg_8], rsi
0x1800041aa  push    rdi
0x1800041ab  sub     rsp, 20h
0x1800041af  mov     rdi, r9
0x1800041b2  mov     rsi, r8
0x1800041b5  test    r9, r9
0x1800041b8  jnz     short loc_1800041C4
0x1800041ba  mov     edi, 80070057h
0x1800041bf  jmp     loc_18000425C
0x1800041c4  mov     qword ptr [r9], 0
0x1800041cb  test    rdx, rdx
0x1800041ce  jz      short loc_1800041DA
0x1800041d0  mov     edi, 80040110h
0x1800041d5  jmp     loc_18000425C
0x1800041da  mov     ecx, 38h ; '8'; Size
0x1800041df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041e4  mov     ecx, 1
0x1800041e9  mov     [rsp+28h+arg_18], rax
0x1800041ee  mov     rbx, rax
0x1800041f1  mov     qword ptr [rax+8], 0
0x1800041f9  mov     dword ptr [rax+10h], 0
0x180004200  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180004208  mov     [rax+20h], ecx
0x18000420b  mov     dword ptr [rax+24h], 0
0x180004212  mov     qword ptr [rax+28h], 0
0x18000421a  mov     qword ptr [rax+30h], 0
0x180004222  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180004229  lea     rax, ??_7CPlutonTasksHandler@@6B@; const CPlutonTasksHandler::`vftable'
0x180004230  mov     r8, rdi
0x180004233  mov     [rbx], rax
0x180004236  mov     rdx, rsi
0x180004239  mov     [rbx+10h], ecx
0x18000423c  mov     rcx, rbx
0x18000423f  mov     rax, cs:??_7CPlutonTasksHandler@@6B@; const CPlutonTasksHandler::`vftable'
0x180004246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000424b  mov     edi, eax
0x18000424d  mov     rcx, [rbx]
0x180004250  mov     rax, [rcx+10h]
0x180004254  mov     rcx, rbx
0x180004257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425c  mov     rbx, [rsp+28h+arg_0]
0x180004261  mov     eax, edi
0x180004263  mov     rsi, [rsp+28h+arg_8]
0x180004268  add     rsp, 20h
0x18000426c  pop     rdi
0x18000426d  retn
```
