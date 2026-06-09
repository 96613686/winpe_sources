# PackageManagerWrapper::UriVectorToStringArray(Windows::Foundation::Collections::IVector<Windows::Foundation::Uri *> *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> * *,uint *)

- ea: `0x18002907c`
- end: `0x180029390`
- name: `?UriVectorToStringArray@PackageManagerWrapper@@AEAAJPEAU?$IVector@PEAVUri@Foundation@Windows@@@Collections@Foundation@Windows@@PEAPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@PEAI@Z`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025cec`

## callees

- `0x180002fb4`
- `0x180002fcc`
- `0x18000d3dc`
- `0x18001db90`
- `0x18002907c`
- `0x18006b444`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002920f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800292ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002920f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800292ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800291dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800291dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002919e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002919e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800292bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029306`

## string_xrefs

- `0x1800290c6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180029291`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800292f0`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180029339`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180029379`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PackageManagerWrapper::UriVectorToStringArray(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rsi
  unsigned int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  _QWORD *v15; // rax
  unsigned int v16; // r14d
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v22; // eax
  __int64 v23; // rbx
  void *v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-40h]
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  _QWORD *v33; // [rsp+38h] [rbp-28h]
  __int128 v34; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v37; // [rsp+A0h] [rbp+40h] BYREF
  int v38; // [rsp+A4h] [rbp+44h]
  __int64 v39; // [rsp+A8h] [rbp+48h] BYREF

  v38 = HIDWORD(a1);
  v37 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v37);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = 0;
    v33 = 0;
    v10 = v37;
    if ( v37 )
    {
      v11 = v37;
      v12 = 8LL * v37;
      if ( !is_mul_ok(v37, 8u) )
        v12 = -1;
      v13 = __CFADD__(v12, 8);
      v14 = v12 + 8;
      if ( v13 )
        v14 = -1;
      v15 = operator new[](v14);
      if ( !v15
        || (*v15 = v11,
            v9 = v15 + 1,
            `eh vector constructor iterator'(
              v15 + 1,
              8u,
              (unsigned int)v11,
              wil::com_ptr_t<MsixPackage::Provisioning::Library::MsixAdapterCollection,wil::err_returncode_policy>::com_ptr_t<MsixPackage::Provisioning::Library::MsixAdapterCollection,wil::err_returncode_policy>,
              Common::AutoArray<unsigned short const *,&void Common::AutoArrayDeallocate<unsigned short const *>(unsigned short const * *)>::~AutoArray<unsigned short const *,&void Common::AutoArrayDeallocate<unsigned short const *>(unsigned short const * *)>),
            !v9) )
      {
        v8 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x617,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)0x8007000ELL,
          v31);
        goto LABEL_20;
      }
      Common::AutoArrayDeallocate<Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>>(0);
      v33 = v9;
      v16 = 0;
      v10 = v37;
      if ( v37 )
      {
        while ( 1 )
        {
          v39 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, v16, &v39);
          v8 = v17;
          if ( v17 < 0 )
            break;
          string = 0;
          v18 = v39;
          v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 128LL);
          WindowsDeleteString(0);
          string = 0;
          v20 = v19(v18, &string);
          v8 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x623,
              (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
              (const char *)(unsigned int)v20,
              v31);
            WindowsDeleteString(string);
            string = 0;
            v29 = v39;
            if ( v39 )
            {
              v39 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            goto LABEL_33;
          }
          v34 = 0;
          v35 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v22 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v34, StringRawBuffer);
          v8 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x625,
              (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
              (const char *)(unsigned int)v22,
              v31);
            if ( *((_QWORD *)&v34 + 1) )
              operator delete[](*((void **)&v34 + 1));
            WindowsDeleteString(string);
            string = 0;
            v28 = v39;
            if ( v39 )
            {
              v39 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            goto LABEL_33;
          }
          v23 = *((_QWORD *)&v34 + 1);
          v24 = (void *)v9[v16];
          if ( v24 != *((void **)&v34 + 1) )
          {
            operator delete[](v24);
            v9[v16] = v23;
          }
          WindowsDeleteString(string);
          string = 0;
          v25 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          ++v16;
          v10 = v37;
          if ( v16 >= v37 )
            goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x61C,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v17,
          v31);
        v30 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
LABEL_33:
        v26 = v9;
        goto LABEL_21;
      }
    }
LABEL_19:
    *a3 = v9;
    *a4 = v10;
    v8 = 0;
LABEL_20:
    v26 = 0;
LABEL_21:
    Common::AutoArrayDeallocate<Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>>(v26);
    return v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x611,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v7,
    v31);
  return v8;
}

```

## disassembly

```asm
0x18002907c  mov     [rsp-38h+arg_10], rbx
0x180029081  mov     [rsp-38h+arg_0], rcx
0x180029086  push    rbp
0x180029087  push    rsi
0x180029088  push    rdi
0x180029089  push    r12
0x18002908b  push    r13
0x18002908d  push    r14
0x18002908f  push    r15
0x180029091  mov     rbp, rsp
0x180029094  sub     rsp, 60h
0x180029098  mov     r12, r9
0x18002909b  mov     r13, r8
0x18002909e  mov     r15, rdx
0x1800290a1  xor     edi, edi
0x1800290a3  mov     dword ptr [rbp+arg_0], edi
0x1800290a6  mov     rax, [rdx]
0x1800290a9  lea     rdx, [rbp+arg_0]
0x1800290ad  mov     rcx, r15
0x1800290b0  mov     rax, [rax+38h]
0x1800290b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290b9  mov     ebx, eax
0x1800290bb  test    eax, eax
0x1800290bd  jns     short loc_1800290DC
0x1800290bf  mov     rcx, [rbp+38h]; this
0x1800290c3  mov     r9d, eax; char *
0x1800290c6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800290cd  mov     edx, 611h; void *
0x1800290d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800290d7  jmp     loc_18002926F
0x1800290dc  mov     rsi, rdi
0x1800290df  mov     [rbp+var_28], rdi
0x1800290e3  mov     eax, dword ptr [rbp+arg_0]
0x1800290e6  test    eax, eax
0x1800290e8  jz      loc_18002925E
0x1800290ee  mov     ebx, eax
0x1800290f0  mov     r14d, 8
0x1800290f6  mov     eax, r14d
0x1800290f9  mul     rbx
0x1800290fc  lea     rcx, [r14-9]
0x180029100  cmovb   rax, rcx
0x180029104  add     rax, r14
0x180029107  cmovb   rax, rcx
0x18002910b  mov     rcx, rax; unsigned __int64
0x18002910e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029113  test    rax, rax
0x180029116  jz      loc_18002936D
0x18002911c  mov     [rax], rbx
0x18002911f  lea     rsi, [rax+8]
0x180029123  lea     rax, ??1?$AutoArray@PEBG$1??$AutoArrayDeallocate@PEBG@Common@@YAXPEAPEBG@Z@Common@@QEAA@XZ; Common::AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>::~AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>(void)
0x18002912a  mov     qword ptr [rsp+60h+var_40], rax; int
0x18002912f  lea     r9, ??0?$com_ptr_t@VMsixAdapterCollection@Library@Provisioning@MsixPackage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180029136  mov     r8d, ebx; unsigned __int64
0x180029139  mov     edx, r14d; unsigned __int64
0x18002913c  mov     rcx, rsi; void *
0x18002913f  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180029144  test    rsi, rsi
0x180029147  jz      loc_18002936D
0x18002914d  xor     ecx, ecx
0x18002914f  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x180029154  mov     [rbp+var_28], rsi
0x180029158  mov     r14d, edi
0x18002915b  mov     eax, dword ptr [rbp+arg_0]
0x18002915e  test    eax, eax
0x180029160  jz      loc_18002925E
0x180029166  mov     [rbp+arg_8], rdi
0x18002916a  mov     rax, [r15]
0x18002916d  lea     r8, [rbp+arg_8]
0x180029171  mov     edx, r14d
0x180029174  mov     rcx, r15
0x180029177  mov     rax, [rax+30h]
0x18002917b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029180  mov     ebx, eax
0x180029182  test    eax, eax
0x180029184  js      loc_180029332
0x18002918a  mov     [rbp+string], rdi
0x18002918e  mov     rdi, [rbp+arg_8]
0x180029192  mov     rax, [rdi]
0x180029195  mov     rbx, [rax+80h]
0x18002919c  xor     ecx, ecx; string
0x18002919e  call    cs:__imp_WindowsDeleteString
0x1800291a5  nop     dword ptr [rax+rax+00h]
0x1800291aa  mov     [rbp+string], 0
0x1800291b2  lea     rdx, [rbp+string]
0x1800291b6  mov     rcx, rdi
0x1800291b9  mov     rax, rbx
0x1800291bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291c1  mov     ebx, eax
0x1800291c3  xor     edi, edi
0x1800291c5  test    eax, eax
0x1800291c7  js      loc_1800292E9
0x1800291cd  xorps   xmm0, xmm0
0x1800291d0  movups  [rbp+var_20], xmm0
0x1800291d4  mov     [rbp+var_10], edi
0x1800291d7  xor     edx, edx; length
0x1800291d9  mov     rcx, [rbp+string]; string
0x1800291dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800291e4  nop     dword ptr [rax+rax+00h]
0x1800291e9  mov     rdx, rax; Src
0x1800291ec  lea     rcx, [rbp+var_20]; this
0x1800291f0  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800291f5  mov     ebx, eax
0x1800291f7  test    eax, eax
0x1800291f9  js      loc_18002928A
0x1800291ff  mov     rbx, qword ptr [rbp+var_20+8]
0x180029203  mov     edi, r14d
0x180029206  mov     rcx, [rsi+rdi*8]
0x18002920a  cmp     rcx, rbx
0x18002920d  jz      short loc_18002921F
0x18002920f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029216  nop     dword ptr [rax+rax+00h]
0x18002921b  mov     [rsi+rdi*8], rbx
0x18002921f  mov     rcx, [rbp+string]; string
0x180029223  call    cs:__imp_WindowsDeleteString
0x18002922a  nop     dword ptr [rax+rax+00h]
0x18002922f  xor     edi, edi
0x180029231  mov     [rbp+string], rdi
0x180029235  mov     rcx, [rbp+arg_8]
0x180029239  test    rcx, rcx
0x18002923c  jz      short loc_18002924F
0x18002923e  mov     [rbp+arg_8], rdi
0x180029242  mov     rax, [rcx]
0x180029245  mov     rax, [rax+10h]
0x180029249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002924e  nop
0x18002924f  inc     r14d
0x180029252  mov     eax, dword ptr [rbp+arg_0]
0x180029255  cmp     r14d, eax
0x180029258  jb      loc_180029166
0x18002925e  mov     [r13+0], rsi
0x180029262  mov     [r12], eax
0x180029266  mov     ebx, edi
0x180029268  xor     ecx, ecx
0x18002926a  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x18002926f  mov     eax, ebx
0x180029271  mov     rbx, [rsp+60h+arg_10]
0x180029279  add     rsp, 60h
0x18002927d  pop     r15
0x18002927f  pop     r14
0x180029281  pop     r13
0x180029283  pop     r12
0x180029285  pop     rdi
0x180029286  pop     rsi
0x180029287  pop     rbp
0x180029288  retn
0x18002928a  mov     rcx, [rbp+38h]; this
0x18002928e  mov     r9d, eax; char *
0x180029291  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180029298  mov     edx, 625h; void *
0x18002929d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800292a2  nop
0x1800292a3  mov     rcx, qword ptr [rbp+var_20+8]
0x1800292a7  test    rcx, rcx
0x1800292aa  jz      short loc_1800292B9
0x1800292ac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800292b3  nop     dword ptr [rax+rax+00h]
0x1800292b8  nop
0x1800292b9  mov     rcx, [rbp+string]; string
0x1800292bd  call    cs:__imp_WindowsDeleteString
0x1800292c4  nop     dword ptr [rax+rax+00h]
0x1800292c9  mov     [rbp+string], rdi
0x1800292cd  mov     rcx, [rbp+arg_8]
0x1800292d1  test    rcx, rcx
0x1800292d4  jz      short loc_1800292E7
0x1800292d6  mov     [rbp+arg_8], rdi
0x1800292da  mov     rax, [rcx]
0x1800292dd  mov     rax, [rax+10h]
0x1800292e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292e6  nop
0x1800292e7  jmp     short loc_180029365
0x1800292e9  mov     rcx, [rbp+38h]; this
0x1800292ed  mov     r9d, eax; char *
0x1800292f0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800292f7  mov     edx, 623h; void *
0x1800292fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029301  nop
0x180029302  mov     rcx, [rbp+string]; string
0x180029306  call    cs:__imp_WindowsDeleteString
0x18002930d  nop     dword ptr [rax+rax+00h]
0x180029312  mov     [rbp+string], rdi
0x180029316  mov     rcx, [rbp+arg_8]
0x18002931a  test    rcx, rcx
0x18002931d  jz      short loc_180029330
0x18002931f  mov     [rbp+arg_8], rdi
0x180029323  mov     rax, [rcx]
0x180029326  mov     rax, [rax+10h]
0x18002932a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002932f  nop
0x180029330  jmp     short loc_180029365
0x180029332  mov     rcx, [rbp+38h]; this
0x180029336  mov     r9d, eax; char *
0x180029339  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180029340  mov     edx, 61Ch; void *
0x180029345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002934a  nop
0x18002934b  mov     rcx, [rbp+arg_8]
0x18002934f  test    rcx, rcx
0x180029352  jz      short loc_180029365
0x180029354  mov     [rbp+arg_8], rdi
0x180029358  mov     rax, [rcx]
0x18002935b  mov     rax, [rax+10h]
0x18002935f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029364  nop
0x180029365  mov     rcx, rsi
0x180029368  jmp     loc_18002926A
0x18002936d  mov     rcx, [rbp+38h]; this
0x180029371  mov     ebx, 8007000Eh
0x180029376  mov     r9d, ebx; char *
0x180029379  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180029380  mov     edx, 617h; void *
0x180029385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002938a  jmp     loc_180029268
```
