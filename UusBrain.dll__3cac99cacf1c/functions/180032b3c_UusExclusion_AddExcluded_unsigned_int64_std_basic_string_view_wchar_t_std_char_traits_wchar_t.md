# UusExclusion::AddExcluded(unsigned __int64,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180032b3c`
- end: `0x180032fbf`
- name: `?AddExcluded@UusExclusion@@QEAAX_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `1155`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180036a04`

## callees

- `0x1800089f4`
- `0x180029344`
- `0x180029644`
- `0x1800296cc`
- `0x180029708`
- `0x1800298d4`
- `0x18002a9c8`
- `0x180032b3c`
- `0x180033264`
- `0x180033470`
- `0x18003e2f4`
- `0x18003e514`
- `0x1800427d0`
- `0x180042bfc`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x180032f95`: `JSON field is not expected type.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall UusExclusion::AddExcluded(UusExclusion *this, unsigned __int64 a2, __int128 *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  double *v11; // rax
  __int64 result; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  __int64 String; // r13
  void *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r13
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  char *v23; // rax
  bool v24; // cl
  __int64 v25; // rcx
  __int64 v26; // rax
  _QWORD *v27; // [rsp+28h] [rbp-100h] BYREF
  void **v28; // [rsp+30h] [rbp-F8h] BYREF
  unsigned __int64 v29; // [rsp+38h] [rbp-F0h]
  __int128 v30; // [rsp+40h] [rbp-E8h] BYREF
  _QWORD v31[4]; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v32; // [rsp+70h] [rbp-B8h] BYREF
  _OWORD v33[2]; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+A0h] [rbp-88h] BYREF
  char v35[32]; // [rsp+B8h] [rbp-70h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-50h] BYREF

  *(_QWORD *)&v30 = a3;
  v31[2] = a3;
  v27 = 0;
  web::json::value::value((web::json::value *)&v27);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 8LL))(
         *((_QWORD *)this + 1),
         UusExclusion::_keyExclusionListLocal) )
  {
    v6 = web::json::value::at((char *)this + 8, UusExclusion::_keyExclusionListLocal);
    web::json::value::operator=(&v27, v6);
    if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v27 + 88LL))(v27) != 4 )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "JSON field is not expected type.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v7 = (_QWORD *)web::json::value::at((char *)this + 8, UusExclusion::_keyExclusionListLocal);
    v8 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 152LL))(*v7);
    v9 = (_QWORD *)*v8;
    v10 = (_QWORD *)v8[1];
    while ( v9 != v10 )
    {
      v36 = 0;
      (**(void (__fastcall ***)(_QWORD, __int64 *))*v9)(*v9, &v36);
      (**(void (__fastcall ***)(__int64, _QWORD *))v36)(v36, v31);
      v11 = UusExclusion::ParseVersionRangeFromValue((double *)v33, v31);
      if ( a2 >= *(_QWORD *)v11 && a2 <= *((_QWORD *)v11 + 1) )
      {
        v28 = &UusVersion::`vftable';
        v29 = a2;
        v30 = *a3;
        result = uus::UndockedUpdateCoreTelemetry::UusFailoverVersionExcludedNoOp(&v28, &v30);
        if ( v36 )
          result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 192LL))(v36, 1);
        if ( v27 )
          return (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v27 + 192LL))(v27, 1);
        return result;
      }
      if ( v36 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 192LL))(v36, 1);
      ++v9;
    }
  }
  else
  {
    v13 = operator new(0x20u);
    *v13 = &web::json::details::_Array::`vftable';
    v13[1] = 0;
    v13[2] = 0;
    v13[3] = 0;
    v14 = v27;
    v27 = v13;
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v14 + 192LL))(v14, 1);
  }
  v31[0] = &UusVersion::`vftable';
  v31[1] = a2;
  String = UusVersion::GetString(v31, v35);
  v28 = (void **)String;
  v16 = operator new(0x30u);
  v33[0] = *(_OWORD *)String;
  v33[1] = *(_OWORD *)(String + 16);
  *(_QWORD *)(String + 16) = 0;
  *(_QWORD *)(String + 24) = 7;
  *(_WORD *)String = 0;
  v17 = web::json::details::_String::_String(v16, v33);
  v32 = v17;
  std::wstring::_Tidy_deallocate(String);
  v18 = (*(__int64 (__fastcall **)(_QWORD *))(*v27 + 184LL))(v27);
  if ( (*(unsigned int (__fastcall **)(_QWORD *))(*v27 + 88LL))(v27) != 5 )
    goto LABEL_20;
  v19 = operator new(0x20u);
  *v19 = &web::json::details::_Array::`vftable';
  v19[1] = 0;
  v19[2] = 0;
  v19[3] = 0;
  v20 = v27;
  v27 = v19;
  if ( v20 )
  {
    (*(void (__fastcall **)(_QWORD *, __int64))(*v20 + 192LL))(v20, 1);
LABEL_20:
    v19 = v27;
  }
  v21 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD *, __int64))(*v19 + 32LL))(v19, v18);
  if ( v21 != &v32 )
  {
    v22 = *v21;
    *v21 = v17;
    v17 = v22;
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 192LL))(v17, 1);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 88LL))(*((_QWORD *)this + 1)) == 5 )
  {
    v23 = (char *)operator new(0x28u);
    *(_DWORD *)(v23 + 33) = 0;
    *(_WORD *)(v23 + 37) = 0;
    v23[39] = 0;
    v24 = web::json::details::g_keep_json_object_unsorted;
    *(_QWORD *)v23 = &web::json::details::_Object::`vftable';
    *((_QWORD *)v23 + 1) = 0;
    *((_QWORD *)v23 + 2) = 0;
    *((_QWORD *)v23 + 3) = 0;
    v23[32] = v24;
    v25 = *((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v23;
    if ( v25 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 192LL))(v25, 1);
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 40LL))(
          *((_QWORD *)this + 1),
          UusExclusion::_keyExclusionListLocal);
  web::json::value::operator=(v26, &v27);
  UusExclusion::Save(this);
  if ( v27 )
    (*(void (__fastcall **)(_QWORD *, __int64))(*v27 + 192LL))(v27, 1);
  v28 = &UusVersion::`vftable';
  v29 = a2;
  v30 = *(_OWORD *)v30;
  return uus::UndockedUpdateCoreTelemetry::UusFailoverVersionExcludedSuccess(&v28, &v30);
}

```

## disassembly

```asm
0x180032b3c  mov     [rsp+arg_8], rdx
0x180032b41  push    rbx
0x180032b42  push    rsi
0x180032b43  push    rdi
0x180032b44  push    r12
0x180032b46  push    r13
0x180032b48  push    r14
0x180032b4a  push    r15
0x180032b4c  sub     rsp, 0F0h
0x180032b53  mov     rax, cs:__security_cookie
0x180032b5a  xor     rax, rsp
0x180032b5d  mov     [rsp+128h+var_48], rax
0x180032b65  mov     r12, r8
0x180032b68  mov     qword ptr [rsp+128h+var_E8], r8
0x180032b6d  mov     r14, rdx
0x180032b70  mov     r15, rcx
0x180032b73  mov     [rsp+128h+var_C8], r8
0x180032b78  xor     esi, esi
0x180032b7a  lea     r13d, [rsi+1]
0x180032b7e  mov     [rsp+128h+var_108], r13b
0x180032b83  mov     [rsp+128h+var_100], rsi
0x180032b88  lea     rcx, [rsp+128h+var_100]; this
0x180032b8d  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180032b92  nop
0x180032b93  lea     rbx, [r15+8]
0x180032b97  mov     rcx, [rbx]
0x180032b9a  mov     rax, [rcx]
0x180032b9d  lea     rdi, ?_keyExclusionListLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_keyExclusionListLocal
0x180032ba4  mov     rdx, rdi
0x180032ba7  mov     rax, [rax+8]
0x180032bab  call    _guard_dispatch_icall
0x180032bb0  test    al, al
0x180032bb2  jz      loc_180032D06
0x180032bb8  mov     rdx, rdi
0x180032bbb  mov     rcx, rbx
0x180032bbe  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180032bc3  mov     rdx, rax
0x180032bc6  lea     rcx, [rsp+128h+var_100]
0x180032bcb  call    ??4value@json@web@@QEAAAEAV012@AEBV012@@Z; web::json::value::operator=(web::json::value const &)
0x180032bd0  mov     rcx, [rsp+128h+var_100]
0x180032bd5  mov     rax, [rcx]
0x180032bd8  mov     rax, [rax+58h]
0x180032bdc  call    _guard_dispatch_icall
0x180032be1  cmp     eax, 4
0x180032be4  jnz     loc_180032F95
0x180032bea  mov     rdx, rdi
0x180032bed  mov     rcx, rbx
0x180032bf0  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180032bf5  mov     rcx, [rax]
0x180032bf8  mov     rax, [rcx]
0x180032bfb  mov     rax, [rax+98h]
0x180032c02  call    _guard_dispatch_icall
0x180032c07  mov     rbx, [rax]
0x180032c0a  mov     rdi, [rax+8]
0x180032c0e  cmp     rbx, rdi
0x180032c11  jz      loc_180032CFD
0x180032c17  mov     [rsp+128h+var_50], rsi
0x180032c1f  mov     rcx, [rbx]
0x180032c22  mov     rax, [rcx]
0x180032c25  lea     rdx, [rsp+128h+var_50]
0x180032c2d  mov     rax, [rax]
0x180032c30  call    _guard_dispatch_icall
0x180032c35  nop
0x180032c36  mov     rcx, [rsp+128h+var_50]
0x180032c3e  mov     rax, [rcx]
0x180032c41  lea     rdx, [rsp+128h+var_D8]
0x180032c46  mov     rax, [rax]
0x180032c49  call    _guard_dispatch_icall
0x180032c4e  lea     rdx, [rsp+128h+var_D8]
0x180032c53  lea     rcx, [rsp+128h+var_B0]
0x180032c58  call    ?ParseVersionRangeFromValue@UusExclusion@@CA?AU?$pair@_K_K@std@@Vvalue@json@web@@@Z; UusExclusion::ParseVersionRangeFromValue(web::json::value)
0x180032c5d  cmp     r14, [rax]
0x180032c60  jb      short loc_180032CD5
0x180032c62  cmp     r14, [rax+8]
0x180032c66  ja      short loc_180032CD5
0x180032c68  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180032c6f  mov     [rsp+128h+var_F8], rdi
0x180032c74  mov     [rsp+128h+var_F0], r14
0x180032c79  movaps  xmm0, xmmword ptr [r12]
0x180032c7e  movdqa  [rsp+128h+var_E8], xmm0
0x180032c84  lea     rdx, [rsp+128h+var_E8]
0x180032c89  lea     rcx, [rsp+128h+var_F8]
0x180032c8e  call    ?UusFailoverVersionExcludedNoOp@UndockedUpdateCoreTelemetry@uus@@SAXAEBVUusVersion@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; uus::UndockedUpdateCoreTelemetry::UusFailoverVersionExcludedNoOp(UusVersion const &,std::wstring_view)
0x180032c93  nop
0x180032c94  mov     rcx, [rsp+128h+var_50]
0x180032c9c  test    rcx, rcx
0x180032c9f  jz      short loc_180032CB4
0x180032ca1  mov     rax, [rcx]
0x180032ca4  mov     edx, r13d
0x180032ca7  mov     rax, [rax+0C0h]
0x180032cae  call    _guard_dispatch_icall
0x180032cb3  nop
0x180032cb4  mov     rcx, [rsp+128h+var_100]
0x180032cb9  test    rcx, rcx
0x180032cbc  jz      short loc_180032CD0
0x180032cbe  mov     rax, [rcx]
0x180032cc1  mov     edx, r13d
0x180032cc4  mov     rax, [rax+0C0h]
0x180032ccb  call    _guard_dispatch_icall
0x180032cd0  jmp     loc_180032F72
0x180032cd5  mov     rcx, [rsp+128h+var_50]
0x180032cdd  test    rcx, rcx
0x180032ce0  jz      short loc_180032CF4
0x180032ce2  mov     rax, [rcx]
0x180032ce5  mov     edx, r13d
0x180032ce8  mov     rax, [rax+0C0h]
0x180032cef  call    _guard_dispatch_icall
0x180032cf4  add     rbx, 8
0x180032cf8  jmp     loc_180032C0E
0x180032cfd  lea     r12, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x180032d04  jmp     short loc_180032D47
0x180032d06  mov     ecx, 20h ; ' '; Size
0x180032d0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032d10  lea     r12, ??_7_Array@details@json@web@@6B@; const web::json::details::_Array::`vftable'
0x180032d17  mov     [rax], r12
0x180032d1a  mov     [rax+8], rsi
0x180032d1e  mov     [rax+10h], rsi
0x180032d22  mov     [rax+18h], rsi
0x180032d26  mov     rcx, [rsp+128h+var_100]
0x180032d2b  mov     [rsp+128h+var_100], rax
0x180032d30  test    rcx, rcx
0x180032d33  jz      short loc_180032D47
0x180032d35  mov     rax, [rcx]
0x180032d38  mov     edx, r13d
0x180032d3b  mov     rax, [rax+0C0h]
0x180032d42  call    _guard_dispatch_icall
0x180032d47  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180032d4e  mov     [rsp+128h+var_D8], rdi
0x180032d53  mov     [rsp+128h+var_D0], r14
0x180032d58  lea     rdx, [rsp+128h+var_70]
0x180032d60  lea     rcx, [rsp+128h+var_D8]
0x180032d65  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180032d6a  mov     r13, rax
0x180032d6d  mov     [rsp+128h+var_F8], rax
0x180032d72  mov     ecx, 30h ; '0'; Size
0x180032d77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032d7c  movups  xmm0, xmmword ptr [r13+0]
0x180032d81  movups  [rsp+128h+var_B0], xmm0
0x180032d86  movups  xmm1, xmmword ptr [r13+10h]
0x180032d8b  movups  [rsp+128h+var_A0], xmm1
0x180032d93  mov     [r13+10h], rsi
0x180032d97  mov     qword ptr [r13+18h], 7
0x180032d9f  mov     [r13+0], si
0x180032da4  lea     rdx, [rsp+128h+var_B0]
0x180032da9  mov     rcx, rax
0x180032dac  call    ??0_String@details@json@web@@QEAA@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::details::_String::_String(std::wstring)
0x180032db1  mov     rbx, rax
0x180032db4  mov     [rsp+128h+var_B8], rax
0x180032db9  mov     rcx, r13
0x180032dbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032dc1  nop
0x180032dc2  mov     rcx, [rsp+128h+var_100]
0x180032dc7  mov     rax, [rcx]
0x180032dca  mov     rax, [rax+0B8h]
0x180032dd1  call    _guard_dispatch_icall
0x180032dd6  mov     r13, rax
0x180032dd9  mov     rcx, [rsp+128h+var_100]
0x180032dde  mov     rax, [rcx]
0x180032de1  mov     rax, [rax+58h]
0x180032de5  call    _guard_dispatch_icall
0x180032dea  cmp     eax, 5
0x180032ded  jnz     short loc_180032E29
0x180032def  lea     ecx, [rax+1Bh]; Size
0x180032df2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032df7  mov     [rax], r12
0x180032dfa  mov     [rax+8], rsi
0x180032dfe  mov     [rax+10h], rsi
0x180032e02  mov     [rax+18h], rsi
0x180032e06  mov     rcx, [rsp+128h+var_100]
0x180032e0b  mov     [rsp+128h+var_100], rax
0x180032e10  test    rcx, rcx
0x180032e13  jz      short loc_180032E2E
0x180032e15  mov     rax, [rcx]
0x180032e18  mov     edx, 1
0x180032e1d  mov     rax, [rax+0C0h]
0x180032e24  call    _guard_dispatch_icall
0x180032e29  mov     rax, [rsp+128h+var_100]
0x180032e2e  mov     rcx, [rax]
0x180032e31  mov     r8, [rcx+20h]
0x180032e35  mov     rdx, r13
0x180032e38  mov     rcx, rax
0x180032e3b  mov     rax, r8
0x180032e3e  call    _guard_dispatch_icall
0x180032e43  lea     rcx, [rsp+128h+var_B8]
0x180032e48  cmp     rax, rcx
0x180032e4b  jz      short loc_180032E56
0x180032e4d  mov     rcx, [rax]
0x180032e50  mov     [rax], rbx
0x180032e53  mov     rbx, rcx
0x180032e56  test    rbx, rbx
0x180032e59  jz      short loc_180032E73
0x180032e5b  mov     rax, [rbx]
0x180032e5e  mov     edx, 1
0x180032e63  mov     rcx, rbx
0x180032e66  mov     rax, [rax+0C0h]
0x180032e6d  call    _guard_dispatch_icall
0x180032e72  nop
0x180032e73  mov     rcx, [r15+8]
0x180032e77  mov     rax, [rcx]
0x180032e7a  mov     rax, [rax+58h]
0x180032e7e  call    _guard_dispatch_icall
0x180032e83  cmp     eax, 5
0x180032e86  jnz     short loc_180032EDB
0x180032e88  lea     ecx, [rax+23h]; Size
0x180032e8b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032e90  mov     [rax+21h], esi
0x180032e93  mov     [rax+25h], si
0x180032e97  mov     [rax+27h], sil
0x180032e9b  mov     cl, cs:?g_keep_json_object_unsorted@details@json@web@@3_NA; bool web::json::details::g_keep_json_object_unsorted
0x180032ea1  lea     rdx, ??_7_Object@details@json@web@@6B@; const web::json::details::_Object::`vftable'
0x180032ea8  mov     [rax], rdx
0x180032eab  mov     [rax+8], rsi
0x180032eaf  mov     [rax+10h], rsi
0x180032eb3  mov     [rax+18h], rsi
0x180032eb7  mov     [rax+20h], cl
0x180032eba  mov     rcx, [r15+8]
0x180032ebe  mov     [r15+8], rax
0x180032ec2  test    rcx, rcx
0x180032ec5  jz      short loc_180032EDB
0x180032ec7  mov     rax, [rcx]
0x180032eca  mov     edx, 1
0x180032ecf  mov     rax, [rax+0C0h]
0x180032ed6  call    _guard_dispatch_icall
0x180032edb  mov     rcx, [r15+8]
0x180032edf  mov     rax, [rcx]
0x180032ee2  lea     rdx, ?_keyExclusionListLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_keyExclusionListLocal
0x180032ee9  mov     rax, [rax+28h]
0x180032eed  call    _guard_dispatch_icall
0x180032ef2  lea     rdx, [rsp+128h+var_100]
0x180032ef7  mov     rcx, rax
0x180032efa  call    ??4value@json@web@@QEAAAEAV012@AEBV012@@Z; web::json::value::operator=(web::json::value const &)
0x180032eff  mov     rcx, r15; this
0x180032f02  call    ?Save@UusExclusion@@AEAAXXZ; UusExclusion::Save(void)
0x180032f07  mov     [rsp+128h+var_108], sil
0x180032f0c  mov     rcx, [rsp+128h+var_100]
0x180032f11  test    rcx, rcx
0x180032f14  jz      short loc_180032F2B
0x180032f16  mov     rax, [rcx]
0x180032f19  mov     edx, 1
0x180032f1e  mov     rax, [rax+0C0h]
0x180032f25  call    _guard_dispatch_icall
0x180032f2a  nop
0x180032f2b  mov     rax, qword ptr [rsp+128h+var_E8]
0x180032f30  jmp     short loc_180032F4F
0x180032f32  xor     esi, esi
0x180032f34  cmp     [rsp+128h+var_108], sil
0x180032f39  jnz     short loc_180032F72
0x180032f3b  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180032f42  mov     r14, [rsp+128h+arg_8]
0x180032f4a  mov     rax, [rsp+128h+var_C8]
0x180032f4f  mov     [rsp+128h+var_F8], rdi
0x180032f54  mov     [rsp+128h+var_F0], r14
0x180032f59  movaps  xmm0, xmmword ptr [rax]
0x180032f5c  movdqa  [rsp+128h+var_E8], xmm0
0x180032f62  lea     rdx, [rsp+128h+var_E8]
0x180032f67  lea     rcx, [rsp+128h+var_F8]
0x180032f6c  call    ?UusFailoverVersionExcludedSuccess@UndockedUpdateCoreTelemetry@uus@@SAXAEBVUusVersion@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; uus::UndockedUpdateCoreTelemetry::UusFailoverVersionExcludedSuccess(UusVersion const &,std::wstring_view)
0x180032f71  nop
0x180032f72  mov     rcx, [rsp+128h+var_48]
0x180032f7a  xor     rcx, rsp; StackCookie
0x180032f7d  call    __security_check_cookie
0x180032f82  add     rsp, 0F0h
0x180032f89  pop     r15
0x180032f8b  pop     r14
0x180032f8d  pop     r13
0x180032f8f  pop     r12
0x180032f91  pop     rdi
0x180032f92  pop     rsi
0x180032f93  pop     rbx
0x180032f94  retn
0x180032f95  lea     rdx, aJsonFieldIsNot; "JSON field is not expected type."
0x180032f9c  lea     rcx, [rsp+128h+pExceptionObject]; this
0x180032fa4  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180032fa9  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180032fb0  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180032fb8  call    _CxxThrowException
```
