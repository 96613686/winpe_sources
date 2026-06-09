# MsixPackage::Provisioning::Library::MsixAppxPackaging::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180036d5c`
- end: `0x180036e7c`
- name: `?DllGetClassObject@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixAppxPackaging *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003167c`
- `0x18003b0b0`

## callees

- `0x18000cfe8`
- `0x180036d5c`
- `0x180038f50`
- `0x180039e9c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036dde`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e05`

## string_xrefs

- `0x180036e2a`: `Unable to GetProcAddress 'DllGetClassObject'`
- `0x180036dd7`: `DllGetClassObject`
- `0x180036d82`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180036daf`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x180036e39`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`

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
0x180036d5c  push    rbx
0x180036d5e  push    rbp
0x180036d5f  push    rsi
0x180036d60  push    rdi
0x180036d61  sub     rsp, 38h
0x180036d65  mov     rsi, r9
0x180036d68  mov     rbp, rdx
0x180036d6b  mov     rbx, rcx
0x180036d6e  test    r9, r9
0x180036d71  jnz     short loc_180036D98
0x180036d73  mov     ebx, 80070057h
0x180036d78  mov     edx, 98h; void *
0x180036d7d  mov     rcx, [rsp+58h]; this
0x180036d82  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036d89  mov     r9d, ebx; char *
0x180036d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d91  mov     eax, ebx
0x180036d93  jmp     loc_180036E73
0x180036d98  mov     qword ptr [r9], 0
0x180036d9f  call    ?LoadDynamic@?$MsixProvisioningModule@VMsixAppxPackaging@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::MsixAppxPackaging>::LoadDynamic(void)
0x180036da4  mov     edi, eax
0x180036da6  test    eax, eax
0x180036da8  jns     short loc_180036DCA
0x180036daa  mov     rcx, [rsp+58h]; this
0x180036daf  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036db6  mov     r9d, eax; char *
0x180036db9  mov     edx, 9Ah; void *
0x180036dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036dc3  mov     eax, edi
0x180036dc5  jmp     loc_180036E73
0x180036dca  mov     rax, [rbx+38h]
0x180036dce  test    rax, rax
0x180036dd1  jnz     short loc_180036E4F
0x180036dd3  mov     rcx, [rbx+8]; hModule
0x180036dd7  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180036dde  call    cs:__imp_GetProcAddress
0x180036de4  mov     [rbx+38h], rax
0x180036de8  test    rax, rax
0x180036deb  jnz     short loc_180036E4F
0x180036ded  call    cs:__imp_GetLastError
0x180036df3  mov     edi, 80070000h
0x180036df8  test    eax, eax
0x180036dfa  jle     short loc_180036E03
0x180036dfc  movzx   eax, ax
0x180036dff  or      eax, edi
0x180036e01  test    eax, eax
0x180036e03  jns     short loc_180036E20
0x180036e05  call    cs:__imp_GetLastError
0x180036e0b  mov     ebx, eax
0x180036e0d  test    eax, eax
0x180036e0f  jle     short loc_180036E16
0x180036e11  movzx   ebx, ax
0x180036e14  or      ebx, edi
0x180036e16  test    ebx, ebx
0x180036e18  jns     loc_180036D91
0x180036e1e  jmp     short loc_180036E25
0x180036e20  mov     ebx, 80004005h
0x180036e25  mov     rcx, [rsp+58h]; this
0x180036e2a  lea     rax, aUnableToGetpro_9; "Unable to GetProcAddress 'DllGetClassOb"...
0x180036e31  mov     r9d, ebx; char *
0x180036e34  mov     qword ptr [rsp+58h+var_38], rax; int
0x180036e39  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180036e40  mov     edx, 0A2h; void *
0x180036e45  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036e4a  jmp     loc_180036D91
0x180036e4f  mov     r8, rsi
0x180036e52  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x180036e59  mov     rcx, rbp
0x180036e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e61  mov     ebx, eax
0x180036e63  test    eax, eax
0x180036e65  jns     short loc_180036E71
0x180036e67  mov     edx, 0A6h
0x180036e6c  jmp     loc_180036D7D
0x180036e71  xor     eax, eax
0x180036e73  add     rsp, 38h
0x180036e77  pop     rdi
0x180036e78  pop     rsi
0x180036e79  pop     rbp
0x180036e7a  pop     rbx
0x180036e7b  retn
```
