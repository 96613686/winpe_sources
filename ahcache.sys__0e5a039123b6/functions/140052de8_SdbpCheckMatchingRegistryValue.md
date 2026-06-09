# SdbpCheckMatchingRegistryValue

- ea: `0x140052de8`
- end: `0x1400531ba`
- name: `SdbpCheckMatchingRegistryValue`
- size: `978`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14002f82c`
- `0x140052bf0`

## callees

- `0x14000440f`
- `0x14000449f`
- `0x1400044f9`
- `0x140006354`
- `0x1400063e8`
- `0x140007b40`
- `0x140008360`
- `0x14003e364`
- `0x14003e76c`
- `0x14004102c`
- `0x140045d44`
- `0x140052de8`
- `0x14005498c`

## string_xrefs

- `0x140052ec3`: `dbRegistryDefaultName`
- `0x140052e8f`: `SdbpCheckMatchingRegistryValue`
- `0x140052f54`: `SdbpCheckMatchingRegistryValue`
- `0x140052f9b`: `SdbpCheckMatchingRegistryValue`
- `0x140052f8e`: `Failed to read value`
- `0x140052ffc`: `Unknown registry value data type`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryValue(
        __int64 a1,
        void *a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        void *Src,
        size_t Size,
        _DWORD *a9)
{
  unsigned int v9; // esi
  __int64 v11; // rcx
  ULONG v13; // [rsp+30h] [rbp-51h]
  PCWSTR SourceString; // [rsp+38h] [rbp-49h]
  void *Buf1[2]; // [rsp+40h] [rbp-41h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-31h]
  wchar_t *Str1[2]; // [rsp+60h] [rbp-21h]
  __int128 v18; // [rsp+70h] [rbp-11h]

  SourceString = 0;
  v13 = 0;
  v9 = 0;
  DestinationString = 0;
  *(_OWORD *)Str1 = 0;
  v18 = 0;
  *(_OWORD *)Buf1 = 0;
  SdbpUmaInit_PCWSTR(a2);
  SdbpUmaInit_PCWSTR(a4);
  SdbpUmaInit_PCVOID(Src, Size);
  if ( *((_QWORD *)&v18 + 1) || !Buf1[0] && Buf1[1] )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryValue", 1205, "Out of memory");
  }
  else
  {
    *a9 = 1;
    v9 = 1;
  }
  if ( SourceString )
    AslFree(v11, (void *)SourceString);
  if ( Buf1[0] && Buf1[0] != Buf1[1] )
    AslFree(v11, Buf1[0]);
  return v9;
}

```

## disassembly

```asm
0x140052de8  mov     [rsp-8+KeyHandle], rcx
0x140052ded  push    rbp
0x140052dee  push    rbx
0x140052def  push    rsi
0x140052df0  push    rdi
0x140052df1  push    r12
0x140052df3  push    r13
0x140052df5  push    r14
0x140052df7  push    r15
0x140052df9  lea     rbp, [rsp-7]
0x140052dfe  sub     rsp, 88h
0x140052e05  xorps   xmm0, xmm0
0x140052e08  xor     edi, edi
0x140052e0a  mov     rcx, rdx; Src
0x140052e0d  mov     [rbp+3Fh+SourceString], rdi
0x140052e11  xorps   xmm1, xmm1
0x140052e14  mov     [rbp+3Fh+var_90], edi
0x140052e17  lea     rdx, [rbp+3Fh+Str1]
0x140052e1b  mov     esi, edi
0x140052e1d  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140052e21  mov     rbx, r9
0x140052e24  mov     r15d, r8d
0x140052e27  movups  xmmword ptr [rbp+3Fh+Str1], xmm0
0x140052e2b  movups  [rbp+3Fh+var_50], xmm1
0x140052e2f  movups  xmmword ptr [rbp+3Fh+Buf1], xmm0
0x140052e33  call    SdbpUmaInit_PCWSTR
0x140052e38  lea     rdx, [rbp+3Fh+var_50]
0x140052e3c  mov     rcx, rbx; Src
0x140052e3f  call    SdbpUmaInit_PCWSTR
0x140052e44  mov     rdx, [rbp+3Fh+Size]; Size
0x140052e4b  lea     r8, [rbp+3Fh+Buf1]
0x140052e4f  mov     rcx, [rbp+3Fh+Src]; Src
0x140052e53  call    SdbpUmaInit_PCVOID
0x140052e58  mov     r12, [rbp+3Fh+Str1]
0x140052e5c  mov     r13, qword ptr [rbp+3Fh+var_50]
0x140052e60  test    r12, r12
0x140052e63  jnz     short loc_140052E6B
0x140052e65  cmp     [rbp+3Fh+Str1+8], rdi
0x140052e69  jnz     short loc_140052E82
0x140052e6b  test    r13, r13
0x140052e6e  jnz     short loc_140052E76
0x140052e70  cmp     qword ptr [rbp+3Fh+var_50+8], rdi
0x140052e74  jnz     short loc_140052E82
0x140052e76  cmp     [rbp+3Fh+Buf1], rdi
0x140052e7a  jnz     short loc_140052EA5
0x140052e7c  cmp     [rbp+3Fh+Buf1+8], rdi
0x140052e80  jz      short loc_140052EA5
0x140052e82  lea     r9, aOutOfMemory; "Out of memory"
0x140052e89  mov     r8d, 4B5h
0x140052e8f  lea     rdx, aSdbpcheckmatch_8; "SdbpCheckMatchingRegistryValue"
0x140052e96  mov     ecx, 1
0x140052e9b  call    AslLogCallPrintf
0x140052ea0  jmp     loc_140053156
0x140052ea5  xor     eax, eax
0x140052ea7  mov     r14, rdi
0x140052eaa  mov     ebx, 1
0x140052eaf  test    r12, r12
0x140052eb2  jz      loc_14005312F
0x140052eb8  cmp     [r12], ax
0x140052ebd  jz      loc_14005312F
0x140052ec3  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x140052eca  mov     rcx, r12; Str1
0x140052ecd  call    _wcsicmp_0
0x140052ed2  test    eax, eax
0x140052ed4  jnz     short loc_140052EDA
0x140052ed6  xor     edx, edx
0x140052ed8  jmp     short loc_140052EF2
0x140052eda  mov     rdx, r12
0x140052edd  lea     rcx, [rbp+3Fh+SourceString]
0x140052ee1  call    AslStringDuplicate
0x140052ee6  test    eax, eax
0x140052ee8  js      loc_140053156
0x140052eee  mov     rdx, [rbp+3Fh+SourceString]; SourceString
0x140052ef2  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140052ef6  call    RtlInitUnicodeString_0
0x140052efb  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140052eff  lea     rax, [rbp+3Fh+var_90]
0x140052f03  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140052f08  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x140052f0c  xor     r9d, r9d; KeyValueInformation
0x140052f0f  mov     [rsp+0C0h+Length], edi; Length
0x140052f13  mov     r8d, ebx; KeyValueInformationClass
0x140052f16  call    ZwQueryValueKey_0
0x140052f1b  test    eax, eax
0x140052f1d  jns     short loc_140052F34
0x140052f1f  cmp     eax, 80000005h
0x140052f24  jz      short loc_140052F34
0x140052f26  cmp     eax, 0C0000023h
0x140052f2b  jz      short loc_140052F34
0x140052f2d  mov     esi, ebx
0x140052f2f  jmp     loc_140053156
0x140052f34  mov     edx, [rbp+3Fh+var_90]
0x140052f37  mov     r8d, ebx
0x140052f3a  call    AslAlloc
0x140052f3f  mov     rdi, rax
0x140052f42  test    rax, rax
0x140052f45  jnz     short loc_140052F67
0x140052f47  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140052f4e  mov     r8d, 4E1h
0x140052f54  lea     rdx, aSdbpcheckmatch_8; "SdbpCheckMatchingRegistryValue"
0x140052f5b  mov     ecx, ebx
0x140052f5d  call    AslLogCallPrintf
0x140052f62  jmp     loc_140053156
0x140052f67  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140052f6b  lea     rax, [rbp+3Fh+var_90]
0x140052f6f  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140052f74  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x140052f78  mov     eax, [rbp+3Fh+var_90]
0x140052f7b  mov     r9, rdi; KeyValueInformation
0x140052f7e  mov     r8d, ebx; KeyValueInformationClass
0x140052f81  mov     [rsp+0C0h+Length], eax; Length
0x140052f85  call    ZwQueryValueKey_0
0x140052f8a  test    eax, eax
0x140052f8c  jns     short loc_140052FAE
0x140052f8e  lea     r9, aFailedToReadVa_2; "Failed to read value"
0x140052f95  mov     r8d, 4ECh
0x140052f9b  lea     rdx, aSdbpcheckmatch_8; "SdbpCheckMatchingRegistryValue"
0x140052fa2  mov     ecx, ebx
0x140052fa4  call    AslLogCallPrintf
0x140052fa9  jmp     loc_14005313F
0x140052fae  test    r15d, r15d
0x140052fb1  jnz     short loc_140052FC3
0x140052fb3  mov     rax, [rbp+3Fh+arg_40]
0x140052fba  mov     [rax], ebx
0x140052fbc  mov     esi, ebx
0x140052fbe  jmp     loc_14005313F
0x140052fc3  mov     ecx, [rdi+4]
0x140052fc6  cmp     ecx, r15d
0x140052fc9  jnz     short loc_140052FBC
0x140052fcb  mov     r15d, [rdi+8]
0x140052fcf  add     r15, rdi
0x140052fd2  sub     ecx, ebx
0x140052fd4  jz      loc_1400530D3
0x140052fda  sub     ecx, ebx
0x140052fdc  jz      loc_1400530D3
0x140052fe2  sub     ecx, ebx
0x140052fe4  jz      loc_1400530AC
0x140052fea  sub     ecx, ebx
0x140052fec  jz      loc_14005309B
0x140052ff2  sub     ecx, 3
0x140052ff5  jz      short loc_140053017
0x140052ff7  cmp     ecx, 4
0x140052ffa  jz      short loc_14005300B
0x140052ffc  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x140053003  mov     r8d, 574h
0x140053009  jmp     short loc_140052F9B
0x14005300b  mov     rax, [r15]
0x14005300e  cmp     [rbp+3Fh+arg_28], rax
0x140053012  jmp     loc_1400530A1
0x140053017  mov     edx, [rdi+0Ch]
0x14005301a  mov     r8d, ebx
0x14005301d  add     rdx, 2
0x140053021  call    AslAlloc
0x140053026  mov     r14, rax
0x140053029  test    rax, rax
0x14005302c  jnz     short loc_140053040
0x14005302e  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140053035  mov     r8d, 529h
0x14005303b  jmp     loc_140052F9B
0x140053040  mov     r8d, [rdi+0Ch]; Size
0x140053044  mov     rdx, r15; Src
0x140053047  mov     rcx, r14; void *
0x14005304a  call    memmove
0x14005304f  mov     ecx, [rdi+0Ch]
0x140053052  shr     rcx, 1
0x140053055  mov     [r14+rcx*2], si
0x14005305a  mov     rcx, r14
0x14005305d  mov     eax, [rdi+0Ch]
0x140053060  and     rax, 0FFFFFFFFFFFFFFFEh
0x140053064  add     rax, r14
0x140053067  cmp     r14, rax
0x14005306a  jnb     loc_140053116
0x140053070  lea     rax, [rcx+2]
0x140053074  cmp     [rcx], si
0x140053077  jnz     short loc_140053087
0x140053079  cmp     [rax], si
0x14005307c  jz      loc_140053116
0x140053082  mov     word ptr [rcx], 3Bh ; ';'
0x140053087  mov     rcx, rax
0x14005308a  mov     eax, [rdi+0Ch]
0x14005308d  and     rax, 0FFFFFFFFFFFFFFFEh
0x140053091  add     rax, r14
0x140053094  cmp     rcx, rax
0x140053097  jb      short loc_140053070
0x140053099  jmp     short loc_140053116
0x14005309b  mov     eax, [r15]
0x14005309e  cmp     [rbp+3Fh+arg_20], eax
0x1400530a1  jz      loc_14005312F
0x1400530a7  jmp     loc_140052FBC
0x1400530ac  mov     eax, [rdi+0Ch]
0x1400530af  cmp     [rbp+3Fh+Size], rax
0x1400530b6  jnz     loc_140052FBC
0x1400530bc  mov     r8, [rbp+3Fh+Size]; Size
0x1400530c3  mov     rdx, r15; Buf2
0x1400530c6  mov     rcx, [rbp+3Fh+Buf1]; Buf1
0x1400530ca  call    memcmp
0x1400530cf  test    eax, eax
0x1400530d1  jmp     short loc_1400530A1
0x1400530d3  mov     edx, [rdi+0Ch]
0x1400530d6  mov     r8d, ebx
0x1400530d9  add     rdx, 2
0x1400530dd  call    AslAlloc
0x1400530e2  mov     r14, rax
0x1400530e5  test    rax, rax
0x1400530e8  jnz     short loc_1400530FC
0x1400530ea  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x1400530f1  mov     r8d, 511h
0x1400530f7  jmp     loc_140052F9B
0x1400530fc  mov     r8d, [rdi+0Ch]; Size
0x140053100  mov     rdx, r15; Src
0x140053103  mov     rcx, r14; void *
0x140053106  call    memmove
0x14005310b  mov     ecx, [rdi+0Ch]
0x14005310e  shr     rcx, 1
0x140053111  mov     [r14+rcx*2], si
0x140053116  xor     r9d, r9d
0x140053119  xor     r8d, r8d
0x14005311c  mov     rdx, r14
0x14005311f  mov     rcx, r13
0x140053122  call    AslStringPatternMatchExW
0x140053127  test    eax, eax
0x140053129  jz      loc_140052FBC
0x14005312f  mov     rax, [rbp+3Fh+arg_40]
0x140053136  mov     [rax], ebx
0x140053138  mov     esi, ebx
0x14005313a  test    rdi, rdi
0x14005313d  jz      short loc_140053147
0x14005313f  mov     rdx, rdi
0x140053142  call    AslFree
0x140053147  xor     edi, edi
0x140053149  test    r14, r14
0x14005314c  jz      short loc_140053156
0x14005314e  mov     rdx, r14
0x140053151  call    AslFree
0x140053156  mov     rdx, [rbp+3Fh+SourceString]
0x14005315a  test    rdx, rdx
0x14005315d  jz      short loc_140053164
0x14005315f  call    AslFree
0x140053164  test    r12, r12
0x140053167  jz      short loc_140053177
0x140053169  cmp     r12, [rbp+3Fh+Str1+8]
0x14005316d  jz      short loc_140053177
0x14005316f  mov     rdx, r12
0x140053172  call    AslFree
0x140053177  test    r13, r13
0x14005317a  jz      short loc_14005318A
0x14005317c  cmp     r13, qword ptr [rbp+3Fh+var_50+8]
0x140053180  jz      short loc_14005318A
0x140053182  mov     rdx, r13
0x140053185  call    AslFree
0x14005318a  cmp     [rbp+3Fh+Buf1], rdi
0x14005318e  jz      short loc_1400531A3
0x140053190  mov     rax, [rbp+3Fh+Buf1+8]
0x140053194  cmp     [rbp+3Fh+Buf1], rax
0x140053198  jz      short loc_1400531A3
0x14005319a  mov     rdx, [rbp+3Fh+Buf1]
0x14005319e  call    AslFree
0x1400531a3  mov     eax, esi
0x1400531a5  add     rsp, 88h
0x1400531ac  pop     r15
0x1400531ae  pop     r14
0x1400531b0  pop     r13
0x1400531b2  pop     r12
0x1400531b4  pop     rdi
0x1400531b5  pop     rsi
0x1400531b6  pop     rbx
0x1400531b7  pop     rbp
0x1400531b8  retn
```
