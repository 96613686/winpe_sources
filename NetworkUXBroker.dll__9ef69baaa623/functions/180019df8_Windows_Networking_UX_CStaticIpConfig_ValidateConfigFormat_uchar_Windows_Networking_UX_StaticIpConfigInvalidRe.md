# Windows::Networking::UX::CStaticIpConfig::ValidateConfigFormat(uchar *,Windows::Networking::UX::StaticIpConfigInvalidReasons *)

- ea: `0x180019df8`
- end: `0x18001a13a`
- name: `?ValidateConfigFormat@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAEPEAW4StaticIpConfigInvalidReasons@234@@Z`
- size: `834`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CStaticIpConfig *__hidden this, unsigned __int8 *, enum Windows::Networking::UX::StaticIpConfigInvalidReasons *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180015b10`

## callees

- `0x180002520`
- `0x18000c78c`
- `0x18000e768`
- `0x18000f0b0`
- `0x180013b8c`
- `0x180014df0`
- `0x180017060`
- `0x180017188`
- `0x180019df8`
- `0x18001a900`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a06a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a06a`

## string_xrefs

- `0x180019e61`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019edb`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019f63`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180019fa3`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001a103`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::ValidateConfigFormat(
        Windows::Networking::UX::CStaticIpConfig *this,
        unsigned __int8 *a2,
        enum Windows::Networking::UX::StaticIpConfigInvalidReasons *a3)
{
  int IsValidIpArray; // eax
  int Size; // ebx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int IsValidIpFormat; // r14d
  unsigned int v12; // r14d
  int v13; // eax
  unsigned int v14; // r15d
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rcx
  enum Windows::Networking::UX::StaticIpConfigInvalidReasons *v18; // rax
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-49h] BYREF
  enum Windows::Networking::UX::StaticIpConfigInvalidReasons *v21; // [rsp+28h] [rbp-41h] BYREF
  unsigned int v22; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-35h] BYREF
  __int128 v24; // [rsp+38h] [rbp-31h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h]
  enum Windows::Networking::UX::StaticIpConfigInvalidReasons **v26; // [rsp+50h] [rbp-19h]
  char v27; // [rsp+58h] [rbp-11h]
  _BYTE v28[16]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v29; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v21 = a3;
  *a2 = 1;
  *(_DWORD *)a3 = 1;
  v26 = &v21;
  v27 = 1;
  LOBYTE(v20) = 0;
  IsValidIpArray = Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(
                     (__int64)this,
                     *((_DWORD *)this + 8),
                     *((_QWORD *)this + 5),
                     &v20);
  Size = IsValidIpArray;
  if ( IsValidIpArray < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)IsValidIpArray,
      v20);
    if ( *(_DWORD *)v21 != 1 )
      *(_DWORD *)v21 &= ~1u;
    return (unsigned int)Size;
  }
  v8 = 32;
  if ( !(_BYTE)v20 )
  {
    *a2 = 0;
    *(_DWORD *)v21 |= 0x20u;
  }
  v22 = 0;
  if ( *((_DWORD *)this + 8) != 4 )
    v8 = 128;
  v9 = *((_QWORD *)this + 6);
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 56LL))(v9, &v22);
    IsValidIpFormat = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v10,
        v20);
      if ( *(_DWORD *)v21 != 1 )
        *(_DWORD *)v21 &= ~1u;
      return (unsigned int)IsValidIpFormat;
    }
    v12 = 0;
    if ( v22 )
    {
      while ( 1 )
      {
        v23 = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 6) + 48LL))(
                *((_QWORD *)this + 6),
                v12,
                &v23);
        v14 = v13;
        if ( v13 < 0 )
          break;
        if ( v23 > v8 )
        {
          *a2 = 0;
          *(_DWORD *)v21 |= 0x40u;
          goto LABEL_18;
        }
        if ( ++v12 >= v22 )
          goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v13,
        v20);
      if ( *(_DWORD *)v21 != 1 )
        *(_DWORD *)v21 &= ~1u;
      return v14;
    }
  }
LABEL_18:
  LOBYTE(v20) = 0;
  Size = Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(
           v9,
           *((_DWORD *)this + 8),
           *((_QWORD *)this + 7),
           &v20);
  if ( Size < 0 )
  {
    v15 = 528;
    goto LABEL_20;
  }
  if ( !(_BYTE)v20 )
  {
    *a2 = 0;
    *(_DWORD *)v21 |= 0x80u;
  }
  Size = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::get_Size(
           *((_QWORD *)this + 9),
           &v22);
  if ( Size < 0 )
  {
    v15 = 536;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)Size,
      v20);
    if ( *(_DWORD *)v21 != 1 )
      *(_DWORD *)v21 &= ~1u;
    return (unsigned int)Size;
  }
  v16 = 0;
  if ( v22 )
  {
    while ( 1 )
    {
      v24 = 0;
      string = 0;
      IsValidIpFormat = Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(
                          *((_QWORD *)this + 9),
                          v16,
                          &v24);
      if ( IsValidIpFormat < 0 )
        break;
      IsValidIpFormat = Windows::Networking::UX::CStaticIpConfig::IsValidIpFormat(
                          v17,
                          *((unsigned int *)this + 8),
                          *((_QWORD *)&v24 + 1),
                          &v20);
      if ( IsValidIpFormat < 0 )
      {
        v19 = 543;
        goto LABEL_50;
      }
      if ( !(_BYTE)v20 )
      {
        *a2 = 0;
        if ( v16 )
          *(_DWORD *)v21 |= 0x200u;
        else
          *(_DWORD *)v21 |= 0x100u;
      }
      WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(v28);
      if ( (BYTE4(v24) & 2) != 0 && !v29 )
      {
        *a2 = 0;
        if ( v16 )
          *(_DWORD *)v21 |= 0x800u;
        else
          *(_DWORD *)v21 |= 0x400u;
      }
      std::wstring::_Tidy_deallocate(v28);
      FreeDnsServer((HSTRING *)&v24);
      if ( ++v16 >= v22 )
        goto LABEL_43;
    }
    v19 = 541;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)IsValidIpFormat,
      v20);
    FreeDnsServer((HSTRING *)&v24);
    if ( *(_DWORD *)v21 != 1 )
      *(_DWORD *)v21 &= ~1u;
    return (unsigned int)IsValidIpFormat;
  }
LABEL_43:
  v18 = v21;
  if ( *(_DWORD *)v21 == 1 )
  {
    *(_DWORD *)v21 = 0;
    v18 = v21;
  }
  if ( *(_DWORD *)v18 != 1 )
    *(_DWORD *)v18 &= ~1u;
  return 0;
}

```

## disassembly

```asm
0x180019df8  push    rbp
0x180019dfa  push    rbx
0x180019dfb  push    rsi
0x180019dfc  push    rdi
0x180019dfd  push    r12
0x180019dff  push    r14
0x180019e01  push    r15
0x180019e03  lea     rbp, [rsp-27h]
0x180019e08  sub     rsp, 90h
0x180019e0f  mov     rax, cs:__security_cookie
0x180019e16  xor     rax, rsp
0x180019e19  mov     [rbp+57h+var_40], rax
0x180019e1d  mov     rsi, rdx
0x180019e20  mov     rdi, rcx
0x180019e23  mov     [rbp+57h+var_98], r8
0x180019e27  mov     byte ptr [rdx], 1
0x180019e2a  mov     dword ptr [r8], 1
0x180019e31  lea     rax, [rbp+57h+var_98]
0x180019e35  mov     [rbp+57h+var_70], rax
0x180019e39  mov     [rbp+57h+var_68], 1
0x180019e3d  xor     r12d, r12d
0x180019e40  mov     byte ptr [rbp+57h+var_A0], r12b
0x180019e44  lea     r9, [rbp+57h+var_A0]
0x180019e48  mov     r8, [rcx+28h]
0x180019e4c  mov     edx, [rcx+20h]
0x180019e4f  call    ?IsValidIpArray@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@PEAE@Z; Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(Windows::Networking::UX::IpFamily,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,uchar *)
0x180019e54  mov     ebx, eax
0x180019e56  test    eax, eax
0x180019e58  jns     short loc_180019E8A
0x180019e5a  mov     rcx, [rbp+5Fh]; this
0x180019e5e  mov     r9d, eax; char *
0x180019e61  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019e68  mov     edx, 1F3h; void *
0x180019e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e72  nop
0x180019e73  mov     rdx, [rbp+57h+var_98]
0x180019e77  mov     ecx, [rdx]
0x180019e79  cmp     ecx, 1
0x180019e7c  jz      short loc_180019E83
0x180019e7e  and     ecx, 0FFFFFFFEh
0x180019e81  mov     [rdx], ecx
0x180019e83  mov     eax, ebx
0x180019e85  jmp     loc_18001A0D9
0x180019e8a  mov     ebx, 20h ; ' '
0x180019e8f  cmp     byte ptr [rbp+57h+var_A0], r12b
0x180019e93  jnz     short loc_180019E9E
0x180019e95  mov     [rsi], r12b
0x180019e98  mov     rax, [rbp+57h+var_98]
0x180019e9c  or      [rax], ebx
0x180019e9e  mov     [rbp+57h+var_90], r12d
0x180019ea2  mov     r14d, 80h
0x180019ea8  cmp     dword ptr [rdi+20h], 4
0x180019eac  cmovnz  ebx, r14d
0x180019eb0  mov     rcx, [rdi+30h]
0x180019eb4  test    rcx, rcx
0x180019eb7  jz      loc_180019F44
0x180019ebd  mov     rax, [rcx]
0x180019ec0  lea     rdx, [rbp+57h+var_90]
0x180019ec4  mov     rax, [rax+38h]
0x180019ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ecd  mov     r14d, eax
0x180019ed0  test    eax, eax
0x180019ed2  jns     short loc_180019F05
0x180019ed4  mov     rcx, [rbp+5Fh]; this
0x180019ed8  mov     r9d, eax; char *
0x180019edb  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019ee2  mov     edx, 1FFh; void *
0x180019ee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eec  nop
0x180019eed  mov     rax, [rbp+57h+var_98]
0x180019ef1  mov     ecx, [rax]
0x180019ef3  cmp     ecx, 1
0x180019ef6  jz      short loc_180019EFD
0x180019ef8  and     ecx, 0FFFFFFFEh
0x180019efb  mov     [rax], ecx
0x180019efd  mov     eax, r14d
0x180019f00  jmp     loc_18001A0D9
0x180019f05  mov     r14d, r12d
0x180019f08  cmp     [rbp+57h+var_90], r12d
0x180019f0c  jbe     short loc_180019F3E
0x180019f0e  mov     [rbp+57h+var_8C], r12d
0x180019f12  mov     rcx, [rdi+30h]
0x180019f16  mov     rax, [rcx]
0x180019f19  lea     r8, [rbp+57h+var_8C]
0x180019f1d  mov     edx, r14d
0x180019f20  mov     rax, [rax+30h]
0x180019f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f29  mov     r15d, eax
0x180019f2c  test    eax, eax
0x180019f2e  js      short loc_180019F9C
0x180019f30  cmp     [rbp+57h+var_8C], ebx
0x180019f33  ja      short loc_180019F90
0x180019f35  inc     r14d
0x180019f38  cmp     r14d, [rbp+57h+var_90]
0x180019f3c  jb      short loc_180019F0E
0x180019f3e  mov     r14d, 80h
0x180019f44  mov     byte ptr [rbp+57h+var_A0], r12b
0x180019f48  lea     r9, [rbp+57h+var_A0]
0x180019f4c  mov     r8, [rdi+38h]
0x180019f50  mov     edx, [rdi+20h]
0x180019f53  call    ?IsValidIpArray@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@PEAE@Z; Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(Windows::Networking::UX::IpFamily,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,uchar *)
0x180019f58  mov     ebx, eax
0x180019f5a  test    eax, eax
0x180019f5c  jns     short loc_180019FCD
0x180019f5e  mov     edx, 210h; void *
0x180019f63  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019f6a  mov     r9d, ebx; char *
0x180019f6d  mov     rcx, [rbp+5Fh]; this
0x180019f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f76  nop
0x180019f77  mov     rax, [rbp+57h+var_98]
0x180019f7b  mov     ecx, [rax]
0x180019f7d  cmp     ecx, 1
0x180019f80  jz      loc_180019E83
0x180019f86  and     ecx, 0FFFFFFFEh
0x180019f89  mov     [rax], ecx
0x180019f8b  jmp     loc_180019E83
0x180019f90  mov     [rsi], r12b
0x180019f93  mov     rax, [rbp+57h+var_98]
0x180019f97  or      dword ptr [rax], 40h
0x180019f9a  jmp     short loc_180019F3E
0x180019f9c  mov     rcx, [rbp+5Fh]; this
0x180019fa0  mov     r9d, r15d; char *
0x180019fa3  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180019faa  mov     edx, 203h; void *
0x180019faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fb4  nop
0x180019fb5  mov     rcx, [rbp+57h+var_98]
0x180019fb9  mov     eax, [rcx]
0x180019fbb  cmp     eax, 1
0x180019fbe  jz      short loc_180019FC5
0x180019fc0  and     eax, 0FFFFFFFEh
0x180019fc3  mov     [rcx], eax
0x180019fc5  mov     eax, r15d
0x180019fc8  jmp     loc_18001A0D9
0x180019fcd  cmp     byte ptr [rbp+57h+var_A0], r12b
0x180019fd1  jnz     short loc_180019FDD
0x180019fd3  mov     [rsi], r12b
0x180019fd6  mov     rax, [rbp+57h+var_98]
0x180019fda  or      [rax], r14d
0x180019fdd  lea     rdx, [rbp+57h+var_90]
0x180019fe1  mov     rcx, [rdi+48h]
0x180019fe5  call    ?get_Size@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::get_Size(uint *)
0x180019fea  mov     ebx, eax
0x180019fec  test    eax, eax
0x180019fee  jns     short loc_180019FFA
0x180019ff0  mov     edx, 218h
0x180019ff5  jmp     loc_180019F63
0x180019ffa  mov     ebx, r12d
0x180019ffd  cmp     [rbp+57h+var_90], r12d
0x18001a001  jbe     loc_18001A0BB
0x18001a007  xorps   xmm0, xmm0
0x18001a00a  xor     eax, eax
0x18001a00c  movups  [rbp+57h+var_88], xmm0
0x18001a010  mov     [rbp+57h+string], rax
0x18001a014  lea     r8, [rbp+57h+var_88]
0x18001a018  mov     edx, ebx
0x18001a01a  mov     rcx, [rdi+48h]
0x18001a01e  call    ?GetAt@?$Vector@UDnsServer@UX@Networking@Windows@@UDnsServerEqualityPredicate@Internal@234@UDnsServerLifetimePredicate@6234@U?$VectorOptions@UDnsServer@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJIPEAUDnsServer@UX@Networking@5@@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::DnsServer,Windows::Networking::UX::Internal::DnsServerEqualityPredicate,Windows::Networking::UX::Internal::DnsServerLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::DnsServer,0,1,0>>::GetAt(uint,Windows::Networking::UX::DnsServer *)
0x18001a023  mov     r14d, eax
0x18001a026  test    eax, eax
0x18001a028  js      loc_18001A0FE
0x18001a02e  lea     r9, [rbp+57h+var_A0]
0x18001a032  mov     r8, qword ptr [rbp+57h+var_88+8]
0x18001a036  mov     edx, [rdi+20h]
0x18001a039  call    ?IsValidIpFormat@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAE@Z; Windows::Networking::UX::CStaticIpConfig::IsValidIpFormat(Windows::Networking::UX::IpFamily,HSTRING__ *,uchar *)
0x18001a03e  mov     r14d, eax
0x18001a041  test    eax, eax
0x18001a043  js      loc_18001A0F7
0x18001a049  cmp     byte ptr [rbp+57h+var_A0], r12b
0x18001a04d  jnz     short loc_18001A064
0x18001a04f  mov     [rsi], r12b
0x18001a052  mov     rax, [rbp+57h+var_98]
0x18001a056  test    ebx, ebx
0x18001a058  jnz     short loc_18001A060
0x18001a05a  bts     dword ptr [rax], 8
0x18001a05e  jmp     short loc_18001A064
0x18001a060  bts     dword ptr [rax], 9
0x18001a064  xor     edx, edx; length
0x18001a066  mov     rcx, [rbp+57h+string]; string
0x18001a06a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a070  mov     rdx, rax
0x18001a073  lea     rcx, [rbp+57h+var_60]
0x18001a077  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001a07c  test    byte ptr [rbp+57h+var_88+4], 2
0x18001a080  jz      short loc_18001A09D
0x18001a082  cmp     [rbp+57h+var_50], r12
0x18001a086  jnz     short loc_18001A09D
0x18001a088  mov     [rsi], r12b
0x18001a08b  mov     rax, [rbp+57h+var_98]
0x18001a08f  test    ebx, ebx
0x18001a091  jnz     short loc_18001A099
0x18001a093  bts     dword ptr [rax], 0Ah
0x18001a097  jmp     short loc_18001A09D
0x18001a099  bts     dword ptr [rax], 0Bh
0x18001a09d  lea     rcx, [rbp+57h+var_60]
0x18001a0a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a0a6  nop
0x18001a0a7  lea     rcx, [rbp+57h+var_88]; struct Windows::Networking::UX::DnsServer *
0x18001a0ab  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001a0b0  inc     ebx
0x18001a0b2  cmp     ebx, [rbp+57h+var_90]
0x18001a0b5  jb      loc_18001A007
0x18001a0bb  mov     rax, [rbp+57h+var_98]
0x18001a0bf  cmp     dword ptr [rax], 1
0x18001a0c2  jnz     short loc_18001A0CB
0x18001a0c4  mov     [rax], r12d
0x18001a0c7  mov     rax, [rbp+57h+var_98]
0x18001a0cb  mov     ecx, [rax]
0x18001a0cd  cmp     ecx, 1
0x18001a0d0  jz      short loc_18001A0D7
0x18001a0d2  and     ecx, 0FFFFFFFEh
0x18001a0d5  mov     [rax], ecx
0x18001a0d7  xor     eax, eax
0x18001a0d9  mov     rcx, [rbp+57h+var_40]
0x18001a0dd  xor     rcx, rsp; StackCookie
0x18001a0e0  call    __security_check_cookie
0x18001a0e5  add     rsp, 90h
0x18001a0ec  pop     r15
0x18001a0ee  pop     r14
0x18001a0f0  pop     r12
0x18001a0f2  pop     rdi
0x18001a0f3  pop     rsi
0x18001a0f4  pop     rbx
0x18001a0f5  pop     rbp
0x18001a0f6  retn
0x18001a0f7  mov     edx, 21Fh
0x18001a0fc  jmp     short loc_18001A103
0x18001a0fe  mov     edx, 21Dh; void *
0x18001a103  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001a10a  mov     r9d, r14d; char *
0x18001a10d  mov     rcx, [rbp+5Fh]; this
0x18001a111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a116  nop
0x18001a117  lea     rcx, [rbp+57h+var_88]; struct Windows::Networking::UX::DnsServer *
0x18001a11b  call    ?FreeDnsServer@@YAXPEAUDnsServer@UX@Networking@Windows@@@Z; FreeDnsServer(Windows::Networking::UX::DnsServer *)
0x18001a120  nop
0x18001a121  mov     rcx, [rbp+57h+var_98]
0x18001a125  mov     eax, [rcx]
0x18001a127  cmp     eax, 1
0x18001a12a  jz      loc_180019EFD
0x18001a130  and     eax, 0FFFFFFFEh
0x18001a133  mov     [rcx], eax
0x18001a135  jmp     loc_180019EFD
```
