# SharedFileToken::Initialize(_GUID const &,ushort const *,_GUID const &,_DS_TOKEN_USAGE_TYPE const &,_DS_TOKEN_LIFETIME_TYPE const &,ShareAccessControl const &,ushort const *,ushort const *,ushort const *)

- ea: `0x180013bf0`
- end: `0x180013d38`
- name: `?Initialize@SharedFileToken@@QEAAJAEBU_GUID@@PEBG0AEBW4_DS_TOKEN_USAGE_TYPE@@AEBW4_DS_TOKEN_LIFETIME_TYPE@@AEBVShareAccessControl@@111@Z`
- size: `328`
- prototype: `__int64 __usercall@<rax>(SharedFileToken *__hidden this@<rcx>, const struct _GUID *@<rdx>, const unsigned __int16 *@<r8>, const struct _GUID *@<r9>, const enum _DS_TOKEN_USAGE_TYPE *, const enum _DS_TOKEN_LIFETIME_TYPE *, const struct ShareAccessControl *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f740`

## callees

- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x180011c64`
- `0x180013bf0`
- `0x180014434`

## string_xrefs

- `0x180013c2d`: `SharedFileToken::Initialize failed as filepath length exceeds DS_MAX_PATH`
- `0x180013c3a`: `SharedFileToken::Initialize`
- `0x180013d1c`: `SharedFileToken::Initialize`

## pseudocode

```c
__int64 __fastcall SharedFileToken::Initialize(
        SharedFileToken *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        const enum _DS_TOKEN_USAGE_TYPE *a5,
        const enum _DS_TOKEN_LIFETIME_TYPE *a6,
        const struct ShareAccessControl *a7,
        const unsigned __int16 *a8,
        wil *a9,
        const unsigned __int16 *a10)
{
  __int64 v10; // r10
  __int64 v11; // rax
  int *v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  int *v16; // rax
  const unsigned __int16 *v17; // rdx
  bool is_extended_length_path; // al
  int *v19; // rax
  enum _DS_TOKEN_USAGE_TYPE *v21; // [rsp+20h] [rbp-48h]

  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a8[v11] );
  if ( (unsigned __int64)(v11 + 1) >= 0x7FFF )
  {
    v13 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(0x7FFF);
    DSLogger::LogError(
      (DSLogger *)v13,
      L"SharedFileToken::Initialize",
      148,
      L"SharedFileToken::Initialize failed as filepath length exceeds DS_MAX_PATH");
LABEL_5:
    v15 = -1055719416;
LABEL_14:
    v19 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v14);
    LODWORD(v21) = v15;
    DSLogger::LogError((DSLogger *)v19, L"SharedFileToken::Initialize", 176, L"hr=0x%x.", v21);
    return (unsigned int)v15;
  }
  do
    ++v10;
  while ( *((_WORD *)a9 + v10) );
  if ( (unsigned __int64)(v10 + 1) >= 0x7FFF )
  {
    v16 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(0x7FFF);
    DSLogger::LogError((DSLogger *)v16, L"SharedFileToken::Initialize", 156, (const unsigned __int16 *)&stru_180022210);
    goto LABEL_5;
  }
  v15 = SharingToken::Initialize(this, a2, a3, a4, a5, a6, a7);
  if ( v15 < 0 )
    goto LABEL_14;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 184,
                           a8)
    || (is_extended_length_path = wil::is_extended_length_path(a9, v17),
        !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 152,
                            (char *)a9 + 8 * is_extended_length_path))
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 216,
                           a10) )
  {
    v15 = -2147024882;
    goto LABEL_14;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180013bf0  push    rbx
0x180013bf2  push    rbp
0x180013bf3  push    rsi
0x180013bf4  push    rdi
0x180013bf5  push    r14
0x180013bf7  sub     rsp, 40h
0x180013bfb  mov     rbp, [rsp+68h+arg_38]
0x180013c03  or      r10, 0FFFFFFFFFFFFFFFFh
0x180013c07  mov     rax, r10
0x180013c0a  xor     r14d, r14d
0x180013c0d  mov     rdi, rcx
0x180013c10  inc     rax
0x180013c13  cmp     [rbp+rax*2+0], r14w
0x180013c19  jnz     short loc_180013C10
0x180013c1b  inc     rax
0x180013c1e  mov     ecx, 7FFFh
0x180013c23  cmp     rax, rcx
0x180013c26  jb      short loc_180013C53
0x180013c28  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180013c2d  lea     r9, aSharedfiletoke_2; "SharedFileToken::Initialize failed as f"...
0x180013c34  mov     r8d, 94h; unsigned int
0x180013c3a  lea     rdx, aSharedfiletoke_0; "SharedFileToken::Initialize"
0x180013c41  mov     rcx, rax; this
0x180013c44  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180013c49  mov     ebx, 0C1130008h
0x180013c4e  jmp     loc_180013D06
0x180013c53  mov     rsi, [rsp+68h+arg_40]
0x180013c5b  inc     r10
0x180013c5e  cmp     [rsi+r10*2], r14w
0x180013c63  jnz     short loc_180013C5B
0x180013c65  lea     rax, [r10+1]
0x180013c69  cmp     rax, rcx
0x180013c6c  jb      short loc_180013C82
0x180013c6e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180013c73  lea     r9, stru_180022210; struct _GUID *
0x180013c7a  mov     r8d, 9Ch; unsigned __int16 *
0x180013c80  jmp     short loc_180013C3A
0x180013c82  mov     rax, [rsp+68h+arg_30]
0x180013c8a  mov     rcx, rdi; this
0x180013c8d  mov     [rsp+68h+var_38], rax; struct ShareAccessControl *
0x180013c92  mov     rax, [rsp+68h+arg_28]
0x180013c9a  mov     [rsp+68h+var_40], rax; enum _DS_TOKEN_LIFETIME_TYPE *
0x180013c9f  mov     rax, [rsp+68h+arg_20]
0x180013ca7  mov     [rsp+68h+var_48], rax; enum _DS_TOKEN_USAGE_TYPE *
0x180013cac  call    ?Initialize@SharingToken@@QEAAJAEBU_GUID@@PEBG0AEBW4_DS_TOKEN_USAGE_TYPE@@AEBW4_DS_TOKEN_LIFETIME_TYPE@@AEBVShareAccessControl@@@Z; SharingToken::Initialize(_GUID const &,ushort const *,_GUID const &,_DS_TOKEN_USAGE_TYPE const &,_DS_TOKEN_LIFETIME_TYPE const &,ShareAccessControl const &)
0x180013cb1  mov     ebx, eax
0x180013cb3  test    eax, eax
0x180013cb5  js      short loc_180013D06
0x180013cb7  lea     rcx, [rdi+0B8h]
0x180013cbe  mov     rdx, rbp
0x180013cc1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013cc6  test    al, al
0x180013cc8  jz      short loc_180013D01
0x180013cca  mov     rcx, rsi; this
0x180013ccd  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180013cd2  movzx   eax, al
0x180013cd5  lea     rcx, [rdi+98h]
0x180013cdc  lea     rdx, [rsi+rax*8]
0x180013ce0  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013ce5  test    al, al
0x180013ce7  jz      short loc_180013D01
0x180013ce9  mov     rdx, [rsp+68h+arg_48]
0x180013cf1  lea     rcx, [rdi+0D8h]
0x180013cf8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013cfd  test    al, al
0x180013cff  jnz     short loc_180013D2B
0x180013d01  mov     ebx, 8007000Eh
0x180013d06  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180013d0b  lea     r9, aHr0xX; "hr=0x%x."
0x180013d12  mov     dword ptr [rsp+68h+var_48], ebx
0x180013d16  mov     r8d, 0B0h; unsigned int
0x180013d1c  lea     rdx, aSharedfiletoke_0; "SharedFileToken::Initialize"
0x180013d23  mov     rcx, rax; this
0x180013d26  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180013d2b  mov     eax, ebx
0x180013d2d  add     rsp, 40h
0x180013d31  pop     r14
0x180013d33  pop     rdi
0x180013d34  pop     rsi
0x180013d35  pop     rbp
0x180013d36  pop     rbx
0x180013d37  retn
```
