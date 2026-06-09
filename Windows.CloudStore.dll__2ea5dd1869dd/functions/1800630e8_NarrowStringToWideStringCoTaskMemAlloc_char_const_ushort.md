# NarrowStringToWideStringCoTaskMemAlloc(char const *,ushort * *)

- ea: `0x1800630e8`
- end: `0x180063224`
- name: `?NarrowStringToWideStringCoTaskMemAlloc@@YAJPEBDPEAPEAG@Z`
- size: `316`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180063bcc`

## callees

- `0x180047904`
- `0x180062040`
- `0x1800630e8`
- `0x18006322c`
- `0x1800c8458`
- `0x1800fc644`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006311c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180063194`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006311c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180063194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800631f3`

## string_xrefs

- `0x1800631b9`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`
- `0x1800631d4`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`
- `0x180063202`: `onecoreuap\shell\cloudstore\common\src\stringconversion.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NarrowStringToWideStringCoTaskMemAlloc(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  int v4; // eax
  __int64 v5; // rcx
  const char *v6; // r9
  int cchWideChar; // esi
  int LastError; // ebx
  const char *v9; // r9
  int lpWideCharStr; // [rsp+20h] [rbp-58h]
  LPWSTR *v12; // [rsp+30h] [rbp-48h] BYREF
  void *v13; // [rsp+38h] [rbp-40h] BYREF
  char v14; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  LPWSTR v16; // [rsp+88h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = MultiByteToWideChar(0, 8u, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v4;
  if ( !v4 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x18,
             (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
             v6);
  v16 = 0;
  v12 = &v16;
  v13 = 0;
  v14 = 1;
  LastError = _AllocArray<unsigned short,CTCoAllocPolicy>(v5, 1, v4, &v13);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
      (const char *)(unsigned int)LastError,
      lpWideCharStr);
    if ( v16 )
      CoTaskMemFree(v16);
  }
  else
  {
    if ( MultiByteToWideChar(0, 8u, lpMultiByteStr, -1, v16, cchWideChar) )
    {
      *a2 = v16;
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\stringconversion.cpp",
                  v9);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v16);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800630e8  push    rbx
0x1800630ea  push    rbp
0x1800630eb  push    rsi
0x1800630ec  push    rdi
0x1800630ed  sub     rsp, 58h
0x1800630f1  mov     rdi, rdx
0x1800630f4  mov     rbp, rcx
0x1800630f7  mov     qword ptr [rdx], 0
0x1800630fe  mov     [rsp+78h+cchWideChar], 0; cchWideChar
0x180063106  mov     [rsp+78h+lpWideCharStr], 0; int
0x18006310f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180063113  mov     r8, rcx; lpMultiByteStr
0x180063116  lea     edx, [r9+9]; dwFlags
0x18006311a  xor     ecx, ecx; CodePage
0x18006311c  call    cs:__imp_MultiByteToWideChar
0x180063122  movsxd  rsi, eax
0x180063125  test    eax, eax
0x180063127  jz      loc_1800631B4
0x18006312d  mov     [rsp+78h+arg_8], 0
0x180063139  lea     rax, [rsp+78h+arg_8]
0x180063141  mov     [rsp+78h+var_48], rax
0x180063146  mov     [rsp+78h+var_40], 0
0x18006314f  mov     [rsp+78h+var_38], 1
0x180063154  mov     r8, rsi
0x180063157  lea     r9, [rsp+78h+var_40]
0x18006315c  mov     edx, 1
0x180063161  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180063166  mov     ebx, eax
0x180063168  lea     rcx, [rsp+78h+var_48]
0x18006316d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180063172  test    ebx, ebx
0x180063174  js      short loc_1800631CC
0x180063176  mov     [rsp+78h+cchWideChar], esi; cchWideChar
0x18006317a  mov     rax, [rsp+78h+arg_8]
0x180063182  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x180063187  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006318b  mov     r8, rbp; lpMultiByteStr
0x18006318e  lea     edx, [r9+9]; dwFlags
0x180063192  xor     ecx, ecx; CodePage
0x180063194  call    cs:__imp_MultiByteToWideChar
0x18006319a  test    eax, eax
0x18006319c  jz      short loc_1800631FD
0x18006319e  mov     rax, [rsp+78h+arg_8]
0x1800631a6  mov     [rdi], rax
0x1800631a9  xor     eax, eax
0x1800631ab  add     rsp, 58h
0x1800631af  pop     rdi
0x1800631b0  pop     rsi
0x1800631b1  pop     rbp
0x1800631b2  pop     rbx
0x1800631b3  retn
0x1800631b4  mov     rcx, [rsp+78h]; this
0x1800631b9  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800631c0  mov     edx, 18h; void *
0x1800631c5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800631ca  jmp     short loc_1800631AB
0x1800631cc  mov     rcx, [rsp+78h]; this
0x1800631d1  mov     r9d, ebx; char *
0x1800631d4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800631db  mov     edx, 1Bh; void *
0x1800631e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800631e5  nop
0x1800631e6  mov     rcx, [rsp+78h+arg_8]; pv
0x1800631ee  test    rcx, rcx
0x1800631f1  jz      short loc_1800631F9
0x1800631f3  call    cs:__imp_CoTaskMemFree
0x1800631f9  mov     eax, ebx
0x1800631fb  jmp     short loc_1800631AB
0x1800631fd  mov     rcx, [rsp+78h]; this
0x180063202  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180063209  mov     edx, 1Ch; void *
0x18006320e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063213  mov     ebx, eax
0x180063215  lea     rcx, [rsp+78h+arg_8]
0x18006321d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180063222  jmp     short loc_1800631F9
```
