# CommandParamReceiver::operator()(DestroyParams const &)

- ea: `0x140009434`
- end: `0x1400095ba`
- name: `??RCommandParamReceiver@@QEAAXAEBVDestroyParams@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(Output **, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000ded8`

## callees

- `0x140001990`
- `0x14000641c`
- `0x1400076b4`
- `0x140008454`
- `0x140009434`
- `0x1400098b0`
- `0x140009e94`
- `0x140009f58`
- `0x14000a75c`
- `0x14000cf20`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()(Output **a1, __int64 *a2)
{
  __int64 *v2; // rbx
  __int64 v4; // rcx
  _DWORD *v5; // rdi
  Output *v6; // rcx
  const struct _GUID *v7; // r8
  unsigned int v8; // edx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, __int64 *, _DWORD *, int *); // r15
  __int64 v11; // rax
  Output *v12; // rcx
  int v13; // edx
  _QWORD v15[4]; // [rsp+38h] [rbp-20h] BYREF
  int v16; // [rsp+90h] [rbp+38h] BYREF
  _DWORD *v17; // [rsp+98h] [rbp+40h] BYREF
  int v18; // [rsp+A0h] [rbp+48h] BYREF
  int v19; // [rsp+A4h] [rbp+4Ch]
  __int64 v20; // [rsp+A8h] [rbp+50h] BYREF

  v2 = a2;
  v18 = 0;
  v19 = 1;
  if ( !*((_BYTE *)a2 + 32) )
  {
    LODWORD(v17) = -2147024809;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v18, &v17);
    v15[0] = L"/instance";
    v15[1] = L"parameterName";
    v15[2] = L"";
    v19 = 3;
    if ( v18 < 0 )
    {
      Output::DisplayErrorResource<unsigned short const *>(v4, 421, v15);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v18);
    }
  }
  Output::DisplayStatusResource(*a1, 503);
  v5 = operator new(0x18u);
  v17 = v5;
  v6 = *a1;
  *(_QWORD *)v5 = &StatusCallbackImpl::`vftable';
  v5[2] = 1;
  *((_QWORD *)v5 + 2) = v6;
  CommandParamReceiver::CreateInstance((HWND)a1, (struct _GUID *)&v20, v7);
  v16 = 0;
  v9 = v20;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *, _DWORD *, int *))(*(_QWORD *)v20 + 32LL);
  if ( !*((_BYTE *)v2 + 32) )
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v8);
  if ( (unsigned __int64)v2[3] > 7 )
    v2 = (__int64 *)*v2;
  LODWORD(v17) = v10(v9, v2, v5, &v16);
  v11 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v18, &v17);
  errorlib::scoped_error<hresult_error::tag>::throwfailed(v11);
  if ( v16 )
  {
    v13 = 514;
    if ( *((_BYTE *)*a1 + 40) )
      v13 = 515;
    Output::PromptUser(v12, v13);
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  return errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v18);
}

```

## disassembly

```asm
0x140009434  push    rbp
0x140009436  push    rbx
0x140009437  push    rsi
0x140009438  push    rdi
0x140009439  push    r14
0x14000943b  push    r15
0x14000943d  mov     rbp, rsp
0x140009440  sub     rsp, 58h
0x140009444  mov     rbx, rdx
0x140009447  mov     rsi, rcx
0x14000944a  mov     [rbp+arg_10], 0
0x140009451  mov     r14d, 1
0x140009457  mov     [rbp+arg_14], r14d
0x14000945b  cmp     byte ptr [rdx+20h], 0
0x14000945f  jnz     short loc_1400094BA
0x140009461  mov     dword ptr [rbp+arg_8], 80070057h
0x140009468  lea     rdx, [rbp+arg_8]
0x14000946c  lea     rcx, [rbp+arg_10]
0x140009470  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140009475  mov     rax, cs:off_140014138; "/instance"
0x14000947c  mov     [rbp+var_20], rax
0x140009480  lea     rax, aParametername; "parameterName"
0x140009487  mov     [rbp+var_18], rax
0x14000948b  lea     rax, aParametername+1Ah; ""
0x140009492  mov     [rbp+var_10], rax
0x140009496  mov     [rbp+arg_14], 3
0x14000949d  cmp     [rbp+arg_10], 0
0x1400094a1  jge     short loc_1400094BA
0x1400094a3  lea     r8, [rbp+var_20]
0x1400094a7  mov     edx, 1A5h
0x1400094ac  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x1400094b1  lea     rcx, [rbp+arg_10]
0x1400094b5  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x1400094ba  mov     edx, 1F7h; int
0x1400094bf  mov     rcx, [rsi]; this
0x1400094c2  call    ?DisplayStatusResource@Output@@QEBAXH@Z; Output::DisplayStatusResource(int)
0x1400094c7  mov     [rbp+var_28], 0
0x1400094cf  mov     ecx, 18h; Size
0x1400094d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400094d9  mov     rdi, rax
0x1400094dc  mov     [rbp+arg_8], rax
0x1400094e0  mov     rcx, [rsi]
0x1400094e3  lea     rax, ??_7StatusCallbackImpl@@6B@; const StatusCallbackImpl::`vftable'
0x1400094ea  mov     [rdi], rax
0x1400094ed  mov     [rdi+8], r14d
0x1400094f1  mov     [rdi+10h], rcx
0x1400094f5  mov     [rbp+var_28], rdi
0x1400094f9  lea     rdx, [rbp+arg_18]
0x1400094fd  mov     rcx, rsi
0x140009500  call    ?CreateInstance@CommandParamReceiver@@AEAA?AV?$com_ptr_t@UITpmVirtualSmartCardManager@@Uerr_exception_policy@wil@@@wil@@XZ; CommandParamReceiver::CreateInstance(void)
0x140009505  nop
0x140009506  mov     [rbp+arg_0], 0
0x14000950d  mov     r14, [rbp+arg_18]
0x140009511  mov     rax, [r14]
0x140009514  mov     r15, [rax+20h]
0x140009518  cmp     byte ptr [rbx+20h], 0
0x14000951c  jnz     short loc_140009528
0x14000951e  mov     ecx, 80004004h; this
0x140009523  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140009528  cmp     qword ptr [rbx+18h], 7
0x14000952d  jbe     short loc_140009532
0x14000952f  mov     rbx, [rbx]
0x140009532  lea     r9, [rbp+arg_0]
0x140009536  mov     r8, rdi
0x140009539  mov     rdx, rbx
0x14000953c  mov     rcx, r14
0x14000953f  mov     rax, r15
0x140009542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009547  mov     dword ptr [rbp+arg_8], eax
0x14000954a  lea     rdx, [rbp+arg_8]
0x14000954e  lea     rcx, [rbp+arg_10]
0x140009552  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140009557  mov     rcx, rax
0x14000955a  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x14000955f  cmp     [rbp+arg_0], 0
0x140009563  jz      short loc_14000957E
0x140009565  mov     rax, [rsi]
0x140009568  cmp     byte ptr [rax+28h], 0
0x14000956c  mov     edx, 202h
0x140009571  jz      short loc_140009578
0x140009573  mov     edx, 203h; int
0x140009578  call    ?PromptUser@Output@@QEBAXH@Z; Output::PromptUser(int)
0x14000957d  nop
0x14000957e  mov     rcx, [rbp+arg_18]
0x140009582  test    rcx, rcx
0x140009585  jz      short loc_140009594
0x140009587  mov     rax, [rcx]
0x14000958a  mov     rax, [rax+10h]
0x14000958e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009593  nop
0x140009594  mov     rax, [rdi]
0x140009597  mov     rcx, rdi
0x14000959a  mov     rax, [rax+10h]
0x14000959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095a3  nop
0x1400095a4  lea     rcx, [rbp+arg_10]
0x1400095a8  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1400095ad  add     rsp, 58h
0x1400095b1  pop     r15
0x1400095b3  pop     r14
0x1400095b5  pop     rdi
0x1400095b6  pop     rsi
0x1400095b7  pop     rbx
0x1400095b8  pop     rbp
0x1400095b9  retn
```
