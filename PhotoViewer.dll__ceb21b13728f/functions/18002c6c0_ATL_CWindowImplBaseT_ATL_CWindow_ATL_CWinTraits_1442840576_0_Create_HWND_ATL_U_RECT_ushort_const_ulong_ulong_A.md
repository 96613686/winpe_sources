# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x18002c6c0`
- end: `0x18002c818`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `344`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002b5a0`
- `0x18002bca4`
- `0x18002c3d0`
- `0x18003bd30`
- `0x18003edd0`

## callees

- `0x180021a90`
- `0x180021ab8`
- `0x180021ae0`
- `0x18002c6c0`
- `0x180033468`
- `0x180035b90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002c737`
- `KERNEL32!GetCurrentThreadId` at `0x18002c737`
- `KERNEL32!RaiseException` at `0x18002c811`
- `KERNEL32!RaiseException` at `0x18002c811`
- `KERNEL32!SetLastError` at `0x18002c6f2`
- `KERNEL32!SetLastError` at `0x18002c6f2`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
        HMENU a1,
        __int64 a2,
        int *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        DWORD dwExStyle,
        HMENU a7,
        unsigned __int16 a8)
{
  AtlThunkData_t *Data; // rax
  HMENU v13; // rcx
  int *v14; // rax
  ULONG_PTR v15; // [rsp+58h] [rbp-40h]
  _RTL_CRITICAL_SECTION *v16; // [rsp+60h] [rbp-38h] BYREF
  char v17; // [rsp+68h] [rbp-30h]

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
    JUMPOUT(0x18002C817LL);
  }
  *((_QWORD *)a1 + 2) = a1;
  v17 = 0;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  v16 = &stru_1800A3A88;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16) >= 0 )
  {
    *((_QWORD *)a1 + 4) = qword_1800A3AB0;
    qword_1800A3AB0 = (__int64)(a1 + 4);
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)&v16);
  v13 = a7;
  if ( !a7 && (dwStyle & 0x40000000) != 0 )
    v13 = a1;
  v14 = &ATL::CWindow::rcDefault;
  if ( a3 )
    v14 = a3;
  return IsolationAwareCreateWindowExW(
           dwExStyle,
           (LPCWSTR)a8,
           a4,
           dwStyle,
           *v14,
           v14[1],
           v14[2] - *v14,
           v14[3] - v14[1],
           HWND_MESSAGE,
           v13,
           hModule,
           v15);
}

```

## disassembly

```asm
0x18002c6c0  push    rbx
0x18002c6c2  push    rsi
0x18002c6c3  push    rdi
0x18002c6c4  push    r14
0x18002c6c6  push    r15
0x18002c6c8  sub     rsp, 70h
0x18002c6cc  mov     rax, [rcx+28h]
0x18002c6d0  xor     r15d, r15d
0x18002c6d3  mov     r14, r9
0x18002c6d6  mov     rbx, r8
0x18002c6d9  mov     rdi, rcx
0x18002c6dc  test    rax, rax
0x18002c6df  jnz     short loc_18002C706
0x18002c6e1  call    AtlThunk_AllocateData
0x18002c6e6  mov     [rdi+28h], rax
0x18002c6ea  test    rax, rax
0x18002c6ed  jnz     short loc_18002C706
0x18002c6ef  lea     ecx, [rax+0Eh]; dwErrCode
0x18002c6f2  call    cs:__imp_SetLastError
0x18002c6f8  xor     eax, eax
0x18002c6fa  add     rsp, 70h
0x18002c6fe  pop     r15
0x18002c700  pop     r14
0x18002c702  pop     rdi
0x18002c703  pop     rsi
0x18002c704  pop     rbx
0x18002c705  retn
0x18002c706  xor     r8d, r8d; FirstParameter
0x18002c709  xor     edx, edx; Proc
0x18002c70b  mov     rcx, rax; Thunk
0x18002c70e  call    AtlThunk_InitData
0x18002c713  cmp     [rsp+98h+arg_38], r15w
0x18002c71c  jz      short loc_18002C6F8
0x18002c71e  lea     rsi, [rdi+10h]
0x18002c722  test    rsi, rsi
0x18002c725  jz      loc_18002C802
0x18002c72b  test    rdi, rdi
0x18002c72e  jz      loc_18002C802
0x18002c734  mov     [rsi], rdi
0x18002c737  call    cs:__imp_GetCurrentThreadId
0x18002c73d  lea     rcx, [rsp+98h+var_38]
0x18002c742  mov     [rsp+98h+var_30], r15b
0x18002c747  mov     [rsi+8], eax
0x18002c74a  lea     rax, stru_1800A3A88
0x18002c751  mov     [rsp+98h+var_38], rax
0x18002c756  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18002c75b  test    eax, eax
0x18002c75d  js      short loc_18002C771
0x18002c75f  mov     rax, cs:qword_1800A3AB0
0x18002c766  mov     [rsi+10h], rax
0x18002c76a  mov     cs:qword_1800A3AB0, rsi
0x18002c771  lea     rcx, [rsp+98h+var_38]; this
0x18002c776  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002c77b  mov     rcx, [rsp+98h+arg_30]
0x18002c783  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x18002c78b  test    rcx, rcx
0x18002c78e  jnz     short loc_18002C799
0x18002c790  bt      r9d, 1Eh
0x18002c795  cmovb   rcx, rdi
0x18002c799  mov     r10, cs:hModule
0x18002c7a0  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18002c7a7  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x18002c7af  test    rbx, rbx
0x18002c7b2  mov     [rsp+98h+var_48], r10; HINSTANCE
0x18002c7b7  cmovnz  rax, rbx
0x18002c7bb  mov     [rsp+98h+var_50], rcx; HMENU
0x18002c7c0  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x18002c7c7  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFDh; HWND
0x18002c7d0  mov     ebx, [rax+4]
0x18002c7d3  mov     r8d, [rax+8]
0x18002c7d7  mov     edi, [rax]
0x18002c7d9  sub     r8d, edi
0x18002c7dc  mov     r11d, [rax+0Ch]
0x18002c7e0  sub     r11d, ebx
0x18002c7e3  mov     [rsp+98h+var_60], r11d; int
0x18002c7e8  mov     [rsp+98h+var_68], r8d; int
0x18002c7ed  mov     r8, r14; lpWindowName
0x18002c7f0  mov     [rsp+98h+var_70], ebx; int
0x18002c7f4  mov     [rsp+98h+var_78], edi; int
0x18002c7f8  call    IsolationAwareCreateWindowExW
0x18002c7fd  jmp     loc_18002C6FA
0x18002c802  xor     r9d, r9d; lpArguments
0x18002c805  xor     r8d, r8d; nNumberOfArguments
0x18002c808  mov     ecx, 0C0000005h; dwExceptionCode
0x18002c80d  lea     edx, [r9+1]; dwExceptionFlags
0x18002c811  call    cs:__imp_RaiseException
```
