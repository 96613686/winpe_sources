# Apx::ApfIpcIoLink_CommandProcess::~ApfIpcIoLink_CommandProcess(void)

- ea: `0x180027640`
- end: `0x18002764b`
- name: `??1ApfIpcIoLink_CommandProcess@Apx@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(Apx::ApfIpcIoLink_CommandProcess *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029afa`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink_CommandProcess::~ApfIpcIoLink_CommandProcess(Apx::ApfIpcIoLink_CommandProcess *this)
{
  *(_QWORD *)this = &Apx::ApfWorkItemBase::`vftable';
}

```

## disassembly

```asm
0x180027640  lea     rax, ??_7ApfWorkItemBase@Apx@@6B@; const Apx::ApfWorkItemBase::`vftable'
0x180027647  mov     [rcx], rax
0x18002764a  retn
```
