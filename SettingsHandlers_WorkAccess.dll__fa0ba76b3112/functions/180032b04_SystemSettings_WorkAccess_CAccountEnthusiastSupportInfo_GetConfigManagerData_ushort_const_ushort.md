# SystemSettings::WorkAccess::CAccountEnthusiastSupportInfo::GetConfigManagerData(ushort const *,ushort * *)

- ea: `0x180032b04`
- end: `0x180032cac`
- name: `?GetConfigManagerData@CAccountEnthusiastSupportInfo@WorkAccess@SystemSettings@@QEAAJPEBGPEAPEAG@Z`
- size: `424`
- prototype: `int(SystemSettings::WorkAccess::CAccountEnthusiastSupportInfo *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800335a0`

## callees

- `0x1800096ec`
- `0x180023458`
- `0x180023ae0`
- `0x1800290b8`
- `0x180032b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032c6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032c6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032b2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032b2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bc0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032c20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032c20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032c09`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032b9f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180032b9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032bcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180032b4a`
- `OLEAUT32!__imp_SysFreeString` at `0x180032b4a`

## string_xrefs

- `0x180032c3e`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CAccountEnthusiastSupportInfo::GetConfigManagerData(
        SystemSettings::WorkAccess::CAccountEnthusiastSupportInfo *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  _bstr_t *v6; // rax
  HANDLE v7; // rax
  void *v8; // rbx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  int v15; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF
  char v20; // [rsp+78h] [rbp+20h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  ThreadId = 0;
  if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value )
  {
    SysFreeString(SystemSettings::WorkAccess::CEnrollmentHelper::_value);
    SystemSettings::WorkAccess::CEnrollmentHelper::_value = 0;
  }
  v6 = _bstr_t::_bstr_t((_bstr_t *)&v20, a2);
  _bstr_t::operator=(&SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty, v6);
  _bstr_t::_Free((_bstr_t *)&v20);
  v7 = CreateThread(
         0,
         0,
         (LPTHREAD_START_ROUTINE)SystemSettings::WorkAccess::CEnrollmentHelper::GetStringByNodePath,
         0,
         0,
         &ThreadId);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 929;
LABEL_11:
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
    goto LABEL_15;
  }
  WaitForSingleObject(v7, 0xFFFFFFFF);
  CloseHandle(v8);
  if ( SystemSettings::WorkAccess::CEnrollmentHelper::_value )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( SystemSettings::WorkAccess::CEnrollmentHelper::_value[v12] );
    ProcessHeap = GetProcessHeap();
    v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v12 + 2);
    *a3 = v14;
    if ( !v14 )
    {
      v9 = 941;
      goto LABEL_11;
    }
    do
      ++v11;
    while ( SystemSettings::WorkAccess::CEnrollmentHelper::_value[v11] );
    v15 = _o_wcscpy_s(v14, v11 + 1, SystemSettings::WorkAccess::CEnrollmentHelper::_value);
    v10 = v15;
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v10 = -2147467259;
  }
LABEL_15:
  LeaveCriticalSection(v5);
  return v10;
}

```

## disassembly

```asm
0x180032b04  mov     [rsp+arg_8], rbx
0x180032b09  mov     [rsp+arg_10], rbp
0x180032b0e  push    rsi
0x180032b0f  push    rdi
0x180032b10  push    r14
0x180032b12  sub     rsp, 40h
0x180032b16  mov     r14, r8
0x180032b19  mov     rbx, rdx
0x180032b1c  lea     rsi, [rcx+0D8h]
0x180032b23  mov     [rsp+58h+var_28], rsi
0x180032b28  mov     rcx, rsi; lpCriticalSection
0x180032b2b  call    cs:__imp_EnterCriticalSection
0x180032b32  nop     dword ptr [rax+rax+00h]
0x180032b37  nop
0x180032b38  xor     ebp, ebp
0x180032b3a  mov     [rsp+58h+ThreadId], ebp
0x180032b3e  mov     rcx, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; bstrString
0x180032b45  test    rcx, rcx
0x180032b48  jz      short loc_180032B5D
0x180032b4a  call    cs:__imp_SysFreeString
0x180032b51  nop     dword ptr [rax+rax+00h]
0x180032b56  mov     cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, rbp; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180032b5d  mov     rdx, rbx; unsigned __int16 *
0x180032b60  lea     rcx, [rsp+58h+arg_18]; this
0x180032b65  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180032b6a  mov     rdx, rax
0x180032b6d  lea     rcx, ?_stringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty
0x180032b74  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180032b79  lea     rcx, [rsp+58h+arg_18]; this
0x180032b7e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180032b83  lea     rax, [rsp+58h+ThreadId]
0x180032b88  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180032b8d  mov     [rsp+58h+dwCreationFlags], ebp; int
0x180032b91  xor     r9d, r9d; lpParameter
0x180032b94  lea     r8, ?GetStringByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x180032b9b  xor     edx, edx; dwStackSize
0x180032b9d  xor     ecx, ecx; lpThreadAttributes
0x180032b9f  call    cs:__imp_CreateThread
0x180032ba6  nop     dword ptr [rax+rax+00h]
0x180032bab  mov     rbx, rax
0x180032bae  test    rax, rax
0x180032bb1  jnz     short loc_180032BBA
0x180032bb3  mov     edx, 3A1h
0x180032bb8  jmp     short loc_180032C39
0x180032bba  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032bbd  mov     rcx, rbx; hHandle
0x180032bc0  call    cs:__imp_WaitForSingleObject
0x180032bc7  nop     dword ptr [rax+rax+00h]
0x180032bcc  mov     rcx, rbx; hObject
0x180032bcf  call    cs:__imp_CloseHandle
0x180032bd6  nop     dword ptr [rax+rax+00h]
0x180032bdb  mov     rax, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180032be2  test    rax, rax
0x180032be5  jnz     short loc_180032BF1
0x180032be7  mov     ebx, 80004005h
0x180032bec  jmp     loc_180032C87
0x180032bf1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032bf5  mov     rbx, rdi
0x180032bf8  inc     rbx
0x180032bfb  cmp     [rax+rbx*2], bp
0x180032bff  jnz     short loc_180032BF8
0x180032c01  lea     rbx, ds:2[rbx*2]
0x180032c09  call    cs:__imp_GetProcessHeap
0x180032c10  nop     dword ptr [rax+rax+00h]
0x180032c15  mov     rcx, rax; hHeap
0x180032c18  mov     r8, rbx; dwBytes
0x180032c1b  mov     edx, 8; dwFlags
0x180032c20  call    cs:__imp_HeapAlloc
0x180032c27  nop     dword ptr [rax+rax+00h]
0x180032c2c  mov     [r14], rax
0x180032c2f  test    rax, rax
0x180032c32  jnz     short loc_180032C54
0x180032c34  mov     edx, 3ADh; void *
0x180032c39  mov     ebx, 8007000Eh
0x180032c3e  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032c45  mov     r9d, ebx; char *
0x180032c48  mov     rcx, [rsp+58h]; this
0x180032c4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c52  jmp     short loc_180032C87
0x180032c54  mov     r8, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180032c5b  inc     rdi
0x180032c5e  cmp     [r8+rdi*2], bp
0x180032c63  jnz     short loc_180032C5B
0x180032c65  lea     rdx, [rdi+1]
0x180032c69  mov     rcx, rax
0x180032c6c  call    cs:__imp__o_wcscpy_s
0x180032c73  nop     dword ptr [rax+rax+00h]
0x180032c78  mov     ebx, eax
0x180032c7a  test    eax, eax
0x180032c7c  jle     short loc_180032C87
0x180032c7e  movzx   ebx, ax
0x180032c81  or      ebx, 80070000h
0x180032c87  mov     rcx, rsi; lpCriticalSection
0x180032c8a  call    cs:__imp_LeaveCriticalSection
0x180032c91  nop     dword ptr [rax+rax+00h]
0x180032c96  mov     eax, ebx
0x180032c98  mov     rbx, [rsp+58h+arg_8]
0x180032c9d  mov     rbp, [rsp+58h+arg_10]
0x180032ca2  add     rsp, 40h
0x180032ca6  pop     r14
0x180032ca8  pop     rdi
0x180032ca9  pop     rsi
0x180032caa  retn
```
