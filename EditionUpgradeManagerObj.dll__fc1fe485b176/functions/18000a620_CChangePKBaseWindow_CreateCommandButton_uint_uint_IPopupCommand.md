# CChangePKBaseWindow::CreateCommandButton(uint,uint,IPopupCommand * *)

- ea: `0x18000a620`
- end: `0x18000a6c6`
- name: `?CreateCommandButton@CChangePKBaseWindow@@UEAAJIIPEAPEAUIPopupCommand@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(CChangePKBaseWindow *this, int, int, struct IPopupCommand **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a1fc`
- `0x18000a620`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CChangePKBaseWindow::CreateCommandButton(
        CChangePKBaseWindow *this,
        int a2,
        int a3,
        struct IPopupCommand **a4)
{
  unsigned int v4; // ebx
  struct IPopupCommand **v6; // rax
  struct IPopupCommand *v7; // rsi
  __int64 v8; // rcx
  CChangePKBaseWindow *v10; // [rsp+30h] [rbp-28h] BYREF
  __int64 (__fastcall *v11[4])(struct IPopupWindow *, struct IPopupCommand *, void *); // [rsp+38h] [rbp-20h] BYREF
  int v12; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = a3;
  v12 = a2;
  v4 = 0;
  if ( a4 )
  {
    v10 = this;
    v11[0] = CChangePKBaseWindow::sOnCommand;
    v6 = (struct IPopupCommand **)Microsoft::WRL::Details::Make<CLicensingUIPopupCommand,HINSTANCE__ * &,long (*)(IPopupWindow *,IPopupCommand *,void *),void *,unsigned int &,unsigned int &>(
                                    &v14,
                                    (__int64 *)this + 4,
                                    (__int64 *)v11,
                                    (__int64 *)&v10,
                                    &v12,
                                    &v13);
    v7 = *v6;
    *v6 = 0;
    v8 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( v7 )
    {
      *a4 = v7;
      goto LABEL_9;
    }
    v4 = -2147024882;
  }
  else
  {
    v4 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18000a620  mov     [rsp+arg_10], r8d
0x18000a625  mov     [rsp+arg_8], edx
0x18000a629  push    rbx
0x18000a62a  push    rsi
0x18000a62b  push    rdi
0x18000a62c  sub     rsp, 40h
0x18000a630  xor     ebx, ebx
0x18000a632  mov     rdi, r9
0x18000a635  test    r9, r9
0x18000a638  jnz     short loc_18000A648
0x18000a63a  mov     ebx, 80070057h
0x18000a63f  mov     ecx, ebx
0x18000a641  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a646  jmp     short loc_18000A6B5
0x18000a648  lea     rax, ?sOnCommand@CChangePKBaseWindow@@SAJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z; CChangePKBaseWindow::sOnCommand(IPopupWindow *,IPopupCommand *,void *)
0x18000a64f  mov     [rsp+58h+var_28], rcx
0x18000a654  mov     [rsp+58h+var_20], rax
0x18000a659  lea     rdx, [rcx+20h]
0x18000a65d  lea     rax, [rsp+58h+arg_10]
0x18000a662  mov     [rsp+58h+var_30], rax
0x18000a667  lea     r9, [rsp+58h+var_28]
0x18000a66c  lea     rax, [rsp+58h+arg_8]
0x18000a671  lea     r8, [rsp+58h+var_20]
0x18000a676  mov     [rsp+58h+var_38], rax
0x18000a67b  lea     rcx, [rsp+58h+arg_18]
0x18000a680  call    ??$Make@VCLicensingUIPopupCommand@@AEAPEAUHINSTANCE__@@P6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@ZPEAXAEAIAEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCLicensingUIPopupCommand@@@12@AEAPEAUHINSTANCE__@@$$QEAP6AJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z$$QEAPEAXAEAI6@Z; Microsoft::WRL::Details::Make<CLicensingUIPopupCommand,HINSTANCE__ * &,long (*)(IPopupWindow *,IPopupCommand *,void *),void *,uint &,uint &>(HINSTANCE__ * &,long (*&&)(IPopupWindow *,IPopupCommand *,void *),void * &&,uint &,uint &)
0x18000a685  mov     rsi, [rax]
0x18000a688  mov     [rax], rbx
0x18000a68b  mov     rcx, [rsp+58h+arg_18]
0x18000a690  test    rcx, rcx
0x18000a693  jz      short loc_18000A6A6
0x18000a695  mov     [rsp+58h+arg_18], rbx
0x18000a69a  mov     rax, [rcx]
0x18000a69d  mov     rax, [rax+10h]
0x18000a6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a6  test    rsi, rsi
0x18000a6a9  jnz     short loc_18000A6B2
0x18000a6ab  mov     ebx, 8007000Eh
0x18000a6b0  jmp     short loc_18000A63F
0x18000a6b2  mov     [rdi], rsi
0x18000a6b5  mov     ecx, ebx
0x18000a6b7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a6bc  mov     eax, ebx
0x18000a6be  add     rsp, 40h
0x18000a6c2  pop     rdi
0x18000a6c3  pop     rsi
0x18000a6c4  pop     rbx
0x18000a6c5  retn
```
