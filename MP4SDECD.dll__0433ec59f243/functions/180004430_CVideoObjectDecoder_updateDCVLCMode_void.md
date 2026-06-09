# CVideoObjectDecoder::updateDCVLCMode(void)

- ea: `0x180004430`
- end: `0x180004464`
- name: `?updateDCVLCMode@CVideoObjectDecoder@@AEAAXXZ`
- size: `52`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180002e90`
- `0x180004f10`
- `0x180024e8c`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180004430`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::updateDCVLCMode(CVideoObjectDecoder *this)
{
  int v1; // eax

  v1 = *((_DWORD *)this + 219);
  *((_DWORD *)this + 347) = v1 && (v1 == 7 || *((_DWORD *)this + 349) >= 2 * v1 + 11);
}

```

## disassembly

```asm
0x180004430  mov     eax, [rcx+36Ch]
0x180004436  test    eax, eax
0x180004438  jnz     short loc_180004445
0x18000443a  mov     dword ptr [rcx+56Ch], 0
0x180004444  retn
0x180004445  cmp     eax, 7
0x180004448  jz      short loc_180004459
0x18000444a  lea     eax, ds:0Bh[rax*2]
0x180004451  cmp     [rcx+574h], eax
0x180004457  jl      short loc_18000443A
0x180004459  mov     dword ptr [rcx+56Ch], 1
0x180004463  retn
```
