# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x180011db0`
- end: `0x180011dd9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVProductKeyRedemptionResult@Licensing@System@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011de0`

## callees

- `0x180011db0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Licensing::ProductKeyRedemptionResult *>,Microsoft::WRL::FtmBase>::AddRef(
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
0x180011db0  mov     r9d, 7FFFFFFFh
0x180011db6  jmp     short loc_180011DC6
0x180011db8  lea     edx, [r8+1]
0x180011dbc  mov     eax, r8d
0x180011dbf  lock cmpxchg [rcx+2Ch], edx
0x180011dc4  jz      short loc_180011DD1
0x180011dc6  mov     r8d, [rcx+2Ch]
0x180011dca  cmp     r8d, r9d
0x180011dcd  jnz     short loc_180011DB8
0x180011dcf  jmp     short loc_180011DD5
0x180011dd1  lea     r9d, [r8+1]
0x180011dd5  mov     eax, r9d
0x180011dd8  retn
```
