# _RegistryManager::CreateRedirectionMap_::_1_::dtor$0

- ea: `0x140007548`
- end: `0x14000756e`
- name: `_RegistryManager::CreateRedirectionMap_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140006444`
- `0x140007548`

## pseudocode

```c
__int64 __fastcall RegistryManager::CreateRedirectionMap_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::map<unsigned short const *,unsigned short const *>::~map<unsigned short const *,unsigned short const *>(*(_QWORD *)(a2 + 72));
  }
  return result;
}

```

## disassembly

```asm
0x140007548  push    rbp
0x14000754a  sub     rsp, 20h
0x14000754e  mov     rbp, rdx
0x140007551  mov     eax, [rbp+20h]
0x140007554  and     eax, 1
0x140007557  test    eax, eax
0x140007559  jz      short loc_140007568
0x14000755b  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14000755f  mov     rcx, [rbp+48h]
0x140007563  call    ??1?$map@PEBGPEBGU?$less@PEBG@std@@V?$allocator@U?$pair@QEBGPEBG@std@@@2@@std@@QEAA@XZ; std::map<ushort const *,ushort const *>::~map<ushort const *,ushort const *>(void)
0x140007568  add     rsp, 20h
0x14000756c  pop     rbp
0x14000756d  retn
```
