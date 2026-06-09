# Dynamo::details::DataStore::Delete(void)

- ea: `0x140040b10`
- end: `0x140040d8c`
- name: `?Delete@DataStore@details@Dynamo@@UEAAXXZ`
- size: `636`
- prototype: `void __fastcall(Dynamo::details::DataStore *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400042f0`
- `0x140004314`
- `0x14000a6e4`
- `0x14003d008`
- `0x14003dbb4`
- `0x140040b10`
- `0x1400419a4`
- `0x14004480c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040cb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040cc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040cc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140040c07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140040c07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040cbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140040cbb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140040c7b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140040c7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Dynamo::details::DataStore::Delete(Dynamo::details::DataStore *this)
{
  char *v2; // rbx
  char *v3; // rsi
  Dynamo::TaskCreator *v4; // rax
  const char *v5; // r9
  Dynamo::TaskCreator *v6; // rsi
  HKEY v7; // r14
  LSTATUS ValueW; // eax
  bool v9; // sf
  void *v10; // rbx
  const char *v11; // r9
  unsigned int v12; // eax
  HKEY v13; // r14
  DWORD LastError; // ebx
  const unsigned __int16 *v15; // r9
  unsigned int v16; // eax
  const char *v17; // r9
  unsigned int pdwType; // [rsp+20h] [rbp-50h]
  DWORD pcbData; // [rsp+44h] [rbp-2Ch] BYREF
  Dynamo::TaskCreator *v20; // [rsp+48h] [rbp-28h]
  void *v21; // [rsp+50h] [rbp-20h]
  Dynamo::TaskCreator *pvData; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = (char *)*((_QWORD *)this + 2);
  v3 = (char *)*((_QWORD *)this + 1);
  v4 = (Dynamo::TaskCreator *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  pvData = v4;
  if ( v4 )
    v6 = Dynamo::TaskCreator::TaskCreator(v4, v3, v2, v5);
  else
    v6 = 0;
  v20 = v6;
  if ( !v6 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x18,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\DefaultFactories.h",
      v5);
  (*(void (__fastcall **)(Dynamo::TaskCreator *))(*(_QWORD *)v6 + 32LL))(v6);
  (*(void (__fastcall **)(Dynamo::TaskCreator *))(*(_QWORD *)v6 + 48LL))(v6);
  (*(void (__fastcall **)(Dynamo::TaskCreator *))(*(_QWORD *)v6 + 16LL))(v6);
  (*(void (__fastcall **)(Dynamo::TaskCreator *))(*(_QWORD *)v6 + 64LL))(v6);
  v7 = (HKEY)*((_QWORD *)this + 3);
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(v7, 0, L"StateName", 0x48u, 0, &pvData, &pcbData);
  v9 = ValueW < 0;
  if ( ValueW > 0 )
    v9 = 1;
  if ( !v9 )
  {
    v10 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 )
      *(_QWORD *)v10 = &Dynamo::WnfGenerator::`vftable';
    else
      v10 = 0;
    v21 = v10;
    if ( !v10 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x18,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\DefaultFactories.h",
        v11);
    (*(void (__fastcall **)(void *, Dynamo::TaskCreator **))(*(_QWORD *)v10 + 16LL))(v10, &pvData);
    v12 = RegDeleteValueW(v7, L"StateName");
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5C,
        (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
        (const char *)v12,
        pdwType);
    (**(void (__fastcall ***)(void *, __int64))v10)(v10, 1);
  }
  v13 = (HKEY)*((_QWORD *)this + 3);
  if ( v13 )
  {
    LastError = GetLastError();
    RegCloseKey(v13);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = 0;
  (*(void (__fastcall **)(Dynamo::details::DataStore *))(*(_QWORD *)this + 112LL))(this);
  v16 = dmstd::DeleteDynamicManagementRegistryTree(
          *((dmstd **)this + 1),
          *((const unsigned __int16 **)this + 2),
          L"Contexts",
          v15);
  v17 = (const char *)v16;
  if ( v16 == -2147024894 )
    v17 = 0;
  if ( (int)v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xBD,
      (int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\datastore.cpp",
      v17,
      pdwType);
  (**(void (__fastcall ***)(Dynamo::TaskCreator *, __int64))v6)(v6, 1);
}

```

## disassembly

```asm
0x140040b10  mov     [rsp-18h+arg_8], rbx
0x140040b15  mov     [rsp-18h+arg_10], rsi
0x140040b1a  push    rbp
0x140040b1b  push    rdi
0x140040b1c  push    r14
0x140040b1e  mov     rbp, rsp
0x140040b21  sub     rsp, 70h
0x140040b25  mov     rax, cs:__security_cookie
0x140040b2c  xor     rax, rsp
0x140040b2f  mov     [rbp+var_10], rax
0x140040b33  mov     rdi, rcx
0x140040b36  mov     [rbp+var_30], 0
0x140040b3d  mov     rbx, [rcx+10h]
0x140040b41  mov     rsi, [rcx+8]
0x140040b45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140040b4c  mov     ecx, 18h; unsigned __int64
0x140040b51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140040b56  mov     [rbp+var_18], rax
0x140040b5a  test    rax, rax
0x140040b5d  jz      short loc_140040B72
0x140040b5f  mov     r8, rbx; unsigned __int16 *
0x140040b62  mov     rdx, rsi; unsigned __int16 *
0x140040b65  mov     rcx, rax; this
0x140040b68  call    ??0TaskCreator@Dynamo@@QEAA@PEBG0@Z; Dynamo::TaskCreator::TaskCreator(ushort const *,ushort const *)
0x140040b6d  mov     rsi, rax
0x140040b70  jmp     short loc_140040B74
0x140040b72  xor     esi, esi
0x140040b74  mov     [rbp+var_28], rsi
0x140040b78  mov     [rbp+var_30], 3
0x140040b7f  mov     rcx, [rbp+18h]; this
0x140040b83  test    rsi, rsi
0x140040b86  jz      loc_140040D53
0x140040b8c  mov     rax, [rsi]
0x140040b8f  mov     rcx, rsi
0x140040b92  mov     rax, [rax+20h]
0x140040b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040b9b  mov     rax, [rsi]
0x140040b9e  mov     rcx, rsi
0x140040ba1  mov     rax, [rax+30h]
0x140040ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040baa  mov     rax, [rsi]
0x140040bad  mov     rcx, rsi
0x140040bb0  mov     rax, [rax+10h]
0x140040bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040bb9  mov     rax, [rsi]
0x140040bbc  mov     rcx, rsi
0x140040bbf  mov     rax, [rax+40h]
0x140040bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040bc8  mov     r14, [rdi+18h]
0x140040bcc  mov     [rbp+var_18], 0
0x140040bd4  mov     ebx, 8
0x140040bd9  mov     [rbp+var_2C], ebx
0x140040bdc  lea     rax, [rbp+var_2C]
0x140040be0  mov     [rsp+70h+pcbData], rax; pcbData
0x140040be5  lea     rax, [rbp+var_18]
0x140040be9  mov     [rsp+70h+pvData], rax; pvData
0x140040bee  mov     [rsp+70h+pdwType], 0; unsigned int
0x140040bf7  lea     r9d, [rbx+40h]; dwFlags
0x140040bfb  lea     r8, aStatename; "StateName"
0x140040c02  xor     edx, edx; lpSubKey
0x140040c04  mov     rcx, r14; hkey
0x140040c07  call    cs:__imp_RegGetValueW
0x140040c0d  test    eax, eax
0x140040c0f  jle     short loc_140040C1B
0x140040c11  movzx   eax, ax
0x140040c14  or      eax, 80070000h
0x140040c19  test    eax, eax
0x140040c1b  js      loc_140040CA7
0x140040c21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140040c28  mov     rcx, rbx; unsigned __int64
0x140040c2b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140040c30  mov     rbx, rax
0x140040c33  test    rax, rax
0x140040c36  jz      short loc_140040C44
0x140040c38  lea     rax, ??_7WnfGenerator@Dynamo@@6B@; const Dynamo::WnfGenerator::`vftable'
0x140040c3f  mov     [rbx], rax
0x140040c42  jmp     short loc_140040C46
0x140040c44  xor     ebx, ebx
0x140040c46  mov     [rbp+var_20], rbx
0x140040c4a  mov     [rbp+var_30], 7
0x140040c51  mov     rcx, [rbp+18h]; this
0x140040c55  test    rbx, rbx
0x140040c58  jz      loc_140040D65
0x140040c5e  mov     rax, [rbx]
0x140040c61  lea     rdx, [rbp+var_18]
0x140040c65  mov     rcx, rbx
0x140040c68  mov     rax, [rax+10h]
0x140040c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040c71  lea     rdx, aStatename; "StateName"
0x140040c78  mov     rcx, r14; hKey
0x140040c7b  call    cs:__imp_RegDeleteValueW
0x140040c81  mov     rcx, [rbp+18h]; this
0x140040c85  test    eax, eax
0x140040c87  jnz     loc_140040D77
0x140040c8d  mov     [rbp+var_30], 3
0x140040c94  mov     rax, [rbx]
0x140040c97  mov     edx, 1
0x140040c9c  mov     rcx, rbx
0x140040c9f  mov     rax, [rax]
0x140040ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040ca7  mov     r14, [rdi+18h]
0x140040cab  test    r14, r14
0x140040cae  jz      short loc_140040CC9
0x140040cb0  call    cs:__imp_GetLastError
0x140040cb6  mov     ebx, eax
0x140040cb8  mov     rcx, r14; hKey
0x140040cbb  call    cs:__imp_RegCloseKey
0x140040cc1  mov     ecx, ebx; dwErrCode
0x140040cc3  call    cs:__imp_SetLastError
0x140040cc9  mov     qword ptr [rdi+18h], 0
0x140040cd1  mov     rax, [rdi]
0x140040cd4  mov     rcx, rdi
0x140040cd7  mov     rax, [rax+70h]
0x140040cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040ce0  lea     r8, aContexts; "Contexts"
0x140040ce7  mov     rdx, [rdi+10h]; unsigned __int16 *
0x140040ceb  mov     rcx, [rdi+8]; this
0x140040cef  call    ?DeleteDynamicManagementRegistryTree@dmstd@@YAJPEBG00@Z; dmstd::DeleteDynamicManagementRegistryTree(ushort const *,ushort const *,ushort const *)
0x140040cf4  mov     r9d, eax
0x140040cf7  xor     eax, eax
0x140040cf9  cmp     r9d, 80070002h
0x140040d00  cmovz   r9d, eax; char *
0x140040d04  mov     rcx, [rbp+18h]; this
0x140040d08  test    r9d, r9d
0x140040d0b  js      short loc_140040D41
0x140040d0d  mov     rax, [rsi]
0x140040d10  mov     edx, 1
0x140040d15  mov     rcx, rsi
0x140040d18  mov     rax, [rax]
0x140040d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040d20  mov     rcx, [rbp+var_10]
0x140040d24  xor     rcx, rsp; StackCookie
0x140040d27  call    __security_check_cookie
0x140040d2c  lea     r11, [rsp+70h+var_s0]
0x140040d31  mov     rbx, [r11+28h]
0x140040d35  mov     rsi, [r11+30h]
0x140040d39  mov     rsp, r11
0x140040d3c  pop     r14
0x140040d3e  pop     rdi
0x140040d3f  pop     rbp
0x140040d40  retn
0x140040d41  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140040d48  mov     edx, 0BDh; void *
0x140040d4d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140040d53  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140040d5a  mov     edx, 18h; void *
0x140040d5f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140040d65  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140040d6c  mov     edx, 18h; void *
0x140040d71  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140040d77  mov     r9d, eax; char *
0x140040d7a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140040d81  mov     edx, 5Ch ; '\'; void *
0x140040d86  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
