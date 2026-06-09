# CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800294a0`
- end: `0x18002957b`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800020c4`
- `0x1800294a0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::CreateInstance(
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
        *v7 = &CDeferredChargingTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CDeferredChargingTaskHandler::`vftable')(v7, a3, a4);
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
0x1800294a0  mov     [rsp+arg_0], rbx
0x1800294a5  mov     [rsp+arg_8], rsi
0x1800294aa  push    rdi
0x1800294ab  sub     rsp, 20h
0x1800294af  mov     rdi, r9
0x1800294b2  mov     rsi, r8
0x1800294b5  test    r9, r9
0x1800294b8  jnz     short loc_1800294C4
0x1800294ba  mov     edi, 80070057h
0x1800294bf  jmp     loc_180029569
0x1800294c4  mov     qword ptr [r9], 0
0x1800294cb  test    rdx, rdx
0x1800294ce  jz      short loc_1800294DA
0x1800294d0  mov     edi, 80040110h
0x1800294d5  jmp     loc_180029569
0x1800294da  mov     ecx, 38h ; '8'; Size
0x1800294df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800294e4  mov     [rsp+28h+arg_18], rax
0x1800294e9  mov     rbx, rax
0x1800294ec  test    rax, rax
0x1800294ef  jz      short loc_180029564
0x1800294f1  mov     qword ptr [rax+8], 0
0x1800294f9  mov     ecx, 1
0x1800294fe  mov     dword ptr [rax+10h], 0
0x180029505  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18002950d  mov     [rax+20h], ecx
0x180029510  mov     dword ptr [rax+24h], 0
0x180029517  mov     qword ptr [rax+28h], 0
0x18002951f  mov     qword ptr [rax+30h], 0
0x180029527  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18002952e  lea     rax, ??_7CDeferredChargingTaskHandler@@6B@; const CDeferredChargingTaskHandler::`vftable'
0x180029535  mov     [rbx], rax
0x180029538  test    rbx, rbx
0x18002953b  jz      short loc_180029564
0x18002953d  mov     rax, [rax]
0x180029540  mov     r8, rdi
0x180029543  mov     [rbx+10h], ecx
0x180029546  mov     rdx, rsi
0x180029549  mov     rcx, rbx
0x18002954c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029551  mov     rdx, [rbx]
0x180029554  mov     edi, eax
0x180029556  mov     rcx, rbx
0x180029559  mov     rax, [rdx+10h]
0x18002955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029562  jmp     short loc_180029569
0x180029564  mov     edi, 8007000Eh
0x180029569  mov     rbx, [rsp+28h+arg_0]
0x18002956e  mov     eax, edi
0x180029570  mov     rsi, [rsp+28h+arg_8]
0x180029575  add     rsp, 20h
0x180029579  pop     rdi
0x18002957a  retn
```
