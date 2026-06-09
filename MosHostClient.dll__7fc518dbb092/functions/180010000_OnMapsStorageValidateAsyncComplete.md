# OnMapsStorageValidateAsyncComplete

- ea: `0x180010000`
- end: `0x180010031`
- name: `OnMapsStorageValidateAsyncComplete`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall OnMapsStorageValidateAsyncComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 (__fastcall *v4)(__int64, __int128 *, __int64); // rax
  __int64 v5; // xmm1_8
  __int64 v6; // r8
  __int128 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h]

  v3 = *(_OWORD *)(a3 + 32);
  v4 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(a3 + 16);
  v5 = *(_QWORD *)(a3 + 48);
  v6 = *(_QWORD *)(a3 + 24);
  v8 = v3;
  v9 = v5;
  return v4(a1, &v8, v6);
}

```

## disassembly

```asm
0x180010000  sub     rsp, 48h
0x180010004  movups  xmm0, xmmword ptr [r8+20h]
0x180010009  lea     rdx, [rsp+48h+var_28]
0x18001000e  mov     rax, [r8+10h]
0x180010012  movsd   xmm1, qword ptr [r8+30h]
0x180010018  mov     r8, [r8+18h]
0x18001001c  movaps  [rsp+48h+var_28], xmm0
0x180010021  movsd   [rsp+48h+var_18], xmm1
0x180010027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002c  add     rsp, 48h
0x180010030  retn
```
