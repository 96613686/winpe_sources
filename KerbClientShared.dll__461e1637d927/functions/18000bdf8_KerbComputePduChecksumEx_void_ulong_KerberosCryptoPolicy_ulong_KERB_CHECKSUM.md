# KerbComputePduChecksumEx(void *,ulong,KerberosCryptoPolicy *,ulong,KERB_CHECKSUM *)

- ea: `0x18000bdf8`
- end: `0x18000be7e`
- name: `?KerbComputePduChecksumEx@@YAJPEAXKPEAVKerberosCryptoPolicy@@KPEAUKERB_CHECKSUM@@@Z`
- size: `134`
- prototype: `int(void *, unsigned int, struct KerberosCryptoPolicy *, unsigned int, struct KERB_CHECKSUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bcf4`

## callees

- `0x180001ea0`
- `0x180007e10`
- `0x180009bd8`
- `0x18000bdf8`

## pseudocode

```c
__int64 __fastcall KerbComputePduChecksumEx(
        __int64 a1,
        unsigned int a2,
        struct KerberosCryptoPolicy *a3,
        unsigned int a4,
        struct KERB_CHECKSUM *a5)
{
  unsigned int v8; // edi
  unsigned __int8 *v9; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
    return 3221225485LL;
  v10 = 0;
  v9 = 0;
  if ( (unsigned int)KerbPackData(a1, a2, &v10, &v9) )
    v8 = -1073741801;
  else
    v8 = KerbComputeAsn1PackedPduChecksumEx(v9, v10, a3, a4, a5);
  if ( v9 )
    MIDL_user_free(v9);
  return v8;
}

```

## disassembly

```asm
0x18000bdf8  mov     [rsp+arg_8], rsi
0x18000bdfd  push    rdi
0x18000bdfe  sub     rsp, 40h
0x18000be02  mov     edi, r9d
0x18000be05  mov     rsi, r8
0x18000be08  test    rcx, rcx
0x18000be0b  jnz     short loc_18000BE14
0x18000be0d  mov     eax, 0C000000Dh
0x18000be12  jmp     short loc_18000BE73
0x18000be14  lea     r9, [rsp+48h+var_18]
0x18000be19  mov     [rsp+48h+arg_0], 0
0x18000be21  lea     r8, [rsp+48h+arg_0]
0x18000be26  mov     [rsp+48h+var_18], 0
0x18000be2f  call    KerbPackData
0x18000be34  test    eax, eax
0x18000be36  jz      short loc_18000BE3F
0x18000be38  mov     edi, 0C0000017h
0x18000be3d  jmp     short loc_18000BE5F
0x18000be3f  mov     rax, [rsp+48h+arg_20]
0x18000be44  mov     r9d, edi; unsigned int
0x18000be47  mov     edx, [rsp+48h+arg_0]; unsigned int
0x18000be4b  mov     r8, rsi; struct KerberosCryptoPolicy *
0x18000be4e  mov     rcx, [rsp+48h+var_18]; unsigned __int8 *
0x18000be53  mov     [rsp+48h+var_28], rax; struct KERB_CHECKSUM *
0x18000be58  call    ?KerbComputeAsn1PackedPduChecksumEx@@YAJPEAEKPEAVKerberosCryptoPolicy@@KPEAUKERB_CHECKSUM@@@Z; KerbComputeAsn1PackedPduChecksumEx(uchar *,ulong,KerberosCryptoPolicy *,ulong,KERB_CHECKSUM *)
0x18000be5d  mov     edi, eax
0x18000be5f  cmp     [rsp+48h+var_18], 0
0x18000be65  jz      short loc_18000BE71
0x18000be67  mov     rcx, [rsp+48h+var_18]; void *
0x18000be6c  call    MIDL_user_free
0x18000be71  mov     eax, edi
0x18000be73  mov     rsi, [rsp+48h+arg_8]
0x18000be78  add     rsp, 40h
0x18000be7c  pop     rdi
0x18000be7d  retn
```
