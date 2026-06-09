# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x18000dc1c`
- end: `0x18000dcd6`
- name: `??0?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e9e8`
- `0x18000edbc`
- `0x180010444`

## callees

- `0x18000354c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  v4 = (_QWORD *)(a1 + 88);
  v4[19] = 0;
  v4[20] = 0;
  memset_0(v4, 0, 0x98u);
  *(_DWORD *)(v3 + 248) = 1;
  *(_QWORD *)(v3 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v3;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  *(_BYTE *)(a1 + 328) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000dc1c  mov     [rsp+arg_0], rbx
0x18000dc21  mov     [rsp+arg_8], rsi
0x18000dc26  push    rdi
0x18000dc27  sub     rsp, 20h
0x18000dc2b  mov     rdi, rcx
0x18000dc2e  lea     rax, ??_7?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000dc35  mov     [rcx], rax
0x18000dc38  lea     rbx, [rcx+8]
0x18000dc3c  xor     esi, esi
0x18000dc3e  mov     [rbx], esi
0x18000dc40  mov     [rbx+4], sil
0x18000dc44  mov     [rbx+40h], sil
0x18000dc48  mov     [rbx+28h], esi
0x18000dc4b  mov     [rbx+30h], rdx
0x18000dc4f  mov     [rbx+38h], rsi
0x18000dc53  mov     [rbx+48h], esi
0x18000dc56  lea     rcx, [rbx+50h]; void *
0x18000dc5a  mov     [rcx+98h], rsi
0x18000dc61  mov     [rcx+0A0h], rsi
0x18000dc68  xor     edx, edx; Val
0x18000dc6a  mov     r8d, 98h; Size
0x18000dc70  call    memset_0
0x18000dc75  mov     dword ptr [rbx+0F8h], 1
0x18000dc7f  xor     eax, eax
0x18000dc81  mov     [rbx+100h], rax
0x18000dc88  mov     [rdi+110h], rbx
0x18000dc8f  mov     [rdi+118h], rsi
0x18000dc96  mov     [rdi+120h], rsi
0x18000dc9d  mov     [rdi+128h], rdi
0x18000dca4  mov     [rdi+130h], rsi
0x18000dcab  mov     [rdi+138h], esi
0x18000dcb1  lea     rax, [rdi+30h]
0x18000dcb5  mov     [rdi+140h], rax
0x18000dcbc  mov     [rdi+148h], sil
0x18000dcc3  mov     rax, rdi
0x18000dcc6  mov     rbx, [rsp+28h+arg_0]
0x18000dccb  mov     rsi, [rsp+28h+arg_8]
0x18000dcd0  add     rsp, 20h
0x18000dcd4  pop     rdi
0x18000dcd5  retn
```
