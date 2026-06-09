# GEL::CreateCap(GEL::PenInfo const &,GEL::PenEndInfo const &,Ofc::TOwningPtr<GEL::CustomLineCap> &)

- ea: `0x1800e3528`
- end: `0x1800e3656`
- name: `?CreateCap@GEL@@YAXAEBUPenInfo@1@AEBUPenEndInfo@1@AEAV?$TOwningPtr@VCustomLineCap@GEL@@@Ofc@@@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800e3490`

## callees

- `0x1800e3528`
- `0x1800e3658`
- `0x1800e3c90`
- `0x1801da78c`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1800e358f`
- `KERNEL32!EncodePointer` at `0x1800e358f`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800e35aa`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800e35aa`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800e35b5`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800e35b5`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e35d9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e3609`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e364f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e35d9`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e3609`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800e364f`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e3570`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e35f2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e3638`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e3570`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e35f2`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800e3638`

## pseudocode

```c
void __fastcall GEL::CreateCap(GEL *a1, const struct GEL::PenInfo *a2, const struct GEL::PenEndInfo *a3)
{
  struct GEL::CustomLineCap *v4; // rdi
  unsigned int v5; // r8d
  __int64 *v6; // rbx
  unsigned int v7; // r8d
  unsigned int v8; // r8d
  float v9; // [rsp+20h] [rbp-8h]
  struct Ofc::CProxyPtrImpl *v10; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_BYTE *)a2 + 8) )
  {
    if ( *((_BYTE *)a2 + 9) )
    {
      if ( *((_BYTE *)a2 + 9) == 1 )
      {
        v4 = GEL::ReferenceSquareAnchor(a1);
        if ( v4 )
        {
          v6 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v7);
          if ( !v6 )
          {
            CrashWithRecoveryOnOOM(0x1E000188u);
            __debugbreak();
          }
          goto LABEL_7;
        }
      }
      else
      {
        if ( *((_BYTE *)a2 + 9) != 3 )
          return;
        v4 = GEL::ReferenceCustomAnchor(a1, a2, a3);
        if ( v4 )
        {
          v6 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v5);
          if ( !v6 )
          {
            CrashWithRecoveryOnOOM(0x1E000188u);
            __debugbreak();
          }
LABEL_7:
          *(_DWORD *)v6 = 1;
          *((_DWORD *)v6 + 1) = 1;
          v6[1] = (__int64)EncodePointer(Ofc::TDeleteFromProxy<GEL::CustomLineCap>);
          v6[2] = (__int64)v4;
LABEL_8:
          v10 = (struct Ofc::CProxyPtrImpl *)v6;
          Ofc::CProxyPtrImpl::StrongMoveAssign((struct Ofc::CProxyPtrImpl **)a3, &v10);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v10);
          return;
        }
      }
    }
    else
    {
      v4 = GEL::ReferenceRoundAnchor(a1, -1.0, 2.0, 2.0, v9);
      if ( v4 )
      {
        v6 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v8);
        if ( !v6 )
        {
          CrashWithRecoveryOnOOM(0x1E000188u);
          JUMPOUT(0x1800E3655LL);
        }
        goto LABEL_7;
      }
    }
    v6 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1800e3528  mov     [rsp+arg_0], rbx
0x1800e352d  mov     [rsp+arg_10], rsi
0x1800e3532  push    rdi; float
0x1800e3533  sub     rsp, 20h
0x1800e3537  cmp     byte ptr [rdx+8], 0
0x1800e353b  mov     rsi, r8
0x1800e353e  jz      short loc_1800E35BB
0x1800e3540  movzx   r9d, byte ptr [rdx+9]
0x1800e3545  test    r9d, r9d
0x1800e3548  jz      loc_1800E3610
0x1800e354e  sub     r9d, 1
0x1800e3552  jz      loc_1800E35E0
0x1800e3558  cmp     r9d, 2
0x1800e355c  jnz     short loc_1800E35BB
0x1800e355e  call    ?ReferenceCustomAnchor@GEL@@YAPEAVCustomLineCap@1@AEBUPenInfo@1@AEBUPenEndInfo@1@@Z; GEL::ReferenceCustomAnchor(GEL::PenInfo const &,GEL::PenEndInfo const &)
0x1800e3563  mov     rdi, rax
0x1800e3566  test    rax, rax
0x1800e3569  jz      short loc_1800E35CB
0x1800e356b  xor     edx, edx
0x1800e356d  lea     ecx, [rdx+18h]
0x1800e3570  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e3576  mov     rbx, rax
0x1800e3579  test    rax, rax
0x1800e357c  jz      short loc_1800E35D4
0x1800e357e  mov     eax, 1
0x1800e3583  lea     rcx, ??$TDeleteFromProxy@VCustomLineCap@GEL@@@Ofc@@YAXPEAX@Z; Ptr
0x1800e358a  mov     [rbx], eax
0x1800e358c  mov     [rbx+4], eax
0x1800e358f  call    cs:__imp_EncodePointer
0x1800e3595  mov     [rbx+8], rax
0x1800e3599  mov     [rbx+10h], rdi
0x1800e359d  lea     rdx, [rsp+28h+arg_8]
0x1800e35a2  mov     [rsp+28h+arg_8], rbx
0x1800e35a7  mov     rcx, rsi
0x1800e35aa  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1800e35b0  lea     rcx, [rsp+28h+arg_8]
0x1800e35b5  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800e35bb  mov     rbx, [rsp+28h+arg_0]
0x1800e35c0  mov     rsi, [rsp+28h+arg_10]
0x1800e35c5  add     rsp, 20h
0x1800e35c9  pop     rdi
0x1800e35ca  retn
0x1800e35cb  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1800e35d2  jmp     short loc_1800E359D
0x1800e35d4  mov     ecx, 1E000188h
0x1800e35d9  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800e35df  int     3; Trap to Debugger
0x1800e35e0  call    ?ReferenceSquareAnchor@GEL@@YAPEAVCustomLineCap@1@XZ; GEL::ReferenceSquareAnchor(void)
0x1800e35e5  mov     rdi, rax
0x1800e35e8  test    rax, rax
0x1800e35eb  jz      short loc_1800E35CB
0x1800e35ed  xor     edx, edx
0x1800e35ef  lea     ecx, [rdx+18h]
0x1800e35f2  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e35f8  mov     rbx, rax
0x1800e35fb  test    rax, rax
0x1800e35fe  jnz     loc_1800E357E
0x1800e3604  mov     ecx, 1E000188h
0x1800e3609  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800e360f  int     3; Trap to Debugger
0x1800e3610  movss   xmm2, cs:__real@40000000; float
0x1800e3618  movss   xmm0, cs:__real@bf800000
0x1800e3620  movaps  xmm3, xmm2; float
0x1800e3623  movaps  xmm1, xmm0; float
0x1800e3626  call    ?ReferenceRoundAnchor@GEL@@YAPEAVCustomLineCap@1@MMMM@Z; GEL::ReferenceRoundAnchor(float,float,float,float)
0x1800e362b  mov     rdi, rax
0x1800e362e  test    rax, rax
0x1800e3631  jz      short loc_1800E35CB
0x1800e3633  xor     edx, edx
0x1800e3635  lea     ecx, [rdx+18h]
0x1800e3638  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800e363e  mov     rbx, rax
0x1800e3641  test    rax, rax
0x1800e3644  jnz     loc_1800E357E
0x1800e364a  mov     ecx, 1E000188h
0x1800e364f  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
```
