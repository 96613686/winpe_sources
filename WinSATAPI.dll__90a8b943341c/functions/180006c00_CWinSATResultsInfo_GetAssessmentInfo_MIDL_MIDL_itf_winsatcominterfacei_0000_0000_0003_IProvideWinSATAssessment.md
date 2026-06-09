# CWinSATResultsInfo::GetAssessmentInfo(__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003,IProvideWinSATAssessmentInfo * *)

- ea: `0x180006c00`
- end: `0x180006f1f`
- name: `?GetAssessmentInfo@CWinSATResultsInfo@@UEAAJW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003@@PEAPEAUIProvideWinSATAssessmentInfo@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(CWinSATResultsInfo *__hidden this, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003, struct IProvideWinSATAssessmentInfo **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006c00`
- `0x180006f30`
- `0x180008490`
- `0x1800108f4`
- `0x180011e70`
- `0x180011ee0`
- `0x180012c06`
- `0x18001dc3c`
- `0x18001dd38`
- `0x18001ddc4`
- `0x18001dff0`
- `0x180033010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006daa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006db9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006de4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006daa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006db9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006de4`

## pseudocode

```c
__int64 __fastcall CWinSATResultsInfo::GetAssessmentInfo(
        CWinSATResultsInfo *this,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0003 a2,
        struct IProvideWinSATAssessmentInfo **a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  void *v12; // rax
  __int64 v13; // rcx
  int GraphicsStrings; // ebx
  int v15; // xmm6_4
  __int64 v16; // rsi
  _QWORD *v17; // rbx
  _QWORD *v18; // rdi
  int v19; // esi
  bool v20; // zf
  void *v21; // rcx
  void *v22; // rcx
  int v24; // esi
  int v25; // esi
  int v26; // esi
  _QWORD *v27; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v28[3]; // [rsp+28h] [rbp-28h] BYREF
  _QWORD *v29; // [rsp+88h] [rbp+38h] BYREF

  v28[1] = -2;
  v6 = operator new(0x28u);
  v7 = v6;
  if ( !v6 )
    goto LABEL_46;
  v6[2] = 1;
  v6[3] = 0;
  *v6 = 0;
  v6[1] = 0;
  v8 = operator new(2u);
  if ( !v8 )
    goto LABEL_46;
  v7[3] = v8;
  if ( *v7 )
    memcpy_0(v8, 0, 2LL * *v7);
  v9 = v7[3];
  if ( v9 )
    *(_WORD *)(v9 + 2LL * *v7) = 0;
  v27 = v7;
  v10 = operator new(0x28u);
  v11 = v10;
  if ( !v10 || (v10[2] = 1, v10[3] = 0, *v10 = 0, v10[1] = 0, (v12 = operator new(2u)) == 0) )
LABEL_46:
    std::_Xbad_alloc();
  v11[3] = v12;
  if ( *v11 )
    memcpy_0(v12, 0, 2LL * *v11);
  v13 = v11[3];
  if ( v13 )
    *(_WORD *)(v13 + 2LL * *v11) = 0;
  v29 = v11;
  if ( a2 )
  {
    v24 = a2 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v29);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v27);
            return 2147745813LL;
          }
          GraphicsStrings = CWinSATResultsInfo::GetGraphicsStrings(this, &v29, &v27);
          if ( GraphicsStrings < 0 )
            goto LABEL_44;
          v15 = *((_DWORD *)this + 116);
        }
        else
        {
          GraphicsStrings = CWinSATResultsInfo::GetD3DStrings(this, &v29, &v27);
          if ( GraphicsStrings < 0 )
            goto LABEL_44;
          v15 = *((_DWORD *)this + 117);
        }
      }
      else
      {
        GraphicsStrings = CWinSATResultsInfo::GetDiskStrings(v13, (__int64)&v29, (__int64)&v27);
        if ( GraphicsStrings < 0 )
          goto LABEL_44;
        v15 = *((_DWORD *)this + 115);
      }
    }
    else
    {
      GraphicsStrings = CWinSATResultsInfo::GetCPUStrings(v13, &v29, &v27);
      if ( GraphicsStrings < 0 )
        goto LABEL_44;
      v15 = *((_DWORD *)this + 113);
    }
  }
  else
  {
    GraphicsStrings = CWinSATResultsInfo::GetMemoryStrings(v13, &v29, &v27);
    if ( GraphicsStrings < 0 )
    {
LABEL_44:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v29);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v27);
      return (unsigned int)GraphicsStrings;
    }
    v15 = *((_DWORD *)this + 114);
  }
  v28[0] = 0;
  GraphicsStrings = ATL::CComObject<CWinSATAssessmentInfo>::CreateInstance(v28);
  if ( GraphicsStrings < 0 )
    goto LABEL_44;
  v16 = v28[0];
  *(_DWORD *)(v28[0] + 88LL) = v15;
  if ( *(_QWORD *)(v16 + 72) )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v16 + 72);
  v17 = v27;
  *(_QWORD *)(v16 + 72) = v27;
  ++v17[2];
  if ( *(_QWORD *)(v16 + 80) )
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v16 + 80);
  v18 = v29;
  *(_QWORD *)(v16 + 80) = v29;
  ++v18[2];
  v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IProvideWinSATAssessmentInfo **))v16)(
          v16,
          &GUID_0cd1c380_52d3_4678_ac6f_e929e480be9e,
          a3);
  if ( v19 >= 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v29);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v27);
    return 0;
  }
  else
  {
    v20 = v18[2]-- == 1;
    if ( v20 )
    {
      v21 = (void *)v18[3];
      if ( v21 )
        operator delete(v21);
      operator delete(v18);
    }
    v20 = v17[2]-- == 1;
    if ( v20 )
    {
      v22 = (void *)v17[3];
      if ( v22 )
        operator delete(v22);
      operator delete(v17);
    }
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x180006c00  mov     rax, rsp
0x180006c03  push    rbp
0x180006c04  push    r14
0x180006c06  push    r15
0x180006c08  mov     rbp, rsp
0x180006c0b  sub     rsp, 50h
0x180006c0f  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x180006c17  mov     [rax+8], rbx
0x180006c1b  mov     [rax+10h], rsi
0x180006c1f  mov     [rax+18h], rdi
0x180006c23  movaps  xmmword ptr [rax-28h], xmm6
0x180006c27  mov     r15, r8
0x180006c2a  mov     esi, edx
0x180006c2c  mov     rdi, rcx
0x180006c2f  mov     ecx, 28h ; '('; Size
0x180006c34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c39  mov     rbx, rax
0x180006c3c  test    rax, rax
0x180006c3f  jz      loc_180006F19
0x180006c45  mov     qword ptr [rax+10h], 1
0x180006c4d  xor     r14d, r14d
0x180006c50  mov     [rax+18h], r14
0x180006c54  mov     [rax], r14
0x180006c57  mov     [rax+8], r14
0x180006c5b  lea     ecx, [r14+2]; Size
0x180006c5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006c64  test    rax, rax
0x180006c67  jz      loc_180006F19
0x180006c6d  mov     [rbx+18h], rax
0x180006c71  mov     r8, [rbx]
0x180006c74  test    r8, r8
0x180006c77  jz      short loc_180006C86
0x180006c79  add     r8, r8; Size
0x180006c7c  xor     edx, edx; Src
0x180006c7e  mov     rcx, rax; void *
0x180006c81  call    memcpy_0
0x180006c86  mov     rdx, [rbx+18h]
0x180006c8a  test    rdx, rdx
0x180006c8d  jz      short loc_180006C97
0x180006c8f  mov     rax, [rbx]
0x180006c92  mov     [rdx+rax*2], r14w
0x180006c97  mov     [rbp+var_30], rbx
0x180006c9b  mov     ecx, 28h ; '('; Size
0x180006ca0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006ca5  mov     rbx, rax
0x180006ca8  test    rax, rax
0x180006cab  jz      loc_180006F19
0x180006cb1  mov     qword ptr [rax+10h], 1
0x180006cb9  mov     [rax+18h], r14
0x180006cbd  mov     [rax], r14
0x180006cc0  mov     [rax+8], r14
0x180006cc4  mov     ecx, 2; Size
0x180006cc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006cce  test    rax, rax
0x180006cd1  jz      loc_180006F19
0x180006cd7  mov     [rbx+18h], rax
0x180006cdb  mov     r8, [rbx]
0x180006cde  test    r8, r8
0x180006ce1  jz      short loc_180006CF0
0x180006ce3  add     r8, r8; Size
0x180006ce6  xor     edx, edx; Src
0x180006ce8  mov     rcx, rax; void *
0x180006ceb  call    memcpy_0
0x180006cf0  mov     rcx, [rbx+18h]
0x180006cf4  test    rcx, rcx
0x180006cf7  jz      short loc_180006D01
0x180006cf9  mov     rax, [rbx]
0x180006cfc  mov     [rcx+rax*2], r14w
0x180006d01  mov     [rbp+arg_18], rbx
0x180006d05  test    esi, esi
0x180006d07  jnz     loc_180006E30
0x180006d0d  lea     r8, [rbp+var_30]
0x180006d11  lea     rdx, [rbp+arg_18]
0x180006d15  call    ?GetMemoryStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetMemoryStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180006d1a  mov     ebx, eax
0x180006d1c  test    eax, eax
0x180006d1e  js      loc_180006EE7
0x180006d24  movss   xmm6, dword ptr [rdi+1C8h]
0x180006d2c  mov     [rbp+var_28], r14
0x180006d30  lea     rcx, [rbp+var_28]
0x180006d34  call    ?CreateInstance@?$CComObject@VCWinSATAssessmentInfo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWinSATAssessmentInfo>::CreateInstance(ATL::CComObject<CWinSATAssessmentInfo> * *)
0x180006d39  mov     ebx, eax
0x180006d3b  test    eax, eax
0x180006d3d  js      loc_180006EE7
0x180006d43  mov     rsi, [rbp+var_28]
0x180006d47  movss   dword ptr [rsi+58h], xmm6
0x180006d4c  cmp     [rsi+48h], r14
0x180006d50  jnz     loc_180006E14
0x180006d56  mov     rbx, [rbp+var_30]
0x180006d5a  mov     [rsi+48h], rbx
0x180006d5e  inc     qword ptr [rbx+10h]
0x180006d62  cmp     [rsi+50h], r14
0x180006d66  jnz     loc_180006E22
0x180006d6c  mov     rdi, [rbp+arg_18]
0x180006d70  mov     [rsi+50h], rdi
0x180006d74  inc     qword ptr [rdi+10h]
0x180006d78  mov     rax, [rsi]
0x180006d7b  mov     r8, r15
0x180006d7e  lea     rdx, _GUID_0cd1c380_52d3_4678_ac6f_e929e480be9e
0x180006d85  mov     rcx, rsi
0x180006d88  mov     rax, [rax]
0x180006d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d90  mov     esi, eax
0x180006d92  test    eax, eax
0x180006d94  jns     loc_180006F00
0x180006d9a  sub     qword ptr [rdi+10h], 1
0x180006d9f  jnz     short loc_180006DC5
0x180006da1  mov     rcx, [rdi+18h]
0x180006da5  test    rcx, rcx
0x180006da8  jz      short loc_180006DB6
0x180006daa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006db1  nop     dword ptr [rax+rax+00h]
0x180006db6  mov     rcx, rdi
0x180006db9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006dc0  nop     dword ptr [rax+rax+00h]
0x180006dc5  sub     qword ptr [rbx+10h], 1
0x180006dca  jnz     short loc_180006DF0
0x180006dcc  mov     rcx, [rbx+18h]
0x180006dd0  test    rcx, rcx
0x180006dd3  jz      short loc_180006DE1
0x180006dd5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006ddc  nop     dword ptr [rax+rax+00h]
0x180006de1  mov     rcx, rbx
0x180006de4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006deb  nop     dword ptr [rax+rax+00h]
0x180006df0  mov     eax, esi
0x180006df2  mov     rbx, [rsp+50h+arg_0]
0x180006df7  mov     rsi, [rsp+50h+arg_8]
0x180006dfc  mov     rdi, [rsp+50h+arg_10]
0x180006e04  movaps  xmm6, [rsp+50h+var_10]
0x180006e09  add     rsp, 50h
0x180006e0d  pop     r15
0x180006e0f  pop     r14
0x180006e11  pop     rbp
0x180006e12  retn
0x180006e14  lea     rcx, [rsi+48h]
0x180006e18  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006e1d  jmp     loc_180006D56
0x180006e22  lea     rcx, [rsi+50h]
0x180006e26  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006e2b  jmp     loc_180006D6C
0x180006e30  sub     esi, 1
0x180006e33  jz      loc_180006EC7
0x180006e39  sub     esi, 1
0x180006e3c  jz      short loc_180006EA7
0x180006e3e  sub     esi, 1
0x180006e41  jz      short loc_180006E84
0x180006e43  cmp     esi, 1
0x180006e46  jz      short loc_180006E61
0x180006e48  lea     rcx, [rbp+arg_18]
0x180006e4c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006e51  lea     rcx, [rbp+var_30]
0x180006e55  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006e5a  mov     eax, 80040015h
0x180006e5f  jmp     short loc_180006DF2
0x180006e61  lea     r8, [rbp+var_30]
0x180006e65  lea     rdx, [rbp+arg_18]
0x180006e69  mov     rcx, rdi
0x180006e6c  call    ?GetGraphicsStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetGraphicsStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180006e71  mov     ebx, eax
0x180006e73  test    eax, eax
0x180006e75  js      short loc_180006EE7
0x180006e77  movss   xmm6, dword ptr [rdi+1D0h]
0x180006e7f  jmp     loc_180006D2C
0x180006e84  lea     r8, [rbp+var_30]
0x180006e88  lea     rdx, [rbp+arg_18]
0x180006e8c  mov     rcx, rdi
0x180006e8f  call    ?GetD3DStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetD3DStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180006e94  mov     ebx, eax
0x180006e96  test    eax, eax
0x180006e98  js      short loc_180006EE7
0x180006e9a  movss   xmm6, dword ptr [rdi+1D4h]
0x180006ea2  jmp     loc_180006D2C
0x180006ea7  lea     r8, [rbp+var_30]
0x180006eab  lea     rdx, [rbp+arg_18]
0x180006eaf  call    ?GetDiskStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetDiskStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180006eb4  mov     ebx, eax
0x180006eb6  test    eax, eax
0x180006eb8  js      short loc_180006EE7
0x180006eba  movss   xmm6, dword ptr [rdi+1CCh]
0x180006ec2  jmp     loc_180006D2C
0x180006ec7  lea     r8, [rbp+var_30]
0x180006ecb  lea     rdx, [rbp+arg_18]
0x180006ecf  call    ?GetCPUStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; CWinSATResultsInfo::GetCPUStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180006ed4  mov     ebx, eax
0x180006ed6  test    eax, eax
0x180006ed8  js      short loc_180006EE7
0x180006eda  movss   xmm6, dword ptr [rdi+1C4h]
0x180006ee2  jmp     loc_180006D2C
0x180006ee7  lea     rcx, [rbp+arg_18]
0x180006eeb  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006ef0  lea     rcx, [rbp+var_30]
0x180006ef4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006ef9  mov     eax, ebx
0x180006efb  jmp     loc_180006DF2
0x180006f00  lea     rcx, [rbp+arg_18]
0x180006f04  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006f09  lea     rcx, [rbp+var_30]
0x180006f0d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180006f12  xor     eax, eax
0x180006f14  jmp     loc_180006DF2
0x180006f19  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
