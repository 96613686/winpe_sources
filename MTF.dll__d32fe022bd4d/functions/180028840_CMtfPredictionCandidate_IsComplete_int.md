# CMtfPredictionCandidate::IsComplete(int *)

- ea: `0x180028840`
- end: `0x18002884d`
- name: `?IsComplete@CMtfPredictionCandidate@@UEAAJPEAH@Z`
- size: `13`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::IsComplete(CMtfPredictionCandidate *this, int *a2)
{
  *a2 = *((_BYTE *)this + 104) != 0;
  return 0;
}

```

## disassembly

```asm
0x180028840  xor     eax, eax
0x180028842  cmp     [rcx+68h], al
0x180028845  setnz   al
0x180028848  mov     [rdx], eax
0x18002884a  xor     eax, eax
0x18002884c  retn
```
