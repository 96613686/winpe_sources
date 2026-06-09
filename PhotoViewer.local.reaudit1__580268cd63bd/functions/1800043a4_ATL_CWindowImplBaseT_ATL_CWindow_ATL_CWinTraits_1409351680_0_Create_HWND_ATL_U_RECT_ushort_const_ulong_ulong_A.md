# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)

- ea: `0x1800043a4`
- end: `0x1800044f7`
- name: `?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z`
- size: `339`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e0c`
- `0x180003d60`
- `0x18002c454`

## callees

- `0x1800043a4`
- `0x180021a90`
- `0x180021ae0`
- `0x180033468`
- `0x180035b90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004422`
- `KERNEL32!GetCurrentThreadId` at `0x180004422`
- `KERNEL32!RaiseException` at `0x1800044f0`
- `KERNEL32!RaiseException` at `0x1800044f0`
- `KERNEL32!SetLastError` at `0x1800043db`
- `KERNEL32!SetLastError` at `0x1800043db`
- `KERNEL32!EnterCriticalSection` at `0x180004437`
- `KERNEL32!EnterCriticalSection` at `0x180004437`

## pseudocode

```c
HWND __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(
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
    JUMPOUT(0x1800044F6LL);
  }
  *((_QWORD *)a1 + 2) = a1;
  *((_DWORD *)a1 + 6) = GetCurrentThreadId();
  v17 = &stru_1800A3A88;
  EnterCriticalSection(&stru_1800A3A88);
  *((_QWORD *)a1 + 4) = qword_1800A3AB0;
  qword_1800A3AB0 = (__int64)(a1 + 4);
  v18 = 1;
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
0x1800043a4  push    rbx
0x1800043a6  push    rsi
0x1800043a7  push    rdi
0x1800043a8  push    r12
0x1800043aa  push    r14
0x1800043ac  push    r15
0x1800043ae  sub     rsp, 78h
0x1800043b2  mov     rax, [rcx+28h]
0x1800043b6  xor     r12d, r12d
0x1800043b9  mov     r14, r9
0x1800043bc  mov     rbx, r8
0x1800043bf  mov     r15, rdx
0x1800043c2  mov     rdi, rcx
0x1800043c5  test    rax, rax
0x1800043c8  jnz     short loc_1800043F1
0x1800043ca  call    AtlThunk_AllocateData
0x1800043cf  mov     [rdi+28h], rax
0x1800043d3  test    rax, rax
0x1800043d6  jnz     short loc_1800043F1
0x1800043d8  lea     ecx, [rax+0Eh]; dwErrCode
0x1800043db  call    cs:__imp_SetLastError
0x1800043e1  xor     eax, eax
0x1800043e3  add     rsp, 78h
0x1800043e7  pop     r15
0x1800043e9  pop     r14
0x1800043eb  pop     r12
0x1800043ed  pop     rdi
0x1800043ee  pop     rsi
0x1800043ef  pop     rbx
0x1800043f0  retn
0x1800043f1  xor     r8d, r8d; FirstParameter
0x1800043f4  xor     edx, edx; Proc
0x1800043f6  mov     rcx, rax; Thunk
0x1800043f9  call    AtlThunk_InitData
0x1800043fe  cmp     [rsp+0A8h+arg_38], r12w
0x180004407  jz      short loc_1800043E1
0x180004409  lea     rsi, [rdi+10h]
0x18000440d  test    rsi, rsi
0x180004410  jz      loc_1800044E1
0x180004416  test    rdi, rdi
0x180004419  jz      loc_1800044E1
0x18000441f  mov     [rsi], rdi
0x180004422  call    cs:__imp_GetCurrentThreadId
0x180004428  lea     rcx, stru_1800A3A88; lpCriticalSection
0x18000442f  mov     [rsi+8], eax
0x180004432  mov     [rsp+0A8h+var_48], rcx
0x180004437  call    cs:__imp_EnterCriticalSection
0x18000443d  mov     rax, cs:qword_1800A3AB0
0x180004444  lea     rcx, [rsp+0A8h+var_48]; this
0x180004449  mov     [rsi+10h], rax
0x18000444d  mov     cs:qword_1800A3AB0, rsi
0x180004454  mov     [rsp+0A8h+var_40], 1
0x180004459  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x18000445e  mov     rcx, [rsp+0A8h+arg_30]
0x180004466  mov     r9d, [rsp+0A8h+dwStyle]; dwStyle
0x18000446e  test    rcx, rcx
0x180004471  jnz     short loc_18000447C
0x180004473  bt      r9d, 1Eh
0x180004478  cmovb   rcx, rdi
0x18000447c  mov     r10, cs:hModule
0x180004483  lea     rax, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x18000448a  movzx   edx, [rsp+0A8h+arg_38]; lpClassName
0x180004492  test    rbx, rbx
0x180004495  mov     [rsp+0A8h+var_58], r10; HINSTANCE
0x18000449a  cmovnz  rax, rbx
0x18000449e  mov     [rsp+0A8h+var_60], rcx; HMENU
0x1800044a3  mov     ecx, [rsp+0A8h+dwExStyle]; dwExStyle
0x1800044aa  mov     [rsp+0A8h+var_68], r15; HWND
0x1800044af  mov     ebx, [rax+4]
0x1800044b2  mov     r8d, [rax+8]
0x1800044b6  mov     edi, [rax]
0x1800044b8  sub     r8d, edi
0x1800044bb  mov     r11d, [rax+0Ch]
0x1800044bf  sub     r11d, ebx
0x1800044c2  mov     [rsp+0A8h+var_70], r11d; int
0x1800044c7  mov     [rsp+0A8h+var_78], r8d; int
0x1800044cc  mov     r8, r14; lpWindowName
0x1800044cf  mov     [rsp+0A8h+var_80], ebx; int
0x1800044d3  mov     [rsp+0A8h+var_88], edi; int
0x1800044d7  call    IsolationAwareCreateWindowExW
0x1800044dc  jmp     loc_1800043E3
0x1800044e1  xor     r9d, r9d; lpArguments
0x1800044e4  xor     r8d, r8d; nNumberOfArguments
0x1800044e7  mov     ecx, 0C0000005h; dwExceptionCode
0x1800044ec  lea     edx, [r9+1]; dwExceptionFlags
0x1800044f0  call    cs:__imp_RaiseException
```
