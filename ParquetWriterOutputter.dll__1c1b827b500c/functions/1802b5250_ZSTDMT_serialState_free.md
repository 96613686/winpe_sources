# ZSTDMT_serialState_free

- ea: `0x1802b5250`
- end: `0x1802b52da`
- name: `ZSTDMT_serialState_free`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1802b4440`

## callees

- `0x1802af0e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1802b5273`
- `KERNEL32!DeleteCriticalSection` at `0x1802b5280`
- `KERNEL32!DeleteCriticalSection` at `0x1802b5273`
- `KERNEL32!DeleteCriticalSection` at `0x1802b5280`

## pseudocode

```c
__int64 __fastcall ZSTDMT_serialState_free(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int128 v5; // [rsp+20h] [rbp-38h]
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]
  __int64 v8; // [rsp+60h] [rbp+8h]

  v5 = *(_OWORD *)(a1 + 168);
  v8 = *(_QWORD *)(a1 + 184);
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 344));
  v2 = *(_QWORD *)(a1 + 224);
  v6 = v5;
  v7 = v8;
  ZSTD_free(v2, &v6);
  v3 = *(_QWORD *)(a1 + 232);
  v6 = v5;
  v7 = v8;
  return ZSTD_free(v3, &v6);
}

```

## disassembly

```asm
0x1802b5250  push    rbx
0x1802b5252  sub     rsp, 50h
0x1802b5256  movups  xmm0, xmmword ptr [rcx+0A8h]
0x1802b525d  mov     rbx, rcx
0x1802b5260  movups  [rsp+58h+var_38], xmm0
0x1802b5265  movsd   xmm0, qword ptr [rcx+0B8h]
0x1802b526d  movsd   [rsp+58h+arg_0], xmm0
0x1802b5273  call    cs:__imp_DeleteCriticalSection
0x1802b5279  lea     rcx, [rbx+158h]; lpCriticalSection
0x1802b5280  call    cs:__imp_DeleteCriticalSection
0x1802b5286  movups  xmm0, [rsp+58h+var_38]
0x1802b528b  mov     rcx, [rbx+0E0h]
0x1802b5292  lea     rdx, [rsp+58h+var_28]
0x1802b5297  movaps  [rsp+58h+var_28], xmm0
0x1802b529c  movsd   xmm0, [rsp+58h+arg_0]
0x1802b52a2  movsd   [rsp+58h+var_18], xmm0
0x1802b52a8  call    ZSTD_free
0x1802b52ad  movups  xmm0, [rsp+58h+var_38]
0x1802b52b2  mov     rcx, [rbx+0E8h]
0x1802b52b9  lea     rdx, [rsp+58h+var_28]
0x1802b52be  movaps  [rsp+58h+var_28], xmm0
0x1802b52c3  movsd   xmm0, [rsp+58h+arg_0]
0x1802b52c9  movsd   [rsp+58h+var_18], xmm0
0x1802b52cf  call    ZSTD_free
0x1802b52d4  add     rsp, 50h
0x1802b52d8  pop     rbx
0x1802b52d9  retn
```
