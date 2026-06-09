# GetRpcClientProcessPathNameFromProcessId(ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180086394`
- end: `0x1800866cb`
- name: `?GetRpcClientProcessPathNameFromProcessId@@YAJKPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800866d4`

## callees

- `0x1800056a0`
- `0x180006e94`
- `0x180009094`
- `0x18000b760`
- `0x18003cd04`
- `0x180086394`
- `0x180086b10`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086483`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180086483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008647b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800865d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008661e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086686`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008647b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800865d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008661e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086686`
- `RPCRT4!RpcRevertToSelf` at `0x1800865dc`
- `RPCRT4!RpcRevertToSelf` at `0x180086624`
- `RPCRT4!RpcRevertToSelf` at `0x18008668c`
- `RPCRT4!RpcRevertToSelf` at `0x1800865dc`
- `RPCRT4!RpcRevertToSelf` at `0x180086624`
- `RPCRT4!RpcRevertToSelf` at `0x18008668c`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800863ce`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800863ce`
- `RPCRT4!RpcImpersonateClient` at `0x18008640c`
- `RPCRT4!RpcImpersonateClient` at `0x18008640c`
- `RPCRT4!RpcBindingFree` at `0x18008663b`
- `RPCRT4!RpcBindingFree` at `0x1800866a3`
- `RPCRT4!RpcBindingFree` at `0x18008663b`
- `RPCRT4!RpcBindingFree` at `0x1800866a3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008643b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008645d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008643b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008645d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008655c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18008655c`

## string_xrefs

- `0x1800864b0`: `onecoreuap\net\phone\phoneservice\service\lib\publicphonerpc.cpp`

## pseudocode

```c
__int64 __fastcall GetRpcClientProcessPathNameFromProcessId(DWORD dwProcessId, __int64 a2)
{
  _WORD *v3; // rcx
  RPC_STATUS v5; // eax
  BackTraceCollection *v6; // rcx
  signed int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  RPC_STATUS v10; // eax
  BackTraceCollection *v11; // rcx
  char *v12; // rbx
  char *v13; // rsi
  DWORD LastError; // edi
  signed int v15; // eax
  void *v16; // rcx
  BackTraceCollection *v17; // rcx
  LPWSTR v18; // rdi
  __int64 i; // rcx
  signed int v20; // eax
  BackTraceCollection *v21; // rcx
  __int64 v22; // r8
  __int64 v24; // r8
  int v25; // [rsp+20h] [rbp-50h]
  RPC_BINDING_HANDLE v26; // [rsp+30h] [rbp-40h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-38h] BYREF
  DWORD dwSize; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR lpExeName; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR v30; // [rsp+50h] [rbp-20h]
  __int16 v31; // [rsp+58h] [rbp-18h] BYREF
  __int64 v32; // [rsp+5Ah] [rbp-16h]
  int v33; // [rsp+62h] [rbp-Eh]
  __int16 v34; // [rsp+66h] [rbp-Ah]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v3 = *(_WORD **)a2;
  *(_QWORD *)(a2 + 8) = *(_QWORD *)a2;
  *v3 = 0;
  Binding = 0;
  v5 = RpcServerInqBindingHandle(&Binding);
  v7 = v5;
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  if ( v7 < 0 )
  {
    BackTraceCollection::Capture(v6, v7);
    v9 = 116;
LABEL_5:
    Log_HREvent_31((unsigned int)v7, 1, v8, v9);
LABEL_49:
    if ( !Binding )
      return (unsigned int)v7;
    v26 = Binding;
LABEL_51:
    RpcBindingFree(&v26);
    return (unsigned int)v7;
  }
  v10 = RpcImpersonateClient(Binding);
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 < 0 )
  {
    BackTraceCollection::Capture(v11, v7);
    v9 = 118;
    goto LABEL_5;
  }
  v12 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
  if ( ((unsigned __int64)(v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v13 = (char *)OpenProcess(0x400u, 0, dwProcessId);
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v12);
      SetLastError(LastError);
    }
    if ( ((unsigned __int64)(v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v15 = GetLastError();
      v7 = v15;
      if ( v15 > 0 )
        v7 = (unsigned __int16)v15 | 0x80070000;
      if ( v7 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\net\\phone\\phoneservice\\service\\lib\\publicphonerpc.cpp",
          (const char *)(unsigned int)v7,
          v25);
      if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_48;
      v16 = v13;
LABEL_47:
      CloseHandle(v16);
LABEL_48:
      RpcRevertToSelf();
      goto LABEL_49;
    }
    v12 = v13;
  }
  v32 = 0;
  v34 = 0;
  v33 = 0;
  lpExeName = (LPWSTR)&v31;
  v30 = (LPWSTR)&v31;
  v31 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(
                           &lpExeName,
                           260) )
  {
    v7 = -2147024882;
    BackTraceCollection::Capture(v17, -2147024882);
    Log_HREvent_31(2147942414LL, 0, v24, 132);
LABEL_43:
    if ( lpExeName != (LPWSTR)&v31 )
      operator delete(lpExeName);
    if ( (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_48;
    v16 = v12;
    goto LABEL_47;
  }
  v18 = lpExeName;
  for ( i = 260; i; --i )
    *v18++ = 0;
  v30 = lpExeName + 260;
  lpExeName[260] = 0;
  dwSize = v30 - lpExeName;
  if ( !QueryFullProcessImageNameW(v12, 0, lpExeName, &dwSize) )
  {
    v20 = GetLastError();
    v7 = v20;
    if ( v20 > 0 )
      v7 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_43;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a2,
                           lpExeName) )
  {
    v7 = -2147024882;
    BackTraceCollection::Capture(v21, -2147024882);
    Log_HREvent_31(2147942414LL, 0, v22, 139);
    if ( lpExeName != (LPWSTR)&v31 )
      operator delete(lpExeName);
    if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v12);
    RpcRevertToSelf();
    if ( !Binding )
      return (unsigned int)v7;
    v26 = Binding;
    goto LABEL_51;
  }
  if ( lpExeName != (LPWSTR)&v31 )
    operator delete(lpExeName);
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v12);
  RpcRevertToSelf();
  if ( Binding )
  {
    v26 = Binding;
    RpcBindingFree(&v26);
  }
  return 0;
}

```

## disassembly

```asm
0x180086394  mov     [rsp-28h+arg_10], rbx
0x180086399  push    rbp
0x18008639a  push    rsi
0x18008639b  push    rdi
0x18008639c  push    r12
0x18008639e  push    r14
0x1800863a0  mov     rbp, rsp
0x1800863a3  sub     rsp, 70h
0x1800863a7  mov     rax, cs:__security_cookie
0x1800863ae  xor     rax, rsp
0x1800863b1  mov     [rbp+var_8], rax
0x1800863b5  mov     esi, ecx
0x1800863b7  xor     eax, eax
0x1800863b9  mov     rcx, [rdx]
0x1800863bc  mov     r14, rdx
0x1800863bf  mov     [rdx+8], rcx
0x1800863c3  mov     [rcx], ax
0x1800863c6  lea     rcx, [rbp+Binding]; Binding
0x1800863ca  mov     [rbp+Binding], rax
0x1800863ce  call    cs:__imp_RpcServerInqBindingHandle
0x1800863d4  mov     edi, eax
0x1800863d6  mov     r12d, 80070000h
0x1800863dc  test    eax, eax
0x1800863de  jle     short loc_1800863E6
0x1800863e0  movzx   edi, ax
0x1800863e3  or      edi, r12d
0x1800863e6  test    edi, edi
0x1800863e8  jns     short loc_180086408
0x1800863ea  mov     edx, edi; int
0x1800863ec  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800863f1  mov     r9d, 74h ; 't'
0x1800863f7  mov     edx, 1
0x1800863fc  mov     ecx, edi
0x1800863fe  call    Log_HREvent_31
0x180086403  jmp     loc_180086692
0x180086408  mov     rcx, [rbp+Binding]; BindingHandle
0x18008640c  call    cs:__imp_RpcImpersonateClient
0x180086412  mov     edi, eax
0x180086414  test    eax, eax
0x180086416  jle     short loc_18008641E
0x180086418  movzx   edi, ax
0x18008641b  or      edi, r12d
0x18008641e  test    edi, edi
0x180086420  jns     short loc_180086431
0x180086422  mov     edx, edi; int
0x180086424  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086429  mov     r9d, 76h ; 'v'
0x18008642f  jmp     short loc_1800863F7
0x180086431  mov     r8d, esi; dwProcessId
0x180086434  xor     edx, edx; bInheritHandle
0x180086436  mov     ecx, 1000h; dwDesiredAccess
0x18008643b  call    cs:__imp_OpenProcess
0x180086441  mov     rbx, rax
0x180086444  inc     rax
0x180086447  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008644d  jnz     loc_1800864DD
0x180086453  mov     r8d, esi; dwProcessId
0x180086456  xor     edx, edx; bInheritHandle
0x180086458  mov     ecx, 400h; dwDesiredAccess
0x18008645d  call    cs:__imp_OpenProcess
0x180086463  lea     rcx, [rbx-1]
0x180086467  mov     rsi, rax
0x18008646a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18008646e  ja      short loc_180086489
0x180086470  call    cs:__imp_GetLastError
0x180086476  mov     rcx, rbx; hObject
0x180086479  mov     edi, eax
0x18008647b  call    cs:__imp_CloseHandle
0x180086481  mov     ecx, edi; dwErrCode
0x180086483  call    cs:__imp_SetLastError
0x180086489  lea     rcx, [rsi+1]
0x18008648d  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180086494  jnz     short loc_1800864DA
0x180086496  call    cs:__imp_GetLastError
0x18008649c  mov     edi, eax
0x18008649e  test    eax, eax
0x1800864a0  jle     short loc_1800864A8
0x1800864a2  movzx   edi, ax
0x1800864a5  or      edi, r12d
0x1800864a8  test    edi, edi
0x1800864aa  jns     short loc_1800864C4
0x1800864ac  mov     rcx, [rbp+28h]; this
0x1800864b0  lea     r8, aOnecoreuapNetP_14; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800864b7  mov     r9d, edi; char *
0x1800864ba  mov     edx, 80h; void *
0x1800864bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800864c4  lea     rax, [rsi-1]
0x1800864c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800864cc  ja      loc_18008668C
0x1800864d2  mov     rcx, rsi
0x1800864d5  jmp     loc_180086686
0x1800864da  mov     rbx, rsi
0x1800864dd  xor     eax, eax
0x1800864df  mov     [rbp+var_16], 0
0x1800864e7  mov     [rbp+var_A], ax
0x1800864eb  lea     rcx, [rbp+lpExeName]
0x1800864ef  lea     rax, [rbp+var_18]
0x1800864f3  mov     [rbp+var_E], 0
0x1800864fa  mov     [rbp+lpExeName], rax
0x1800864fe  mov     esi, 104h
0x180086503  lea     rax, [rbp+var_18]
0x180086507  mov     edx, esi
0x180086509  mov     [rbp+var_20], rax
0x18008650d  xor     eax, eax
0x18008650f  mov     [rbp+var_18], ax
0x180086513  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x180086518  test    al, al
0x18008651a  jz      loc_180086645
0x180086520  mov     rdi, [rbp+lpExeName]
0x180086524  lea     r9, [rbp+dwSize]; lpdwSize
0x180086528  xor     eax, eax
0x18008652a  mov     ecx, esi
0x18008652c  movzx   eax, ax
0x18008652f  xor     edx, edx; dwFlags
0x180086531  rep stosw
0x180086534  mov     rcx, [rbp+lpExeName]
0x180086538  xor     eax, eax
0x18008653a  add     rcx, 208h
0x180086541  mov     [rbp+var_20], rcx
0x180086545  mov     [rcx], ax
0x180086548  mov     rcx, rbx; hProcess
0x18008654b  mov     rax, [rbp+var_20]
0x18008654f  mov     r8, [rbp+lpExeName]; lpExeName
0x180086553  sub     rax, r8
0x180086556  sar     rax, 1
0x180086559  mov     [rbp+dwSize], eax
0x18008655c  call    cs:__imp_QueryFullProcessImageNameW
0x180086562  test    eax, eax
0x180086564  jnz     short loc_180086581
0x180086566  call    cs:__imp_GetLastError
0x18008656c  mov     edi, eax
0x18008656e  test    eax, eax
0x180086570  jle     loc_180086660
0x180086576  movzx   edi, ax
0x180086579  or      edi, r12d
0x18008657c  jmp     loc_180086660
0x180086581  mov     r8d, [rbp+dwSize]
0x180086585  mov     rcx, r14
0x180086588  mov     rdx, [rbp+lpExeName]
0x18008658c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180086591  test    al, al
0x180086593  jnz     short loc_1800865F8
0x180086595  mov     edi, 8007000Eh
0x18008659a  mov     edx, edi; int
0x18008659c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800865a1  xor     edx, edx
0x1800865a3  mov     r9d, 8Bh
0x1800865a9  mov     ecx, edi
0x1800865ab  call    Log_HREvent_31
0x1800865b0  mov     rcx, [rbp+lpExeName]; Block
0x1800865b4  lea     rax, [rbp+var_18]
0x1800865b8  cmp     rcx, rax
0x1800865bb  jz      short loc_1800865C9
0x1800865bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800865c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800865c9  lea     rax, [rbx-1]
0x1800865cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800865d1  ja      short loc_1800865DC
0x1800865d3  mov     rcx, rbx; hObject
0x1800865d6  call    cs:__imp_CloseHandle
0x1800865dc  call    cs:__imp_RpcRevertToSelf
0x1800865e2  mov     rax, [rbp+Binding]
0x1800865e6  test    rax, rax
0x1800865e9  jz      loc_1800866A9
0x1800865ef  mov     [rbp+var_40], rax
0x1800865f3  jmp     loc_18008669F
0x1800865f8  mov     rcx, [rbp+lpExeName]; Block
0x1800865fc  lea     rax, [rbp+var_18]
0x180086600  cmp     rcx, rax
0x180086603  jz      short loc_180086611
0x180086605  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18008660c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086611  lea     rax, [rbx-1]
0x180086615  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180086619  ja      short loc_180086624
0x18008661b  mov     rcx, rbx; hObject
0x18008661e  call    cs:__imp_CloseHandle
0x180086624  call    cs:__imp_RpcRevertToSelf
0x18008662a  mov     rax, [rbp+Binding]
0x18008662e  test    rax, rax
0x180086631  jz      short loc_180086641
0x180086633  lea     rcx, [rbp+var_40]; Binding
0x180086637  mov     [rbp+var_40], rax
0x18008663b  call    cs:__imp_RpcBindingFree
0x180086641  xor     eax, eax
0x180086643  jmp     short loc_1800866AB
0x180086645  mov     edi, 8007000Eh
0x18008664a  mov     edx, edi; int
0x18008664c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180086651  xor     edx, edx
0x180086653  mov     r9d, 84h
0x180086659  mov     ecx, edi
0x18008665b  call    Log_HREvent_31
0x180086660  mov     rcx, [rbp+lpExeName]; Block
0x180086664  lea     rax, [rbp+var_18]
0x180086668  cmp     rcx, rax
0x18008666b  jz      short loc_180086679
0x18008666d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180086674  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086679  lea     rax, [rbx-1]
0x18008667d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180086681  ja      short loc_18008668C
0x180086683  mov     rcx, rbx; hObject
0x180086686  call    cs:__imp_CloseHandle
0x18008668c  call    cs:__imp_RpcRevertToSelf
0x180086692  mov     rcx, [rbp+Binding]
0x180086696  test    rcx, rcx
0x180086699  jz      short loc_1800866A9
0x18008669b  mov     [rbp+var_40], rcx
0x18008669f  lea     rcx, [rbp+var_40]; Binding
0x1800866a3  call    cs:__imp_RpcBindingFree
0x1800866a9  mov     eax, edi
0x1800866ab  mov     rcx, [rbp+var_8]
0x1800866af  xor     rcx, rsp; StackCookie
0x1800866b2  call    __security_check_cookie
0x1800866b7  mov     rbx, [rsp+70h+arg_10]
0x1800866bf  add     rsp, 70h
0x1800866c3  pop     r14
0x1800866c5  pop     r12
0x1800866c7  pop     rdi
0x1800866c8  pop     rsi
0x1800866c9  pop     rbp
0x1800866ca  retn
```
