# Art::TextTabsFlexDlgRunner::Init(void)

- ea: `0x180a07f78`
- end: `0x180a08193`
- name: `?Init@TextTabsFlexDlgRunner@Art@@AEAAXXZ`
- size: `539`
- prototype: `void __fastcall(Art::TextTabsFlexDlgRunner *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180a07934`

## callees

- `0x180279050`
- `0x1802a23d0`
- `0x1802d56d0`
- `0x1809c3010`
- `0x180a07f78`
- `0x180a085b4`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a07fce`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x180a07fce`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x180a08016`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x180a08016`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x180a08053`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x180a08053`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a07f8a`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x180a07f8a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08047`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a080ad`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08119`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08179`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08047`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a080ad`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08119`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x180a08179`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a080eb`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0814b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a080eb`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x180a0814b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a07ff2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a080d2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a08135`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a07ff2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a080d2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180a08135`

## pseudocode

```c
void __fastcall Art::TextTabsFlexDlgRunner::Init(Art::TextTabsFlexDlgRunner *this)
{
  int inited; // eax
  struct IDataSource **v3; // r9
  __int64 *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rsi
  bool v7; // al
  struct FlexUI::FlexList *v8; // rcx
  char v9; // al
  struct FlexUI::FlexList *v10; // rcx
  char v11; // si
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // rbx
  struct FlexUI::FlexList *v15; // [rsp+58h] [rbp+28h] BYREF
  NetUI::BaseValue *v16; // [rsp+60h] [rbp+30h] BYREF

  inited = MsoHrInitNetUI();
  if ( inited < 0 )
  {
    Ofc::CHResultException::ThrowTag(inited, 0x2348408Fu);
    __debugbreak();
  }
  v4 = (__int64 *)((char *)this + 40);
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *v4 = 0;
  if ( !FlexUI::MsoCreateFlexDataSource((FlexUI *)0x13A0, 134226432, (_DWORD)this + 40, v3) )
  {
    Ofc::CAbortException::ThrowTag(0, 591937678);
    __debugbreak();
  }
  v6 = *v4;
  if ( !*v4 )
  {
    MsoShipAssertTagProc(7997250);
    goto LABEL_22;
  }
  v16 = 0;
  v15 = 0;
  v7 = FlexUI::FlexList::Create(5u, &v15);
  v8 = v15;
  if ( !v7 )
  {
    if ( !v15 )
      goto LABEL_12;
    goto LABEL_11;
  }
  FlexUI::FlexValue::CreateList(v15, (struct FlexUI::FlexValueSP *)&v16);
  if ( !v16 )
  {
    v8 = v15;
    if ( !v15 )
      goto LABEL_22;
LABEL_11:
    v15 = 0;
    (*(void (__fastcall **)(struct FlexUI::FlexList *))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_12:
    if ( v16 )
      NetUI::BaseValue::Release(v16);
    goto LABEL_22;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 48LL))(v6, 0, 6);
  v10 = v15;
  v11 = v9;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(struct FlexUI::FlexList *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v16 )
    NetUI::BaseValue::Release(v16);
  if ( !v11 )
  {
LABEL_22:
    Ofc::CAbortException::ThrowTag(0, 591937677);
    __debugbreak();
  }
  v12 = *v4;
  if ( *v4 )
  {
    v15 = 0;
    FlexUI::FlexValue::CreateInt32(51206400, (struct FlexUI::FlexValueSP *)&v15);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v12 + 48LL))(v12, 0, 4);
      if ( v15 )
        NetUI::BaseValue::Release(v15);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  v13 = sub_1809C3010((char *)this + 80);
  v14 = *v4;
  if ( v14 )
  {
    v15 = 0;
    FlexUI::FlexValue::CreateInt32(v13, (struct FlexUI::FlexValueSP *)&v15);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 48LL))(v14, 0, 8);
      if ( v15 )
        NetUI::BaseValue::Release(v15);
    }
  }
  else
  {
    MsoShipAssertTagProc(7997248);
  }
  Art::TextTabsFlexDlgRunner::RefreshDialogData(this);
}

```

## disassembly

```asm
0x180a07f78  mov     [rsp-18h+arg_0], rbx
0x180a07f7d  push    rbp
0x180a07f7e  push    rsi
0x180a07f7f  push    rdi
0x180a07f80  mov     rbp, rsp
0x180a07f83  sub     rsp, 30h
0x180a07f87  mov     rdi, rcx
0x180a07f8a  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x180a07f90  test    eax, eax
0x180a07f92  jns     short loc_180A07FA1
0x180a07f94  mov     edx, 2348408Fh; unsigned int
0x180a07f99  mov     ecx, eax; int
0x180a07f9b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180a07fa0  int     3; Trap to Debugger
0x180a07fa1  lea     rbx, [rdi+28h]
0x180a07fa5  mov     rcx, [rbx]
0x180a07fa8  test    rcx, rcx
0x180a07fab  jz      short loc_180A07FBA
0x180a07fad  mov     rax, [rcx]
0x180a07fb0  mov     rax, [rax+10h]
0x180a07fb4  call    cs:__guard_dispatch_icall_fptr
0x180a07fba  mov     r8, rbx
0x180a07fbd  mov     qword ptr [rbx], 0
0x180a07fc4  mov     edx, 8002200h
0x180a07fc9  mov     ecx, 13A0h
0x180a07fce  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x180a07fd4  test    al, al
0x180a07fd6  jnz     short loc_180A07FE5
0x180a07fd8  mov     edx, 2348408Eh
0x180a07fdd  xor     ecx, ecx
0x180a07fdf  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x180a07fe4  int     3; Trap to Debugger
0x180a07fe5  mov     rsi, [rbx]
0x180a07fe8  test    rsi, rsi
0x180a07feb  jnz     short loc_180A07FFD
0x180a07fed  mov     ecx, 7A0742h
0x180a07ff2  call    cs:__imp_MsoShipAssertTagProc
0x180a07ff8  jmp     loc_180A080B8
0x180a07ffd  lea     rdx, [rbp+arg_8]
0x180a08001  mov     [rbp+arg_10], 0
0x180a08009  mov     ecx, 5
0x180a0800e  mov     [rbp+arg_8], 0
0x180a08016  call    cs:__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z; FlexUI::FlexList::Create(uint,FlexUI::FlexList * *)
0x180a0801c  mov     rcx, [rbp+arg_8]
0x180a08020  test    al, al
0x180a08022  jnz     short loc_180A0804F
0x180a08024  test    rcx, rcx
0x180a08027  jz      short loc_180A0803E
0x180a08029  mov     [rbp+arg_8], 0
0x180a08031  mov     rax, [rcx]
0x180a08034  mov     rax, [rax+10h]
0x180a08038  call    cs:__guard_dispatch_icall_fptr
0x180a0803e  mov     rcx, [rbp+arg_10]
0x180a08042  test    rcx, rcx
0x180a08045  jz      short loc_180A080B8
0x180a08047  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a0804d  jmp     short loc_180A080B8
0x180a0804f  lea     rdx, [rbp+arg_10]
0x180a08053  call    cs:__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateList(FlexUI::IFlexList *,FlexUI::FlexValueSP &)
0x180a08059  mov     r9, [rbp+arg_10]
0x180a0805d  test    r9, r9
0x180a08060  jnz     short loc_180A0806D
0x180a08062  mov     rcx, [rbp+arg_8]
0x180a08066  test    rcx, rcx
0x180a08069  jz      short loc_180A080B8
0x180a0806b  jmp     short loc_180A08029
0x180a0806d  mov     rax, [rsi]
0x180a08070  xor     edx, edx
0x180a08072  mov     rcx, rsi
0x180a08075  mov     rax, [rax+30h]
0x180a08079  lea     r8d, [rdx+6]
0x180a0807d  call    cs:__guard_dispatch_icall_fptr
0x180a08083  mov     rcx, [rbp+arg_8]
0x180a08087  mov     sil, al
0x180a0808a  test    rcx, rcx
0x180a0808d  jz      short loc_180A080A4
0x180a0808f  mov     [rbp+arg_8], 0
0x180a08097  mov     rdx, [rcx]
0x180a0809a  mov     rax, [rdx+10h]
0x180a0809e  call    cs:__guard_dispatch_icall_fptr
0x180a080a4  mov     rcx, [rbp+arg_10]
0x180a080a8  test    rcx, rcx
0x180a080ab  jz      short loc_180A080B3
0x180a080ad  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a080b3  test    sil, sil
0x180a080b6  jnz     short loc_180A080C5
0x180a080b8  mov     edx, 2348408Dh
0x180a080bd  xor     ecx, ecx
0x180a080bf  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x180a080c4  int     3; Trap to Debugger
0x180a080c5  mov     rsi, [rbx]
0x180a080c8  test    rsi, rsi
0x180a080cb  jnz     short loc_180A080DA
0x180a080cd  mov     ecx, 7A0740h
0x180a080d2  call    cs:__imp_MsoShipAssertTagProc
0x180a080d8  jmp     short loc_180A0811F
0x180a080da  lea     rdx, [rbp+arg_8]
0x180a080de  mov     [rbp+arg_8], 0
0x180a080e6  mov     ecx, 30D5900h
0x180a080eb  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a080f1  mov     r9, [rbp+arg_8]
0x180a080f5  test    r9, r9
0x180a080f8  jz      short loc_180A0811F
0x180a080fa  mov     rax, [rsi]
0x180a080fd  xor     edx, edx
0x180a080ff  mov     rcx, rsi
0x180a08102  mov     rax, [rax+30h]
0x180a08106  lea     r8d, [rdx+4]
0x180a0810a  call    cs:__guard_dispatch_icall_fptr
0x180a08110  mov     rcx, [rbp+arg_8]
0x180a08114  test    rcx, rcx
0x180a08117  jz      short loc_180A0811F
0x180a08119  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a0811f  lea     rcx, [rdi+50h]
0x180a08123  call    sub_1809C3010
0x180a08128  mov     rbx, [rbx]
0x180a0812b  test    rbx, rbx
0x180a0812e  jnz     short loc_180A0813D
0x180a08130  mov     ecx, 7A0740h
0x180a08135  call    cs:__imp_MsoShipAssertTagProc
0x180a0813b  jmp     short loc_180A0817F
0x180a0813d  lea     rdx, [rbp+arg_8]
0x180a08141  mov     [rbp+arg_8], 0
0x180a08149  mov     ecx, eax
0x180a0814b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180a08151  mov     r9, [rbp+arg_8]
0x180a08155  test    r9, r9
0x180a08158  jz      short loc_180A0817F
0x180a0815a  mov     rax, [rbx]
0x180a0815d  xor     edx, edx
0x180a0815f  mov     rcx, rbx
0x180a08162  mov     rax, [rax+30h]
0x180a08166  lea     r8d, [rdx+8]
0x180a0816a  call    cs:__guard_dispatch_icall_fptr
0x180a08170  mov     rcx, [rbp+arg_8]
0x180a08174  test    rcx, rcx
0x180a08177  jz      short loc_180A0817F
0x180a08179  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180a0817f  mov     rcx, rdi; this
0x180a08182  mov     rbx, [rsp+30h+arg_0]
0x180a08187  add     rsp, 30h
0x180a0818b  pop     rdi
0x180a0818c  pop     rsi
0x180a0818d  pop     rbp
0x180a0818e  jmp     ?RefreshDialogData@TextTabsFlexDlgRunner@Art@@AEAAXXZ; Art::TextTabsFlexDlgRunner::RefreshDialogData(void)
```
