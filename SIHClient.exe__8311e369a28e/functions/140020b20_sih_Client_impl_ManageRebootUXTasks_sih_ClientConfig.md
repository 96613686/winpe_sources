# sih::Client::impl::ManageRebootUXTasks(sih::ClientConfig)

- ea: `0x140020b20`
- end: `0x140020d22`
- name: `?ManageRebootUXTasks@impl@Client@sih@@QEAAXUClientConfig@3@@Z`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140021e70`

## callees

- `0x1400072b4`
- `0x1400073f0`
- `0x1400154b4`
- `0x140017650`
- `0x14001ed4c`
- `0x14002035c`
- `0x140020b20`
- `0x140045dc0`
- `0x1400481f8`
- `0x14004cd00`

## string_xrefs

- `0x140020cdf`: `Incorrect Task`
- `0x140020b9a`: `ManageRebootUXTasks with cv = %hs, actionID = %ws, misc = %ws, mode = %d`
- `0x140020bdc`: `ManageCommit`
- `0x140020c26`: `ManageCommit`
- `0x140020ca1`: `ManageRebootUXTasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall sih::Client::impl::ManageRebootUXTasks(sih::Client::impl *a1, __int64 a2)
{
  const wchar_t *v4; // rsi
  _QWORD *v5; // rbx
  FARPROC EngineProc; // rax
  const wchar_t *v7; // r8
  int v8; // ebx
  __int64 v9; // [rsp+20h] [rbp-89h]
  _OWORD pExceptionObject[2]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v11[80]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v12; // [rsp+C0h] [rbp+17h]

  v12 = a2;
  v4 = (const wchar_t *)(a2 + 56);
  Trace::GuidToString::GuidToString((Trace::GuidToString *)v11, (const struct _GUID *)(a2 + 40));
  v5 = (_QWORD *)(a2 + 8);
  WUTrace(0, 0, 0x400000, 4, 0, L"ManageRebootUXTasks with cv = %hs, actionID = %ws, misc = %ws, mode = %d");
  switch ( *(_DWORD *)a2 )
  {
    case 2:
      EngineProc = sih::Client::impl::GetEngineProc(a1, "ManageCommit");
      v7 = (const wchar_t *)(a2 + 56);
      if ( *(_QWORD *)(a2 + 80) > 7u )
        v7 = *(const wchar_t **)v7;
      if ( *(_QWORD *)(a2 + 32) > 0xFu )
        v5 = (_QWORD *)*v5;
      break;
    case 3:
      EngineProc = sih::Client::impl::GetEngineProc(a1, "ManageRebootUI");
      if ( *((_QWORD *)v4 + 3) > 7u )
        v4 = *(const wchar_t **)v4;
      if ( *(_QWORD *)(a2 + 32) > 0xFu )
        v5 = (_QWORD *)*v5;
      v7 = v4;
      break;
    case 4:
      EngineProc = sih::Client::impl::GetEngineProc(a1, "ManageCommit");
      if ( *(_QWORD *)(a2 + 32) > 0xFu )
        v5 = (_QWORD *)*v5;
      v7 = L"PostReboot";
      break;
    default:
      LODWORD(v9) = -2145103361;
      WUTrace(0, 0, 0x400000, 1, v9, L"Incorrect Task");
      sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, -2145103361);
      throw (sih::hr_exception *)pExceptionObject;
  }
  pExceptionObject[0] = *(_OWORD *)(a2 + 40);
  v8 = ((__int64 (__fastcall *)(_OWORD *, _QWORD *, const wchar_t *))EngineProc)(pExceptionObject, v5, v7);
  if ( v8 < 0 )
  {
    LODWORD(v9) = v8;
    WUTrace(0, 0, 0x400000, 1, v9, L"ManageRebootUXTasks");
    sih::hr_exception::hr_exception((sih::hr_exception *)pExceptionObject, v8);
    throw (sih::hr_exception *)pExceptionObject;
  }
  std::wstring::~wstring((_QWORD *)(a2 + 56));
  std::string::~string(a2 + 8);
}

```

## disassembly

```asm
0x140020b20  mov     [rsp-8+arg_10], rbx
0x140020b25  push    rbp
0x140020b26  push    rsi
0x140020b27  push    rdi
0x140020b28  push    r12
0x140020b2a  push    r13
0x140020b2c  push    r14
0x140020b2e  push    r15
0x140020b30  lea     rbp, [rsp-27h]
0x140020b35  sub     rsp, 0D0h
0x140020b3c  mov     rax, cs:__security_cookie
0x140020b43  xor     rax, rsp
0x140020b46  mov     [rbp+57h+var_38], rax
0x140020b4a  mov     rdi, rdx
0x140020b4d  mov     r14, rcx
0x140020b50  mov     [rbp+57h+var_40], rdx
0x140020b54  mov     r13d, [rdx]
0x140020b57  lea     rsi, [rdx+38h]
0x140020b5b  mov     r15, rsi
0x140020b5e  cmp     qword ptr [rsi+18h], 7
0x140020b63  jbe     short loc_140020B68
0x140020b65  mov     r15, [rsi]
0x140020b68  add     rdx, 28h ; '('; struct _GUID *
0x140020b6c  lea     rcx, [rbp+57h+var_90]; this
0x140020b70  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x140020b75  lea     rbx, [rdi+8]
0x140020b79  mov     rcx, rbx
0x140020b7c  cmp     qword ptr [rbx+18h], 0Fh
0x140020b81  jbe     short loc_140020B86
0x140020b83  mov     rcx, [rbx]
0x140020b86  mov     [rsp+100h+var_B8], r13d
0x140020b8b  mov     [rsp+100h+var_C0], r15
0x140020b90  mov     [rsp+100h+var_C8], rax
0x140020b95  mov     [rsp+100h+var_D0], rcx
0x140020b9a  lea     rax, aManagerebootux_1; "ManageRebootUXTasks with cv = %hs, acti"...
0x140020ba1  mov     [rsp+100h+var_D8], rax
0x140020ba6  mov     [rsp+100h+var_E0], 0
0x140020baf  mov     r9d, 4
0x140020bb5  mov     r15d, 400000h
0x140020bbb  mov     r8d, r15d
0x140020bbe  xor     edx, edx
0x140020bc0  xor     ecx, ecx
0x140020bc2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140020bc7  mov     ecx, [rdi]
0x140020bc9  sub     ecx, 2
0x140020bcc  jz      short loc_140020C26
0x140020bce  sub     ecx, 1
0x140020bd1  jz      short loc_140020BFE
0x140020bd3  cmp     ecx, 1
0x140020bd6  jnz     loc_140020CDF
0x140020bdc  lea     rdx, aManagecommit; "ManageCommit"
0x140020be3  mov     rcx, r14; this
0x140020be6  call    ?GetEngineProc@impl@Client@sih@@AEAAP6A_JXZPEBD@Z; sih::Client::impl::GetEngineProc(char const *)
0x140020beb  cmp     qword ptr [rbx+18h], 0Fh
0x140020bf0  jbe     short loc_140020BF5
0x140020bf2  mov     rbx, [rbx]
0x140020bf5  lea     r8, aPostreboot_0; "PostReboot"
0x140020bfc  jmp     short loc_140020C4D
0x140020bfe  lea     rdx, aManagerebootui_0; "ManageRebootUI"
0x140020c05  mov     rcx, r14; this
0x140020c08  call    ?GetEngineProc@impl@Client@sih@@AEAAP6A_JXZPEBD@Z; sih::Client::impl::GetEngineProc(char const *)
0x140020c0d  cmp     qword ptr [rsi+18h], 7
0x140020c12  jbe     short loc_140020C17
0x140020c14  mov     rsi, [rsi]
0x140020c17  cmp     qword ptr [rbx+18h], 0Fh
0x140020c1c  jbe     short loc_140020C21
0x140020c1e  mov     rbx, [rbx]
0x140020c21  mov     r8, rsi
0x140020c24  jmp     short loc_140020C4D
0x140020c26  lea     rdx, aManagecommit; "ManageCommit"
0x140020c2d  mov     rcx, r14; this
0x140020c30  call    ?GetEngineProc@impl@Client@sih@@AEAAP6A_JXZPEBD@Z; sih::Client::impl::GetEngineProc(char const *)
0x140020c35  lea     r8, [rdi+38h]
0x140020c39  cmp     qword ptr [r8+18h], 7
0x140020c3e  jbe     short loc_140020C43
0x140020c40  mov     r8, [r8]
0x140020c43  cmp     qword ptr [rbx+18h], 0Fh
0x140020c48  jbe     short loc_140020C4D
0x140020c4a  mov     rbx, [rbx]
0x140020c4d  movups  xmm0, xmmword ptr [rdi+28h]
0x140020c51  movdqu  [rbp+57h+pExceptionObject], xmm0
0x140020c56  mov     rdx, rbx
0x140020c59  lea     rcx, [rbp+57h+pExceptionObject]
0x140020c5d  call    _guard_dispatch_icall
0x140020c62  mov     ebx, eax
0x140020c64  test    eax, eax
0x140020c66  js      short loc_140020CA1
0x140020c68  lea     rcx, [rdi+38h]; void *
0x140020c6c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140020c71  lea     rcx, [rdi+8]
0x140020c75  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140020c7a  mov     rcx, [rbp+57h+var_38]
0x140020c7e  xor     rcx, rsp; StackCookie
0x140020c81  call    __security_check_cookie
0x140020c86  mov     rbx, [rsp+100h+arg_10]
0x140020c8e  add     rsp, 0D0h
0x140020c95  pop     r15
0x140020c97  pop     r14
0x140020c99  pop     r13
0x140020c9b  pop     r12
0x140020c9d  pop     rdi
0x140020c9e  pop     rsi
0x140020c9f  pop     rbp
0x140020ca0  retn
0x140020ca1  lea     rax, aManagerebootux; "ManageRebootUXTasks"
0x140020ca8  mov     [rsp+100h+var_D8], rax
0x140020cad  mov     dword ptr [rsp+100h+var_E0], ebx
0x140020cb1  mov     r9d, 1
0x140020cb7  mov     r8d, r15d
0x140020cba  xor     edx, edx
0x140020cbc  xor     ecx, ecx
0x140020cbe  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140020cc3  mov     edx, ebx; int
0x140020cc5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140020cc9  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140020cce  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140020cd5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140020cd9  call    _CxxThrowException
0x140020cdf  lea     rax, aIncorrectTask; "Incorrect Task"
0x140020ce6  mov     [rsp+100h+var_D8], rax
0x140020ceb  mov     ebx, 802451FFh
0x140020cf0  mov     dword ptr [rsp+100h+var_E0], ebx
0x140020cf4  mov     r9d, 1
0x140020cfa  mov     r8d, r15d
0x140020cfd  xor     edx, edx
0x140020cff  xor     ecx, ecx
0x140020d01  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140020d06  mov     edx, ebx; int
0x140020d08  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140020d0c  call    ??0hr_exception@sih@@QEAA@J@Z; sih::hr_exception::hr_exception(long)
0x140020d11  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140020d18  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140020d1c  call    _CxxThrowException
```
