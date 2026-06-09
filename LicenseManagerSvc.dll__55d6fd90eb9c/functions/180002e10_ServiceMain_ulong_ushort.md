# ServiceMain(ulong,ushort * *)

- ea: `0x180002e10`
- end: `0x180002e4b`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `59`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180001ea0`

## pseudocode

```c
void __fastcall ServiceMain(const unsigned __int16 *a1, unsigned __int16 **a2, __int64 a3, unsigned __int16 **a4)
{
  void **v4; // [rsp+20h] [rbp-48h] BYREF
  int v5; // [rsp+28h] [rbp-40h]
  __int64 v6; // [rsp+30h] [rbp-38h]
  char v7; // [rsp+38h] [rbp-30h]
  __int128 v8; // [rsp+40h] [rbp-28h]
  __int64 v9; // [rsp+50h] [rbp-18h]

  v4 = &LMCallback::`vftable';
  v8 = 0;
  v5 = 0;
  v7 = 0;
  v9 = 0;
  v6 = 0;
  ServiceMainImpl(a1, (struct ServiceMainCallback *)&v4, a3, a4);
}

```

## disassembly

```asm
0x180002e10  mov     r11, rsp
0x180002e13  sub     rsp, 68h
0x180002e17  lea     rax, ??_7LMCallback@@6B@; const LMCallback::`vftable'
0x180002e1e  xorps   xmm0, xmm0
0x180002e21  mov     [r11-48h], rax
0x180002e25  lea     rdx, [r11-48h]; struct ServiceMainCallback *
0x180002e29  xor     eax, eax
0x180002e2b  movdqa  [rsp+68h+var_28], xmm0
0x180002e31  mov     [rsp+68h+var_40], eax
0x180002e35  mov     [rsp+68h+var_30], al
0x180002e39  mov     [r11-18h], rax
0x180002e3d  mov     [r11-38h], rax
0x180002e41  call    ?ServiceMainImpl@@YAJPEBGPEAUServiceMainCallback@@KPEAPEAG@Z; ServiceMainImpl(ushort const *,ServiceMainCallback *,ulong,ushort * *)
0x180002e46  add     rsp, 68h
0x180002e4a  retn
```
