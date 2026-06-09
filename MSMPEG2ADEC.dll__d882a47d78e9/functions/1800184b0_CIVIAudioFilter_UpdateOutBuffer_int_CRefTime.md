# CIVIAudioFilter::UpdateOutBuffer(int,CRefTime)

- ea: `0x1800184b0`
- end: `0x1800184be`
- name: `?UpdateOutBuffer@CIVIAudioFilter@@MEAAXHVCRefTime@@@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
void __fastcall CIVIAudioFilter::UpdateOutBuffer(__int64 a1, int a2, __int64 a3)
{
  *(_QWORD *)(a1 + 16376) += a3;
  *(_DWORD *)(a1 + 16400) += a2;
}

```

## disassembly

```asm
0x1800184b0  add     [rcx+3FF8h], r8
0x1800184b7  add     [rcx+4010h], edx
0x1800184bd  retn
```
