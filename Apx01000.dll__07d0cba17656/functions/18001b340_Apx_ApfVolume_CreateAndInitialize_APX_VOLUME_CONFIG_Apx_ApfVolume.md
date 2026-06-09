# Apx::ApfVolume::_CreateAndInitialize(_APX_VOLUME_CONFIG *,Apx::ApfVolume * *)

- ea: `0x18001b340`
- end: `0x18001b41a`
- name: `?_CreateAndInitialize@ApfVolume@Apx@@SAJPEAU_APX_VOLUME_CONFIG@@PEAPEAV12@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _APX_VOLUME_CONFIG *, struct Apx::ApfVolume **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b830`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18001afc4`
- `0x18001b274`
- `0x18001b340`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfVolume::_CreateAndInitialize(struct _APX_VOLUME_CONFIG *a1, struct Apx::ApfVolume **a2)
{
  Apx::ApfVolume *v4; // rax
  Apx::ApfVolume *v5; // rax
  struct Apx::ApfVolume *v6; // rdi
  int v7; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfVolume *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 && (v5 = (Apx::ApfVolume *)Apx::ApfVolume::ApfVolume(v4), (v6 = v5) != 0) )
  {
    v7 = Apx::ApfVolume::Initialize(v5, a1);
    if ( v7 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfVolume *, __int64))v6)(v6, 1);
    }
    else
    {
      *a2 = v6;
      v7 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b340  push    rbx
0x18001b342  push    rbp
0x18001b343  push    rsi
0x18001b344  push    rdi
0x18001b345  sub     rsp, 28h
0x18001b349  mov     rsi, rdx
0x18001b34c  mov     rbx, rcx
0x18001b34f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b356  lea     rbp, WPP_GLOBAL_Control
0x18001b35d  cmp     rcx, rbp
0x18001b360  jz      short loc_18001B383
0x18001b362  test    byte ptr [rcx+1Ch], 1
0x18001b366  jz      short loc_18001B383
0x18001b368  cmp     byte ptr [rcx+19h], 5
0x18001b36c  jb      short loc_18001B383
0x18001b36e  mov     rcx, [rcx+10h]
0x18001b372  lea     r8, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids
0x18001b379  mov     edx, 0Ah
0x18001b37e  call    WPP_SF_
0x18001b383  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b38a  mov     qword ptr [rsi], 0
0x18001b391  mov     ecx, 70h ; 'p'; unsigned __int64
0x18001b396  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b39b  test    rax, rax
0x18001b39e  jz      short loc_18001B3DD
0x18001b3a0  mov     rcx, rax; this
0x18001b3a3  call    ??0ApfVolume@Apx@@AEAA@XZ; Apx::ApfVolume::ApfVolume(void)
0x18001b3a8  mov     rdi, rax
0x18001b3ab  test    rax, rax
0x18001b3ae  jz      short loc_18001B3DD
0x18001b3b0  mov     rdx, rbx; struct _APX_VOLUME_CONFIG *
0x18001b3b3  mov     rcx, rax; this
0x18001b3b6  call    ?Initialize@ApfVolume@Apx@@AEAAJPEAU_APX_VOLUME_CONFIG@@@Z; Apx::ApfVolume::Initialize(_APX_VOLUME_CONFIG *)
0x18001b3bb  mov     ebx, eax
0x18001b3bd  test    eax, eax
0x18001b3bf  js      short loc_18001B3C8
0x18001b3c1  mov     [rsi], rdi
0x18001b3c4  xor     ebx, ebx
0x18001b3c6  jmp     short loc_18001B3E2
0x18001b3c8  mov     rax, [rdi]
0x18001b3cb  mov     edx, 1
0x18001b3d0  mov     rcx, rdi
0x18001b3d3  mov     rax, [rax]
0x18001b3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3db  jmp     short loc_18001B3E2
0x18001b3dd  mov     ebx, 8007000Eh
0x18001b3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3e9  cmp     rcx, rbp
0x18001b3ec  jz      short loc_18001B40F
0x18001b3ee  test    byte ptr [rcx+1Ch], 1
0x18001b3f2  jz      short loc_18001B40F
0x18001b3f4  cmp     byte ptr [rcx+19h], 5
0x18001b3f8  jb      short loc_18001B40F
0x18001b3fa  mov     rcx, [rcx+10h]
0x18001b3fe  lea     r8, WPP_148a2d0fd9843186e17fb739fb0326db_Traceguids
0x18001b405  mov     edx, 0Bh
0x18001b40a  call    WPP_SF_
0x18001b40f  mov     eax, ebx
0x18001b411  add     rsp, 28h
0x18001b415  pop     rdi
0x18001b416  pop     rsi
0x18001b417  pop     rbp
0x18001b418  pop     rbx
0x18001b419  retn
```
