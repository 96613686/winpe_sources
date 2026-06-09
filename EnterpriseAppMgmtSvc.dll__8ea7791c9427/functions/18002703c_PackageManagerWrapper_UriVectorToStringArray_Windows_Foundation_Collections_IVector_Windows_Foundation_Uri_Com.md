# PackageManagerWrapper::UriVectorToStringArray(Windows::Foundation::Collections::IVector<Windows::Foundation::Uri *> *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> * *,uint *)

- ea: `0x18002703c`
- end: `0x180027321`
- name: `?UriVectorToStringArray@PackageManagerWrapper@@AEAAJPEAU?$IVector@PEAVUri@Foundation@Windows@@@Collections@Foundation@Windows@@PEAPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@PEAI@Z`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800242c0`

## callees

- `0x180002f64`
- `0x180002f7c`
- `0x18000cfe8`
- `0x18001caf0`
- `0x18002703c`
- `0x180065a64`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800271bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002724f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800271bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002724f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002715e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002725a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002715e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002725a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002729d`

## string_xrefs

- `0x180027086`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180027234`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180027287`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800272ca`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002730a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PackageManagerWrapper::UriVectorToStringArray(__int64 a1, __int64 a2, char **a3, unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char *v9; // rsi
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
  char *v26; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-40h]
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  char *v33; // [rsp+38h] [rbp-28h]
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
            v9 = (char *)(v15 + 1),
            `eh vector constructor iterator'(
              v15 + 1,
              8u,
              (unsigned int)v11,
              (void (*)(void *))wil::com_ptr_t<MsixPackage::Provisioning::Library::MsixAdapterCollection,wil::err_returncode_policy>::com_ptr_t<MsixPackage::Provisioning::Library::MsixAdapterCollection,wil::err_returncode_policy>,
              (void (*)(void *))Common::AutoArray<unsigned short const *,&void Common::AutoArrayDeallocate<unsigned short const *>(unsigned short const * *)>::~AutoArray<unsigned short const *,&void Common::AutoArrayDeallocate<unsigned short const *>(unsigned short const * *)>),
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
          v24 = *(void **)&v9[8 * v16];
          if ( v24 != *((void **)&v34 + 1) )
          {
            operator delete[](v24);
            *(_QWORD *)&v9[8 * v16] = v23;
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
0x18002703c  mov     [rsp-38h+arg_10], rbx
0x180027041  mov     [rsp-38h+arg_0], rcx
0x180027046  push    rbp
0x180027047  push    rsi
0x180027048  push    rdi
0x180027049  push    r12
0x18002704b  push    r13
0x18002704d  push    r14
0x18002704f  push    r15
0x180027051  mov     rbp, rsp
0x180027054  sub     rsp, 60h
0x180027058  mov     r12, r9
0x18002705b  mov     r13, r8
0x18002705e  mov     r15, rdx
0x180027061  xor     edi, edi
0x180027063  mov     dword ptr [rbp+arg_0], edi
0x180027066  mov     rax, [rdx]
0x180027069  lea     rdx, [rbp+arg_0]
0x18002706d  mov     rcx, r15
0x180027070  mov     rax, [rax+38h]
0x180027074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027079  mov     ebx, eax
0x18002707b  test    eax, eax
0x18002707d  jns     short loc_18002709C
0x18002707f  mov     rcx, [rbp+38h]; this
0x180027083  mov     r9d, eax; char *
0x180027086  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002708d  mov     edx, 611h; void *
0x180027092  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027097  jmp     loc_180027213
0x18002709c  mov     rsi, rdi
0x18002709f  mov     [rbp+var_28], rdi
0x1800270a3  mov     eax, dword ptr [rbp+arg_0]
0x1800270a6  test    eax, eax
0x1800270a8  jz      loc_180027202
0x1800270ae  mov     ebx, eax
0x1800270b0  mov     r14d, 8
0x1800270b6  mov     eax, r14d
0x1800270b9  mul     rbx
0x1800270bc  lea     rcx, [r14-9]
0x1800270c0  cmovb   rax, rcx
0x1800270c4  add     rax, r14
0x1800270c7  cmovb   rax, rcx
0x1800270cb  mov     rcx, rax; unsigned __int64
0x1800270ce  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800270d3  test    rax, rax
0x1800270d6  jz      loc_1800272FE
0x1800270dc  mov     [rax], rbx
0x1800270df  lea     rsi, [rax+8]
0x1800270e3  lea     rax, ??1?$AutoArray@PEBG$1??$AutoArrayDeallocate@PEBG@Common@@YAXPEAPEBG@Z@Common@@QEAA@XZ; Common::AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>::~AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>(void)
0x1800270ea  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800270ef  lea     r9, ??0?$com_ptr_t@VMsixAdapterCollection@Library@Provisioning@MsixPackage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800270f6  mov     r8d, ebx; unsigned __int64
0x1800270f9  mov     edx, r14d; unsigned __int64
0x1800270fc  mov     rcx, rsi; void *
0x1800270ff  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180027104  test    rsi, rsi
0x180027107  jz      loc_1800272FE
0x18002710d  xor     ecx, ecx
0x18002710f  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x180027114  mov     [rbp+var_28], rsi
0x180027118  mov     r14d, edi
0x18002711b  mov     eax, dword ptr [rbp+arg_0]
0x18002711e  test    eax, eax
0x180027120  jz      loc_180027202
0x180027126  mov     [rbp+arg_8], rdi
0x18002712a  mov     rax, [r15]
0x18002712d  lea     r8, [rbp+arg_8]
0x180027131  mov     edx, r14d
0x180027134  mov     rcx, r15
0x180027137  mov     rax, [rax+30h]
0x18002713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027140  mov     ebx, eax
0x180027142  test    eax, eax
0x180027144  js      loc_1800272C3
0x18002714a  mov     [rbp+string], rdi
0x18002714e  mov     rdi, [rbp+arg_8]
0x180027152  mov     rax, [rdi]
0x180027155  mov     rbx, [rax+80h]
0x18002715c  xor     ecx, ecx; string
0x18002715e  call    cs:__imp_WindowsDeleteString
0x180027164  mov     [rbp+string], 0
0x18002716c  lea     rdx, [rbp+string]
0x180027170  mov     rcx, rdi
0x180027173  mov     rax, rbx
0x180027176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002717b  mov     ebx, eax
0x18002717d  xor     edi, edi
0x18002717f  test    eax, eax
0x180027181  js      loc_180027280
0x180027187  xorps   xmm0, xmm0
0x18002718a  movups  [rbp+var_20], xmm0
0x18002718e  mov     [rbp+var_10], edi
0x180027191  xor     edx, edx; length
0x180027193  mov     rcx, [rbp+string]; string
0x180027197  call    cs:__imp_WindowsGetStringRawBuffer
0x18002719d  mov     rdx, rax; Src
0x1800271a0  lea     rcx, [rbp+var_20]; this
0x1800271a4  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800271a9  mov     ebx, eax
0x1800271ab  test    eax, eax
0x1800271ad  js      short loc_18002722D
0x1800271af  mov     rbx, qword ptr [rbp+var_20+8]
0x1800271b3  mov     edi, r14d
0x1800271b6  mov     rcx, [rsi+rdi*8]
0x1800271ba  cmp     rcx, rbx
0x1800271bd  jz      short loc_1800271C9
0x1800271bf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800271c5  mov     [rsi+rdi*8], rbx
0x1800271c9  mov     rcx, [rbp+string]; string
0x1800271cd  call    cs:__imp_WindowsDeleteString
0x1800271d3  xor     edi, edi
0x1800271d5  mov     [rbp+string], rdi
0x1800271d9  mov     rcx, [rbp+arg_8]
0x1800271dd  test    rcx, rcx
0x1800271e0  jz      short loc_1800271F3
0x1800271e2  mov     [rbp+arg_8], rdi
0x1800271e6  mov     rax, [rcx]
0x1800271e9  mov     rax, [rax+10h]
0x1800271ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271f2  nop
0x1800271f3  inc     r14d
0x1800271f6  mov     eax, dword ptr [rbp+arg_0]
0x1800271f9  cmp     r14d, eax
0x1800271fc  jb      loc_180027126
0x180027202  mov     [r13+0], rsi
0x180027206  mov     [r12], eax
0x18002720a  mov     ebx, edi
0x18002720c  xor     ecx, ecx
0x18002720e  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x180027213  mov     eax, ebx
0x180027215  mov     rbx, [rsp+60h+arg_10]
0x18002721d  add     rsp, 60h
0x180027221  pop     r15
0x180027223  pop     r14
0x180027225  pop     r13
0x180027227  pop     r12
0x180027229  pop     rdi
0x18002722a  pop     rsi
0x18002722b  pop     rbp
0x18002722c  retn
0x18002722d  mov     rcx, [rbp+38h]; this
0x180027231  mov     r9d, eax; char *
0x180027234  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002723b  mov     edx, 625h; void *
0x180027240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027245  nop
0x180027246  mov     rcx, qword ptr [rbp+var_20+8]
0x18002724a  test    rcx, rcx
0x18002724d  jz      short loc_180027256
0x18002724f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180027255  nop
0x180027256  mov     rcx, [rbp+string]; string
0x18002725a  call    cs:__imp_WindowsDeleteString
0x180027260  mov     [rbp+string], rdi
0x180027264  mov     rcx, [rbp+arg_8]
0x180027268  test    rcx, rcx
0x18002726b  jz      short loc_18002727E
0x18002726d  mov     [rbp+arg_8], rdi
0x180027271  mov     rax, [rcx]
0x180027274  mov     rax, [rax+10h]
0x180027278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002727d  nop
0x18002727e  jmp     short loc_1800272F6
0x180027280  mov     rcx, [rbp+38h]; this
0x180027284  mov     r9d, eax; char *
0x180027287  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002728e  mov     edx, 623h; void *
0x180027293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027298  nop
0x180027299  mov     rcx, [rbp+string]; string
0x18002729d  call    cs:__imp_WindowsDeleteString
0x1800272a3  mov     [rbp+string], rdi
0x1800272a7  mov     rcx, [rbp+arg_8]
0x1800272ab  test    rcx, rcx
0x1800272ae  jz      short loc_1800272C1
0x1800272b0  mov     [rbp+arg_8], rdi
0x1800272b4  mov     rax, [rcx]
0x1800272b7  mov     rax, [rax+10h]
0x1800272bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272c0  nop
0x1800272c1  jmp     short loc_1800272F6
0x1800272c3  mov     rcx, [rbp+38h]; this
0x1800272c7  mov     r9d, eax; char *
0x1800272ca  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800272d1  mov     edx, 61Ch; void *
0x1800272d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272db  nop
0x1800272dc  mov     rcx, [rbp+arg_8]
0x1800272e0  test    rcx, rcx
0x1800272e3  jz      short loc_1800272F6
0x1800272e5  mov     [rbp+arg_8], rdi
0x1800272e9  mov     rax, [rcx]
0x1800272ec  mov     rax, [rax+10h]
0x1800272f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272f5  nop
0x1800272f6  mov     rcx, rsi
0x1800272f9  jmp     loc_18002720E
0x1800272fe  mov     rcx, [rbp+38h]; this
0x180027302  mov     ebx, 8007000Eh
0x180027307  mov     r9d, ebx; char *
0x18002730a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180027311  mov     edx, 617h; void *
0x180027316  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002731b  jmp     loc_18002720C
```
