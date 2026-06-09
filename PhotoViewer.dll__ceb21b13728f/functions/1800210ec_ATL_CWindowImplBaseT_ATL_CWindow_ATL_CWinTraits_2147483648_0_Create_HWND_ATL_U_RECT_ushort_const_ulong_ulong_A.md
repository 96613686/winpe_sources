# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<2147483648,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x1800210ec`
- end: `0x18002123c`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0IAAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004b710`

## callees

- `0x1800210ec`
- `0x180021a90`
- `0x180021ae0`
- `0x180033468`
- `0x180035b90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021163`
- `KERNEL32!GetCurrentThreadId` at `0x180021163`
- `KERNEL32!RaiseException` at `0x180021235`
- `KERNEL32!RaiseException` at `0x180021235`
- `KERNEL32!SetLastError` at `0x18002111e`
- `KERNEL32!SetLastError` at `0x18002111e`
- `KERNEL32!EnterCriticalSection` at `0x180021178`
- `KERNEL32!EnterCriticalSection` at `0x180021178`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<2147483648,0>>::Create(
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
    JUMPOUT(0x18002123BLL);
  }
  *((_QWORD *)a1 + 2) = a1;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  v16 = &stru_1800A3A88;
  EnterCriticalSection(&stru_1800A3A88);
  *((_QWORD *)a1 + 4) = qword_1800A3AB0;
  qword_1800A3AB0 = (__int64)(a1 + 4);
  v17 = 1;
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
0x1800210ec  push    rbx
0x1800210ee  push    rsi
0x1800210ef  push    rdi
0x1800210f0  push    r14
0x1800210f2  push    r15
0x1800210f4  sub     rsp, 70h
0x1800210f8  mov     rax, [rcx+28h]
0x1800210fc  xor     r15d, r15d
0x1800210ff  mov     r14, r9
0x180021102  mov     rbx, r8
0x180021105  mov     rdi, rcx
0x180021108  test    rax, rax
0x18002110b  jnz     short loc_180021132
0x18002110d  call    AtlThunk_AllocateData
0x180021112  mov     [rdi+28h], rax
0x180021116  test    rax, rax
0x180021119  jnz     short loc_180021132
0x18002111b  lea     ecx, [rax+0Eh]; dwErrCode
0x18002111e  call    cs:__imp_SetLastError
0x180021124  xor     eax, eax
0x180021126  add     rsp, 70h
0x18002112a  pop     r15
0x18002112c  pop     r14
0x18002112e  pop     rdi
0x18002112f  pop     rsi
0x180021130  pop     rbx
0x180021131  retn
0x180021132  xor     r8d, r8d; FirstParameter
0x180021135  xor     edx, edx; Proc
0x180021137  mov     rcx, rax; Thunk
0x18002113a  call    AtlThunk_InitData
0x18002113f  cmp     [rsp+98h+arg_38], r15w
0x180021148  jz      short loc_180021124
0x18002114a  lea     rsi, [rdi+10h]
0x18002114e  test    rsi, rsi
0x180021151  jz      loc_180021226
0x180021157  test    rdi, rdi
0x18002115a  jz      loc_180021226
0x180021160  mov     [rsi], rdi
0x180021163  call    cs:__imp_GetCurrentThreadId
0x180021169  lea     rcx, stru_1800A3A88; lpCriticalSection
0x180021170  mov     [rsi+8], eax
0x180021173  mov     [rsp+98h+var_38], rcx
0x180021178  call    cs:__imp_EnterCriticalSection
0x18002117e  mov     rax, cs:qword_1800A3AB0
0x180021185  lea     rcx, [rsp+98h+var_38]; this
0x18002118a  mov     [rsi+10h], rax
0x18002118e  mov     cs:qword_1800A3AB0, rsi
0x180021195  mov     [rsp+98h+var_30], 1
0x18002119a  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18002119f  mov     rcx, [rsp+98h+arg_30]
0x1800211a7  mov     r9d, [rsp+98h+dwStyle]; dwStyle
0x1800211af  test    rcx, rcx
0x1800211b2  jnz     short loc_1800211BD
0x1800211b4  bt      r9d, 1Eh
0x1800211b9  cmovb   rcx, rdi
0x1800211bd  mov     r10, cs:hModule
0x1800211c4  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x1800211cb  movzx   edx, [rsp+98h+arg_38]; lpClassName
0x1800211d3  test    rbx, rbx
0x1800211d6  mov     [rsp+98h+var_48], r10; HINSTANCE
0x1800211db  cmovnz  rax, rbx
0x1800211df  mov     [rsp+98h+var_50], rcx; HMENU
0x1800211e4  mov     ecx, [rsp+98h+dwExStyle]; dwExStyle
0x1800211eb  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFDh; HWND
0x1800211f4  mov     ebx, [rax+4]
0x1800211f7  mov     r8d, [rax+8]
0x1800211fb  mov     edi, [rax]
0x1800211fd  sub     r8d, edi
0x180021200  mov     r11d, [rax+0Ch]
0x180021204  sub     r11d, ebx
0x180021207  mov     [rsp+98h+var_60], r11d; int
0x18002120c  mov     [rsp+98h+var_68], r8d; int
0x180021211  mov     r8, r14; lpWindowName
0x180021214  mov     [rsp+98h+var_70], ebx; int
0x180021218  mov     [rsp+98h+var_78], edi; int
0x18002121c  call    IsolationAwareCreateWindowExW
0x180021221  jmp     loc_180021126
0x180021226  xor     r9d, r9d; lpArguments
0x180021229  xor     r8d, r8d; nNumberOfArguments
0x18002122c  mov     ecx, 0C0000005h; dwExceptionCode
0x180021231  lea     edx, [r9+1]; dwExceptionFlags
0x180021235  call    cs:__imp_RaiseException
```
