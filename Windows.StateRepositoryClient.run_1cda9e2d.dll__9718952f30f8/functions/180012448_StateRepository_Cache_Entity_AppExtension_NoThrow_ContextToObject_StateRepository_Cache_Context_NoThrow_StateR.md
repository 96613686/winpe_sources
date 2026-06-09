# StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180012448`
- end: `0x180012630`
- name: `?ContextToObject@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180012d30`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x18000b0b0`
- `0x18000b130`
- `0x180012448`
- `0x180013804`

## string_xrefs

- `0x18001249b`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180012608`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x1800125b5`: `Extension`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v11,
      (int)v12);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x180012448  push    rbp
0x18001244a  push    rbx
0x18001244b  push    rsi
0x18001244c  push    rdi
0x18001244d  push    r14
0x18001244f  mov     rbp, rsp
0x180012452  sub     rsp, 40h
0x180012456  lea     rax, [rdx+8]
0x18001245a  mov     [rbp+var_18], 0
0x180012462  mov     rbx, rdx
0x180012465  mov     [rbp+var_20], rax
0x180012469  lea     rdx, aName; "Name"
0x180012470  mov     [rbp+var_10], 1
0x180012474  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180012478  mov     r14, r9
0x18001247b  mov     rdi, rcx
0x18001247e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180012483  lea     rcx, [rbp+var_20]
0x180012487  mov     esi, eax
0x180012489  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18001248e  test    esi, esi
0x180012490  jns     short loc_1800124B1
0x180012492  mov     edx, 2CEh; void *
0x180012497  mov     rcx, [rbp+28h]; this
0x18001249b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x1800124a2  mov     r9d, esi; char *
0x1800124a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800124aa  mov     eax, esi
0x1800124ac  jmp     loc_180012625
0x1800124b1  lea     rax, [rbx+10h]
0x1800124b5  mov     [rbp+var_18], 0
0x1800124bd  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800124c1  mov     [rbp+var_20], rax
0x1800124c5  lea     rdx, aId; "Id"
0x1800124cc  mov     [rbp+var_10], 1
0x1800124d0  mov     rcx, rdi; this
0x1800124d3  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800124d8  lea     rcx, [rbp+var_20]
0x1800124dc  mov     esi, eax
0x1800124de  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800124e3  test    esi, esi
0x1800124e5  jns     short loc_1800124EE
0x1800124e7  mov     edx, 2D2h
0x1800124ec  jmp     short loc_180012497
0x1800124ee  lea     rax, [rbx+18h]
0x1800124f2  mov     [rbp+var_18], 0
0x1800124fa  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800124fe  mov     [rbp+var_20], rax
0x180012502  lea     rdx, aPublicfolder; "PublicFolder"
0x180012509  mov     [rbp+var_10], 1
0x18001250d  mov     rcx, rdi; this
0x180012510  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180012515  lea     rcx, [rbp+var_20]
0x180012519  mov     esi, eax
0x18001251b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012520  test    esi, esi
0x180012522  jns     short loc_18001252E
0x180012524  mov     edx, 2D6h
0x180012529  jmp     loc_180012497
0x18001252e  lea     rax, [rbx+20h]
0x180012532  mov     [rbp+var_18], 0
0x18001253a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001253e  mov     [rbp+var_20], rax
0x180012542  lea     rdx, aDisplayname; "DisplayName"
0x180012549  mov     [rbp+var_10], 1
0x18001254d  mov     rcx, rdi; this
0x180012550  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180012555  lea     rcx, [rbp+var_20]
0x180012559  mov     esi, eax
0x18001255b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012560  test    esi, esi
0x180012562  jns     short loc_18001256E
0x180012564  mov     edx, 2DAh
0x180012569  jmp     loc_180012497
0x18001256e  lea     rax, [rbx+28h]
0x180012572  mov     [rbp+var_18], 0
0x18001257a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18001257e  mov     [rbp+var_20], rax
0x180012582  lea     rdx, aDescription; "Description"
0x180012589  mov     [rbp+var_10], 1
0x18001258d  mov     rcx, rdi; this
0x180012590  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180012595  lea     rcx, [rbp+var_20]
0x180012599  mov     esi, eax
0x18001259b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800125a0  test    esi, esi
0x1800125a2  jns     short loc_1800125AE
0x1800125a4  mov     edx, 2DEh
0x1800125a9  jmp     loc_180012497
0x1800125ae  lea     r8, [rbx+30h]; unsigned int *
0x1800125b2  mov     rcx, rdi; this
0x1800125b5  lea     rdx, aExtension; "Extension"
0x1800125bc  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800125c1  mov     esi, eax
0x1800125c3  test    eax, eax
0x1800125c5  jns     short loc_1800125D1
0x1800125c7  mov     edx, 2E2h
0x1800125cc  jmp     loc_180012497
0x1800125d1  lea     rax, [rbx+38h]
0x1800125d5  mov     [rbp+var_18], 0
0x1800125dd  lea     r8, [rbx+40h]; unsigned int *
0x1800125e1  mov     [rbp+var_20], rax
0x1800125e5  lea     r9, [rbp+var_18]; unsigned __int8 **
0x1800125e9  mov     [rbp+var_10], 1
0x1800125ed  mov     rcx, rdi; this
0x1800125f0  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAIPEAPEAE@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &,uchar * *)
0x1800125f5  lea     rcx, [rbp+var_20]
0x1800125f9  mov     edi, eax
0x1800125fb  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012600  test    edi, edi
0x180012602  jns     short loc_180012620
0x180012604  mov     rcx, [rbp+28h]; this
0x180012608  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x18001260f  mov     r9d, edi; char *
0x180012612  mov     edx, 2E6h; void *
0x180012617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001261c  mov     eax, edi
0x18001261e  jmp     short loc_180012625
0x180012620  mov     [rbx], r14
0x180012623  xor     eax, eax
0x180012625  add     rsp, 40h
0x180012629  pop     r14
0x18001262b  pop     rdi
0x18001262c  pop     rsi
0x18001262d  pop     rbx
0x18001262e  pop     rbp
0x18001262f  retn
```
