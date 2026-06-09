# Pal::Task::run(void)

- ea: `0x18001c1cc`
- end: `0x18001c289`
- name: `?run@Task@Pal@@QEAAXXZ`
- size: `189`
- prototype: `void __fastcall(Pal::Task *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012fa0`
- `0x180016e84`
- `0x18003afb0`

## callees

- `0x180012438`
- `0x180014cd8`
- `0x1800188f0`
- `0x18001c1cc`
- `0x18001c6f0`
- `0x180043010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c227`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c227`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c1e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c282`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Pal::Task::run(Pal::Task *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( *((_BYTE *)this + 400) )
    goto LABEL_8;
  if ( *((_QWORD *)this + 41) )
  {
    std::_Func_class<void,>::operator()((char *)this + 272, v3);
    std::_Func_class<void,>::_Tidy((char *)this + 272);
LABEL_8:
    if ( !*((_BYTE *)this + 225) )
      *((_BYTE *)this + 225) = 1;
    Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(this, 1);
    goto LABEL_11;
  }
  v4 = *((_QWORD *)this + 49);
  if ( !v4 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 16LL))(v4, (char *)this + 401);
  if ( !(unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 401) )
  {
    std::_Func_class<void,>::_Tidy((char *)this + 336);
    goto LABEL_8;
  }
LABEL_11:
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x18001c1cc  push    rbx
0x18001c1ce  push    rbp
0x18001c1cf  push    rsi
0x18001c1d0  push    rdi
0x18001c1d1  sub     rsp, 28h
0x18001c1d5  mov     rdi, rcx
0x18001c1d8  lea     rsi, [rcx+0E8h]
0x18001c1df  mov     [rsp+48h+arg_0], rsi
0x18001c1e4  mov     rcx, rsi; lpCriticalSection
0x18001c1e7  call    cs:__imp_EnterCriticalSection
0x18001c1ed  nop
0x18001c1ee  cmp     byte ptr [rdi+190h], 0
0x18001c1f5  jnz     short loc_18001C258
0x18001c1f7  lea     rbx, [rdi+110h]
0x18001c1fe  cmp     qword ptr [rbx+38h], 0
0x18001c203  jz      short loc_18001C217
0x18001c205  mov     rcx, rbx
0x18001c208  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18001c20d  mov     rcx, rbx
0x18001c210  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001c215  jmp     short loc_18001C258
0x18001c217  lea     rbp, [rdi+150h]
0x18001c21e  mov     rcx, [rbp+38h]
0x18001c222  test    rcx, rcx
0x18001c225  jnz     short loc_18001C22E
0x18001c227  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001c22d  int     3; Trap to Debugger
0x18001c22e  lea     rbx, [rdi+191h]
0x18001c235  mov     rax, [rcx]
0x18001c238  mov     rdx, rbx
0x18001c23b  mov     rax, [rax+10h]
0x18001c23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c244  mov     rcx, rbx
0x18001c247  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18001c24c  test    al, al
0x18001c24e  jnz     short loc_18001C277
0x18001c250  mov     rcx, rbp
0x18001c253  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001c258  cmp     byte ptr [rdi+0E1h], 0
0x18001c25f  jnz     short loc_18001C268
0x18001c261  mov     byte ptr [rdi+0E1h], 1
0x18001c268  mov     edx, cs:dword_180048CD0
0x18001c26e  mov     rcx, rdi
0x18001c271  call    ?setSucceededOrFailedInternal@UntypedAsyncOperation@Pal@@AEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setSucceededOrFailedInternal(Core::StatusCode)
0x18001c276  nop
0x18001c277  mov     rcx, rsi
0x18001c27a  add     rsp, 28h
0x18001c27e  pop     rdi
0x18001c27f  pop     rsi
0x18001c280  pop     rbp
0x18001c281  pop     rbx
0x18001c282  jmp     cs:__imp_LeaveCriticalSection
```
