# Apx::ApfPin::_CreateAndInitialize(_APX_PIN_CONFIG *,Apx::ApfPin * *)

- ea: `0x180023274`
- end: `0x18002337e`
- name: `?_CreateAndInitialize@ApfPin@Apx@@SAJPEAU_APX_PIN_CONFIG@@PEAPEAV12@@Z`
- size: `266`
- prototype: `__int64 __fastcall(struct _APX_PIN_CONFIG *, struct Apx::ApfPin **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800246d0`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18002267c`
- `0x180022e5c`
- `0x180023274`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfPin::_CreateAndInitialize(struct _APX_PIN_CONFIG *a1, struct Apx::ApfPin **a2)
{
  Apx::ApfPin *v4; // rax
  Apx::ApfPin *v5; // rax
  struct Apx::ApfPin *v6; // rdi
  int v7; // ebx
  _QWORD *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  }
  *a2 = 0;
  v4 = (Apx::ApfPin *)operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    v5 = (Apx::ApfPin *)Apx::ApfPin::ApfPin(v4);
    v6 = v5;
    if ( v5 )
    {
      v7 = Apx::ApfPin::Initialize(v5, a1);
      if ( v7 < 0 )
      {
        (**(void (__fastcall ***)(struct Apx::ApfPin *, __int64))v6)(v6, 1);
      }
      else
      {
        *a2 = v6;
        v7 = 0;
      }
      goto LABEL_14;
    }
  }
  v7 = -2147024882;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
LABEL_14:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_(v8[2], 12, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023274  push    rbx
0x180023276  push    rbp
0x180023277  push    rsi
0x180023278  push    rdi
0x180023279  sub     rsp, 28h
0x18002327d  mov     rsi, rdx
0x180023280  mov     rbx, rcx
0x180023283  mov     rcx, cs:WPP_GLOBAL_Control
0x18002328a  lea     rbp, WPP_GLOBAL_Control
0x180023291  cmp     rcx, rbp
0x180023294  jz      short loc_1800232B7
0x180023296  test    byte ptr [rcx+1Ch], 1
0x18002329a  jz      short loc_1800232B7
0x18002329c  cmp     byte ptr [rcx+19h], 5
0x1800232a0  jb      short loc_1800232B7
0x1800232a2  mov     rcx, [rcx+10h]
0x1800232a6  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x1800232ad  mov     edx, 0Ah
0x1800232b2  call    WPP_SF_
0x1800232b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800232be  mov     qword ptr [rsi], 0
0x1800232c5  mov     ecx, 0A0h; unsigned __int64
0x1800232ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800232cf  test    rax, rax
0x1800232d2  jz      short loc_180023311
0x1800232d4  mov     rcx, rax; this
0x1800232d7  call    ??0ApfPin@Apx@@AEAA@XZ; Apx::ApfPin::ApfPin(void)
0x1800232dc  mov     rdi, rax
0x1800232df  test    rax, rax
0x1800232e2  jz      short loc_180023311
0x1800232e4  mov     rdx, rbx; struct _APX_PIN_CONFIG *
0x1800232e7  mov     rcx, rax; this
0x1800232ea  call    ?Initialize@ApfPin@Apx@@AEAAJPEAU_APX_PIN_CONFIG@@@Z; Apx::ApfPin::Initialize(_APX_PIN_CONFIG *)
0x1800232ef  mov     ebx, eax
0x1800232f1  test    eax, eax
0x1800232f3  js      short loc_1800232FC
0x1800232f5  mov     [rsi], rdi
0x1800232f8  xor     ebx, ebx
0x1800232fa  jmp     short loc_180023346
0x1800232fc  mov     rax, [rdi]
0x1800232ff  mov     edx, 1
0x180023304  mov     rcx, rdi
0x180023307  mov     rax, [rax]
0x18002330a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002330f  jmp     short loc_180023346
0x180023311  mov     ebx, 8007000Eh
0x180023316  mov     rcx, cs:WPP_GLOBAL_Control
0x18002331d  cmp     rcx, rbp
0x180023320  jz      short loc_180023373
0x180023322  test    byte ptr [rcx+1Ch], 20h
0x180023326  jz      short loc_18002334D
0x180023328  cmp     byte ptr [rcx+19h], 2
0x18002332c  jb      short loc_18002334D
0x18002332e  mov     rcx, [rcx+10h]
0x180023332  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x180023339  mov     edx, 0Bh
0x18002333e  mov     r9d, ebx
0x180023341  call    WPP_SF_d
0x180023346  mov     rcx, cs:WPP_GLOBAL_Control
0x18002334d  cmp     rcx, rbp
0x180023350  jz      short loc_180023373
0x180023352  test    byte ptr [rcx+1Ch], 1
0x180023356  jz      short loc_180023373
0x180023358  cmp     byte ptr [rcx+19h], 5
0x18002335c  jb      short loc_180023373
0x18002335e  mov     rcx, [rcx+10h]
0x180023362  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x180023369  mov     edx, 0Ch
0x18002336e  call    WPP_SF_
0x180023373  mov     eax, ebx
0x180023375  add     rsp, 28h
0x180023379  pop     rdi
0x18002337a  pop     rsi
0x18002337b  pop     rbp
0x18002337c  pop     rbx
0x18002337d  retn
```
