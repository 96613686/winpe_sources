# CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000bab0`
- end: `0x18000bb7e`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VShowFeedbackToastHandler@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000300c`
- `0x18000bab0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::CreateInstance(
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
      *v7 = &ShowFeedbackToastHandler::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))ShowFeedbackToastHandler::`vftable')(v7, a3, a4);
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
0x18000bab0  mov     [rsp+arg_0], rbx
0x18000bab5  mov     [rsp+arg_8], rsi
0x18000baba  push    rdi
0x18000babb  sub     rsp, 20h
0x18000babf  mov     rdi, r9
0x18000bac2  mov     rsi, r8
0x18000bac5  test    r9, r9
0x18000bac8  jnz     short loc_18000BAD4
0x18000baca  mov     edi, 80070057h
0x18000bacf  jmp     loc_18000BB6C
0x18000bad4  mov     qword ptr [r9], 0
0x18000badb  test    rdx, rdx
0x18000bade  jz      short loc_18000BAEA
0x18000bae0  mov     edi, 80040110h
0x18000bae5  jmp     loc_18000BB6C
0x18000baea  mov     ecx, 38h ; '8'; Size
0x18000baef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000baf4  mov     ecx, 1
0x18000baf9  mov     [rsp+28h+arg_18], rax
0x18000bafe  mov     rbx, rax
0x18000bb01  mov     qword ptr [rax+8], 0
0x18000bb09  mov     dword ptr [rax+10h], 0
0x18000bb10  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18000bb18  mov     [rax+20h], ecx
0x18000bb1b  mov     dword ptr [rax+24h], 0
0x18000bb22  mov     qword ptr [rax+28h], 0
0x18000bb2a  mov     qword ptr [rax+30h], 0
0x18000bb32  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x18000bb39  lea     rax, ??_7ShowFeedbackToastHandler@@6B@; const ShowFeedbackToastHandler::`vftable'
0x18000bb40  mov     r8, rdi
0x18000bb43  mov     [rbx], rax
0x18000bb46  mov     rdx, rsi
0x18000bb49  mov     [rbx+10h], ecx
0x18000bb4c  mov     rcx, rbx
0x18000bb4f  mov     rax, cs:??_7ShowFeedbackToastHandler@@6B@; const ShowFeedbackToastHandler::`vftable'
0x18000bb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5b  mov     edi, eax
0x18000bb5d  mov     rcx, [rbx]
0x18000bb60  mov     rax, [rcx+10h]
0x18000bb64  mov     rcx, rbx
0x18000bb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb6c  mov     rbx, [rsp+28h+arg_0]
0x18000bb71  mov     eax, edi
0x18000bb73  mov     rsi, [rsp+28h+arg_8]
0x18000bb78  add     rsp, 20h
0x18000bb7c  pop     rdi
0x18000bb7d  retn
```
