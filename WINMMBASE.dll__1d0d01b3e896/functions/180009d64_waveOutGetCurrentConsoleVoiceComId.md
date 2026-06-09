# waveOutGetCurrentConsoleVoiceComId

- ea: `0x180009d64`
- end: `0x180009d93`
- name: `waveOutGetCurrentConsoleVoiceComId`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007dd0`

## callees

- `0x180008be0`
- `0x180009d64`

## pseudocode

```c
__int64 __fastcall waveOutGetCurrentConsoleVoiceComId(_DWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  *a1 = -1;
  result = gfUsePreferredWaveOnly != 0;
  *a2 = result;
  if ( gpstrWoConsoleVoiceComStringId )
    return mregGetIdFromStringId(&waveoutdrvZ, gpstrWoConsoleVoiceComStringId, a1);
  return result;
}

```

## disassembly

```asm
0x180009d64  xor     eax, eax
0x180009d66  mov     dword ptr [rcx], 0FFFFFFFFh
0x180009d6c  cmp     cs:?gfUsePreferredWaveOnly@@3HA, eax; int gfUsePreferredWaveOnly
0x180009d72  setnz   al
0x180009d75  mov     [rdx], eax
0x180009d77  mov     rdx, cs:?gpstrWoConsoleVoiceComStringId@@3PEAGEA; ushort * gpstrWoConsoleVoiceComStringId
0x180009d7e  test    rdx, rdx
0x180009d81  jnz     short loc_180009D84
0x180009d83  retn
0x180009d84  mov     r8, rcx
0x180009d87  lea     rcx, waveoutdrvZ
0x180009d8e  jmp     mregGetIdFromStringId
```
