# _FileFolder::CreateSubFolder_::_1_::dtor$0

- ea: `0x18001789d`
- end: `0x1800178a9`
- name: `_FileFolder::CreateSubFolder_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800058f4`

## pseudocode

```c
__int64 __fastcall FileFolder::CreateSubFolder_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<FileFolder>::~ComPtr<FileFolder>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x18001789d  lea     rcx, [rdx+40h]
0x1800178a4  jmp     ??1?$ComPtr@VFileFolder@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<FileFolder>::~ComPtr<FileFolder>(void)
```
