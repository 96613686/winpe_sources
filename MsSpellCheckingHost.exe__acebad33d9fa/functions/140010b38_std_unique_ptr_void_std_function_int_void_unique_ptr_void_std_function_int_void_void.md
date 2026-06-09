# std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)

- ea: `0x140010b38`
- end: `0x140010b9b`
- name: `??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ`
- size: `99`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140010d08`
- `0x140012555`
- `0x140012567`

## callees

- `0x140001780`
- `0x140010b38`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(
        __int64 *a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  result = *a1;
  if ( *a1 )
  {
    v7 = *a1;
    v4 = a1[4];
    if ( !v4 )
      std::_Xbad_function_call();
    result = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 16LL))(v4, &v7);
  }
  v5 = a1 + 1;
  v6 = (_QWORD *)v5[3];
  if ( v6 )
  {
    LOBYTE(a2) = v6 != v5;
    result = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v6 + 32LL))(v6, a2);
    v5[3] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140010b38  push    rbx
0x140010b3a  sub     rsp, 20h
0x140010b3e  mov     rbx, rcx
0x140010b41  mov     rax, [rcx]
0x140010b44  test    rax, rax
0x140010b47  jz      short loc_140010B68
0x140010b49  mov     [rsp+28h+arg_0], rax
0x140010b4e  mov     rcx, [rcx+20h]
0x140010b52  test    rcx, rcx
0x140010b55  jz      short loc_140010B95
0x140010b57  mov     rax, [rcx]
0x140010b5a  lea     rdx, [rsp+28h+arg_0]
0x140010b5f  mov     rax, [rax+10h]
0x140010b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b68  add     rbx, 8
0x140010b6c  mov     rcx, [rbx+18h]
0x140010b70  test    rcx, rcx
0x140010b73  jz      short loc_140010B8F
0x140010b75  mov     rax, [rcx]
0x140010b78  cmp     rcx, rbx
0x140010b7b  setnz   dl
0x140010b7e  mov     rax, [rax+20h]
0x140010b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b87  mov     qword ptr [rbx+18h], 0
0x140010b8f  add     rsp, 20h
0x140010b93  pop     rbx
0x140010b94  retn
0x140010b95  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
