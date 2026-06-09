# Apx::ApfPin::~ApfPin(void)

- ea: `0x180022770`
- end: `0x1800228c8`
- name: `??1ApfPin@Apx@@EEAA@XZ`
- size: `344`
- prototype: `void __fastcall(Apx::ApfPin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800228d0`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000d2f0`
- `0x180022770`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022880`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022880`

## pseudocode

```c
void __fastcall Apx::ApfPin::~ApfPin(Apx::ApfPin *this)
{
  _QWORD **v2; // rsi
  _QWORD *v3; // rdi
  _QWORD *v4; // rax
  _QWORD **v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rsi

  *(_QWORD *)this = &Apx::ApfPin::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  }
  v2 = (_QWORD **)((char *)this + 104);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
LABEL_16:
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~v3[4]);
    operator delete(v3, (const struct std::nothrow_t *)0x28);
  }
  v5 = (_QWORD **)((char *)this + 120);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    if ( (_QWORD **)v6[1] != v5 )
      goto LABEL_16;
    v7 = (_QWORD *)*v6;
    if ( *(_QWORD **)(*v6 + 8LL) != v6 )
      goto LABEL_16;
    *v5 = v7;
    v8 = (void (__fastcall ***)(_QWORD, __int64))(v6 - 7);
    v7[1] = v5;
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~(unsigned __int64)(v6 - 7));
    if ( v8 )
      (**v8)(v8, 1);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b80f8302e70934d41d7f826282614d49_Traceguids);
  }
  *(_QWORD *)this = &Apx::ApfObject::`vftable';
}

```

## disassembly

```asm
0x180022770  push    rbx
0x180022772  push    rbp
0x180022773  push    rsi
0x180022774  push    rdi
0x180022775  push    r14
0x180022777  sub     rsp, 30h
0x18002277b  lea     rax, ??_7ApfPin@Apx@@6B@; const Apx::ApfPin::`vftable'
0x180022782  mov     rbx, rcx
0x180022785  mov     [rcx], rax
0x180022788  mov     rcx, cs:WPP_GLOBAL_Control
0x18002278f  lea     rbp, WPP_GLOBAL_Control
0x180022796  cmp     rcx, rbp
0x180022799  jz      short loc_1800227BC
0x18002279b  test    byte ptr [rcx+1Ch], 1
0x18002279f  jz      short loc_1800227BC
0x1800227a1  cmp     byte ptr [rcx+19h], 5
0x1800227a5  jb      short loc_1800227BC
0x1800227a7  mov     rcx, [rcx+10h]
0x1800227ab  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x1800227b2  mov     edx, 0Fh
0x1800227b7  call    WPP_SF_
0x1800227bc  lea     rsi, [rbx+68h]
0x1800227c0  lea     r14, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x1800227c7  mov     rdi, [rsi]
0x1800227ca  cmp     rdi, rsi
0x1800227cd  jz      short loc_180022819
0x1800227cf  cmp     [rdi+8], rsi
0x1800227d3  jnz     loc_180022875
0x1800227d9  mov     rax, [rdi]
0x1800227dc  cmp     [rax+8], rdi
0x1800227e0  jnz     loc_180022875
0x1800227e6  mov     [rsi], rax
0x1800227e9  xor     ecx, ecx; this
0x1800227eb  mov     [rax+8], rsi
0x1800227ef  mov     r8, rbx
0x1800227f2  mov     rdx, [rdi+20h]
0x1800227f6  not     r8
0x1800227f9  not     rdx; Apx::ApfVerify *
0x1800227fc  mov     [rsp+58h+var_38], r14
0x180022801  lea     r9d, [rcx+67h]
0x180022805  call    imp_ApxObjectDereferenceActual
0x18002280a  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18002280f  mov     rcx, rdi; void *
0x180022812  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180022817  jmp     short loc_1800227C7
0x180022819  lea     rdi, [rbx+78h]
0x18002281d  mov     rax, [rdi]
0x180022820  cmp     rax, rdi
0x180022823  jz      short loc_18002287C
0x180022825  cmp     [rax+8], rdi
0x180022829  jnz     short loc_180022875
0x18002282b  mov     rcx, [rax]
0x18002282e  cmp     [rcx+8], rax
0x180022832  jnz     short loc_180022875
0x180022834  mov     [rdi], rcx
0x180022837  lea     rsi, [rax-38h]
0x18002283b  mov     [rcx+8], rdi
0x18002283f  mov     r8, rbx
0x180022842  xor     ecx, ecx; this
0x180022844  mov     [rsp+58h+var_38], r14
0x180022849  mov     rdx, rsi
0x18002284c  not     r8
0x18002284f  not     rdx; Apx::ApfVerify *
0x180022852  lea     r9d, [rcx+6Fh]
0x180022856  call    imp_ApxObjectDereferenceActual
0x18002285b  test    rsi, rsi
0x18002285e  jz      short loc_18002281D
0x180022860  mov     rax, [rsi]
0x180022863  mov     edx, 1
0x180022868  mov     rcx, rsi
0x18002286b  mov     rax, [rax]
0x18002286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022873  jmp     short loc_18002281D
0x180022875  mov     ecx, 3
0x18002287a  int     29h; Win8: RtlFailFast(ecx)
0x18002287c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180022880  call    cs:__imp_DeleteCriticalSection
0x180022886  mov     rcx, cs:WPP_GLOBAL_Control
0x18002288d  cmp     rcx, rbp
0x180022890  jz      short loc_1800228B3
0x180022892  test    byte ptr [rcx+1Ch], 1
0x180022896  jz      short loc_1800228B3
0x180022898  cmp     byte ptr [rcx+19h], 5
0x18002289c  jb      short loc_1800228B3
0x18002289e  mov     rcx, [rcx+10h]
0x1800228a2  lea     r8, WPP_b80f8302e70934d41d7f826282614d49_Traceguids
0x1800228a9  mov     edx, 10h
0x1800228ae  call    WPP_SF_
0x1800228b3  lea     rax, ??_7ApfObject@Apx@@6B@; const Apx::ApfObject::`vftable'
0x1800228ba  mov     [rbx], rax
0x1800228bd  add     rsp, 30h
0x1800228c1  pop     r14
0x1800228c3  pop     rdi
0x1800228c4  pop     rsi
0x1800228c5  pop     rbp
0x1800228c6  pop     rbx
0x1800228c7  retn
```
