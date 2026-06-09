# HashAndEncodeForUninstallBlocklist

- ea: `0x18000dc54`
- end: `0x18000de88`
- name: `HashAndEncodeForUninstallBlocklist`
- size: `564`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d908`

## callees

- `0x18000dc54`
- `0x18000de90`
- `0x18000e050`
- `0x18000e18c`
- `0x18000e3c8`
- `0x18000e4d4`
- `0x180018248`
- `0x18001a56c`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlDowncaseUnicodeString` at `0x18000dcca`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000dcca`
- `ntdll!RtlFreeUnicodeString` at `0x18000dcee`
- `ntdll!RtlFreeUnicodeString` at `0x18000de45`
- `ntdll!RtlInitUnicodeString` at `0x18000dcb2`
- `ntdll!RtlInitUnicodeString` at `0x18000dcb2`

## string_xrefs

- `0x18000ddb1`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x18000dcd8`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000dd4d`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`
- `0x18000de62`: `onecore\base\appmodel\common\appxuninstallblocklist.cpp`

## pseudocode

```c
__int64 __fastcall HashAndEncodeForUninstallBlocklist(PCWSTR SourceString, __int64 a2, unsigned __int16 *a3)
{
  __int64 v4; // rdx
  PCWSTR v5; // rax
  signed int started; // ebx
  NTSTATUS v7; // eax
  void **v8; // rcx
  __int64 v9; // rdx
  void **v10; // rcx
  int v11; // eax
  void **v12; // rcx
  int v14; // [rsp+20h] [rbp-50h]
  struct _UNICODE_STRING UniDest; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct Common::CryptoProvider *v17[2]; // [rsp+50h] [rbp-20h] BYREF
  char v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF
  Common::CryptoProvider *v21; // [rsp+A8h] [rbp+38h] BYREF

  v20 = a2;
  if ( !SourceString )
  {
    started = -2147024809;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
      (const char *)(unsigned int)started,
      v14);
    return (unsigned int)started;
  }
  v4 = 65;
  v5 = SourceString;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  started = v4 == 0 ? 0x80070057 : 0;
  if ( !v4 )
    goto LABEL_29;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  UniDest = 0;
  v7 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 1u);
  if ( v7 < 0 )
  {
    started = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x2A,
                (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
                (const char *)(unsigned int)v7,
                v14);
LABEL_8:
    ((void (__fastcall *)(struct _UNICODE_STRING *))RtlFreeUnicodeString)(&UniDest);
    return (unsigned int)started;
  }
  v21 = 0;
  v17[0] = (struct Common::CryptoProvider *)&v21;
  v17[1] = 0;
  v18 = 1;
  started = Common::CryptoProvider::Create(&v17[1]);
  if ( v18 )
  {
    v8 = *(void ***)v17[0];
    *(_QWORD *)v17[0] = v17[1];
    if ( v8 )
      Common::CryptoProvider::`scalar deleting destructor'(v8);
  }
  if ( started < 0 )
  {
    v9 = 46;
    goto LABEL_14;
  }
  started = Common::CryptoProvider::StartDigest(v21);
  if ( started < 0 )
  {
    v9 = 47;
    goto LABEL_14;
  }
  v11 = ((__int64 (__fastcall *)(_QWORD, PWSTR, _QWORD, _QWORD))xmmword_180064E08)(
          *((_QWORD *)v21 + 1),
          UniDest.Buffer,
          UniDest.Length,
          0);
  if ( v11 < 0 )
  {
    started = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x91,
                (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
                (const char *)(unsigned int)v11,
                v14);
    if ( started < 0 )
    {
      v9 = 50;
      goto LABEL_14;
    }
  }
  *(_OWORD *)v17 = 0;
  started = Common::CryptoProvider::GetDigest(v21, (struct Common::COMMON_BYTES *)v17);
  if ( started < 0 )
  {
    v9 = 52;
    goto LABEL_14;
  }
  LODWORD(v20) = 0;
  started = Common::Base32Encoding::GetChars((const unsigned __int8 *)v17[1], 0x20u, 0x38u, a3, (unsigned int *)&v20);
  if ( started < 0 )
  {
    v9 = 57;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\common\\appxuninstallblocklist.cpp",
      (const char *)(unsigned int)started,
      v14);
    v10 = (void **)v21;
    v21 = 0;
    if ( v10 )
      Common::CryptoProvider::`scalar deleting destructor'(v10);
    goto LABEL_8;
  }
  a3[(unsigned int)(v20 + 1)] = 0;
  v12 = (void **)v21;
  v21 = 0;
  if ( v12 )
    Common::CryptoProvider::`scalar deleting destructor'(v12);
  ((void (__fastcall *)(struct _UNICODE_STRING *))RtlFreeUnicodeString)(&UniDest);
  return 0;
}

```

## disassembly

```asm
0x18000dc54  mov     [rsp-18h+arg_0], rbx
0x18000dc59  mov     [rsp-18h+arg_8], rdx
0x18000dc5e  push    rbp
0x18000dc5f  push    rsi
0x18000dc60  push    rdi
0x18000dc61  mov     rbp, rsp
0x18000dc64  sub     rsp, 70h
0x18000dc68  xor     esi, esi
0x18000dc6a  mov     rdi, r8
0x18000dc6d  test    rcx, rcx
0x18000dc70  jz      loc_18000DE59
0x18000dc76  lea     edx, [rsi+41h]
0x18000dc79  mov     rax, rcx
0x18000dc7c  cmp     [rax], si
0x18000dc7f  jz      short loc_18000DC8B
0x18000dc81  add     rax, 2
0x18000dc85  sub     rdx, 1
0x18000dc89  jnz     short loc_18000DC7C
0x18000dc8b  mov     rax, rdx
0x18000dc8e  neg     rax
0x18000dc91  sbb     ebx, ebx
0x18000dc93  not     ebx
0x18000dc95  and     ebx, 80070057h
0x18000dc9b  test    rdx, rdx
0x18000dc9e  jz      loc_18000DE5E
0x18000dca4  xorps   xmm0, xmm0
0x18000dca7  mov     rdx, rcx; SourceString
0x18000dcaa  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000dcae  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000dcb2  call    cs:__imp_RtlInitUnicodeString
0x18000dcb8  xorps   xmm0, xmm0
0x18000dcbb  lea     rdx, [rbp+DestinationString]; UniSource
0x18000dcbf  mov     r8b, 1; AllocateDestinationString
0x18000dcc2  lea     rcx, [rbp+UniDest]; UniDest
0x18000dcc6  movups  xmmword ptr [rbp+UniDest.Length], xmm0
0x18000dcca  call    cs:__imp_RtlDowncaseUnicodeString
0x18000dcd0  test    eax, eax
0x18000dcd2  jns     short loc_18000DD03
0x18000dcd4  mov     rcx, [rbp+18h]; this
0x18000dcd8  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000dcdf  mov     r9d, eax; char *
0x18000dce2  mov     edx, 2Ah ; '*'; void *
0x18000dce7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000dcec  mov     ebx, eax
0x18000dcee  mov     rax, cs:__imp_RtlFreeUnicodeString
0x18000dcf5  lea     rcx, [rbp+UniDest]
0x18000dcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcfe  jmp     loc_18000DE76
0x18000dd03  lea     rax, [rbp+arg_18]
0x18000dd07  mov     [rbp+arg_18], rsi
0x18000dd0b  lea     rcx, [rbp+var_20+8]; struct Common::CryptoProvider **
0x18000dd0f  mov     [rbp+var_20], rax
0x18000dd13  mov     [rbp+var_20+8], rsi
0x18000dd17  mov     [rbp+var_10], 1
0x18000dd1b  call    ?Create@CryptoProvider@Common@@SAJPEAPEAV12@@Z; Common::CryptoProvider::Create(Common::CryptoProvider * *)
0x18000dd20  mov     ebx, eax
0x18000dd22  cmp     [rbp+var_10], sil
0x18000dd26  jz      short loc_18000DD40
0x18000dd28  mov     rdx, [rbp+var_20]; unsigned int
0x18000dd2c  mov     rax, [rbp+var_20+8]
0x18000dd30  mov     rcx, [rdx]; this
0x18000dd33  mov     [rdx], rax
0x18000dd36  test    rcx, rcx
0x18000dd39  jz      short loc_18000DD40
0x18000dd3b  call    ??_GCryptoProvider@Common@@QEAAPEAXI@Z; Common::CryptoProvider::`scalar deleting destructor'(uint)
0x18000dd40  test    ebx, ebx
0x18000dd42  jns     short loc_18000DD73
0x18000dd44  mov     edx, 2Eh ; '.'; void *
0x18000dd49  mov     rcx, [rbp+18h]; this
0x18000dd4d  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000dd54  mov     r9d, ebx; char *
0x18000dd57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd5c  mov     rcx, [rbp+arg_18]; this
0x18000dd60  mov     [rbp+arg_18], rsi
0x18000dd64  test    rcx, rcx
0x18000dd67  jz      short loc_18000DCEE
0x18000dd69  call    ??_GCryptoProvider@Common@@QEAAPEAXI@Z; Common::CryptoProvider::`scalar deleting destructor'(uint)
0x18000dd6e  jmp     loc_18000DCEE
0x18000dd73  mov     rcx, [rbp+arg_18]; this
0x18000dd77  call    ?StartDigest@CryptoProvider@Common@@QEAAJXZ; Common::CryptoProvider::StartDigest(void)
0x18000dd7c  mov     ebx, eax
0x18000dd7e  test    eax, eax
0x18000dd80  jns     short loc_18000DD89
0x18000dd82  mov     edx, 2Fh ; '/'
0x18000dd87  jmp     short loc_18000DD49
0x18000dd89  mov     rcx, [rbp+arg_18]
0x18000dd8d  xor     r9d, r9d
0x18000dd90  movzx   r8d, [rbp+UniDest.Length]
0x18000dd95  mov     rdx, [rbp+UniDest.Buffer]
0x18000dd99  mov     rax, qword ptr cs:xmmword_180064E08
0x18000dda0  mov     rcx, [rcx+8]
0x18000dda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda9  test    eax, eax
0x18000ddab  jns     short loc_18000DDD5
0x18000ddad  mov     rcx, [rbp+18h]; this
0x18000ddb1  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\common\\crypto"...
0x18000ddb8  mov     r9d, eax; char *
0x18000ddbb  mov     edx, 91h; void *
0x18000ddc0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000ddc5  mov     ebx, eax
0x18000ddc7  test    eax, eax
0x18000ddc9  jns     short loc_18000DDD5
0x18000ddcb  mov     edx, 32h ; '2'
0x18000ddd0  jmp     loc_18000DD49
0x18000ddd5  mov     rcx, [rbp+arg_18]; this
0x18000ddd9  lea     rdx, [rbp+var_20]; struct Common::COMMON_BYTES *
0x18000dddd  xorps   xmm0, xmm0
0x18000dde0  movups  xmmword ptr [rbp+var_20], xmm0
0x18000dde4  call    ?GetDigest@CryptoProvider@Common@@QEAAJPEAUCOMMON_BYTES@2@@Z; Common::CryptoProvider::GetDigest(Common::COMMON_BYTES *)
0x18000dde9  mov     ebx, eax
0x18000ddeb  test    eax, eax
0x18000dded  jns     short loc_18000DDF9
0x18000ddef  mov     edx, 34h ; '4'
0x18000ddf4  jmp     loc_18000DD49
0x18000ddf9  mov     rcx, [rbp+var_20+8]; unsigned __int8 *
0x18000ddfd  lea     rax, [rbp+arg_8]
0x18000de01  mov     edx, 20h ; ' '; unsigned int
0x18000de06  mov     dword ptr [rbp+arg_8], esi
0x18000de09  mov     r9, rdi; unsigned __int16 *
0x18000de0c  mov     qword ptr [rsp+70h+var_50], rax; unsigned int *
0x18000de11  lea     r8d, [rdx+18h]; unsigned int
0x18000de15  call    ?GetChars@Base32Encoding@Common@@SAJPEBEKKPEAGPEAK@Z; Common::Base32Encoding::GetChars(uchar const *,ulong,ulong,ushort *,ulong *)
0x18000de1a  mov     ebx, eax
0x18000de1c  test    eax, eax
0x18000de1e  jns     short loc_18000DE2A
0x18000de20  mov     edx, 39h ; '9'
0x18000de25  jmp     loc_18000DD49
0x18000de2a  mov     eax, dword ptr [rbp+arg_8]
0x18000de2d  inc     eax
0x18000de2f  mov     [rdi+rax*2], si
0x18000de33  mov     rcx, [rbp+arg_18]; this
0x18000de37  mov     [rbp+arg_18], rsi
0x18000de3b  test    rcx, rcx
0x18000de3e  jz      short loc_18000DE45
0x18000de40  call    ??_GCryptoProvider@Common@@QEAAPEAXI@Z; Common::CryptoProvider::`scalar deleting destructor'(uint)
0x18000de45  mov     rax, cs:__imp_RtlFreeUnicodeString
0x18000de4c  lea     rcx, [rbp+UniDest]
0x18000de50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de55  xor     eax, eax
0x18000de57  jmp     short loc_18000DE78
0x18000de59  mov     ebx, 80070057h
0x18000de5e  mov     rcx, [rbp+18h]; this
0x18000de62  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\appxun"...
0x18000de69  mov     r9d, ebx; char *
0x18000de6c  mov     edx, 24h ; '$'; void *
0x18000de71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de76  mov     eax, ebx
0x18000de78  mov     rbx, [rsp+70h+arg_0]
0x18000de80  add     rsp, 70h
0x18000de84  pop     rdi
0x18000de85  pop     rsi
0x18000de86  pop     rbp
0x18000de87  retn
```
