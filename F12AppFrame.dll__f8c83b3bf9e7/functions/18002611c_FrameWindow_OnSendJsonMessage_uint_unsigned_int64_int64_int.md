# FrameWindow::OnSendJsonMessage(uint,unsigned __int64,__int64,int &)

- ea: `0x18002611c`
- end: `0x180026203`
- name: `?OnSendJsonMessage@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `231`
- prototype: `__int64(FrameWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18002b910`

## callees

- `0x180001900`
- `0x18000193c`
- `0x180002dd4`
- `0x180003858`
- `0x18002611c`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800261bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800261bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261dc`
- `USER32!PostMessageW` at `0x180026179`
- `USER32!PostMessageW` at `0x180026179`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FrameWindow::OnSendJsonMessage(HWND *this, __int64 a2, WPARAM a3, __int64 a4)
{
  const OLECHAR *v7; // rcx
  OLECHAR *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  volatile signed __int32 *v11; // rdx

  v7 = *(const OLECHAR **)(a4 + 8);
  if ( v7 )
  {
    v8 = SysAllocString(v7);
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v8 = 0;
  }
  v9 = operator new(0x10u);
  *(_DWORD *)v9 = *(_DWORD *)a4;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    v9 + 1,
    (__int64)v8);
  if ( PostMessageW(this[1], 0x760u, a3, (LPARAM)v9) )
  {
    v10 = 0;
  }
  else
  {
    v10 = -1;
    if ( v9 )
    {
      v11 = (volatile signed __int32 *)(v9[1] - 24LL);
      if ( _InterlockedDecrement(v11 + 4) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
      operator delete(v9);
    }
  }
  SysFreeString(v8);
  return v10;
}

```

## disassembly

```asm
0x18002611c  mov     [rsp+arg_0], rbx
0x180026121  mov     [rsp+arg_8], rbp
0x180026126  push    rsi
0x180026127  push    rdi
0x180026128  push    r14
0x18002612a  sub     rsp, 20h
0x18002612e  mov     rsi, r9
0x180026131  mov     rbp, r8
0x180026134  mov     r14, rcx
0x180026137  mov     rcx, [r9+8]; psz
0x18002613b  test    rcx, rcx
0x18002613e  jnz     short loc_1800261BF
0x180026140  xor     ebx, ebx
0x180026142  mov     [rsp+38h+arg_18], rbx
0x180026147  mov     ecx, 10h; Size
0x18002614c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026151  mov     rdi, rax
0x180026154  mov     [rsp+38h+arg_20], rax
0x180026159  mov     eax, [rsi]
0x18002615b  mov     [rdi], eax
0x18002615d  lea     rcx, [rdi+8]
0x180026161  mov     rdx, rbx
0x180026164  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180026169  nop
0x18002616a  mov     r9, rdi; lParam
0x18002616d  mov     r8, rbp; wParam
0x180026170  mov     edx, 760h; Msg
0x180026175  mov     rcx, [r14+8]; hWnd
0x180026179  call    cs:__imp_PostMessageW
0x18002617f  test    eax, eax
0x180026181  jnz     short loc_1800261D7
0x180026183  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180026187  test    rdi, rdi
0x18002618a  jz      short loc_1800261D9
0x18002618c  mov     rdx, [rdi+8]
0x180026190  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180026194  mov     eax, esi
0x180026196  lock xadd [rdx+10h], eax
0x18002619b  add     eax, esi
0x18002619d  test    eax, eax
0x18002619f  jg      short loc_1800261B0
0x1800261a1  mov     rcx, [rdx]
0x1800261a4  mov     rax, [rcx]
0x1800261a7  mov     rax, [rax+8]
0x1800261ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261b0  mov     edx, 10h
0x1800261b5  mov     rcx, rdi; Block
0x1800261b8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800261bd  jmp     short loc_1800261D9
0x1800261bf  call    cs:__imp_SysAllocString
0x1800261c5  mov     rbx, rax
0x1800261c8  mov     [rsp+38h+arg_18], rax
0x1800261cd  test    rax, rax
0x1800261d0  jz      short loc_1800261F8
0x1800261d2  jmp     loc_180026147
0x1800261d7  xor     esi, esi
0x1800261d9  mov     rcx, rbx; bstrString
0x1800261dc  call    cs:__imp_SysFreeString
0x1800261e2  mov     rax, rsi
0x1800261e5  mov     rbx, [rsp+38h+arg_0]
0x1800261ea  mov     rbp, [rsp+38h+arg_8]
0x1800261ef  add     rsp, 20h
0x1800261f3  pop     r14
0x1800261f5  pop     rdi
0x1800261f6  pop     rsi
0x1800261f7  retn
0x1800261f8  mov     ecx, 8007000Eh; int
0x1800261fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
