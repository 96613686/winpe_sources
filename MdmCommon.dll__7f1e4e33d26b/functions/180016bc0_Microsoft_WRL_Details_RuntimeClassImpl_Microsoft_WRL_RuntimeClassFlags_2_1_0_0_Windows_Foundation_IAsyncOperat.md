# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>>::AddRef(void)

- ea: `0x180016bc0`
- end: `0x180016be9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016bc0`

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
0x180016bc0  mov     r9d, 7FFFFFFFh
0x180016bc6  jmp     short loc_180016BD6
0x180016bc8  lea     edx, [r8+1]
0x180016bcc  mov     eax, r8d
0x180016bcf  lock cmpxchg [rcx+0Ch], edx
0x180016bd4  jz      short loc_180016BE1
0x180016bd6  mov     r8d, [rcx+0Ch]
0x180016bda  cmp     r8d, r9d
0x180016bdd  jnz     short loc_180016BC8
0x180016bdf  jmp     short loc_180016BE5
0x180016be1  lea     r9d, [r8+1]
0x180016be5  mov     eax, r9d
0x180016be8  retn
```
