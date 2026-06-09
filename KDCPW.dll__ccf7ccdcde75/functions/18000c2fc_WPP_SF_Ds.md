# WPP_SF_Ds

- ea: `0x18000c2fc`
- end: `0x18000c34d`
- name: `WPP_SF_Ds`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000c034`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c342`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000c342`

## string_xrefs

- `0x18000c30f`: `KerberosCryptoPolicy::OpenEncryptionAlgorithm`

## pseudocode

```c
ULONG __fastcall WPP_SF_Ds(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids,
           a2,
           &v5,
           4,
           "KerberosCryptoPolicy::OpenEncryptionAlgorithm",
           46,
           0);
}

```

## disassembly

```asm
0x18000c2fc  mov     r11, rsp
0x18000c2ff  mov     [r11+20h], r9d
0x18000c303  sub     rsp, 58h
0x18000c307  mov     qword ptr [r11-18h], 0
0x18000c30f  lea     rax, aKerberoscrypto; "KerberosCryptoPolicy::OpenEncryptionAlg"...
0x18000c316  mov     qword ptr [r11-20h], 2Eh ; '.'
0x18000c31e  lea     r8, WPP_f81d0d46d7e031887edddacc4e8197ab_Traceguids; MessageGuid
0x18000c325  mov     [r11-28h], rax
0x18000c329  lea     rax, [r11+20h]
0x18000c32d  movzx   r9d, dx; MessageNumber
0x18000c331  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c336  mov     qword ptr [r11-30h], 4
0x18000c33e  mov     [r11-38h], rax
0x18000c342  call    cs:__imp_TraceMessage
0x18000c348  add     rsp, 58h
0x18000c34c  retn
```
