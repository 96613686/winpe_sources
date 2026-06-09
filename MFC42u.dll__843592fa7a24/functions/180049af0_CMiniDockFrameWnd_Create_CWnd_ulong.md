# CMiniDockFrameWnd::Create(CWnd *,ulong)

- ea: `0x180049af0`
- end: `0x180049c87`
- name: `?Create@CMiniDockFrameWnd@@UEAAHPEAVCWnd@@K@Z`
- size: `407`
- prototype: `__int64 __fastcall(CMiniDockFrameWnd *__hidden this, struct CWnd *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180014640`
- `0x180019290`
- `0x18002cdb0`
- `0x180046060`
- `0x180049a50`
- `0x180049af0`
- `0x18004abc0`

## import_xrefs

- `USER32!GetSystemMenu` at `0x180049b89`
- `USER32!GetSystemMenu` at `0x180049b89`
- `USER32!DeleteMenu` at `0x180049ba6`
- `USER32!DeleteMenu` at `0x180049bb8`
- `USER32!DeleteMenu` at `0x180049bca`
- `USER32!DeleteMenu` at `0x180049bdc`
- `USER32!DeleteMenu` at `0x180049c0d`
- `USER32!DeleteMenu` at `0x180049ba6`
- `USER32!DeleteMenu` at `0x180049bb8`
- `USER32!DeleteMenu` at `0x180049bca`
- `USER32!DeleteMenu` at `0x180049bdc`
- `USER32!DeleteMenu` at `0x180049c0d`
- `USER32!AppendMenuW` at `0x180049c24`
- `USER32!AppendMenuW` at `0x180049c24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMiniDockFrameWnd::Create(CMiniDockFrameWnd *this, struct CWnd *a2, __int16 a3)
{
  unsigned int v6; // esi
  __int64 result; // rax
  int v8; // edi
  HMENU SystemMenu; // rax
  struct CMenu *v10; // rbp
  LPCWSTR lpNewItem; // [rsp+60h] [rbp+8h] BYREF

  v6 = 1;
  *((_DWORD *)this + 78) = 1;
  result = CMiniFrameWnd::CreateEx(
             this,
             0,
             0,
             &afxChNil,
             ~(a3 << 9) & 0x800 | 0x80C83300,
             &CFrameWnd::rectDefault,
             a2,
             0);
  if ( (_DWORD)result )
  {
    v8 = a3 & 0x40 | ((a3 & 0x5000) != 0 ? 4096 : 0x2000);
    SystemMenu = GetSystemMenu(*((HWND *)this + 8), 0);
    v10 = CMenu::FromHandle(SystemMenu);
    DeleteMenu(*((HMENU *)v10 + 1), 0xF000u, 0);
    DeleteMenu(*((HMENU *)v10 + 1), 0xF020u, 0);
    DeleteMenu(*((HMENU *)v10 + 1), 0xF030u, 0);
    DeleteMenu(*((HMENU *)v10 + 1), 0xF120u, 0);
    lpNewItem = _afxPchNil;
    if ( (unsigned int)CString::LoadStringW((CString *)&lpNewItem, 0xF011u) )
    {
      DeleteMenu(*((HMENU *)v10 + 1), 0xF060u, 0);
      AppendMenuW(*((HMENU *)v10 + 1), 0, 0xF060u, lpNewItem);
    }
    if ( (unsigned int)CDockBar::Create((CMiniDockFrameWnd *)((char *)this + 360), a2, v8 | 0x50000000u, 0xE81Fu) )
      CWnd::SetParent((CMiniDockFrameWnd *)((char *)this + 360), this);
    else
      v6 = 0;
    *((_DWORD *)this + 78) = 0;
    CString::~CString((CString *)&lpNewItem);
    return v6;
  }
  else
  {
    *((_DWORD *)this + 78) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180049af0  mov     r11, rsp
0x180049af3  mov     [r11+10h], rbx
0x180049af7  mov     [r11+18h], rbp
0x180049afb  push    rsi
0x180049afc  push    rdi
0x180049afd  push    r14
0x180049aff  sub     rsp, 40h
0x180049b03  mov     ebp, r8d
0x180049b06  mov     r14, rdx
0x180049b09  mov     rbx, rcx
0x180049b0c  mov     esi, 1
0x180049b11  mov     [rcx+138h], esi
0x180049b17  mov     eax, r8d
0x180049b1a  shl     eax, 9
0x180049b1d  not     eax
0x180049b1f  and     eax, 800h
0x180049b24  or      eax, 80C83300h
0x180049b29  mov     [rsp+58h+var_20], 0; unsigned int
0x180049b31  mov     [r11-28h], rdx
0x180049b35  lea     rcx, ?rectDefault@CFrameWnd@@2VCRect@@B; CRect const CFrameWnd::rectDefault
0x180049b3c  mov     [r11-30h], rcx
0x180049b40  mov     [rsp+58h+var_38], eax; unsigned int
0x180049b44  lea     r9, ?afxChNil@@3GA; unsigned __int16 *
0x180049b4b  xor     r8d, r8d; unsigned __int16 *
0x180049b4e  xor     edx, edx; unsigned int
0x180049b50  mov     rcx, rbx; this
0x180049b53  call    ?CreateEx@CMiniFrameWnd@@QEAAHKPEBG0KAEBUtagRECT@@PEAVCWnd@@I@Z; CMiniFrameWnd::CreateEx(ulong,ushort const *,ushort const *,ulong,tagRECT const &,CWnd *,uint)
0x180049b58  test    eax, eax
0x180049b5a  jnz     short loc_180049B67
0x180049b5c  mov     [rbx+138h], eax
0x180049b62  jmp     loc_180049C74
0x180049b67  mov     eax, ebp
0x180049b69  and     eax, 5000h
0x180049b6e  neg     eax
0x180049b70  sbb     edi, edi
0x180049b72  and     edi, 0FFFFF000h
0x180049b78  add     edi, 2000h
0x180049b7e  and     ebp, 40h
0x180049b81  or      edi, ebp
0x180049b83  xor     edx, edx; bRevert
0x180049b85  mov     rcx, [rbx+40h]; hWnd
0x180049b89  call    cs:__imp_GetSystemMenu
0x180049b8f  mov     rcx, rax; HMENU
0x180049b92  call    ?FromHandle@CMenu@@SAPEAV1@PEAUHMENU__@@@Z; CMenu::FromHandle(HMENU__ *)
0x180049b97  mov     rbp, rax
0x180049b9a  xor     r8d, r8d; uFlags
0x180049b9d  mov     edx, 0F000h; uPosition
0x180049ba2  mov     rcx, [rax+8]; hMenu
0x180049ba6  call    cs:__imp_DeleteMenu
0x180049bac  xor     r8d, r8d; uFlags
0x180049baf  mov     edx, 0F020h; uPosition
0x180049bb4  mov     rcx, [rbp+8]; hMenu
0x180049bb8  call    cs:__imp_DeleteMenu
0x180049bbe  xor     r8d, r8d; uFlags
0x180049bc1  mov     edx, 0F030h; uPosition
0x180049bc6  mov     rcx, [rbp+8]; hMenu
0x180049bca  call    cs:__imp_DeleteMenu
0x180049bd0  xor     r8d, r8d; uFlags
0x180049bd3  mov     edx, 0F120h; uPosition
0x180049bd8  mov     rcx, [rbp+8]; hMenu
0x180049bdc  call    cs:__imp_DeleteMenu
0x180049be2  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180049be9  mov     [rsp+58h+lpNewItem], rax
0x180049bee  mov     edx, 0F011h; uID
0x180049bf3  lea     rcx, [rsp+58h+lpNewItem]; this
0x180049bf8  call    ?LoadStringW@CString@@QEAAHI@Z; CString::LoadStringW(uint)
0x180049bfd  test    eax, eax
0x180049bff  jz      short loc_180049C2A
0x180049c01  xor     r8d, r8d; uFlags
0x180049c04  mov     edx, 0F060h; uPosition
0x180049c09  mov     rcx, [rbp+8]; hMenu
0x180049c0d  call    cs:__imp_DeleteMenu
0x180049c13  mov     r9, [rsp+58h+lpNewItem]; lpNewItem
0x180049c18  xor     edx, edx; uFlags
0x180049c1a  mov     r8d, 0F060h; uIDNewItem
0x180049c20  mov     rcx, [rbp+8]; hMenu
0x180049c24  call    cs:__imp_AppendMenuW
0x180049c2a  lea     rbp, [rbx+168h]
0x180049c31  or      edi, 50000000h
0x180049c37  mov     r9d, 0E81Fh; unsigned int
0x180049c3d  mov     r8d, edi; unsigned int
0x180049c40  mov     rdx, r14; struct CWnd *
0x180049c43  mov     rcx, rbp; this
0x180049c46  call    ?Create@CDockBar@@QEAAHPEAVCWnd@@KI@Z; CDockBar::Create(CWnd *,ulong,uint)
0x180049c4b  test    eax, eax
0x180049c4d  jnz     short loc_180049C53
0x180049c4f  xor     esi, esi
0x180049c51  jmp     short loc_180049C5E
0x180049c53  mov     rdx, rbx; struct CWnd *
0x180049c56  mov     rcx, rbp; this
0x180049c59  call    ?SetParent@CWnd@@QEAAPEAV1@PEAV1@@Z; CWnd::SetParent(CWnd *)
0x180049c5e  mov     dword ptr [rbx+138h], 0
0x180049c68  lea     rcx, [rsp+58h+lpNewItem]; this
0x180049c6d  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180049c72  mov     eax, esi
0x180049c74  mov     rbx, [rsp+58h+arg_8]
0x180049c79  mov     rbp, [rsp+58h+arg_10]
0x180049c7e  add     rsp, 40h
0x180049c82  pop     r14
0x180049c84  pop     rdi
0x180049c85  pop     rsi
0x180049c86  retn
```
