# Microsoft::WRL::ComPtr<MapsBrokerAsyncOperation>::~ComPtr<MapsBrokerAsyncOperation>(void)

- ea: `0x180008fb0`
- end: `0x180008fd0`
- name: `??1?$ComPtr@VMapsBrokerAsyncOperation@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011259`
- `0x18001147b`

## callees

- `0x180007d70`
- `0x180008fb0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<MapsBrokerAsyncOperation>::~ComPtr<MapsBrokerAsyncOperation>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x180008fb0  sub     rsp, 28h
0x180008fb4  mov     rax, [rcx]
0x180008fb7  test    rax, rax
0x180008fba  jz      short loc_180008FCB
0x180008fbc  mov     qword ptr [rcx], 0
0x180008fc3  mov     rcx, rax
0x180008fc6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x180008fcb  add     rsp, 28h
0x180008fcf  retn
```
