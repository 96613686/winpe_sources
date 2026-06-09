# WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,HMENU__ *,void *)

- ea: `0x180020fc0`
- end: `0x1800210de`
- name: `?Create@?$CFrameWindowImpl@VFrameWindow@@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@3@@WTL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@ATL@@PEBGKKPEAUHMENU__@@PEAX@Z`
- size: `286`
- prototype: `HWND __fastcall(__int64, __int64, int *, const WCHAR *, __int64, __int64, HMENU hMenu)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022c00`

## callees

- `0x180006e00`
- `0x180020fc0`
- `0x180027f84`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180021041`
- `KERNEL32!EnterCriticalSection` at `0x180021041`
- `KERNEL32!LeaveCriticalSection` at `0x180021060`
- `KERNEL32!LeaveCriticalSection` at `0x180021060`
- `KERNEL32!GetCurrentThreadId` at `0x180021031`
- `KERNEL32!GetCurrentThreadId` at `0x180021031`
- `USER32!CreateWindowExW` at `0x1800210c8`
- `USER32!CreateWindowExW` at `0x1800210c8`

## pseudocode

```c
HWND __fastcall WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>::Create(
        __int64 a1,
        __int64 a2,
        int *a3,
        const WCHAR *a4,
        __int64 a5,
        __int64 a6,
        HMENU hMenu)
{
  int v10; // edx
  unsigned int v11; // r8d
  const WCHAR *v12; // r14
  int *v13; // rsi
  int *v14; // rdi

  v12 = (const WCHAR *)WTL::CFrameWndClassInfo::Register(
                         (WTL::CFrameWndClassInfo *)&`FrameWindow::GetWndClassInfo'::`2'::wc,
                         (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))(a1 + 64));
  v13 = &ATL::CWindow::rcDefault;
  v14 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v14 = a3;
  if ( !(_WORD)v12 )
    return 0;
  if ( a1 == -16 || !a1 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, v10, v11);
    JUMPOUT(0x1800210DDLL);
  }
  *(_QWORD *)(a1 + 16) = a1;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  EnterCriticalSection(&stru_1800503B8);
  *(_QWORD *)(a1 + 32) = qword_1800503E0;
  qword_1800503E0 = a1 + 16;
  LeaveCriticalSection(&stru_1800503B8);
  if ( v14 )
    v13 = v14;
  return CreateWindowExW(
           0x40000u,
           v12,
           a4,
           0x860F0000,
           *v13,
           v13[1],
           v13[2] - *v13,
           v13[3] - v13[1],
           0,
           hMenu,
           hInst,
           0);
}

```

## disassembly

```asm
0x180020fc0  push    rbx
0x180020fc2  push    rbp
0x180020fc3  push    rsi
0x180020fc4  push    rdi
0x180020fc5  push    r12
0x180020fc7  push    r14
0x180020fc9  push    r15
0x180020fcb  sub     rsp, 60h
0x180020fcf  mov     rbp, rcx
0x180020fd2  lea     rdx, [rcx+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x180020fd6  lea     rcx, ?wc@?1??GetWndClassInfo@FrameWindow@@SAAEAVCFrameWndClassInfo@WTL@@XZ@4V34@A; this
0x180020fdd  mov     r15, r9
0x180020fe0  mov     rbx, r8
0x180020fe3  call    ?Register@CFrameWndClassInfo@WTL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; WTL::CFrameWndClassInfo::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x180020fe8  xor     r12d, r12d
0x180020feb  movzx   r14d, ax
0x180020fef  test    rbx, rbx
0x180020ff2  lea     rsi, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x180020ff9  mov     rdi, rsi
0x180020ffc  cmovnz  rdi, rbx
0x180021000  test    r14w, r14w
0x180021004  jnz     short loc_180021018
0x180021006  mov     eax, r12d
0x180021009  add     rsp, 60h
0x18002100d  pop     r15
0x18002100f  pop     r14
0x180021011  pop     r12
0x180021013  pop     rdi
0x180021014  pop     rsi
0x180021015  pop     rbp
0x180021016  pop     rbx
0x180021017  retn
0x180021018  lea     rbx, [rbp+10h]
0x18002101c  test    rbx, rbx
0x18002101f  jz      loc_1800210D3
0x180021025  test    rbp, rbp
0x180021028  jz      loc_1800210D3
0x18002102e  mov     [rbx], rbp
0x180021031  call    cs:__imp_GetCurrentThreadId
0x180021037  lea     rcx, stru_1800503B8; lpCriticalSection
0x18002103e  mov     [rbx+8], eax
0x180021041  call    cs:__imp_EnterCriticalSection
0x180021047  mov     rax, cs:qword_1800503E0
0x18002104e  lea     rcx, stru_1800503B8; lpCriticalSection
0x180021055  mov     [rbx+10h], rax
0x180021059  mov     cs:qword_1800503E0, rbx
0x180021060  call    cs:__imp_LeaveCriticalSection
0x180021066  mov     rax, cs:hInst
0x18002106d  test    rdi, rdi
0x180021070  mov     [rsp+98h+lpParam], r12; lpParam
0x180021075  mov     rdx, r14; lpClassName
0x180021078  mov     [rsp+98h+hInstance], rax; hInstance
0x18002107d  cmovnz  rsi, rdi
0x180021081  mov     rax, [rsp+98h+arg_30]
0x180021089  mov     [rsp+98h+hMenu], rax; hMenu
0x18002108e  mov     [rsp+98h+hWndParent], r12; hWndParent
0x180021093  mov     r9d, [rsi+4]
0x180021097  mov     r8d, [rsi+0Ch]
0x18002109b  mov     r10d, [rsi]
0x18002109e  sub     r8d, r9d
0x1800210a1  mov     ecx, [rsi+8]
0x1800210a4  mov     [rsp+98h+nHeight], r8d; nHeight
0x1800210a9  sub     ecx, r10d
0x1800210ac  mov     [rsp+98h+nWidth], ecx; nWidth
0x1800210b0  mov     r8, r15; lpWindowName
0x1800210b3  mov     [rsp+98h+Y], r9d; Y
0x1800210b8  mov     ecx, 40000h; dwExStyle
0x1800210bd  mov     r9d, 860F0000h; dwStyle
0x1800210c3  mov     [rsp+98h+X], r10d; X
0x1800210c8  call    cs:__imp_CreateWindowExW
0x1800210ce  jmp     loc_180021009
0x1800210d3  mov     ecx, 0C0000005h; this
0x1800210d8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
