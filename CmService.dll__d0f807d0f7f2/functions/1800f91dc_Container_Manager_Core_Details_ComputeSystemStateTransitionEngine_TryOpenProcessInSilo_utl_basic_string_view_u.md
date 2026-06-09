# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::TryOpenProcessInSilo(utl::basic_string_view<ushort,utl::char_traits<ushort>>,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x1800f91dc`
- end: `0x1800f9513`
- name: `?TryOpenProcessInSilo@ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@AEBAJV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `823`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f9078`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18002ccf0`
- `0x18002e2b4`
- `0x1800f91dc`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800f930e`
- `ntdll!NtQueryInformationProcess` at `0x1800f930e`
- `ntdll!RtlEqualUnicodeString` at `0x1800f9363`
- `ntdll!RtlEqualUnicodeString` at `0x1800f9363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f93a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f93a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f93c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f93c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9376`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f93b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f93fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f94ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9376`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f93b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f93fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f9449`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f94ad`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f92c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f9395`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f92c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f9395`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::TryOpenProcessInSilo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v5; // rcx
  int JobProcessList; // eax
  unsigned int v8; // ebx
  void *v9; // rcx
  WCHAR *v11; // rax
  void *v12; // rsi
  DWORD *i; // rdi
  char *v14; // rbx
  const char *v15; // r9
  NTSTATUS v16; // eax
  char *v17; // r14
  DWORD v18; // edi
  const char *v19; // r9
  unsigned int LastError; // edi
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING String2; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-B8h] BYREF
  void *v26[2]; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  char *v29; // [rsp+78h] [rbp-88h]
  char v30; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = *(void **)(a1 + 1440);
  *(__m128i *)v26 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v27 = -1;
  JobProcessList = Csl::QueryJobProcessList(v5);
  v8 = JobProcessList;
  if ( JobProcessList < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
      (const char *)(unsigned int)JobProcessList,
      ReturnLength);
    v9 = v26[0];
    if ( v26[0] != (void *)-1LL )
      goto LABEL_3;
    return v8;
  }
  v11 = *(WCHAR **)a2;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = v11;
  String2.Length = 2 * *(_WORD *)(a2 + 8);
  String2.MaximumLength = String2.Length;
  memset_0(&ProcessInformation, 0, 0x218u);
  v12 = v26[0];
  for ( i = (DWORD *)v26[0]; ; ++i )
  {
    if ( i == v26[1] )
    {
      if ( v12 != (void *)-1LL )
        operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
      return 2147943568LL;
    }
    v14 = (char *)OpenProcess(0x1000u, 0, *i);
    if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xAB5,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
                    v15);
      goto LABEL_22;
    }
    ProcessInformation = 34078720;
    v29 = &v30;
    v16 = NtQueryInformationProcess(v14, ProcessImageFileName, &ProcessInformation, 0x218u, 0);
    if ( v16 < 0 )
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0xAC2,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
                    (const char *)(unsigned int)v16,
                    ReturnLengtha);
      CloseHandle(v14);
LABEL_22:
      if ( v12 != (void *)-1LL )
        operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
      return LastError;
    }
    if ( (unsigned __int16)ProcessInformation - String2.Length >= 0 )
    {
      String1.Length = String2.Length;
      String1.MaximumLength = String2.Length;
      *(_DWORD *)(&String1.MaximumLength + 1) = 0;
      String1.Buffer = (PWSTR)&v29[2 * (((unsigned __int16)ProcessInformation - (unsigned __int64)String2.Length) >> 1)];
      if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
        break;
    }
    CloseHandle(v14);
  }
  v17 = (char *)OpenProcess(0x3008u, 0, *i);
  v18 = GetLastError();
  CloseHandle(v14);
  SetLastError(v18);
  hObject = v17;
  if ( (unsigned __int64)(v17 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a4,
      &hObject);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( v12 != (void *)-1LL )
      operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  v8 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0xAE8,
         (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\engine.cpp",
         v19);
  if ( v12 == (void *)-1LL )
    return v8;
  v9 = v12;
LABEL_3:
  operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
  return v8;
}

```

## disassembly

```asm
0x1800f91dc  mov     [rsp-8+arg_10], rbx
0x1800f91e1  push    rbp
0x1800f91e2  push    rsi
0x1800f91e3  push    rdi
0x1800f91e4  push    r14
0x1800f91e6  push    r15
0x1800f91e8  lea     rbp, [rsp-1A0h]
0x1800f91f0  sub     rsp, 2A0h
0x1800f91f7  mov     rax, cs:__security_cookie
0x1800f91fe  xor     rax, rsp
0x1800f9201  mov     [rbp+1C0h+var_30], rax
0x1800f9208  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800f9210  mov     rdi, rdx
0x1800f9213  mov     rcx, [rcx+5A0h]; hJob
0x1800f921a  lea     rdx, [rsp+2C0h+var_268]
0x1800f921f  movdqu  xmmword ptr [rsp+2C0h+var_268], xmm0
0x1800f9225  mov     r15, r9
0x1800f9228  mov     [rsp+2C0h+var_258], 0FFFFFFFFFFFFFFFFh
0x1800f9231  call    ?QueryJobProcessList@Csl@@YAJPEAXAEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; Csl::QueryJobProcessList(void *,utl::vector<ulong,utl::allocator<ulong>> &)
0x1800f9236  mov     ebx, eax
0x1800f9238  test    eax, eax
0x1800f923a  jns     short loc_1800F9275
0x1800f923c  mov     rcx, [rbp+1C8h]; this
0x1800f9243  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f924a  mov     r9d, eax; char *
0x1800f924d  mov     edx, 0A9Dh; void *
0x1800f9252  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9257  mov     rcx, [rsp+2C0h+var_268]; void *
0x1800f925c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f9260  jz      short loc_1800F926E
0x1800f9262  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f9269  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f926e  mov     eax, ebx
0x1800f9270  jmp     loc_1800F94EC
0x1800f9275  mov     rax, [rdi]
0x1800f9278  lea     rcx, [rsp+2C0h+ProcessInformation]; void *
0x1800f927d  xorps   xmm0, xmm0
0x1800f9280  mov     r14d, 218h
0x1800f9286  movups  xmmword ptr [rsp+2C0h+String2.Length], xmm0
0x1800f928b  mov     [rsp+2C0h+String2.Buffer], rax
0x1800f9290  mov     r8d, r14d; Size
0x1800f9293  movzx   eax, word ptr [rdi+8]
0x1800f9297  xor     edx, edx; Val
0x1800f9299  add     ax, ax
0x1800f929c  mov     [rsp+2C0h+String2.Length], ax
0x1800f92a1  mov     [rsp+2C0h+String2.MaximumLength], ax
0x1800f92a6  call    memset_0
0x1800f92ab  mov     rsi, [rsp+2C0h+var_268]
0x1800f92b0  mov     rdi, rsi
0x1800f92b3  cmp     rdi, [rsp+2C0h+var_268+8]
0x1800f92b8  jz      loc_1800F94D2
0x1800f92be  mov     r8d, [rdi]; dwProcessId
0x1800f92c1  xor     edx, edx; bInheritHandle
0x1800f92c3  mov     ecx, 1000h; dwDesiredAccess
0x1800f92c8  call    cs:__imp_OpenProcess
0x1800f92cf  nop     dword ptr [rax+rax+00h]
0x1800f92d4  mov     rbx, rax
0x1800f92d7  dec     rax
0x1800f92da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f92de  ja      loc_1800F9486
0x1800f92e4  lea     rax, [rbp+1C0h+var_240]
0x1800f92e8  mov     [rsp+2C0h+ProcessInformation], 2080000h
0x1800f92f0  mov     r9d, r14d; ProcessInformationLength
0x1800f92f3  mov     [rsp+2C0h+var_248], rax
0x1800f92f8  lea     r8, [rsp+2C0h+ProcessInformation]; ProcessInformation
0x1800f92fd  mov     qword ptr [rsp+2C0h+ReturnLength], 0; int
0x1800f9306  mov     edx, 1Bh; ProcessInformationClass
0x1800f930b  mov     rcx, rbx; ProcessHandle
0x1800f930e  call    cs:__imp_NtQueryInformationProcess
0x1800f9315  nop     dword ptr [rax+rax+00h]
0x1800f931a  test    eax, eax
0x1800f931c  js      loc_1800F9467
0x1800f9322  movzx   edx, [rsp+2C0h+String2.Length]
0x1800f9327  movzx   ecx, word ptr [rsp+2C0h+ProcessInformation]
0x1800f932c  cmp     ecx, edx
0x1800f932e  js      short loc_1800F9373
0x1800f9330  mov     rax, [rsp+2C0h+var_248]
0x1800f9335  sub     rcx, rdx
0x1800f9338  shr     rcx, 1
0x1800f933b  mov     r8b, 1; CaseInsensitive
0x1800f933e  mov     [rsp+2C0h+String1.Length], dx
0x1800f9343  mov     [rsp+2C0h+String1.MaximumLength], dx
0x1800f9348  lea     rdx, [rsp+2C0h+String2]; String2
0x1800f934d  mov     dword ptr [rsp+2C0h+String1+4], 0
0x1800f9355  lea     rcx, [rax+rcx*2]
0x1800f9359  mov     [rsp+2C0h+String1.Buffer], rcx
0x1800f935e  lea     rcx, [rsp+2C0h+String1]; String1
0x1800f9363  call    cs:__imp_RtlEqualUnicodeString
0x1800f936a  nop     dword ptr [rax+rax+00h]
0x1800f936f  test    al, al
0x1800f9371  jnz     short loc_1800F938B
0x1800f9373  mov     rcx, rbx; hObject
0x1800f9376  call    cs:__imp_CloseHandle
0x1800f937d  nop     dword ptr [rax+rax+00h]
0x1800f9382  add     rdi, 4
0x1800f9386  jmp     loc_1800F92B3
0x1800f938b  mov     r8d, [rdi]; dwProcessId
0x1800f938e  xor     edx, edx; bInheritHandle
0x1800f9390  mov     ecx, 3008h; dwDesiredAccess
0x1800f9395  call    cs:__imp_OpenProcess
0x1800f939c  nop     dword ptr [rax+rax+00h]
0x1800f93a1  mov     r14, rax
0x1800f93a4  call    cs:__imp_GetLastError
0x1800f93ab  nop     dword ptr [rax+rax+00h]
0x1800f93b0  mov     rcx, rbx; hObject
0x1800f93b3  mov     edi, eax
0x1800f93b5  call    cs:__imp_CloseHandle
0x1800f93bc  nop     dword ptr [rax+rax+00h]
0x1800f93c1  mov     ecx, edi; dwErrCode
0x1800f93c3  call    cs:__imp_SetLastError
0x1800f93ca  nop     dword ptr [rax+rax+00h]
0x1800f93cf  lea     rdx, [r14-1]
0x1800f93d3  mov     [rsp+2C0h+hObject], r14
0x1800f93d8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800f93dc  ja      short loc_1800F9422
0x1800f93de  lea     rdx, [rsp+2C0h+hObject]
0x1800f93e3  mov     rcx, r15
0x1800f93e6  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800f93eb  mov     rcx, [rsp+2C0h+hObject]; hObject
0x1800f93f0  lea     rax, [rcx-1]
0x1800f93f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f93f8  ja      short loc_1800F9406
0x1800f93fa  call    cs:__imp_CloseHandle
0x1800f9401  nop     dword ptr [rax+rax+00h]
0x1800f9406  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f940a  jz      short loc_1800F941B
0x1800f940c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f9413  mov     rcx, rsi; void *
0x1800f9416  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f941b  xor     eax, eax
0x1800f941d  jmp     loc_1800F94EC
0x1800f9422  mov     rcx, [rbp+1C8h]; this
0x1800f9429  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f9430  mov     edx, 0AE8h; void *
0x1800f9435  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f943a  lea     rcx, [r14-1]
0x1800f943e  mov     ebx, eax
0x1800f9440  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800f9444  ja      short loc_1800F9455
0x1800f9446  mov     rcx, r14; hObject
0x1800f9449  call    cs:__imp_CloseHandle
0x1800f9450  nop     dword ptr [rax+rax+00h]
0x1800f9455  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f9459  jz      loc_1800F926E
0x1800f945f  mov     rcx, rsi
0x1800f9462  jmp     loc_1800F9262
0x1800f9467  mov     rcx, [rbp+1C8h]; this
0x1800f946e  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f9475  mov     r9d, eax; char *
0x1800f9478  mov     edx, 0AC2h; void *
0x1800f947d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800f9482  mov     edi, eax
0x1800f9484  jmp     short loc_1800F94AA
0x1800f9486  mov     rcx, [rbp+1C8h]; this
0x1800f948d  lea     r8, aOnecoreBaseGen_40; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800f9494  mov     edx, 0AB5h; void *
0x1800f9499  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f949e  lea     rcx, [rbx-1]
0x1800f94a2  mov     edi, eax
0x1800f94a4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800f94a8  ja      short loc_1800F94B9
0x1800f94aa  mov     rcx, rbx; hObject
0x1800f94ad  call    cs:__imp_CloseHandle
0x1800f94b4  nop     dword ptr [rax+rax+00h]
0x1800f94b9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f94bd  jz      short loc_1800F94CE
0x1800f94bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f94c6  mov     rcx, rsi; void *
0x1800f94c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f94ce  mov     eax, edi
0x1800f94d0  jmp     short loc_1800F94EC
0x1800f94d2  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800f94d6  jz      short loc_1800F94E7
0x1800f94d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f94df  mov     rcx, rsi; void *
0x1800f94e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f94e7  mov     eax, 80070490h
0x1800f94ec  mov     rcx, [rbp+1C0h+var_30]
0x1800f94f3  xor     rcx, rsp; StackCookie
0x1800f94f6  call    __security_check_cookie
0x1800f94fb  mov     rbx, [rsp+2C0h+arg_10]
0x1800f9503  add     rsp, 2A0h
0x1800f950a  pop     r15
0x1800f950c  pop     r14
0x1800f950e  pop     rdi
0x1800f950f  pop     rsi
0x1800f9510  pop     rbp
0x1800f9511  retn
```
