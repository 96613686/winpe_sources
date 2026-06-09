# EaSignalEventImpl

- ea: `0x18006b128`
- end: `0x18006b2a2`
- name: `EaSignalEventImpl`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18003429c`

## callees

- `0x180003a60`
- `0x180004998`
- `0x18006b128`
- `0x18006b2a8`

## import_xrefs

- `ntdll!ZwUpdateWnfStateData` at `0x18006b25a`
- `ntdll!ZwUpdateWnfStateData` at `0x18006b25a`
- `ntdll!RtlAllocateHeap` at `0x18006b1e1`
- `ntdll!RtlAllocateHeap` at `0x18006b1e1`
- `ntdll!RtlFreeHeap` at `0x18006b279`
- `ntdll!RtlFreeHeap` at `0x18006b279`

## pseudocode

```c
__int64 __fastcall EaSignalEventImpl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int128 *a5, __int64 a6)
{
  __int128 v6; // xmm0
  int v7; // eax
  unsigned int updated; // ebx
  size_t v9; // rbx
  PVOID Heap; // rax
  void *v11; // rdi
  int v12; // edx
  int v13; // ecx
  __int64 v14; // r8
  SIZE_T Size; // [rsp+40h] [rbp-29h] BYREF
  int v17[2]; // [rsp+48h] [rbp-21h] BYREF
  _OWORD *v18; // [rsp+50h] [rbp-19h]
  __int64 v19; // [rsp+58h] [rbp-11h]
  __int64 v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+68h] [rbp-1h]
  int v22; // [rsp+6Ch] [rbp+3h]
  __int64 v23; // [rsp+70h] [rbp+7h] BYREF
  _OWORD v24[2]; // [rsp+78h] [rbp+Fh] BYREF

  *(_QWORD *)v17 = 0;
  v18 = 0;
  v19 = 0;
  v22 = 0;
  memset(v24, 0, sizeof(v24));
  if ( a5 )
  {
    v6 = *a5;
    v18 = v24;
    v24[0] = v6;
  }
  v20 = a6;
  v21 = 96;
  v23 = a1;
  LODWORD(Size) = 0;
  v7 = EapSignalContentPrepareEventForPublishing(a1, a6, (int)v17, (int)&Size, 0);
  updated = v7;
  if ( v7 == -1073741789 )
  {
    v9 = (unsigned int)Size;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    v11 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    memset_0(Heap, 0, v9);
    EapSignalContentPrepareEventForPublishing(v13, v12, (int)v17, (int)&Size, v11);
    v14 = (unsigned int)Size;
  }
  else
  {
    v11 = 0;
    v14 = 0;
    if ( v7 < 0 )
      return updated;
  }
  if ( (unsigned int)v14 <= 0x1000 )
    updated = ZwUpdateWnfStateData(&v23, v11, v14, 0, 0, 0, 0);
  else
    updated = -2147483643;
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return updated;
}

```

## disassembly

```asm
0x18006b128  mov     [rsp-8+arg_8], rbx
0x18006b12d  mov     [rsp-8+arg_10], rdi
0x18006b132  push    rbp
0x18006b133  lea     rbp, [rsp-37h]
0x18006b138  sub     rsp, 0A0h
0x18006b13f  mov     rax, cs:__security_cookie
0x18006b146  xor     rax, rsp
0x18006b149  mov     [rbp+37h+var_8], rax
0x18006b14d  mov     rax, [rbp+37h+arg_20]
0x18006b151  xorps   xmm0, xmm0
0x18006b154  mov     rdx, qword ptr [rbp+37h+arg_28]; int
0x18006b158  xorps   xmm1, xmm1
0x18006b15b  mov     qword ptr [rbp+37h+var_58], 0
0x18006b163  mov     [rbp+37h+var_50], 0
0x18006b16b  mov     [rbp+37h+var_48], 0
0x18006b173  mov     [rbp+37h+var_34], 0
0x18006b17a  movups  [rbp+37h+var_18], xmm0
0x18006b17e  movups  [rbp+37h+var_28], xmm1
0x18006b182  test    rax, rax
0x18006b185  jz      short loc_18006B197
0x18006b187  movaps  xmm0, xmmword ptr [rax]
0x18006b18a  lea     rax, [rbp+37h+var_28]
0x18006b18e  mov     [rbp+37h+var_50], rax
0x18006b192  movdqu  [rbp+37h+var_28], xmm0
0x18006b197  lea     r9, [rbp+37h+Size]; int
0x18006b19b  mov     [rbp+37h+var_40], rdx
0x18006b19f  lea     r8, [rbp+37h+var_58]; int
0x18006b1a3  mov     [rbp+37h+var_38], 60h ; '`'
0x18006b1aa  mov     [rbp+37h+var_30], rcx
0x18006b1ae  mov     dword ptr [rbp+37h+Size], 0
0x18006b1b5  mov     [rsp+0A0h+var_80], 0; void *
0x18006b1be  call    EapSignalContentPrepareEventForPublishing
0x18006b1c3  mov     ebx, eax
0x18006b1c5  cmp     eax, 0C0000023h
0x18006b1ca  jnz     short loc_18006B21E
0x18006b1cc  mov     rcx, gs:60h
0x18006b1d5  xor     edx, edx; Flags
0x18006b1d7  mov     ebx, dword ptr [rbp+37h+Size]
0x18006b1da  mov     r8d, ebx; Size
0x18006b1dd  mov     rcx, [rcx+30h]; HeapHandle
0x18006b1e1  call    cs:__imp_RtlAllocateHeap
0x18006b1e7  mov     rdi, rax
0x18006b1ea  test    rax, rax
0x18006b1ed  jnz     short loc_18006B1F9
0x18006b1ef  mov     ebx, 0C0000017h
0x18006b1f4  jmp     loc_18006B27F
0x18006b1f9  mov     r8, rbx; Size
0x18006b1fc  xor     edx, edx; Val
0x18006b1fe  mov     rcx, rdi; void *
0x18006b201  call    memset_0
0x18006b206  lea     r9, [rbp+37h+Size]; int
0x18006b20a  mov     [rsp+0A0h+var_80], rdi; void *
0x18006b20f  lea     r8, [rbp+37h+var_58]; int
0x18006b213  call    EapSignalContentPrepareEventForPublishing
0x18006b218  mov     r8d, dword ptr [rbp+37h+Size]
0x18006b21c  jmp     short loc_18006B227
0x18006b21e  xor     edi, edi
0x18006b220  xor     r8d, r8d
0x18006b223  test    eax, eax
0x18006b225  js      short loc_18006B27F
0x18006b227  cmp     r8d, 1000h
0x18006b22e  jbe     short loc_18006B237
0x18006b230  mov     ebx, 80000005h
0x18006b235  jmp     short loc_18006B262
0x18006b237  mov     [rsp+0A0h+var_70], 0
0x18006b23f  lea     rcx, [rbp+37h+var_30]
0x18006b243  mov     [rsp+0A0h+var_78], 0
0x18006b24b  xor     r9d, r9d
0x18006b24e  mov     rdx, rdi
0x18006b251  mov     [rsp+0A0h+var_80], 0
0x18006b25a  call    cs:__imp_ZwUpdateWnfStateData
0x18006b260  mov     ebx, eax
0x18006b262  test    rdi, rdi
0x18006b265  jz      short loc_18006B27F
0x18006b267  mov     rcx, gs:60h
0x18006b270  mov     r8, rdi; P
0x18006b273  xor     edx, edx; Flags
0x18006b275  mov     rcx, [rcx+30h]; HeapHandle
0x18006b279  call    cs:__imp_RtlFreeHeap
0x18006b27f  mov     eax, ebx
0x18006b281  mov     rcx, [rbp+37h+var_8]
0x18006b285  xor     rcx, rsp; StackCookie
0x18006b288  call    __security_check_cookie
0x18006b28d  lea     r11, [rsp+0A0h+var_s0]
0x18006b295  mov     rbx, [r11+18h]
0x18006b299  mov     rdi, [r11+20h]
0x18006b29d  mov     rsp, r11
0x18006b2a0  pop     rbp
0x18006b2a1  retn
```
