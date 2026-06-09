# HDV::IPC::DeviceHostServices::Initialize(IVmDeviceHost *,void *,void * *)

- ea: `0x140131420`
- end: `0x14013181e`
- name: `?Initialize@DeviceHostServices@IPC@HDV@@UEAAXPEAUIVmDeviceHost@@PEAXPEAPEAX@Z`
- size: `1022`
- prototype: `void __fastcall(HDV::IPC::DeviceHostServices *this, struct IVmDeviceHost *, void *, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140021d00`
- `0x14004cb10`
- `0x14005adc4`
- `0x14005ae4c`
- `0x14005b628`
- `0x14006af38`
- `0x14006fec8`
- `0x1400828dc`
- `0x1400841e4`
- `0x140131420`
- `0x140131910`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x14025f1b0`
- `0x140297264`
- `0x140297f78`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131804`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131811`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131804`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140131811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131754`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131754`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14013177f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14013177f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14013152b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14013152b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1401314d8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1401314d8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14013154f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14013154f`

## string_xrefs

- `0x14013146c`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131493`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131507`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131576`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131793`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HDV::IPC::DeviceHostServices::Initialize(
        HDV::IPC::DeviceHostServices *this,
        struct IVmDeviceHost *a2,
        void *a3,
        void **a4)
{
  int v7; // ecx
  unsigned int v8; // r14d
  HANDLE FileMappingW; // rax
  const char *v10; // r9
  char *v11; // r10
  LPVOID v12; // rbx
  const char *v13; // r9
  const void *v14; // rsi
  __int64 v15; // rcx
  __m128i v16; // xmm0
  size_t v17; // rax
  _DWORD *v18; // rsi
  __m128i v19; // xmm6
  __int64 v20; // rcx
  unsigned __int64 v21; // xmm6_8
  unsigned __int64 v22; // rax
  struct HDV::IPC::CallControlBlock *v23; // r14
  struct HDV::IPC::CallControlBlock *i; // rsi
  void *v25; // rbx
  HDV::IPC::Details::CallImpl *v26; // rax
  HDV::IPC::Details::CallImpl *v27; // rbx
  Vml::VmSharableObject *v28; // rcx
  HDV::IPC::Details::CallImpl **v29; // rdx
  void *v30; // rbx
  HANDLE CurrentProcess; // rax
  const char *v32; // r9
  __int64 v33; // rbx
  int dwMaximumSizeLow; // [rsp+20h] [rbp-60h]
  __m128i v35; // [rsp+40h] [rbp-40h] BYREF
  LPHANDLE lpTargetHandle; // [rsp+50h] [rbp-30h]
  _QWORD v37[2]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  lpTargetHandle = a4;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      (const char *)0x80070057LL,
      dwMaximumSizeLow);
  if ( *((_QWORD *)this + 14) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      (const char *)0x8007139FLL,
      dwMaximumSizeLow);
  v7 = *((_DWORD *)this + 4) << 7;
  if ( !is_mul_ok(0x80u, *((_DWORD *)this + 4)) )
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  v8 = v7 + 64;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v7 + 64, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 24,
    FileMappingW);
  v11 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v10);
  v12 = MapViewOfFile(v11, 6u, 0, 0, 0);
  v14 = (const void *)*((_QWORD *)this + 5);
  if ( v14 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v37);
    UnmapViewOfFile(v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v37);
  }
  *((_QWORD *)this + 5) = v12;
  if ( !v12 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v13);
  gsl::details::extent_type<-1>::extent_type<-1>(&v35, v8);
  v35.m128i_i64[1] = (__int64)v12;
  if ( v35.m128i_i64[0] == -1 )
    goto LABEL_35;
  v16 = v35;
  *((__m128i *)this + 3) = v35;
  v35 = v16;
  v17 = gsl::span<unsigned char,-1>::size_bytes(&v35);
  memset_0((void *)_mm_srli_si128(v16, 8).m128i_i64[0], 0, v17);
  v18 = (_DWORD *)*((_QWORD *)this + 7);
  v35.m128i_i64[0] = *((_QWORD *)this + 6);
  v35.m128i_i64[1] = (__int64)v18;
  if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(&v35) < 0xC )
  {
LABEL_35:
    _o_terminate(v15);
    __debugbreak();
    JUMPOUT(0x14013181ELL);
  }
  gsl::span<unsigned char,-1>::size_bytes(&v35);
  *v18 = 4096;
  v18[1] = *((_DWORD *)this + 4);
  v18[2] = 64;
  v19 = *(__m128i *)gsl::span<unsigned char,-1>::subspan((char *)this + 48, v37, 64);
  v35 = v19;
  if ( (gsl::span<unsigned char,-1>::size_bytes(&v35) & 0x7F) != 0
    || (v35 = v19,
        v21 = _mm_srli_si128(v19, 8).m128i_u64[0],
        v22 = gsl::span<unsigned char,-1>::size_bytes(&v35),
        gsl::details::extent_type<-1>::extent_type<-1>(&v35, v22 >> 7),
        v35.m128i_i64[1] = v21,
        v35.m128i_i64[0] == -1)
    || !v21 && v35.m128i_i64[0] )
  {
    _o_terminate(v20);
    __debugbreak();
    goto LABEL_35;
  }
  *((__m128i *)this + 4) = v35;
  v23 = (struct HDV::IPC::CallControlBlock *)*((_QWORD *)this + 9);
  for ( i = (struct HDV::IPC::CallControlBlock *)((char *)v23 + 128 * *((_QWORD *)this + 8));
        v23 != i;
        v23 = (struct HDV::IPC::CallControlBlock *)((char *)v23 + 128) )
  {
    v37[0] = 0;
    v25 = operator new(0xA0u);
    v35.m128i_i64[0] = (__int64)v25;
    memset_0(v25, 0, 0xA0u);
    v26 = HDV::IPC::Details::CallImpl::CallImpl((HDV::IPC::Details::CallImpl *)v25, v23, a3);
    v27 = v26;
    if ( v26 )
      v28 = (HDV::IPC::Details::CallImpl *)((char *)v26 + *(int *)(*((_QWORD *)v26 + 1) + 4LL) + 8);
    else
      v28 = 0;
    Vml::VmSharableObject::IncrementUserCount(v28);
    v37[0] = v27;
    v29 = (HDV::IPC::Details::CallImpl **)*((_QWORD *)this + 12);
    if ( v29 == *((HDV::IPC::Details::CallImpl ***)this + 13) )
    {
      std::vector<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>(
        (char *)this + 88,
        v29,
        v37);
    }
    else
    {
      v37[0] = 0;
      *v29 = v27;
      *((_QWORD *)this + 12) += 8LL;
    }
    wil::com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>::~com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>(v37);
  }
  v30 = (void *)*((_QWORD *)this + 3);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v30, a3, lpTargetHandle, 6u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v32);
  v33 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IVmDeviceHost *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
}

```

## disassembly

```asm
0x140131420  mov     [rsp-38h+arg_8], rbx
0x140131425  push    rbp
0x140131426  push    rsi
0x140131427  push    rdi
0x140131428  push    r12
0x14013142a  push    r13
0x14013142c  push    r14
0x14013142e  push    r15
0x140131430  mov     rbp, rsp
0x140131433  sub     rsp, 80h
0x14013143a  movaps  [rsp+80h+var_10], xmm6
0x14013143f  mov     rax, cs:__security_cookie
0x140131446  xor     rax, rsp
0x140131449  mov     [rbp+var_18], rax
0x14013144d  mov     [rbp+lpTargetHandle], r9
0x140131451  mov     r13, r8
0x140131454  mov     r12, rdx
0x140131457  mov     rdi, rcx
0x14013145a  mov     rcx, [rbp+38h]; this
0x14013145e  xor     r15d, r15d
0x140131461  test    r8, r8
0x140131464  jnz     short loc_14013147E
0x140131466  mov     r9d, 80070057h; char *
0x14013146c  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131473  mov     edx, 0D6h; void *
0x140131478  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14013147e  cmp     [rdi+70h], r15
0x140131482  setnz   al
0x140131485  mov     rcx, [rbp+38h]; this
0x140131489  test    al, al
0x14013148b  jz      short loc_1401314A5
0x14013148d  mov     r9d, 8007139Fh; char *
0x140131493  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013149a  mov     edx, 0D7h; void *
0x14013149f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401314a5  mov     ecx, [rdi+10h]
0x1401314a8  shl     rcx, 7
0x1401314ac  mov     rax, rcx
0x1401314af  shr     rax, 20h
0x1401314b3  test    eax, eax
0x1401314b5  jz      short loc_1401314BD
0x1401314b7  call    ?SafeIntOnOverflow@SafeIntErrorPolicy_SafeIntException@utilities@msl@@SAXXZ; msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow(void)
0x1401314bd  lea     r14d, [rcx+40h]
0x1401314c1  mov     [rsp+80h+lpName], r15; lpName
0x1401314c6  mov     [rsp+80h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x1401314cb  xor     r9d, r9d; dwMaximumSizeHigh
0x1401314ce  xor     edx, edx; lpFileMappingAttributes
0x1401314d0  lea     r8d, [r9+4]; flProtect
0x1401314d4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1401314d8  call    cs:__imp_CreateFileMappingW
0x1401314df  nop     dword ptr [rax+rax+00h]
0x1401314e4  mov     rdx, rax
0x1401314e7  lea     rcx, [rdi+18h]
0x1401314eb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1401314f0  mov     r10, [rdi+18h]
0x1401314f4  lea     rax, [r10-1]
0x1401314f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401314fc  setnbe  al
0x1401314ff  mov     rcx, [rbp+38h]; this
0x140131503  test    al, al
0x140131505  jz      short loc_140131519
0x140131507  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013150e  mov     edx, 0E3h; void *
0x140131513  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131519  mov     qword ptr [rsp+80h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x14013151e  xor     r9d, r9d; dwFileOffsetLow
0x140131521  xor     r8d, r8d; dwFileOffsetHigh
0x140131524  lea     edx, [r9+6]; dwDesiredAccess
0x140131528  mov     rcx, r10; hFileMappingObject
0x14013152b  call    cs:__imp_MapViewOfFile
0x140131532  nop     dword ptr [rax+rax+00h]
0x140131537  mov     rbx, rax
0x14013153a  mov     rsi, [rdi+28h]
0x14013153e  test    rsi, rsi
0x140131541  jz      short loc_140131564
0x140131543  lea     rcx, [rbp+var_28]; this
0x140131547  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14013154c  mov     rcx, rsi; lpBaseAddress
0x14013154f  call    cs:__imp_UnmapViewOfFile
0x140131556  nop     dword ptr [rax+rax+00h]
0x14013155b  lea     rcx, [rbp+var_28]; this
0x14013155f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140131564  mov     [rdi+28h], rbx
0x140131568  test    rbx, rbx
0x14013156b  setz    al
0x14013156e  mov     rcx, [rbp+38h]; this
0x140131572  test    al, al
0x140131574  jz      short loc_140131588
0x140131576  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013157d  mov     edx, 0E6h; void *
0x140131582  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131588  mov     edx, r14d
0x14013158b  lea     rcx, [rbp+var_40]
0x14013158f  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140131594  mov     qword ptr [rbp+var_40+8], rbx
0x140131598  mov     rax, qword ptr [rbp+var_40]
0x14013159c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401315a0  jz      loc_140131811
0x1401315a6  test    rbx, rbx
0x1401315a9  jnz     short loc_1401315B4
0x1401315ab  test    rax, rax
0x1401315ae  jnz     loc_140131811
0x1401315b4  lea     rbx, [rdi+30h]
0x1401315b8  movups  xmm0, [rbp+var_40]
0x1401315bc  movdqu  xmmword ptr [rbx], xmm0
0x1401315c0  movups  xmm6, xmm0
0x1401315c3  movaps  [rbp+var_40], xmm0
0x1401315c7  lea     rcx, [rbp+var_40]
0x1401315cb  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x1401315d0  mov     r8, rax; Size
0x1401315d3  xor     edx, edx; Val
0x1401315d5  psrldq  xmm6, 8
0x1401315da  movq    rcx, xmm6; void *
0x1401315df  call    memset_0
0x1401315e4  mov     rax, [rbx]
0x1401315e7  mov     rsi, [rbx+8]
0x1401315eb  mov     qword ptr [rbp+var_40], rax
0x1401315ef  mov     qword ptr [rbp+var_40+8], rsi
0x1401315f3  lea     rcx, [rbp+var_40]
0x1401315f7  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x1401315fc  cmp     rax, 0Ch
0x140131600  jb      loc_140131811
0x140131606  lea     rcx, [rbp+var_40]
0x14013160a  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x14013160f  mov     dword ptr [rsi], 1000h
0x140131615  mov     eax, [rdi+10h]
0x140131618  mov     [rsi+4], eax
0x14013161b  mov     r8d, 40h ; '@'
0x140131621  mov     [rsi+8], r8d
0x140131625  lea     rdx, [rbp+var_28]
0x140131629  mov     rcx, rbx
0x14013162c  call    ?subspan@?$span@E$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<uchar,-1>::subspan(unsigned __int64,unsigned __int64)
0x140131631  movups  xmm6, xmmword ptr [rax]
0x140131634  movaps  [rbp+var_40], xmm6
0x140131638  lea     rcx, [rbp+var_40]
0x14013163c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140131641  test    al, 7Fh
0x140131643  jnz     loc_140131804
0x140131649  movdqa  [rbp+var_40], xmm6
0x14013164e  psrldq  xmm6, 8
0x140131653  movq    rbx, xmm6
0x140131658  lea     rcx, [rbp+var_40]
0x14013165c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140131661  shr     rax, 7
0x140131665  mov     rdx, rax
0x140131668  lea     rcx, [rbp+var_40]
0x14013166c  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140131671  mov     qword ptr [rbp+var_40+8], rbx
0x140131675  mov     rax, qword ptr [rbp+var_40]
0x140131679  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14013167d  jz      loc_140131804
0x140131683  test    rbx, rbx
0x140131686  jnz     short loc_140131691
0x140131688  test    rax, rax
0x14013168b  jnz     loc_140131804
0x140131691  movups  xmm0, [rbp+var_40]
0x140131695  movdqu  xmmword ptr [rdi+40h], xmm0
0x14013169a  mov     r14, [rdi+48h]
0x14013169e  mov     rsi, [rdi+40h]
0x1401316a2  shl     rsi, 7
0x1401316a6  add     rsi, r14
0x1401316a9  cmp     r14, rsi
0x1401316ac  jz      loc_140131750
0x1401316b2  mov     [rbp+var_28], 0
0x1401316ba  mov     ecx, 0A0h; Size
0x1401316bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401316c4  mov     rbx, rax
0x1401316c7  mov     qword ptr [rbp+var_40], rax
0x1401316cb  xor     edx, edx; Val
0x1401316cd  mov     r8d, 0A0h; Size
0x1401316d3  mov     rcx, rax; void *
0x1401316d6  call    memset_0
0x1401316db  mov     r8, r13; void *
0x1401316de  mov     rdx, r14; struct HDV::IPC::CallControlBlock *
0x1401316e1  mov     rcx, rbx; this
0x1401316e4  call    ??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z; HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)
0x1401316e9  mov     rbx, rax
0x1401316ec  test    rax, rax
0x1401316ef  jnz     short loc_1401316F5
0x1401316f1  xor     ecx, ecx
0x1401316f3  jmp     short loc_140131704
0x1401316f5  mov     rax, [rax+8]
0x1401316f9  movsxd  rcx, dword ptr [rax+4]
0x1401316fd  add     rcx, 8
0x140131701  add     rcx, rbx; this
0x140131704  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x140131709  mov     [rbp+var_28], rbx
0x14013170d  mov     rdx, [rdi+60h]
0x140131711  cmp     rdx, [rdi+68h]
0x140131715  jz      short loc_140131729
0x140131717  mov     [rbp+var_28], 0
0x14013171f  mov     [rdx], rbx
0x140131722  add     qword ptr [rdi+60h], 8
0x140131727  jmp     short loc_140131737
0x140131729  lea     r8, [rbp+var_28]
0x14013172d  lea     rcx, [rdi+58h]
0x140131731  call    ??$_Emplace_reallocate@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@VCallImpl@Details@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy>>(wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> * const,wil::com_ptr_t<HDV::IPC::Details::CallImpl,wil::err_exception_policy> &&)
0x140131736  nop
0x140131737  lea     rcx, [rbp+var_28]
0x14013173b  call    ??1?$com_ptr_t@VDeviceHostServices@IPC@HDV@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>::~com_ptr_t<HDV::IPC::DeviceHostServices,wil::err_exception_policy>(void)
0x140131740  sub     r14, 0FFFFFFFFFFFFFF80h
0x140131744  cmp     r14, rsi
0x140131747  jnz     loc_1401316B2
0x14013174d  xor     r15d, r15d
0x140131750  mov     rbx, [rdi+18h]
0x140131754  call    cs:__imp_GetCurrentProcess
0x14013175b  nop     dword ptr [rax+rax+00h]
0x140131760  mov     [rsp+80h+dwOptions], r15d; dwOptions
0x140131765  mov     dword ptr [rsp+80h+lpName], r15d; bInheritHandle
0x14013176a  mov     [rsp+80h+dwMaximumSizeLow], 6; dwDesiredAccess
0x140131772  mov     r9, [rbp+lpTargetHandle]; lpTargetHandle
0x140131776  mov     r8, r13; hTargetProcessHandle
0x140131779  mov     rdx, rbx; hSourceHandle
0x14013177c  mov     rcx, rax; hSourceProcessHandle
0x14013177f  call    cs:__imp_DuplicateHandle
0x140131786  nop     dword ptr [rax+rax+00h]
0x14013178b  mov     rcx, [rbp+38h]; this
0x14013178f  test    eax, eax
0x140131791  jnz     short loc_1401317A5
0x140131793  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x14013179a  mov     edx, 102h; void *
0x14013179f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401317a5  mov     rbx, [rdi+70h]
0x1401317a9  mov     [rdi+70h], r12
0x1401317ad  test    r12, r12
0x1401317b0  jz      short loc_1401317C2
0x1401317b2  mov     rax, [r12]
0x1401317b6  mov     rcx, r12
0x1401317b9  mov     rax, [rax+8]
0x1401317bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401317c2  test    rbx, rbx
0x1401317c5  jz      short loc_1401317D7
0x1401317c7  mov     rax, [rbx]
0x1401317ca  mov     rcx, rbx
0x1401317cd  mov     rax, [rax+10h]
0x1401317d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401317d6  nop
0x1401317d7  mov     rcx, [rbp+var_18]
0x1401317db  xor     rcx, rsp; StackCookie
0x1401317de  call    __security_check_cookie
0x1401317e3  mov     rbx, [rsp+80h+arg_8]
0x1401317eb  movaps  xmm6, [rsp+80h+var_10]
0x1401317f0  add     rsp, 80h
0x1401317f7  pop     r15
0x1401317f9  pop     r14
0x1401317fb  pop     r13
0x1401317fd  pop     r12
0x1401317ff  pop     rdi
0x140131800  pop     rsi
0x140131801  pop     rbp
0x140131802  retn
0x140131804  call    cs:__imp__o_terminate
0x14013180b  nop     dword ptr [rax+rax+00h]
0x140131810  int     3; Trap to Debugger
0x140131811  call    cs:__imp__o_terminate
0x140131818  nop     dword ptr [rax+rax+00h]
0x14013181d  int     3; Trap to Debugger
```
