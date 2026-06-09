# CWinTaskClassFactoryT<PerformanceTraceHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000b9a0`
- end: `0x18000ba9f`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VPerformanceTraceHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000300c`
- `0x18000b9a0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<PerformanceTraceHandler,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rbx
  __int64 (__fastcall **v8)(void *, __int64, _QWORD *); // rax

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0xC8u);
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &PerformanceTraceHandler::`vftable';
      v7[7] = 0;
      v7[8] = 0;
      v7[9] = 0;
      v7[10] = 0;
      v7[11] = 0;
      v7[12] = 0;
      v7[13] = 0;
      v7[14] = 0;
      v7[15] = 0;
      v7[16] = 0;
      v7[17] = 0;
      v7[18] = 0;
      v7[19] = 0;
      v7[20] = 0;
      v7[21] = 0;
      v7[24] = 0;
      v8 = (__int64 (__fastcall **)(void *, __int64, _QWORD *))*v7;
      *((_DWORD *)v7 + 4) = 1;
      v6 = (*v8)(v7, a3, a4);
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
0x18000b9a0  push    rbx
0x18000b9a2  push    rbp
0x18000b9a3  push    rsi
0x18000b9a4  push    rdi
0x18000b9a5  sub     rsp, 28h
0x18000b9a9  xor     ebp, ebp
0x18000b9ab  mov     rdi, r9
0x18000b9ae  mov     rsi, r8
0x18000b9b1  test    r9, r9
0x18000b9b4  jnz     short loc_18000B9C0
0x18000b9b6  mov     edi, 80070057h
0x18000b9bb  jmp     loc_18000BA94
0x18000b9c0  mov     [r9], rbp
0x18000b9c3  test    rdx, rdx
0x18000b9c6  jz      short loc_18000B9D2
0x18000b9c8  mov     edi, 80040110h
0x18000b9cd  jmp     loc_18000BA94
0x18000b9d2  mov     ecx, 0C8h; Size
0x18000b9d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b9dc  mov     ecx, 1
0x18000b9e1  mov     [rsp+48h+arg_18], rax
0x18000b9e6  mov     rbx, rax
0x18000b9e9  mov     [rax+8], rbp
0x18000b9ed  mov     [rax+10h], ebp
0x18000b9f0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000b9f8  mov     [rax+20h], ecx
0x18000b9fb  mov     [rax+24h], ebp
0x18000b9fe  mov     [rax+28h], rbp
0x18000ba02  mov     [rax+30h], rbp
0x18000ba06  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000ba0d  lea     rax, ??_7PerformanceTraceHandler@@6B@; const PerformanceTraceHandler::`vftable'
0x18000ba14  mov     r8, rdi
0x18000ba17  mov     [rbx], rax
0x18000ba1a  mov     rdx, rsi
0x18000ba1d  mov     [rbx+38h], rbp
0x18000ba21  mov     [rbx+40h], rbp
0x18000ba25  mov     [rbx+48h], rbp
0x18000ba29  mov     [rbx+50h], rbp
0x18000ba2d  mov     [rbx+58h], rbp
0x18000ba31  mov     [rbx+60h], rbp
0x18000ba35  mov     [rbx+68h], rbp
0x18000ba39  mov     [rbx+70h], rbp
0x18000ba3d  mov     [rbx+78h], rbp
0x18000ba41  mov     [rbx+80h], rbp
0x18000ba48  mov     [rbx+88h], rbp
0x18000ba4f  mov     [rbx+90h], rbp
0x18000ba56  mov     [rbx+98h], rbp
0x18000ba5d  mov     [rbx+0A0h], rbp
0x18000ba64  mov     [rbx+0A8h], rbp
0x18000ba6b  mov     [rbx+0C0h], rbp
0x18000ba72  mov     rax, [rbx]
0x18000ba75  mov     [rbx+10h], ecx
0x18000ba78  mov     rcx, rbx
0x18000ba7b  mov     rax, [rax]
0x18000ba7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba83  mov     edi, eax
0x18000ba85  mov     rcx, [rbx]
0x18000ba88  mov     rax, [rcx+10h]
0x18000ba8c  mov     rcx, rbx
0x18000ba8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba94  mov     eax, edi
0x18000ba96  add     rsp, 28h
0x18000ba9a  pop     rdi
0x18000ba9b  pop     rsi
0x18000ba9c  pop     rbp
0x18000ba9d  pop     rbx
0x18000ba9e  retn
```
