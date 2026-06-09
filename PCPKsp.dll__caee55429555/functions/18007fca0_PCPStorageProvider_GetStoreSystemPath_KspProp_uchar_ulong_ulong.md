# PCPStorageProvider::GetStoreSystemPath(KspProp,uchar *,ulong,ulong *)

- ea: `0x18007fca0`
- end: `0x18007fe6a`
- name: `?GetStoreSystemPath@PCPStorageProvider@@AEAAJW4KspProp@@PEAEKPEAK@Z`
- size: `458`
- prototype: `int __high(enum KspProp, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bb00`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x1800389c0`
- `0x180046798`
- `0x180052168`
- `0x1800764d0`
- `0x18007bccc`
- `0x18007edc4`
- `0x18007fca0`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x18007fd26`
- `SHELL32!SHGetKnownFolderPath` at `0x18007fd26`

## string_xrefs

- `0x18007fcf1`: `PCPStorageProvider::GetStoreSystemPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PCPStorageProvider::GetStoreSystemPath(
        __int64 a1,
        int a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  rsize_t v5; // rdi
  HRESULT v8; // ebx
  __int64 v9; // rdx
  wchar_t *v10; // rbx
  unsigned int v11; // eax
  void **v12; // r8
  void *v14; // [rsp+20h] [rbp-60h] BYREF
  void **v15; // [rsp+28h] [rbp-58h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-50h] BYREF
  char v17; // [rsp+38h] [rbp-48h]
  _BYTE v18[24]; // [rsp+40h] [rbp-40h] BYREF
  void *Source[2]; // [rsp+58h] [rbp-28h] BYREF
  __m128i si128; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  *(_OWORD *)Source = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Source[0]) = 0;
  v14 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v18, L"PCPStorageProvider::GetStoreSystemPath", 1);
  v15 = &v14;
  ppszPath = 0;
  v17 = 1;
  v8 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v15);
  if ( v8 < 0 )
  {
    v9 = 1087;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
      (const char *)(unsigned int)v8,
      (int)v14);
    goto LABEL_21;
  }
  std::wstring::append(Source, v14);
  if ( a2 == 34 )
  {
    v10 = L"Microsoft\\Crypto\\PCPKSP\\WindowsAIK";
  }
  else
  {
    if ( a2 != 40 )
    {
      v8 = -2146893785;
      v9 = 1102;
      goto LABEL_20;
    }
    v10 = L"Microsoft\\Crypto\\PCPKSP\\WindowsEK";
  }
  std::wstring::append(Source, (void *)L"\\");
  std::wstring::append(Source, v10);
  v11 = 2 * si128.m128i_i32[0] + 2;
  v12 = Source;
  if ( si128.m128i_i64[1] > 7uLL )
    v12 = (void **)Source[0];
  if ( a5 )
    *a5 = v11;
  if ( (_DWORD)v5 && a3 )
  {
    if ( (unsigned int)v5 < v11 )
    {
      v8 = -2146893784;
      v9 = 1117;
      goto LABEL_20;
    }
    if ( !memcpy_s_1(a3, v5, v12, v11) )
    {
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v18);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
      std::wstring::~wstring(Source);
      return 0;
    }
    v8 = -2147418113;
  }
  else
  {
    v8 = 0;
  }
LABEL_21:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v18);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
  std::wstring::~wstring(Source);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007fca0  mov     [rsp-28h+arg_0], rbx
0x18007fca5  push    rbp
0x18007fca6  push    rsi
0x18007fca7  push    rdi
0x18007fca8  push    r14
0x18007fcaa  push    r15
0x18007fcac  mov     rbp, rsp
0x18007fcaf  sub     rsp, 80h
0x18007fcb6  mov     rax, cs:__security_cookie
0x18007fcbd  xor     rax, rsp
0x18007fcc0  mov     [rbp+var_8], rax
0x18007fcc4  mov     edi, r9d
0x18007fcc7  mov     r14, r8
0x18007fcca  mov     esi, edx
0x18007fccc  mov     r15, [rbp+arg_20]
0x18007fcd0  xorps   xmm0, xmm0
0x18007fcd3  movups  xmmword ptr [rbp+Source], xmm0
0x18007fcd7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007fcdf  movdqu  [rbp+var_18], xmm1
0x18007fce4  xor     eax, eax
0x18007fce6  mov     word ptr [rbp+Source], ax
0x18007fcea  mov     [rbp+var_60], rax
0x18007fcee  mov     r8b, 1; bool
0x18007fcf1  lea     rdx, aPcpstorageprov_5; "PCPStorageProvider::GetStoreSystemPath"
0x18007fcf8  lea     rcx, [rbp+var_40]; this
0x18007fcfc  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18007fd01  nop
0x18007fd02  lea     rax, [rbp+var_60]
0x18007fd06  mov     [rbp+var_58], rax
0x18007fd0a  mov     [rbp+ppszPath], 0
0x18007fd12  mov     [rbp+var_48], 1
0x18007fd16  lea     r9, [rbp+ppszPath]; ppszPath
0x18007fd1a  xor     r8d, r8d; hToken
0x18007fd1d  xor     edx, edx; dwFlags
0x18007fd1f  lea     rcx, FOLDERID_ProgramData; rfid
0x18007fd26  call    cs:__imp_SHGetKnownFolderPath
0x18007fd2d  nop     dword ptr [rax+rax+00h]
0x18007fd32  mov     ebx, eax
0x18007fd34  lea     rcx, [rbp+var_58]
0x18007fd38  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18007fd3d  test    ebx, ebx
0x18007fd3f  jns     short loc_18007FD4B
0x18007fd41  mov     edx, 43Fh
0x18007fd46  jmp     loc_18007FE13
0x18007fd4b  mov     rdx, [rbp+var_60]; void *
0x18007fd4f  lea     rcx, [rbp+Source]; Src
0x18007fd53  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007fd58  cmp     esi, 22h ; '"'
0x18007fd5b  jnz     short loc_18007FD66
0x18007fd5d  lea     rbx, aMicrosoftCrypt; "Microsoft\\Crypto\\PCPKSP\\WindowsAIK"
0x18007fd64  jmp     short loc_18007FD76
0x18007fd66  cmp     esi, 28h ; '('
0x18007fd69  jnz     loc_18007FE09
0x18007fd6f  lea     rbx, aMicrosoftCrypt_0; "Microsoft\\Crypto\\PCPKSP\\WindowsEK"
0x18007fd76  lea     rdx, asc_1800D5B38; "\\"
0x18007fd7d  lea     rcx, [rbp+Source]; Src
0x18007fd81  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007fd86  mov     rdx, rbx; void *
0x18007fd89  lea     rcx, [rbp+Source]; Src
0x18007fd8d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007fd92  mov     eax, dword ptr [rbp+var_18]
0x18007fd95  lea     eax, ds:2[rax*2]
0x18007fd9c  lea     r8, [rbp+Source]
0x18007fda0  cmp     qword ptr [rbp+var_18+8], 7
0x18007fda5  cmova   r8, [rbp+Source]; Source
0x18007fdaa  test    r15, r15
0x18007fdad  jz      short loc_18007FDB2
0x18007fdaf  mov     [r15], eax
0x18007fdb2  test    edi, edi
0x18007fdb4  jz      short loc_18007FE05
0x18007fdb6  test    r14, r14
0x18007fdb9  jz      short loc_18007FE05
0x18007fdbb  cmp     edi, eax
0x18007fdbd  jnb     short loc_18007FDCB
0x18007fdbf  mov     ebx, 80090028h
0x18007fdc4  mov     edx, 45Dh
0x18007fdc9  jmp     short loc_18007FE13
0x18007fdcb  mov     r9d, eax; SourceSize
0x18007fdce  mov     rdx, rdi; DestinationSize
0x18007fdd1  mov     rcx, r14; Destination
0x18007fdd4  call    memcpy_s_1
0x18007fdd9  test    eax, eax
0x18007fddb  jz      short loc_18007FDE4
0x18007fddd  mov     ebx, 8000FFFFh
0x18007fde2  jmp     short loc_18007FE27
0x18007fde4  lea     rcx, [rbp+var_40]; this
0x18007fde8  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007fded  nop
0x18007fdee  lea     rcx, [rbp+var_60]
0x18007fdf2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007fdf7  nop
0x18007fdf8  lea     rcx, [rbp+Source]
0x18007fdfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007fe01  xor     eax, eax
0x18007fe03  jmp     short loc_18007FE46
0x18007fe05  xor     ebx, ebx
0x18007fe07  jmp     short loc_18007FE27
0x18007fe09  mov     ebx, 80090027h
0x18007fe0e  mov     edx, 44Eh; void *
0x18007fe13  mov     r9d, ebx; char *
0x18007fe16  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007fe1d  mov     rcx, [rbp+28h]; this
0x18007fe21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fe26  nop
0x18007fe27  lea     rcx, [rbp+var_40]; this
0x18007fe2b  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007fe30  nop
0x18007fe31  lea     rcx, [rbp+var_60]
0x18007fe35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007fe3a  nop
0x18007fe3b  lea     rcx, [rbp+Source]
0x18007fe3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007fe44  mov     eax, ebx
0x18007fe46  mov     rcx, [rbp+var_8]
0x18007fe4a  xor     rcx, rsp; StackCookie
0x18007fe4d  call    __security_check_cookie
0x18007fe52  mov     rbx, [rsp+80h+arg_0]
0x18007fe5a  add     rsp, 80h
0x18007fe61  pop     r15
0x18007fe63  pop     r14
0x18007fe65  pop     rdi
0x18007fe66  pop     rsi
0x18007fe67  pop     rbp
0x18007fe68  retn
```
