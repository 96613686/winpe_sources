# KerbComputeAsn1PackedPduChecksumEx(uchar *,ulong,KerberosCryptoPolicy *,ulong,KERB_CHECKSUM *)

- ea: `0x180009bd8`
- end: `0x180009c41`
- name: `?KerbComputeAsn1PackedPduChecksumEx@@YAJPEAEKPEAVKerberosCryptoPolicy@@KPEAUKERB_CHECKSUM@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct KerberosCryptoPolicy *, unsigned int, struct KERB_CHECKSUM *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a920`
- `0x18000bdf8`

## callees

- `0x180009bd8`
- `0x18001799c`
- `0x180018280`

## pseudocode

```c
__int64 __fastcall KerbComputeAsn1PackedPduChecksumEx(
        unsigned __int8 *a1,
        unsigned int a2,
        struct KerberosCryptoPolicy *a3,
        unsigned int a4,
        struct KERB_CHECKSUM *a5)
{
  __int64 v5; // rsi
  __int64 v9; // rax
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF

  v5 = a2;
  v9 = KerberosCryptoPolicy::SelectChecksumAlgorithm(a3, a4);
  if ( !v9 )
    return 3221226227LL;
  v11[0] = v5;
  v11[1] = a1;
  return KerberosCryptoPolicy::GetMic(a3, v9, a4, (__int64)v11, (__int64)a5) == 0 ? 0xC00002F3 : 0;
}

```

## disassembly

```asm
0x180009bd8  push    rbx
0x180009bda  push    rbp
0x180009bdb  push    rsi
0x180009bdc  push    rdi
0x180009bdd  sub     rsp, 48h
0x180009be1  mov     esi, edx
0x180009be3  mov     rbp, rcx
0x180009be6  mov     edx, r9d
0x180009be9  mov     rcx, r8
0x180009bec  mov     rbx, r8
0x180009bef  mov     edi, r9d
0x180009bf2  call    ?SelectChecksumAlgorithm@KerberosCryptoPolicy@@QEAAPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectChecksumAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x180009bf7  test    rax, rax
0x180009bfa  jz      short loc_180009C33
0x180009bfc  mov     rcx, [rsp+68h+arg_20]
0x180009c04  lea     r9, [rsp+68h+var_38]
0x180009c09  mov     [rsp+68h+var_48], rcx
0x180009c0e  mov     r8d, edi
0x180009c11  mov     rcx, rbx
0x180009c14  mov     [rsp+68h+var_38], rsi
0x180009c19  mov     rdx, rax
0x180009c1c  mov     [rsp+68h+var_30], rbp
0x180009c21  call    ?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAUKERB_CHECKSUM@@@Z; KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,KERB_CHECKSUM *)
0x180009c26  neg     al
0x180009c28  sbb     eax, eax
0x180009c2a  not     eax
0x180009c2c  and     eax, 0C00002F3h
0x180009c31  jmp     short loc_180009C38
0x180009c33  mov     eax, 0C00002F3h
0x180009c38  add     rsp, 48h
0x180009c3c  pop     rdi
0x180009c3d  pop     rsi
0x180009c3e  pop     rbp
0x180009c3f  pop     rbx
0x180009c40  retn
```
