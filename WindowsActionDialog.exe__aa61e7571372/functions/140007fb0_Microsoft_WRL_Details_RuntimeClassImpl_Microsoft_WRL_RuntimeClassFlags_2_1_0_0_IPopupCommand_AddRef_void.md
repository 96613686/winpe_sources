# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::AddRef(void)

- ea: `0x140007fb0`
- end: `0x140007fd9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007fb0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::AddRef(
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
0x140007fb0  mov     r9d, 7FFFFFFFh
0x140007fb6  jmp     short loc_140007FC6
0x140007fb8  lea     edx, [r8+1]
0x140007fbc  mov     eax, r8d
0x140007fbf  lock cmpxchg [rcx+0Ch], edx
0x140007fc4  jz      short loc_140007FD1
0x140007fc6  mov     r8d, [rcx+0Ch]
0x140007fca  cmp     r8d, r9d
0x140007fcd  jnz     short loc_140007FB8
0x140007fcf  jmp     short loc_140007FD5
0x140007fd1  lea     r9d, [r8+1]
0x140007fd5  mov     eax, r9d
0x140007fd8  retn
```
