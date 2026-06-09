# BrowserToolThreadWindow::ProcessPluginMessage(PluginMessageInfo const *)

- ea: `0x180008990`
- end: `0x180008dae`
- name: `?ProcessPluginMessage@BrowserToolThreadWindow@@AEAAJPEBUPluginMessageInfo@@@Z`
- size: `1054`
- prototype: `__int64 __fastcall(BrowserToolThreadWindow *__hidden this, const struct PluginMessageInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180008dc0`

## callees

- `0x180003858`
- `0x180007f08`
- `0x180008990`
- `0x180009278`
- `0x18000bb44`
- `0x180010dac`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008c58`
- `OLEAUT32!__imp_SysAllocString` at `0x180008cd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180008d5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180008c58`
- `OLEAUT32!__imp_SysAllocString` at `0x180008cd6`
- `OLEAUT32!__imp_SysAllocString` at `0x180008d5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c94`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c94`
- `USER32!DestroyWindow` at `0x1800089f7`
- `USER32!DestroyWindow` at `0x1800089f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrowserToolThreadWindow::ProcessPluginMessage(
        BrowserToolThreadWindow *this,
        const struct PluginMessageInfo *a2)
{
  int v5; // ecx
  BrowserToolWindow *v6; // rcx
  __int64 v7; // r10
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  void (__fastcall *v13)(_QWORD); // rax
  __int64 v14; // rdx
  void (__fastcall *v15)(_QWORD, __int64); // rax
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  __int64 v24; // rax
  volatile signed __int32 *v25; // rbx
  const OLECHAR *v26; // rcx
  OLECHAR *v27; // rbx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  const OLECHAR *v32; // rcx
  unsigned int v33; // ebx
  const OLECHAR *v34; // rcx
  __int64 v35; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v36; // [rsp+38h] [rbp-10h]
  OLECHAR *v37; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( FrameWindow::s_isDestroying && (*((_DWORD *)a2 + 2) & 0xFFFFFFF7) != 0 || *((_BYTE *)this + 136) )
    return 0;
  v5 = *((_DWORD *)a2 + 2);
  if ( !v5 )
  {
    *((_BYTE *)this + 136) = 1;
    v6 = (BrowserToolWindow *)*((_QWORD *)this + 12);
    if ( v6 )
      BrowserToolWindow::Cleanup(v6);
    DestroyWindow(*((HWND *)this + 1));
    return 0;
  }
  v7 = *((_QWORD *)this + 19);
  if ( !v7 )
    return 2147947423LL;
  if ( v5 <= 14 )
  {
    if ( v5 == 14 )
    {
      v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 136LL);
      goto LABEL_81;
    }
    if ( v5 > 8 )
    {
      v16 = v5 - 9;
      if ( !v16 )
      {
        v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 96LL);
        goto LABEL_81;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( !v18 )
        {
          v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 112LL);
          goto LABEL_81;
        }
        v19 = v18 - 1;
        if ( !v19 )
        {
          v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 120LL);
          goto LABEL_81;
        }
        if ( v19 == 1 )
        {
          v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 128LL);
          goto LABEL_81;
        }
        return 0;
      }
      v14 = *((unsigned __int8 *)a2 + 16);
      v15 = *(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v7 + 104LL);
    }
    else
    {
      if ( v5 == 8 )
      {
        v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 88LL);
        goto LABEL_81;
      }
      v8 = v5 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 2;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              v12 = v11 - 1;
              if ( !v12 )
              {
                v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 72LL);
                goto LABEL_81;
              }
              if ( v12 == 1 )
              {
                v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 80LL);
LABEL_81:
                v13(*((_QWORD *)this + 19));
                return 0;
              }
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v7 + 64LL))(
                *((_QWORD *)this + 19),
                *((unsigned int *)a2 + 4),
                *((unsigned int *)a2 + 5));
            }
          }
          else
          {
            LOWORD(v37) = 0;
            (*(void (__fastcall **)(__int64, _QWORD, _QWORD, OLECHAR **))(*(_QWORD *)v7 + 224LL))(
              v7,
              *((unsigned __int8 *)a2 + 16),
              *((unsigned __int8 *)a2 + 17),
              &v37);
          }
        }
        else
        {
          BrowserToolThreadWindow::TabInto(this);
        }
        return 0;
      }
      v14 = *((unsigned int *)a2 + 3);
      v15 = *(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v7 + 240LL);
    }
LABEL_28:
    v15(*((_QWORD *)this + 19), v14);
    return 0;
  }
  if ( v5 <= 20 )
  {
    if ( v5 != 20 )
    {
      v20 = v5 - 15;
      if ( !v20 )
      {
        v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 144LL);
        goto LABEL_81;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 152LL);
        goto LABEL_81;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 160LL);
        goto LABEL_81;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v24 = *((_QWORD *)a2 + 3);
        if ( v24 )
          _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
        v35 = *((_QWORD *)a2 + 2);
        v36 = (volatile signed __int32 *)*((_QWORD *)a2 + 3);
        v25 = v36;
        BrowserToolThreadWindow::FireJsonMessage(this, &v35);
        if ( v25 )
        {
          if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        return 0;
      }
      if ( v23 != 1 )
        return 0;
      v14 = *((unsigned __int8 *)a2 + 16);
      v15 = *(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v7 + 176LL);
      goto LABEL_28;
    }
    v26 = (const OLECHAR *)*((_QWORD *)a2 + 2);
    if ( !v26 )
    {
      v27 = 0;
      v37 = 0;
LABEL_62:
      (*(void (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD))(**((_QWORD **)this + 19) + 184LL))(
        *((_QWORD *)this + 19),
        v27,
        *((unsigned int *)a2 + 6),
        *((unsigned int *)a2 + 7));
LABEL_63:
      SysFreeString(v27);
      return 0;
    }
    v27 = SysAllocString(v26);
    v37 = v27;
    if ( v27 )
      goto LABEL_62;
LABEL_83:
    ATL::AtlThrowImpl(-2147024882);
  }
  v28 = v5 - 21;
  if ( !v28 )
  {
    v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 192LL);
    goto LABEL_81;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    v13 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 200LL);
    goto LABEL_81;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    v34 = (const OLECHAR *)*((_QWORD *)a2 + 2);
    if ( v34 )
    {
      v27 = SysAllocString(v34);
      v37 = v27;
      if ( !v27 )
        goto LABEL_83;
    }
    else
    {
      v27 = 0;
      v37 = 0;
    }
    (*(void (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 19) + 208LL))(*((_QWORD *)this + 19), v27);
    goto LABEL_63;
  }
  v31 = v30 - 2;
  if ( !v31 )
  {
    v33 = *((_DWORD *)a2 + 4);
    BrowserToolWindow::SetCurrentZoomLevel(*((BrowserToolWindow **)this + 12), v33);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 19) + 232LL))(*((_QWORD *)this + 19), v33);
    return 0;
  }
  if ( v31 == 1 )
  {
    v32 = (const OLECHAR *)*((_QWORD *)a2 + 2);
    if ( v32 )
    {
      v27 = SysAllocString(v32);
      v37 = v27;
      if ( !v27 )
        goto LABEL_83;
    }
    else
    {
      v27 = 0;
      v37 = 0;
    }
    (*(void (__fastcall **)(_QWORD, OLECHAR *))(**((_QWORD **)this + 19) + 216LL))(*((_QWORD *)this + 19), v27);
    goto LABEL_63;
  }
  return 0;
}

```

## disassembly

```asm
0x180008990  mov     [rsp+arg_0], rbx
0x180008995  mov     [rsp+arg_10], rsi
0x18000899a  push    rdi
0x18000899b  sub     rsp, 40h
0x18000899f  mov     rdi, rdx
0x1800089a2  mov     rsi, rcx
0x1800089a5  test    rdx, rdx
0x1800089a8  jnz     short loc_1800089B4
0x1800089aa  mov     eax, 80070057h
0x1800089af  jmp     loc_180008D93
0x1800089b4  cmp     cs:?s_isDestroying@FrameWindow@@2_NA, 0; bool FrameWindow::s_isDestroying
0x1800089bb  jz      short loc_1800089CA
0x1800089bd  test    dword ptr [rdx+8], 0FFFFFFF7h
0x1800089c4  jnz     loc_180008D91
0x1800089ca  cmp     byte ptr [rcx+88h], 0
0x1800089d1  jnz     loc_180008D91
0x1800089d7  mov     ecx, [rdx+8]
0x1800089da  test    ecx, ecx
0x1800089dc  jnz     short loc_180008A02
0x1800089de  mov     byte ptr [rsi+88h], 1
0x1800089e5  mov     rcx, [rsi+60h]; this
0x1800089e9  test    rcx, rcx
0x1800089ec  jz      short loc_1800089F3
0x1800089ee  call    ?Cleanup@BrowserToolWindow@@QEAAXXZ; BrowserToolWindow::Cleanup(void)
0x1800089f3  mov     rcx, [rsi+8]; hWnd
0x1800089f7  call    cs:__imp_DestroyWindow
0x1800089fd  jmp     loc_180008D91
0x180008a02  mov     r10, [rsi+98h]
0x180008a09  test    r10, r10
0x180008a0c  jnz     short loc_180008A18
0x180008a0e  mov     eax, 8007139Fh
0x180008a13  jmp     loc_180008D93
0x180008a18  cmp     ecx, 0Eh
0x180008a1b  jg      loc_180008B5A
0x180008a21  jz      loc_180008B4B
0x180008a27  cmp     ecx, 8
0x180008a2a  jg      loc_180008AEE
0x180008a30  jz      loc_180008AE2
0x180008a36  sub     ecx, 1
0x180008a39  jz      loc_180008AC8
0x180008a3f  sub     ecx, 1
0x180008a42  jz      short loc_180008ABB
0x180008a44  sub     ecx, 2
0x180008a47  jz      short loc_180008A8F
0x180008a49  sub     ecx, 1
0x180008a4c  jz      short loc_180008A74
0x180008a4e  sub     ecx, 1
0x180008a51  jz      short loc_180008A68
0x180008a53  cmp     ecx, 1
0x180008a56  jnz     loc_180008D91
0x180008a5c  mov     rax, [r10]
0x180008a5f  mov     rax, [rax+50h]
0x180008a63  jmp     loc_180008D89
0x180008a68  mov     rax, [r10]
0x180008a6b  mov     rax, [rax+48h]
0x180008a6f  jmp     loc_180008D89
0x180008a74  mov     rax, [r10]
0x180008a77  mov     r8d, [rdx+14h]
0x180008a7b  mov     edx, [rdx+10h]
0x180008a7e  mov     rcx, r10
0x180008a81  mov     rax, [rax+40h]
0x180008a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8a  jmp     loc_180008D91
0x180008a8f  xor     eax, eax
0x180008a91  mov     word ptr [rsp+48h+arg_8], ax
0x180008a96  mov     rax, [r10]
0x180008a99  movzx   r8d, byte ptr [rdx+11h]
0x180008a9e  movzx   edx, byte ptr [rdx+10h]
0x180008aa2  lea     r9, [rsp+48h+arg_8]
0x180008aa7  mov     rcx, r10
0x180008aaa  mov     rax, [rax+0E0h]
0x180008ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab6  jmp     loc_180008D91
0x180008abb  mov     rcx, rsi; this
0x180008abe  call    ?TabInto@BrowserToolThreadWindow@@AEAAJXZ; BrowserToolThreadWindow::TabInto(void)
0x180008ac3  jmp     loc_180008D91
0x180008ac8  mov     rax, [r10]
0x180008acb  mov     edx, [rdx+0Ch]
0x180008ace  mov     rax, [rax+0F0h]
0x180008ad5  mov     rcx, r10
0x180008ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008add  jmp     loc_180008D91
0x180008ae2  mov     rax, [r10]
0x180008ae5  mov     rax, [rax+58h]
0x180008ae9  jmp     loc_180008D89
0x180008aee  sub     ecx, 9
0x180008af1  jz      short loc_180008B3F
0x180008af3  sub     ecx, 1
0x180008af6  jz      short loc_180008B32
0x180008af8  sub     ecx, 1
0x180008afb  jz      short loc_180008B26
0x180008afd  sub     ecx, 1
0x180008b00  jz      short loc_180008B1A
0x180008b02  cmp     ecx, 1
0x180008b05  jnz     loc_180008D91
0x180008b0b  mov     rax, [r10]
0x180008b0e  mov     rax, [rax+80h]
0x180008b15  jmp     loc_180008D89
0x180008b1a  mov     rax, [r10]
0x180008b1d  mov     rax, [rax+78h]
0x180008b21  jmp     loc_180008D89
0x180008b26  mov     rax, [r10]
0x180008b29  mov     rax, [rax+70h]
0x180008b2d  jmp     loc_180008D89
0x180008b32  mov     rax, [r10]
0x180008b35  movzx   edx, byte ptr [rdx+10h]
0x180008b39  mov     rax, [rax+68h]
0x180008b3d  jmp     short loc_180008AD5
0x180008b3f  mov     rax, [r10]
0x180008b42  mov     rax, [rax+60h]
0x180008b46  jmp     loc_180008D89
0x180008b4b  mov     rax, [r10]
0x180008b4e  mov     rax, [rax+88h]
0x180008b55  jmp     loc_180008D89
0x180008b5a  cmp     ecx, 14h
0x180008b5d  jg      loc_180008C9F
0x180008b63  jz      loc_180008C46
0x180008b69  sub     ecx, 0Fh
0x180008b6c  jz      loc_180008C37
0x180008b72  sub     ecx, 1
0x180008b75  jz      loc_180008C28
0x180008b7b  sub     ecx, 1
0x180008b7e  jz      loc_180008C19
0x180008b84  sub     ecx, 1
0x180008b87  jz      short loc_180008BA5
0x180008b89  cmp     ecx, 1
0x180008b8c  jnz     loc_180008D91
0x180008b92  mov     rax, [r10]
0x180008b95  movzx   edx, byte ptr [rdx+10h]
0x180008b99  mov     rax, [rax+0B0h]
0x180008ba0  jmp     loc_180008AD5
0x180008ba5  mov     rax, [rdx+18h]
0x180008ba9  test    rax, rax
0x180008bac  jz      short loc_180008BB2
0x180008bae  lock inc dword ptr [rax+8]
0x180008bb2  mov     rax, [rdx+10h]
0x180008bb6  mov     [rsp+48h+var_18], rax
0x180008bbb  mov     rbx, [rdx+18h]
0x180008bbf  mov     [rsp+48h+var_10], rbx
0x180008bc4  lea     rdx, [rsp+48h+var_18]
0x180008bc9  mov     rcx, rsi
0x180008bcc  call    ?FireJsonMessage@BrowserToolThreadWindow@@AEAAJAEAV?$shared_ptr@UPluginPendingMessage@@@std@@@Z; BrowserToolThreadWindow::FireJsonMessage(std::shared_ptr<PluginPendingMessage> &)
0x180008bd1  nop
0x180008bd2  test    rbx, rbx
0x180008bd5  jz      loc_180008D91
0x180008bdb  or      edi, 0FFFFFFFFh
0x180008bde  mov     eax, edi
0x180008be0  lock xadd [rbx+8], eax
0x180008be5  add     eax, edi
0x180008be7  jnz     loc_180008D91
0x180008bed  mov     rax, [rbx]
0x180008bf0  mov     rcx, rbx
0x180008bf3  mov     rax, [rax]
0x180008bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bfb  mov     eax, edi
0x180008bfd  lock xadd [rbx+0Ch], eax
0x180008c02  add     eax, edi
0x180008c04  jnz     loc_180008D91
0x180008c0a  mov     rax, [rbx]
0x180008c0d  mov     rcx, rbx
0x180008c10  mov     rax, [rax+8]
0x180008c14  jmp     loc_180008D8C
0x180008c19  mov     rax, [r10]
0x180008c1c  mov     rax, [rax+0A0h]
0x180008c23  jmp     loc_180008D89
0x180008c28  mov     rax, [r10]
0x180008c2b  mov     rax, [rax+98h]
0x180008c32  jmp     loc_180008D89
0x180008c37  mov     rax, [r10]
0x180008c3a  mov     rax, [rax+90h]
0x180008c41  jmp     loc_180008D89
0x180008c46  mov     rcx, [rdx+10h]; psz
0x180008c4a  test    rcx, rcx
0x180008c4d  jnz     short loc_180008C58
0x180008c4f  xor     ebx, ebx
0x180008c51  mov     [rsp+48h+arg_8], rbx
0x180008c56  jmp     short loc_180008C6F
0x180008c58  call    cs:__imp_SysAllocString
0x180008c5e  mov     rbx, rax
0x180008c61  mov     [rsp+48h+arg_8], rax
0x180008c66  test    rax, rax
0x180008c69  jz      loc_180008DA3
0x180008c6f  mov     rcx, [rsi+98h]
0x180008c76  mov     rax, [rcx]
0x180008c79  mov     r9d, [rdi+1Ch]
0x180008c7d  mov     r8d, [rdi+18h]
0x180008c81  mov     rdx, rbx
0x180008c84  mov     rax, [rax+0B8h]
0x180008c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c90  nop
0x180008c91  mov     rcx, rbx; bstrString
0x180008c94  call    cs:__imp_SysFreeString
0x180008c9a  jmp     loc_180008D91
0x180008c9f  sub     ecx, 15h
0x180008ca2  jz      loc_180008D7F
0x180008ca8  sub     ecx, 1
0x180008cab  jz      loc_180008D73
0x180008cb1  sub     ecx, 1
0x180008cb4  jz      short loc_180008D2F
0x180008cb6  sub     ecx, 2
0x180008cb9  jz      short loc_180008D09
0x180008cbb  cmp     ecx, 1
0x180008cbe  jnz     loc_180008D91
0x180008cc4  mov     rcx, [rdx+10h]; psz
0x180008cc8  test    rcx, rcx
0x180008ccb  jnz     short loc_180008CD6
0x180008ccd  xor     ebx, ebx
0x180008ccf  mov     [rsp+48h+arg_8], rbx
0x180008cd4  jmp     short loc_180008CED
0x180008cd6  call    cs:__imp_SysAllocString
0x180008cdc  mov     rbx, rax
0x180008cdf  mov     [rsp+48h+arg_8], rax
0x180008ce4  test    rax, rax
0x180008ce7  jz      loc_180008DA3
0x180008ced  mov     rcx, [rsi+98h]
0x180008cf4  mov     rax, [rcx]
0x180008cf7  mov     rdx, rbx
0x180008cfa  mov     rax, [rax+0D8h]
0x180008d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d06  nop
0x180008d07  jmp     short loc_180008C91
0x180008d09  mov     ebx, [rdx+10h]
0x180008d0c  mov     edx, ebx; int
0x180008d0e  mov     rcx, [rsi+60h]; this
0x180008d12  call    ?SetCurrentZoomLevel@BrowserToolWindow@@QEAAJH@Z; BrowserToolWindow::SetCurrentZoomLevel(int)
0x180008d17  mov     rcx, [rsi+98h]
0x180008d1e  mov     rax, [rcx]
0x180008d21  mov     edx, ebx
0x180008d23  mov     rax, [rax+0E8h]
0x180008d2a  jmp     loc_180008AD8
0x180008d2f  mov     rcx, [rdx+10h]; psz
0x180008d33  test    rcx, rcx
0x180008d36  jnz     short loc_180008D5E
0x180008d38  xor     ebx, ebx
0x180008d3a  mov     [rsp+48h+arg_8], rbx
0x180008d3f  mov     rcx, [rsi+98h]
0x180008d46  mov     rax, [rcx]
0x180008d49  mov     rdx, rbx
0x180008d4c  mov     rax, [rax+0D0h]
0x180008d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d58  nop
0x180008d59  jmp     loc_180008C91
0x180008d5e  call    cs:__imp_SysAllocString
0x180008d64  mov     rbx, rax
0x180008d67  mov     [rsp+48h+arg_8], rax
0x180008d6c  test    rax, rax
0x180008d6f  jz      short loc_180008DA3
0x180008d71  jmp     short loc_180008D3F
0x180008d73  mov     rax, [r10]
0x180008d76  mov     rax, [rax+0C8h]
0x180008d7d  jmp     short loc_180008D89
0x180008d7f  mov     rax, [r10]
0x180008d82  mov     rax, [rax+0C0h]
0x180008d89  mov     rcx, r10
0x180008d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d91  xor     eax, eax
0x180008d93  mov     rbx, [rsp+48h+arg_0]
0x180008d98  mov     rsi, [rsp+48h+arg_10]
0x180008d9d  add     rsp, 40h
0x180008da1  pop     rdi
0x180008da2  retn
0x180008da3  mov     ecx, 8007000Eh; int
0x180008da8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
