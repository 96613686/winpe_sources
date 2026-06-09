# CWinTaskClassFactoryT<WhesvcUXHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000bb90`
- end: `0x18000bc5e`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VWhesvcUXHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000300c`
- `0x18000bb90`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<WhesvcUXHandler,1>::CreateInstance(
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
      *v7 = &WhesvcUXHandler::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))WhesvcUXHandler::`vftable')(v7, a3, a4);
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
0x18000bb90  mov     [rsp+arg_0], rbx
0x18000bb95  mov     [rsp+arg_8], rsi
0x18000bb9a  push    rdi
0x18000bb9b  sub     rsp, 20h
0x18000bb9f  mov     rdi, r9
0x18000bba2  mov     rsi, r8
0x18000bba5  test    r9, r9
0x18000bba8  jnz     short loc_18000BBB4
0x18000bbaa  mov     edi, 80070057h
0x18000bbaf  jmp     loc_18000BC4C
0x18000bbb4  mov     qword ptr [r9], 0
0x18000bbbb  test    rdx, rdx
0x18000bbbe  jz      short loc_18000BBCA
0x18000bbc0  mov     edi, 80040110h
0x18000bbc5  jmp     loc_18000BC4C
0x18000bbca  mov     ecx, 38h ; '8'; Size
0x18000bbcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bbd4  mov     ecx, 1
0x18000bbd9  mov     [rsp+28h+arg_18], rax
0x18000bbde  mov     rbx, rax
0x18000bbe1  mov     qword ptr [rax+8], 0
0x18000bbe9  mov     dword ptr [rax+10h], 0
0x18000bbf0  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000bbf8  mov     [rax+20h], ecx
0x18000bbfb  mov     dword ptr [rax+24h], 0
0x18000bc02  mov     qword ptr [rax+28h], 0
0x18000bc0a  mov     qword ptr [rax+30h], 0
0x18000bc12  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000bc19  lea     rax, ??_7WhesvcUXHandler@@6B@; const WhesvcUXHandler::`vftable'
0x18000bc20  mov     r8, rdi
0x18000bc23  mov     [rbx], rax
0x18000bc26  mov     rdx, rsi
0x18000bc29  mov     [rbx+10h], ecx
0x18000bc2c  mov     rcx, rbx
0x18000bc2f  mov     rax, cs:??_7WhesvcUXHandler@@6B@; const WhesvcUXHandler::`vftable'
0x18000bc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc3b  mov     edi, eax
0x18000bc3d  mov     rcx, [rbx]
0x18000bc40  mov     rax, [rcx+10h]
0x18000bc44  mov     rcx, rbx
0x18000bc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4c  mov     rbx, [rsp+28h+arg_0]
0x18000bc51  mov     eax, edi
0x18000bc53  mov     rsi, [rsp+28h+arg_8]
0x18000bc58  add     rsp, 20h
0x18000bc5c  pop     rdi
0x18000bc5d  retn
```
