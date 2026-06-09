# std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::~_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>(void)

- ea: `0x18005708c`
- end: `0x1800570df`
- name: `??1?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@UEAA@XZ`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800575e0`

## callees

- `0x180029298`
- `0x18005708c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800570c5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800570c5`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800570b5`
- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x1800570b5`

## pseudocode

```c
__int64 __fastcall std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::~_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>(
        __int64 a1)
{
  bool v1; // zf

  v1 = *(_BYTE *)(a1 + 201) == 0;
  *(_QWORD *)a1 = &std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>>::`vftable';
  if ( !v1 && !*(_DWORD *)(a1 + 196) )
    _Cnd_unregister_at_thread_exit((_Mtx_t)(a1 + 40));
  __ExceptionPtrDestroy((void *)(a1 + 24));
  return std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>::~unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&long WinBioFree(void *)>>(a1 + 16);
}

```

## disassembly

```asm
0x18005708c  push    rbx
0x18005708e  sub     rsp, 20h
0x180057092  cmp     byte ptr [rcx+0C9h], 0
0x180057099  lea     rax, ??_7?$_Associated_state@V?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@@std@@6B@; const std::_Associated_state<std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>>::`vftable'
0x1800570a0  mov     [rcx], rax
0x1800570a3  mov     rbx, rcx
0x1800570a6  jz      short loc_1800570C1
0x1800570a8  cmp     dword ptr [rcx+0C4h], 0
0x1800570af  jnz     short loc_1800570C1
0x1800570b1  add     rcx, 28h ; '('; _Mtx_t
0x1800570b5  call    cs:__imp__Cnd_unregister_at_thread_exit
0x1800570bc  nop     dword ptr [rax+rax+00h]
0x1800570c1  lea     rcx, [rbx+18h]
0x1800570c5  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800570cc  nop     dword ptr [rax+rax+00h]
0x1800570d1  lea     rcx, [rbx+10h]
0x1800570d5  add     rsp, 20h
0x1800570d9  pop     rbx
0x1800570da  jmp     ??1?$unique_ptr@U_WINBIO_ASYNC_RESULT@@U?$function_deleter@P6AJPEAX@Z$1?WinBioFree@@YAJ0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>::~unique_ptr<_WINBIO_ASYNC_RESULT,wil::function_deleter<long (*)(void *),&WinBioFree(void *)>>(void)
```
