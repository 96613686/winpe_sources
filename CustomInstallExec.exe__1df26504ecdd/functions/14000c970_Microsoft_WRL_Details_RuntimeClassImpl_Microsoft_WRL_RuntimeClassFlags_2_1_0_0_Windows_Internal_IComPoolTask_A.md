# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::AddRef(void)

- ea: `0x14000c970`
- end: `0x14000c999`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c970`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 12);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x14000c970  mov     r9d, 7FFFFFFFh
0x14000c976  jmp     short loc_14000C986
0x14000c978  lea     edx, [r8+1]
0x14000c97c  mov     eax, r8d
0x14000c97f  lock cmpxchg [rcx+0Ch], edx
0x14000c984  jz      short loc_14000C991
0x14000c986  mov     r8d, [rcx+0Ch]
0x14000c98a  cmp     r8d, r9d
0x14000c98d  jnz     short loc_14000C978
0x14000c98f  jmp     short loc_14000C995
0x14000c991  lea     r9d, [r8+1]
0x14000c995  mov     eax, r9d
0x14000c998  retn
```
