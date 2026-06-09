# StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180016f78`
- end: `0x180017160`
- name: `?ContextToObject@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001749c`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x18000b0b0`
- `0x18000b130`
- `0x180013804`
- `0x180016f78`

## string_xrefs

- `0x1800170e5`: `Extension`
- `0x180016fcb`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017138`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // esi
  __int64 v8; // rdx
  const unsigned __int16 *v10; // rdx
  int v11; // edi
  __int64 *v12; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-18h] BYREF
  char v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v13 = 0;
  v12 = (__int64 *)(a2 + 8);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Name", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 718;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)Field,
      (int)v12);
    return (unsigned int)Field;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 16);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Id", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 722;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 24);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PublicFolder", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 726;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 32);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"DisplayName", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 730;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 40);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Description", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 734;
    goto LABEL_3;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Extension", (unsigned int *)(a2 + 48));
  if ( Field < 0 )
  {
    v8 = 738;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 56);
  v14 = 1;
  v11 = StateRepository::Cache::Context_NoThrow::GetField(a1, v10, (unsigned int *)(a2 + 64), (unsigned __int8 **)&v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( v11 >= 0 )
  {
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v11,
      (int)v12);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x180016f78  push    rbp
0x180016f7a  push    rbx
0x180016f7b  push    rsi
0x180016f7c  push    rdi
0x180016f7d  push    r14
0x180016f7f  mov     rbp, rsp
0x180016f82  sub     rsp, 40h
0x180016f86  lea     rax, [rdx+8]
0x180016f8a  mov     [rbp+var_18], 0
0x180016f92  mov     rbx, rdx
0x180016f95  mov     [rbp+var_20], rax
0x180016f99  lea     rdx, aName; "Name"
0x180016fa0  mov     [rbp+var_10], 1
0x180016fa4  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016fa8  mov     r14, r9
0x180016fab  mov     rdi, rcx
0x180016fae  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180016fb3  lea     rcx, [rbp+var_20]
0x180016fb7  mov     esi, eax
0x180016fb9  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180016fbe  test    esi, esi
0x180016fc0  jns     short loc_180016FE1
0x180016fc2  mov     edx, 2CEh; void *
0x180016fc7  mov     rcx, [rbp+28h]; this
0x180016fcb  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180016fd2  mov     r9d, esi; char *
0x180016fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fda  mov     eax, esi
0x180016fdc  jmp     loc_180017155
0x180016fe1  lea     rax, [rbx+10h]
0x180016fe5  mov     [rbp+var_18], 0
0x180016fed  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016ff1  mov     [rbp+var_20], rax
0x180016ff5  lea     rdx, aId; "Id"
0x180016ffc  mov     [rbp+var_10], 1
0x180017000  mov     rcx, rdi; this
0x180017003  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180017008  lea     rcx, [rbp+var_20]
0x18001700c  mov     esi, eax
0x18001700e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017013  test    esi, esi
0x180017015  jns     short loc_18001701E
0x180017017  mov     edx, 2D2h
0x18001701c  jmp     short loc_180016FC7
0x18001701e  lea     rax, [rbx+18h]
0x180017022  mov     [rbp+var_18], 0
0x18001702a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001702e  mov     [rbp+var_20], rax
0x180017032  lea     rdx, aPublicfolder; "PublicFolder"
0x180017039  mov     [rbp+var_10], 1
0x18001703d  mov     rcx, rdi; this
0x180017040  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180017045  lea     rcx, [rbp+var_20]
0x180017049  mov     esi, eax
0x18001704b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017050  test    esi, esi
0x180017052  jns     short loc_18001705E
0x180017054  mov     edx, 2D6h
0x180017059  jmp     loc_180016FC7
0x18001705e  lea     rax, [rbx+20h]
0x180017062  mov     [rbp+var_18], 0
0x18001706a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001706e  mov     [rbp+var_20], rax
0x180017072  lea     rdx, aDisplayname; "DisplayName"
0x180017079  mov     [rbp+var_10], 1
0x18001707d  mov     rcx, rdi; this
0x180017080  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180017085  lea     rcx, [rbp+var_20]
0x180017089  mov     esi, eax
0x18001708b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017090  test    esi, esi
0x180017092  jns     short loc_18001709E
0x180017094  mov     edx, 2DAh
0x180017099  jmp     loc_180016FC7
0x18001709e  lea     rax, [rbx+28h]
0x1800170a2  mov     [rbp+var_18], 0
0x1800170aa  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800170ae  mov     [rbp+var_20], rax
0x1800170b2  lea     rdx, aDescription; "Description"
0x1800170b9  mov     [rbp+var_10], 1
0x1800170bd  mov     rcx, rdi; this
0x1800170c0  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800170c5  lea     rcx, [rbp+var_20]
0x1800170c9  mov     esi, eax
0x1800170cb  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800170d0  test    esi, esi
0x1800170d2  jns     short loc_1800170DE
0x1800170d4  mov     edx, 2DEh
0x1800170d9  jmp     loc_180016FC7
0x1800170de  lea     r8, [rbx+30h]; unsigned int *
0x1800170e2  mov     rcx, rdi; this
0x1800170e5  lea     rdx, aExtension; "Extension"
0x1800170ec  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800170f1  mov     esi, eax
0x1800170f3  test    eax, eax
0x1800170f5  jns     short loc_180017101
0x1800170f7  mov     edx, 2E2h
0x1800170fc  jmp     loc_180016FC7
0x180017101  lea     rax, [rbx+38h]
0x180017105  mov     [rbp+var_18], 0
0x18001710d  lea     r8, [rbx+40h]; unsigned int *
0x180017111  mov     [rbp+var_20], rax
0x180017115  lea     r9, [rbp+var_18]; unsigned __int8 **
0x180017119  mov     [rbp+var_10], 1
0x18001711d  mov     rcx, rdi; this
0x180017120  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAIPEAPEAE@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &,uchar * *)
0x180017125  lea     rcx, [rbp+var_20]
0x180017129  mov     edi, eax
0x18001712b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180017130  test    edi, edi
0x180017132  jns     short loc_180017150
0x180017134  mov     rcx, [rbp+28h]; this
0x180017138  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x18001713f  mov     r9d, edi; char *
0x180017142  mov     edx, 2E6h; void *
0x180017147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001714c  mov     eax, edi
0x18001714e  jmp     short loc_180017155
0x180017150  mov     [rbx], r14
0x180017153  xor     eax, eax
0x180017155  add     rsp, 40h
0x180017159  pop     r14
0x18001715b  pop     rdi
0x18001715c  pop     rsi
0x18001715d  pop     rbx
0x18001715e  pop     rbp
0x18001715f  retn
```
