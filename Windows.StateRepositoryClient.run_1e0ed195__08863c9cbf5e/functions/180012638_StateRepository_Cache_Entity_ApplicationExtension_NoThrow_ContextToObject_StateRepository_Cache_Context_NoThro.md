# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180012638`
- end: `0x180012846`
- name: `?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180012e10`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x18000b0b0`
- `0x18000b130`
- `0x180012638`
- `0x180013804`

## string_xrefs

- `0x18001266e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x18001281e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800127bb`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(
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

  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Application", (unsigned int *)(a2 + 8));
  if ( Field < 0 )
  {
    v8 = 974;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)Field,
      (int)v12);
    return (unsigned int)Field;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Index", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v8 = 978;
    goto LABEL_3;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  if ( Field < 0 )
  {
    v8 = 982;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 24);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Category", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 986;
    goto LABEL_3;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 32));
  if ( Field < 0 )
  {
    v8 = 990;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 40);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 994;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 48);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 998;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 56);
  v14 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v12);
  if ( Field < 0 )
  {
    v8 = 1002;
    goto LABEL_3;
  }
  v13 = 0;
  v12 = (__int64 *)(a2 + 64);
  v14 = 1;
  v11 = StateRepository::Cache::Context_NoThrow::GetField(a1, v10, (unsigned int *)(a2 + 72), (unsigned __int8 **)&v13);
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
      (void *)0x3EE,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v11,
      (int)v12);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x180012638  push    rbp
0x18001263a  push    rbx
0x18001263b  push    rsi
0x18001263c  push    rdi
0x18001263d  push    r14
0x18001263f  mov     rbp, rsp
0x180012642  sub     rsp, 40h
0x180012646  mov     rbx, rdx
0x180012649  lea     r8, [rdx+8]; unsigned int *
0x18001264d  lea     rdx, aApplication; "Application"
0x180012654  mov     r14, r9
0x180012657  mov     rdi, rcx
0x18001265a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x18001265f  mov     esi, eax
0x180012661  test    eax, eax
0x180012663  jns     short loc_180012684
0x180012665  mov     edx, 3CEh; void *
0x18001266a  mov     rcx, [rbp+28h]; this
0x18001266e  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180012675  mov     r9d, esi; char *
0x180012678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001267d  mov     eax, esi
0x18001267f  jmp     loc_18001283B
0x180012684  lea     r8, [rbx+10h]; unsigned int *
0x180012688  mov     rcx, rdi; this
0x18001268b  lea     rdx, aIndex; "Index"
0x180012692  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180012697  mov     esi, eax
0x180012699  test    eax, eax
0x18001269b  jns     short loc_1800126A4
0x18001269d  mov     edx, 3D2h
0x1800126a2  jmp     short loc_18001266A
0x1800126a4  lea     r8, [rbx+14h]; unsigned int *
0x1800126a8  mov     rcx, rdi; this
0x1800126ab  lea     rdx, aFlags; "Flags"
0x1800126b2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800126b7  mov     esi, eax
0x1800126b9  test    eax, eax
0x1800126bb  jns     short loc_1800126C4
0x1800126bd  mov     edx, 3D6h
0x1800126c2  jmp     short loc_18001266A
0x1800126c4  lea     rax, [rbx+18h]
0x1800126c8  mov     [rbp+var_18], 0
0x1800126d0  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800126d4  mov     [rbp+var_20], rax
0x1800126d8  lea     rdx, aCategory; "Category"
0x1800126df  mov     [rbp+var_10], 1
0x1800126e3  mov     rcx, rdi; this
0x1800126e6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800126eb  lea     rcx, [rbp+var_20]
0x1800126ef  mov     esi, eax
0x1800126f1  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800126f6  test    esi, esi
0x1800126f8  jns     short loc_180012704
0x1800126fa  mov     edx, 3DAh
0x1800126ff  jmp     loc_18001266A
0x180012704  lea     r8, [rbx+20h]; unsigned int *
0x180012708  mov     rcx, rdi; this
0x18001270b  lea     rdx, aActivation; "Activation"
0x180012712  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180012717  mov     esi, eax
0x180012719  test    eax, eax
0x18001271b  jns     short loc_180012727
0x18001271d  mov     edx, 3DEh
0x180012722  jmp     loc_18001266A
0x180012727  lea     rax, [rbx+28h]
0x18001272b  mov     [rbp+var_18], 0
0x180012733  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180012737  mov     [rbp+var_20], rax
0x18001273b  lea     rdx, aHostid; "HostId"
0x180012742  mov     [rbp+var_10], 1
0x180012746  mov     rcx, rdi; this
0x180012749  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001274e  lea     rcx, [rbp+var_20]
0x180012752  mov     esi, eax
0x180012754  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012759  test    esi, esi
0x18001275b  jns     short loc_180012767
0x18001275d  mov     edx, 3E2h
0x180012762  jmp     loc_18001266A
0x180012767  lea     rax, [rbx+30h]
0x18001276b  mov     [rbp+var_18], 0
0x180012773  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180012777  mov     [rbp+var_20], rax
0x18001277b  lea     rdx, aParameters; "Parameters"
0x180012782  mov     [rbp+var_10], 1
0x180012786  mov     rcx, rdi; this
0x180012789  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18001278e  lea     rcx, [rbp+var_20]
0x180012792  mov     esi, eax
0x180012794  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012799  test    esi, esi
0x18001279b  jns     short loc_1800127A7
0x18001279d  mov     edx, 3E6h
0x1800127a2  jmp     loc_18001266A
0x1800127a7  lea     rax, [rbx+38h]
0x1800127ab  mov     [rbp+var_18], 0
0x1800127b3  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800127b7  mov     [rbp+var_20], rax
0x1800127bb  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x1800127c2  mov     [rbp+var_10], 1
0x1800127c6  mov     rcx, rdi; this
0x1800127c9  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x1800127ce  lea     rcx, [rbp+var_20]
0x1800127d2  mov     esi, eax
0x1800127d4  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800127d9  test    esi, esi
0x1800127db  jns     short loc_1800127E7
0x1800127dd  mov     edx, 3EAh
0x1800127e2  jmp     loc_18001266A
0x1800127e7  lea     rax, [rbx+40h]
0x1800127eb  mov     [rbp+var_18], 0
0x1800127f3  lea     r8, [rbx+48h]; unsigned int *
0x1800127f7  mov     [rbp+var_20], rax
0x1800127fb  lea     r9, [rbp+var_18]; unsigned __int8 **
0x1800127ff  mov     [rbp+var_10], 1
0x180012803  mov     rcx, rdi; this
0x180012806  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAIPEAPEAE@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &,uchar * *)
0x18001280b  lea     rcx, [rbp+var_20]
0x18001280f  mov     edi, eax
0x180012811  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180012816  test    edi, edi
0x180012818  jns     short loc_180012836
0x18001281a  mov     rcx, [rbp+28h]; this
0x18001281e  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180012825  mov     r9d, edi; char *
0x180012828  mov     edx, 3EEh; void *
0x18001282d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012832  mov     eax, edi
0x180012834  jmp     short loc_18001283B
0x180012836  mov     [rbx], r14
0x180012839  xor     eax, eax
0x18001283b  add     rsp, 40h
0x18001283f  pop     r14
0x180012841  pop     rdi
0x180012842  pop     rsi
0x180012843  pop     rbx
0x180012844  pop     rbp
0x180012845  retn
```
