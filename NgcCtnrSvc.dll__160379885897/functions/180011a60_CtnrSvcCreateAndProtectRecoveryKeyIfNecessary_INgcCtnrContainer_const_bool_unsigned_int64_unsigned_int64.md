# CtnrSvcCreateAndProtectRecoveryKeyIfNecessary(INgcCtnrContainer * const,bool,unsigned __int64,unsigned __int64)

- ea: `0x180011a60`
- end: `0x180011d80`
- name: `?CtnrSvcCreateAndProtectRecoveryKeyIfNecessary@@YAXQEAUINgcCtnrContainer@@_N_K2@Z`
- size: `800`
- prototype: `void __fastcall(struct INgcCtnrContainer *const, bool, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180011a60`
- `0x180011d88`
- `0x180011e20`
- `0x180011ff8`
- `0x180012034`
- `0x180012090`
- `0x180022e68`
- `0x180023278`
- `0x180025874`
- `0x180026a08`
- `0x18002cdec`
- `0x18005a70c`
- `0x180080010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180011c35`
- `msvcp_win!_Mtx_unlock` at `0x180011c35`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180011c52`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180011c52`

## string_xrefs

- `0x180011cd4`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180011cf2`: `onecore\ds\security\ngc\ctnrsvc\service\containermanager.cpp`
- `0x180011bc8`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`
- `0x180011d63`: `onecore\ds\security\ngc\utils\common\lib\threadpoolmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CtnrSvcCreateAndProtectRecoveryKeyIfNecessary(struct INgcCtnrContainer *const a1, char a2, __int64 a3)
{
  int v5; // eax
  struct ThreadpoolManager *v6; // r14
  struct INgcCtnrContainer *v7; // rbx
  _DWORD *v8; // rdi
  int LastError; // ebx
  __int64 v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rcx
  const char *v13; // r9
  _QWORD *v14; // rdx
  const char *v15; // r9
  int v16[2]; // [rsp+20h] [rbp-108h] BYREF
  _QWORD v17[2]; // [rsp+28h] [rbp-100h] BYREF
  __int16 v18; // [rsp+38h] [rbp-F0h]
  __int64 v19; // [rsp+40h] [rbp-E8h]
  _BYTE *v20; // [rsp+48h] [rbp-E0h]
  _QWORD v21[4]; // [rsp+50h] [rbp-D8h] BYREF
  char v22; // [rsp+70h] [rbp-B8h]
  struct INgcCtnrContainer *v23; // [rsp+78h] [rbp-B0h]
  _QWORD *v24; // [rsp+88h] [rbp-A0h]
  _QWORD *v25; // [rsp+90h] [rbp-98h]
  _DWORD *v26; // [rsp+98h] [rbp-90h]
  __int64 (*v27)(__int64 **, unsigned int, __int64, ...); // [rsp+A0h] [rbp-88h]
  __int64 v28; // [rsp+A8h] [rbp-80h]
  __int64 v29; // [rsp+B0h] [rbp-78h]
  char v30; // [rsp+B8h] [rbp-70h]
  __int64 v31; // [rsp+C0h] [rbp-68h]
  _BYTE v32[56]; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v33; // [rsp+100h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  struct INgcCtnrContainer *v35; // [rsp+130h] [rbp+8h] BYREF

  v35 = a1;
  *(_QWORD *)v16 = 0;
  try
  {
    v5 = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *const))(*(_QWORD *)a1 + 456LL))(a1);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x71C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
        (const char *)(unsigned int)v5,
        v16[0]);
    }
    else
    {
      v17[0] = &v35;
      v17[1] = v16;
      v18 = 256;
      v6 = ThreadpoolManager::Instance();
      v7 = v35;
      if ( v35 )
        (*(void (__fastcall **)(struct INgcCtnrContainer *))(*(_QWORD *)v35 + 8LL))(v35);
      v27 = CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal;
      v28 = *(_QWORD *)v16;
      v29 = a3;
      v30 = a2;
      v19 = 0;
      v21[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool,unsigned __int64,unsigned __int64),wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool &,unsigned __int64 &,unsigned __int64 &>,long,>::`vftable';
      v21[1] = CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal;
      v21[2] = *(_QWORD *)v16;
      v21[3] = a3;
      v22 = a2;
      v31 = 0;
      v23 = v7;
      v24 = v21;
      v25 = v21;
      v8 = *(_DWORD **)v6;
      v20 = v32;
      v33 = 0;
      v33 = std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool,unsigned __int64,unsigned __int64),wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool &,unsigned __int64 &,unsigned __int64 &>,long,>::_Copy(
              v21,
              v32);
      v20 = v32;
      if ( *v8 )
      {
        v26 = v8 + 2;
        std::_Mutex_base::lock((std::_Mutex_base *)(v8 + 2));
        if ( *((_QWORD *)v8 + 13) <= (unsigned __int64)(*((_QWORD *)v8 + 15) + 1LL) )
          std::deque<std::function<long (void)>>::_Growmap(v8 + 22);
        v10 = *((_QWORD *)v8 + 13) - 1LL;
        *((_QWORD *)v8 + 14) &= v10;
        v11 = *((_QWORD *)v8 + 14) + *((_QWORD *)v8 + 15);
        if ( !*(_QWORD *)(*((_QWORD *)v8 + 12) + 8 * (v10 & v11)) )
          *(_QWORD *)(*((_QWORD *)v8 + 12) + 8 * (v10 & v11)) = operator new(0x40u);
        v12 = *(_QWORD *)(*((_QWORD *)v8 + 12) + 8 * (v11 & (*((_QWORD *)v8 + 13) - 1LL)));
        *(_QWORD *)(v12 + 56) = 0;
        std::_Func_class<long,>::_Reset_move(v12, v32);
        ++*((_QWORD *)v8 + 15);
        _Mtx_unlock((_Mtx_t)(v8 + 2));
        if ( TrySubmitThreadpoolCallback(
               ThreadpoolManager::ThreadpoolManagerImpl::WorkItemHandler,
               v8,
               *((PTP_CALLBACK_ENVIRON *)v8 + 26)) )
        {
          LastError = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA0,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\threadpoolmanager.cpp",
                        v13);
        }
      }
      else
      {
        LastError = -2147019873;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\threadpoolmanager.cpp",
          (const char *)0x8007139FLL,
          v16[0]);
      }
      std::function<long (void *,NgcUtils::CredUIStrings *)>::~function<long (void *,NgcUtils::CredUIStrings *)>(v32);
      if ( v24 )
      {
        v14 = v21;
        LOBYTE(v14) = v24 != v21;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v14);
      }
      if ( LastError < 0 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x731,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
          (const char *)(unsigned int)LastError,
          v16[0]);
      else
        HIBYTE(v18) = 0;
      wil::details::ScopeExitFnGuard__lambda_1cc96c7e7b3c99c781ac620cec69465a___::operator()(v17);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x737,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\containermanager.cpp",
      v15);
  }
}

```

## disassembly

```asm
0x180011a60  mov     [rsp+arg_8], rbx
0x180011a65  mov     [rsp+arg_10], rsi
0x180011a6a  mov     [rsp+arg_0], rcx
0x180011a6f  push    rdi
0x180011a70  push    r14
0x180011a72  push    r15
0x180011a74  sub     rsp, 110h
0x180011a7b  mov     rdi, r8
0x180011a7e  mov     sil, dl
0x180011a81  mov     qword ptr [rsp+128h+var_108], 0; int
0x180011a8a  mov     rax, [rcx]
0x180011a8d  lea     r8, [rsp+128h+var_108]
0x180011a92  mov     rdx, r9
0x180011a95  mov     rax, [rax+1C8h]
0x180011a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aa1  test    eax, eax
0x180011aa3  js      loc_180011CC9
0x180011aa9  lea     rax, [rsp+128h+arg_0]
0x180011ab1  mov     [rsp+128h+var_100], rax
0x180011ab6  lea     rax, [rsp+128h+var_108]
0x180011abb  mov     [rsp+128h+var_F8], rax
0x180011ac0  mov     [rsp+128h+var_F0], 100h
0x180011ac7  call    ?Instance@ThreadpoolManager@@SAAEAV1@XZ; ThreadpoolManager::Instance(void)
0x180011acc  mov     r14, rax
0x180011acf  mov     rbx, [rsp+128h+arg_0]
0x180011ad7  test    rbx, rbx
0x180011ada  jz      short loc_180011AEC
0x180011adc  mov     rcx, [rbx]
0x180011adf  mov     rax, [rcx+8]
0x180011ae3  mov     rcx, rbx
0x180011ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aeb  nop
0x180011aec  lea     rdx, CtnrSvcCreateAndProtectRecoveryKeyIfNecessaryInternal
0x180011af3  mov     [rsp+128h+var_88], rdx
0x180011afb  mov     rax, qword ptr [rsp+128h+var_108]
0x180011b00  mov     [rsp+128h+var_80], rax
0x180011b08  mov     [rsp+128h+var_78], rdi
0x180011b10  mov     [rsp+128h+var_70], sil
0x180011b18  mov     [rsp+128h+var_E8], 0
0x180011b21  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AJV?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@_N_K2@ZV34@AEA_NAEA_KAEA_K@std@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool,unsigned __int64,unsigned __int64),wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool &,unsigned __int64 &,unsigned __int64 &>,long,>::`vftable'
0x180011b28  mov     [rsp+128h+var_D8], rcx
0x180011b2d  mov     [rsp+128h+var_D0], rdx
0x180011b32  mov     [rsp+128h+var_C8], rax
0x180011b37  mov     [rsp+128h+var_C0], rdi
0x180011b3c  mov     [rsp+128h+var_B8], sil
0x180011b41  mov     [rsp+128h+var_68], 0
0x180011b4d  mov     [rsp+128h+var_B0], rbx
0x180011b52  lea     rax, [rsp+128h+var_D8]
0x180011b57  mov     [rsp+128h+var_A0], rax
0x180011b5f  lea     rax, [rsp+128h+var_D8]
0x180011b64  mov     [rsp+128h+var_98], rax
0x180011b6c  mov     rdi, [r14]
0x180011b6f  lea     rax, [rsp+128h+var_60]
0x180011b77  mov     [rsp+128h+var_E0], rax
0x180011b7c  mov     [rsp+128h+var_28], 0
0x180011b88  lea     rdx, [rsp+128h+var_60]
0x180011b90  lea     rcx, [rsp+128h+var_D8]
0x180011b95  call    ?_Copy@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AJV?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@_N_K2@ZV34@AEA_NAEA_KAEA_K@std@@J$$V@std@@EEBAPEAV?$_Func_base@J$$V@2@PEAX@Z; std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (&)(wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool,unsigned __int64,unsigned __int64),wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>,bool &,unsigned __int64 &,unsigned __int64 &>,long,>::_Copy(void *)
0x180011b9a  mov     [rsp+128h+var_28], rax
0x180011ba2  lea     rax, [rsp+128h+var_60]
0x180011baa  mov     [rsp+128h+var_E0], rax
0x180011baf  cmp     dword ptr [rdi], 0
0x180011bb2  jnz     loc_180011D10
0x180011bb8  mov     rcx, [rsp+128h]; this
0x180011bc0  mov     ebx, 8007139Fh
0x180011bc5  mov     r9d, ebx; char *
0x180011bc8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011bcf  mov     edx, 95h; void *
0x180011bd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bd9  nop
0x180011bda  jmp     loc_180011C68
0x180011bdf  mov     rdx, [rdi+68h]
0x180011be3  dec     rdx
0x180011be6  and     [rdi+70h], rdx
0x180011bea  mov     r15, [rdi+78h]
0x180011bee  add     r15, [rdi+70h]
0x180011bf2  mov     r14, r15
0x180011bf5  and     r14, rdx
0x180011bf8  mov     rax, [rdi+60h]
0x180011bfc  cmp     qword ptr [rax+r14*8], 0
0x180011c01  jz      loc_180011D44
0x180011c07  mov     rcx, [rdi+68h]
0x180011c0b  dec     rcx
0x180011c0e  and     rcx, r15
0x180011c11  mov     rax, [rdi+60h]
0x180011c15  mov     rcx, [rax+rcx*8]
0x180011c19  mov     qword ptr [rcx+38h], 0
0x180011c21  lea     rdx, [rsp+128h+var_60]
0x180011c29  call    ?_Reset_move@?$_Func_class@J$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<long,>::_Reset_move(std::_Func_class<long,> &&)
0x180011c2e  inc     qword ptr [rdi+78h]
0x180011c32  mov     rcx, rsi; _Mtx_t
0x180011c35  call    cs:__imp__Mtx_unlock
0x180011c3c  nop     dword ptr [rax+rax+00h]
0x180011c41  mov     r8, [rdi+0D0h]; pcbe
0x180011c48  mov     rdx, rdi; pv
0x180011c4b  lea     rcx, ?WorkItemHandler@ThreadpoolManagerImpl@ThreadpoolManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180011c52  call    cs:__imp_TrySubmitThreadpoolCallback
0x180011c59  nop     dword ptr [rax+rax+00h]
0x180011c5e  test    eax, eax
0x180011c60  jz      loc_180011D5B
0x180011c66  xor     ebx, ebx
0x180011c68  lea     rcx, [rsp+128h+var_60]
0x180011c70  call    ??1?$function@$$A6AJPEAXPEAUCredUIStrings@NgcUtils@@@Z@std@@QEAA@XZ; std::function<long (void *,NgcUtils::CredUIStrings *)>::~function<long (void *,NgcUtils::CredUIStrings *)>(void)
0x180011c75  nop
0x180011c76  mov     rcx, [rsp+128h+var_A0]
0x180011c7e  test    rcx, rcx
0x180011c81  jz      short loc_180011C9B
0x180011c83  mov     rax, [rcx]
0x180011c86  lea     rdx, [rsp+128h+var_D8]
0x180011c8b  cmp     rcx, rdx
0x180011c8e  setnz   dl
0x180011c91  mov     rax, [rax+20h]
0x180011c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c9a  nop
0x180011c9b  test    ebx, ebx
0x180011c9d  js      short loc_180011CE7
0x180011c9f  mov     byte ptr [rsp+128h+var_F0+1], 0
0x180011ca4  lea     rcx, [rsp+128h+var_100]
0x180011ca9  call    wil__details__ScopeExitFnGuard__lambda_1cc96c7e7b3c99c781ac620cec69465a_____operator__
0x180011cae  nop
0x180011caf  lea     r11, [rsp+128h+var_18]
0x180011cb7  mov     rbx, [r11+28h]
0x180011cbb  mov     rsi, [r11+30h]
0x180011cbf  mov     rsp, r11
0x180011cc2  pop     r15
0x180011cc4  pop     r14
0x180011cc6  pop     rdi
0x180011cc7  retn
0x180011cc9  mov     rcx, [rsp+128h]; this
0x180011cd1  mov     r9d, eax; char *
0x180011cd4  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180011cdb  mov     edx, 71Ch; void *
0x180011ce0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180011ce5  jmp     short loc_180011CAF
0x180011ce7  mov     rcx, [rsp+128h]; this
0x180011cef  mov     r9d, ebx; char *
0x180011cf2  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180011cf9  mov     edx, 731h; void *
0x180011cfe  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180011d03  nop
0x180011d04  lea     rcx, [rsp+128h+var_100]
0x180011d09  call    wil__details__ScopeExitFnGuard__lambda_1cc96c7e7b3c99c781ac620cec69465a_____operator__
0x180011d0e  jmp     short loc_180011CAF
0x180011d10  lea     rsi, [rdi+8]
0x180011d14  mov     [rsp+128h+var_90], rsi
0x180011d1c  mov     rcx, rsi; this
0x180011d1f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180011d24  nop
0x180011d25  mov     rax, [rdi+78h]
0x180011d29  inc     rax
0x180011d2c  cmp     [rdi+68h], rax
0x180011d30  ja      loc_180011BDF
0x180011d36  lea     rcx, [rdi+58h]
0x180011d3a  call    ?_Growmap@?$deque@V?$function@$$A6AJXZ@std@@V?$allocator@V?$function@$$A6AJXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<long (void)>>::_Growmap(unsigned __int64)
0x180011d3f  jmp     loc_180011BDF
0x180011d44  mov     ecx, 40h ; '@'; Size
0x180011d49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011d4e  mov     rcx, [rdi+60h]
0x180011d52  mov     [rcx+r14*8], rax
0x180011d56  jmp     loc_180011C07
0x180011d5b  mov     rcx, [rsp+128h]; this
0x180011d63  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180011d6a  mov     edx, 0A0h; void *
0x180011d6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011d74  mov     ebx, eax
0x180011d76  jmp     loc_180011BDA
0x180011d7b  jmp     loc_180011CAF
```
