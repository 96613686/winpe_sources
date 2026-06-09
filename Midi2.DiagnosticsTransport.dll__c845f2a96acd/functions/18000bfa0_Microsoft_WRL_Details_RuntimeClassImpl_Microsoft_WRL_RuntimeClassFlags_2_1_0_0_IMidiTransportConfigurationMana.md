# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::AddRef(void)

- ea: `0x18000bfa0`
- end: `0x18000bfc9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMidiTransportConfigurationManager@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000bfa0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMidiTransportConfigurationManager>::AddRef(
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
0x18000bfa0  mov     r9d, 7FFFFFFFh
0x18000bfa6  jmp     short loc_18000BFB6
0x18000bfa8  lea     edx, [r8+1]
0x18000bfac  mov     eax, r8d
0x18000bfaf  lock cmpxchg [rcx+0Ch], edx
0x18000bfb4  jz      short loc_18000BFC1
0x18000bfb6  mov     r8d, [rcx+0Ch]
0x18000bfba  cmp     r8d, r9d
0x18000bfbd  jnz     short loc_18000BFA8
0x18000bfbf  jmp     short loc_18000BFC5
0x18000bfc1  lea     r9d, [r8+1]
0x18000bfc5  mov     eax, r9d
0x18000bfc8  retn
```
