# CMitigationClassFactory::OnClientStubDestroyed(IUnknown *)

- ea: `0x180017760`
- end: `0x180017821`
- name: `?OnClientStubDestroyed@CMitigationClassFactory@@UEAAJPEAUIUnknown@@@Z`
- size: `193`
- prototype: `int(CMitigationClassFactory *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cdb5`
- `0x18000ea68`
- `0x18000f6a8`
- `0x18001208c`
- `0x180017760`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x18001777a`
- `combase!__imp_CoReleaseSharedService` at `0x18001777a`

## string_xrefs

- `0x1800177fb`: `onecore\base\diagnosis\mitigation\client\dll\mitigationclassfactory.cpp`

## pseudocode

```c
__int64 __fastcall CMitigationClassFactory::OnClientStubDestroyed(CMitigationClassFactory *this, struct IUnknown *a2)
{
  unsigned __int64 i; // rcx
  struct IUnknown **v5; // r9
  unsigned __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v12; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180080AB8 )
    CoReleaseSharedService();
  _InterlockedDecrement((volatile signed __int32 *)&g_clientCount);
  wil::EnterCriticalSection(&v12, (char *)this + 40);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_QWORD *)this + 11) )
    {
      v7 = -2147023728;
      v8 = 105;
      goto LABEL_13;
    }
    v5 = (struct IUnknown **)(*((_QWORD *)this + 10) + 8 * i);
    if ( *v5 == a2 )
      break;
  }
  v6 = *((_QWORD *)this + 11);
  if ( i >= v6 )
  {
    v7 = -2147316575;
    v8 = 101;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\mitigationclassfactory.cpp",
      (const char *)v7,
      v10);
    goto LABEL_14;
  }
  if ( i != v6 - 1 )
    memmove_0(v5, v5 + 1, 8 * (v6 - i) - 8);
  --*((_QWORD *)this + 11);
  v7 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180017760  mov     [rsp+arg_8], rbx
0x180017765  push    rdi; int
0x180017766  sub     rsp, 20h
0x18001776a  mov     rbx, rcx
0x18001776d  mov     rdi, rdx
0x180017770  mov     ecx, cs:dword_180080AB8
0x180017776  test    ecx, ecx
0x180017778  jz      short loc_180017780
0x18001777a  call    cs:__imp_CoReleaseSharedService
0x180017780  lock dec cs:?g_clientCount@@3KC; ulong volatile g_clientCount
0x180017787  lea     rdx, [rbx+28h]
0x18001778b  lea     rcx, [rsp+28h+arg_0]
0x180017790  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180017795  xor     ecx, ecx
0x180017797  cmp     rcx, [rbx+58h]
0x18001779b  jnb     short loc_1800177EC
0x18001779d  mov     rax, [rbx+50h]
0x1800177a1  lea     r9, [rax+rcx*8]
0x1800177a5  cmp     [r9], rdi
0x1800177a8  jz      short loc_1800177AF
0x1800177aa  inc     rcx
0x1800177ad  jmp     short loc_180017797
0x1800177af  mov     r8, [rbx+58h]
0x1800177b3  cmp     rcx, r8
0x1800177b6  jb      short loc_1800177C4
0x1800177b8  mov     ebx, 80028CA1h
0x1800177bd  mov     edx, 65h ; 'e'
0x1800177c2  jmp     short loc_1800177F6
0x1800177c4  lea     rax, [r8-1]
0x1800177c8  cmp     rcx, rax
0x1800177cb  jz      short loc_1800177E4
0x1800177cd  sub     r8, rcx
0x1800177d0  lea     rdx, [r9+8]; Src
0x1800177d4  mov     rcx, r9; void *
0x1800177d7  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x1800177df  call    memmove_0
0x1800177e4  dec     qword ptr [rbx+58h]
0x1800177e8  xor     ebx, ebx
0x1800177ea  jmp     short loc_18001780A
0x1800177ec  mov     ebx, 80070490h
0x1800177f1  mov     edx, 69h ; 'i'; void *
0x1800177f6  mov     rcx, [rsp+28h]; this
0x1800177fb  lea     r8, aOnecoreBaseDia_37; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180017802  mov     r9d, ebx; char *
0x180017805  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001780a  lea     rcx, [rsp+28h+arg_0]
0x18001780f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180017814  mov     eax, ebx
0x180017816  mov     rbx, [rsp+28h+arg_8]
0x18001781b  add     rsp, 20h
0x18001781f  pop     rdi
0x180017820  retn
```
