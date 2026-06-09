# Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>(void)

- ea: `0x180022714`
- end: `0x18002277e`
- name: `??1?$Object@UIStream@@UNullType@Private@Com@@@Com@@UEAA@XZ`
- size: `106`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022800`
- `0x180022840`
- `0x180022a84`
- `0x180023ed0`

## callees

- `0x180022714`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>(__int64 a1)
{
  __int64 result; // rax
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)a1 = &Com::Object<IStream,Com::Private::NullType>::`vftable';
  result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 24LL))(*(_QWORD *)(a1 + 8));
  v3 = *(volatile signed __int32 **)(a1 + 16);
  if ( v3 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      result = (unsigned int)_InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180022714  push    rbx
0x180022716  sub     rsp, 20h
0x18002271a  mov     rbx, rcx
0x18002271d  lea     rax, ??_7?$Object@UIStream@@UNullType@Private@Com@@@Com@@6B@; const Com::Object<IStream,Com::Private::NullType>::`vftable'
0x180022724  mov     [rcx], rax
0x180022727  mov     rcx, [rcx+8]
0x18002272b  mov     rax, [rcx]
0x18002272e  mov     rax, [rax+18h]
0x180022732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022737  mov     rbx, [rbx+10h]
0x18002273b  test    rbx, rbx
0x18002273e  jz      short loc_180022778
0x180022740  or      eax, 0FFFFFFFFh
0x180022743  lock xadd [rbx+8], eax
0x180022748  cmp     eax, 1
0x18002274b  jnz     short loc_180022778
0x18002274d  mov     rax, [rbx]
0x180022750  mov     rcx, rbx
0x180022753  mov     rax, [rax]
0x180022756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275b  or      eax, 0FFFFFFFFh
0x18002275e  lock xadd [rbx+0Ch], eax
0x180022763  cmp     eax, 1
0x180022766  jnz     short loc_180022778
0x180022768  mov     rax, [rbx]
0x18002276b  mov     rcx, rbx
0x18002276e  mov     rax, [rax+8]
0x180022772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022777  nop
0x180022778  add     rsp, 20h
0x18002277c  pop     rbx
0x18002277d  retn
```
