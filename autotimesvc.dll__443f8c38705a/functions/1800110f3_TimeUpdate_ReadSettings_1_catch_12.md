# _TimeUpdate::ReadSettings_::_1_::catch$12

- ea: `0x1800110f3`
- end: `0x18001117f`
- name: `_TimeUpdate::ReadSettings_::_1_::catch$12`
- size: `140`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180005a74`
- `0x180006ec4`
- `0x180007e04`
- `0x1800110f3`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ReadSettings_::_1_::catch_12(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  __int64 Settings; // rax
  volatile signed __int32 *v6; // rbx

  wil::details::in1diag3::Log_CaughtException(*(wil::details::in1diag3 **)(a2 + 232), (void *)a2, a3, a4);
  Settings = TimeUpdate::GetSettings(*(_QWORD *)(a2 + 96), a2 + 128);
  std::shared_ptr<Settings>::operator=(*(_QWORD *)(a2 + 104), Settings);
  v6 = *(volatile signed __int32 **)(a2 + 136);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800110f3  mov     [rsp+arg_8], rdx
0x1800110f8  push    rbx
0x1800110f9  push    rbp
0x1800110fa  sub     rsp, 48h
0x1800110fe  mov     rbp, rdx
0x180011101  mov     rcx, [rbp+0E8h]; this
0x180011108  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18001110d  lea     rdx, [rbp+80h]
0x180011114  mov     rcx, [rbp+60h]
0x180011118  call    ?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ; TimeUpdate::GetSettings(void)
0x18001111d  mov     rdx, rax
0x180011120  mov     rcx, [rbp+68h]
0x180011124  call    ??4?$shared_ptr@VSettings@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Settings>::operator=(std::shared_ptr<Settings> &&)
0x180011129  mov     rbx, [rbp+88h]
0x180011130  test    rbx, rbx
0x180011133  jz      short loc_18001116D
0x180011135  or      eax, 0FFFFFFFFh
0x180011138  lock xadd [rbx+8], eax
0x18001113d  cmp     eax, 1
0x180011140  jnz     short loc_18001116D
0x180011142  mov     rax, [rbx]
0x180011145  mov     rcx, rbx
0x180011148  mov     rax, [rax]
0x18001114b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011150  or      eax, 0FFFFFFFFh
0x180011153  lock xadd [rbx+0Ch], eax
0x180011158  cmp     eax, 1
0x18001115b  jnz     short loc_18001116D
0x18001115d  mov     rax, [rbx]
0x180011160  mov     rcx, rbx
0x180011163  mov     rax, [rax+8]
0x180011167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001116c  nop
0x18001116d  mov     rax, 0
0x180011177  add     rsp, 48h
0x18001117b  pop     rbp
0x18001117c  pop     rbx
0x18001117d  retn
```
