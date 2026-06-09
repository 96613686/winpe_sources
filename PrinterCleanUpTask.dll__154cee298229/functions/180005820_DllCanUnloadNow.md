# DllCanUnloadNow

- ea: `0x180005820`
- end: `0x18000585a`
- name: `DllCanUnloadNow`
- size: `58`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ad4`
- `0x180005820`
- `0x180018010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax
  __int64 v1; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (*(unsigned int (__fastcall **)(__int64 *))(*v0 + 24))(v0) )
    LODWORD(v1) = 1;
  else
    return _InterlockedCompareExchange(&CWinTaskHandler::s_cInstances, 0, 0) != 0;
  return v1;
}

```

## disassembly

```asm
0x180005820  sub     rsp, 28h
0x180005824  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180005829  mov     rdx, rax
0x18000582c  mov     rcx, [rax]
0x18000582f  mov     rax, [rcx+18h]
0x180005833  mov     rcx, rdx
0x180005836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000583b  test    eax, eax
0x18000583d  jnz     short loc_180005850
0x18000583f  xor     ecx, ecx
0x180005841  lock cmpxchg cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x180005849  mov     eax, ecx
0x18000584b  setnz   al
0x18000584e  jmp     short loc_180005855
0x180005850  mov     eax, 1
0x180005855  add     rsp, 28h
0x180005859  retn
```
