# CExec::Svc::Service::SignalServiceStarted(void)

- ea: `0x1400121f0`
- end: `0x1400123fb`
- name: `?SignalServiceStarted@Service@Svc@CExec@@AEAAXXZ`
- size: `523`
- prototype: `void __fastcall(CExec::Svc::Service *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140010b20`

## callees

- `0x140002310`
- `0x1400068ac`
- `0x140008160`
- `0x14000894c`
- `0x14000e3a4`
- `0x1400121f0`
- `0x140014f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140012384`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140012384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001233c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400122c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001233c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001235d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400122e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001235d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400122ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400122ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012377`
- `ntdll!NtCreateEvent` at `0x140012305`
- `ntdll!NtCreateEvent` at `0x140012305`

## string_xrefs

- `0x1400123cf`: `onecore\vm\compute\service\cexec\common\cexecevent.cpp`

## pseudocode

```c
void __fastcall CExec::Svc::Service::SignalServiceStarted(CExec::Svc::Service *this)
{
  __int128 *p_Src; // rax
  NTSTATUS v3; // eax
  HANDLE *v4; // rbx
  HANDLE v5; // rsi
  HANDLE v6; // rdi
  DWORD LastError; // r14d
  __int64 v8; // r8
  const char *v9; // r9
  HANDLE v10; // rcx
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // r8
  const char *v14; // r9
  int InitialState; // [rsp+20h] [rbp-49h]
  HANDLE hObject; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+38h] [rbp-31h]
  _WORD v18[2]; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+44h] [rbp-25h]
  __int128 *v20; // [rsp+48h] [rbp-21h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int128 Src; // [rsp+80h] [rbp+17h] BYREF
  __int64 v23; // [rsp+90h] [rbp+27h]
  unsigned __int64 v24; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  hObject = 0;
  v17 = 1;
  Src = 0;
  v23 = 0;
  v24 = 0;
  std::wstring::_Construct<1,unsigned short const *>((__int64)&Src, &szPassword, 0);
  std::wstring::operator+=(&Src, L"\\CExecSvcStarted");
  v18[0] = 2 * v23;
  v18[1] = 2 * v23;
  v19 = 0;
  p_Src = &Src;
  if ( v24 > 7 )
    p_Src = (__int128 *)Src;
  v20 = p_Src;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 128;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  hObject = 0;
  v3 = NtCreateEvent(&hObject, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\common\\cexecevent.cpp",
      (const char *)(unsigned int)v3,
      InitialState);
  std::wstring::~wstring((char **)&Src);
  v4 = (HANDLE *)((char *)this + 240);
  if ( (HANDLE *)((char *)this + 240) == &hObject )
  {
    v10 = hObject;
  }
  else
  {
    v5 = hObject;
    v6 = *v4;
    if ( *v4 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
      SetLastError(LastError);
    }
    *v4 = v5;
    v10 = 0;
    hObject = 0;
  }
  if ( v10 && !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
  if ( !SetEvent(*v4) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v13, v14);
}

```

## disassembly

```asm
0x1400121f0  mov     [rsp-8+arg_8], rbx
0x1400121f5  mov     [rsp-8+arg_10], rsi
0x1400121fa  push    rbp
0x1400121fb  push    rdi
0x1400121fc  push    r14
0x1400121fe  lea     rbp, [rsp-47h]
0x140012203  sub     rsp, 0B0h
0x14001220a  mov     rax, cs:__security_cookie
0x140012211  xor     rax, rsp
0x140012214  mov     [rbp+57h+var_20], rax
0x140012218  mov     rsi, rcx
0x14001221b  mov     [rbp+57h+var_88], 0
0x140012222  mov     [rbp+57h+hObject], 0
0x14001222a  mov     [rbp+57h+var_88], 1
0x140012231  xorps   xmm0, xmm0
0x140012234  movups  [rbp+57h+Src], xmm0
0x140012238  mov     [rbp+57h+var_30], 0
0x140012240  mov     [rbp+57h+var_28], 0
0x140012248  xor     r8d, r8d
0x14001224b  lea     rdx, szPassword
0x140012252  lea     rcx, [rbp+57h+Src]
0x140012256  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14001225b  nop
0x14001225c  lea     rdx, aCexecsvcstarte; "\\CExecSvcStarted"
0x140012263  lea     rcx, [rbp+57h+Src]; Src
0x140012267  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14001226c  movzx   eax, word ptr [rbp+57h+var_30]
0x140012270  add     ax, ax
0x140012273  mov     [rbp+57h+var_80], ax
0x140012277  mov     [rbp+57h+var_7E], ax
0x14001227b  xor     eax, eax
0x14001227d  mov     [rbp+57h+var_7C], eax
0x140012280  lea     rax, [rbp+57h+Src]
0x140012284  cmp     [rbp+57h+var_28], 7
0x140012289  cmova   rax, qword ptr [rbp+57h+Src]
0x14001228e  mov     [rbp+57h+var_78], rax
0x140012292  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001229a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 80h
0x1400122a2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400122aa  lea     rax, [rbp+57h+var_80]
0x1400122ae  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400122b2  xorps   xmm0, xmm0
0x1400122b5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400122ba  mov     rdi, [rbp+57h+hObject]
0x1400122be  test    rdi, rdi
0x1400122c1  jz      short loc_1400122E8
0x1400122c3  call    cs:__imp_GetLastError
0x1400122c9  mov     ebx, eax
0x1400122cb  mov     rcx, rdi; hObject
0x1400122ce  call    cs:__imp_CloseHandle
0x1400122d4  mov     rcx, [rbp+5Fh]; this
0x1400122d8  test    eax, eax
0x1400122da  jz      loc_1400123C1
0x1400122e0  mov     ecx, ebx; dwErrCode
0x1400122e2  call    cs:__imp_SetLastError
0x1400122e8  mov     [rbp+57h+hObject], 0
0x1400122f0  mov     byte ptr [rsp+0C0h+InitialState], 0; int
0x1400122f5  xor     r9d, r9d; EventType
0x1400122f8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400122fc  mov     edx, 1F0003h; DesiredAccess
0x140012301  lea     rcx, [rbp+57h+hObject]; EventHandle
0x140012305  call    cs:__imp_NtCreateEvent
0x14001230b  mov     rcx, [rbp+5Fh]; this
0x14001230f  test    eax, eax
0x140012311  js      loc_1400123CC
0x140012317  lea     rcx, [rbp+57h+Src]
0x14001231b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140012320  lea     rbx, [rsi+0F0h]
0x140012327  lea     rax, [rbp+57h+hObject]
0x14001232b  cmp     rbx, rax
0x14001232e  jz      short loc_14001236E
0x140012330  mov     rsi, [rbp+57h+hObject]
0x140012334  mov     rdi, [rbx]
0x140012337  test    rdi, rdi
0x14001233a  jz      short loc_140012363
0x14001233c  call    cs:__imp_GetLastError
0x140012342  mov     r14d, eax
0x140012345  mov     rcx, rdi; hObject
0x140012348  call    cs:__imp_CloseHandle
0x14001234e  mov     rcx, [rbp+5Fh]; this
0x140012352  test    eax, eax
0x140012354  jz      loc_1400123E1
0x14001235a  mov     ecx, r14d; dwErrCode
0x14001235d  call    cs:__imp_SetLastError
0x140012363  mov     [rbx], rsi
0x140012366  xor     ecx, ecx
0x140012368  mov     [rbp+57h+hObject], rcx
0x14001236c  jmp     short loc_140012372
0x14001236e  mov     rcx, [rbp+57h+hObject]; hObject
0x140012372  test    rcx, rcx
0x140012375  jz      short loc_140012381
0x140012377  call    cs:__imp_CloseHandle
0x14001237d  test    eax, eax
0x14001237f  jz      short loc_1400123EC
0x140012381  mov     rcx, [rbx]; hEvent
0x140012384  call    cs:__imp_SetEvent
0x14001238a  test    eax, eax
0x14001238c  jz      short loc_1400123B2
0x14001238e  mov     rcx, [rbp+57h+var_20]
0x140012392  xor     rcx, rsp; StackCookie
0x140012395  call    __security_check_cookie
0x14001239a  lea     r11, [rsp+0C0h+var_10]
0x1400123a2  mov     rbx, [r11+28h]
0x1400123a6  mov     rsi, [r11+30h]
0x1400123aa  mov     rsp, r11
0x1400123ad  pop     r14
0x1400123af  pop     rdi
0x1400123b0  pop     rbp
0x1400123b1  retn
0x1400123b2  mov     rcx, [rbp+5Fh]; this
0x1400123b6  mov     edx, 0A01h; void *
0x1400123bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400123c1  mov     edx, 0A0Bh; void *
0x1400123c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400123cc  mov     r9d, eax; char *
0x1400123cf  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\service\\cexec\\c"...
0x1400123d6  mov     edx, 2Fh ; '/'; void *
0x1400123db  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400123e1  mov     edx, 0A0Bh; void *
0x1400123e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400123ec  mov     rcx, [rbp+5Fh]; this
0x1400123f0  mov     edx, 0A0Bh; void *
0x1400123f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
