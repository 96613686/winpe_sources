# AiGetAppxFileAttributes

- ea: `0x180006a70`
- end: `0x180006d88`
- name: `AiGetAppxFileAttributes`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002b20`

## callees

- `0x180005cfc`
- `0x180006a70`
- `0x180006d90`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ae0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d00`
- `ntdll!RtlFreeHeap` at `0x180006cc4`
- `ntdll!RtlFreeHeap` at `0x180006cf6`
- `ntdll!RtlFreeHeap` at `0x180006cc4`
- `ntdll!RtlFreeHeap` at `0x180006cf6`
- `ntdll!RtlInitUnicodeString` at `0x180006c07`
- `ntdll!RtlInitUnicodeString` at `0x180006c57`
- `ntdll!RtlInitUnicodeString` at `0x180006c07`
- `ntdll!RtlInitUnicodeString` at `0x180006c57`

## pseudocode

```c
__int64 __fastcall AiGetAppxFileAttributes(__int64 a1, __int64 a2)
{
  HRESULT v4; // ebx
  PVOID v5; // rsi
  PVOID v6; // rdi
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // r8d
  int v13; // ebx
  WCHAR *v14; // rcx
  PCWSTR SourceString; // [rsp+30h] [rbp-49h] BYREF
  __int64 v17; // [rsp+38h] [rbp-41h] BYREF
  __int64 v18; // [rsp+40h] [rbp-39h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v20; // [rsp+60h] [rbp-19h] BYREF
  __int64 v21; // [rsp+68h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+7h] BYREF
  PVOID v24[2]; // [rsp+90h] [rbp+17h] BYREF
  _QWORD v25[6]; // [rsp+A0h] [rbp+27h] BYREF
  int v26; // [rsp+F0h] [rbp+77h] BYREF
  PCWSTR v27; // [rsp+F8h] [rbp+7Fh] BYREF

  ppv = 0;
  v21 = 0;
  v18 = 0;
  v20 = 0;
  v17 = 0;
  v26 = 0;
  SourceString = 0;
  v27 = 0;
  *(_OWORD *)v24 = 0;
  v25[0] = 0;
  *(_OWORD *)P = 0;
  v4 = CoCreateInstance(&IID_AppxFactory, 0, 1u, &IID_IAppxFactory, &ppv);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, a1, &v21);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, &v18);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, &v20);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v20 + 24LL))(v20, L"Framework", &v26);
  if ( v4 < 0 )
    goto LABEL_8;
  if ( v26 )
  {
    v4 = -2146958844;
LABEL_8:
    v5 = v24[1];
LABEL_9:
    v6 = P[1];
    goto LABEL_10;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v17);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v17 + 24LL))(v17, &SourceString);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v17 + 40LL))(v17, &v27);
  if ( v4 < 0 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v17 + 48LL))(v17, v25);
  if ( v4 < 0 )
    goto LABEL_8;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v9 = AiEncodeAttributeString(&DestinationString, v8, v24);
  v5 = v24[1];
  if ( v9 < 0 )
  {
    v4 = v9 | 0x10000000;
    goto LABEL_9;
  }
  if ( !v24[1] )
  {
    *(struct _UNICODE_STRING *)v24 = DestinationString;
    v5 = (PVOID)_mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0];
    SourceString = 0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v27);
  v11 = AiEncodeAttributeString(&DestinationString, v10, P);
  v6 = P[1];
  v13 = v11;
  if ( v11 >= 0 )
  {
    if ( !P[1] )
    {
      *(struct _UNICODE_STRING *)P = DestinationString;
      v6 = (PVOID)_mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0];
      v27 = 0;
    }
    v13 = AiConvertToTokenAttributes((unsigned int)P, (unsigned int)v24, v12, v25[0], a2);
  }
  v4 = v13 | 0x10000000;
LABEL_10:
  if ( v6 )
  {
    if ( v27 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v7 = (WCHAR *)v27;
    }
    else
    {
      v7 = (WCHAR *)v6;
    }
    CoTaskMemFree(v7);
  }
  if ( v5 )
  {
    if ( SourceString )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      v14 = (WCHAR *)SourceString;
    }
    else
    {
      v14 = (WCHAR *)v5;
    }
    CoTaskMemFree(v14);
  }
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006a70  mov     [rsp-8+arg_0], rbx
0x180006a75  push    rbp
0x180006a76  push    rsi
0x180006a77  push    rdi
0x180006a78  push    r14
0x180006a7a  push    r15
0x180006a7c  lea     rbp, [rsp-37h]
0x180006a81  sub     rsp, 0B0h
0x180006a88  xor     r15d, r15d
0x180006a8b  lea     rax, [rbp+57h+var_60]
0x180006a8f  mov     r14, rdx
0x180006a92  mov     [rbp+57h+var_60], r15
0x180006a96  mov     rdi, rcx
0x180006a99  mov     [rbp+57h+var_68], r15
0x180006a9d  xorps   xmm0, xmm0
0x180006aa0  mov     [rbp+57h+var_90], r15
0x180006aa4  xorps   xmm1, xmm1
0x180006aa7  mov     [rbp+57h+var_70], r15
0x180006aab  lea     r8d, [r15+1]; dwClsContext
0x180006aaf  mov     [rbp+57h+var_98], r15
0x180006ab3  lea     r9, IID_IAppxFactory; riid
0x180006aba  mov     [rbp+57h+arg_10], r15d
0x180006abe  xor     edx, edx; pUnkOuter
0x180006ac0  mov     [rbp+57h+SourceString], r15
0x180006ac4  lea     rcx, IID_AppxFactory; rclsid
0x180006acb  mov     [rbp+57h+arg_18], r15
0x180006acf  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180006ad3  mov     [rbp+57h+var_30], r15
0x180006ad7  movups  xmmword ptr [rbp+57h+P], xmm1
0x180006adb  mov     [rsp+0D0h+ppv], rax; ppv
0x180006ae0  call    cs:__imp_CoCreateInstance
0x180006ae6  mov     ebx, eax
0x180006ae8  test    eax, eax
0x180006aea  js      short loc_180006B69
0x180006aec  mov     rcx, [rbp+57h+var_60]
0x180006af0  lea     r8, [rbp+57h+var_68]
0x180006af4  mov     rdx, rdi
0x180006af7  mov     rax, [rcx]
0x180006afa  mov     rax, [rax+20h]
0x180006afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b03  mov     ebx, eax
0x180006b05  test    eax, eax
0x180006b07  js      short loc_180006B69
0x180006b09  mov     rcx, [rbp+57h+var_68]
0x180006b0d  lea     rdx, [rbp+57h+var_90]
0x180006b11  mov     rax, [rcx]
0x180006b14  mov     rax, [rax+38h]
0x180006b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1d  mov     ebx, eax
0x180006b1f  test    eax, eax
0x180006b21  js      short loc_180006B69
0x180006b23  mov     rcx, [rbp+57h+var_90]
0x180006b27  lea     rdx, [rbp+57h+var_70]
0x180006b2b  mov     rax, [rcx]
0x180006b2e  mov     rax, [rax+20h]
0x180006b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b37  mov     ebx, eax
0x180006b39  test    eax, eax
0x180006b3b  js      short loc_180006B69
0x180006b3d  mov     rcx, [rbp+57h+var_70]
0x180006b41  lea     r8, [rbp+57h+arg_10]
0x180006b45  lea     rdx, aFramework; "Framework"
0x180006b4c  mov     rax, [rcx]
0x180006b4f  mov     rax, [rax+18h]
0x180006b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b58  mov     ebx, eax
0x180006b5a  test    eax, eax
0x180006b5c  js      short loc_180006B69
0x180006b5e  cmp     [rbp+57h+arg_10], r15d
0x180006b62  jz      short loc_180006B8C
0x180006b64  mov     ebx, 80080204h
0x180006b69  mov     rsi, [rbp+57h+var_40+8]
0x180006b6d  mov     rdi, [rbp+57h+P+8]
0x180006b71  test    rdi, rdi
0x180006b74  jz      loc_180006CD4
0x180006b7a  cmp     [rbp+57h+arg_18], r15
0x180006b7e  jnz     loc_180006CB2
0x180006b84  mov     rcx, rdi
0x180006b87  jmp     loc_180006CCE
0x180006b8c  mov     rcx, [rbp+57h+var_90]
0x180006b90  lea     rdx, [rbp+57h+var_98]
0x180006b94  mov     rax, [rcx]
0x180006b97  mov     rax, [rax+18h]
0x180006b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba0  mov     ebx, eax
0x180006ba2  test    eax, eax
0x180006ba4  js      short loc_180006B69
0x180006ba6  mov     rcx, [rbp+57h+var_98]
0x180006baa  lea     rdx, [rbp+57h+SourceString]
0x180006bae  mov     rax, [rcx]
0x180006bb1  mov     rax, [rax+18h]
0x180006bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bba  mov     ebx, eax
0x180006bbc  test    eax, eax
0x180006bbe  js      short loc_180006B69
0x180006bc0  mov     rcx, [rbp+57h+var_98]
0x180006bc4  lea     rdx, [rbp+57h+arg_18]
0x180006bc8  mov     rax, [rcx]
0x180006bcb  mov     rax, [rax+28h]
0x180006bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd4  mov     ebx, eax
0x180006bd6  test    eax, eax
0x180006bd8  js      short loc_180006B69
0x180006bda  mov     rcx, [rbp+57h+var_98]
0x180006bde  lea     rdx, [rbp+57h+var_30]
0x180006be2  mov     rax, [rcx]
0x180006be5  mov     rax, [rax+30h]
0x180006be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bee  mov     ebx, eax
0x180006bf0  test    eax, eax
0x180006bf2  js      loc_180006B69
0x180006bf8  mov     rdx, [rbp+57h+SourceString]; SourceString
0x180006bfc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006c00  xorps   xmm0, xmm0
0x180006c03  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006c07  call    cs:__imp_RtlInitUnicodeString
0x180006c0d  lea     r8, [rbp+57h+var_40]
0x180006c11  lea     rcx, [rbp+57h+DestinationString]
0x180006c15  call    AiEncodeAttributeString
0x180006c1a  mov     rsi, [rbp+57h+var_40+8]
0x180006c1e  mov     ebx, eax
0x180006c20  test    eax, eax
0x180006c22  jns     short loc_180006C2D
0x180006c24  bts     ebx, 1Ch
0x180006c28  jmp     loc_180006B6D
0x180006c2d  test    rsi, rsi
0x180006c30  jnz     short loc_180006C48
0x180006c32  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x180006c36  movaps  xmmword ptr [rbp+57h+var_40], xmm0
0x180006c3a  psrldq  xmm0, 8
0x180006c3f  movq    rsi, xmm0
0x180006c44  mov     [rbp+57h+SourceString], r15
0x180006c48  mov     rdx, [rbp+57h+arg_18]; SourceString
0x180006c4c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006c50  xorps   xmm0, xmm0
0x180006c53  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006c57  call    cs:__imp_RtlInitUnicodeString
0x180006c5d  lea     r8, [rbp+57h+P]
0x180006c61  lea     rcx, [rbp+57h+DestinationString]
0x180006c65  call    AiEncodeAttributeString
0x180006c6a  mov     rdi, [rbp+57h+P+8]
0x180006c6e  mov     ebx, eax
0x180006c70  test    eax, eax
0x180006c72  jns     short loc_180006C7D
0x180006c74  bts     ebx, 1Ch
0x180006c78  jmp     loc_180006B71
0x180006c7d  test    rdi, rdi
0x180006c80  jnz     short loc_180006C98
0x180006c82  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x180006c86  movaps  xmmword ptr [rbp+57h+P], xmm0
0x180006c8a  psrldq  xmm0, 8
0x180006c8f  movq    rdi, xmm0
0x180006c94  mov     [rbp+57h+arg_18], r15
0x180006c98  mov     r9, [rbp+57h+var_30]
0x180006c9c  lea     rdx, [rbp+57h+var_40]
0x180006ca0  lea     rcx, [rbp+57h+P]
0x180006ca4  mov     [rsp+0D0h+ppv], r14
0x180006ca9  call    AiConvertToTokenAttributes
0x180006cae  mov     ebx, eax
0x180006cb0  jmp     short loc_180006C74
0x180006cb2  mov     rcx, gs:60h
0x180006cbb  mov     r8, rdi; P
0x180006cbe  xor     edx, edx; Flags
0x180006cc0  mov     rcx, [rcx+30h]; HeapHandle
0x180006cc4  call    cs:__imp_RtlFreeHeap
0x180006cca  mov     rcx, [rbp+57h+arg_18]; pv
0x180006cce  call    cs:__imp_CoTaskMemFree
0x180006cd4  test    rsi, rsi
0x180006cd7  jz      short loc_180006D06
0x180006cd9  cmp     [rbp+57h+SourceString], r15
0x180006cdd  jnz     short loc_180006CE4
0x180006cdf  mov     rcx, rsi
0x180006ce2  jmp     short loc_180006D00
0x180006ce4  mov     rcx, gs:60h
0x180006ced  mov     r8, rsi; P
0x180006cf0  xor     edx, edx; Flags
0x180006cf2  mov     rcx, [rcx+30h]; HeapHandle
0x180006cf6  call    cs:__imp_RtlFreeHeap
0x180006cfc  mov     rcx, [rbp+57h+SourceString]; pv
0x180006d00  call    cs:__imp_CoTaskMemFree
0x180006d06  mov     rcx, [rbp+57h+var_98]
0x180006d0a  test    rcx, rcx
0x180006d0d  jz      short loc_180006D1B
0x180006d0f  mov     rax, [rcx]
0x180006d12  mov     rax, [rax+10h]
0x180006d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1b  mov     rcx, [rbp+57h+var_70]
0x180006d1f  test    rcx, rcx
0x180006d22  jz      short loc_180006D30
0x180006d24  mov     rax, [rcx]
0x180006d27  mov     rax, [rax+10h]
0x180006d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d30  mov     rcx, [rbp+57h+var_90]
0x180006d34  test    rcx, rcx
0x180006d37  jz      short loc_180006D45
0x180006d39  mov     rax, [rcx]
0x180006d3c  mov     rax, [rax+10h]
0x180006d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d45  mov     rcx, [rbp+57h+var_68]
0x180006d49  test    rcx, rcx
0x180006d4c  jz      short loc_180006D5A
0x180006d4e  mov     rax, [rcx]
0x180006d51  mov     rax, [rax+10h]
0x180006d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5a  mov     rcx, [rbp+57h+var_60]
0x180006d5e  test    rcx, rcx
0x180006d61  jz      short loc_180006D6F
0x180006d63  mov     rax, [rcx]
0x180006d66  mov     rax, [rax+10h]
0x180006d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6f  mov     eax, ebx
0x180006d71  mov     rbx, [rsp+0D0h+arg_0]
0x180006d79  add     rsp, 0B0h
0x180006d80  pop     r15
0x180006d82  pop     r14
0x180006d84  pop     rdi
0x180006d85  pop     rsi
0x180006d86  pop     rbp
0x180006d87  retn
```
