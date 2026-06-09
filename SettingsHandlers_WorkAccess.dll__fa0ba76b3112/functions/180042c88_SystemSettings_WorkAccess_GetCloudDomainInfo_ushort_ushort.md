# SystemSettings::WorkAccess::GetCloudDomainInfo(ushort * *,ushort * *)

- ea: `0x180042c88`
- end: `0x180042e13`
- name: `?GetCloudDomainInfo@WorkAccess@SystemSettings@@YAJPEAPEAG0@Z`
- size: `395`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e100`
- `0x1800441d0`

## callees

- `0x1800096ec`
- `0x1800224e8`
- `0x18003b45c`
- `0x1800401cc`
- `0x180042c88`

## import_xrefs

- `dsreg!DsrGetJoinInfo` at `0x180042cc4`
- `dsreg!DsrGetJoinInfo` at `0x180042cc4`
- `dsreg!DsrFreeJoinInfo` at `0x180042deb`
- `dsreg!DsrFreeJoinInfo` at `0x180042deb`

## string_xrefs

- `0x180042cdd`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x180042d5e`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`
- `0x180042dac`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::WorkAccess::GetCloudDomainInfo(
        SystemSettings::WorkAccess *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  int JoinInfo; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // rax
  __int64 v11; // rbx
  void *v12; // rsi
  __int64 v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  unsigned int v19; // esi
  __int64 v20; // r8
  int v21; // eax
  int v22; // r14d
  int v23; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *v25; // [rsp+70h] [rbp+30h] BYREF
  __int64 v26; // [rsp+78h] [rbp+38h] BYREF

  if ( this )
    *(_QWORD *)this = 0;
  if ( a2 )
    *a2 = 0;
  v26 = 0;
  JoinInfo = DsrGetJoinInfo(0, &v26, a3);
  v8 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
      (const char *)(unsigned int)JoinInfo,
      v23);
    return v8;
  }
  v10 = v26;
  v11 = v26;
  if ( !v26 )
    goto LABEL_25;
  v12 = 0;
  v25 = 0;
  v13 = -1;
  if ( !*(_QWORD *)(v26 + 48) || !this )
  {
LABEL_15:
    v20 = *(_QWORD *)(v10 + 40);
    if ( v20 && a2 )
    {
      do
        ++v13;
      while ( *(_WORD *)(v20 + 2 * v13) );
      v21 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v20);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
          (const char *)(unsigned int)v21,
          v23);
        v19 = v22;
        goto LABEL_20;
      }
    }
    if ( this )
    {
      if ( v12 )
      {
        v25 = 0;
        *(_QWORD *)this = v12;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
LABEL_25:
    v19 = 0;
    goto LABEL_26;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v25,
    0);
  v16 = *(_QWORD *)(v26 + 48);
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(v16 + 2 * v17) );
  v18 = _AllocStringWorker<CTCoAllocPolicy>(v15, v14, v16);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v10 = v26;
    v12 = v25;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x92,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
    (const char *)(unsigned int)v18,
    v23);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
LABEL_26:
  DsrFreeJoinInfo(v11);
  return v19;
}

```

## disassembly

```asm
0x180042c88  mov     [rsp-28h+arg_10], rbx
0x180042c8d  mov     [rsp-28h+arg_18], rsi
0x180042c92  push    rbp
0x180042c93  push    rdi
0x180042c94  push    r12
0x180042c96  push    r14
0x180042c98  push    r15
0x180042c9a  mov     rbp, rsp
0x180042c9d  sub     rsp, 40h
0x180042ca1  mov     r14, rdx
0x180042ca4  mov     rdi, rcx
0x180042ca7  xor     r12d, r12d
0x180042caa  test    rcx, rcx
0x180042cad  jz      short loc_180042CB2
0x180042caf  mov     [rcx], r12
0x180042cb2  test    r14, r14
0x180042cb5  jz      short loc_180042CBA
0x180042cb7  mov     [rdx], r12
0x180042cba  mov     [rbp+arg_8], r12
0x180042cbe  lea     rdx, [rbp+arg_8]
0x180042cc2  xor     ecx, ecx
0x180042cc4  call    cs:__imp_DsrGetJoinInfo
0x180042ccb  nop     dword ptr [rax+rax+00h]
0x180042cd0  mov     ebx, eax
0x180042cd2  test    eax, eax
0x180042cd4  jns     short loc_180042CF5
0x180042cd6  mov     rcx, [rbp+28h]; this
0x180042cda  mov     r9d, eax; char *
0x180042cdd  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042ce4  mov     edx, 86h; void *
0x180042ce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042cee  mov     eax, ebx
0x180042cf0  jmp     loc_180042DF9
0x180042cf5  mov     rax, [rbp+arg_8]
0x180042cf9  mov     rbx, rax
0x180042cfc  mov     [rbp+var_10], rax
0x180042d00  mov     [rbp+var_8], 1
0x180042d04  test    rax, rax
0x180042d07  jz      loc_180042DE5
0x180042d0d  mov     rsi, r12
0x180042d10  mov     [rbp+arg_0], r12
0x180042d14  or      r15, 0FFFFFFFFFFFFFFFFh
0x180042d18  cmp     [rax+30h], r12
0x180042d1c  jz      short loc_180042D79
0x180042d1e  test    rdi, rdi
0x180042d21  jz      short loc_180042D79
0x180042d23  xor     edx, edx
0x180042d25  lea     rcx, [rbp+arg_0]
0x180042d29  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180042d2e  mov     rax, [rbp+arg_8]
0x180042d32  mov     r8, [rax+30h]
0x180042d36  mov     r9, r15
0x180042d39  inc     r9
0x180042d3c  cmp     [r8+r9*2], r12w
0x180042d41  jnz     short loc_180042D39
0x180042d43  lea     rax, [rbp+arg_0]
0x180042d47  mov     [rsp+40h+var_18], rax
0x180042d4c  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180042d51  mov     esi, eax
0x180042d53  test    eax, eax
0x180042d55  jns     short loc_180042D71
0x180042d57  mov     rcx, [rbp+28h]; this
0x180042d5b  mov     r9d, eax; char *
0x180042d5e  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042d65  mov     edx, 92h; void *
0x180042d6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042d6f  jmp     short loc_180042DC0
0x180042d71  mov     rax, [rbp+arg_8]
0x180042d75  mov     rsi, [rbp+arg_0]
0x180042d79  mov     r8, [rax+28h]
0x180042d7d  test    r8, r8
0x180042d80  jz      short loc_180042DCB
0x180042d82  test    r14, r14
0x180042d85  jz      short loc_180042DCB
0x180042d87  inc     r15
0x180042d8a  cmp     [r8+r15*2], r12w
0x180042d8f  jnz     short loc_180042D87
0x180042d91  mov     [rsp+40h+var_18], r14
0x180042d96  mov     r9, r15
0x180042d99  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180042d9e  mov     r14d, eax
0x180042da1  test    eax, eax
0x180042da3  jns     short loc_180042DCB
0x180042da5  mov     rcx, [rbp+28h]; this
0x180042da9  mov     r9d, eax; char *
0x180042dac  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042db3  mov     edx, 97h; void *
0x180042db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042dbd  mov     esi, r14d
0x180042dc0  lea     rcx, [rbp+arg_0]
0x180042dc4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042dc9  jmp     short loc_180042DE8
0x180042dcb  test    rdi, rdi
0x180042dce  jz      short loc_180042DDC
0x180042dd0  test    rsi, rsi
0x180042dd3  jz      short loc_180042DDC
0x180042dd5  mov     [rbp+arg_0], r12
0x180042dd9  mov     [rdi], rsi
0x180042ddc  lea     rcx, [rbp+arg_0]
0x180042de0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042de5  mov     esi, r12d
0x180042de8  mov     rcx, rbx
0x180042deb  call    cs:__imp_DsrFreeJoinInfo
0x180042df2  nop     dword ptr [rax+rax+00h]
0x180042df7  mov     eax, esi
0x180042df9  lea     r11, [rsp+40h+var_s0]
0x180042dfe  mov     rbx, [r11+40h]
0x180042e02  mov     rsi, [r11+48h]
0x180042e06  mov     rsp, r11
0x180042e09  pop     r15
0x180042e0b  pop     r14
0x180042e0d  pop     r12
0x180042e0f  pop     rdi
0x180042e10  pop     rbp
0x180042e11  retn
```
