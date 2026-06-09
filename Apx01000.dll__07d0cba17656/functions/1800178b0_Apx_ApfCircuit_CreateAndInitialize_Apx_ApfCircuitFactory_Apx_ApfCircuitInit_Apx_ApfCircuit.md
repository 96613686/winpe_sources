# Apx::ApfCircuit::_CreateAndInitialize(Apx::ApfCircuitFactory *,Apx::ApfCircuitInit *,Apx::ApfCircuit * *)

- ea: `0x1800178b0`
- end: `0x1800179a8`
- name: `?_CreateAndInitialize@ApfCircuit@Apx@@SAJPEAVApfCircuitFactory@2@PEAVApfCircuitInit@2@PEAPEAV12@@Z`
- size: `248`
- prototype: `__int64 __fastcall(struct Apx::ApfCircuitFactory *, struct Apx::ApfCircuitInit *, struct Apx::ApfCircuit **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180019420`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x1800164bc`
- `0x180017278`
- `0x1800178b0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfCircuit::_CreateAndInitialize(
        struct Apx::ApfCircuitFactory *a1,
        struct Apx::ApfCircuitInit *a2,
        struct Apx::ApfCircuit **a3)
{
  Apx::ApfCircuit *v6; // rax
  Apx::ApfCircuit *v7; // rax
  struct Apx::ApfCircuit *v8; // rdi
  int v9; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  *a3 = 0;
  v6 = (Apx::ApfCircuit *)operator new(0x278u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 && (v7 = (Apx::ApfCircuit *)Apx::ApfCircuit::ApfCircuit(v6), (v8 = v7) != 0) )
  {
    v9 = Apx::ApfCircuit::Initialize(v7, a1, a2);
    if ( v9 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfCircuit *, __int64))v8)(v8, 1);
    }
    else
    {
      *a3 = v8;
      v9 = 0;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800178b0  mov     [rsp+arg_0], rbx
0x1800178b5  mov     [rsp+arg_8], rbp
0x1800178ba  push    rsi
0x1800178bb  push    rdi
0x1800178bc  push    r14
0x1800178be  sub     rsp, 20h
0x1800178c2  mov     rsi, r8
0x1800178c5  mov     rbx, rdx
0x1800178c8  mov     rbp, rcx
0x1800178cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178d2  lea     r14, WPP_GLOBAL_Control
0x1800178d9  cmp     rcx, r14
0x1800178dc  jz      short loc_1800178FF
0x1800178de  test    byte ptr [rcx+1Ch], 1
0x1800178e2  jz      short loc_1800178FF
0x1800178e4  cmp     byte ptr [rcx+19h], 5
0x1800178e8  jb      short loc_1800178FF
0x1800178ea  mov     rcx, [rcx+10h]
0x1800178ee  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x1800178f5  mov     edx, 0Ah
0x1800178fa  call    WPP_SF_
0x1800178ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017906  mov     qword ptr [rsi], 0
0x18001790d  mov     ecx, 278h; unsigned __int64
0x180017912  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017917  mov     [rsp+38h+arg_10], rax
0x18001791c  test    rax, rax
0x18001791f  jz      short loc_180017961
0x180017921  mov     rcx, rax; this
0x180017924  call    ??0ApfCircuit@Apx@@AEAA@XZ; Apx::ApfCircuit::ApfCircuit(void)
0x180017929  mov     rdi, rax
0x18001792c  test    rax, rax
0x18001792f  jz      short loc_180017961
0x180017931  mov     r8, rbx; struct Apx::ApfCircuitInit *
0x180017934  mov     rdx, rbp; struct Apx::ApfCircuitFactory *
0x180017937  mov     rcx, rax; this
0x18001793a  call    ?Initialize@ApfCircuit@Apx@@AEAAJPEAVApfCircuitFactory@2@PEAVApfCircuitInit@2@@Z; Apx::ApfCircuit::Initialize(Apx::ApfCircuitFactory *,Apx::ApfCircuitInit *)
0x18001793f  mov     ebx, eax
0x180017941  test    eax, eax
0x180017943  js      short loc_18001794C
0x180017945  mov     [rsi], rdi
0x180017948  xor     ebx, ebx
0x18001794a  jmp     short loc_180017966
0x18001794c  mov     rax, [rdi]
0x18001794f  mov     edx, 1
0x180017954  mov     rcx, rdi
0x180017957  mov     rax, [rax]
0x18001795a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001795f  jmp     short loc_180017966
0x180017961  mov     ebx, 8007000Eh
0x180017966  mov     rcx, cs:WPP_GLOBAL_Control
0x18001796d  cmp     rcx, r14
0x180017970  jz      short loc_180017993
0x180017972  test    byte ptr [rcx+1Ch], 1
0x180017976  jz      short loc_180017993
0x180017978  cmp     byte ptr [rcx+19h], 5
0x18001797c  jb      short loc_180017993
0x18001797e  mov     rcx, [rcx+10h]
0x180017982  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x180017989  mov     edx, 0Bh
0x18001798e  call    WPP_SF_
0x180017993  mov     rbp, [rsp+38h+arg_8]
0x180017998  mov     eax, ebx
0x18001799a  mov     rbx, [rsp+38h+arg_0]
0x18001799f  add     rsp, 20h
0x1800179a3  pop     r14
0x1800179a5  pop     rdi
0x1800179a6  pop     rsi
0x1800179a7  retn
```
