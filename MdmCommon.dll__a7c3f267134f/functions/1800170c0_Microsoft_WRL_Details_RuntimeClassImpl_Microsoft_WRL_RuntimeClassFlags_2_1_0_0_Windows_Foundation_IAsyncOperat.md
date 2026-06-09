# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::AddRef(void)

- ea: `0x1800170c0`
- end: `0x1800170e9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800170c0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::AddRef(
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
0x1800170c0  mov     r9d, 7FFFFFFFh
0x1800170c6  jmp     short loc_1800170D6
0x1800170c8  lea     edx, [r8+1]
0x1800170cc  mov     eax, r8d
0x1800170cf  lock cmpxchg [rcx+0Ch], edx
0x1800170d4  jz      short loc_1800170E1
0x1800170d6  mov     r8d, [rcx+0Ch]
0x1800170da  cmp     r8d, r9d
0x1800170dd  jnz     short loc_1800170C8
0x1800170df  jmp     short loc_1800170E5
0x1800170e1  lea     r9d, [r8+1]
0x1800170e5  mov     eax, r9d
0x1800170e8  retn
```
