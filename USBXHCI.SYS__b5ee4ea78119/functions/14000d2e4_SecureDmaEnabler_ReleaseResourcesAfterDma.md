# SecureDmaEnabler_ReleaseResourcesAfterDma

- ea: `0x14000d2e4`
- end: `0x14000d389`
- name: `SecureDmaEnabler_ReleaseResourcesAfterDma`
- size: `165`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d190`
- `0x14000d5c0`
- `0x140014d70`
- `0x140026150`
- `0x140026550`

## callees

- `0x14000d2e4`
- `0x140010d40`
- `0x1400110e0`
- `0x14001ad0c`

## import_xrefs

- `ntoskrnl!VslDeleteSecureSection` at `0x14000d31b`
- `ntoskrnl!VslDeleteSecureSection` at `0x14000d31b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d2fc`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d2fc`

## pseudocode

```c
void __fastcall SecureDmaEnabler_ReleaseResourcesAfterDma(__int64 a1, __int64 a2)
{
  char v3; // bp
  _QWORD *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // edx
  int v8; // esi

  if ( *(_DWORD *)a2 == 1 )
  {
    v3 = 0;
    v4 = (_QWORD *)(a1 + 8);
    if ( KeGetCurrentIrql() == 2 )
    {
      Controller_LowerAndTrackIrql(*v4);
      v3 = 1;
    }
    v8 = VslDeleteSecureSection(*(_QWORD *)(a2 + 16), v5, v6);
    if ( v3 )
      Controller_RaiseAndTrackIrql(*v4);
    if ( v8 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 3;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*v4 + 72LL),
        v7,
        18,
        18,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
        v8);
    }
  }
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
}

```

## disassembly

```asm
0x14000d2e4  push    rbx
0x14000d2e6  push    rbp
0x14000d2e7  push    rsi
0x14000d2e8  push    rdi
0x14000d2e9  sub     rsp, 38h
0x14000d2ed  cmp     dword ptr [rdx], 1
0x14000d2f0  mov     rbx, rdx
0x14000d2f3  jnz     short loc_14000D332
0x14000d2f5  xor     bpl, bpl
0x14000d2f8  lea     rdi, [rcx+8]
0x14000d2fc  call    cs:__imp_KeGetCurrentIrql
0x14000d303  nop     dword ptr [rax+rax+00h]
0x14000d308  cmp     al, 2
0x14000d30a  jnz     short loc_14000D317
0x14000d30c  mov     rcx, [rdi]
0x14000d30f  call    Controller_LowerAndTrackIrql
0x14000d314  mov     bpl, 1
0x14000d317  mov     rcx, [rbx+10h]
0x14000d31b  call    cs:__imp_VslDeleteSecureSection
0x14000d322  nop     dword ptr [rax+rax+00h]
0x14000d327  mov     esi, eax
0x14000d329  test    bpl, bpl
0x14000d32c  jnz     short loc_14000D346
0x14000d32e  test    esi, esi
0x14000d330  js      short loc_14000D350
0x14000d332  xorps   xmm0, xmm0
0x14000d335  movups  xmmword ptr [rbx], xmm0
0x14000d338  movups  xmmword ptr [rbx+10h], xmm0
0x14000d33c  add     rsp, 38h
0x14000d340  pop     rdi
0x14000d341  pop     rsi
0x14000d342  pop     rbp
0x14000d343  pop     rbx
0x14000d344  retn
0x14000d346  mov     rcx, [rdi]
0x14000d349  call    Controller_RaiseAndTrackIrql
0x14000d34e  jmp     short loc_14000D32E
0x14000d350  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d357  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d35e  jz      short loc_14000D332
0x14000d360  mov     rcx, [rdi]
0x14000d363  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x14000d36a  mov     r8d, 12h
0x14000d370  mov     [rsp+58h+var_30], esi
0x14000d374  mov     r9d, r8d
0x14000d377  mov     [rsp+58h+var_38], rax
0x14000d37c  mov     dl, 3
0x14000d37e  mov     rcx, [rcx+48h]
0x14000d382  call    WPP_RECORDER_SF_d
0x14000d387  jmp     short loc_14000D332
```
