# SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(ushort const *,ushort * *)

- ea: `0x180025450`
- end: `0x1800255f8`
- name: `?GetConfigManagerData@MamUpgradeToMdmLink@WorkAccess@SystemSettings@@QEAAJPEBGPEAPEAG@Z`
- size: `424`
- prototype: `int(SystemSettings::WorkAccess::MamUpgradeToMdmLink *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026be8`

## callees

- `0x1800096ec`
- `0x180023458`
- `0x180023ae0`
- `0x180025450`
- `0x1800290b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800255b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800255b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025477`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002550c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002550c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800255d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800255d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002556c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002556c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025555`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025555`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800254eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800254eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002551b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002551b`
- `OLEAUT32!__imp_SysFreeString` at `0x180025496`
- `OLEAUT32!__imp_SysFreeString` at `0x180025496`

## string_xrefs

- `0x18002558a`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::MamUpgradeToMdmLink::GetConfigManagerData(
        SystemSettings::WorkAccess::MamUpgradeToMdmLink *this,
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
    v9 = 649;
LABEL_11:
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
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
      v9 = 661;
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
0x180025450  mov     [rsp+arg_8], rbx
0x180025455  mov     [rsp+arg_10], rbp
0x18002545a  push    rsi
0x18002545b  push    rdi
0x18002545c  push    r14
0x18002545e  sub     rsp, 40h
0x180025462  mov     r14, r8
0x180025465  mov     rbx, rdx
0x180025468  lea     rsi, [rcx+0D8h]
0x18002546f  mov     [rsp+58h+var_28], rsi
0x180025474  mov     rcx, rsi; lpCriticalSection
0x180025477  call    cs:__imp_EnterCriticalSection
0x18002547e  nop     dword ptr [rax+rax+00h]
0x180025483  nop
0x180025484  xor     ebp, ebp
0x180025486  mov     [rsp+58h+ThreadId], ebp
0x18002548a  mov     rcx, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; bstrString
0x180025491  test    rcx, rcx
0x180025494  jz      short loc_1800254A9
0x180025496  call    cs:__imp_SysFreeString
0x18002549d  nop     dword ptr [rax+rax+00h]
0x1800254a2  mov     cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA, rbp; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x1800254a9  mov     rdx, rbx; unsigned __int16 *
0x1800254ac  lea     rcx, [rsp+58h+arg_18]; this
0x1800254b1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800254b6  mov     rdx, rax
0x1800254b9  lea     rcx, ?_stringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty
0x1800254c0  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800254c5  lea     rcx, [rsp+58h+arg_18]; this
0x1800254ca  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800254cf  lea     rax, [rsp+58h+ThreadId]
0x1800254d4  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800254d9  mov     [rsp+58h+dwCreationFlags], ebp; int
0x1800254dd  xor     r9d, r9d; lpParameter
0x1800254e0  lea     r8, ?GetStringByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z; lpStartAddress
0x1800254e7  xor     edx, edx; dwStackSize
0x1800254e9  xor     ecx, ecx; lpThreadAttributes
0x1800254eb  call    cs:__imp_CreateThread
0x1800254f2  nop     dword ptr [rax+rax+00h]
0x1800254f7  mov     rbx, rax
0x1800254fa  test    rax, rax
0x1800254fd  jnz     short loc_180025506
0x1800254ff  mov     edx, 289h
0x180025504  jmp     short loc_180025585
0x180025506  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025509  mov     rcx, rbx; hHandle
0x18002550c  call    cs:__imp_WaitForSingleObject
0x180025513  nop     dword ptr [rax+rax+00h]
0x180025518  mov     rcx, rbx; hObject
0x18002551b  call    cs:__imp_CloseHandle
0x180025522  nop     dword ptr [rax+rax+00h]
0x180025527  mov     rax, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x18002552e  test    rax, rax
0x180025531  jnz     short loc_18002553D
0x180025533  mov     ebx, 80004005h
0x180025538  jmp     loc_1800255D3
0x18002553d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025541  mov     rbx, rdi
0x180025544  inc     rbx
0x180025547  cmp     [rax+rbx*2], bp
0x18002554b  jnz     short loc_180025544
0x18002554d  lea     rbx, ds:2[rbx*2]
0x180025555  call    cs:__imp_GetProcessHeap
0x18002555c  nop     dword ptr [rax+rax+00h]
0x180025561  mov     rcx, rax; hHeap
0x180025564  mov     r8, rbx; dwBytes
0x180025567  mov     edx, 8; dwFlags
0x18002556c  call    cs:__imp_HeapAlloc
0x180025573  nop     dword ptr [rax+rax+00h]
0x180025578  mov     [r14], rax
0x18002557b  test    rax, rax
0x18002557e  jnz     short loc_1800255A0
0x180025580  mov     edx, 295h; void *
0x180025585  mov     ebx, 8007000Eh
0x18002558a  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180025591  mov     r9d, ebx; char *
0x180025594  mov     rcx, [rsp+58h]; this
0x180025599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002559e  jmp     short loc_1800255D3
0x1800255a0  mov     r8, cs:?_value@CEnrollmentHelper@WorkAccess@SystemSettings@@2PEAGEA; ushort * SystemSettings::WorkAccess::CEnrollmentHelper::_value
0x1800255a7  inc     rdi
0x1800255aa  cmp     [r8+rdi*2], bp
0x1800255af  jnz     short loc_1800255A7
0x1800255b1  lea     rdx, [rdi+1]
0x1800255b5  mov     rcx, rax
0x1800255b8  call    cs:__imp__o_wcscpy_s
0x1800255bf  nop     dword ptr [rax+rax+00h]
0x1800255c4  mov     ebx, eax
0x1800255c6  test    eax, eax
0x1800255c8  jle     short loc_1800255D3
0x1800255ca  movzx   ebx, ax
0x1800255cd  or      ebx, 80070000h
0x1800255d3  mov     rcx, rsi; lpCriticalSection
0x1800255d6  call    cs:__imp_LeaveCriticalSection
0x1800255dd  nop     dword ptr [rax+rax+00h]
0x1800255e2  mov     eax, ebx
0x1800255e4  mov     rbx, [rsp+58h+arg_8]
0x1800255e9  mov     rbp, [rsp+58h+arg_10]
0x1800255ee  add     rsp, 40h
0x1800255f2  pop     r14
0x1800255f4  pop     rdi
0x1800255f5  pop     rsi
0x1800255f6  retn
```
