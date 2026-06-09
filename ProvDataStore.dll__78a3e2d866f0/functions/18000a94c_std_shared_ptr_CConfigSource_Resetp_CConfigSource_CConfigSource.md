# std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(CConfigSource *)

- ea: `0x18000a94c`
- end: `0x18000a9e8`
- name: `??$_Resetp@VCConfigSource@@@?$shared_ptr@VCConfigSource@@@std@@AEAAXPEAVCConfigSource@@@Z`
- size: `156`
- prototype: `unsigned __int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b31c`
- `0x18000b6d8`

## callees

- `0x1800018f4`
- `0x18000a94c`
- `0x180012010`

## pseudocode

```c
unsigned __int64 __fastcall std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(_QWORD *a1)
{
  unsigned __int64 result; // rax
  _QWORD *v3; // rbx
  volatile signed __int32 *v4; // rdi

  try
  {
    result = (unsigned __int64)operator new(0x18u);
    v3 = (_QWORD *)result;
    if ( result )
    {
      *(_DWORD *)(result + 8) = 1;
      *(_DWORD *)(result + 12) = 1;
      result = (unsigned __int64)&std::_Ref_count<CConfigSource>::`vftable';
      *v3 = &std::_Ref_count<CConfigSource>::`vftable';
      v3[2] = 0;
    }
    v4 = (volatile signed __int32 *)a1[1];
    if ( v4 )
    {
      result = (unsigned int)_InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        result = (unsigned int)_InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    a1[1] = v3;
    *a1 = 0;
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000a94c  mov     [rsp+arg_0], rbx
0x18000a951  mov     [rsp+arg_10], rsi
0x18000a956  push    rdi
0x18000a957  sub     rsp, 20h
0x18000a95b  mov     rsi, rcx
0x18000a95e  mov     ecx, 18h; Size
0x18000a963  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a968  mov     rbx, rax
0x18000a96b  test    rbx, rbx
0x18000a96e  jz      short loc_18000A98D
0x18000a970  mov     eax, 1
0x18000a975  mov     [rbx+8], eax
0x18000a978  mov     [rbx+0Ch], eax
0x18000a97b  lea     rax, ??_7?$_Ref_count@VCConfigSource@@@std@@6B@; const std::_Ref_count<CConfigSource>::`vftable'
0x18000a982  mov     [rbx], rax
0x18000a985  mov     qword ptr [rbx+10h], 0
0x18000a98d  mov     rdi, [rsi+8]
0x18000a991  test    rdi, rdi
0x18000a994  jz      short loc_18000A9CD
0x18000a996  or      eax, 0FFFFFFFFh
0x18000a999  lock xadd [rdi+8], eax
0x18000a99e  cmp     eax, 1
0x18000a9a1  jnz     short loc_18000A9CD
0x18000a9a3  mov     rax, [rdi]
0x18000a9a6  mov     rcx, rdi
0x18000a9a9  mov     rax, [rax]
0x18000a9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9b1  or      eax, 0FFFFFFFFh
0x18000a9b4  lock xadd [rdi+0Ch], eax
0x18000a9b9  cmp     eax, 1
0x18000a9bc  jnz     short loc_18000A9CD
0x18000a9be  mov     rax, [rdi]
0x18000a9c1  mov     rcx, rdi
0x18000a9c4  mov     rax, [rax+8]
0x18000a9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9cd  mov     [rsi+8], rbx
0x18000a9d1  mov     qword ptr [rsi], 0
0x18000a9d8  mov     rbx, [rsp+28h+arg_0]
0x18000a9dd  mov     rsi, [rsp+28h+arg_10]
0x18000a9e2  add     rsp, 20h
0x18000a9e6  pop     rdi
0x18000a9e7  retn
```
