# StateRepository::WinRT::DataAccessLayer::User::GetUserSidAsSecurityIdentifierFromUser(Windows::Internal::StateRepository::IUser *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18000da98`
- end: `0x18000dbe6`
- name: `?GetUserSidAsSecurityIdentifierFromUser@User@DataAccessLayer@WinRT@StateRepository@@SAJPEAUIUser@4Internal@Windows@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e050`
- `0x180089d20`
- `0x18008cdd0`
- `0x18008ebb0`
- `0x18017fbe0`

## callees

- `0x18000da98`
- `0x18000e694`
- `0x18001a9e0`
- `0x1800af2d0`
- `0x1800af2f0`
- `0x18019914d`
- `0x18027e010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000dad2`
- `ntdll!RtlLengthSid` at `0x18000dad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000db9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dadd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::WinRT::DataAccessLayer::User::GetUserSidAsSecurityIdentifierFromUser(
        __int64 a1,
        int *a2)
{
  int v3; // eax
  unsigned int v4; // edi
  SIZE_T v5; // r14
  void *v6; // rdi
  void *v7; // rbp
  __int64 v8; // r9
  __int64 v9; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  PSID Sid; // [rsp+50h] [rbp+8h] BYREF
  char v16; // [rsp+58h] [rbp+10h] BYREF

  *(_QWORD *)a2 = 0;
  if ( a1 )
  {
    LODWORD(Sid) = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, PSID *, int *))(*(_QWORD *)a1 + 88LL))(a1, &Sid, a2);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\dal-user.cpp",
        (const char *)(unsigned int)v11,
        v13);
      return v12;
    }
  }
  else
  {
    Sid = 0;
    v3 = StateRepository::AutoCoSid::FromCaller((StateRepository::AutoCoSid *)&Sid);
    v4 = v3;
    if ( v3 < 0 )
    {
      v8 = (unsigned int)v3;
      v9 = 82;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\dal-user.cpp",
        (const char *)v8,
        v13);
      LocalFree(Sid);
      return v4;
    }
    v5 = RtlLengthSid(Sid);
    v6 = CoTaskMemAlloc(v5);
    if ( a2 == &v13 )
    {
      if ( v6 )
        CoTaskMemFree(v6);
    }
    else
    {
      v7 = *(void **)a2;
      if ( *(_QWORD *)a2 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
        CoTaskMemFree(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
      }
      *(_QWORD *)a2 = v6;
    }
    if ( !*(_QWORD *)a2 )
    {
      v4 = -2147024882;
      v8 = 2147942414LL;
      v9 = 87;
      goto LABEL_8;
    }
    memcpy_0(*(void **)a2, Sid, v5);
    LocalFree(Sid);
  }
  return 0;
}

```

## disassembly

```asm
0x18000da98  mov     [rsp+arg_10], rbx
0x18000da9d  push    rbp
0x18000da9e  push    rdi
0x18000da9f  push    r14
0x18000daa1  sub     rsp, 30h
0x18000daa5  mov     rbx, rdx
0x18000daa8  mov     qword ptr [rdx], 0
0x18000daaf  test    rcx, rcx
0x18000dab2  jnz     loc_18000DB4C
0x18000dab8  mov     [rsp+48h+Sid], rcx
0x18000dabd  lea     rcx, [rsp+48h+Sid]; this
0x18000dac2  call    ?FromCaller@AutoCoSid@StateRepository@@QEAAJXZ; StateRepository::AutoCoSid::FromCaller(void)
0x18000dac7  mov     edi, eax
0x18000dac9  test    eax, eax
0x18000dacb  js      short loc_18000DB08
0x18000dacd  mov     rcx, [rsp+48h+Sid]; Sid
0x18000dad2  call    cs:__imp_RtlLengthSid
0x18000dad8  mov     r14d, eax
0x18000dadb  mov     ecx, eax; cb
0x18000dadd  call    cs:__imp_CoTaskMemAlloc
0x18000dae3  mov     rdi, rax
0x18000dae6  lea     rax, [rsp+48h+var_28]
0x18000daeb  cmp     rbx, rax
0x18000daee  jz      loc_18000DBA8
0x18000daf4  mov     rbp, [rbx]
0x18000daf7  test    rbp, rbp
0x18000dafa  jnz     loc_18000DBC3
0x18000db00  mov     [rbx], rdi
0x18000db03  jmp     loc_18000DBB6
0x18000db08  mov     r9d, eax
0x18000db0b  mov     edx, 52h ; 'R'
0x18000db10  jmp     short loc_18000DB1F
0x18000db12  mov     edi, 8007000Eh
0x18000db17  mov     r9d, edi; char *
0x18000db1a  mov     edx, 57h ; 'W'; void *
0x18000db1f  lea     r8, aOnecoreBaseApp_114; "onecore\\base\\appmodel\\staterepositor"...
0x18000db26  mov     rcx, [rsp+48h]; this
0x18000db2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db30  nop
0x18000db31  mov     rcx, [rsp+48h+Sid]; hMem
0x18000db36  call    cs:__imp_LocalFree
0x18000db3c  mov     eax, edi
0x18000db3e  mov     rbx, [rsp+48h+arg_10]
0x18000db43  add     rsp, 30h
0x18000db47  pop     r14
0x18000db49  pop     rdi
0x18000db4a  pop     rbp
0x18000db4b  retn
0x18000db4c  mov     dword ptr [rsp+48h+Sid], 0
0x18000db54  mov     rax, [rcx]
0x18000db57  mov     r8, rbx
0x18000db5a  lea     rdx, [rsp+48h+Sid]
0x18000db5f  mov     rax, [rax+58h]
0x18000db63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db68  mov     ebx, eax
0x18000db6a  test    eax, eax
0x18000db6c  jns     short loc_18000DBA4
0x18000db6e  mov     rcx, [rsp+48h]; this
0x18000db73  mov     r9d, eax; char *
0x18000db76  lea     r8, aOnecoreBaseApp_114; "onecore\\base\\appmodel\\staterepositor"...
0x18000db7d  mov     edx, 4Ch ; 'L'; void *
0x18000db82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db87  mov     eax, ebx
0x18000db89  jmp     short loc_18000DB3E
0x18000db8b  mov     r8, r14; Size
0x18000db8e  mov     rdx, [rsp+48h+Sid]; Src
0x18000db93  call    memcpy_0
0x18000db98  nop
0x18000db99  mov     rcx, [rsp+48h+Sid]; hMem
0x18000db9e  call    cs:__imp_LocalFree
0x18000dba4  xor     eax, eax
0x18000dba6  jmp     short loc_18000DB3E
0x18000dba8  test    rdi, rdi
0x18000dbab  jz      short loc_18000DBB6
0x18000dbad  mov     rcx, rdi; pv
0x18000dbb0  call    cs:__imp_CoTaskMemFree
0x18000dbb6  mov     rcx, [rbx]; void *
0x18000dbb9  test    rcx, rcx
0x18000dbbc  jnz     short loc_18000DB8B
0x18000dbbe  jmp     loc_18000DB12
0x18000dbc3  lea     rcx, [rsp+48h+arg_8]; this
0x18000dbc8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dbcd  mov     rcx, rbp; pv
0x18000dbd0  call    cs:__imp_CoTaskMemFree
0x18000dbd6  lea     rcx, [rsp+48h+arg_8]; this
0x18000dbdb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dbe0  jmp     loc_18000DB00
```
