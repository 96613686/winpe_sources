# std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)

- ea: `0x180007d68`
- end: `0x180007de6`
- name: `??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z`
- size: `126`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008368`
- `0x1800084d0`
- `0x1800085e4`
- `0x1800089dc`
- `0x18000a6e0`
- `0x18000a838`
- `0x18000a9f0`
- `0x18000adac`
- `0x18000c6ec`
- `0x18000c8dc`
- `0x18000ca0c`
- `0x18000d424`

## callees

- `0x180007d68`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(_QWORD *a1, __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  volatile signed __int32 *v5; // rbx

  *a1 = 0;
  a1[1] = 0;
  v3 = a2[1];
  v4 = *a2;
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v5 = (volatile signed __int32 *)a1[1];
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  a1[1] = v3;
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x180007d68  push    rbx
0x180007d6a  push    rbp
0x180007d6b  push    rsi
0x180007d6c  push    rdi
0x180007d6d  sub     rsp, 28h
0x180007d71  mov     rdi, rcx
0x180007d74  mov     qword ptr [rcx], 0
0x180007d7b  mov     qword ptr [rcx+8], 0
0x180007d83  mov     rsi, [rdx+8]
0x180007d87  mov     rbp, [rdx]
0x180007d8a  test    rsi, rsi
0x180007d8d  jz      short loc_180007D93
0x180007d8f  lock inc dword ptr [rsi+8]
0x180007d93  mov     rbx, [rcx+8]
0x180007d97  test    rbx, rbx
0x180007d9a  jz      short loc_180007DD3
0x180007d9c  or      eax, 0FFFFFFFFh
0x180007d9f  lock xadd [rbx+8], eax
0x180007da4  cmp     eax, 1
0x180007da7  jnz     short loc_180007DD3
0x180007da9  mov     rax, [rbx]
0x180007dac  mov     rcx, rbx
0x180007daf  mov     rax, [rax]
0x180007db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db7  or      eax, 0FFFFFFFFh
0x180007dba  lock xadd [rbx+0Ch], eax
0x180007dbf  cmp     eax, 1
0x180007dc2  jnz     short loc_180007DD3
0x180007dc4  mov     rax, [rbx]
0x180007dc7  mov     rcx, rbx
0x180007dca  mov     rax, [rax+8]
0x180007dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd3  mov     [rdi+8], rsi
0x180007dd7  mov     [rdi], rbp
0x180007dda  mov     rax, rdi
0x180007ddd  add     rsp, 28h
0x180007de1  pop     rdi
0x180007de2  pop     rsi
0x180007de3  pop     rbp
0x180007de4  pop     rbx
0x180007de5  retn
```
