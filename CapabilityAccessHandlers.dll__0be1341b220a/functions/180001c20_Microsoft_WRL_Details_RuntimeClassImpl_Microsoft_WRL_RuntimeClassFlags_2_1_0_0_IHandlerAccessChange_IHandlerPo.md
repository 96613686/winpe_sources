# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::AddRef(void)

- ea: `0x180001c20`
- end: `0x180001c47`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessChange@@UIHandlerPolicy@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007520`

## callees

- `0x180001c20`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessChange,IHandlerPolicy>::AddRef(
        __int64 a1)
{
  signed __int32 v1; // eax

  v1 = *(_DWORD *)(a1 + 20);
  if ( v1 == 0x7FFFFFFF )
    return 0x7FFFFFFF;
  while ( v1 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), v1 + 1, v1) )
  {
    v1 = *(_DWORD *)(a1 + 20);
    if ( v1 == 0x7FFFFFFF )
      return 0x7FFFFFFF;
  }
  return (unsigned int)(v1 + 1);
}

```

## disassembly

```asm
0x180001c20  mov     eax, [rcx+14h]
0x180001c23  cmp     eax, 7FFFFFFFh
0x180001c28  jz      short loc_180001C41
0x180001c2a  lea     edx, [rax+1]
0x180001c2d  lock cmpxchg [rcx+14h], edx
0x180001c32  jnz     short loc_180001C37
0x180001c34  mov     eax, edx
0x180001c36  retn
0x180001c37  mov     eax, [rcx+14h]
0x180001c3a  cmp     eax, 7FFFFFFFh
0x180001c3f  jnz     short loc_180001C2A
0x180001c41  mov     eax, 7FFFFFFFh
0x180001c46  retn
```
