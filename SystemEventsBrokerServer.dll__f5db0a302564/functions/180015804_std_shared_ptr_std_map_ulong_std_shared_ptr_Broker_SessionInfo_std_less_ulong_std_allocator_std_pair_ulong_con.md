# std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>::~shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>>(void)

- ea: `0x180015804`
- end: `0x180015850`
- name: `??1?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@QEAA@XZ`
- size: `76`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800225c0`
- `0x1800225e4`
- `0x1800226d2`
- `0x180022760`
- `0x180022790`
- `0x180022b95`
- `0x180022d20`
- `0x180023160`
- `0x180023180`
- `0x180023200`
- `0x180023310`
- `0x1800234b0`
- `0x180023720`
- `0x180023740`
- `0x180023b20`
- `0x180023d90`
- `0x180023dd0`
- `0x180023f80`
- `0x1800242b0`
- `0x180024360`
- `0x1800243c0`
- `0x180024e57`
- `0x180024e80`
- `0x18002532a`
- `0x180025816`
- `0x180025d2c`
- `0x18002603f`

## callees

- `0x180015804`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>::~shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015804  push    rbx
0x180015806  sub     rsp, 20h
0x18001580a  mov     rbx, [rcx+8]
0x18001580e  test    rbx, rbx
0x180015811  jz      short loc_18001584A
0x180015813  or      eax, 0FFFFFFFFh
0x180015816  lock xadd [rbx+8], eax
0x18001581b  cmp     eax, 1
0x18001581e  jnz     short loc_18001584A
0x180015820  mov     rax, [rbx]
0x180015823  mov     rcx, rbx
0x180015826  mov     rax, [rax]
0x180015829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001582e  or      eax, 0FFFFFFFFh
0x180015831  lock xadd [rbx+0Ch], eax
0x180015836  cmp     eax, 1
0x180015839  jnz     short loc_18001584A
0x18001583b  mov     rax, [rbx]
0x18001583e  mov     rcx, rbx
0x180015841  mov     rax, [rax+8]
0x180015845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001584a  add     rsp, 20h
0x18001584e  pop     rbx
0x18001584f  retn
```
