# FSVMMemory::Create(_GUID const &,ulong,bool)

- ea: `0x1800e6c90`
- end: `0x1800e6f99`
- name: `?Create@FSVMMemory@@UEAAJAEBU_GUID@@K_N@Z`
- size: `777`
- prototype: `int(FSVMMemory *__hidden this, const struct _GUID *, unsigned int, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180009b5c`
- `0x180017d90`
- `0x1800198f4`
- `0x18001c444`
- `0x180024e94`
- `0x1800259c4`
- `0x18002681c`
- `0x18004d714`
- `0x18004da70`
- `0x180074374`
- `0x1800e6c90`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6f71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6f71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6cce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6cce`
- `RPCRT4!UuidCreate` at `0x1800e6e05`
- `RPCRT4!UuidCreate` at `0x1800e6e13`
- `RPCRT4!UuidCreate` at `0x1800e6e05`
- `RPCRT4!UuidCreate` at `0x1800e6e13`

## pseudocode

```c
__int64 __fastcall FSVMMemory::Create(FSVMMemory *this, const struct _GUID *a2, unsigned int a3, unsigned __int8 a4)
{
  char v5; // di
  GuidTrace *v9; // rax
  const char *String; // rax
  const char *v11; // rcx
  signed int v12; // ebx
  int v13; // eax
  __int64 v14; // rdx
  unsigned __int8 v15; // r9
  unsigned int v16; // r15d
  struct _GUID v17; // xmm0
  UUID v18; // xmm1
  GuidTrace *v19; // rax
  const char *v20; // rax
  bool v21; // zf
  GuidTrace *v22; // rax
  const char *v23; // rax
  unsigned int v25; // [rsp+40h] [rbp-39h] BYREF
  void *v26; // [rsp+48h] [rbp-31h] BYREF
  void *v27; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v28[32]; // [rsp+58h] [rbp-21h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-1h] BYREF

  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Uuid = GUID_00000000_0000_0000_0000_000000000000;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v9 = GuidTrace::GuidTrace((GuidTrace *)v28, a2);
    String = GuidTrace::GetString(v9);
    v11 = "r";
    if ( !a4 )
      v11 = "rw";
    WPP_SF_qsds(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)String, a3, (__int64)v11);
    v5 = 1;
  }
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    FSString::~FSString((FSString *)v28);
  }
  if ( a3 - 1 > 0x1FFFFFFF )
  {
    v12 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_d5790f42b8633b0065c313df689c4601_Traceguids,
        (char *)this - 32,
        -2147024809);
    goto LABEL_23;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 4) + 8LL))((char *)this - 32);
  v13 = FSVMGetBoundedSize(a3, &v25);
  v12 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_22;
    v14 = 23;
LABEL_13:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_d5790f42b8633b0065c313df689c4601_Traceguids,
      (char *)this - 32,
      v13);
    goto LABEL_22;
  }
  if ( !UuidCreate(&Uuid) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v26,
      0);
    v15 = a4;
    v16 = v25;
    v13 = FSVMCreateMemory(&Uuid, a2, v25, v15, &v27, &v26);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v17 = *a2;
      v18 = Uuid;
      *((_QWORD *)this + 8) = v27;
      *(struct _GUID *)((char *)this + 76) = v17;
      *((_DWORD *)this + 18) = v16;
      *(UUID *)((char *)this - 24) = v18;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
        (char *)this + 56,
        &v26);
      goto LABEL_22;
    }
    if ( !g_wppLevels )
      goto LABEL_22;
    v14 = 25;
    goto LABEL_13;
  }
  v12 = UuidCreate(&Uuid) | 0x80010000;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_d5790f42b8633b0065c313df689c4601_Traceguids,
      (char *)this - 32,
      v12);
LABEL_22:
  if ( v12 < 0 )
  {
LABEL_23:
    if ( byte_18010EC4D )
    {
      v5 |= 2u;
      v19 = GuidTrace::GuidTrace((GuidTrace *)v28, &Uuid);
      v20 = GuidTrace::GetString(v19);
      WPP_SF_qDs(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        26,
        (unsigned int)&WPP_d5790f42b8633b0065c313df689c4601_Traceguids,
        (_DWORD)this - 32,
        v12,
        (__int64)v20);
    }
    v21 = (v5 & 2) == 0;
    goto LABEL_29;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v5 |= 4u;
    v22 = GuidTrace::GuidTrace((GuidTrace *)v28, &Uuid);
    v23 = GuidTrace::GetString(v22);
    WPP_SF_qDs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      27,
      (unsigned int)&WPP_d5790f42b8633b0065c313df689c4601_Traceguids,
      (_DWORD)this - 32,
      v12,
      (__int64)v23);
  }
  v21 = (v5 & 4) == 0;
LABEL_29:
  if ( !v21 )
    FSString::~FSString((FSString *)v28);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800e6c90  push    rbp
0x1800e6c92  push    rbx
0x1800e6c93  push    rsi
0x1800e6c94  push    rdi
0x1800e6c95  push    r12
0x1800e6c97  push    r13
0x1800e6c99  push    r14
0x1800e6c9b  push    r15
0x1800e6c9d  lea     rbp, [rsp-1Fh]
0x1800e6ca2  sub     rsp, 98h
0x1800e6ca9  mov     rax, cs:__security_cookie
0x1800e6cb0  xor     rax, rsp
0x1800e6cb3  mov     [rbp+57h+var_48], rax
0x1800e6cb7  xor     esi, esi
0x1800e6cb9  mov     r14, rcx
0x1800e6cbc  add     rcx, 10h; lpCriticalSection
0x1800e6cc0  mov     [rbp+57h+var_90], esi
0x1800e6cc3  mov     edi, esi
0x1800e6cc5  mov     r15b, r9b
0x1800e6cc8  mov     ebx, r8d
0x1800e6ccb  mov     r12, rdx
0x1800e6cce  call    cs:__imp_EnterCriticalSection
0x1800e6cd4  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800e6cdb  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800e6ce0  mov     [rbp+57h+var_88], rsi
0x1800e6ce4  mov     [rbp+57h+var_80], rsi
0x1800e6ce8  mov     [rbp+57h+var_90], esi
0x1800e6ceb  cmp     cs:byte_18010EC4D, 8
0x1800e6cf2  lea     rsi, [r14-20h]
0x1800e6cf6  jb      short loc_1800E6D56
0x1800e6cf8  mov     rdx, r12; struct _GUID *
0x1800e6cfb  lea     rcx, [rbp+57h+var_78]; this
0x1800e6cff  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e6d04  mov     rcx, rax; this
0x1800e6d07  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e6d0c  lea     rdx, aRw; "rw"
0x1800e6d13  test    r15b, r15b
0x1800e6d16  lea     rcx, aR; "r"
0x1800e6d1d  mov     r9, rsi
0x1800e6d20  cmovz   rcx, rdx
0x1800e6d24  lea     r8, WPP_d5790f42b8633b0065c313df689c4601_Traceguids
0x1800e6d2b  mov     [rsp+0D0h+var_A0], rcx; __int64
0x1800e6d30  mov     edx, 15h
0x1800e6d35  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6d3c  mov     dword ptr [rsp+0D0h+var_A8], ebx; char
0x1800e6d40  mov     [rsp+0D0h+var_B0], rax; __int64
0x1800e6d45  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800e6d4c  call    WPP_SF_qsds
0x1800e6d51  mov     edi, 1
0x1800e6d56  test    dil, 1
0x1800e6d5a  jz      short loc_1800E6D68
0x1800e6d5c  and     edi, 0FFFFFFFEh
0x1800e6d5f  lea     rcx, [rbp+57h+var_78]; this
0x1800e6d63  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e6d68  lea     eax, [rbx-1]
0x1800e6d6b  cmp     eax, 1FFFFFFFh
0x1800e6d70  jbe     short loc_1800E6DAC
0x1800e6d72  mov     ebx, 80070057h
0x1800e6d77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6d7e  jb      loc_1800E6EB7
0x1800e6d84  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6d8b  lea     r8, WPP_d5790f42b8633b0065c313df689c4601_Traceguids
0x1800e6d92  mov     edx, 16h
0x1800e6d97  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e6d9b  mov     r9, rsi
0x1800e6d9e  mov     rcx, [rcx+10h]
0x1800e6da2  call    WPP_SF_qD
0x1800e6da7  jmp     loc_1800E6EB7
0x1800e6dac  mov     rax, [rsi]
0x1800e6daf  mov     rcx, rsi
0x1800e6db2  mov     rax, [rax+8]
0x1800e6db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6dbb  lea     rdx, [rbp+57h+var_90]; unsigned int *
0x1800e6dbf  mov     ecx, ebx; unsigned int
0x1800e6dc1  call    ?FSVMGetBoundedSize@@YAJKPEAK@Z; FSVMGetBoundedSize(ulong,ulong *)
0x1800e6dc6  mov     ebx, eax
0x1800e6dc8  test    eax, eax
0x1800e6dca  jns     short loc_1800E6E01
0x1800e6dcc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6dd3  jb      loc_1800E6EB3
0x1800e6dd9  mov     edx, 17h
0x1800e6dde  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800e6de2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6de9  lea     r8, WPP_d5790f42b8633b0065c313df689c4601_Traceguids
0x1800e6df0  mov     r9, rsi
0x1800e6df3  mov     rcx, [rcx+10h]
0x1800e6df7  call    WPP_SF_qD
0x1800e6dfc  jmp     loc_1800E6EB3
0x1800e6e01  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800e6e05  call    cs:__imp_UuidCreate
0x1800e6e0b  test    eax, eax
0x1800e6e0d  jz      short loc_1800E6E39
0x1800e6e0f  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800e6e13  call    cs:__imp_UuidCreate
0x1800e6e19  mov     ebx, eax
0x1800e6e1b  or      ebx, 80010000h
0x1800e6e21  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6e28  jb      loc_1800E6EB3
0x1800e6e2e  mov     edx, 18h
0x1800e6e33  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e6e37  jmp     short loc_1800E6DE2
0x1800e6e39  xor     edx, edx
0x1800e6e3b  lea     rcx, [rbp+57h+var_88]
0x1800e6e3f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e6e44  lea     rax, [rbp+57h+var_88]
0x1800e6e48  mov     r9b, r15b; bool
0x1800e6e4b  mov     r15d, [rbp+57h+var_90]
0x1800e6e4f  lea     rcx, [rbp+57h+Uuid]; struct _GUID *
0x1800e6e53  mov     [rsp+0D0h+var_A8], rax; void **
0x1800e6e58  mov     r8d, r15d; unsigned int
0x1800e6e5b  lea     rax, [rbp+57h+var_80]
0x1800e6e5f  mov     rdx, r12; struct _GUID *
0x1800e6e62  mov     [rsp+0D0h+var_B0], rax; void **
0x1800e6e67  call    ?FSVMCreateMemory@@YAJAEBU_GUID@@0K_NPEAPEAX2@Z; FSVMCreateMemory(_GUID const &,_GUID const &,ulong,bool,void * *,void * *)
0x1800e6e6c  mov     ebx, eax
0x1800e6e6e  test    eax, eax
0x1800e6e70  jns     short loc_1800E6E85
0x1800e6e72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800e6e79  jb      short loc_1800E6EB3
0x1800e6e7b  mov     edx, 19h
0x1800e6e80  jmp     loc_1800E6DDE
0x1800e6e85  movups  xmm0, xmmword ptr [r12]
0x1800e6e8a  mov     rax, [rbp+57h+var_80]
0x1800e6e8e  lea     rcx, [r14+38h]
0x1800e6e92  movups  xmm1, xmmword ptr [rbp+57h+Uuid.Data1]
0x1800e6e96  lea     rdx, [rbp+57h+var_88]
0x1800e6e9a  mov     [r14+40h], rax
0x1800e6e9e  movdqu  xmmword ptr [r14+4Ch], xmm0
0x1800e6ea4  mov     [r14+48h], r15d
0x1800e6ea8  movdqu  xmmword ptr [r14-18h], xmm1
0x1800e6eae  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800e6eb3  test    ebx, ebx
0x1800e6eb5  jns     short loc_1800E6F09
0x1800e6eb7  cmp     cs:byte_18010EC4D, 1
0x1800e6ebe  jb      short loc_1800E6F03
0x1800e6ec0  lea     rdx, [rbp+57h+Uuid]; struct _GUID *
0x1800e6ec4  or      edi, 2
0x1800e6ec7  lea     rcx, [rbp+57h+var_78]; this
0x1800e6ecb  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e6ed0  mov     rcx, rax; this
0x1800e6ed3  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e6ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6edf  lea     r8, WPP_d5790f42b8633b0065c313df689c4601_Traceguids
0x1800e6ee6  mov     [rsp+0D0h+var_A8], rax
0x1800e6eeb  mov     edx, 1Ah
0x1800e6ef0  mov     r9, rsi
0x1800e6ef3  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e6ef7  mov     rcx, [rcx+0D8h]
0x1800e6efe  call    WPP_SF_qDs
0x1800e6f03  test    dil, 2
0x1800e6f07  jmp     short loc_1800E6F59
0x1800e6f09  cmp     cs:byte_18010EC4D, 8
0x1800e6f10  jb      short loc_1800E6F55
0x1800e6f12  lea     rdx, [rbp+57h+Uuid]; struct _GUID *
0x1800e6f16  or      edi, 4
0x1800e6f19  lea     rcx, [rbp+57h+var_78]; this
0x1800e6f1d  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800e6f22  mov     rcx, rax; this
0x1800e6f25  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800e6f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e6f31  lea     r8, WPP_d5790f42b8633b0065c313df689c4601_Traceguids
0x1800e6f38  mov     [rsp+0D0h+var_A8], rax
0x1800e6f3d  mov     edx, 1Bh
0x1800e6f42  mov     r9, rsi
0x1800e6f45  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800e6f49  mov     rcx, [rcx+0D8h]
0x1800e6f50  call    WPP_SF_qDs
0x1800e6f55  test    dil, 4
0x1800e6f59  jz      short loc_1800E6F64
0x1800e6f5b  lea     rcx, [rbp+57h+var_78]; this
0x1800e6f5f  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800e6f64  lea     rcx, [rbp+57h+var_88]
0x1800e6f68  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6f6d  lea     rcx, [r14+10h]; lpCriticalSection
0x1800e6f71  call    cs:__imp_LeaveCriticalSection
0x1800e6f77  mov     eax, ebx
0x1800e6f79  mov     rcx, [rbp+57h+var_48]
0x1800e6f7d  xor     rcx, rsp; StackCookie
0x1800e6f80  call    __security_check_cookie
0x1800e6f85  add     rsp, 98h
0x1800e6f8c  pop     r15
0x1800e6f8e  pop     r14
0x1800e6f90  pop     r13
0x1800e6f92  pop     r12
0x1800e6f94  pop     rdi
0x1800e6f95  pop     rsi
0x1800e6f96  pop     rbx
0x1800e6f97  pop     rbp
0x1800e6f98  retn
```
