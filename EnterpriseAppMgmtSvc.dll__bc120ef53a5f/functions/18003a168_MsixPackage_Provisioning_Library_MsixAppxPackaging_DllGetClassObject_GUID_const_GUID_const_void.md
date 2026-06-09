# MsixPackage::Provisioning::Library::MsixAppxPackaging::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18003a168`
- end: `0x18003a29f`
- name: `?DllGetClassObject@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `311`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxPackaging *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800344e4`
- `0x18003e780`

## callees

- `0x18000d3dc`
- `0x18003a168`
- `0x18003c4dc`
- `0x18003d4ec`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a1ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a221`

## string_xrefs

- `0x18003a1e7`: `DllGetClassObject`
- `0x18003a24c`: `Unable to GetProcAddress 'DllGetClassObject'`
- `0x18003a18e`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003a1bb`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18003a25b`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixAppxPackaging::DllGetClassObject(
        MsixPackage::Provisioning::Library::MsixAppxPackaging *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int Dynamic; // eax
  unsigned int v11; // edi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v14; // sf
  signed int v15; // eax
  int v16; // [rsp+20h] [rbp-38h]
  const char *v17; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a4 )
  {
    v7 = -2147024809;
    v8 = 152;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)v7,
      v16);
    return v7;
  }
  *a4 = 0;
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadDynamic(
              this,
              a2,
              a3);
  v11 = Dynamic;
  if ( Dynamic >= 0 )
  {
    ProcAddress = (FARPROC)*((_QWORD *)this + 7);
    if ( !ProcAddress )
    {
      ProcAddress = GetProcAddress(*((HMODULE *)this + 1), "DllGetClassObject");
      *((_QWORD *)this + 7) = ProcAddress;
      if ( !ProcAddress )
      {
        LastError = GetLastError();
        v14 = LastError < 0;
        if ( LastError > 0 )
          v14 = 1;
        if ( v14 )
        {
          v15 = GetLastError();
          v7 = v15;
          if ( v15 > 0 )
            v7 = (unsigned __int16)v15 | 0x80070000;
          if ( (v7 & 0x80000000) == 0 )
            return v7;
        }
        else
        {
          v7 = -2147467259;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
          (const char *)v7,
          (int)"Unable to GetProcAddress 'DllGetClassObject'",
          v17);
        return v7;
      }
    }
    v7 = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, void **))ProcAddress)(
           a2,
           &GUID_00000001_0000_0000_c000_000000000046,
           a4);
    if ( (v7 & 0x80000000) != 0 )
    {
      v8 = 166;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)Dynamic,
      v16);
    return v11;
  }
}

```

## disassembly

```asm
0x18003a168  push    rbx
0x18003a16a  push    rbp
0x18003a16b  push    rsi
0x18003a16c  push    rdi
0x18003a16d  sub     rsp, 38h
0x18003a171  mov     rsi, r9
0x18003a174  mov     rbp, rdx
0x18003a177  mov     rbx, rcx
0x18003a17a  test    r9, r9
0x18003a17d  jnz     short loc_18003A1A4
0x18003a17f  mov     ebx, 80070057h
0x18003a184  mov     edx, 98h; void *
0x18003a189  mov     rcx, [rsp+58h]; this
0x18003a18e  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a195  mov     r9d, ebx; char *
0x18003a198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a19d  mov     eax, ebx
0x18003a19f  jmp     loc_18003A295
0x18003a1a4  mov     qword ptr [r9], 0
0x18003a1ab  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxPackaging@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadDynamic(void)
0x18003a1b0  mov     edi, eax
0x18003a1b2  test    eax, eax
0x18003a1b4  jns     short loc_18003A1D6
0x18003a1b6  mov     rcx, [rsp+58h]; this
0x18003a1bb  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a1c2  mov     r9d, eax; char *
0x18003a1c5  mov     edx, 9Ah; void *
0x18003a1ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a1cf  mov     eax, edi
0x18003a1d1  jmp     loc_18003A295
0x18003a1d6  mov     rax, [rbx+38h]
0x18003a1da  test    rax, rax
0x18003a1dd  jnz     loc_18003A271
0x18003a1e3  mov     rcx, [rbx+8]; hModule
0x18003a1e7  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18003a1ee  call    cs:__imp_GetProcAddress
0x18003a1f5  nop     dword ptr [rax+rax+00h]
0x18003a1fa  mov     [rbx+38h], rax
0x18003a1fe  test    rax, rax
0x18003a201  jnz     short loc_18003A271
0x18003a203  call    cs:__imp_GetLastError
0x18003a20a  nop     dword ptr [rax+rax+00h]
0x18003a20f  mov     edi, 80070000h
0x18003a214  test    eax, eax
0x18003a216  jle     short loc_18003A21F
0x18003a218  movzx   eax, ax
0x18003a21b  or      eax, edi
0x18003a21d  test    eax, eax
0x18003a21f  jns     short loc_18003A242
0x18003a221  call    cs:__imp_GetLastError
0x18003a228  nop     dword ptr [rax+rax+00h]
0x18003a22d  mov     ebx, eax
0x18003a22f  test    eax, eax
0x18003a231  jle     short loc_18003A238
0x18003a233  movzx   ebx, ax
0x18003a236  or      ebx, edi
0x18003a238  test    ebx, ebx
0x18003a23a  jns     loc_18003A19D
0x18003a240  jmp     short loc_18003A247
0x18003a242  mov     ebx, 80004005h
0x18003a247  mov     rcx, [rsp+58h]; this
0x18003a24c  lea     rax, aUnableToGetpro_9; "Unable to GetProcAddress 'DllGetClassOb"...
0x18003a253  mov     r9d, ebx; char *
0x18003a256  mov     qword ptr [rsp+58h+var_38], rax; int
0x18003a25b  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003a262  mov     edx, 0A2h; void *
0x18003a267  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003a26c  jmp     loc_18003A19D
0x18003a271  mov     r8, rsi
0x18003a274  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x18003a27b  mov     rcx, rbp
0x18003a27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a283  mov     ebx, eax
0x18003a285  test    eax, eax
0x18003a287  jns     short loc_18003A293
0x18003a289  mov     edx, 0A6h
0x18003a28e  jmp     loc_18003A189
0x18003a293  xor     eax, eax
0x18003a295  add     rsp, 38h
0x18003a299  pop     rdi
0x18003a29a  pop     rsi
0x18003a29b  pop     rbp
0x18003a29c  pop     rbx
0x18003a29d  retn
```
