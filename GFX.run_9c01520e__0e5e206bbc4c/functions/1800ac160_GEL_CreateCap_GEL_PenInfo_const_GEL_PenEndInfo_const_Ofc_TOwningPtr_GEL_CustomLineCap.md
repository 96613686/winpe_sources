# GEL::CreateCap(GEL::PenInfo const &,GEL::PenEndInfo const &,Ofc::TOwningPtr<GEL::CustomLineCap> &)

- ea: `0x1800ac160`
- end: `0x1800ac273`
- name: `?CreateCap@GEL@@YAXAEBUPenInfo@1@AEBUPenEndInfo@1@AEAV?$TOwningPtr@VCustomLineCap@GEL@@@Ofc@@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ac0c4`

## callees

- `0x1800a86ac`
- `0x1800ab6fc`
- `0x1800ac160`
- `0x1801de27c`
- `0x1801de2ac`

## import_xrefs

- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ac1cb`
- `mso40uiWin32Client!__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z` at `0x1800ac1cb`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ac1d6`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1800ac1d6`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac1fa`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac226`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac26c`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac1fa`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac226`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1800ac26c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac1a4`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac213`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac255`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac1a4`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac213`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800ac255`

## pseudocode

```c
void __fastcall GEL::CreateCap(GEL *a1, const struct GEL::PenInfo *a2, const struct GEL::PenEndInfo *a3)
{
  struct GEL::CustomLineCap *v4; // rdi
  unsigned int v5; // r8d
  void (*v6)(void *); // rdx
  __int64 *v7; // rbx
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  float v10; // [rsp+20h] [rbp-8h]
  struct Ofc::CProxyPtrImpl *v11; // [rsp+38h] [rbp+10h] BYREF

  if ( *((_BYTE *)a2 + 8) )
  {
    if ( *((_BYTE *)a2 + 9) )
    {
      if ( *((_BYTE *)a2 + 9) == 1 )
      {
        v4 = GEL::ReferenceSquareAnchor(a1);
        if ( v4 )
        {
          v7 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v8);
          if ( !v7 )
          {
            CrashWithRecoveryOnOOM(0x1F3C0756u);
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
          v7 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v5);
          if ( !v7 )
          {
            CrashWithRecoveryOnOOM(0x1F3C0756u);
            __debugbreak();
          }
LABEL_7:
          Ofc::CProxyPtrImpl::CProxyPtrImpl((Ofc::CProxyPtrImpl *)v7, v6);
          v7[2] = (__int64)v4;
LABEL_8:
          v11 = (struct Ofc::CProxyPtrImpl *)v7;
          Ofc::CProxyPtrImpl::StrongMoveAssign((struct Ofc::CProxyPtrImpl **)a3, &v11);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v11);
          return;
        }
      }
    }
    else
    {
      v4 = GEL::ReferenceRoundAnchor(a1, -1.0, 2.0, 2.0, v10);
      if ( v4 )
      {
        v7 = (__int64 *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v9);
        if ( !v7 )
        {
          CrashWithRecoveryOnOOM(0x1F3C0756u);
          JUMPOUT(0x1800AC272LL);
        }
        goto LABEL_7;
      }
    }
    v7 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1800ac160  mov     [rsp+arg_0], rbx
0x1800ac165  mov     [rsp+arg_10], rsi
0x1800ac16a  push    rdi; float
0x1800ac16b  sub     rsp, 20h
0x1800ac16f  cmp     byte ptr [rdx+8], 0
0x1800ac173  mov     rsi, r8
0x1800ac176  jz      short loc_1800AC1DC
0x1800ac178  movzx   r9d, byte ptr [rdx+9]
0x1800ac17d  test    r9d, r9d
0x1800ac180  jz      loc_1800AC22D
0x1800ac186  sub     r9d, 1
0x1800ac18a  jz      short loc_1800AC201
0x1800ac18c  cmp     r9d, 2
0x1800ac190  jnz     short loc_1800AC1DC
0x1800ac192  call    ?ReferenceCustomAnchor@GEL@@YAPEAVCustomLineCap@1@AEBUPenInfo@1@AEBUPenEndInfo@1@@Z; GEL::ReferenceCustomAnchor(GEL::PenInfo const &,GEL::PenEndInfo const &)
0x1800ac197  mov     rdi, rax
0x1800ac19a  test    rax, rax
0x1800ac19d  jz      short loc_1800AC1EC
0x1800ac19f  xor     edx, edx
0x1800ac1a1  lea     ecx, [rdx+18h]
0x1800ac1a4  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ac1aa  mov     rbx, rax
0x1800ac1ad  test    rax, rax
0x1800ac1b0  jz      short loc_1800AC1F5
0x1800ac1b2  mov     rcx, rbx; this
0x1800ac1b5  call    ??0CProxyPtrImpl@Ofc@@IEAA@P6AXPEAX@Z@Z; Ofc::CProxyPtrImpl::CProxyPtrImpl(void (*)(void *))
0x1800ac1ba  mov     [rbx+10h], rdi
0x1800ac1be  lea     rdx, [rsp+28h+arg_8]
0x1800ac1c3  mov     [rsp+28h+arg_8], rbx
0x1800ac1c8  mov     rcx, rsi
0x1800ac1cb  call    cs:__imp_?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1800ac1d1  lea     rcx, [rsp+28h+arg_8]
0x1800ac1d6  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800ac1dc  mov     rbx, [rsp+28h+arg_0]
0x1800ac1e1  mov     rsi, [rsp+28h+arg_10]
0x1800ac1e6  add     rsp, 20h
0x1800ac1ea  pop     rdi
0x1800ac1eb  retn
0x1800ac1ec  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1800ac1f3  jmp     short loc_1800AC1BE
0x1800ac1f5  mov     ecx, 1F3C0756h
0x1800ac1fa  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800ac200  int     3; Trap to Debugger
0x1800ac201  call    ?ReferenceSquareAnchor@GEL@@YAPEAVCustomLineCap@1@XZ; GEL::ReferenceSquareAnchor(void)
0x1800ac206  mov     rdi, rax
0x1800ac209  test    rax, rax
0x1800ac20c  jz      short loc_1800AC1EC
0x1800ac20e  xor     edx, edx
0x1800ac210  lea     ecx, [rdx+18h]
0x1800ac213  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ac219  mov     rbx, rax
0x1800ac21c  test    rax, rax
0x1800ac21f  jnz     short loc_1800AC1B2
0x1800ac221  mov     ecx, 1F3C0756h
0x1800ac226  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x1800ac22c  int     3; Trap to Debugger
0x1800ac22d  movss   xmm2, cs:__real@40000000; float
0x1800ac235  movss   xmm0, cs:__real@bf800000
0x1800ac23d  movaps  xmm3, xmm2; float
0x1800ac240  movaps  xmm1, xmm0; float
0x1800ac243  call    ?ReferenceRoundAnchor@GEL@@YAPEAVCustomLineCap@1@MMMM@Z; GEL::ReferenceRoundAnchor(float,float,float,float)
0x1800ac248  mov     rdi, rax
0x1800ac24b  test    rax, rax
0x1800ac24e  jz      short loc_1800AC1EC
0x1800ac250  xor     edx, edx
0x1800ac252  lea     ecx, [rdx+18h]
0x1800ac255  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800ac25b  mov     rbx, rax
0x1800ac25e  test    rax, rax
0x1800ac261  jnz     loc_1800AC1B2
0x1800ac267  mov     ecx, 1F3C0756h
0x1800ac26c  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
```
