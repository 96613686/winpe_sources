# SystemSettings::WorkAccess::IsMachineDomainJoinedAndGetName(bool *,ushort * *,ushort * *)

- ea: `0x180043448`
- end: `0x1800435de`
- name: `?IsMachineDomainJoinedAndGetName@WorkAccess@SystemSettings@@YAJPEA_NPEAPEAG1@Z`
- size: `406`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess *__hidden this, bool *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e100`
- `0x180029400`

## callees

- `0x1800096ec`
- `0x1800224e8`
- `0x18003b45c`
- `0x1800401cc`
- `0x180043448`

## import_xrefs

- `NETAPI32!DsRoleGetPrimaryDomainInformation` at `0x18004349b`
- `NETAPI32!DsRoleGetPrimaryDomainInformation` at `0x18004349b`
- `NETAPI32!DsRoleFreeMemory` at `0x1800435b6`
- `NETAPI32!DsRoleFreeMemory` at `0x1800435b6`

## string_xrefs

- `0x180043521`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x18004356f`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkAccess::IsMachineDomainJoinedAndGetName(
        SystemSettings::WorkAccess *this,
        bool *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  signed int PrimaryDomainInformation; // eax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  PBYTE v10; // rcx
  void *v11; // rdi
  __int64 v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // r8
  int v20; // eax
  int v21; // r14d
  int v23; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *v25; // [rsp+70h] [rbp+30h] BYREF
  PBYTE Buffer; // [rsp+78h] [rbp+38h] BYREF

  *(_BYTE *)this = 0;
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( a3 )
    *a3 = 0;
  Buffer = 0;
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  v9 = PrimaryDomainInformation;
  if ( PrimaryDomainInformation )
  {
    if ( PrimaryDomainInformation > 0 )
      v9 = (unsigned __int16)PrimaryDomainInformation | 0x80070000;
    goto LABEL_26;
  }
  v10 = Buffer;
  if ( !Buffer || ((*(_DWORD *)Buffer - 1) & 0xFFFFFFFD) != 0 )
  {
LABEL_26:
    v18 = v9;
    goto LABEL_27;
  }
  *(_BYTE *)this = 1;
  v11 = 0;
  v25 = 0;
  v12 = -1;
  if ( !*((_QWORD *)v10 + 2) || !a2 )
  {
LABEL_15:
    v19 = *((_QWORD *)Buffer + 1);
    if ( v19 && a3 )
    {
      do
        ++v12;
      while ( *(_WORD *)(v19 + 2 * v12) );
      v20 = _AllocStringWorker<CTCoAllocPolicy>(v10, v8, v19);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC7,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
          (const char *)(unsigned int)v20,
          v23);
        v18 = v21;
        goto LABEL_20;
      }
    }
    if ( v11 )
    {
      v25 = 0;
      *(_QWORD *)a2 = v11;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
    goto LABEL_26;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v25,
    0);
  v15 = *((_QWORD *)Buffer + 2);
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)(v15 + 2 * v16) );
  v17 = _AllocStringWorker<CTCoAllocPolicy>(v14, v13, v15);
  v18 = v17;
  if ( v17 >= 0 )
  {
    v11 = v25;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC2,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
    (const char *)(unsigned int)v17,
    v23);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
LABEL_27:
  DsRoleFreeMemory(Buffer);
  return v18;
}

```

## disassembly

```asm
0x180043448  mov     [rsp-28h+arg_10], rbx
0x18004344d  mov     [rsp-28h+arg_18], rsi
0x180043452  push    rbp
0x180043453  push    rdi
0x180043454  push    r12
0x180043456  push    r14
0x180043458  push    r15
0x18004345a  mov     rbp, rsp
0x18004345d  sub     rsp, 40h
0x180043461  mov     r14, r8
0x180043464  mov     rsi, rdx
0x180043467  mov     rdi, rcx
0x18004346a  xor     r12d, r12d
0x18004346d  mov     [rcx], r12b
0x180043470  test    rdx, rdx
0x180043473  jz      short loc_180043478
0x180043475  mov     [rdx], r12
0x180043478  test    r14, r14
0x18004347b  jz      short loc_180043480
0x18004347d  mov     [r8], r12
0x180043480  mov     [rbp+Buffer], r12
0x180043484  lea     rax, [rbp+Buffer]
0x180043488  mov     [rbp+var_10], rax
0x18004348c  mov     [rbp+var_8], 1
0x180043490  lea     r8, [rbp+Buffer]; Buffer
0x180043494  mov     edx, 1; InfoLevel
0x180043499  xor     ecx, ecx; lpServer
0x18004349b  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800434a2  nop     dword ptr [rax+rax+00h]
0x1800434a7  mov     ebx, eax
0x1800434a9  test    eax, eax
0x1800434ab  jnz     loc_1800435A5
0x1800434b1  mov     rcx, [rbp+Buffer]
0x1800434b5  test    rcx, rcx
0x1800434b8  jz      loc_1800435B0
0x1800434be  mov     eax, [rcx]
0x1800434c0  dec     eax
0x1800434c2  test    eax, 0FFFFFFFDh
0x1800434c7  jnz     loc_1800435B0
0x1800434cd  mov     byte ptr [rdi], 1
0x1800434d0  mov     rdi, r12
0x1800434d3  mov     [rbp+arg_0], r12
0x1800434d7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800434db  cmp     [rcx+10h], r12
0x1800434df  jz      short loc_180043538
0x1800434e1  test    rsi, rsi
0x1800434e4  jz      short loc_180043538
0x1800434e6  xor     edx, edx
0x1800434e8  lea     rcx, [rbp+arg_0]
0x1800434ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800434f1  mov     rax, [rbp+Buffer]
0x1800434f5  mov     r8, [rax+10h]
0x1800434f9  mov     r9, r15
0x1800434fc  inc     r9
0x1800434ff  cmp     [r8+r9*2], r12w
0x180043504  jnz     short loc_1800434FC
0x180043506  lea     rax, [rbp+arg_0]
0x18004350a  mov     [rsp+40h+var_18], rax
0x18004350f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180043514  mov     edi, eax
0x180043516  test    eax, eax
0x180043518  jns     short loc_180043534
0x18004351a  mov     rcx, [rbp+28h]; this
0x18004351e  mov     r9d, eax; char *
0x180043521  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180043528  mov     edx, 0C2h; void *
0x18004352d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043532  jmp     short loc_180043583
0x180043534  mov     rdi, [rbp+arg_0]
0x180043538  mov     rax, [rbp+Buffer]
0x18004353c  mov     r8, [rax+8]
0x180043540  test    r8, r8
0x180043543  jz      short loc_18004358E
0x180043545  test    r14, r14
0x180043548  jz      short loc_18004358E
0x18004354a  inc     r15
0x18004354d  cmp     [r8+r15*2], r12w
0x180043552  jnz     short loc_18004354A
0x180043554  mov     [rsp+40h+var_18], r14
0x180043559  mov     r9, r15
0x18004355c  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180043561  mov     r14d, eax
0x180043564  test    eax, eax
0x180043566  jns     short loc_18004358E
0x180043568  mov     rcx, [rbp+28h]; this
0x18004356c  mov     r9d, eax; char *
0x18004356f  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180043576  mov     edx, 0C7h; void *
0x18004357b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043580  mov     edi, r14d
0x180043583  lea     rcx, [rbp+arg_0]
0x180043587  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004358c  jmp     short loc_1800435B2
0x18004358e  test    rdi, rdi
0x180043591  jz      short loc_18004359A
0x180043593  mov     [rbp+arg_0], r12
0x180043597  mov     [rsi], rdi
0x18004359a  lea     rcx, [rbp+arg_0]
0x18004359e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800435a3  jmp     short loc_1800435B0
0x1800435a5  jle     short loc_1800435B0
0x1800435a7  movzx   ebx, ax
0x1800435aa  or      ebx, 80070000h
0x1800435b0  mov     edi, ebx
0x1800435b2  mov     rcx, [rbp+Buffer]; Buffer
0x1800435b6  call    cs:__imp_DsRoleFreeMemory
0x1800435bd  nop     dword ptr [rax+rax+00h]
0x1800435c2  mov     eax, edi
0x1800435c4  lea     r11, [rsp+40h+var_s0]
0x1800435c9  mov     rbx, [r11+40h]
0x1800435cd  mov     rsi, [r11+48h]
0x1800435d1  mov     rsp, r11
0x1800435d4  pop     r15
0x1800435d6  pop     r14
0x1800435d8  pop     r12
0x1800435da  pop     rdi
0x1800435db  pop     rbp
0x1800435dc  retn
```
