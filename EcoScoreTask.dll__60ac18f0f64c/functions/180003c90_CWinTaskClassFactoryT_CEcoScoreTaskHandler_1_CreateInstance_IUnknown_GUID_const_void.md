# CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003c90`
- end: `0x180003d61`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001a64`
- `0x180003c90`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::CreateInstance(
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
        *v7 = &CEcoScoreTaskHandler::`vftable';
        *((_DWORD *)v7 + 4) = 1;
        v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CEcoScoreTaskHandler::`vftable')(v7, a3, a4);
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
0x180003c90  mov     [rsp+arg_0], rbx
0x180003c95  mov     [rsp+arg_8], rsi
0x180003c9a  push    rdi
0x180003c9b  sub     rsp, 20h
0x180003c9f  mov     rbx, r9
0x180003ca2  mov     rsi, r8
0x180003ca5  test    r9, r9
0x180003ca8  jnz     short loc_180003CB4
0x180003caa  mov     ebx, 80070057h
0x180003caf  jmp     loc_180003D4F
0x180003cb4  mov     qword ptr [r9], 0
0x180003cbb  test    rdx, rdx
0x180003cbe  jz      short loc_180003CCA
0x180003cc0  mov     ebx, 80040110h
0x180003cc5  jmp     loc_180003D4F
0x180003cca  mov     ecx, 38h ; '8'; Size
0x180003ccf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003cd4  mov     rdi, rax
0x180003cd7  test    rax, rax
0x180003cda  jz      short loc_180003D4A
0x180003cdc  mov     qword ptr [rax+8], 0
0x180003ce4  mov     ecx, 1
0x180003ce9  mov     dword ptr [rax+10h], 0
0x180003cf0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003cf8  mov     [rax+20h], ecx
0x180003cfb  mov     dword ptr [rax+24h], 0
0x180003d02  mov     qword ptr [rax+28h], 0
0x180003d0a  mov     qword ptr [rax+30h], 0
0x180003d12  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180003d19  lea     rax, ??_7CEcoScoreTaskHandler@@6B@; const CEcoScoreTaskHandler::`vftable'
0x180003d20  mov     r8, rbx
0x180003d23  mov     [rdi], rax
0x180003d26  mov     rdx, rsi
0x180003d29  mov     rax, [rax]
0x180003d2c  mov     [rdi+10h], ecx
0x180003d2f  mov     rcx, rdi
0x180003d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d37  mov     ebx, eax
0x180003d39  mov     rcx, [rdi]
0x180003d3c  mov     rax, [rcx+10h]
0x180003d40  mov     rcx, rdi
0x180003d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d48  jmp     short loc_180003D4F
0x180003d4a  mov     ebx, 8007000Eh
0x180003d4f  mov     rsi, [rsp+28h+arg_8]
0x180003d54  mov     eax, ebx
0x180003d56  mov     rbx, [rsp+28h+arg_0]
0x180003d5b  add     rsp, 20h
0x180003d5f  pop     rdi
0x180003d60  retn
```
