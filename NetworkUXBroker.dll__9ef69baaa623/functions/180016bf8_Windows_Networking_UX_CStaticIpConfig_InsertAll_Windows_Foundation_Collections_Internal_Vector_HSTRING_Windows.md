# Windows::Networking::UX::CStaticIpConfig::InsertAll(Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>> *)

- ea: `0x180016bf8`
- end: `0x180016d0e`
- name: `?InsertAll@CStaticIpConfig@UX@Networking@Windows@@AEAAJPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@4@PEAV?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@6784@@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800161d0`

## callees

- `0x18000e768`
- `0x180016bf8`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016cf3`

## string_xrefs

- `0x180016c3a`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180016cdc`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::InsertAll(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int i; // edi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+58h] [rbp+10h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  v15 = a1;
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    for ( i = 0; i < v16; ++i )
    {
      string = 0;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a2 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v10 = v9(a2, i, &string);
      v6 = v10;
      if ( v10 < 0 )
      {
        v12 = 708;
        goto LABEL_11;
      }
      LOBYTE(v15) = 0;
      LOBYTE(v11) = 1;
      v10 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 *))(*(_QWORD *)a3 + 80LL))(
              a3,
              string,
              v11,
              &v15);
      v6 = v10;
      if ( v10 < 0 )
      {
        v12 = 711;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
          (const char *)(unsigned int)v10,
          v13);
        WindowsDeleteString(string);
        return v6;
      }
      WindowsDeleteString(string);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BF,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
      (const char *)(unsigned int)v5,
      v13);
    return v6;
  }
}

```

## disassembly

```asm
0x180016bf8  mov     [rsp+arg_10], rbx
0x180016bfd  mov     [rsp+arg_0], rcx
0x180016c02  push    rsi
0x180016c03  push    rdi
0x180016c04  push    r14
0x180016c06  sub     rsp, 30h
0x180016c0a  mov     r14, r8
0x180016c0d  mov     rsi, rdx
0x180016c10  mov     [rsp+48h+arg_8], 0
0x180016c18  mov     rax, [rdx]
0x180016c1b  lea     rdx, [rsp+48h+arg_8]
0x180016c20  mov     rcx, rsi
0x180016c23  mov     rax, [rax+38h]
0x180016c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2c  mov     ebx, eax
0x180016c2e  test    eax, eax
0x180016c30  jns     short loc_180016C52
0x180016c32  mov     rcx, [rsp+48h]; this
0x180016c37  mov     r9d, eax; char *
0x180016c3a  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180016c41  mov     edx, 2BFh; void *
0x180016c46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c4b  mov     eax, ebx
0x180016c4d  jmp     loc_180016D00
0x180016c52  xor     edi, edi
0x180016c54  cmp     edi, [rsp+48h+arg_8]
0x180016c58  jnb     loc_180016CFE
0x180016c5e  mov     [rsp+48h+string], 0
0x180016c67  mov     rax, [rsi]
0x180016c6a  mov     rbx, [rax+30h]
0x180016c6e  xor     ecx, ecx; string
0x180016c70  call    cs:__imp_WindowsDeleteString
0x180016c76  mov     [rsp+48h+string], 0
0x180016c7f  lea     r8, [rsp+48h+string]
0x180016c84  mov     edx, edi
0x180016c86  mov     rcx, rsi
0x180016c89  mov     rax, rbx
0x180016c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c91  mov     ebx, eax
0x180016c93  test    eax, eax
0x180016c95  js      short loc_180016CD4
0x180016c97  mov     byte ptr [rsp+48h+arg_0], 0
0x180016c9c  mov     rax, [r14]
0x180016c9f  lea     r9, [rsp+48h+arg_0]
0x180016ca4  mov     r8b, 1
0x180016ca7  mov     rdx, [rsp+48h+string]
0x180016cac  mov     rcx, r14
0x180016caf  mov     rax, [rax+50h]
0x180016cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cb8  mov     ebx, eax
0x180016cba  test    eax, eax
0x180016cbc  js      short loc_180016CCD
0x180016cbe  mov     rcx, [rsp+48h+string]; string
0x180016cc3  call    cs:__imp_WindowsDeleteString
0x180016cc9  inc     edi
0x180016ccb  jmp     short loc_180016C54
0x180016ccd  mov     edx, 2C7h
0x180016cd2  jmp     short loc_180016CD9
0x180016cd4  mov     edx, 2C4h; void *
0x180016cd9  mov     r9d, eax; char *
0x180016cdc  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180016ce3  mov     rcx, [rsp+48h]; this
0x180016ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ced  nop
0x180016cee  mov     rcx, [rsp+48h+string]; string
0x180016cf3  call    cs:__imp_WindowsDeleteString
0x180016cf9  jmp     loc_180016C4B
0x180016cfe  xor     eax, eax
0x180016d00  mov     rbx, [rsp+48h+arg_10]
0x180016d05  add     rsp, 30h
0x180016d09  pop     r14
0x180016d0b  pop     rdi
0x180016d0c  pop     rsi
0x180016d0d  retn
```
