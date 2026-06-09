# CheckLimitedAccessFeatureForClientProcess

- ea: `0x180033104`
- end: `0x18003332c`
- name: `CheckLimitedAccessFeatureForClientProcess`
- size: `552`
- prototype: `bool __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180032e60`
- `0x180053cf0`
- `0x180058110`

## callees

- `0x18000302e`
- `0x180003458`
- `0x1800034ac`
- `0x180011e18`
- `0x180031c64`
- `0x180032290`
- `0x180033104`
- `0x180033334`
- `0x18003537c`
- `0x1800356e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332f3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332f3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003316f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003316f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800332af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800332af`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800331c3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800331c3`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003319a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18003319a`

## string_xrefs

- `0x18003312c`: `com.microsoft.windows.usersession.control`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CheckLimitedAccessFeatureForClientProcess(__int64 a1, unsigned int a2)
{
  struct winrt::impl::shared_hstring_header *v2; // rax
  volatile signed __int32 *v3; // rdi
  unsigned int v4; // eax
  char *v5; // rbx
  void *AccessStatusForProcess; // r14
  int v7; // eax
  HANDLE ProcessHeap; // rax
  int v10; // eax
  HANDLE v11; // rax
  volatile signed __int32 *v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF
  unsigned int Pid; // [rsp+88h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp+20h] BYREF

  v2 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x29, a2);
  v3 = (volatile signed __int32 *)v2;
  lpMem = v2;
  if ( v2 == (struct winrt::impl::shared_hstring_header *)-28LL )
  {
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    *(_OWORD *)((char *)v2 + 28) = *(_OWORD *)L"com.microsoft.windows.usersession.control";
    *(_OWORD *)((char *)v2 + 44) = *(_OWORD *)L"osoft.windows.usersession.control";
    *(_OWORD *)((char *)v2 + 60) = *(_OWORD *)L"ndows.usersession.control";
    *(_OWORD *)((char *)v2 + 76) = *(_OWORD *)L"ersession.control";
    *(_OWORD *)((char *)v2 + 92) = *(_OWORD *)L"n.control";
    *((_WORD *)v2 + 54) = aComMicrosoftWi[40];
  }
  Pid = 0;
  v4 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( !v4 && Pid )
  {
    v5 = (char *)OpenProcess(0x1000u, 0, Pid);
    hObject = v5;
    winrt::get_activation_factory<winrt::Windows::ApplicationModel::LimitedAccessFeatures,winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal2>(&v13);
    v12 = v3;
    AccessStatusForProcess = (void *)(int)winrt::impl::consume_Windows_ApplicationModel_InternalApi_ILimitedAccessFeaturesInternal2<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal2>::GetAccessStatusForProcess(
                                            &v13,
                                            &v12,
                                            v5);
    if ( v13 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
    LOBYTE(v13) = (_DWORD)AccessStatusForProcess == 1;
    lpMem = AccessStatusForProcess;
    LODWORD(hObject) = 0;
    IsoEnvBrokerTelemetry::LafCheckResult<bool &,int,unsigned __int64>(&v13, &hObject, &lpMem);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    if ( !v3 )
      return (_DWORD)AccessStatusForProcess == 1;
    v7 = _InterlockedDecrement(v3 + 6);
    if ( !v7 )
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
      return (_DWORD)AccessStatusForProcess == 1;
    }
    if ( v7 >= 0 )
      return (_DWORD)AccessStatusForProcess == 1;
LABEL_17:
    abort();
  }
  Log(2u, L"I_RpcBindingInqLocalClientPID failed status=%#x: pid %d", v4, Pid, v3);
  if ( v3 )
  {
    v10 = _InterlockedDecrement(v3 + 6);
    if ( v10 )
    {
      if ( v10 < 0 )
        goto LABEL_17;
    }
    else
    {
      v11 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v11, 0, (LPVOID)v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180033104  push    rbx
0x180033106  push    rsi
0x180033107  push    rdi
0x180033108  push    r14
0x18003310a  sub     rsp, 58h
0x18003310e  mov     ecx, 29h ; ')'; this
0x180033113  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180033118  mov     rdi, rax
0x18003311b  mov     [rsp+78h+lpMem], rax
0x180033123  lea     rcx, [rax+1Ch]
0x180033127  test    rcx, rcx
0x18003312a  jz      short loc_18003316F
0x18003312c  movaps  xmm0, xmmword ptr cs:aComMicrosoftWi; "com.microsoft.windows.usersession.contr"...
0x180033133  movups  xmmword ptr [rcx], xmm0
0x180033136  movaps  xmm1, xmmword ptr cs:aComMicrosoftWi+10h; "osoft.windows.usersession.control"
0x18003313d  movups  xmmword ptr [rcx+10h], xmm1
0x180033141  movaps  xmm0, xmmword ptr cs:aComMicrosoftWi+20h; "ndows.usersession.control"
0x180033148  movups  xmmword ptr [rcx+20h], xmm0
0x18003314c  movaps  xmm1, xmmword ptr cs:aComMicrosoftWi+30h; "ersession.control"
0x180033153  movups  xmmword ptr [rcx+30h], xmm1
0x180033157  movaps  xmm0, xmmword ptr cs:aComMicrosoftWi+40h; "n.control"
0x18003315e  movups  xmmword ptr [rcx+40h], xmm0
0x180033162  movzx   eax, word ptr cs:aComMicrosoftWi+50h; "l"
0x180033169  mov     [rcx+50h], ax
0x18003316d  jmp     short loc_180033180
0x18003316f  call    cs:__imp__o__errno
0x180033175  mov     dword ptr [rax], 16h
0x18003317b  call    _invalid_parameter_noinfo
0x180033180  mov     [rsp+78h+var_58], rdi
0x180033185  mov     [rsp+78h+Pid], 0
0x180033190  lea     rdx, [rsp+78h+Pid]; Pid
0x180033198  xor     ecx, ecx; Binding
0x18003319a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800331a0  mov     r9d, [rsp+78h+Pid]
0x1800331a8  test    eax, eax
0x1800331aa  jnz     loc_1800332FA
0x1800331b0  test    r9d, r9d
0x1800331b3  jz      loc_1800332FA
0x1800331b9  mov     r8d, r9d; dwProcessId
0x1800331bc  xor     edx, edx; bInheritHandle
0x1800331be  mov     ecx, 1000h; dwDesiredAccess
0x1800331c3  call    cs:__imp_OpenProcess
0x1800331c9  mov     rbx, rax
0x1800331cc  mov     [rsp+78h+hObject], rax
0x1800331d4  lea     rcx, [rsp+78h+arg_0]
0x1800331dc  call    ??$get_activation_factory@ULimitedAccessFeatures@ApplicationModel@Windows@winrt@@UILimitedAccessFeaturesInternal2@InternalApi@234@@winrt@@YA?A_PXZ
0x1800331e1  nop
0x1800331e2  mov     [rsp+78h+var_48], rdi
0x1800331e7  mov     r8, rbx
0x1800331ea  lea     rdx, [rsp+78h+var_48]
0x1800331ef  lea     rcx, [rsp+78h+arg_0]
0x1800331f7  call    ?GetAccessStatusForProcess@?$consume_Windows_ApplicationModel_InternalApi_ILimitedAccessFeaturesInternal2@UILimitedAccessFeaturesInternal2@InternalApi@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_K@Z; winrt::impl::consume_Windows_ApplicationModel_InternalApi_ILimitedAccessFeaturesInternal2<winrt::Windows::ApplicationModel::InternalApi::ILimitedAccessFeaturesInternal2>::GetAccessStatusForProcess(winrt::param::hstring const &,unsigned __int64)
0x1800331fc  movsxd  r14, eax
0x1800331ff  cmp     [rsp+78h+arg_0], 0
0x180033208  jz      short loc_180033218
0x18003320a  lea     rcx, [rsp+78h+arg_0]
0x180033212  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180033217  nop
0x180033218  cmp     r14d, 1
0x18003321c  setz    sil
0x180033220  mov     byte ptr [rsp+78h+arg_0], sil
0x180033228  mov     [rsp+78h+lpMem], r14
0x180033230  mov     dword ptr [rsp+78h+hObject], 0
0x18003323b  lea     r8, [rsp+78h+lpMem]
0x180033243  lea     rdx, [rsp+78h+hObject]
0x18003324b  lea     rcx, [rsp+78h+arg_0]
0x180033253  call    ??$LafCheckResult@AEA_NH_K@IsoEnvBrokerTelemetry@@SAXAEA_N$$QEAH$$QEA_K@Z; IsoEnvBrokerTelemetry::LafCheckResult<bool &,int,unsigned __int64>(bool &,int &&,unsigned __int64 &&)
0x180033258  nop
0x180033259  lea     rax, [rbx-1]
0x18003325d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033261  ja      short loc_18003326D
0x180033263  mov     rcx, rbx; hObject
0x180033266  call    cs:__imp_CloseHandle
0x18003326c  nop
0x18003326d  test    rdi, rdi
0x180033270  jz      short loc_180033298
0x180033272  or      eax, 0FFFFFFFFh
0x180033275  lock xadd [rdi+18h], eax
0x18003327a  sub     eax, 1
0x18003327d  jnz     short loc_180033294
0x18003327f  nop
0x180033280  call    WINRT_IMPL_GetProcessHeap
0x180033285  mov     rcx, rax; hHeap
0x180033288  mov     r8, rdi; lpMem
0x18003328b  xor     edx, edx; dwFlags
0x18003328d  call    WINRT_IMPL_HeapFree
0x180033292  jmp     short loc_180033298
0x180033294  test    eax, eax
0x180033296  js      short loc_1800332F3
0x180033298  mov     al, sil
0x18003329b  jmp     short loc_1800332E5
0x18003329d  mov     rcx, [rsp+78h+hObject]; hObject
0x1800332a5  lea     rax, [rcx-1]
0x1800332a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800332ad  ja      short loc_1800332B6
0x1800332af  call    cs:__imp_CloseHandle
0x1800332b5  nop
0x1800332b6  mov     rbx, [rsp+78h+lpMem]
0x1800332be  test    rbx, rbx
0x1800332c1  jz      short loc_1800332E3
0x1800332c3  or      eax, 0FFFFFFFFh
0x1800332c6  lock xadd [rbx+18h], eax
0x1800332cb  sub     eax, 1
0x1800332ce  jnz     short loc_1800332EF
0x1800332d0  nop
0x1800332d1  call    WINRT_IMPL_GetProcessHeap
0x1800332d6  mov     r8, rbx; lpMem
0x1800332d9  xor     edx, edx; dwFlags
0x1800332db  mov     rcx, rax; hHeap
0x1800332de  call    WINRT_IMPL_HeapFree
0x1800332e3  xor     al, al
0x1800332e5  add     rsp, 58h
0x1800332e9  pop     r14
0x1800332eb  pop     rdi
0x1800332ec  pop     rsi
0x1800332ed  pop     rbx
0x1800332ee  retn
0x1800332ef  test    eax, eax
0x1800332f1  jns     short loc_1800332E3
0x1800332f3  call    cs:__imp_abort
0x1800332fa  mov     r8d, eax
0x1800332fd  lea     rdx, aIRpcbindinginq_0; "I_RpcBindingInqLocalClientPID failed st"...
0x180033304  mov     ecx, 2; unsigned __int8
0x180033309  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003330e  nop
0x18003330f  test    rdi, rdi
0x180033312  jz      short loc_1800332E3
0x180033314  or      eax, 0FFFFFFFFh
0x180033317  lock xadd [rdi+18h], eax
0x18003331c  sub     eax, 1
0x18003331f  jnz     short loc_1800332EF
0x180033321  nop
0x180033322  call    WINRT_IMPL_GetProcessHeap
0x180033327  mov     r8, rdi
0x18003332a  jmp     short loc_1800332D9
```
