# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x18000f35c`
- end: `0x18000f416`
- name: `??0?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c0f4`
- `0x18001b6e0`
- `0x18001fb70`
- `0x18001fe10`
- `0x18001ff10`
- `0x180020010`
- `0x1800202f0`

## callees

- `0x1800032dc`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
0x18000f35c  mov     [rsp+arg_0], rbx
0x18000f361  mov     [rsp+arg_8], rsi
0x18000f366  push    rdi
0x18000f367  sub     rsp, 20h
0x18000f36b  mov     rdi, rcx
0x18000f36e  lea     rax, ??_7?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x18000f375  mov     [rcx], rax
0x18000f378  lea     rbx, [rcx+8]
0x18000f37c  xor     esi, esi
0x18000f37e  mov     [rbx], esi
0x18000f380  mov     [rbx+4], sil
0x18000f384  mov     [rbx+40h], sil
0x18000f388  mov     [rbx+28h], esi
0x18000f38b  mov     [rbx+30h], rdx
0x18000f38f  mov     [rbx+38h], rsi
0x18000f393  mov     [rbx+48h], esi
0x18000f396  lea     rcx, [rbx+50h]; void *
0x18000f39a  mov     [rcx+98h], rsi
0x18000f3a1  mov     [rcx+0A0h], rsi
0x18000f3a8  xor     edx, edx; Val
0x18000f3aa  mov     r8d, 98h; Size
0x18000f3b0  call    memset_0
0x18000f3b5  mov     dword ptr [rbx+0F8h], 1
0x18000f3bf  xor     eax, eax
0x18000f3c1  mov     [rbx+100h], rax
0x18000f3c8  mov     [rdi+110h], rbx
0x18000f3cf  mov     [rdi+118h], rsi
0x18000f3d6  mov     [rdi+120h], rsi
0x18000f3dd  mov     [rdi+128h], rdi
0x18000f3e4  mov     [rdi+130h], rsi
0x18000f3eb  mov     [rdi+138h], esi
0x18000f3f1  lea     rax, [rdi+30h]
0x18000f3f5  mov     [rdi+140h], rax
0x18000f3fc  mov     [rdi+148h], sil
0x18000f403  mov     rax, rdi
0x18000f406  mov     rbx, [rsp+28h+arg_0]
0x18000f40b  mov     rsi, [rsp+28h+arg_8]
0x18000f410  add     rsp, 20h
0x18000f414  pop     rdi
0x18000f415  retn
```
