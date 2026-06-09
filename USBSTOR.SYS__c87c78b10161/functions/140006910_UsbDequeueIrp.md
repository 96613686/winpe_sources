# UsbDequeueIrp

- ea: `0x140006910`
- end: `0x140006a5b`
- name: `UsbDequeueIrp`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140004ed0`
- `0x14000811c`
- `0x14000dd1c`

## callees

- `0x140006910`
- `0x140006a70`
- `0x140010664`
- `0x140010e74`

## pseudocode

```c
_QWORD *__fastcall UsbDequeueIrp(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  _QWORD *v6; // rsi
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x22u,
      (__int64)WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  while ( *(_DWORD *)(a1 + 4) )
  {
    v6 = 0;
    v7 = (_QWORD *)(a1 + 32);
    if ( (_QWORD *)*v7 != v7 || (PortAvioSchedulerTransferBatch(a1, a2, a3), (_QWORD *)*v7 != v7) )
    {
      v6 = *(_QWORD **)(a1 + 48);
      *(_QWORD *)(a1 + 48) = *v6;
      *(_QWORD *)(a1 + 72) = v6[2] + 1LL;
      v8 = *v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
        __fastfail(3u);
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      v10 = *(_QWORD *)(a1 + 64);
      --*(_DWORD *)(a1 + 56);
      if ( v10 )
        --*(_DWORD *)(v10 + 4);
      if ( *(_QWORD *)(a1 + 48) == a1 + 32 )
        *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 32);
    }
    v4 = v6 - 15;
    if ( _InterlockedExchange64(v6 - 2, 0) )
      goto LABEL_4;
  }
  v4 = 0;
LABEL_4:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140006910  mov     [rsp+arg_10], rbp
0x140006915  push    rdi
0x140006916  sub     rsp, 20h
0x14000691a  mov     rdi, rcx
0x14000691d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006924  lea     rbp, WPP_GLOBAL_Control
0x14000692b  cmp     rcx, rbp
0x14000692e  jnz     loc_1400069F2
0x140006934  mov     [rsp+28h+arg_0], rbx
0x140006939  mov     [rsp+28h+arg_8], rsi
0x14000693e  cmp     dword ptr [rdi+4], 0
0x140006942  jnz     short loc_14000696F
0x140006944  xor     ebx, ebx
0x140006946  mov     rcx, cs:WPP_GLOBAL_Control
0x14000694d  cmp     rcx, rbp
0x140006950  jnz     loc_140006A21
0x140006956  mov     rsi, [rsp+28h+arg_8]
0x14000695b  mov     rax, rbx
0x14000695e  mov     rbx, [rsp+28h+arg_0]
0x140006963  mov     rbp, [rsp+28h+arg_10]
0x140006968  add     rsp, 20h
0x14000696c  pop     rdi
0x14000696d  retn
0x14000696f  xor     esi, esi
0x140006971  lea     rbx, [rdi+20h]
0x140006975  cmp     [rbx], rbx
0x140006978  jnz     short loc_140006987
0x14000697a  mov     rcx, rdi
0x14000697d  call    PortAvioSchedulerTransferBatch
0x140006982  cmp     [rbx], rbx
0x140006985  jz      short loc_1400069DA
0x140006987  mov     rsi, [rbx+10h]
0x14000698b  mov     rax, [rsi]
0x14000698e  mov     [rbx+10h], rax
0x140006992  mov     rax, [rsi+10h]
0x140006996  inc     rax
0x140006999  mov     [rbx+28h], rax
0x14000699d  mov     rcx, [rsi]
0x1400069a0  cmp     [rcx+8], rsi
0x1400069a4  jnz     loc_140006A54
0x1400069aa  mov     rax, [rsi+8]
0x1400069ae  cmp     [rax], rsi
0x1400069b1  jnz     loc_140006A54
0x1400069b7  mov     [rax], rcx
0x1400069ba  mov     [rcx+8], rax
0x1400069be  mov     rax, [rbx+20h]
0x1400069c2  dec     dword ptr [rbx+18h]
0x1400069c5  test    rax, rax
0x1400069c8  jz      short loc_1400069CD
0x1400069ca  dec     dword ptr [rax+4]
0x1400069cd  cmp     [rbx+10h], rbx
0x1400069d1  jnz     short loc_1400069DA
0x1400069d3  mov     rax, [rbx]
0x1400069d6  mov     [rbx+10h], rax
0x1400069da  xor     eax, eax
0x1400069dc  lea     rbx, [rsi-78h]
0x1400069e0  xchg    rax, [rbx+68h]
0x1400069e4  test    rax, rax
0x1400069e7  jnz     loc_140006946
0x1400069ed  jmp     loc_14000693E
0x1400069f2  mov     eax, [rcx+2Ch]
0x1400069f5  test    al, 20h
0x1400069f7  jz      loc_140006934
0x1400069fd  cmp     byte ptr [rcx+29h], 4
0x140006a01  jb      loc_140006934
0x140006a07  mov     rcx, [rcx+18h]
0x140006a0b  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140006a12  mov     edx, 22h ; '"'
0x140006a17  call    WPP_SF_
0x140006a1c  jmp     loc_140006934
0x140006a21  mov     edx, [rcx+2Ch]
0x140006a24  test    dl, 20h
0x140006a27  jz      loc_140006956
0x140006a2d  cmp     byte ptr [rcx+29h], 4
0x140006a31  jb      loc_140006956
0x140006a37  mov     rcx, [rcx+18h]
0x140006a3b  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x140006a42  mov     edx, 23h ; '#'
0x140006a47  mov     r9, rbx
0x140006a4a  call    WPP_SF_q
0x140006a4f  jmp     loc_140006956
0x140006a54  mov     ecx, 3
0x140006a59  int     29h; Win8: RtlFailFast(ecx)
```
