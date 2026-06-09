# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x180004f80`
- end: `0x180004fa9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVRadio@Radios@Devices@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004fb0`

## callees

- `0x180004f80`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Devices::Radios::Radio *> *>,Microsoft::WRL::FtmBase>::AddRef(
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
0x180004f80  mov     r9d, 7FFFFFFFh
0x180004f86  jmp     short loc_180004F96
0x180004f88  lea     edx, [r8+1]
0x180004f8c  mov     eax, r8d
0x180004f8f  lock cmpxchg [rcx+2Ch], edx
0x180004f94  jz      short loc_180004FA1
0x180004f96  mov     r8d, [rcx+2Ch]
0x180004f9a  cmp     r8d, r9d
0x180004f9d  jnz     short loc_180004F88
0x180004f9f  jmp     short loc_180004FA5
0x180004fa1  lea     r9d, [r8+1]
0x180004fa5  mov     eax, r9d
0x180004fa8  retn
```
