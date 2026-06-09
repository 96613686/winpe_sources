# CSystemPopupWindow::_OnCommand(IPopupWindow *,IPopupCommand *,void *)

- ea: `0x1400086f0`
- end: `0x14000878a`
- name: `?_OnCommand@CSystemPopupWindow@@CAJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z`
- size: `154`
- prototype: `static int(struct IPopupWindow *, struct IPopupCommand *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001460`
- `0x1400080f4`
- `0x140008698`
- `0x1400086f0`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall CSystemPopupWindow::_OnCommand(
        struct IPopupWindow *a1,
        struct IPopupCommand *a2,
        CSystemPopupWindow *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // edi
  int v8; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *(_QWORD *)a2;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IPopupCommand *, int *))(v3 + 32))(a2, &v8);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v5,
      v8);
    return v6;
  }
  if ( !v8 )
  {
    *((_DWORD *)a3 + 2) = 1;
    goto LABEL_7;
  }
  if ( v8 == 1 )
  {
    *((_DWORD *)a3 + 2) = 0;
LABEL_7:
    CSystemPopupWindow::_DestroyWindow(a3);
  }
  return 0;
}

```

## disassembly

```asm
0x1400086f0  mov     [rsp+arg_0], rbx
0x1400086f5  push    rdi
0x1400086f6  sub     rsp, 30h
0x1400086fa  mov     rax, cs:__security_cookie
0x140008701  xor     rax, rsp
0x140008704  mov     [rsp+38h+var_10], rax
0x140008709  mov     rax, [rdx]
0x14000870c  mov     rcx, rdx
0x14000870f  lea     rdx, [rsp+38h+var_18]
0x140008714  mov     [rsp+38h+var_18], 0; int
0x14000871c  mov     rbx, r8
0x14000871f  mov     rax, [rax+20h]
0x140008723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008728  mov     edi, eax
0x14000872a  test    eax, eax
0x14000872c  jns     short loc_14000874B
0x14000872e  mov     rcx, [rsp+38h]; this
0x140008733  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x14000873a  mov     r9d, eax; char *
0x14000873d  mov     edx, 0A1h; void *
0x140008742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008747  mov     eax, edi
0x140008749  jmp     short loc_140008772
0x14000874b  mov     eax, [rsp+38h+var_18]
0x14000874f  test    eax, eax
0x140008751  jz      short loc_140008761
0x140008753  cmp     eax, 1
0x140008756  jnz     short loc_140008770
0x140008758  mov     dword ptr [rbx+8], 0
0x14000875f  jmp     short loc_140008768
0x140008761  mov     dword ptr [rbx+8], 1
0x140008768  mov     rcx, rbx; this
0x14000876b  call    ?_DestroyWindow@CSystemPopupWindow@@AEAAXXZ; CSystemPopupWindow::_DestroyWindow(void)
0x140008770  xor     eax, eax
0x140008772  mov     rcx, [rsp+38h+var_10]
0x140008777  xor     rcx, rsp; StackCookie
0x14000877a  call    __security_check_cookie
0x14000877f  mov     rbx, [rsp+38h+arg_0]
0x140008784  add     rsp, 30h
0x140008788  pop     rdi
0x140008789  retn
```
