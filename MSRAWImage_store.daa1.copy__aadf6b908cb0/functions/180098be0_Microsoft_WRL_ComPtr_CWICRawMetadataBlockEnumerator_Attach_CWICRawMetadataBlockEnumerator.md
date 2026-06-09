# Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(CWICRawMetadataBlockEnumerator *)

- ea: `0x180098be0`
- end: `0x180098c0c`
- name: `?Attach@?$ComPtr@VCWICRawMetadataBlockEnumerator@@@WRL@Microsoft@@QEAAXPEAVCWICRawMetadataBlockEnumerator@@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800976ac`
- `0x180097808`

## callees

- `0x180098be0`
- `0x18009d150`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<CWICRawMetadataBlockEnumerator>::Attach(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( v4 )
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(v4);
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180098be0  mov     [rsp+arg_0], rbx
0x180098be5  push    rdi
0x180098be6  sub     rsp, 20h
0x180098bea  mov     rbx, rcx
0x180098bed  mov     rdi, rdx
0x180098bf0  mov     rcx, [rcx]
0x180098bf3  test    rcx, rcx
0x180098bf6  jz      short loc_180098BFD
0x180098bf8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEnumUnknown@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEnumUnknown,Microsoft::WRL::FtmBase>::Release(void)
0x180098bfd  mov     [rbx], rdi
0x180098c00  mov     rbx, [rsp+28h+arg_0]
0x180098c05  add     rsp, 20h
0x180098c09  pop     rdi
0x180098c0a  retn
```
