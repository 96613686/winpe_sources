# Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>::~ComPtr<Windows::Storage::IStorageFileStatics>(void)

- ea: `0x180008678`
- end: `0x1800086a0`
- name: `??1?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f79d`
- `0x18000f7af`

## callees

- `0x180008678`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>::~ComPtr<Windows::Storage::IStorageFileStatics>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180008678  sub     rsp, 28h
0x18000867c  mov     rax, rcx
0x18000867f  mov     rcx, [rcx]
0x180008682  test    rcx, rcx
0x180008685  jz      short loc_18000869B
0x180008687  mov     qword ptr [rax], 0
0x18000868e  mov     rax, [rcx]
0x180008691  mov     rax, [rax+10h]
0x180008695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000869a  nop
0x18000869b  add     rsp, 28h
0x18000869f  retn
```
