# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x140005204`
- end: `0x1400052be`
- name: `??0?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007ad8`
- `0x14000b0cc`
- `0x14000f2a4`

## callees

- `0x140003ab8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
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
0x140005204  mov     [rsp+arg_0], rbx
0x140005209  mov     [rsp+arg_8], rsi
0x14000520e  push    rdi
0x14000520f  sub     rsp, 20h
0x140005213  mov     rdi, rcx
0x140005216  lea     rax, ??_7?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x14000521d  mov     [rcx], rax
0x140005220  lea     rbx, [rcx+8]
0x140005224  xor     esi, esi
0x140005226  mov     [rbx], esi
0x140005228  mov     [rbx+4], sil
0x14000522c  mov     [rbx+40h], sil
0x140005230  mov     [rbx+28h], esi
0x140005233  mov     [rbx+30h], rdx
0x140005237  mov     [rbx+38h], rsi
0x14000523b  mov     [rbx+48h], esi
0x14000523e  lea     rcx, [rbx+50h]; void *
0x140005242  mov     [rcx+98h], rsi
0x140005249  mov     [rcx+0A0h], rsi
0x140005250  xor     edx, edx; Val
0x140005252  mov     r8d, 98h; Size
0x140005258  call    memset_0
0x14000525d  mov     dword ptr [rbx+0F8h], 1
0x140005267  xor     eax, eax
0x140005269  mov     [rbx+100h], rax
0x140005270  mov     [rdi+110h], rbx
0x140005277  mov     [rdi+118h], rsi
0x14000527e  mov     [rdi+120h], rsi
0x140005285  mov     [rdi+128h], rdi
0x14000528c  mov     [rdi+130h], rsi
0x140005293  mov     [rdi+138h], esi
0x140005299  lea     rax, [rdi+30h]
0x14000529d  mov     [rdi+140h], rax
0x1400052a4  mov     [rdi+148h], sil
0x1400052ab  mov     rax, rdi
0x1400052ae  mov     rbx, [rsp+28h+arg_0]
0x1400052b3  mov     rsi, [rsp+28h+arg_8]
0x1400052b8  add     rsp, 20h
0x1400052bc  pop     rdi
0x1400052bd  retn
```
