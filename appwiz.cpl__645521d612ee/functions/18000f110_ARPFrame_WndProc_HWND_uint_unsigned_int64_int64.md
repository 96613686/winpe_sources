# ARPFrame::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000f110`
- end: `0x18000f1fa`
- name: `?WndProc@ARPFrame@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `234`
- prototype: `__int64(ARPFrame *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x180008ad8`
- `0x18000aac4`
- `0x18000c0b8`
- `0x18000f110`
- `0x180059010`

## import_xrefs

- `USER32!LockWindowUpdate` at `0x18000f158`
- `USER32!LockWindowUpdate` at `0x18000f1bb`
- `USER32!LockWindowUpdate` at `0x18000f158`
- `USER32!LockWindowUpdate` at `0x18000f1bb`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000f199`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000f199`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x18000f1e1`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18000f14f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18000f14f`

## pseudocode

```c
__int64 __fastcall ARPFrame::WndProc(
        DirectUI::NativeHWNDHost **this,
        HWND a2,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5)
{
  HWND HWND; // rax
  DirectUI::DUIXmlParser *v10; // rbp
  DirectUI::NativeHWNDHost *v12; // [rsp+30h] [rbp-48h] BYREF

  if ( a3 == 26 )
  {
LABEL_4:
    HWND = DirectUI::NativeHWNDHost::GetHWND(this[34]);
    LockWindowUpdate(HWND);
    v10 = this[36];
    v12 = 0;
    if ( v10 )
    {
      (*((void (__fastcall **)(DirectUI::NativeHWNDHost **, DirectUI::NativeHWNDHost **))*this + 55))(this, &v12);
      this[36] = v12;
      DirectUI::DUIXmlParser::Destroy(v10);
      ARPFrame::ManageAnimations((ARPFrame *)this);
      TraverseTree<ClientPicker>(this, CalculateWidthCB, 0);
    }
    LockWindowUpdate(0);
    return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
  }
  if ( a3 != 83 )
  {
    if ( a3 != 794 )
      return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
    goto LABEL_4;
  }
  if ( a5 && *(_DWORD *)(a5 + 4) == 1 )
    ARPFrame::DoHelp((ARPFrame *)this);
  return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000f110  push    rbx
0x18000f112  push    rbp
0x18000f113  push    rsi
0x18000f114  push    rdi
0x18000f115  push    r14
0x18000f117  push    r15
0x18000f119  sub     rsp, 48h
0x18000f11d  mov     rsi, [rsp+78h+arg_20]
0x18000f125  mov     r14, r9
0x18000f128  mov     ebx, r8d
0x18000f12b  mov     r15, rdx
0x18000f12e  mov     rdi, rcx
0x18000f131  cmp     r8d, 1Ah
0x18000f135  jz      short loc_18000F148
0x18000f137  cmp     ebx, 53h ; 'S'
0x18000f13a  jz      loc_18000F1E8
0x18000f140  cmp     ebx, 31Ah
0x18000f146  jnz     short loc_18000F1C1
0x18000f148  mov     rcx, [rcx+110h]
0x18000f14f  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x18000f155  mov     rcx, rax; hWndLock
0x18000f158  call    cs:__imp_LockWindowUpdate
0x18000f15e  mov     rbp, [rdi+120h]
0x18000f165  mov     [rsp+78h+var_48], 0
0x18000f16e  test    rbp, rbp
0x18000f171  jz      short loc_18000F1B9
0x18000f173  mov     rax, [rdi]
0x18000f176  lea     rdx, [rsp+78h+var_48]
0x18000f17b  mov     rcx, rdi
0x18000f17e  mov     rax, [rax+1B8h]
0x18000f185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18a  mov     rax, [rsp+78h+var_48]
0x18000f18f  mov     rcx, rbp
0x18000f192  mov     [rdi+120h], rax
0x18000f199  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18000f19f  mov     rcx, rdi; this
0x18000f1a2  call    ?ManageAnimations@ARPFrame@@QEAAXXZ; ARPFrame::ManageAnimations(void)
0x18000f1a7  xor     r8d, r8d
0x18000f1aa  lea     rdx, ?CalculateWidthCB@@YAJPEAVClientPicker@@_J@Z; CalculateWidthCB(ClientPicker *,__int64)
0x18000f1b1  mov     rcx, rdi
0x18000f1b4  call    ??$TraverseTree@VClientPicker@@@@YAJPEAVElement@DirectUI@@P6AJPEAVClientPicker@@_J@Z2@Z; TraverseTree<ClientPicker>(DirectUI::Element *,long (*)(ClientPicker *,__int64),__int64)
0x18000f1b9  xor     ecx, ecx; hWndLock
0x18000f1bb  call    cs:__imp_LockWindowUpdate
0x18000f1c1  mov     r9, r14
0x18000f1c4  mov     [rsp+78h+arg_20], rsi
0x18000f1cc  mov     r8d, ebx
0x18000f1cf  mov     rdx, r15
0x18000f1d2  mov     rcx, rdi; this
0x18000f1d5  add     rsp, 48h
0x18000f1d9  pop     r15
0x18000f1db  pop     r14
0x18000f1dd  pop     rdi
0x18000f1de  pop     rsi
0x18000f1df  pop     rbp
0x18000f1e0  pop     rbx
0x18000f1e1  jmp     cs:__imp_?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z; DirectUI::HWNDElement::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000f1e8  test    rsi, rsi
0x18000f1eb  jz      short loc_18000F1C1
0x18000f1ed  cmp     dword ptr [rsi+4], 1
0x18000f1f1  jnz     short loc_18000F1C1
0x18000f1f3  call    ?DoHelp@ARPFrame@@QEAAXXZ; ARPFrame::DoHelp(void)
0x18000f1f8  jmp     short loc_18000F1C1
```
