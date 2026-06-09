# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::AddRef(void)

- ea: `0x180007a70`
- end: `0x180007a99`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007a70`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::AddRef(
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
0x180007a70  mov     r9d, 7FFFFFFFh
0x180007a76  jmp     short loc_180007A86
0x180007a78  lea     edx, [r8+1]
0x180007a7c  mov     eax, r8d
0x180007a7f  lock cmpxchg [rcx+0Ch], edx
0x180007a84  jz      short loc_180007A91
0x180007a86  mov     r8d, [rcx+0Ch]
0x180007a8a  cmp     r8d, r9d
0x180007a8d  jnz     short loc_180007A78
0x180007a8f  jmp     short loc_180007A95
0x180007a91  lea     r9d, [r8+1]
0x180007a95  mov     eax, r9d
0x180007a98  retn
```
