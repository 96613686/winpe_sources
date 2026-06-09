# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x14000796c`
- end: `0x140007a30`
- name: `??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007f3c`
- `0x1400093c0`
- `0x14000a8f0`

## callees

- `0x14000369c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
0x14000796c  push    rdi
0x14000796e  sub     rsp, 30h
0x140007972  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000797b  mov     [rsp+38h+arg_0], rbx
0x140007980  mov     [rsp+38h+arg_8], rsi
0x140007985  mov     rdi, rcx
0x140007988  lea     rax, ??_7?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x14000798f  mov     [rcx], rax
0x140007992  lea     rbx, [rcx+8]
0x140007996  xor     esi, esi
0x140007998  mov     [rbx], esi
0x14000799a  mov     [rbx+4], sil
0x14000799e  mov     [rbx+40h], sil
0x1400079a2  mov     [rbx+28h], esi
0x1400079a5  mov     [rbx+30h], rdx
0x1400079a9  mov     [rbx+38h], rsi
0x1400079ad  mov     [rbx+48h], esi
0x1400079b0  lea     rcx, [rbx+50h]; void *
0x1400079b4  mov     [rcx+98h], rsi
0x1400079bb  mov     [rcx+0A0h], rsi
0x1400079c2  xor     edx, edx; Val
0x1400079c4  mov     r8d, 98h; Size
0x1400079ca  call    memset_0
0x1400079cf  mov     dword ptr [rbx+0F8h], 1
0x1400079d9  xor     eax, eax
0x1400079db  mov     [rbx+100h], rax
0x1400079e2  mov     [rdi+110h], rbx
0x1400079e9  mov     [rdi+118h], rsi
0x1400079f0  mov     [rdi+120h], rsi
0x1400079f7  mov     [rdi+128h], rdi
0x1400079fe  mov     [rdi+130h], rsi
0x140007a05  mov     [rdi+138h], esi
0x140007a0b  lea     rax, [rdi+30h]
0x140007a0f  mov     [rdi+140h], rax
0x140007a16  mov     [rdi+148h], sil
0x140007a1d  mov     rax, rdi
0x140007a20  mov     rbx, [rsp+38h+arg_0]
0x140007a25  mov     rsi, [rsp+38h+arg_8]
0x140007a2a  add     rsp, 30h
0x140007a2e  pop     rdi
0x140007a2f  retn
```
