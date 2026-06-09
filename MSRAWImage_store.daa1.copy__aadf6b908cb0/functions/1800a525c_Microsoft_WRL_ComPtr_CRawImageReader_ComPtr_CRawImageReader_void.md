# Microsoft::WRL::ComPtr<CRawImageReader>::~ComPtr<CRawImageReader>(void)

- ea: `0x1800a525c`
- end: `0x1800a527d`
- name: `??1?$ComPtr@VCRawImageReader@@@WRL@Microsoft@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b3037`
- `0x1800b31b1`
- `0x1800b34ab`

## callees

- `0x1800a525c`
- `0x1800ad270`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<CRawImageReader>::~ComPtr<CRawImageReader>(__int64 *a1, volatile int *a2)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(
             result,
             a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800a525c  sub     rsp, 28h
0x1800a5260  mov     rax, [rcx]
0x1800a5263  test    rax, rax
0x1800a5266  jz      short loc_1800A5277
0x1800a5268  mov     qword ptr [rcx], 0
0x1800a526f  mov     rcx, rax
0x1800a5272  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIRawImageReader@@UIMFTelemetryComponent@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IRawImageReader,IMFTelemetryComponent,Microsoft::WRL::FtmBase>::Release(void)
0x1800a5277  add     rsp, 28h
0x1800a527b  retn
```
