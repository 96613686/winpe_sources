# StateRepository::Cache::Entity::PackageExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,__int64)

- ea: `0x180016da0`
- end: `0x180016f71`
- name: `?ContextToObject@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800172f4`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x18000b0b0`
- `0x18000b130`
- `0x180016da0`

## string_xrefs

- `0x180016f23`: `CurrentDirectoryPath`
- `0x180016dd6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`
- `0x180016f49`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // esi
  __int64 v8; // rdx
  int v10; // edi
  __int64 *v11; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v12; // [rsp+28h] [rbp-18h] BYREF
  char v13; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Package", (unsigned int *)(a2 + 8));
  if ( Field < 0 )
  {
    v8 = 925;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)Field,
      (int)v11);
    return (unsigned int)Field;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Index", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v8 = 929;
    goto LABEL_3;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  if ( Field < 0 )
  {
    v8 = 933;
    goto LABEL_3;
  }
  v12 = 0;
  v11 = (__int64 *)(a2 + 24);
  v13 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Category", &v12);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v11);
  if ( Field < 0 )
  {
    v8 = 937;
    goto LABEL_3;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 32));
  if ( Field < 0 )
  {
    v8 = 941;
    goto LABEL_3;
  }
  v12 = 0;
  v11 = (__int64 *)(a2 + 40);
  v13 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v12);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v11);
  if ( Field < 0 )
  {
    v8 = 945;
    goto LABEL_3;
  }
  v12 = 0;
  v11 = (__int64 *)(a2 + 48);
  v13 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v12);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v11);
  if ( Field < 0 )
  {
    v8 = 949;
    goto LABEL_3;
  }
  v12 = 0;
  v11 = (__int64 *)(a2 + 56);
  v13 = 1;
  v10 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"CurrentDirectoryPath", &v12);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v11);
  if ( v10 >= 0 )
  {
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v10,
      (int)v11);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180016da0  push    rbp
0x180016da2  push    rbx
0x180016da3  push    rsi
0x180016da4  push    rdi
0x180016da5  push    r14
0x180016da7  mov     rbp, rsp
0x180016daa  sub     rsp, 40h
0x180016dae  mov     rbx, rdx
0x180016db1  lea     r8, [rdx+8]; unsigned int *
0x180016db5  lea     rdx, aPackage; "Package"
0x180016dbc  mov     r14, r9
0x180016dbf  mov     rdi, rcx
0x180016dc2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180016dc7  mov     esi, eax
0x180016dc9  test    eax, eax
0x180016dcb  jns     short loc_180016DEC
0x180016dcd  mov     edx, 39Dh; void *
0x180016dd2  mov     rcx, [rbp+28h]; this
0x180016dd6  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x180016ddd  mov     r9d, esi; char *
0x180016de0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016de5  mov     eax, esi
0x180016de7  jmp     loc_180016F66
0x180016dec  lea     r8, [rbx+10h]; unsigned int *
0x180016df0  mov     rcx, rdi; this
0x180016df3  lea     rdx, aIndex; "Index"
0x180016dfa  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180016dff  mov     esi, eax
0x180016e01  test    eax, eax
0x180016e03  jns     short loc_180016E0C
0x180016e05  mov     edx, 3A1h
0x180016e0a  jmp     short loc_180016DD2
0x180016e0c  lea     r8, [rbx+14h]; unsigned int *
0x180016e10  mov     rcx, rdi; this
0x180016e13  lea     rdx, aFlags; "Flags"
0x180016e1a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180016e1f  mov     esi, eax
0x180016e21  test    eax, eax
0x180016e23  jns     short loc_180016E2C
0x180016e25  mov     edx, 3A5h
0x180016e2a  jmp     short loc_180016DD2
0x180016e2c  lea     rax, [rbx+18h]
0x180016e30  mov     [rbp+var_18], 0
0x180016e38  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016e3c  mov     [rbp+var_20], rax
0x180016e40  lea     rdx, aCategory; "Category"
0x180016e47  mov     [rbp+var_10], 1
0x180016e4b  mov     rcx, rdi; this
0x180016e4e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180016e53  lea     rcx, [rbp+var_20]
0x180016e57  mov     esi, eax
0x180016e59  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180016e5e  test    esi, esi
0x180016e60  jns     short loc_180016E6C
0x180016e62  mov     edx, 3A9h
0x180016e67  jmp     loc_180016DD2
0x180016e6c  lea     r8, [rbx+20h]; unsigned int *
0x180016e70  mov     rcx, rdi; this
0x180016e73  lea     rdx, aActivation; "Activation"
0x180016e7a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180016e7f  mov     esi, eax
0x180016e81  test    eax, eax
0x180016e83  jns     short loc_180016E8F
0x180016e85  mov     edx, 3ADh
0x180016e8a  jmp     loc_180016DD2
0x180016e8f  lea     rax, [rbx+28h]
0x180016e93  mov     [rbp+var_18], 0
0x180016e9b  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016e9f  mov     [rbp+var_20], rax
0x180016ea3  lea     rdx, aHostid; "HostId"
0x180016eaa  mov     [rbp+var_10], 1
0x180016eae  mov     rcx, rdi; this
0x180016eb1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180016eb6  lea     rcx, [rbp+var_20]
0x180016eba  mov     esi, eax
0x180016ebc  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180016ec1  test    esi, esi
0x180016ec3  jns     short loc_180016ECF
0x180016ec5  mov     edx, 3B1h
0x180016eca  jmp     loc_180016DD2
0x180016ecf  lea     rax, [rbx+30h]
0x180016ed3  mov     [rbp+var_18], 0
0x180016edb  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016edf  mov     [rbp+var_20], rax
0x180016ee3  lea     rdx, aParameters; "Parameters"
0x180016eea  mov     [rbp+var_10], 1
0x180016eee  mov     rcx, rdi; this
0x180016ef1  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180016ef6  lea     rcx, [rbp+var_20]
0x180016efa  mov     esi, eax
0x180016efc  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180016f01  test    esi, esi
0x180016f03  jns     short loc_180016F0F
0x180016f05  mov     edx, 3B5h
0x180016f0a  jmp     loc_180016DD2
0x180016f0f  lea     rax, [rbx+38h]
0x180016f13  mov     [rbp+var_18], 0
0x180016f1b  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180016f1f  mov     [rbp+var_20], rax
0x180016f23  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x180016f2a  mov     [rbp+var_10], 1
0x180016f2e  mov     rcx, rdi; this
0x180016f31  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180016f36  lea     rcx, [rbp+var_20]
0x180016f3a  mov     edi, eax
0x180016f3c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180016f41  test    edi, edi
0x180016f43  jns     short loc_180016F61
0x180016f45  mov     rcx, [rbp+28h]; this
0x180016f49  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x180016f50  mov     r9d, edi; char *
0x180016f53  mov     edx, 3B9h; void *
0x180016f58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f5d  mov     eax, edi
0x180016f5f  jmp     short loc_180016F66
0x180016f61  mov     [rbx], r14
0x180016f64  xor     eax, eax
0x180016f66  add     rsp, 40h
0x180016f6a  pop     r14
0x180016f6c  pop     rdi
0x180016f6d  pop     rsi
0x180016f6e  pop     rbx
0x180016f6f  pop     rbp
0x180016f70  retn
```
