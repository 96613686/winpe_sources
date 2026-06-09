# CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800022e0`
- end: `0x1800023bb`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCTimeSyncTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001028`
- `0x1800022e0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CTimeSyncTaskHandler,1>::CreateInstance(
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
        *v7 = &CTimeSyncTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CTimeSyncTaskHandler::`vftable')(v7, a3, a4);
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
0x1800022e0  mov     [rsp+arg_0], rbx
0x1800022e5  mov     [rsp+arg_8], rsi
0x1800022ea  push    rdi
0x1800022eb  sub     rsp, 20h
0x1800022ef  mov     rdi, r9
0x1800022f2  mov     rsi, r8
0x1800022f5  test    r9, r9
0x1800022f8  jnz     short loc_180002304
0x1800022fa  mov     edi, 80070057h
0x1800022ff  jmp     loc_1800023A9
0x180002304  mov     qword ptr [r9], 0
0x18000230b  test    rdx, rdx
0x18000230e  jz      short loc_18000231A
0x180002310  mov     edi, 80040110h
0x180002315  jmp     loc_1800023A9
0x18000231a  mov     ecx, 38h ; '8'; Size
0x18000231f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002324  mov     [rsp+28h+arg_18], rax
0x180002329  mov     rbx, rax
0x18000232c  test    rax, rax
0x18000232f  jz      short loc_1800023A4
0x180002331  mov     qword ptr [rax+8], 0
0x180002339  mov     ecx, 1
0x18000233e  mov     dword ptr [rax+10h], 0
0x180002345  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000234d  mov     [rax+20h], ecx
0x180002350  mov     dword ptr [rax+24h], 0
0x180002357  mov     qword ptr [rax+28h], 0
0x18000235f  mov     qword ptr [rax+30h], 0
0x180002367  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000236e  lea     rax, ??_7CTimeSyncTaskHandler@@6B@; const CTimeSyncTaskHandler::`vftable'
0x180002375  mov     [rbx], rax
0x180002378  test    rbx, rbx
0x18000237b  jz      short loc_1800023A4
0x18000237d  mov     rax, [rax]
0x180002380  mov     r8, rdi
0x180002383  mov     [rbx+10h], ecx
0x180002386  mov     rdx, rsi
0x180002389  mov     rcx, rbx
0x18000238c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002391  mov     rdx, [rbx]
0x180002394  mov     edi, eax
0x180002396  mov     rcx, rbx
0x180002399  mov     rax, [rdx+10h]
0x18000239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a2  jmp     short loc_1800023A9
0x1800023a4  mov     edi, 8007000Eh
0x1800023a9  mov     rbx, [rsp+28h+arg_0]
0x1800023ae  mov     eax, edi
0x1800023b0  mov     rsi, [rsp+28h+arg_8]
0x1800023b5  add     rsp, 20h
0x1800023b9  pop     rdi
0x1800023ba  retn
```
