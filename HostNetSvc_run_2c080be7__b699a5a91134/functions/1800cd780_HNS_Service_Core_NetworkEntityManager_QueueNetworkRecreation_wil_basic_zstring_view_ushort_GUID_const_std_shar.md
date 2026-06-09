# HNS::Service::Core::NetworkEntityManager::QueueNetworkRecreation(wil::basic_zstring_view<ushort>,_GUID const &,std::shared_ptr<HNS::Service::Events::Event> const &,std::shared_ptr<HNS::Service::Resource::SwitchResource>)

- ea: `0x1800cd780`
- end: `0x1800cda18`
- name: `?QueueNetworkRecreation@NetworkEntityManager@Core@Service@HNS@@QEAAXV?$basic_zstring_view@G@wil@@AEBU_GUID@@AEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@V?$shared_ptr@VSwitchResource@Resource@Service@HNS@@@9@@Z`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800cb6c4`

## callees

- `0x180001b68`
- `0x18005f0c0`
- `0x18005f59c`
- `0x18005ffb8`
- `0x180061240`
- `0x180069104`
- `0x18007e864`
- `0x1800bec8c`
- `0x1800cd780`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd9ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cd90d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cd90d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cd962`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cd962`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800cd96b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800cd96b`

## string_xrefs

- `0x1800cda06`: `onecore\vm\dv\net\hns\service\core\networkentitymanager.cpp`
- `0x1800cd9fa`: `Unable to create thread pool work`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HNS::Service::Core::NetworkEntityManager::QueueNetworkRecreation(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  char *v9; // rdi
  __int64 v10; // r8
  _QWORD *v11; // rsi
  const void *v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rbx
  struct _TP_WORK *ThreadpoolWork; // rbx
  volatile signed __int32 *v22; // rbx
  signed int LastError; // ebx
  unsigned int v24; // edx
  unsigned int v25; // eax
  const char *v26; // [rsp+28h] [rbp-80h]
  _BYTE v27[32]; // [rsp+38h] [rbp-70h] BYREF
  _OWORD *v28; // [rsp+58h] [rbp-50h]
  __int64 v29; // [rsp+60h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v9 = (char *)operator new(0x50u);
  *(_QWORD *)v9 = 0;
  *((_QWORD *)v9 + 1) = 0;
  v11 = v9 + 16;
  *((_OWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 7;
  *((_WORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 6) = 0;
  *((_QWORD *)v9 + 7) = 0;
  *((_QWORD *)v9 + 8) = 0;
  *((_QWORD *)v9 + 9) = 0;
  *(_OWORD *)v9 = *a3;
  v12 = *(const void **)a2;
  v13 = *(_QWORD *)(a2 + 8);
  if ( v13 > *((_QWORD *)v9 + 5) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v11, v13, v10, v12);
  }
  else
  {
    if ( *((_QWORD *)v9 + 5) > 7u )
      v11 = (_QWORD *)*v11;
    *((_QWORD *)v9 + 4) = v13;
    v14 = 2 * v13;
    memmove_0(v11, v12, 2 * v13);
    *(_WORD *)((char *)v11 + v14) = 0;
  }
  v15 = a4[1];
  if ( v15 )
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  v16 = a4[1];
  *((_QWORD *)v9 + 6) = *a4;
  v17 = (volatile signed __int32 *)*((_QWORD *)v9 + 7);
  *((_QWORD *)v9 + 7) = v16;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = a5[1];
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
  v19 = a5[1];
  *((_QWORD *)v9 + 8) = *a5;
  v20 = (volatile signed __int32 *)*((_QWORD *)v9 + 9);
  *((_QWORD *)v9 + 9) = v19;
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     HNS::Service::Core::NetworkEntityManager::NonHnsNetRecreationCallback,
                     v9,
                     (PTP_CALLBACK_ENVIRON)(a1 + 872));
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    HNS::Service::Core::NonHnsNetRecreationData::`scalar deleting destructor'(
      (HNS::Service::Core::NonHnsNetRecreationData *)v9,
      v24);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v25 = wil::verify_hresult<long>((unsigned int)LastError);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x9F9,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networkentitymanager.cpp",
      (const char *)v25,
      (int)"Unable to create thread pool work",
      v26);
  }
  if ( *(_DWORD *)qword_1803989E8 > 4u )
  {
    v28 = a3;
    v29 = 16;
    tlgWriteTransfer_EventWriteTransfer(qword_1803989E8, &byte_18033614F, 0, 0, 3, v27);
  }
  SubmitThreadpoolWork(ThreadpoolWork);
  CloseThreadpoolWork(ThreadpoolWork);
  v22 = (volatile signed __int32 *)a5[1];
  if ( v22 && !_InterlockedDecrement(v22 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
    if ( !_InterlockedDecrement(v22 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
  }
}

```

## disassembly

```asm
0x1800cd780  push    rbx
0x1800cd782  push    rbp
0x1800cd783  push    rsi
0x1800cd784  push    rdi
0x1800cd785  push    r13
0x1800cd787  push    r14
0x1800cd789  push    r15
0x1800cd78b  sub     rsp, 70h
0x1800cd78f  mov     rax, cs:__security_cookie
0x1800cd796  xor     rax, rsp
0x1800cd799  mov     [rsp+0A8h+var_40], rax
0x1800cd79e  mov     r15, r9
0x1800cd7a1  mov     rbp, r8
0x1800cd7a4  mov     rbx, rdx
0x1800cd7a7  mov     r13, rcx
0x1800cd7aa  mov     r14, [rsp+0A8h+arg_20]
0x1800cd7b2  mov     [rsp+0A8h+var_78], r14
0x1800cd7b7  mov     ecx, 50h ; 'P'; Size
0x1800cd7bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800cd7c1  mov     rdi, rax
0x1800cd7c4  mov     qword ptr [rax], 0
0x1800cd7cb  mov     qword ptr [rax+8], 0
0x1800cd7d3  lea     rsi, [rax+10h]
0x1800cd7d7  xorps   xmm0, xmm0
0x1800cd7da  movups  xmmword ptr [rsi], xmm0
0x1800cd7dd  lea     rax, [rsi+10h]
0x1800cd7e1  mov     qword ptr [rax], 0
0x1800cd7e8  mov     qword ptr [rsi+18h], 7
0x1800cd7f0  xor     ecx, ecx
0x1800cd7f2  mov     [rsi], cx
0x1800cd7f5  mov     [rdi+30h], rcx
0x1800cd7f9  mov     [rdi+38h], rcx
0x1800cd7fd  mov     [rdi+40h], rcx
0x1800cd801  mov     [rdi+48h], rcx
0x1800cd805  movups  xmm0, xmmword ptr [rbp+0]
0x1800cd809  movdqu  xmmword ptr [rdi], xmm0
0x1800cd80d  mov     r9, [rbx]
0x1800cd810  mov     rdx, [rbx+8]
0x1800cd814  cmp     rdx, [rsi+18h]
0x1800cd818  ja      short loc_1800CD841
0x1800cd81a  cmp     qword ptr [rsi+18h], 7
0x1800cd81f  jbe     short loc_1800CD824
0x1800cd821  mov     rsi, [rsi]
0x1800cd824  mov     [rax], rdx
0x1800cd827  lea     rbx, [rdx+rdx]
0x1800cd82b  mov     r8, rbx; Size
0x1800cd82e  mov     rdx, r9; Src
0x1800cd831  mov     rcx, rsi; void *
0x1800cd834  call    memmove_0
0x1800cd839  xor     eax, eax
0x1800cd83b  mov     [rbx+rsi], ax
0x1800cd83f  jmp     short loc_1800CD849
0x1800cd841  mov     rcx, rsi
0x1800cd844  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800cd849  mov     rax, [r15+8]
0x1800cd84d  test    rax, rax
0x1800cd850  jz      short loc_1800CD856
0x1800cd852  lock inc dword ptr [rax+8]
0x1800cd856  mov     rcx, [r15+8]
0x1800cd85a  mov     rax, [r15]
0x1800cd85d  mov     [rdi+30h], rax
0x1800cd861  mov     rbx, [rdi+38h]
0x1800cd865  mov     [rdi+38h], rcx
0x1800cd869  or      esi, 0FFFFFFFFh
0x1800cd86c  test    rbx, rbx
0x1800cd86f  jz      short loc_1800CD8A4
0x1800cd871  mov     eax, esi
0x1800cd873  lock xadd [rbx+8], eax
0x1800cd878  add     eax, esi
0x1800cd87a  jnz     short loc_1800CD8A4
0x1800cd87c  mov     rax, [rbx]
0x1800cd87f  mov     rcx, rbx
0x1800cd882  mov     rax, [rax]
0x1800cd885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd88a  mov     eax, esi
0x1800cd88c  lock xadd [rbx+0Ch], eax
0x1800cd891  add     eax, esi
0x1800cd893  jnz     short loc_1800CD8A4
0x1800cd895  mov     rax, [rbx]
0x1800cd898  mov     rcx, rbx
0x1800cd89b  mov     rax, [rax+8]
0x1800cd89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8a4  mov     rax, [r14+8]
0x1800cd8a8  test    rax, rax
0x1800cd8ab  jz      short loc_1800CD8B1
0x1800cd8ad  lock inc dword ptr [rax+8]
0x1800cd8b1  mov     rcx, [r14+8]
0x1800cd8b5  mov     rax, [r14]
0x1800cd8b8  mov     [rdi+40h], rax
0x1800cd8bc  mov     rbx, [rdi+48h]
0x1800cd8c0  mov     [rdi+48h], rcx
0x1800cd8c4  test    rbx, rbx
0x1800cd8c7  jz      short loc_1800CD8FC
0x1800cd8c9  mov     eax, esi
0x1800cd8cb  lock xadd [rbx+8], eax
0x1800cd8d0  add     eax, esi
0x1800cd8d2  jnz     short loc_1800CD8FC
0x1800cd8d4  mov     rax, [rbx]
0x1800cd8d7  mov     rcx, rbx
0x1800cd8da  mov     rax, [rax]
0x1800cd8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8e2  mov     eax, esi
0x1800cd8e4  lock xadd [rbx+0Ch], eax
0x1800cd8e9  add     eax, esi
0x1800cd8eb  jnz     short loc_1800CD8FC
0x1800cd8ed  mov     rax, [rbx]
0x1800cd8f0  mov     rcx, rbx
0x1800cd8f3  mov     rax, [rax+8]
0x1800cd8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8fc  lea     r8, [r13+368h]; pcbe
0x1800cd903  mov     rdx, rdi; pv
0x1800cd906  lea     rcx, ?NonHnsNetRecreationCallback@NetworkEntityManager@Core@Service@HNS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800cd90d  call    cs:__imp_CreateThreadpoolWork
0x1800cd913  mov     rbx, rax
0x1800cd916  test    rax, rax
0x1800cd919  jz      loc_1800CD9CA
0x1800cd91f  mov     rcx, cs:qword_1803989E8
0x1800cd926  mov     eax, [rcx]
0x1800cd928  cmp     eax, 4
0x1800cd92b  jbe     short loc_1800CD95F
0x1800cd92d  mov     [rsp+0A8h+var_50], rbp
0x1800cd932  mov     [rsp+0A8h+var_48], 10h
0x1800cd93b  lea     rax, [rsp+0A8h+var_70]
0x1800cd940  mov     [rsp+0A8h+var_80], rax
0x1800cd945  mov     [rsp+0A8h+var_88], 3
0x1800cd94d  xor     r9d, r9d
0x1800cd950  xor     r8d, r8d
0x1800cd953  lea     rdx, byte_18033614F
0x1800cd95a  call    _tlgWriteTransfer_EventWriteTransfer
0x1800cd95f  mov     rcx, rbx; pwk
0x1800cd962  call    cs:__imp_SubmitThreadpoolWork
0x1800cd968  mov     rcx, rbx; pwk
0x1800cd96b  call    cs:__imp_CloseThreadpoolWork
0x1800cd971  nop
0x1800cd972  mov     rbx, [r14+8]
0x1800cd976  test    rbx, rbx
0x1800cd979  jz      short loc_1800CD9AE
0x1800cd97b  mov     eax, esi
0x1800cd97d  lock xadd [rbx+8], eax
0x1800cd982  add     eax, esi
0x1800cd984  jnz     short loc_1800CD9AE
0x1800cd986  mov     rax, [rbx]
0x1800cd989  mov     rcx, rbx
0x1800cd98c  mov     rax, [rax]
0x1800cd98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd994  mov     eax, esi
0x1800cd996  lock xadd [rbx+0Ch], eax
0x1800cd99b  add     eax, esi
0x1800cd99d  jnz     short loc_1800CD9AE
0x1800cd99f  mov     rax, [rbx]
0x1800cd9a2  mov     rcx, rbx
0x1800cd9a5  mov     rax, [rax+8]
0x1800cd9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd9ae  mov     rcx, [rsp+0A8h+var_40]
0x1800cd9b3  xor     rcx, rsp; StackCookie
0x1800cd9b6  call    __security_check_cookie
0x1800cd9bb  add     rsp, 70h
0x1800cd9bf  pop     r15
0x1800cd9c1  pop     r14
0x1800cd9c3  pop     r13
0x1800cd9c5  pop     rdi
0x1800cd9c6  pop     rsi
0x1800cd9c7  pop     rbp
0x1800cd9c8  pop     rbx
0x1800cd9c9  retn
0x1800cd9ca  call    cs:__imp_GetLastError
0x1800cd9d0  nop
0x1800cd9d1  mov     ebx, eax
0x1800cd9d3  mov     rcx, rdi; this
0x1800cd9d6  call    ??_GNonHnsNetRecreationData@Core@Service@HNS@@QEAAPEAXI@Z; HNS::Service::Core::NonHnsNetRecreationData::`scalar deleting destructor'(uint)
0x1800cd9db  test    ebx, ebx
0x1800cd9dd  jle     short loc_1800CD9E8
0x1800cd9df  movzx   ebx, bx
0x1800cd9e2  or      ebx, 80070000h
0x1800cd9e8  mov     ecx, ebx
0x1800cd9ea  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800cd9ef  mov     r9d, eax; char *
0x1800cd9f2  mov     rcx, [rsp+0A8h]; this
0x1800cd9fa  lea     rax, aUnableToCreate_2; "Unable to create thread pool work"
0x1800cda01  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x1800cda06  lea     r8, aOnecoreVmDvNet_188; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800cda0d  mov     edx, 9F9h; void *
0x1800cda12  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
