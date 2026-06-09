# COCMFrame::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800338e0`
- end: `0x180033a13`
- name: `?WndProc@COCMFrame@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `307`
- prototype: `__int64 __fastcall(COCMFrame *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180031c80`
- `0x180032ce0`
- `0x1800338e0`
- `0x180059010`

## import_xrefs

- `USER32!LockWindowUpdate` at `0x18003399d`
- `USER32!LockWindowUpdate` at `0x1800339e6`
- `USER32!LockWindowUpdate` at `0x18003399d`
- `USER32!LockWindowUpdate` at `0x1800339e6`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x180033973`
- `DUI70!?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z` at `0x180033973`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800339de`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800339de`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x180033a0c`
- `DUI70!?DestroyWindow@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x180033951`
- `DUI70!?DestroyWindow@NativeHWNDHost@DirectUI@@QEAAXXZ` at `0x180033951`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180033994`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180033994`

## pseudocode

```c
__int64 __fastcall COCMFrame::WndProc(
        DirectUI::NativeHWNDHost **this,
        HWND a2,
        unsigned int a3,
        unsigned __int64 a4,
        __int64 a5)
{
  CWindowFeaturesData *v9; // rbx
  HWND v10; // rax
  HWND HWND; // rax
  DirectUI::DUIXmlParser *v12; // rbx
  DirectUI::NativeHWNDHost *v14; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v16; // [rsp+40h] [rbp-58h]

  if ( a3 == 26 )
  {
LABEL_11:
    HWND = DirectUI::NativeHWNDHost::GetHWND(this[32]);
    LockWindowUpdate(HWND);
    v12 = this[34];
    v14 = 0;
    if ( v12 )
    {
      (*((void (__fastcall **)(DirectUI::NativeHWNDHost **, DirectUI::NativeHWNDHost **))*this + 55))(this, &v14);
      this[34] = v14;
      DirectUI::DUIXmlParser::Destroy(v12);
    }
    LockWindowUpdate(0);
    return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
  }
  if ( a3 != 83 )
  {
    if ( a3 != 794 )
    {
      if ( a3 == 0x8000 )
      {
        v16 = COCMFrame::DataAvailableUICommand;
        DirectUI::Element::FireEvent((DirectUI::Element *)this, (struct DirectUI::Event *)v15, 1, 0);
      }
      else if ( a3 == 32769 )
      {
        v9 = this[42];
        v10 = (HWND)(*((__int64 (__fastcall **)(DirectUI::NativeHWNDHost **))*this + 45))(this);
        CWindowFeaturesData::InstallSelectedItems(v9, v10);
        DirectUI::NativeHWNDHost::DestroyWindow(this[32]);
      }
      return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
    }
    goto LABEL_11;
  }
  if ( a5 && *(_DWORD *)(a5 + 4) == 1 )
    COCMFrame::DoHelp((COCMFrame *)this);
  return DirectUI::HWNDElement::WndProc((DirectUI::HWNDElement *)this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800338e0  push    rbx
0x1800338e2  push    rbp
0x1800338e3  push    rsi
0x1800338e4  push    rdi
0x1800338e5  push    r14
0x1800338e7  push    r15
0x1800338e9  sub     rsp, 68h
0x1800338ed  mov     rsi, [rsp+98h+arg_20]
0x1800338f5  mov     eax, r8d
0x1800338f8  mov     r14, r9
0x1800338fb  mov     ebp, r8d
0x1800338fe  mov     r15, rdx
0x180033901  mov     rdi, rcx
0x180033904  sub     eax, 1Ah
0x180033907  jz      loc_18003398D
0x18003390d  sub     eax, 39h ; '9'
0x180033910  jz      short loc_18003397B
0x180033912  sub     eax, 2C7h
0x180033917  jz      short loc_18003398D
0x180033919  sub     eax, 7CE6h
0x18003391e  jz      short loc_18003395C
0x180033920  cmp     eax, 1
0x180033923  jnz     loc_1800339EC
0x180033929  mov     rax, [rcx]
0x18003392c  mov     rbx, [rcx+150h]
0x180033933  mov     rax, [rax+168h]
0x18003393a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003393f  mov     rdx, rax; HWND
0x180033942  mov     rcx, rbx; this
0x180033945  call    ?InstallSelectedItems@CWindowFeaturesData@@QEAAJPEAUHWND__@@@Z; CWindowFeaturesData::InstallSelectedItems(HWND__ *)
0x18003394a  mov     rcx, [rdi+100h]
0x180033951  call    cs:__imp_?DestroyWindow@NativeHWNDHost@DirectUI@@QEAAXXZ; DirectUI::NativeHWNDHost::DestroyWindow(void)
0x180033957  jmp     loc_1800339EC
0x18003395c  mov     rax, cs:?DataAvailableUICommand@COCMFrame@@0VUID@@A; UID COCMFrame::DataAvailableUICommand
0x180033963  lea     rdx, [rsp+98h+var_60]
0x180033968  xor     r9d, r9d
0x18003396b  mov     [rsp+98h+var_58], rax
0x180033970  mov     r8b, 1
0x180033973  call    cs:__imp_?FireEvent@Element@DirectUI@@QEAAXPEAUEvent@2@_N1@Z; DirectUI::Element::FireEvent(DirectUI::Event *,bool,bool)
0x180033979  jmp     short loc_1800339EC
0x18003397b  test    rsi, rsi
0x18003397e  jz      short loc_1800339EC
0x180033980  cmp     dword ptr [rsi+4], 1
0x180033984  jnz     short loc_1800339EC
0x180033986  call    ?DoHelp@COCMFrame@@QEAAXXZ; COCMFrame::DoHelp(void)
0x18003398b  jmp     short loc_1800339EC
0x18003398d  mov     rcx, [rcx+100h]
0x180033994  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x18003399a  mov     rcx, rax; hWndLock
0x18003399d  call    cs:__imp_LockWindowUpdate
0x1800339a3  mov     rbx, [rdi+110h]
0x1800339aa  mov     [rsp+98h+var_68], 0
0x1800339b3  test    rbx, rbx
0x1800339b6  jz      short loc_1800339E4
0x1800339b8  mov     rax, [rdi]
0x1800339bb  lea     rdx, [rsp+98h+var_68]
0x1800339c0  mov     rcx, rdi
0x1800339c3  mov     rax, [rax+1B8h]
0x1800339ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339cf  mov     rax, [rsp+98h+var_68]
0x1800339d4  mov     rcx, rbx
0x1800339d7  mov     [rdi+110h], rax
0x1800339de  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800339e4  xor     ecx, ecx; hWndLock
0x1800339e6  call    cs:__imp_LockWindowUpdate
0x1800339ec  mov     r9, r14
0x1800339ef  mov     [rsp+98h+arg_20], rsi
0x1800339f7  mov     r8d, ebp
0x1800339fa  mov     rdx, r15
0x1800339fd  mov     rcx, rdi
0x180033a00  add     rsp, 68h
0x180033a04  pop     r15
0x180033a06  pop     r14
0x180033a08  pop     rdi
0x180033a09  pop     rsi
0x180033a0a  pop     rbp
0x180033a0b  pop     rbx
0x180033a0c  jmp     cs:__imp_?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z; DirectUI::HWNDElement::WndProc(HWND__ *,uint,unsigned __int64,__int64)
```
