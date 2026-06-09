# BfCommonPreOp

- ea: `0x140020730`
- end: `0x1400207e3`
- name: `BfCommonPreOp`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001348`
- `0x1400060f0`
- `0x140020730`

## pseudocode

```c
__int64 __fastcall BfCommonPreOp(struct _FLT_CALLBACK_DATA *a1, __int64 a2)
{
  int v3; // edx
  int v4; // edi
  __int64 result; // rax
  int v6; // [rsp+38h] [rbp-10h]

  if ( !*(_QWORD *)(a2 + 32) )
    return 1;
  v4 = BfCheckAndSwitchTarget(a1);
  if ( v4 >= 0 )
    return 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = v4;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      4,
      21,
      (__int64)WPP_5390131927d33d8db09f7c25a9551f08_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\bindflt.c",
      100,
      v6);
  }
  a1->IoStatus.Status = v4;
  result = 4;
  a1->IoStatus.Information = 0;
  return result;
}

```

## disassembly

```asm
0x140020730  push    rbx
0x140020732  sub     rsp, 40h
0x140020736  cmp     qword ptr [rdx+20h], 0
0x14002073b  mov     rbx, rcx
0x14002073e  jz      short loc_140020793
0x140020740  xor     r9d, r9d
0x140020743  mov     [rsp+48h+arg_0], rdi
0x140020748  xor     r8d, r8d
0x14002074b  call    BfCheckAndSwitchTarget
0x140020750  mov     edi, eax
0x140020752  test    eax, eax
0x140020754  js      short loc_140020767
0x140020756  mov     rdi, [rsp+48h+arg_0]
0x14002075b  mov     eax, 1
0x140020760  add     rsp, 40h
0x140020764  pop     rbx
0x140020765  retn
0x140020767  lea     rax, WPP_RECORDER_INITIALIZED
0x14002076e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020775  jnz     short loc_14002079F
0x140020777  mov     [rbx+18h], edi
0x14002077a  mov     eax, 4
0x14002077f  mov     rdi, [rsp+48h+arg_0]
0x140020784  mov     qword ptr [rbx+20h], 0
0x14002078c  add     rsp, 40h
0x140020790  pop     rbx
0x140020791  retn
0x140020793  mov     eax, 1
0x140020798  add     rsp, 40h
0x14002079c  pop     rbx
0x14002079d  retn
0x14002079f  mov     [rsp+48h+var_10], edi
0x1400207a3  lea     rcx, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400207aa  mov     [rsp+48h+var_18], 564h
0x1400207b2  mov     r9d, 15h
0x1400207b8  mov     [rsp+48h+var_20], rcx
0x1400207bd  mov     r8d, 4
0x1400207c3  lea     rcx, WPP_5390131927d33d8db09f7c25a9551f08_Traceguids
0x1400207ca  mov     dl, 2
0x1400207cc  mov     [rsp+48h+var_28], rcx
0x1400207d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207d8  mov     rcx, [rcx+40h]
0x1400207dc  call    WPP_RECORDER_SF_sDd
0x1400207e1  jmp     short loc_140020777
```
