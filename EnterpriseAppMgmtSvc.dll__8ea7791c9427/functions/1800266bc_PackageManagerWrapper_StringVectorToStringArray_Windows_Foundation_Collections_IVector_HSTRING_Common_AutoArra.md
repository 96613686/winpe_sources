# PackageManagerWrapper::StringVectorToStringArray(Windows::Foundation::Collections::IVector<HSTRING__ *> *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> * *,uint *)

- ea: `0x1800266bc`
- end: `0x1800268db`
- name: `?StringVectorToStringArray@PackageManagerWrapper@@AEAAJPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@PEAI@Z`
- size: `543`
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
- `0x1800266bc`
- `0x180065a64`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180026812`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026880`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026812`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800267ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800267ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800267b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800268a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800267b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026820`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800268a5`

## string_xrefs

- `0x180026708`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180026865`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002688f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800268c4`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageManagerWrapper::StringVectorToStringArray(
        __int64 a1,
        __int64 a2,
        char **a3,
        unsigned int *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  char *v9; // rdi
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
  char *v23; // rcx
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
          v22 = *(void **)&v9[8 * v16];
          if ( v22 != *((void **)&v26 + 1) )
          {
            operator delete[](v22);
            *(_QWORD *)&v9[8 * v16] = v21;
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
0x1800266bc  mov     [rsp-38h+arg_10], rbx
0x1800266c1  mov     [rsp-38h+arg_0], rcx
0x1800266c6  push    rbp
0x1800266c7  push    rsi
0x1800266c8  push    rdi
0x1800266c9  push    r12
0x1800266cb  push    r13
0x1800266cd  push    r14
0x1800266cf  push    r15
0x1800266d1  mov     rbp, rsp
0x1800266d4  sub     rsp, 50h
0x1800266d8  mov     r12, r9
0x1800266db  mov     r13, r8
0x1800266de  mov     r15, rdx
0x1800266e1  mov     dword ptr [rbp+arg_0], 0
0x1800266e8  mov     rax, [rdx]
0x1800266eb  lea     rdx, [rbp+arg_0]
0x1800266ef  mov     rcx, r15
0x1800266f2  mov     rax, [rax+38h]
0x1800266f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266fb  mov     ebx, eax
0x1800266fd  test    eax, eax
0x1800266ff  jns     short loc_18002671E
0x180026701  mov     rcx, [rbp+38h]; this
0x180026705  mov     r9d, eax; char *
0x180026708  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002670f  mov     edx, 637h; void *
0x180026714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026719  jmp     loc_180026844
0x18002671e  xor     edi, edi
0x180026720  mov     [rbp+var_20], rdi
0x180026724  mov     eax, dword ptr [rbp+arg_0]
0x180026727  test    eax, eax
0x180026729  jz      loc_180026833
0x18002672f  mov     ebx, eax
0x180026731  lea     esi, [rdi+8]
0x180026734  mov     eax, esi
0x180026736  mul     rbx
0x180026739  lea     rcx, [rdi-1]
0x18002673d  cmovb   rax, rcx
0x180026741  add     rax, rsi
0x180026744  cmovb   rax, rcx
0x180026748  mov     rcx, rax; unsigned __int64
0x18002674b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026750  test    rax, rax
0x180026753  jz      loc_1800268B8
0x180026759  mov     [rax], rbx
0x18002675c  lea     rdi, [rax+8]
0x180026760  lea     rax, ??1?$AutoArray@PEBG$1??$AutoArrayDeallocate@PEBG@Common@@YAXPEAPEBG@Z@Common@@QEAA@XZ; Common::AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>::~AutoArray<ushort const *,&Common::AutoArrayDeallocate<ushort const *>(ushort const * *)>(void)
0x180026767  mov     qword ptr [rsp+50h+var_30], rax; int
0x18002676c  lea     r9, ??0?$com_ptr_t@VMsixAdapterCollection@Library@Provisioning@MsixPackage@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x180026773  mov     r8d, ebx; unsigned __int64
0x180026776  mov     edx, esi; unsigned __int64
0x180026778  mov     rcx, rdi; void *
0x18002677b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180026780  test    rdi, rdi
0x180026783  jz      loc_1800268B8
0x180026789  xor     ecx, ecx
0x18002678b  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x180026790  mov     [rbp+var_20], rdi
0x180026794  xor     esi, esi
0x180026796  mov     eax, dword ptr [rbp+arg_0]
0x180026799  test    eax, eax
0x18002679b  jz      loc_180026833
0x1800267a1  mov     [rbp+string], 0
0x1800267a9  mov     rax, [r15]
0x1800267ac  mov     rbx, [rax+30h]
0x1800267b0  xor     ecx, ecx; string
0x1800267b2  call    cs:__imp_WindowsDeleteString
0x1800267b8  mov     [rbp+string], 0
0x1800267c0  lea     r8, [rbp+string]
0x1800267c4  mov     edx, esi
0x1800267c6  mov     rcx, r15
0x1800267c9  mov     rax, rbx
0x1800267cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267d1  mov     ebx, eax
0x1800267d3  test    eax, eax
0x1800267d5  js      loc_180026888
0x1800267db  xor     eax, eax
0x1800267dd  xorps   xmm0, xmm0
0x1800267e0  movups  [rbp+var_18], xmm0
0x1800267e4  mov     [rbp+var_8], eax
0x1800267e7  xor     edx, edx; length
0x1800267e9  mov     rcx, [rbp+string]; string
0x1800267ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800267f3  mov     rdx, rax; Src
0x1800267f6  lea     rcx, [rbp+var_18]; this
0x1800267fa  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800267ff  mov     ebx, eax
0x180026801  test    eax, eax
0x180026803  js      short loc_18002685E
0x180026805  mov     rbx, qword ptr [rbp+var_18+8]
0x180026809  mov     rcx, [rdi+rsi*8]
0x18002680d  cmp     rcx, rbx
0x180026810  jz      short loc_18002681C
0x180026812  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026818  mov     [rdi+rsi*8], rbx
0x18002681c  mov     rcx, [rbp+string]; string
0x180026820  call    cs:__imp_WindowsDeleteString
0x180026826  inc     esi
0x180026828  mov     eax, dword ptr [rbp+arg_0]
0x18002682b  cmp     esi, eax
0x18002682d  jb      loc_1800267A1
0x180026833  mov     [r13+0], rdi
0x180026837  mov     [r12], eax
0x18002683b  xor     ebx, ebx
0x18002683d  xor     ecx, ecx
0x18002683f  call    ??$AutoArrayDeallocate@V?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Common@@YAXPEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@0@@Z; Common::AutoArrayDeallocate<Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)>>(Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> *)
0x180026844  mov     eax, ebx
0x180026846  mov     rbx, [rsp+50h+arg_10]
0x18002684e  add     rsp, 50h
0x180026852  pop     r15
0x180026854  pop     r14
0x180026856  pop     r13
0x180026858  pop     r12
0x18002685a  pop     rdi
0x18002685b  pop     rsi
0x18002685c  pop     rbp
0x18002685d  retn
0x18002685e  mov     rcx, [rbp+38h]; this
0x180026862  mov     r9d, eax; char *
0x180026865  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002686c  mov     edx, 646h; void *
0x180026871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026876  nop
0x180026877  mov     rcx, qword ptr [rbp+var_18+8]
0x18002687b  test    rcx, rcx
0x18002687e  jz      short loc_1800268A1
0x180026880  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026886  jmp     short loc_1800268A1
0x180026888  mov     rcx, [rbp+38h]; this
0x18002688c  mov     r9d, eax; char *
0x18002688f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026896  mov     edx, 643h; void *
0x18002689b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268a0  nop
0x1800268a1  mov     rcx, [rbp+string]; string
0x1800268a5  call    cs:__imp_WindowsDeleteString
0x1800268ab  mov     [rbp+string], 0
0x1800268b3  mov     rcx, rdi
0x1800268b6  jmp     short loc_18002683F
0x1800268b8  mov     rcx, [rbp+38h]; this
0x1800268bc  mov     ebx, 8007000Eh
0x1800268c1  mov     r9d, ebx; char *
0x1800268c4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800268cb  mov     edx, 63Dh; void *
0x1800268d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268d5  jmp     loc_18002683D
```
