# SystemSettings::WorkAccess::CAccountEnthusiastConnectionInfo::GetConfigManagerData(ushort const *,ushort * *)

- ea: `0x180032954`
- end: `0x180032afc`
- name: `?GetConfigManagerData@CAccountEnthusiastConnectionInfo@WorkAccess@SystemSettings@@QEAAJPEBGPEAPEAG@Z`
- size: `424`
- prototype: `int(SystemSettings::WorkAccess::CAccountEnthusiastConnectionInfo *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800333e0`

## callees

- `0x1800096ec`
- `0x180023458`
- `0x180023ae0`
- `0x1800290b8`
- `0x180032954`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032abc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180032abc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003297b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003297b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032a10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032a10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032ada`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032a59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032a59`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800329ef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800329ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003299a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003299a`

## string_xrefs

- `0x180032a8e`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CAccountEnthusiastConnectionInfo::GetConfigManagerData(
        SystemSettings::WorkAccess::CAccountEnthusiastConnectionInfo *this,
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
    v9 = 1070;
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
      v9 = 1082;
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
0x180032954  mov     [rsp+arg_8], rbx
0x180032959  mov     [rsp+arg_10], rbp
0x18003295e  push    rsi
0x18003295f  push    rdi
0x180032960  push    r14
0x180032962  sub     rsp, 40h
0x180032966  mov     r14, r8
0x180032969  mov     rbx, rdx
0x18003296c  lea     rsi, [rcx+0D8h]
0x180032973  mov     [rsp+58h+var_28], rsi
0x180032978  mov     rcx, rsi; lpCriticalSection
0x18003297b  call    cs:__imp_EnterCriticalSection
0x180032982  nop     dword ptr [rax+rax+00h]
0x180032987  nop
0x180032988  xor     ebp, ebp
0x18003298a  mov     [rsp+58h+ThreadId], ebp
0x18003298e  mov     rcx, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; bstrString
0x180032995  test    rcx, rcx
0x180032998  jz      short loc_1800329AD
0x18003299a  call    cs:__imp_SysFreeString
0x1800329a1  nop     dword ptr [rax+rax+00h]
0x1800329a6  mov     cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, rbp; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x1800329ad  mov     rdx, rbx; unsigned __int16 *
0x1800329b0  lea     rcx, [rsp+58h+arg_18]; this
0x1800329b5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800329ba  mov     rdx, rax
0x1800329bd  lea     rcx, ?_stringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty
0x1800329c4  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800329c9  lea     rcx, [rsp+58h+arg_18]; this
0x1800329ce  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800329d3  lea     rax, [rsp+58h+ThreadId]
0x1800329d8  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800329dd  mov     [rsp+58h+dwCreationFlags], ebp; int
0x1800329e1  xor     r9d, r9d; lpParameter
0x1800329e4  lea     r8, ?GetStringByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x1800329eb  xor     edx, edx; dwStackSize
0x1800329ed  xor     ecx, ecx; lpThreadAttributes
0x1800329ef  call    cs:__imp_CreateThread
0x1800329f6  nop     dword ptr [rax+rax+00h]
0x1800329fb  mov     rbx, rax
0x1800329fe  test    rax, rax
0x180032a01  jnz     short loc_180032A0A
0x180032a03  mov     edx, 42Eh
0x180032a08  jmp     short loc_180032A89
0x180032a0a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180032a0d  mov     rcx, rbx; hHandle
0x180032a10  call    cs:__imp_WaitForSingleObject
0x180032a17  nop     dword ptr [rax+rax+00h]
0x180032a1c  mov     rcx, rbx; hObject
0x180032a1f  call    cs:__imp_CloseHandle
0x180032a26  nop     dword ptr [rax+rax+00h]
0x180032a2b  mov     rax, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180032a32  test    rax, rax
0x180032a35  jnz     short loc_180032A41
0x180032a37  mov     ebx, 80004005h
0x180032a3c  jmp     loc_180032AD7
0x180032a41  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180032a45  mov     rbx, rdi
0x180032a48  inc     rbx
0x180032a4b  cmp     [rax+rbx*2], bp
0x180032a4f  jnz     short loc_180032A48
0x180032a51  lea     rbx, ds:2[rbx*2]
0x180032a59  call    cs:__imp_GetProcessHeap
0x180032a60  nop     dword ptr [rax+rax+00h]
0x180032a65  mov     rcx, rax; hHeap
0x180032a68  mov     r8, rbx; dwBytes
0x180032a6b  mov     edx, 8; dwFlags
0x180032a70  call    cs:__imp_HeapAlloc
0x180032a77  nop     dword ptr [rax+rax+00h]
0x180032a7c  mov     [r14], rax
0x180032a7f  test    rax, rax
0x180032a82  jnz     short loc_180032AA4
0x180032a84  mov     edx, 43Ah; void *
0x180032a89  mov     ebx, 8007000Eh
0x180032a8e  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032a95  mov     r9d, ebx; char *
0x180032a98  mov     rcx, [rsp+58h]; this
0x180032a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032aa2  jmp     short loc_180032AD7
0x180032aa4  mov     r8, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x180032aab  inc     rdi
0x180032aae  cmp     [r8+rdi*2], bp
0x180032ab3  jnz     short loc_180032AAB
0x180032ab5  lea     rdx, [rdi+1]
0x180032ab9  mov     rcx, rax
0x180032abc  call    cs:__imp__o_wcscpy_s
0x180032ac3  nop     dword ptr [rax+rax+00h]
0x180032ac8  mov     ebx, eax
0x180032aca  test    eax, eax
0x180032acc  jle     short loc_180032AD7
0x180032ace  movzx   ebx, ax
0x180032ad1  or      ebx, 80070000h
0x180032ad7  mov     rcx, rsi; lpCriticalSection
0x180032ada  call    cs:__imp_LeaveCriticalSection
0x180032ae1  nop     dword ptr [rax+rax+00h]
0x180032ae6  mov     eax, ebx
0x180032ae8  mov     rbx, [rsp+58h+arg_8]
0x180032aed  mov     rbp, [rsp+58h+arg_10]
0x180032af2  add     rsp, 40h
0x180032af6  pop     r14
0x180032af8  pop     rdi
0x180032af9  pop     rsi
0x180032afa  retn
```
