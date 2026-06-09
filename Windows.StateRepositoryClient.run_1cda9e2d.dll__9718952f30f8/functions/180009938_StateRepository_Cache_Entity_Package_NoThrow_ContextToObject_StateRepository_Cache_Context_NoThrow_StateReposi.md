# StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)

- ea: `0x180009938`
- end: `0x180009ca9`
- name: `?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a0d0`

## callees

- `0x1800075e4`
- `0x180009444`
- `0x180009938`
- `0x18000b0b0`
- `0x18000b0f0`
- `0x18000b130`

## string_xrefs

- `0x18000999c`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x180009c7f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x180009b0e`: `InstalledLocation`
- `0x180009b5c`: `MutableLink`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field; // r14d
  __int64 v9; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 *v13; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-20h] BYREF
  char v15; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_7;
  v14 = 0;
  v13 = (__int64 *)(a2 + 8);
  v15 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFullName", &v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
  if ( Field < 0 )
  {
    v9 = 2091;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)Field,
      (int)v13);
    return (unsigned int)Field;
  }
  if ( a3 )
  {
LABEL_7:
    if ( (a3 & 2) == 0 )
      goto LABEL_11;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageFamily", (unsigned int *)(a2 + 16));
  if ( Field < 0 )
  {
    v9 = 2095;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_11:
    if ( (a3 & 4) == 0 )
      goto LABEL_15;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageType", (unsigned int *)(a2 + 24));
  if ( Field < 0 )
  {
    v9 = 2099;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_15:
    if ( (a3 & 8) == 0 )
      goto LABEL_19;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 28));
  if ( Field < 0 )
  {
    v9 = 2103;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_19:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_23;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags2", (unsigned int *)(a2 + 32));
  if ( Field < 0 )
  {
    v9 = 2107;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_23:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_27;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"PackageOrigin", (unsigned int *)(a2 + 36));
  if ( Field < 0 )
  {
    v9 = 2111;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_27:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_31;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Volume", (unsigned int *)(a2 + 40));
  if ( Field < 0 )
  {
    v9 = 2115;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_31:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_35;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"OSMaxVersionTested", (unsigned __int64 *)(a2 + 48));
  if ( Field < 0 )
  {
    v9 = 2119;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_35:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_39;
  }
  v14 = 0;
  v13 = (__int64 *)(a2 + 56);
  v15 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"InstalledLocation", &v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
  if ( Field < 0 )
  {
    v9 = 2123;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_39:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_43;
  }
  v14 = 0;
  v13 = (__int64 *)(a2 + 64);
  v15 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLink", &v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
  if ( Field < 0 )
  {
    v9 = 2127;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_43:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_47;
  }
  v14 = 0;
  v13 = (__int64 *)(a2 + 72);
  v15 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"MutableLocation", &v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
  if ( Field < 0 )
  {
    v9 = 2131;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_47:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_51;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"TargetDeviceFamilyName", (unsigned int *)(a2 + 80));
  if ( Field < 0 )
  {
    v9 = 2135;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_51:
    if ( (a3 & 0x1000) == 0 )
      goto LABEL_55;
  }
  v14 = 0;
  v13 = (__int64 *)(a2 + 88);
  v15 = 1;
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"DisplayName", &v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v13);
  if ( Field < 0 )
  {
    v9 = 2139;
    goto LABEL_5;
  }
  if ( a3 )
  {
LABEL_55:
    if ( (a3 & 0x2000) == 0 )
      goto LABEL_58;
  }
  v11 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"SourceBundle", (unsigned int *)(a2 + 96));
  v12 = v11;
  if ( v11 >= 0 )
  {
LABEL_58:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x85F,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      (int)v13);
    return v12;
  }
}

```

## disassembly

```asm
0x180009938  push    rbp
0x18000993a  push    rbx
0x18000993b  push    rsi
0x18000993c  push    rdi
0x18000993d  push    r14
0x18000993f  push    r15
0x180009941  mov     rbp, rsp
0x180009944  sub     rsp, 48h
0x180009948  mov     r15, r9
0x18000994b  mov     rbx, r8
0x18000994e  mov     rdi, rdx
0x180009951  mov     rsi, rcx
0x180009954  test    r8, r8
0x180009957  jz      short loc_18000995E
0x180009959  test    bl, 1
0x18000995c  jz      short loc_1800099B8
0x18000995e  lea     rax, [rdx+8]
0x180009962  mov     [rbp+var_20], 0
0x18000996a  lea     rdx, aPackagefullnam; "PackageFullName"
0x180009971  mov     [rbp+var_28], rax
0x180009975  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180009979  mov     [rbp+var_18], 1
0x18000997d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009982  lea     rcx, [rbp+var_28]
0x180009986  mov     r14d, eax
0x180009989  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x18000998e  test    r14d, r14d
0x180009991  jns     short loc_1800099B3
0x180009993  mov     edx, 82Bh; void *
0x180009998  mov     rcx, [rbp+30h]; this
0x18000999c  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x1800099a3  mov     r9d, r14d; char *
0x1800099a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099ab  mov     eax, r14d
0x1800099ae  jmp     loc_180009C9C
0x1800099b3  test    rbx, rbx
0x1800099b6  jz      short loc_1800099BD
0x1800099b8  test    bl, 2
0x1800099bb  jz      short loc_1800099E3
0x1800099bd  lea     r8, [rdi+10h]; unsigned int *
0x1800099c1  mov     rcx, rsi; this
0x1800099c4  lea     rdx, aPackagefamily; "PackageFamily"
0x1800099cb  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800099d0  mov     r14d, eax
0x1800099d3  test    eax, eax
0x1800099d5  jns     short loc_1800099DE
0x1800099d7  mov     edx, 82Fh
0x1800099dc  jmp     short loc_180009998
0x1800099de  test    rbx, rbx
0x1800099e1  jz      short loc_1800099E8
0x1800099e3  test    bl, 4
0x1800099e6  jz      short loc_180009A0E
0x1800099e8  lea     r8, [rdi+18h]; unsigned int *
0x1800099ec  mov     rcx, rsi; this
0x1800099ef  lea     rdx, aPackagetype; "PackageType"
0x1800099f6  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800099fb  mov     r14d, eax
0x1800099fe  test    eax, eax
0x180009a00  jns     short loc_180009A09
0x180009a02  mov     edx, 833h
0x180009a07  jmp     short loc_180009998
0x180009a09  test    rbx, rbx
0x180009a0c  jz      short loc_180009A13
0x180009a0e  test    bl, 8
0x180009a11  jz      short loc_180009A3C
0x180009a13  lea     r8, [rdi+1Ch]; unsigned int *
0x180009a17  mov     rcx, rsi; this
0x180009a1a  lea     rdx, aFlags; "Flags"
0x180009a21  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009a26  mov     r14d, eax
0x180009a29  test    eax, eax
0x180009a2b  jns     short loc_180009A37
0x180009a2d  mov     edx, 837h
0x180009a32  jmp     loc_180009998
0x180009a37  test    rbx, rbx
0x180009a3a  jz      short loc_180009A41
0x180009a3c  test    bl, 10h
0x180009a3f  jz      short loc_180009A6A
0x180009a41  lea     r8, [rdi+20h]; unsigned int *
0x180009a45  mov     rcx, rsi; this
0x180009a48  lea     rdx, aFlags2; "Flags2"
0x180009a4f  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009a54  mov     r14d, eax
0x180009a57  test    eax, eax
0x180009a59  jns     short loc_180009A65
0x180009a5b  mov     edx, 83Bh
0x180009a60  jmp     loc_180009998
0x180009a65  test    rbx, rbx
0x180009a68  jz      short loc_180009A6F
0x180009a6a  test    bl, 20h
0x180009a6d  jz      short loc_180009A98
0x180009a6f  lea     r8, [rdi+24h]; unsigned int *
0x180009a73  mov     rcx, rsi; this
0x180009a76  lea     rdx, aPackageorigin; "PackageOrigin"
0x180009a7d  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009a82  mov     r14d, eax
0x180009a85  test    eax, eax
0x180009a87  jns     short loc_180009A93
0x180009a89  mov     edx, 83Fh
0x180009a8e  jmp     loc_180009998
0x180009a93  test    rbx, rbx
0x180009a96  jz      short loc_180009A9D
0x180009a98  test    bl, 40h
0x180009a9b  jz      short loc_180009AC6
0x180009a9d  lea     r8, [rdi+28h]; unsigned int *
0x180009aa1  mov     rcx, rsi; this
0x180009aa4  lea     rdx, aVolume; "Volume"
0x180009aab  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009ab0  mov     r14d, eax
0x180009ab3  test    eax, eax
0x180009ab5  jns     short loc_180009AC1
0x180009ab7  mov     edx, 843h
0x180009abc  jmp     loc_180009998
0x180009ac1  test    rbx, rbx
0x180009ac4  jz      short loc_180009ACA
0x180009ac6  test    bl, bl
0x180009ac8  jns     short loc_180009AF3
0x180009aca  lea     r8, [rdi+30h]; unsigned __int64 *
0x180009ace  mov     rcx, rsi; this
0x180009ad1  lea     rdx, aOsmaxversionte; "OSMaxVersionTested"
0x180009ad8  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEA_K@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,unsigned __int64 &)
0x180009add  mov     r14d, eax
0x180009ae0  test    eax, eax
0x180009ae2  jns     short loc_180009AEE
0x180009ae4  mov     edx, 847h
0x180009ae9  jmp     loc_180009998
0x180009aee  test    rbx, rbx
0x180009af1  jz      short loc_180009AFA
0x180009af3  bt      rbx, 8
0x180009af8  jnb     short loc_180009B41
0x180009afa  lea     rax, [rdi+38h]
0x180009afe  mov     [rbp+var_20], 0
0x180009b06  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180009b0a  mov     [rbp+var_28], rax
0x180009b0e  lea     rdx, aInstalledlocat; "InstalledLocation"
0x180009b15  mov     [rbp+var_18], 1
0x180009b19  mov     rcx, rsi; this
0x180009b1c  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009b21  lea     rcx, [rbp+var_28]
0x180009b25  mov     r14d, eax
0x180009b28  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009b2d  test    r14d, r14d
0x180009b30  jns     short loc_180009B3C
0x180009b32  mov     edx, 84Bh
0x180009b37  jmp     loc_180009998
0x180009b3c  test    rbx, rbx
0x180009b3f  jz      short loc_180009B48
0x180009b41  bt      rbx, 9
0x180009b46  jnb     short loc_180009B8F
0x180009b48  lea     rax, [rdi+40h]
0x180009b4c  mov     [rbp+var_20], 0
0x180009b54  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180009b58  mov     [rbp+var_28], rax
0x180009b5c  lea     rdx, aMutablelink; "MutableLink"
0x180009b63  mov     [rbp+var_18], 1
0x180009b67  mov     rcx, rsi; this
0x180009b6a  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009b6f  lea     rcx, [rbp+var_28]
0x180009b73  mov     r14d, eax
0x180009b76  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009b7b  test    r14d, r14d
0x180009b7e  jns     short loc_180009B8A
0x180009b80  mov     edx, 84Fh
0x180009b85  jmp     loc_180009998
0x180009b8a  test    rbx, rbx
0x180009b8d  jz      short loc_180009B96
0x180009b8f  bt      rbx, 0Ah
0x180009b94  jnb     short loc_180009BDD
0x180009b96  lea     rax, [rdi+48h]
0x180009b9a  mov     [rbp+var_20], 0
0x180009ba2  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180009ba6  mov     [rbp+var_28], rax
0x180009baa  lea     rdx, aMutablelocatio; "MutableLocation"
0x180009bb1  mov     [rbp+var_18], 1
0x180009bb5  mov     rcx, rsi; this
0x180009bb8  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009bbd  lea     rcx, [rbp+var_28]
0x180009bc1  mov     r14d, eax
0x180009bc4  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009bc9  test    r14d, r14d
0x180009bcc  jns     short loc_180009BD8
0x180009bce  mov     edx, 853h
0x180009bd3  jmp     loc_180009998
0x180009bd8  test    rbx, rbx
0x180009bdb  jz      short loc_180009BE4
0x180009bdd  bt      rbx, 0Bh
0x180009be2  jnb     short loc_180009C0D
0x180009be4  lea     r8, [rdi+50h]; unsigned int *
0x180009be8  mov     rcx, rsi; this
0x180009beb  lea     rdx, aTargetdevicefa; "TargetDeviceFamilyName"
0x180009bf2  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009bf7  mov     r14d, eax
0x180009bfa  test    eax, eax
0x180009bfc  jns     short loc_180009C08
0x180009bfe  mov     edx, 857h
0x180009c03  jmp     loc_180009998
0x180009c08  test    rbx, rbx
0x180009c0b  jz      short loc_180009C14
0x180009c0d  bt      rbx, 0Ch
0x180009c12  jnb     short loc_180009C5B
0x180009c14  lea     rax, [rdi+58h]
0x180009c18  mov     [rbp+var_20], 0
0x180009c20  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180009c24  mov     [rbp+var_28], rax
0x180009c28  lea     rdx, aDisplayname; "DisplayName"
0x180009c2f  mov     [rbp+var_18], 1
0x180009c33  mov     rcx, rsi; this
0x180009c36  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009c3b  lea     rcx, [rbp+var_28]
0x180009c3f  mov     r14d, eax
0x180009c42  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009c47  test    r14d, r14d
0x180009c4a  jns     short loc_180009C56
0x180009c4c  mov     edx, 85Bh
0x180009c51  jmp     loc_180009998
0x180009c56  test    rbx, rbx
0x180009c59  jz      short loc_180009C62
0x180009c5b  bt      rbx, 0Dh
0x180009c60  jnb     short loc_180009C97
0x180009c62  lea     r8, [rdi+60h]; unsigned int *
0x180009c66  mov     rcx, rsi; this
0x180009c69  lea     rdx, aSourcebundle; "SourceBundle"
0x180009c70  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180009c75  mov     ebx, eax
0x180009c77  test    eax, eax
0x180009c79  jns     short loc_180009C97
0x180009c7b  mov     rcx, [rbp+30h]; this
0x180009c7f  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x180009c86  mov     r9d, eax; char *
0x180009c89  mov     edx, 85Fh; void *
0x180009c8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c93  mov     eax, ebx
0x180009c95  jmp     short loc_180009C9C
0x180009c97  mov     [rdi], r15
0x180009c9a  xor     eax, eax
0x180009c9c  add     rsp, 48h
0x180009ca0  pop     r15
0x180009ca2  pop     r14
0x180009ca4  pop     rdi
0x180009ca5  pop     rsi
0x180009ca6  pop     rbx
0x180009ca7  pop     rbp
0x180009ca8  retn
```
