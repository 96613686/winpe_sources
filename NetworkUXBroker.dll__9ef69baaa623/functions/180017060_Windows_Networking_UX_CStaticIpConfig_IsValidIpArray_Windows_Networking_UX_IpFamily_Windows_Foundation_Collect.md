# Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(Windows::Networking::UX::IpFamily,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,uchar *)

- ea: `0x180017060`
- end: `0x180017182`
- name: `?IsValidIpArray@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@PEAE@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019df8`

## callees

- `0x18000e768`
- `0x180017060`
- `0x180017188`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001712e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001712e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017164`

## string_xrefs

- `0x1800170b1`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x18001714f`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::IsValidIpArray(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _BYTE *a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  int IsValidIpFormat; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+40h] BYREF
  HSTRING string; // [rsp+68h] [rbp+48h] BYREF

  v17 = a1;
  *a4 = 1;
  v18 = 0;
  if ( a3
    && (v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a3 + 56LL))(a3, &v18), v8 = v7, v7 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)v7,
      savedregs);
    return v8;
  }
  else
  {
    for ( i = 0; i < v18; ++i )
    {
      string = 0;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a3 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      IsValidIpFormat = v11(a3, i, &string);
      v8 = IsValidIpFormat;
      if ( IsValidIpFormat < 0 )
      {
        v14 = 594;
        goto LABEL_14;
      }
      LOBYTE(v17) = 0;
      IsValidIpFormat = Windows::Networking::UX::CStaticIpConfig::IsValidIpFormat(v13, a2, string, &v17);
      v8 = IsValidIpFormat;
      if ( IsValidIpFormat < 0 )
      {
        v14 = 597;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)IsValidIpFormat,
          savedregs);
        goto LABEL_15;
      }
      if ( !(_BYTE)v17 )
      {
        *a4 = 0;
        v8 = 0;
LABEL_15:
        WindowsDeleteString(string);
        return v8;
      }
      WindowsDeleteString(string);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180017060  mov     [rsp-28h+arg_8], rbx
0x180017065  mov     [rsp-28h+arg_0], rcx
0x18001706a  push    rbp
0x18001706b  push    rsi
0x18001706c  push    rdi
0x18001706d  push    r14
0x18001706f  push    r15; int
0x180017071  mov     rbp, rsp
0x180017074  sub     rsp, 20h
0x180017078  mov     r14, r9
0x18001707b  mov     rsi, r8
0x18001707e  mov     r15d, edx
0x180017081  mov     byte ptr [r9], 1
0x180017085  mov     [rbp+arg_10], 0
0x18001708c  test    r8, r8
0x18001708f  jz      short loc_1800170C9
0x180017091  mov     rax, [r8]
0x180017094  lea     rdx, [rbp+arg_10]
0x180017098  mov     rcx, r8
0x18001709b  mov     rax, [rax+38h]
0x18001709f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170a4  mov     ebx, eax
0x1800170a6  test    eax, eax
0x1800170a8  jns     short loc_1800170C9
0x1800170aa  mov     rcx, [rbp+28h]; this
0x1800170ae  mov     r9d, eax; char *
0x1800170b1  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x1800170b8  mov     edx, 24Ch; void *
0x1800170bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800170c2  mov     eax, ebx
0x1800170c4  jmp     loc_180017171
0x1800170c9  xor     edi, edi
0x1800170cb  cmp     edi, [rbp+arg_10]
0x1800170ce  jnb     loc_18001716F
0x1800170d4  mov     [rbp+string], 0
0x1800170dc  mov     rax, [rsi]
0x1800170df  mov     rbx, [rax+30h]
0x1800170e3  xor     ecx, ecx; string
0x1800170e5  call    cs:__imp_WindowsDeleteString
0x1800170eb  mov     [rbp+string], 0
0x1800170f3  lea     r8, [rbp+string]
0x1800170f7  mov     edx, edi
0x1800170f9  mov     rcx, rsi
0x1800170fc  mov     rax, rbx
0x1800170ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017104  mov     ebx, eax
0x180017106  test    eax, eax
0x180017108  js      short loc_180017147
0x18001710a  mov     byte ptr [rbp+arg_0], 0
0x18001710e  lea     r9, [rbp+arg_0]
0x180017112  mov     r8, [rbp+string]
0x180017116  mov     edx, r15d
0x180017119  call    ?IsValidIpFormat@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAE@Z; Windows::Networking::UX::CStaticIpConfig::IsValidIpFormat(Windows::Networking::UX::IpFamily,HSTRING__ *,uchar *)
0x18001711e  mov     ebx, eax
0x180017120  test    eax, eax
0x180017122  js      short loc_180017140
0x180017124  cmp     byte ptr [rbp+arg_0], 0
0x180017128  jz      short loc_180017138
0x18001712a  mov     rcx, [rbp+string]; string
0x18001712e  call    cs:__imp_WindowsDeleteString
0x180017134  inc     edi
0x180017136  jmp     short loc_1800170CB
0x180017138  mov     byte ptr [r14], 0
0x18001713c  xor     ebx, ebx
0x18001713e  jmp     short loc_180017160
0x180017140  mov     edx, 255h
0x180017145  jmp     short loc_18001714C
0x180017147  mov     edx, 252h; void *
0x18001714c  mov     r9d, eax; char *
0x18001714f  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180017156  mov     rcx, [rbp+28h]; this
0x18001715a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001715f  nop
0x180017160  mov     rcx, [rbp+string]; string
0x180017164  call    cs:__imp_WindowsDeleteString
0x18001716a  jmp     loc_1800170C2
0x18001716f  xor     eax, eax
0x180017171  mov     rbx, [rsp+20h+arg_8]
0x180017176  add     rsp, 20h
0x18001717a  pop     r15
0x18001717c  pop     r14
0x18001717e  pop     rdi
0x18001717f  pop     rsi
0x180017180  pop     rbp
0x180017181  retn
```
