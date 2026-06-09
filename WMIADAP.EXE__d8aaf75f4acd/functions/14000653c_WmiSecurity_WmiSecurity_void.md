# WmiSecurity::WmiSecurity(void)

- ea: `0x14000653c`
- end: `0x140006615`
- name: `??0WmiSecurity@@QEAA@XZ`
- size: `217`
- prototype: `WmiSecurity *__fastcall(WmiSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000661c`

## callees

- `0x14000653c`
- `0x140006b2c`
- `0x140007024`
- `0x140007068`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400065dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400065fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400065dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400065fc`

## pseudocode

```c
WmiSecurity *__fastcall WmiSecurity::WmiSecurity(WmiSecurity *this)
{
  void **v1; // rdi
  int v2; // esi
  WmiSecurity *v3; // rcx
  void *v4; // rdx
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  v1 = (void **)this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  v2 = 0;
  if ( (int)WmiSecurity::Initialize(this, L"O:BAG:BAD:(A;NP;GA;;;BA)(A;NP;GA;;;LA)(A;NP;GA;;;SY)", (void **)this) >= 0 )
  {
    v2 = 1;
    hMem = 0;
    if ( (int)WmiSecurity::Initialize(
                v3,
                L"O:BAG:BAD:(A;NP;CC;;;BA)(A;NP;CC;;;LA)(A;NP;CC;;;SY)(A;NP;CC;;;NS)(A;NP;CC;;;LS)",
                &hMem) >= 0 )
    {
      try
      {
        if ( WmiSecurity::MakeAbsolute((WmiSecurity *)v1, hMem, v1 + 1) < 0 )
          WmiSecurity::DestructAbsoluteSD((WmiSecurity *)v1, v4);
        LocalFree(hMem);
      }
      catch ( ... )
      {
        v1 = (void **)this;
        v2 = 1;
      }
    }
  }
  if ( !v2 && *v1 )
  {
    LocalFree(*v1);
    *v1 = 0;
  }
  return (WmiSecurity *)v1;
}

```

## disassembly

```asm
0x14000653c  mov     [rsp+arg_0], rcx
0x140006541  push    rsi
0x140006542  push    rdi
0x140006543  push    r14
0x140006545  sub     rsp, 20h
0x140006549  mov     rdi, rcx
0x14000654c  mov     qword ptr [rcx], 0
0x140006553  mov     qword ptr [rcx+8], 0
0x14000655b  mov     qword ptr [rcx+10h], 0
0x140006563  mov     qword ptr [rcx+18h], 0
0x14000656b  mov     qword ptr [rcx+20h], 0
0x140006573  mov     qword ptr [rcx+28h], 0
0x14000657b  xor     esi, esi
0x14000657d  mov     [rsp+38h+arg_8], esi
0x140006581  mov     r8, rcx; void **
0x140006584  lea     rdx, aOBagBadANpGaBa; "O:BAG:BAD:(A;NP;GA;;;BA)(A;NP;GA;;;LA)("...
0x14000658b  call    ?Initialize@WmiSecurity@@AEAAJPEBGPEAPEAX@Z; WmiSecurity::Initialize(ushort const *,void * *)
0x140006590  test    eax, eax
0x140006592  js      short loc_1400065E4
0x140006594  mov     esi, 1
0x140006599  mov     [rsp+38h+arg_8], esi
0x14000659d  mov     [rsp+38h+hMem], 0
0x1400065a6  lea     r8, [rsp+38h+hMem]; void **
0x1400065ab  lea     rdx, aOBagBadANpCcBa; "O:BAG:BAD:(A;NP;CC;;;BA)(A;NP;CC;;;LA)("...
0x1400065b2  call    ?Initialize@WmiSecurity@@AEAAJPEBGPEAPEAX@Z; WmiSecurity::Initialize(ushort const *,void * *)
0x1400065b7  test    eax, eax
0x1400065b9  js      short loc_1400065E4
0x1400065bb  lea     r8, [rdi+8]; void **
0x1400065bf  mov     rdx, [rsp+38h+hMem]; void *
0x1400065c4  mov     rcx, rdi; this
0x1400065c7  call    ?MakeAbsolute@WmiSecurity@@AEAAJPEAXPEAPEAX@Z; WmiSecurity::MakeAbsolute(void *,void * *)
0x1400065cc  test    eax, eax
0x1400065ce  jns     short loc_1400065D8
0x1400065d0  mov     rcx, rdi; this
0x1400065d3  call    ?DestructAbsoluteSD@WmiSecurity@@AEAAXPEAX@Z; WmiSecurity::DestructAbsoluteSD(void *)
0x1400065d8  mov     rcx, [rsp+38h+hMem]; hMem
0x1400065dd  call    cs:__imp_LocalFree
0x1400065e3  nop
0x1400065e4  jmp     short loc_1400065EF
0x1400065e6  mov     rdi, [rsp+38h+arg_0]
0x1400065eb  mov     esi, [rsp+38h+arg_8]
0x1400065ef  test    esi, esi
0x1400065f1  jnz     short loc_140006609
0x1400065f3  cmp     qword ptr [rdi], 0
0x1400065f7  jz      short loc_140006609
0x1400065f9  mov     rcx, [rdi]; hMem
0x1400065fc  call    cs:__imp_LocalFree
0x140006602  mov     qword ptr [rdi], 0
0x140006609  mov     rax, rdi
0x14000660c  add     rsp, 20h
0x140006610  pop     r14
0x140006612  pop     rdi
0x140006613  pop     rsi
0x140006614  retn
```
