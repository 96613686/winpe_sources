# DpspIsSemUpdateRequiredForGroupPolicy

- ea: `0x180001740`
- end: `0x180001760`
- name: `DpspIsSemUpdateRequiredForGroupPolicy`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000866c`
- `0x1800166f4`

## callees

- `0x180001740`

## pseudocode

```c
char __fastcall DpspIsSemUpdateRequiredForGroupPolicy(int a1, int a2)
{
  if ( a1 == -1 || a2 == -1 )
    return 0;
  if ( a1 )
  {
    if ( a2 )
      return 0;
  }
  else if ( !a2 )
  {
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001740  or      eax, 0FFFFFFFFh
0x180001743  cmp     ecx, eax
0x180001745  jz      short loc_18000175D
0x180001747  cmp     edx, eax
0x180001749  jz      short loc_18000175D
0x18000174b  test    ecx, ecx
0x18000174d  jnz     short loc_180001756
0x18000174f  test    edx, edx
0x180001751  jnz     short loc_18000175A
0x180001753  xor     eax, eax
0x180001755  retn
0x180001756  test    edx, edx
0x180001758  jnz     short loc_180001753
0x18000175a  mov     al, 1
0x18000175c  retn
0x18000175d  xor     al, al
0x18000175f  retn
```
