# CSmsRpcUtils::CreateWNFStateName(_WNF_STATE_NAME *,ushort const *,ulong,_WNF_STATE_NAME_LIFETIME)

- ea: `0x1800267f8`
- end: `0x180026a3a`
- name: `?CreateWNFStateName@CSmsRpcUtils@@SAJPEAU_WNF_STATE_NAME@@PEBGKW4_WNF_STATE_NAME_LIFETIME@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016e74`
- `0x18003547c`
- `0x180035660`
- `0x18003eb68`

## callees

- `0x180003a60`
- `0x180004998`
- `0x1800069f0`
- `0x1800093d4`
- `0x1800267f8`
- `0x180026bd0`
- `0x1800276a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800268cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800268cb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002696e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026a26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002696e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180026a26`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800268e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026927`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026a1c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026915`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180026915`
- `ntdll!NtCreateWnfStateName` at `0x180026a0a`
- `ntdll!NtCreateWnfStateName` at `0x180026a0a`
- `ntdll!RtlNtStatusToDosError` at `0x180026a2e`
- `ntdll!RtlNtStatusToDosError` at `0x180026a2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026998`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026998`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsRpcUtils::CreateWNFStateName(__int64 a1, void *a2)
{
  __m128i si128; // xmm1
  __int128 *p_Src; // r9
  HANDLE CurrentProcess; // rax
  void *v7; // rbx
  unsigned int v8; // esi
  void *v10; // rdi
  signed int LastError; // eax
  NTSTATUS WnfStateName; // esi
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int128 Src; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v16; // [rsp+60h] [rbp-A0h]
  _OWORD v17[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR StringSecurityDescriptor[1024]; // [rsp+90h] [rbp-70h] BYREF

  SecurityDescriptor = 0;
  memset_0(StringSecurityDescriptor, 0, sizeof(StringSecurityDescriptor));
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v16 = si128;
  LOWORD(Src) = 0;
  if ( a2 )
  {
    std::wstring::append(&Src, a2);
  }
  else
  {
    v17[0] = 0;
    v17[1] = si128;
    LOWORD(v17[0]) = 0;
    CSmsRpcUtils::GetUserAndAppSid((void **)&Src, (void **)v17);
    std::wstring::~wstring((char **)v17);
  }
  p_Src = &Src;
  if ( v16.m128i_i64[1] > 7uLL )
    p_Src = (__int128 *)Src;
  StringCchPrintfW(
    StringSecurityDescriptor,
    0x400u,
    L"D:(A;;GRGX;;;WD)(A;;GRGWGX;;;OW)(A;;GRGWGX;;;SY)(A;;GRGWGX;;;LS)(A;;GRGWGX;;;S-1-5-80-2950457502-2299174248-33282454"
     "79-1326271200-3113355612)(A;;GRGX;;;S-1-15-2-1)(A;;GRGX;;;%s)",
    p_Src);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
    goto LABEL_10;
  v7 = TokenHandle;
  TokenHandle = 0;
  if ( !DuplicateTokenEx(v7, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &TokenHandle) )
  {
LABEL_8:
    if ( v7 )
      CloseHandle(v7);
LABEL_10:
    v8 = -2147467259;
    goto LABEL_11;
  }
  v10 = TokenHandle;
  TokenHandle = 0;
  if ( !SetThreadToken(0, v10) )
  {
    if ( v10 )
      CloseHandle(v10);
    goto LABEL_8;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    WnfStateName = NtCreateWnfStateName(a1, 3, 0);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    SetThreadToken(0, 0);
    LastError = RtlNtStatusToDosError(WnfStateName);
  }
  else
  {
    LastError = GetLastError();
  }
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 )
    CloseHandle(v10);
  if ( v7 )
    CloseHandle(v7);
LABEL_11:
  std::wstring::~wstring((char **)&Src);
  return v8;
}

```

## disassembly

```asm
0x1800267f8  push    rbp
0x1800267fa  push    rbx
0x1800267fb  push    rsi
0x1800267fc  push    rdi
0x1800267fd  push    r14
0x1800267ff  lea     rbp, [rsp-7A0h]
0x180026807  sub     rsp, 8A0h
0x18002680e  mov     rax, cs:__security_cookie
0x180026815  xor     rax, rsp
0x180026818  mov     [rbp+7C0h+var_30], rax
0x18002681f  mov     esi, r8d
0x180026822  mov     rbx, rdx
0x180026825  mov     r14, rcx
0x180026828  mov     [rsp+8C0h+SecurityDescriptor], 0
0x180026831  xor     edx, edx; Val
0x180026833  mov     r8d, 800h; Size
0x180026839  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; void *
0x18002683d  call    memset_0
0x180026842  xorps   xmm0, xmm0
0x180026845  movups  [rsp+8C0h+Src], xmm0
0x18002684a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026852  movdqu  [rsp+8C0h+var_860], xmm1
0x180026858  xor     eax, eax
0x18002685a  mov     word ptr [rsp+8C0h+Src], ax
0x18002685f  test    rbx, rbx
0x180026862  jnz     short loc_18002688F
0x180026864  movups  [rsp+8C0h+var_850], xmm0
0x180026869  movdqu  [rbp+7C0h+var_840], xmm1
0x18002686e  mov     word ptr [rsp+8C0h+var_850], ax
0x180026873  lea     rdx, [rsp+8C0h+var_850]
0x180026878  lea     rcx, [rsp+8C0h+Src]
0x18002687d  call    ?GetUserAndAppSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; CSmsRpcUtils::GetUserAndAppSid(std::wstring &,std::wstring &)
0x180026882  nop
0x180026883  lea     rcx, [rsp+8C0h+var_850]; void *
0x180026888  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002688d  jmp     short loc_18002689C
0x18002688f  mov     rdx, rbx; void *
0x180026892  lea     rcx, [rsp+8C0h+Src]; Src
0x180026897  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002689c  lea     r9, [rsp+8C0h+Src]
0x1800268a1  cmp     qword ptr [rsp+8C0h+var_860+8], 7
0x1800268a7  cmova   r9, qword ptr [rsp+8C0h+Src]
0x1800268ad  lea     r8, aDAGrgxWdAGrgwg; "D:(A;;GRGX;;;WD)(A;;GRGWGX;;;OW)(A;;GRG"...
0x1800268b4  mov     edx, 400h; unsigned __int64
0x1800268b9  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800268bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800268c2  mov     [rsp+8C0h+TokenHandle], 0
0x1800268cb  call    cs:__imp_GetCurrentProcess
0x1800268d1  mov     rcx, rax; ProcessHandle
0x1800268d4  lea     r8, [rsp+8C0h+TokenHandle]; TokenHandle
0x1800268d9  mov     edi, 2000000h
0x1800268de  mov     edx, edi; DesiredAccess
0x1800268e0  call    cs:__imp_OpenProcessToken
0x1800268e6  test    eax, eax
0x1800268e8  jz      short loc_18002692D
0x1800268ea  mov     rbx, [rsp+8C0h+TokenHandle]
0x1800268ef  mov     [rsp+8C0h+TokenHandle], 0
0x1800268f8  lea     rax, [rsp+8C0h+TokenHandle]
0x1800268fd  mov     [rsp+8C0h+phNewToken], rax; phNewToken
0x180026902  mov     r9d, 2; ImpersonationLevel
0x180026908  mov     [rsp+8C0h+TokenType], r9d; TokenType
0x18002690d  xor     r8d, r8d; lpTokenAttributes
0x180026910  mov     edx, edi; dwDesiredAccess
0x180026912  mov     rcx, rbx; hExistingToken
0x180026915  call    cs:__imp_DuplicateTokenEx
0x18002691b  test    eax, eax
0x18002691d  jnz     short loc_18002695B
0x18002691f  test    rbx, rbx
0x180026922  jz      short loc_18002692D
0x180026924  mov     rcx, rbx; hObject
0x180026927  call    cs:__imp_CloseHandle
0x18002692d  mov     esi, 80004005h
0x180026932  lea     rcx, [rsp+8C0h+Src]; void *
0x180026937  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002693c  mov     eax, esi
0x18002693e  mov     rcx, [rbp+7C0h+var_30]
0x180026945  xor     rcx, rsp; StackCookie
0x180026948  call    __security_check_cookie
0x18002694d  add     rsp, 8A0h
0x180026954  pop     r14
0x180026956  pop     rdi
0x180026957  pop     rsi
0x180026958  pop     rbx
0x180026959  pop     rbp
0x18002695a  retn
0x18002695b  mov     rdi, [rsp+8C0h+TokenHandle]
0x180026960  mov     [rsp+8C0h+TokenHandle], 0
0x180026969  mov     rdx, rdi; Token
0x18002696c  xor     ecx, ecx; Thread
0x18002696e  call    cs:__imp_SetThreadToken
0x180026974  test    eax, eax
0x180026976  jnz     short loc_180026988
0x180026978  test    rdi, rdi
0x18002697b  jz      short loc_18002691F
0x18002697d  mov     rcx, rdi; hObject
0x180026980  call    cs:__imp_CloseHandle
0x180026986  jmp     short loc_18002691F
0x180026988  xor     r9d, r9d; SecurityDescriptorSize
0x18002698b  lea     r8, [rsp+8C0h+SecurityDescriptor]; SecurityDescriptor
0x180026990  lea     edx, [r9+1]; StringSDRevision
0x180026994  lea     rcx, [rbp+7C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180026998  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002699e  test    eax, eax
0x1800269a0  jnz     short loc_1800269DC
0x1800269a2  call    cs:__imp_GetLastError
0x1800269a8  test    eax, eax
0x1800269aa  mov     esi, eax
0x1800269ac  jle     short loc_1800269B7
0x1800269ae  movzx   esi, ax
0x1800269b1  or      esi, 80070000h
0x1800269b7  test    rdi, rdi
0x1800269ba  jz      short loc_1800269C5
0x1800269bc  mov     rcx, rdi; hObject
0x1800269bf  call    cs:__imp_CloseHandle
0x1800269c5  test    rbx, rbx
0x1800269c8  jz      loc_180026932
0x1800269ce  mov     rcx, rbx; hObject
0x1800269d1  call    cs:__imp_CloseHandle
0x1800269d7  jmp     loc_180026932
0x1800269dc  mov     rax, [rsp+8C0h+SecurityDescriptor]
0x1800269e1  mov     edx, 80h
0x1800269e6  test    esi, esi
0x1800269e8  cmovnz  edx, esi
0x1800269eb  mov     [rsp+8C0h+var_890], rax
0x1800269f0  mov     dword ptr [rsp+8C0h+phNewToken], edx
0x1800269f4  mov     qword ptr [rsp+8C0h+TokenType], 0
0x1800269fd  xor     r9d, r9d
0x180026a00  xor     r8d, r8d
0x180026a03  lea     edx, [r9+3]
0x180026a07  mov     rcx, r14
0x180026a0a  call    cs:__imp_NtCreateWnfStateName
0x180026a10  mov     esi, eax
0x180026a12  mov     rcx, [rsp+8C0h+SecurityDescriptor]; hMem
0x180026a17  test    rcx, rcx
0x180026a1a  jz      short loc_180026A22
0x180026a1c  call    cs:__imp_LocalFree
0x180026a22  xor     edx, edx; Token
0x180026a24  xor     ecx, ecx; Thread
0x180026a26  call    cs:__imp_SetThreadToken
0x180026a2c  mov     ecx, esi; Status
0x180026a2e  call    cs:__imp_RtlNtStatusToDosError
0x180026a34  jmp     loc_1800269A8
```
