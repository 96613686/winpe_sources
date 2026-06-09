# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x140006458`
- end: `0x140006494`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `60`
- prototype: `void __fastcall(unsigned __int8, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000649c`

## callees

- `0x140006458`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2)
{
  int v2; // edx
  int v3; // r8d
  signed __int32 v4; // eax
  signed __int32 v5; // ett

  v2 = a2 - 3;
  if ( v2 )
  {
    if ( v2 != 1 )
      return;
    v3 = 32;
  }
  else
  {
    v3 = 16;
  }
  v4 = *Feature_Servicing_GameInputSvcRedirectionGuard__private_descriptor[0];
  do
  {
    if ( (v4 & 2) == 0 )
      break;
    if ( ((a1 ^ (unsigned __int8)v4) & 1) != 0 )
      break;
    v5 = v4;
    v4 = _InterlockedCompareExchange(Feature_Servicing_GameInputSvcRedirectionGuard__private_descriptor[0], v4 | v3, v4);
  }
  while ( v5 != v4 );
}

```

## disassembly

```asm
0x140006458  sub     edx, 3
0x14000645b  jz      short loc_140006468
0x14000645d  cmp     edx, 1
0x140006460  jnz     short locret_140006493
0x140006462  lea     r8d, [rdx+1Fh]
0x140006466  jmp     short loc_14000646E
0x140006468  mov     r8d, 10h
0x14000646e  mov     r9, cs:Feature_Servicing_GameInputSvcRedirectionGuard__private_descriptor
0x140006475  mov     eax, [r9]
0x140006478  jmp     short loc_14000648F
0x14000647a  mov     edx, eax
0x14000647c  xor     edx, ecx
0x14000647e  test    dl, 1
0x140006481  jnz     short locret_140006493
0x140006483  mov     edx, r8d
0x140006486  or      edx, eax
0x140006488  lock cmpxchg [r9], edx
0x14000648d  jz      short locret_140006493
0x14000648f  test    al, 2
0x140006491  jnz     short loc_14000647A
0x140006493  retn
```
