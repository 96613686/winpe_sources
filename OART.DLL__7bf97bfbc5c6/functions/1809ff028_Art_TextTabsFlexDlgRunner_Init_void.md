# Art::TextTabsFlexDlgRunner::Init(void)

- ea: `0x1809ff028`
- end: `0x1809ff243`
- name: `?Init@TextTabsFlexDlgRunner@Art@@AEAAXXZ`
- size: `539`
- prototype: `void __fastcall(Art::TextTabsFlexDlgRunner *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1809fe9f4`

## callees

- `0x180071720`
- `0x1801b09dc`
- `0x18036ba6c`
- `0x1809b8f84`
- `0x1809ff028`
- `0x1809ff664`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809ff07e`
- `Mso98Win32Client!__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z` at `0x1809ff07e`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x1809ff0c6`
- `mso40uiWin32Client!__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z` at `0x1809ff0c6`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1809ff103`
- `mso40uiWin32Client!__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z` at `0x1809ff103`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809ff03a`
- `mso40uiWin32Client!__imp_?MsoHrInitNetUI@@YAJXZ` at `0x1809ff03a`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff0f7`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff15d`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff1c9`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff229`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff0f7`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff15d`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff1c9`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ff229`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809ff19b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809ff1fb`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809ff19b`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1809ff1fb`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff0a2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff182`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff1e5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff0a2`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff182`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ff1e5`

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
  v13 = sub_1809B8F84((char *)this + 80);
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
0x1809ff028  mov     [rsp-18h+arg_0], rbx
0x1809ff02d  push    rbp
0x1809ff02e  push    rsi
0x1809ff02f  push    rdi
0x1809ff030  mov     rbp, rsp
0x1809ff033  sub     rsp, 30h
0x1809ff037  mov     rdi, rcx
0x1809ff03a  call    cs:__imp_?MsoHrInitNetUI@@YAJXZ; MsoHrInitNetUI(void)
0x1809ff040  test    eax, eax
0x1809ff042  jns     short loc_1809FF051
0x1809ff044  mov     edx, 2348408Fh; unsigned int
0x1809ff049  mov     ecx, eax; int
0x1809ff04b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1809ff050  int     3; Trap to Debugger
0x1809ff051  lea     rbx, [rdi+28h]
0x1809ff055  mov     rcx, [rbx]
0x1809ff058  test    rcx, rcx
0x1809ff05b  jz      short loc_1809FF06A
0x1809ff05d  mov     rax, [rcx]
0x1809ff060  mov     rax, [rax+10h]
0x1809ff064  call    cs:__guard_dispatch_icall_fptr
0x1809ff06a  mov     r8, rbx
0x1809ff06d  mov     qword ptr [rbx], 0
0x1809ff074  mov     edx, 8002200h
0x1809ff079  mov     ecx, 13A0h
0x1809ff07e  call    cs:__imp_?MsoCreateFlexDataSource@FlexUI@@YA_NHIPEAPEAUIDataSource@1@@Z; FlexUI::MsoCreateFlexDataSource(int,uint,FlexUI::IDataSource * *)
0x1809ff084  test    al, al
0x1809ff086  jnz     short loc_1809FF095
0x1809ff088  mov     edx, 2348408Eh
0x1809ff08d  xor     ecx, ecx
0x1809ff08f  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809ff094  int     3; Trap to Debugger
0x1809ff095  mov     rsi, [rbx]
0x1809ff098  test    rsi, rsi
0x1809ff09b  jnz     short loc_1809FF0AD
0x1809ff09d  mov     ecx, 7A0742h
0x1809ff0a2  call    cs:__imp_MsoShipAssertTagProc
0x1809ff0a8  jmp     loc_1809FF168
0x1809ff0ad  lea     rdx, [rbp+arg_8]
0x1809ff0b1  mov     [rbp+arg_10], 0
0x1809ff0b9  mov     ecx, 5
0x1809ff0be  mov     [rbp+arg_8], 0
0x1809ff0c6  call    cs:__imp_?Create@FlexList@FlexUI@@SA_NIPEAPEAV12@@Z; FlexUI::FlexList::Create(uint,FlexUI::FlexList * *)
0x1809ff0cc  mov     rcx, [rbp+arg_8]
0x1809ff0d0  test    al, al
0x1809ff0d2  jnz     short loc_1809FF0FF
0x1809ff0d4  test    rcx, rcx
0x1809ff0d7  jz      short loc_1809FF0EE
0x1809ff0d9  mov     [rbp+arg_8], 0
0x1809ff0e1  mov     rax, [rcx]
0x1809ff0e4  mov     rax, [rax+10h]
0x1809ff0e8  call    cs:__guard_dispatch_icall_fptr
0x1809ff0ee  mov     rcx, [rbp+arg_10]
0x1809ff0f2  test    rcx, rcx
0x1809ff0f5  jz      short loc_1809FF168
0x1809ff0f7  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809ff0fd  jmp     short loc_1809FF168
0x1809ff0ff  lea     rdx, [rbp+arg_10]
0x1809ff103  call    cs:__imp_?CreateList@FlexValue@FlexUI@@SA_NPEAUIFlexList@2@AEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateList(FlexUI::IFlexList *,FlexUI::FlexValueSP &)
0x1809ff109  mov     r9, [rbp+arg_10]
0x1809ff10d  test    r9, r9
0x1809ff110  jnz     short loc_1809FF11D
0x1809ff112  mov     rcx, [rbp+arg_8]
0x1809ff116  test    rcx, rcx
0x1809ff119  jz      short loc_1809FF168
0x1809ff11b  jmp     short loc_1809FF0D9
0x1809ff11d  mov     rax, [rsi]
0x1809ff120  xor     edx, edx
0x1809ff122  mov     rcx, rsi
0x1809ff125  mov     rax, [rax+30h]
0x1809ff129  lea     r8d, [rdx+6]
0x1809ff12d  call    cs:__guard_dispatch_icall_fptr
0x1809ff133  mov     rcx, [rbp+arg_8]
0x1809ff137  mov     sil, al
0x1809ff13a  test    rcx, rcx
0x1809ff13d  jz      short loc_1809FF154
0x1809ff13f  mov     [rbp+arg_8], 0
0x1809ff147  mov     rdx, [rcx]
0x1809ff14a  mov     rax, [rdx+10h]
0x1809ff14e  call    cs:__guard_dispatch_icall_fptr
0x1809ff154  mov     rcx, [rbp+arg_10]
0x1809ff158  test    rcx, rcx
0x1809ff15b  jz      short loc_1809FF163
0x1809ff15d  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809ff163  test    sil, sil
0x1809ff166  jnz     short loc_1809FF175
0x1809ff168  mov     edx, 2348408Dh
0x1809ff16d  xor     ecx, ecx
0x1809ff16f  call    ?ThrowTag@CAbortException@Ofc@@SAXW4ExcAbortStrategy@2@K@Z; Ofc::CAbortException::ThrowTag(Ofc::ExcAbortStrategy,ulong)
0x1809ff174  int     3; Trap to Debugger
0x1809ff175  mov     rsi, [rbx]
0x1809ff178  test    rsi, rsi
0x1809ff17b  jnz     short loc_1809FF18A
0x1809ff17d  mov     ecx, 7A0740h
0x1809ff182  call    cs:__imp_MsoShipAssertTagProc
0x1809ff188  jmp     short loc_1809FF1CF
0x1809ff18a  lea     rdx, [rbp+arg_8]
0x1809ff18e  mov     [rbp+arg_8], 0
0x1809ff196  mov     ecx, 30D5900h
0x1809ff19b  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809ff1a1  mov     r9, [rbp+arg_8]
0x1809ff1a5  test    r9, r9
0x1809ff1a8  jz      short loc_1809FF1CF
0x1809ff1aa  mov     rax, [rsi]
0x1809ff1ad  xor     edx, edx
0x1809ff1af  mov     rcx, rsi
0x1809ff1b2  mov     rax, [rax+30h]
0x1809ff1b6  lea     r8d, [rdx+4]
0x1809ff1ba  call    cs:__guard_dispatch_icall_fptr
0x1809ff1c0  mov     rcx, [rbp+arg_8]
0x1809ff1c4  test    rcx, rcx
0x1809ff1c7  jz      short loc_1809FF1CF
0x1809ff1c9  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809ff1cf  lea     rcx, [rdi+50h]
0x1809ff1d3  call    sub_1809B8F84
0x1809ff1d8  mov     rbx, [rbx]
0x1809ff1db  test    rbx, rbx
0x1809ff1de  jnz     short loc_1809FF1ED
0x1809ff1e0  mov     ecx, 7A0740h
0x1809ff1e5  call    cs:__imp_MsoShipAssertTagProc
0x1809ff1eb  jmp     short loc_1809FF22F
0x1809ff1ed  lea     rdx, [rbp+arg_8]
0x1809ff1f1  mov     [rbp+arg_8], 0
0x1809ff1f9  mov     ecx, eax
0x1809ff1fb  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1809ff201  mov     r9, [rbp+arg_8]
0x1809ff205  test    r9, r9
0x1809ff208  jz      short loc_1809FF22F
0x1809ff20a  mov     rax, [rbx]
0x1809ff20d  xor     edx, edx
0x1809ff20f  mov     rcx, rbx
0x1809ff212  mov     rax, [rax+30h]
0x1809ff216  lea     r8d, [rdx+8]
0x1809ff21a  call    cs:__guard_dispatch_icall_fptr
0x1809ff220  mov     rcx, [rbp+arg_8]
0x1809ff224  test    rcx, rcx
0x1809ff227  jz      short loc_1809FF22F
0x1809ff229  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809ff22f  mov     rcx, rdi; this
0x1809ff232  mov     rbx, [rsp+30h+arg_0]
0x1809ff237  add     rsp, 30h
0x1809ff23b  pop     rdi
0x1809ff23c  pop     rsi
0x1809ff23d  pop     rbp
0x1809ff23e  jmp     ?RefreshDialogData@TextTabsFlexDlgRunner@Art@@AEAAXXZ; Art::TextTabsFlexDlgRunner::RefreshDialogData(void)
```
