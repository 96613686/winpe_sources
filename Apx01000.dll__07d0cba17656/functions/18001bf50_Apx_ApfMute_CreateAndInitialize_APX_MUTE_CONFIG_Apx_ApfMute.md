# Apx::ApfMute::_CreateAndInitialize(_APX_MUTE_CONFIG *,Apx::ApfMute * *)

- ea: `0x18001bf50`
- end: `0x18001c02a`
- name: `?_CreateAndInitialize@ApfMute@Apx@@SAJPEAU_APX_MUTE_CONFIG@@PEAPEAV12@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _APX_MUTE_CONFIG *, struct Apx::ApfMute **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001c400`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18001bbdc`
- `0x18001be94`
- `0x18001bf50`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfMute::_CreateAndInitialize(struct _APX_MUTE_CONFIG *a1, struct Apx::ApfMute **a2)
{
  Apx::ApfMute *v4; // rax
  Apx::ApfMute *v5; // rax
  struct Apx::ApfMute *v6; // rdi
  int v7; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfMute *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 && (v5 = (Apx::ApfMute *)Apx::ApfMute::ApfMute(v4), (v6 = v5) != 0) )
  {
    v7 = Apx::ApfMute::Initialize(v5, a1);
    if ( v7 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfMute *, __int64))v6)(v6, 1);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001bf50  push    rbx
0x18001bf52  push    rbp
0x18001bf53  push    rsi
0x18001bf54  push    rdi
0x18001bf55  sub     rsp, 28h
0x18001bf59  mov     rsi, rdx
0x18001bf5c  mov     rbx, rcx
0x18001bf5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf66  lea     rbp, WPP_GLOBAL_Control
0x18001bf6d  cmp     rcx, rbp
0x18001bf70  jz      short loc_18001BF93
0x18001bf72  test    byte ptr [rcx+1Ch], 1
0x18001bf76  jz      short loc_18001BF93
0x18001bf78  cmp     byte ptr [rcx+19h], 5
0x18001bf7c  jb      short loc_18001BF93
0x18001bf7e  mov     rcx, [rcx+10h]
0x18001bf82  lea     r8, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids
0x18001bf89  mov     edx, 0Ah
0x18001bf8e  call    WPP_SF_
0x18001bf93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bf9a  mov     qword ptr [rsi], 0
0x18001bfa1  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001bfa6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bfab  test    rax, rax
0x18001bfae  jz      short loc_18001BFED
0x18001bfb0  mov     rcx, rax; this
0x18001bfb3  call    ??0ApfMute@Apx@@AEAA@XZ; Apx::ApfMute::ApfMute(void)
0x18001bfb8  mov     rdi, rax
0x18001bfbb  test    rax, rax
0x18001bfbe  jz      short loc_18001BFED
0x18001bfc0  mov     rdx, rbx; struct _APX_MUTE_CONFIG *
0x18001bfc3  mov     rcx, rax; this
0x18001bfc6  call    ?Initialize@ApfMute@Apx@@AEAAJPEAU_APX_MUTE_CONFIG@@@Z; Apx::ApfMute::Initialize(_APX_MUTE_CONFIG *)
0x18001bfcb  mov     ebx, eax
0x18001bfcd  test    eax, eax
0x18001bfcf  js      short loc_18001BFD8
0x18001bfd1  mov     [rsi], rdi
0x18001bfd4  xor     ebx, ebx
0x18001bfd6  jmp     short loc_18001BFF2
0x18001bfd8  mov     rax, [rdi]
0x18001bfdb  mov     edx, 1
0x18001bfe0  mov     rcx, rdi
0x18001bfe3  mov     rax, [rax]
0x18001bfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfeb  jmp     short loc_18001BFF2
0x18001bfed  mov     ebx, 8007000Eh
0x18001bff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bff9  cmp     rcx, rbp
0x18001bffc  jz      short loc_18001C01F
0x18001bffe  test    byte ptr [rcx+1Ch], 1
0x18001c002  jz      short loc_18001C01F
0x18001c004  cmp     byte ptr [rcx+19h], 5
0x18001c008  jb      short loc_18001C01F
0x18001c00a  mov     rcx, [rcx+10h]
0x18001c00e  lea     r8, WPP_64ae85588b933d5fc12e048f7b1b1b84_Traceguids
0x18001c015  mov     edx, 0Bh
0x18001c01a  call    WPP_SF_
0x18001c01f  mov     eax, ebx
0x18001c021  add     rsp, 28h
0x18001c025  pop     rdi
0x18001c026  pop     rsi
0x18001c027  pop     rbp
0x18001c028  pop     rbx
0x18001c029  retn
```
