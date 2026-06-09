# Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=(IMFTelemetrySession *)

- ea: `0x18009874c`
- end: `0x180098794`
- name: `??4?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFTelemetrySession@@@Z`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009db90`
- `0x1800a25b8`
- `0x1800ad600`
- `0x1800ad9a0`

## callees

- `0x1800967ac`
- `0x18009874c`
- `0x18009c41c`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<IMFTelemetrySession>::operator=(__int64 *a1, __int64 a2)
{
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 != a2 )
  {
    v5 = a2;
    Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(&v5);
    v5 = *a1;
    *a1 = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18009874c  mov     [rsp+arg_8], rbx
0x180098751  push    rdi
0x180098752  sub     rsp, 20h
0x180098756  mov     rdi, rdx
0x180098759  mov     rbx, rcx
0x18009875c  cmp     [rcx], rdx
0x18009875f  jz      short loc_180098785
0x180098761  lea     rcx, [rsp+28h+arg_0]
0x180098766  mov     [rsp+28h+arg_0], rdx
0x18009876b  call    ?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)
0x180098770  mov     rax, [rbx]
0x180098773  lea     rcx, [rsp+28h+arg_0]
0x180098778  mov     [rsp+28h+arg_0], rax
0x18009877d  mov     [rbx], rdi
0x180098780  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180098785  mov     rax, rbx
0x180098788  mov     rbx, [rsp+28h+arg_8]
0x18009878d  add     rsp, 20h
0x180098791  pop     rdi
0x180098792  retn
```
