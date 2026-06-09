# VsmmPhuStoreHvPartitionTeardown

- ea: `0x1400b4168`
- end: `0x1400b42e3`
- name: `VsmmPhuStoreHvPartitionTeardown`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1400a05b0`

## callees

- `0x1400248f4`
- `0x1400ac6ec`
- `0x1400b4168`
- `0x1400b8678`
- `0x1400ba7e4`

## import_xrefs

- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b42bf`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b42bf`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b41b3`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b41b3`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b429c`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b429c`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b42b0`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b42b0`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionTeardown(__int64 a1, __int64 a2)
{
  bool v4; // zf
  int v5; // eax
  __int64 result; // rax
  __int64 v7; // rbx
  char v8; // al
  char v9; // cl

  if ( *(_DWORD *)(a1 + 8632) == 2 )
  {
    v7 = *(_QWORD *)(a1 + 648);
    *(_QWORD *)(a1 + 648) = -1;
    v8 = *(_BYTE *)(a2 + 49);
    *(_QWORD *)(a2 + 56) = v7;
    *(_BYTE *)(a2 + 49) = v8 ^ (*(_BYTE *)(a1 + 8761) ^ v8) & 1;
    v9 = 2 * *(_BYTE *)(a1 + 8762);
    *(_BYTE *)(a1 + 8761) = 0;
    *(_BYTE *)(a2 + 49) ^= (*(_BYTE *)(a2 + 49) ^ v9) & 2;
    *(_BYTE *)(a1 + 8762) = 0;
    *(_BYTE *)(a2 + 49) ^= (*(_BYTE *)(a2 + 49) ^ (4 * *(_BYTE *)(a1 + 3221))) & 4;
    *(_QWORD *)(a2 + 104) = *(_QWORD *)(a1 + 8768);
    *(_QWORD *)(a1 + 8768) = 0;
    VsmmVsmGetPartitionConfig(a1, a2, a2 + 64);
    *(_BYTE *)(a2 + 48) = 1;
    WinHvSetInterceptRoutine(v7, 0, a2);
    WinHvSetLowMemoryPolicyRoutine(v7, 0, a2);
    result = WinHvUnlinkPreExistingPartition(v7);
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 8768) == 0;
    *(_WORD *)(a1 + 8761) = 0;
    if ( !v4 )
    {
      if ( (*(_DWORD *)(a1 + 8640) & 4) != 0 )
        VsmmPhuStorepHvPartitionMirrorTeardown();
      v5 = WinHvDeletePartitionRemote(*(_QWORD *)(a1 + 648));
      if ( v5 < 0 )
        VidTraceErrorStatusPartitionInternal0(
          (unsigned int)"VsmmPhuStoreHvPartitionTeardown",
          (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          3803,
          v5,
          a1 + 656);
      *(_QWORD *)(a1 + 8768) = 0;
    }
    result = VsmmPhuStorepSerializationChargeDecrease(*(_QWORD *)(a1 + 8648), 144);
  }
  *(_BYTE *)(a1 + 8760) = 0;
  return result;
}

```

## disassembly

```asm
0x1400b4168  mov     [rsp+arg_0], rbx
0x1400b416d  mov     [rsp+arg_8], rbp
0x1400b4172  push    rdi
0x1400b4173  sub     rsp, 30h
0x1400b4177  cmp     dword ptr [rcx+21B8h], 2
0x1400b417e  mov     rbp, rdx
0x1400b4181  mov     rdi, rcx
0x1400b4184  jz      loc_1400B420C
0x1400b418a  cmp     qword ptr [rcx+2240h], 0
0x1400b4192  mov     word ptr [rcx+2239h], 0
0x1400b419b  jz      short loc_1400B41F6
0x1400b419d  mov     eax, [rcx+21C0h]
0x1400b41a3  test    al, 4
0x1400b41a5  jz      short loc_1400B41AC
0x1400b41a7  call    VsmmPhuStorepHvPartitionMirrorTeardown
0x1400b41ac  mov     rcx, [rdi+288h]
0x1400b41b3  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b41ba  nop     dword ptr [rax+rax+00h]
0x1400b41bf  test    eax, eax
0x1400b41c1  jns     short loc_1400B41EB
0x1400b41c3  lea     rcx, [rdi+290h]
0x1400b41ca  mov     r9d, eax
0x1400b41cd  mov     [rsp+38h+var_18], rcx
0x1400b41d2  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b41d9  lea     rcx, aVsmmphustorehv_1; "VsmmPhuStoreHvPartitionTeardown"
0x1400b41e0  mov     r8d, 0EDBh
0x1400b41e6  call    VidTraceErrorStatusPartitionInternal0
0x1400b41eb  mov     qword ptr [rdi+2240h], 0
0x1400b41f6  mov     rcx, [rdi+21C8h]
0x1400b41fd  mov     edx, 90h
0x1400b4202  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b4207  jmp     loc_1400B42CB
0x1400b420c  mov     rbx, [rcx+288h]
0x1400b4213  lea     r8, [rdx+40h]
0x1400b4217  mov     qword ptr [rcx+288h], 0FFFFFFFFFFFFFFFFh
0x1400b4222  mov     al, [rdx+31h]
0x1400b4225  mov     [rdx+38h], rbx
0x1400b4229  mov     cl, al
0x1400b422b  xor     cl, [rdi+2239h]
0x1400b4231  and     cl, 1
0x1400b4234  xor     cl, al
0x1400b4236  mov     [rdx+31h], cl
0x1400b4239  mov     cl, [rdi+223Ah]
0x1400b423f  add     cl, cl
0x1400b4241  mov     byte ptr [rdi+2239h], 0
0x1400b4248  mov     al, [rdx+31h]
0x1400b424b  xor     cl, al
0x1400b424d  and     cl, 2
0x1400b4250  xor     cl, al
0x1400b4252  mov     [rdx+31h], cl
0x1400b4255  mov     byte ptr [rdi+223Ah], 0
0x1400b425c  mov     cl, [rdi+0C95h]
0x1400b4262  mov     al, [rdx+31h]
0x1400b4265  shl     cl, 2
0x1400b4268  xor     cl, al
0x1400b426a  and     cl, 4
0x1400b426d  xor     cl, al
0x1400b426f  mov     [rdx+31h], cl
0x1400b4272  mov     rcx, rdi
0x1400b4275  mov     rax, [rdi+2240h]
0x1400b427c  mov     [rdx+68h], rax
0x1400b4280  mov     qword ptr [rdi+2240h], 0
0x1400b428b  call    VsmmVsmGetPartitionConfig
0x1400b4290  mov     r8, rbp
0x1400b4293  mov     byte ptr [rbp+30h], 1
0x1400b4297  xor     edx, edx
0x1400b4299  mov     rcx, rbx
0x1400b429c  call    cs:__imp_WinHvSetInterceptRoutine
0x1400b42a3  nop     dword ptr [rax+rax+00h]
0x1400b42a8  mov     r8, rbp
0x1400b42ab  xor     edx, edx
0x1400b42ad  mov     rcx, rbx
0x1400b42b0  call    cs:__imp_WinHvSetLowMemoryPolicyRoutine
0x1400b42b7  nop     dword ptr [rax+rax+00h]
0x1400b42bc  mov     rcx, rbx
0x1400b42bf  call    cs:__imp_WinHvUnlinkPreExistingPartition
0x1400b42c6  nop     dword ptr [rax+rax+00h]
0x1400b42cb  mov     byte ptr [rdi+2238h], 0
0x1400b42d2  mov     rbx, [rsp+38h+arg_0]
0x1400b42d7  mov     rbp, [rsp+38h+arg_8]
0x1400b42dc  add     rsp, 30h
0x1400b42e0  pop     rdi
0x1400b42e1  retn
```
