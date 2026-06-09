# PackageManagerWrapper::StringVectorToStringArray(Windows::Foundation::Collections::IVector<HSTRING__ *> *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> * *,uint *)

- ea: `0x180028518`
- end: `0x18002875f`
- name: `?StringVectorToStringArray@PackageManagerWrapper@@AEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@PEAI@Z`
- size: `583`
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
- `0x180028518`
- `0x18006b444`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002867a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800286f5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002867a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800286f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002864f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002864f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002860e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002868e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002860e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002868e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028720`

## string_xrefs

- `0x180028564`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800286da`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002870a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180028748`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageManagerWrapper::StringVectorToStringArray(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rdi
  unsigned int v10; // eax
  __int64 v11; // rbx
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, _QWORD, HSTRING *); // rbx
  int v18; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v20; // eax
  __int64 v21; // rbx
  void *v22; // rcx
  _QWORD *v23; // rcx
  int v25; // [rsp+20h] [rbp-30h]
  __int128 v26; // [rsp+38h] [rbp-18h] BYREF
  int v27; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v29; // [rsp+90h] [rbp+40h] BYREF
  int v30; // [rsp+94h] [rbp+44h]
  HSTRING string; // [rsp+98h] [rbp+48h] BYREF

  v30 = HIDWORD(a1);
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v29);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = 0;
    v10 = v29;
    if ( v29 )
    {
      v11 = v29;
      v12 = 8LL * v29;
      if ( !is_mul_ok(v29, 8u) )
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
          (void *)0x63D,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)0x8007000ELL,
          v25);
        goto LABEL_17;
      }
      Common::AutoArrayDeallocate<Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>>(0);
      v16 = 0;
      v10 = v29;
      if ( v29 )
      {
        while ( 1 )
        {
          string = 0;
          v17 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a2 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          v18 = v17(a2, (unsigned int)v16, &string);
          v8 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x643,
              (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
              (const char *)(unsigned int)v18,
              v25);
            goto LABEL_23;
          }
          v26 = 0;
          v27 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v20 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v26, StringRawBuffer);
          v8 = v20;
          if ( v20 < 0 )
            break;
          v21 = *((_QWORD *)&v26 + 1);
          v22 = (void *)v9[v16];
          if ( v22 != *((void **)&v26 + 1) )
          {
            operator delete[](v22);
            v9[v16] = v21;
          }
          WindowsDeleteString(string);
          v16 = (unsigned int)(v16 + 1);
          v10 = v29;
          if ( (unsigned int)v16 >= v29 )
            goto LABEL_16;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x646,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v20,
          v25);
        if ( *((_QWORD *)&v26 + 1) )
          operator delete[](*((void **)&v26 + 1));
LABEL_23:
        WindowsDeleteString(string);
        string = 0;
        v23 = v9;
        goto LABEL_18;
      }
    }
LABEL_16:
    *a3 = v9;
    *a4 = v10;
    v8 = 0;
LABEL_17:
    v23 = 0;
LABEL_18:
    Common::AutoArrayDeallocate<Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>>(v23);
    return v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x637,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v7,
    v25);
  return v8;
}

```

## disassembly

```asm
0x180028518  mov     [rsp-38h+arg_10], rbx
0x18002851d  mov     [rsp-38h+arg_0], rcx
0x180028522  push    rbp
0x180028523  push    rsi
0x180028524  push    rdi
0x180028525  push    r12
0x180028527  push    r13
0x180028529  push    r14
0x18002852b  push    r15
0x18002852d  mov     rbp, rsp
0x180028530  sub     rsp, 50h
0x180028534  mov     r12, r9
0x180028537  mov     r13, r8
0x18002853a  mov     r15, rdx
0x18002853d  mov     dword ptr [rbp+arg_0], 0
0x180028544  mov     rax, [rdx]
0x180028547  lea     rdx, [rbp+arg_0]
0x18002854b  mov     rcx, r15
0x18002854e  mov     rax, [rax+38h]
0x180028552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028557  mov     ebx, eax
0x180028559  test    eax, eax
0x18002855b  jns     short loc_18002857A
0x18002855d  mov     rcx, [rbp+38h]; this
0x180028561  mov     r9d, eax; char *
0x180028564  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002856b  mov     edx, 637h; void *
0x180028570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028575  jmp     loc_1800286B8
0x18002857a  xor     edi, edi
0x18002857c  mov     [rbp+var_20], rdi
0x180028580  mov     eax, dword ptr [rbp+arg_0]
0x180028583  test    eax, eax
0x180028585  jz      loc_1800286A7
0x18002858b  mov     ebx, eax
0x18002858d  lea     esi, [rdi+8]
0x180028590  mov     eax, esi
0x180028592  mul     rbx
0x180028595  lea     rcx, [rdi-1]
0x180028599  cmovb   rax, rcx
0x18002859d  add     rax, rsi
0x1800285a0  cmovb   rax, rcx
0x1800285a4  mov     rcx, rax; unsigned __int64
0x1800285a7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800285ac  test    rax, rax
0x1800285af  jz      loc_18002873C
0x1800285b5  mov     [rax], rbx
0x1800285b8  lea     rdi, [rax+8]
0x1800285bc  lea     rax, ??1?$AutoArray@PEBG$1??$AutoArrayDeallocate@PEBG@Common@@YAXPEAPEBG@Z@Common@@QEAA@XZ; Common::AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>::~AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>(void)
0x1800285c3  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800285c8  lea     r9, ??0?$com_ptr_t@VMsixAdapterCollection@Library@Provisioning@MsixPackage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800285cf  mov     r8d, ebx; unsigned __int64
0x1800285d2  mov     edx, esi; unsigned __int64
0x1800285d4  mov     rcx, rdi; void *
0x1800285d7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800285dc  test    rdi, rdi
0x1800285df  jz      loc_18002873C
0x1800285e5  xor     ecx, ecx
0x1800285e7  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x1800285ec  mov     [rbp+var_20], rdi
0x1800285f0  xor     esi, esi
0x1800285f2  mov     eax, dword ptr [rbp+arg_0]
0x1800285f5  test    eax, eax
0x1800285f7  jz      loc_1800286A7
0x1800285fd  mov     [rbp+string], 0
0x180028605  mov     rax, [r15]
0x180028608  mov     rbx, [rax+30h]
0x18002860c  xor     ecx, ecx; string
0x18002860e  call    cs:__imp_WindowsDeleteString
0x180028615  nop     dword ptr [rax+rax+00h]
0x18002861a  mov     [rbp+string], 0
0x180028622  lea     r8, [rbp+string]
0x180028626  mov     edx, esi
0x180028628  mov     rcx, r15
0x18002862b  mov     rax, rbx
0x18002862e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028633  mov     ebx, eax
0x180028635  test    eax, eax
0x180028637  js      loc_180028703
0x18002863d  xor     eax, eax
0x18002863f  xorps   xmm0, xmm0
0x180028642  movups  [rbp+var_18], xmm0
0x180028646  mov     [rbp+var_8], eax
0x180028649  xor     edx, edx; length
0x18002864b  mov     rcx, [rbp+string]; string
0x18002864f  call    cs:__imp_WindowsGetStringRawBuffer
0x180028656  nop     dword ptr [rax+rax+00h]
0x18002865b  mov     rdx, rax; Src
0x18002865e  lea     rcx, [rbp+var_18]; this
0x180028662  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180028667  mov     ebx, eax
0x180028669  test    eax, eax
0x18002866b  js      short loc_1800286D3
0x18002866d  mov     rbx, qword ptr [rbp+var_18+8]
0x180028671  mov     rcx, [rdi+rsi*8]
0x180028675  cmp     rcx, rbx
0x180028678  jz      short loc_18002868A
0x18002867a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028681  nop     dword ptr [rax+rax+00h]
0x180028686  mov     [rdi+rsi*8], rbx
0x18002868a  mov     rcx, [rbp+string]; string
0x18002868e  call    cs:__imp_WindowsDeleteString
0x180028695  nop     dword ptr [rax+rax+00h]
0x18002869a  inc     esi
0x18002869c  mov     eax, dword ptr [rbp+arg_0]
0x18002869f  cmp     esi, eax
0x1800286a1  jb      loc_1800285FD
0x1800286a7  mov     [r13+0], rdi
0x1800286ab  mov     [r12], eax
0x1800286af  xor     ebx, ebx
0x1800286b1  xor     ecx, ecx
0x1800286b3  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x1800286b8  mov     eax, ebx
0x1800286ba  mov     rbx, [rsp+50h+arg_10]
0x1800286c2  add     rsp, 50h
0x1800286c6  pop     r15
0x1800286c8  pop     r14
0x1800286ca  pop     r13
0x1800286cc  pop     r12
0x1800286ce  pop     rdi
0x1800286cf  pop     rsi
0x1800286d0  pop     rbp
0x1800286d1  retn
0x1800286d3  mov     rcx, [rbp+38h]; this
0x1800286d7  mov     r9d, eax; char *
0x1800286da  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800286e1  mov     edx, 646h; void *
0x1800286e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286eb  nop
0x1800286ec  mov     rcx, qword ptr [rbp+var_18+8]
0x1800286f0  test    rcx, rcx
0x1800286f3  jz      short loc_18002871C
0x1800286f5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800286fc  nop     dword ptr [rax+rax+00h]
0x180028701  jmp     short loc_18002871C
0x180028703  mov     rcx, [rbp+38h]; this
0x180028707  mov     r9d, eax; char *
0x18002870a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028711  mov     edx, 643h; void *
0x180028716  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002871b  nop
0x18002871c  mov     rcx, [rbp+string]; string
0x180028720  call    cs:__imp_WindowsDeleteString
0x180028727  nop     dword ptr [rax+rax+00h]
0x18002872c  mov     [rbp+string], 0
0x180028734  mov     rcx, rdi
0x180028737  jmp     loc_1800286B3
0x18002873c  mov     rcx, [rbp+38h]; this
0x180028740  mov     ebx, 8007000Eh
0x180028745  mov     r9d, ebx; char *
0x180028748  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002874f  mov     edx, 63Dh; void *
0x180028754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028759  jmp     loc_1800286B1
```
