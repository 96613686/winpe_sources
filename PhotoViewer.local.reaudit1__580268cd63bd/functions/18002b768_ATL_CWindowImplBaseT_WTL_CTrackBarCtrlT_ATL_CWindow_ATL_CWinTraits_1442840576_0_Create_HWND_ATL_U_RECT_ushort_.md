# ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x18002b768`
- end: `0x18002b8c3`
- name: `?Create@?$CWindowImplBaseT@V?$CTrackBarCtrlT@VCWindow@ATL@@@WTL@@V?$CWinTraits@$0FGAAAAAA@$0A@@ATL@@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `347`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002b658`
- `0x18002b990`
- `0x18002bdc4`
- `0x18002bed0`
- `0x18002bf6c`
- `0x18002c078`
- `0x180038164`
- `0x18004c870`
- `0x18006a280`
- `0x1800718ec`

## callees

- `0x180021a90`
- `0x180021ab8`
- `0x180021ae0`
- `0x18002b768`
- `0x180033468`
- `0x180035b90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002b7e6`
- `KERNEL32!GetCurrentThreadId` at `0x18002b7e6`
- `KERNEL32!RaiseException` at `0x18002b8bc`
- `KERNEL32!RaiseException` at `0x18002b8bc`
- `KERNEL32!SetLastError` at `0x18002b79f`
- `KERNEL32!SetLastError` at `0x18002b79f`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU a1,
        HWND a2,
        int *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        HMENU a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  HMENU v14; // rcx
  int *v15; // rax
  ULONG_PTR v16; // [rsp+58h] [rbp-50h]
  _RTL_CRITICAL_SECTION *v17; // [rsp+60h] [rbp-48h] BYREF
  char v18; // [rsp+68h] [rbp-40h]

  Data = (AtlThunkData_t *)*((_QWORD *)a1 + 5);
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)a1 + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return 0;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  if ( !a8 )
    return 0;
  if ( a1 == (HMENU)-16LL || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x18002B8C2LL);
  }
  *((_QWORD *)a1 + 2) = a1;
  v18 = 0;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  v17 = &stru_1800A3A88;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v17) >= 0 )
  {
    *((_QWORD *)a1 + 4) = qword_1800A3AB0;
    qword_1800A3AB0 = (__int64)(a1 + 4);
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&v17);
  v14 = a7;
  if ( !a7 && (dwStyle & 0x40000000) != 0 )
    v14 = a1;
  v15 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v15 = a3;
  return IsolationAwareCreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           *v15,
           v15[1],
           v15[2] - *v15,
           v15[3] - v15[1],
           a2,
           v14,
           hModule,
           v16);
}

```

## disassembly

```asm
0x18002b768  push    rbx
0x18002b76a  push    rsi
0x18002b76b  push    rdi
0x18002b76c  push    r12
0x18002b76e  push    r14
0x18002b770  push    r15
0x18002b772  sub     rsp, 78h
0x18002b776  mov     rax, [rcx+28h]
0x18002b77a  xor     r12d, r12d
0x18002b77d  mov     r14, r9
0x18002b780  mov     rbx, r8
0x18002b783  mov     r15, rdx
0x18002b786  mov     rdi, rcx
0x18002b789  test    rax, rax
0x18002b78c  jnz     short loc_18002B7B5
0x18002b78e  call    AtlThunk_AllocateData
0x18002b793  mov     [rdi+28h], rax
0x18002b797  test    rax, rax
0x18002b79a  jnz     short loc_18002B7B5
0x18002b79c  lea     ecx, [rax+0Eh]; dwErrCode
0x18002b79f  call    cs:__imp_SetLastError
0x18002b7a5  xor     eax, eax
0x18002b7a7  add     rsp, 78h
0x18002b7ab  pop     r15
0x18002b7ad  pop     r14
0x18002b7af  pop     r12
0x18002b7b1  pop     rdi
0x18002b7b2  pop     rsi
0x18002b7b3  pop     rbx
0x18002b7b4  retn
0x18002b7b5  xor     r8d, r8d; FirstParameter
0x18002b7b8  xor     edx, edx; Proc
0x18002b7ba  mov     rcx, rax; Thunk
0x18002b7bd  call    AtlThunk_InitData
0x18002b7c2  cmp     [rsp+0A8h+arg_38], r12w
0x18002b7cb  jz      short loc_18002B7A5
0x18002b7cd  lea     rsi, [rdi+10h]
0x18002b7d1  test    rsi, rsi
0x18002b7d4  jz      loc_18002B8AD
0x18002b7da  test    rdi, rdi
0x18002b7dd  jz      loc_18002B8AD
0x18002b7e3  mov     [rsi], rdi
0x18002b7e6  call    cs:__imp_GetCurrentThreadId
0x18002b7ec  lea     rcx, [rsp+0A8h+var_48]
0x18002b7f1  mov     [rsp+0A8h+var_40], r12b
0x18002b7f6  mov     [rsi+8], eax
0x18002b7f9  lea     rax, stru_1800A3A88
0x18002b800  mov     [rsp+0A8h+var_48], rax
0x18002b805  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002b80a  test    eax, eax
0x18002b80c  js      short loc_18002B820
0x18002b80e  mov     rax, cs:qword_1800A3AB0
0x18002b815  mov     [rsi+10h], rax
0x18002b819  mov     cs:qword_1800A3AB0, rsi
0x18002b820  lea     rcx, [rsp+0A8h+var_48]; this
0x18002b825  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002b82a  mov     rcx, [rsp+0A8h+arg_30]
0x18002b832  mov     r9d, [rsp+0A8h+dwStyle]; dwStyle
0x18002b83a  test    rcx, rcx
0x18002b83d  jnz     short loc_18002B848
0x18002b83f  bt      r9d, 1Eh
0x18002b844  cmovb   rcx, rdi
0x18002b848  mov     r10, cs:hModule
0x18002b84f  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18002b856  movzx   edx, [rsp+0A8h+arg_38]; lpClassName
0x18002b85e  test    rbx, rbx
0x18002b861  mov     [rsp+0A8h+var_58], r10; HINSTANCE
0x18002b866  cmovnz  rax, rbx
0x18002b86a  mov     [rsp+0A8h+var_60], rcx; HMENU
0x18002b86f  mov     ecx, [rsp+0A8h+dwExStyle]; dwExStyle
0x18002b876  mov     [rsp+0A8h+var_68], r15; HWND
0x18002b87b  mov     ebx, [rax+4]
0x18002b87e  mov     r8d, [rax+8]
0x18002b882  mov     edi, [rax]
0x18002b884  sub     r8d, edi
0x18002b887  mov     r11d, [rax+0Ch]
0x18002b88b  sub     r11d, ebx
0x18002b88e  mov     [rsp+0A8h+var_70], r11d; int
0x18002b893  mov     [rsp+0A8h+var_78], r8d; int
0x18002b898  mov     r8, r14; lpWindowName
0x18002b89b  mov     [rsp+0A8h+var_80], ebx; int
0x18002b89f  mov     [rsp+0A8h+var_88], edi; int
0x18002b8a3  call    IsolationAwareCreateWindowExW
0x18002b8a8  jmp     loc_18002B7A7
0x18002b8ad  xor     r9d, r9d; lpArguments
0x18002b8b0  xor     r8d, r8d; nNumberOfArguments
0x18002b8b3  mov     ecx, 0C0000005h; dwExceptionCode
0x18002b8b8  lea     edx, [r9+1]; dwExceptionFlags
0x18002b8bc  call    cs:__imp_RaiseException
```
