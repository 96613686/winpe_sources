# Apx::ApfObjectBag::_CreateAndInitialize(Apx::_APF_OBJECTBAG_CONFIG *,Apx::ApfObjectBag * *)

- ea: `0x1800203ac`
- end: `0x180020501`
- name: `?_CreateAndInitialize@ApfObjectBag@Apx@@SAJPEAU_APF_OBJECTBAG_CONFIG@2@PEAPEAV12@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct Apx::_APF_OBJECTBAG_CONFIG *, struct Apx::ApfObjectBag **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800208ec`

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18001fa80`
- `0x1800203ac`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Apx::ApfObjectBag::_CreateAndInitialize(
        struct Apx::_APF_OBJECTBAG_CONFIG *a1,
        struct Apx::ApfObjectBag **a2)
{
  struct Apx::ApfObjectBag *v4; // rax
  struct Apx::ApfObjectBag *v5; // rbx
  _QWORD *v6; // rcx
  int v7; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
  }
  *a2 = 0;
  v4 = (struct Apx::ApfObjectBag *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *(_QWORD *)v4 = &Apx::ApfObjectBag::`vftable';
    *((_DWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
        WPP_SF_(v6[2], 13, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
    }
    v7 = Apx::ApfObjectBag::Initialize((unsigned __int64)v5, a1);
    if ( v7 < 0 )
    {
      (**(void (__fastcall ***)(struct Apx::ApfObjectBag *, __int64))v5)(v5, 1);
    }
    else
    {
      *a2 = v5;
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800203ac  push    rbx
0x1800203ae  push    rsi
0x1800203af  push    rdi
0x1800203b0  push    r12
0x1800203b2  sub     rsp, 28h
0x1800203b6  mov     rsi, rdx
0x1800203b9  mov     rdi, rcx
0x1800203bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203c3  lea     r12, WPP_GLOBAL_Control
0x1800203ca  cmp     rcx, r12
0x1800203cd  jz      short loc_1800203F0
0x1800203cf  test    byte ptr [rcx+1Ch], 1
0x1800203d3  jz      short loc_1800203F0
0x1800203d5  cmp     byte ptr [rcx+19h], 5
0x1800203d9  jb      short loc_1800203F0
0x1800203db  mov     rcx, [rcx+10h]
0x1800203df  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x1800203e6  mov     edx, 0Ah
0x1800203eb  call    WPP_SF_
0x1800203f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800203f7  mov     qword ptr [rsi], 0
0x1800203fe  mov     ecx, 30h ; '0'; unsigned __int64
0x180020403  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020408  mov     rbx, rax
0x18002040b  test    rax, rax
0x18002040e  jz      loc_1800204C3
0x180020414  mov     dword ptr [rax+8], 1
0x18002041b  lea     rax, ??_7ApfObjectBag@Apx@@6B@; const Apx::ApfObjectBag::`vftable'
0x180020422  mov     [rbx], rax
0x180020425  mov     dword ptr [rbx+10h], 0
0x18002042c  mov     qword ptr [rbx+18h], 0
0x180020434  mov     qword ptr [rbx+20h], 0
0x18002043c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020443  cmp     rcx, r12
0x180020446  jz      short loc_180020496
0x180020448  test    byte ptr [rcx+1Ch], 1
0x18002044c  jz      short loc_180020470
0x18002044e  cmp     byte ptr [rcx+19h], 5
0x180020452  jb      short loc_180020470
0x180020454  mov     rcx, [rcx+10h]
0x180020458  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18002045f  mov     edx, 0Ch
0x180020464  call    WPP_SF_
0x180020469  mov     rcx, cs:WPP_GLOBAL_Control
0x180020470  cmp     rcx, r12
0x180020473  jz      short loc_180020496
0x180020475  test    byte ptr [rcx+1Ch], 1
0x180020479  jz      short loc_180020496
0x18002047b  cmp     byte ptr [rcx+19h], 5
0x18002047f  jb      short loc_180020496
0x180020481  mov     rcx, [rcx+10h]
0x180020485  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x18002048c  mov     edx, 0Dh
0x180020491  call    WPP_SF_
0x180020496  mov     rdx, rdi; struct Apx::_APF_OBJECTBAG_CONFIG *
0x180020499  mov     rcx, rbx; this
0x18002049c  call    ?Initialize@ApfObjectBag@Apx@@AEAAJPEAU_APF_OBJECTBAG_CONFIG@2@@Z; Apx::ApfObjectBag::Initialize(Apx::_APF_OBJECTBAG_CONFIG *)
0x1800204a1  mov     edi, eax
0x1800204a3  test    eax, eax
0x1800204a5  js      short loc_1800204AE
0x1800204a7  mov     [rsi], rbx
0x1800204aa  xor     edi, edi
0x1800204ac  jmp     short loc_1800204C8
0x1800204ae  mov     rax, [rbx]
0x1800204b1  mov     edx, 1
0x1800204b6  mov     rcx, rbx
0x1800204b9  mov     rax, [rax]
0x1800204bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204c1  jmp     short loc_1800204C8
0x1800204c3  mov     edi, 8007000Eh
0x1800204c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204cf  cmp     rcx, r12
0x1800204d2  jz      short loc_1800204F5
0x1800204d4  test    byte ptr [rcx+1Ch], 1
0x1800204d8  jz      short loc_1800204F5
0x1800204da  cmp     byte ptr [rcx+19h], 5
0x1800204de  jb      short loc_1800204F5
0x1800204e0  mov     rcx, [rcx+10h]
0x1800204e4  lea     r8, WPP_56dfc2b02d7631e6b8bb1f3c1bb101c5_Traceguids
0x1800204eb  mov     edx, 0Bh
0x1800204f0  call    WPP_SF_
0x1800204f5  mov     eax, edi
0x1800204f7  add     rsp, 28h
0x1800204fb  pop     r12
0x1800204fd  pop     rdi
0x1800204fe  pop     rsi
0x1800204ff  pop     rbx
0x180020500  retn
```
