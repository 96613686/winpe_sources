# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x140010620`
- end: `0x140010649`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x140010620`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 44);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 44), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140010620  mov     r9d, 7FFFFFFFh
0x140010626  jmp     short loc_140010636
0x140010628  lea     edx, [r8+1]
0x14001062c  mov     eax, r8d
0x14001062f  lock cmpxchg [rcx+2Ch], edx
0x140010634  jz      short loc_140010641
0x140010636  mov     r8d, [rcx+2Ch]
0x14001063a  cmp     r8d, r9d
0x14001063d  jnz     short loc_140010628
0x14001063f  jmp     short loc_140010645
0x140010641  lea     r9d, [r8+1]
0x140010645  mov     eax, r9d
0x140010648  retn
```
