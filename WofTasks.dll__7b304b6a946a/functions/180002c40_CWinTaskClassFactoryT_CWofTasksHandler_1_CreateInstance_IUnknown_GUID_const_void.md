# CWinTaskClassFactoryT<CWofTasksHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002c40`
- end: `0x180002d11`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x180002c40`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CWofTasksHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi

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
        *((_DWORD *)v7 + 8) = 1;
        *((_DWORD *)v7 + 9) = 0;
        v7[5] = 0;
        v7[6] = 0;
        _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
        *v7 = &CWofTasksHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CWofTasksHandler::`vftable')(v7, a3, a4);
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
0x180002c40  mov     [rsp+arg_0], rbx
0x180002c45  mov     [rsp+arg_8], rsi
0x180002c4a  push    rdi
0x180002c4b  sub     rsp, 20h
0x180002c4f  mov     rbx, r9
0x180002c52  mov     rsi, r8
0x180002c55  test    r9, r9
0x180002c58  jnz     short loc_180002C64
0x180002c5a  mov     ebx, 80070057h
0x180002c5f  jmp     loc_180002CFF
0x180002c64  mov     qword ptr [r9], 0
0x180002c6b  test    rdx, rdx
0x180002c6e  jz      short loc_180002C7A
0x180002c70  mov     ebx, 80040110h
0x180002c75  jmp     loc_180002CFF
0x180002c7a  mov     ecx, 38h ; '8'; Size
0x180002c7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c84  mov     rdi, rax
0x180002c87  test    rax, rax
0x180002c8a  jz      short loc_180002CFA
0x180002c8c  mov     qword ptr [rax+8], 0
0x180002c94  mov     ecx, 1
0x180002c99  mov     dword ptr [rax+10h], 0
0x180002ca0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180002ca8  mov     [rax+20h], ecx
0x180002cab  mov     dword ptr [rax+24h], 0
0x180002cb2  mov     qword ptr [rax+28h], 0
0x180002cba  mov     qword ptr [rax+30h], 0
0x180002cc2  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180002cc9  lea     rax, ??_7CWofTasksHandler@@6B@; const CWofTasksHandler::`vftable'
0x180002cd0  mov     r8, rbx
0x180002cd3  mov     [rdi], rax
0x180002cd6  mov     rdx, rsi
0x180002cd9  mov     rax, [rax]
0x180002cdc  mov     [rdi+10h], ecx
0x180002cdf  mov     rcx, rdi
0x180002ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce7  mov     ebx, eax
0x180002ce9  mov     rcx, [rdi]
0x180002cec  mov     rax, [rcx+10h]
0x180002cf0  mov     rcx, rdi
0x180002cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf8  jmp     short loc_180002CFF
0x180002cfa  mov     ebx, 8007000Eh
0x180002cff  mov     rsi, [rsp+28h+arg_8]
0x180002d04  mov     eax, ebx
0x180002d06  mov     rbx, [rsp+28h+arg_0]
0x180002d0b  add     rsp, 20h
0x180002d0f  pop     rdi
0x180002d10  retn
```
