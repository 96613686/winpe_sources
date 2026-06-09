# BampComputeExemptProcessPpmPolicy

- ea: `0x140011010`
- end: `0x14001107b`
- name: `BampComputeExemptProcessPpmPolicy`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010a30`

## callees

- `0x140011010`
- `0x140011090`

## pseudocode

```c
__int64 __fastcall BampComputeExemptProcessPpmPolicy(__int64 a1)
{
  _DWORD *v1; // rcx
  __int128 v3; // [rsp+20h] [rbp-28h] BYREF
  __int64 v4; // [rsp+30h] [rbp-18h]

  v3 = 0;
  v4 = 0;
  BampThrottledProcessGetEffectiveState(a1, &v3);
  if ( HIDWORD(v4) == 2 )
    return 3;
  if ( (v1[79] & 1) != 0 )
  {
    if ( (v1[80] & 1) != 0 )
      return (v3 & 1) != 0 ? 3 : 0;
    return 3;
  }
  if ( (v1[94] & 1) != 0 )
    return (v3 & 1) != 0 ? 3 : 0;
  return 0;
}

```

## disassembly

```asm
0x140011010  sub     rsp, 48h
0x140011014  xorps   xmm0, xmm0
0x140011017  lea     rdx, [rsp+48h+var_28]
0x14001101c  xor     eax, eax
0x14001101e  movups  [rsp+48h+var_28], xmm0
0x140011023  mov     [rsp+48h+var_18], rax
0x140011028  call    BampThrottledProcessGetEffectiveState
0x14001102d  cmp     dword ptr [rsp+48h+var_18+4], 2
0x140011032  jz      short loc_14001105C
0x140011034  mov     eax, [rcx+13Ch]
0x14001103a  test    al, 1
0x14001103c  jnz     short loc_14001106F
0x14001103e  mov     eax, [rcx+178h]
0x140011044  test    al, 1
0x140011046  jz      short loc_140011067
0x140011048  movzx   eax, byte ptr [rsp+48h+var_28]
0x14001104d  and     al, 1
0x14001104f  neg     al
0x140011051  sbb     eax, eax
0x140011053  and     eax, 3
0x140011056  add     rsp, 48h
0x14001105a  retn
0x14001105c  mov     eax, 3
0x140011061  add     rsp, 48h
0x140011065  retn
0x140011067  xor     eax, eax
0x140011069  add     rsp, 48h
0x14001106d  retn
0x14001106f  mov     eax, [rcx+140h]
0x140011075  test    al, 1
0x140011077  jnz     short loc_140011048
0x140011079  jmp     short loc_14001105C
```
