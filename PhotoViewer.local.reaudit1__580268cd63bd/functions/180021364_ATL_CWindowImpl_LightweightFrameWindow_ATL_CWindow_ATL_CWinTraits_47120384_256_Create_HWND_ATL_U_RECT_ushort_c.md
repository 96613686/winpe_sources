# ATL::CWindowImpl<LightweightFrameWindow,ATL::CWindow,ATL::CWinTraits<47120384,256>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,void *)

- ea: `0x180021364`
- end: `0x1800214c3`
- name: `?Create@?$CWindowImpl@VLightweightFrameWindow@@VCWindow@ATL@@V?$CWinTraits@$0CMPAAAA@$0BAA@@3@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@PEAX@Z`
- size: `351`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HMENU)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021244`

## callees

- `0x180021364`
- `0x1800214cc`
- `0x180021a90`
- `0x180021ab8`
- `0x180021ae0`
- `0x180033468`
- `0x180035b90`
- `0x180036b78`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800213f9`
- `KERNEL32!GetCurrentThreadId` at `0x1800213f9`
- `KERNEL32!RaiseException` at `0x1800214bc`
- `KERNEL32!RaiseException` at `0x1800214bc`
- `KERNEL32!SetLastError` at `0x1800213ba`
- `KERNEL32!SetLastError` at `0x1800213ba`

## pseudocode

```c
HWND __fastcall ATL::CWindowImpl<LightweightFrameWindow,ATL::CWindow,ATL::CWinTraits<47120384,256>>::Create(
        __int64 a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        int a5,
        int a6,
        HMENU a7)
{
  WNDCLASSEXW *WndClassInfo; // rax
  const WCHAR *v10; // rbp
  AtlThunkData_t *Data; // rax
  int *v13; // rax
  ULONG_PTR v14; // [rsp+58h] [rbp-40h]
  _RTL_CRITICAL_SECTION *v15; // [rsp+60h] [rbp-38h] BYREF
  char v16; // [rsp+68h] [rbp-30h]

  if ( !*((_QWORD *)LightweightFrameWindow::GetWndClassInfo() + 10) )
    *((_QWORD *)LightweightFrameWindow::GetWndClassInfo() + 10) = 0;
  WndClassInfo = (WNDCLASSEXW *)LightweightFrameWindow::GetWndClassInfo();
  v10 = (const WCHAR *)WTL::CFrameWndClassInfo::Register(
                         WndClassInfo,
                         (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))(a1 + 64));
  Data = *(AtlThunkData_t **)(a1 + 40);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *(_QWORD *)(a1 + 40) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !(_WORD)v10 )
    return 0;
  if ( a1 == -16 || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x1800214C2LL);
  }
  *(_QWORD *)(a1 + 16) = a1;
  v16 = 0;
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  v15 = &stru_1800A3A88;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15) >= 0 )
  {
    *(_QWORD *)(a1 + 32) = qword_1800A3AB0;
    qword_1800A3AB0 = a1 + 16;
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&v15);
  v13 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v13 = a3;
  return IsolationAwareCreateWindowExW(
           0x100u,
           v10,
           0,
           0x2CF0000u,
           *v13,
           v13[1],
           v13[2] - *v13,
           v13[3] - v13[1],
           0,
           a7,
           hModule,
           v14);
}

```

## disassembly

```asm
0x180021364  push    rbx
0x180021366  push    rbp
0x180021367  push    rsi
0x180021368  push    rdi
0x180021369  push    r14
0x18002136b  sub     rsp, 70h
0x18002136f  mov     rbx, r8
0x180021372  mov     rdi, rcx
0x180021375  call    ?GetWndClassInfo@LightweightFrameWindow@@SAAEAVCFrameWndClassInfo@WTL@@XZ; LightweightFrameWindow::GetWndClassInfo(void)
0x18002137a  xor     r14d, r14d
0x18002137d  cmp     [rax+50h], r14
0x180021381  jnz     short loc_18002138C
0x180021383  call    ?GetWndClassInfo@LightweightFrameWindow@@SAAEAVCFrameWndClassInfo@WTL@@XZ; LightweightFrameWindow::GetWndClassInfo(void)
0x180021388  mov     [rax+50h], r14
0x18002138c  call    ?GetWndClassInfo@LightweightFrameWindow@@SAAEAVCFrameWndClassInfo@WTL@@XZ; LightweightFrameWindow::GetWndClassInfo(void)
0x180021391  lea     rdx, [rdi+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x180021395  mov     rcx, rax; this
0x180021398  call    ?Register@CFrameWndClassInfo@WTL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; WTL::CFrameWndClassInfo::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x18002139d  movzx   ebp, ax
0x1800213a0  mov     rax, [rdi+28h]
0x1800213a4  test    rax, rax
0x1800213a7  jnz     short loc_1800213CE
0x1800213a9  call    AtlThunk_AllocateData
0x1800213ae  mov     [rdi+28h], rax
0x1800213b2  test    rax, rax
0x1800213b5  jnz     short loc_1800213CE
0x1800213b7  lea     ecx, [rax+0Eh]; dwErrCode
0x1800213ba  call    cs:__imp_SetLastError
0x1800213c0  mov     rax, r14
0x1800213c3  add     rsp, 70h
0x1800213c7  pop     r14
0x1800213c9  pop     rdi
0x1800213ca  pop     rsi
0x1800213cb  pop     rbp
0x1800213cc  pop     rbx
0x1800213cd  retn
0x1800213ce  xor     r8d, r8d; FirstParameter
0x1800213d1  xor     edx, edx; Proc
0x1800213d3  mov     rcx, rax; Thunk
0x1800213d6  call    AtlThunk_InitData
0x1800213db  test    bp, bp
0x1800213de  jz      short loc_1800213C0
0x1800213e0  lea     rsi, [rdi+10h]
0x1800213e4  test    rsi, rsi
0x1800213e7  jz      loc_1800214AD
0x1800213ed  test    rdi, rdi
0x1800213f0  jz      loc_1800214AD
0x1800213f6  mov     [rsi], rdi
0x1800213f9  call    cs:__imp_GetCurrentThreadId
0x1800213ff  lea     rcx, [rsp+98h+var_38]
0x180021404  mov     [rsp+98h+var_30], r14b
0x180021409  mov     [rsi+8], eax
0x18002140c  lea     rax, stru_1800A3A88
0x180021413  mov     [rsp+98h+var_38], rax
0x180021418  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002141d  test    eax, eax
0x18002141f  js      short loc_180021433
0x180021421  mov     rax, cs:qword_1800A3AB0
0x180021428  mov     [rsi+10h], rax
0x18002142c  mov     cs:qword_1800A3AB0, rsi
0x180021433  lea     rcx, [rsp+98h+var_38]; this
0x180021438  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002143d  mov     rcx, cs:hModule
0x180021444  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18002144b  mov     [rsp+98h+var_48], rcx; HINSTANCE
0x180021450  test    rbx, rbx
0x180021453  mov     rdx, rbp; lpClassName
0x180021456  mov     ecx, 100h; dwExStyle
0x18002145b  cmovnz  rax, rbx
0x18002145f  mov     r10d, [rax+4]
0x180021463  mov     r11d, [rax]
0x180021466  mov     r8d, [rax+8]
0x18002146a  mov     r9d, [rax+0Ch]
0x18002146e  sub     r8d, r11d
0x180021471  mov     rax, [rsp+98h+arg_30]
0x180021479  sub     r9d, r10d
0x18002147c  mov     [rsp+98h+var_50], rax; HMENU
0x180021481  mov     [rsp+98h+var_58], r14; HWND
0x180021486  mov     [rsp+98h+var_60], r9d; int
0x18002148b  mov     r9d, 2CF0000h; dwStyle
0x180021491  mov     [rsp+98h+var_68], r8d; int
0x180021496  xor     r8d, r8d; lpWindowName
0x180021499  mov     [rsp+98h+var_70], r10d; int
0x18002149e  mov     [rsp+98h+var_78], r11d; int
0x1800214a3  call    IsolationAwareCreateWindowExW
0x1800214a8  jmp     loc_1800213C3
0x1800214ad  xor     r9d, r9d; lpArguments
0x1800214b0  xor     r8d, r8d; nNumberOfArguments
0x1800214b3  mov     ecx, 0C0000005h; dwExceptionCode
0x1800214b8  lea     edx, [r9+1]; dwExceptionFlags
0x1800214bc  call    cs:__imp_RaiseException
```
