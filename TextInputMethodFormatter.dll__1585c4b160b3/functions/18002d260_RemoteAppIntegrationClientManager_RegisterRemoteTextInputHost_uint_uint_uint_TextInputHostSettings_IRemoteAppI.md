# RemoteAppIntegrationClientManager::RegisterRemoteTextInputHost(uint,uint,uint,TextInputHostSettings,IRemoteAppIntegrationOwner *)

- ea: `0x18002d260`
- end: `0x18002d581`
- name: `?RegisterRemoteTextInputHost@RemoteAppIntegrationClientManager@@UEAAJIIIUTextInputHostSettings@@PEAUIRemoteAppIntegrationOwner@@@Z`
- size: `801`
- prototype: `int __high(unsigned int, unsigned int, unsigned int, struct TextInputHostSettings, struct IRemoteAppIntegrationOwner *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002240`
- `0x180002270`
- `0x180006a14`
- `0x1800290cc`
- `0x18002d260`
- `0x180035874`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d401`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d401`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoteAppIntegrationClientManager::RegisterRemoteTextInputHost(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        struct IRemoteAppIntegrationOwner *a6)
{
  __int64 v7; // r14
  struct IMessageSession *v9; // r15
  struct IMessagePort *v10; // r12
  RemoteAppIntegrationHost *v11; // rax
  RemoteAppIntegrationHost *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rax
  int v16; // eax
  __int64 v17; // rbx
  __int128 v18; // xmm7
  __int128 v19; // xmm6
  __int64 v20; // xmm8_8
  _OWORD *v21; // rcx
  __int64 v22; // rcx
  int v23; // [rsp+28h] [rbp-E0h]
  __int128 v25; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v27[24]; // [rsp+78h] [rbp-90h]
  __int128 v28; // [rsp+98h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-60h]
  __int64 v30; // [rsp+B8h] [rbp-50h]
  RemoteAppIntegrationHost *v31; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v33; // [rsp+E0h] [rbp-28h]
  __int64 v34; // [rsp+F0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v7 = a2;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  *((_QWORD *)&v26 + 1) = 0;
  *(_OWORD *)&v27[8] = 0;
  v9 = *(struct IMessageSession **)(a1 + 32);
  v10 = *(struct IMessagePort **)(a1 + 56);
  v11 = (RemoteAppIntegrationHost *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v13 = -2147024882;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclientmanager.cpp",
      (const char *)v13,
      v23);
    return v13;
  }
  *((_DWORD *)v11 + 3) = 1;
  *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      0);
  *(_QWORD *)v12 = &RemoteAppIntegrationHost::`vftable';
  *((_QWORD *)v12 + 2) = 0;
  *((_QWORD *)v12 + 3) = 0;
  *((_QWORD *)v12 + 4) = 0;
  *((_QWORD *)v12 + 5) = 0;
  *((_QWORD *)v12 + 6) = 0;
  v13 = RemoteAppIntegrationHost::RuntimeClassInitialize(v12, a6, v7, v10, v9);
  v14 = *(_QWORD *)v12;
  if ( (v13 & 0x80000000) != 0 )
  {
    (*(void (__fastcall **)(RemoteAppIntegrationHost *))(v14 + 16))(v12);
    goto LABEL_7;
  }
  (*(void (__fastcall **)(RemoteAppIntegrationHost *))(v14 + 8))(v12);
  (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v12 + 16LL))(v12);
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(**(_QWORD **)(a1 + 32) + 136LL))(
          *(_QWORD *)(a1 + 32),
          *((_QWORD *)v12 + 2),
          &v32);
  v13 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationclientmanager.cpp",
      (const char *)(unsigned int)v16,
      v23);
    (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v12 + 16LL))(v12);
    return v13;
  }
  *(_QWORD *)&v25 = *((_QWORD *)&v32 + 1);
  DWORD2(v25) = DWORD1(v32);
  DWORD1(v26) = a3;
  LODWORD(v26) = GetCurrentProcessId();
  *(_OWORD *)&v27[8] = *(_OWORD *)(a1 + 64);
  *(_QWORD *)v27 = v7;
  v17 = *(_QWORD *)(a1 + 16);
  v31 = v12;
  (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v12 + 8LL))(v12);
  v18 = v26;
  v28 = v26;
  v19 = *(_OWORD *)v27;
  v29 = *(_OWORD *)v27;
  v20 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v27[8], *(__m128d *)&v27[8]);
  v30 = v20;
  v26 = v32;
  *(_OWORD *)v27 = v33;
  *(_QWORD *)&v27[16] = v34;
  RemoteAppIntegrationServer::AddHostIdMapping(
    v17,
    v7,
    (unsigned int)&v25,
    (unsigned int)&v26,
    (__int64)&v28,
    (__int64)&v31);
  v21 = *(_OWORD **)(a1 + 16);
  v25 = v21[7];
  v28 = v32;
  v29 = v33;
  v30 = v34;
  (*(void (__fastcall **)(_OWORD *, __int128 *, _QWORD, _QWORD, __int64, __int128 *))(*(_QWORD *)v21 + 24LL))(
    v21,
    &v28,
    0,
    a4,
    a5,
    &v25);
  v22 = *(_QWORD *)(a1 + 16);
  v28 = v18;
  v29 = v19;
  v30 = v20;
  v26 = v32;
  *(_OWORD *)v27 = v33;
  *(_QWORD *)&v27[16] = v34;
  (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v22 + 464LL))(v22, &v26, &v28);
  (*(void (__fastcall **)(RemoteAppIntegrationHost *))(*(_QWORD *)v12 + 16LL))(v12);
  return 0;
}

```

## disassembly

```asm
0x18002d260  mov     rax, rsp
0x18002d263  push    rbp
0x18002d264  push    rbx
0x18002d265  push    rsi
0x18002d266  push    rdi
0x18002d267  push    r12
0x18002d269  push    r13
0x18002d26b  push    r14
0x18002d26d  push    r15
0x18002d26f  lea     rbp, [rax-78h]
0x18002d273  sub     rsp, 138h
0x18002d27a  movaps  xmmword ptr [rax-58h], xmm6
0x18002d27e  movaps  xmmword ptr [rax-68h], xmm7
0x18002d282  movaps  xmmword ptr [rax-78h], xmm8
0x18002d287  mov     rax, cs:__security_cookie
0x18002d28e  xor     rax, rsp
0x18002d291  mov     [rbp+70h+var_80], rax
0x18002d295  mov     [rsp+170h+var_130], r9d
0x18002d29a  mov     r13d, r8d
0x18002d29d  mov     r14d, edx
0x18002d2a0  mov     rsi, rcx
0x18002d2a3  mov     rbx, [rbp+70h+arg_28]
0x18002d2aa  xorps   xmm0, xmm0
0x18002d2ad  xor     eax, eax
0x18002d2af  movups  [rbp+70h+var_A8], xmm0
0x18002d2b3  movups  [rbp+70h+var_98], xmm0
0x18002d2b7  mov     [rbp+70h+var_88], rax
0x18002d2bb  mov     qword ptr [rsp+170h+var_108], rax
0x18002d2c0  movdqu  xmmword ptr [rsp+78h], xmm0
0x18002d2c6  mov     r15, [rcx+20h]
0x18002d2ca  mov     r12, [rcx+38h]
0x18002d2ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d2d5  lea     ecx, [rax+40h]; unsigned __int64
0x18002d2d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d2dd  mov     rdi, rax
0x18002d2e0  xor     edx, edx
0x18002d2e2  test    rax, rax
0x18002d2e5  jnz     short loc_18002D2EE
0x18002d2e7  mov     ebx, 8007000Eh
0x18002d2ec  jmp     short loc_18002D363
0x18002d2ee  mov     dword ptr [rax+0Ch], 1
0x18002d2f5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18002d2fc  mov     [rdi], rax
0x18002d2ff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002d306  test    rcx, rcx
0x18002d309  jz      short loc_18002D319
0x18002d30b  mov     rax, [rcx]
0x18002d30e  mov     rax, [rax+8]
0x18002d312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d317  xor     edx, edx
0x18002d319  lea     rax, ??_7RemoteAppIntegrationHost@@6B@; const RemoteAppIntegrationHost::`vftable'
0x18002d320  mov     [rdi], rax
0x18002d323  mov     [rdi+10h], rdx
0x18002d327  mov     [rdi+18h], rdx
0x18002d32b  mov     [rdi+20h], rdx
0x18002d32f  mov     [rdi+28h], rdx
0x18002d333  mov     [rdi+30h], rdx
0x18002d337  mov     [rsp+170h+var_150], r15; int
0x18002d33c  mov     r9, r12; struct IMessagePort *
0x18002d33f  mov     r8d, r14d; unsigned int
0x18002d342  mov     rdx, rbx; struct IRemoteAppIntegrationOwner *
0x18002d345  mov     rcx, rdi; this
0x18002d348  call    ?RuntimeClassInitialize@RemoteAppIntegrationHost@@QEAAJPEAUIRemoteAppIntegrationOwner@@IPEAUIMessagePort@@PEAUIMessageSession@@@Z; RemoteAppIntegrationHost::RuntimeClassInitialize(IRemoteAppIntegrationOwner *,uint,IMessagePort *,IMessageSession *)
0x18002d34d  mov     ebx, eax
0x18002d34f  mov     rax, [rdi]
0x18002d352  test    ebx, ebx
0x18002d354  jns     short loc_18002D383
0x18002d356  mov     rcx, rdi
0x18002d359  mov     rax, [rax+10h]
0x18002d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d362  nop
0x18002d363  mov     rcx, [rbp+78h]; this
0x18002d367  mov     r9d, ebx; char *
0x18002d36a  lea     r8, aMincoreTextinp_3; "mincore\\textinput\\dev\\virtualization"...
0x18002d371  mov     edx, 71h ; 'q'; void *
0x18002d376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d37b  nop
0x18002d37c  mov     eax, ebx
0x18002d37e  jmp     loc_18002D54E
0x18002d383  mov     rcx, rdi
0x18002d386  mov     rax, [rax+8]
0x18002d38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d38f  nop
0x18002d390  mov     rax, [rdi]
0x18002d393  mov     rcx, rdi
0x18002d396  mov     rax, [rax+10h]
0x18002d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d39f  nop
0x18002d3a0  mov     rcx, [rsi+20h]
0x18002d3a4  mov     rax, [rcx]
0x18002d3a7  lea     r8, [rbp+70h+var_A8]
0x18002d3ab  mov     rdx, [rdi+10h]
0x18002d3af  mov     rax, [rax+88h]
0x18002d3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3bb  mov     ebx, eax
0x18002d3bd  test    eax, eax
0x18002d3bf  jns     short loc_18002D3EC
0x18002d3c1  mov     rcx, [rbp+78h]; this
0x18002d3c5  mov     r9d, eax; char *
0x18002d3c8  lea     r8, aMincoreTextinp_3; "mincore\\textinput\\dev\\virtualization"...
0x18002d3cf  mov     edx, 74h ; 't'; void *
0x18002d3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d3d9  nop
0x18002d3da  mov     rcx, [rdi]
0x18002d3dd  mov     rax, [rcx+10h]
0x18002d3e1  mov     rcx, rdi
0x18002d3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3e9  nop
0x18002d3ea  jmp     short loc_18002D37C
0x18002d3ec  mov     rax, qword ptr [rbp+70h+var_A8+8]
0x18002d3f0  mov     qword ptr [rsp+170h+var_128+8], rax
0x18002d3f5  mov     eax, dword ptr [rbp+70h+var_A8+4]
0x18002d3f8  mov     dword ptr [rsp+170h+var_118], eax
0x18002d3fc  mov     dword ptr [rsp+170h+var_118+0Ch], r13d
0x18002d401  call    cs:__imp_GetCurrentProcessId
0x18002d407  mov     dword ptr [rsp+170h+var_118+8], eax
0x18002d40b  movups  xmm8, xmmword ptr [rsi+40h]
0x18002d410  movdqu  xmmword ptr [rsp+78h], xmm8
0x18002d417  mov     qword ptr [rsp+170h+var_108+8], r14
0x18002d41c  mov     rbx, [rsi+10h]
0x18002d420  mov     [rbp+70h+var_B0], rdi
0x18002d424  mov     rax, [rdi]
0x18002d427  mov     rcx, rdi
0x18002d42a  mov     rax, [rax+8]
0x18002d42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d433  nop
0x18002d434  movups  xmm0, [rbp+70h+var_A8]
0x18002d438  movups  xmm1, [rbp+70h+var_98]
0x18002d43c  movsd   xmm2, [rbp+70h+var_88]
0x18002d441  movups  xmm7, [rsp+170h+var_118+8]
0x18002d446  movaps  [rbp+70h+var_E0], xmm7
0x18002d44a  movups  xmm6, [rsp+170h+var_108+8]
0x18002d44f  movaps  [rbp+70h+var_D0], xmm6
0x18002d453  unpckhpd xmm8, xmm8
0x18002d458  movsd   [rbp+70h+var_C0], xmm8
0x18002d45e  movaps  [rsp+170h+var_118+8], xmm0
0x18002d463  movaps  [rsp+170h+var_108+8], xmm1
0x18002d468  movsd   [rbp+70h+var_F0], xmm2
0x18002d46d  movaps  xmm0, [rsp+170h+var_128+8]
0x18002d472  movdqa  [rsp+170h+var_128+8], xmm0
0x18002d478  lea     rax, [rbp+70h+var_B0]
0x18002d47c  mov     [rsp+170h+var_148], rax
0x18002d481  lea     rax, [rbp+70h+var_E0]
0x18002d485  mov     [rsp+170h+var_150], rax
0x18002d48a  lea     r9, [rsp+170h+var_118+8]
0x18002d48f  lea     r8, [rsp+170h+var_128+8]
0x18002d494  mov     edx, r14d
0x18002d497  mov     rcx, rbx
0x18002d49a  call    ?AddHostIdMapping@RemoteAppIntegrationServer@@QEAAIIUMessageObjectID@@UtagMsgRoutingInfo@@1V?$ComPtr@VRemoteAppIntegrationHost@@@WRL@Microsoft@@@Z; RemoteAppIntegrationServer::AddHostIdMapping(uint,MessageObjectID,tagMsgRoutingInfo,tagMsgRoutingInfo,Microsoft::WRL::ComPtr<RemoteAppIntegrationHost>)
0x18002d49f  mov     rcx, [rsi+10h]
0x18002d4a3  movups  xmm0, xmmword ptr [rcx+70h]
0x18002d4a7  movdqu  [rsp+170h+var_128+8], xmm0
0x18002d4ad  movups  xmm1, [rbp+70h+var_A8]
0x18002d4b1  movaps  [rbp+70h+var_E0], xmm1
0x18002d4b5  movups  xmm0, [rbp+70h+var_98]
0x18002d4b9  movaps  [rbp+70h+var_D0], xmm0
0x18002d4bd  movsd   xmm1, [rbp+70h+var_88]
0x18002d4c2  movsd   [rbp+70h+var_C0], xmm1
0x18002d4c7  mov     rax, [rcx]
0x18002d4ca  lea     rdx, [rsp+170h+var_128+8]
0x18002d4cf  mov     [rsp+170h+var_148], rdx
0x18002d4d4  mov     rdx, [rbp+70h+arg_20]
0x18002d4db  mov     [rsp+170h+var_150], rdx
0x18002d4e0  mov     r9d, [rsp+170h+var_130]
0x18002d4e5  xor     r8d, r8d
0x18002d4e8  lea     rdx, [rbp+70h+var_E0]
0x18002d4ec  mov     rax, [rax+18h]
0x18002d4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4f5  mov     rcx, [rsi+10h]
0x18002d4f9  movups  xmm0, [rbp+70h+var_A8]
0x18002d4fd  movups  xmm1, [rbp+70h+var_98]
0x18002d501  movsd   xmm2, [rbp+70h+var_88]
0x18002d506  movaps  [rbp+70h+var_E0], xmm7
0x18002d50a  movaps  [rbp+70h+var_D0], xmm6
0x18002d50e  movsd   [rbp+70h+var_C0], xmm8
0x18002d514  movaps  [rsp+170h+var_118+8], xmm0
0x18002d519  movaps  [rsp+170h+var_108+8], xmm1
0x18002d51e  movsd   [rbp+70h+var_F0], xmm2
0x18002d523  mov     rax, [rcx]
0x18002d526  lea     r8, [rbp+70h+var_E0]
0x18002d52a  lea     rdx, [rsp+170h+var_118+8]
0x18002d52f  mov     rax, [rax+1D0h]
0x18002d536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d53b  nop
0x18002d53c  mov     rax, [rdi]
0x18002d53f  mov     rcx, rdi
0x18002d542  mov     rax, [rax+10h]
0x18002d546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d54b  nop
0x18002d54c  xor     eax, eax
0x18002d54e  mov     rcx, [rbp+70h+var_80]
0x18002d552  xor     rcx, rsp; StackCookie
0x18002d555  call    __security_check_cookie
0x18002d55a  lea     r11, [rsp+170h+var_38]
0x18002d562  movaps  xmm6, xmmword ptr [r11-18h]
0x18002d567  movaps  xmm7, xmmword ptr [r11-28h]
0x18002d56c  movaps  xmm8, xmmword ptr [r11-38h]
0x18002d571  mov     rsp, r11
0x18002d574  pop     r15
0x18002d576  pop     r14
0x18002d578  pop     r13
0x18002d57a  pop     r12
0x18002d57c  pop     rdi
0x18002d57d  pop     rsi
0x18002d57e  pop     rbx
0x18002d57f  pop     rbp
0x18002d580  retn
```
