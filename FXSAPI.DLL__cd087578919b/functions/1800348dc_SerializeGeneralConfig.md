# SerializeGeneralConfig

- ea: `0x1800348dc`
- end: `0x18003498b`
- name: `SerializeGeneralConfig`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011ed0`

## callees

- `0x18000abe4`
- `0x18002c750`
- `0x1800348dc`

## pseudocode

```c
void __fastcall SerializeGeneralConfig(__int64 a1, int a2, __int64 a3, unsigned int a4, __int64 a5, _QWORD *a6)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids);
  }
  if ( !a2 )
  {
    if ( a3 )
    {
      *(_OWORD *)a5 = *(_OWORD *)a1;
      *(_OWORD *)(a5 + 16) = *(_OWORD *)(a1 + 16);
      *(_OWORD *)(a5 + 32) = *(_OWORD *)(a1 + 32);
      *(_OWORD *)(a5 + 48) = *(_OWORD *)(a1 + 48);
      *(_OWORD *)(a5 + 64) = *(_OWORD *)(a1 + 64);
      *(_QWORD *)(a5 + 80) = *(_QWORD *)(a1 + 80);
    }
    StoreString(*(unsigned __int16 **)(a1 + 8), (_QWORD *)(a5 + 8), a3, a6, a4);
  }
}

```

## disassembly

```asm
0x1800348dc  push    rbx
0x1800348de  push    rbp
0x1800348df  push    rsi
0x1800348e0  push    rdi
0x1800348e1  sub     rsp, 38h
0x1800348e5  mov     ebp, r9d
0x1800348e8  mov     rdi, r8
0x1800348eb  mov     esi, edx
0x1800348ed  mov     rbx, rcx
0x1800348f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348f7  lea     rax, WPP_GLOBAL_Control
0x1800348fe  cmp     rcx, rax
0x180034901  jz      short loc_180034924
0x180034903  test    byte ptr [rcx+1Ch], 2
0x180034907  jz      short loc_180034924
0x180034909  cmp     byte ptr [rcx+19h], 5
0x18003490d  jb      short loc_180034924
0x18003490f  mov     rcx, [rcx+10h]
0x180034913  lea     r8, WPP_6cd65d97da703906276b8bd4a05999a8_Traceguids
0x18003491a  mov     edx, 0Eh
0x18003491f  call    WPP_SF_
0x180034924  test    esi, esi
0x180034926  jnz     short loc_180034981
0x180034928  mov     rdx, [rsp+58h+arg_20]
0x180034930  test    rdi, rdi
0x180034933  jz      short loc_180034965
0x180034935  movups  xmm0, xmmword ptr [rbx]
0x180034938  movups  xmmword ptr [rdx], xmm0
0x18003493b  movups  xmm1, xmmword ptr [rbx+10h]
0x18003493f  movups  xmmword ptr [rdx+10h], xmm1
0x180034943  movups  xmm0, xmmword ptr [rbx+20h]
0x180034947  movups  xmmword ptr [rdx+20h], xmm0
0x18003494b  movups  xmm1, xmmword ptr [rbx+30h]
0x18003494f  movups  xmmword ptr [rdx+30h], xmm1
0x180034953  movups  xmm0, xmmword ptr [rbx+40h]
0x180034957  movups  xmmword ptr [rdx+40h], xmm0
0x18003495b  movsd   xmm1, qword ptr [rbx+50h]
0x180034960  movsd   qword ptr [rdx+50h], xmm1
0x180034965  mov     r9, [rsp+58h+arg_28]
0x18003496d  add     rdx, 8
0x180034971  mov     rcx, [rbx+8]; unsigned __int16 *
0x180034975  mov     r8, rdi
0x180034978  mov     [rsp+58h+var_38], ebp; int
0x18003497c  call    StoreString
0x180034981  add     rsp, 38h
0x180034985  pop     rdi
0x180034986  pop     rsi
0x180034987  pop     rbp
0x180034988  pop     rbx
0x180034989  retn
```
