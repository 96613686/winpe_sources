# waveInGetCurrentConsoleVoiceComId

- ea: `0x18000f1fc`
- end: `0x18000f22b`
- name: `waveInGetCurrentConsoleVoiceComId`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007dd0`

## callees

- `0x180008be0`
- `0x18000f1fc`

## pseudocode

```c
__int64 __fastcall waveInGetCurrentConsoleVoiceComId(_DWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  *a1 = -1;
  result = gfUsePreferredWaveOnly != 0;
  *a2 = result;
  if ( gpstrWiConsoleVoiceComStringId )
    return mregGetIdFromStringId(&waveindrvZ, gpstrWiConsoleVoiceComStringId, a1);
  return result;
}

```

## disassembly

```asm
0x18000f1fc  xor     eax, eax
0x18000f1fe  mov     dword ptr [rcx], 0FFFFFFFFh
0x18000f204  cmp     cs:?gfUsePreferredWaveOnly@@3HA, eax; int gfUsePreferredWaveOnly
0x18000f20a  setnz   al
0x18000f20d  mov     [rdx], eax
0x18000f20f  mov     rdx, cs:?gpstrWiConsoleVoiceComStringId@@3PEAGEA; ushort * gpstrWiConsoleVoiceComStringId
0x18000f216  test    rdx, rdx
0x18000f219  jnz     short loc_18000F21C
0x18000f21b  retn
0x18000f21c  mov     r8, rcx
0x18000f21f  lea     rcx, waveindrvZ
0x18000f226  jmp     mregGetIdFromStringId
```
