# Apx::ApfJack::_CreateAndInitialize(_APX_JACK_CONFIG *,Apx::ApfJack * *)

- ea: `0x180025130`
- end: `0x18002520a`
- name: `?_CreateAndInitialize@ApfJack@Apx@@SAJPEAU_APX_JACK_CONFIG@@PEAPEAV12@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _APX_JACK_CONFIG *, struct Apx::ApfJack **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180025310`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x180024c1c`
- `0x180025078`
- `0x180025130`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfJack::_CreateAndInitialize(struct _APX_JACK_CONFIG *a1, struct Apx::ApfJack **a2)
{
  Apx::ApfJack *v4; // rax
  Apx::ApfJack *v5; // rax
  struct Apx::ApfJack *v6; // rdi
  int v7; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfJack *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 && (v5 = (Apx::ApfJack *)Apx::ApfJack::ApfJack(v4), (v6 = v5) != 0) )
  {
    v7 = Apx::ApfJack::Initialize(v5, a1);
    if ( v7 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfJack *, __int64))v6)(v6, 1);
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025130  push    rbx
0x180025132  push    rbp
0x180025133  push    rsi
0x180025134  push    rdi
0x180025135  sub     rsp, 28h
0x180025139  mov     rsi, rdx
0x18002513c  mov     rbx, rcx
0x18002513f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025146  lea     rbp, WPP_GLOBAL_Control
0x18002514d  cmp     rcx, rbp
0x180025150  jz      short loc_180025173
0x180025152  test    byte ptr [rcx+1Ch], 1
0x180025156  jz      short loc_180025173
0x180025158  cmp     byte ptr [rcx+19h], 5
0x18002515c  jb      short loc_180025173
0x18002515e  mov     rcx, [rcx+10h]
0x180025162  lea     r8, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids
0x180025169  mov     edx, 0Ah
0x18002516e  call    WPP_SF_
0x180025173  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002517a  mov     qword ptr [rsi], 0
0x180025181  mov     ecx, 88h; unsigned __int64
0x180025186  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002518b  test    rax, rax
0x18002518e  jz      short loc_1800251CD
0x180025190  mov     rcx, rax; this
0x180025193  call    ??0ApfJack@Apx@@AEAA@XZ; Apx::ApfJack::ApfJack(void)
0x180025198  mov     rdi, rax
0x18002519b  test    rax, rax
0x18002519e  jz      short loc_1800251CD
0x1800251a0  mov     rdx, rbx; struct _APX_JACK_CONFIG *
0x1800251a3  mov     rcx, rax; this
0x1800251a6  call    ?Initialize@ApfJack@Apx@@AEAAJPEAU_APX_JACK_CONFIG@@@Z; Apx::ApfJack::Initialize(_APX_JACK_CONFIG *)
0x1800251ab  mov     ebx, eax
0x1800251ad  test    eax, eax
0x1800251af  js      short loc_1800251B8
0x1800251b1  mov     [rsi], rdi
0x1800251b4  xor     ebx, ebx
0x1800251b6  jmp     short loc_1800251D2
0x1800251b8  mov     rax, [rdi]
0x1800251bb  mov     edx, 1
0x1800251c0  mov     rcx, rdi
0x1800251c3  mov     rax, [rax]
0x1800251c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251cb  jmp     short loc_1800251D2
0x1800251cd  mov     ebx, 8007000Eh
0x1800251d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251d9  cmp     rcx, rbp
0x1800251dc  jz      short loc_1800251FF
0x1800251de  test    byte ptr [rcx+1Ch], 1
0x1800251e2  jz      short loc_1800251FF
0x1800251e4  cmp     byte ptr [rcx+19h], 5
0x1800251e8  jb      short loc_1800251FF
0x1800251ea  mov     rcx, [rcx+10h]
0x1800251ee  lea     r8, WPP_f8163cda866833e145b9bcd9ddfa387c_Traceguids
0x1800251f5  mov     edx, 0Bh
0x1800251fa  call    WPP_SF_
0x1800251ff  mov     eax, ebx
0x180025201  add     rsp, 28h
0x180025205  pop     rdi
0x180025206  pop     rsi
0x180025207  pop     rbp
0x180025208  pop     rbx
0x180025209  retn
```
