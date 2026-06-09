# Microsoft::WRL::ComPtr<AutoDeleteFileStream>::~ComPtr<AutoDeleteFileStream>(void)

- ea: `0x180010280`
- end: `0x1800102a0`
- name: `??1?$ComPtr@VAutoDeleteFileStream@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011d43`

## callees

- `0x180010280`
- `0x1800106e0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<AutoDeleteFileStream>::~ComPtr<AutoDeleteFileStream>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x180010280  sub     rsp, 28h
0x180010284  mov     rax, [rcx]
0x180010287  test    rax, rax
0x18001028a  jz      short loc_18001029B
0x18001028c  mov     qword ptr [rcx], 0
0x180010293  mov     rcx, rax
0x180010296  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIStream@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream>::Release(void)
0x18001029b  add     rsp, 28h
0x18001029f  retn
```
