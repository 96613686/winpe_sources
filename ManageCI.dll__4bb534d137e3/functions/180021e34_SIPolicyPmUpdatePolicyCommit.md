# SIPolicyPmUpdatePolicyCommit

- ea: `0x180021e34`
- end: `0x180021f53`
- name: `SIPolicyPmUpdatePolicyCommit`
- size: `287`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001595c`

## callees

- `0x180020b44`
- `0x180021e34`
- `0x18002230c`
- `0x180022a30`
- `0x180022bb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f36`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021e9b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021e9b`
- `ntdll!RtlFreeUnicodeString` at `0x180021f19`
- `ntdll!RtlFreeUnicodeString` at `0x180021f23`
- `ntdll!RtlFreeUnicodeString` at `0x180021f2d`
- `ntdll!RtlFreeUnicodeString` at `0x180021f19`
- `ntdll!RtlFreeUnicodeString` at `0x180021f23`
- `ntdll!RtlFreeUnicodeString` at `0x180021f2d`

## pseudocode

```c
__int64 __fastcall SIPolicyPmUpdatePolicyCommit(__int64 a1)
{
  void *v1; // rdi
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbx
  const UNICODE_STRING *v5; // r14
  char IsStateSeparationEnabled; // al
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  struct _UNICODE_STRING *p_UnicodeString; // rdx
  __int64 v11; // rcx
  struct _UNICODE_STRING v13; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v15; // [rsp+50h] [rbp-10h] BYREF
  ULONG v16; // [rsp+80h] [rbp+20h] BYREF
  void *v17; // [rsp+88h] [rbp+28h] BYREF

  v1 = 0;
  v3 = *(_QWORD *)a1;
  v17 = 0;
  v16 = 0;
  UnicodeString = 0;
  v13 = 0;
  v15 = 0;
  if ( !v3 )
    v3 = *(_QWORD *)(a1 + 8) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v3 )
  {
    v5 = 0;
    v4 = (_QWORD *)a1;
  }
  else
  {
    v4 = 0;
    v5 = (const UNICODE_STRING *)(a1 + 16);
  }
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = SIPolicyPmBuildPathFromPolicyID(v4, v5, IsStateSeparationEnabled, &UnicodeString, &v15, &v13);
  if ( v8 >= 0 )
  {
    v8 = SIPolicyPmReadPolicy(v7, &v13, &v17, &v16);
    if ( v8 < 0 )
    {
      v1 = v17;
    }
    else
    {
      p_UnicodeString = &UnicodeString;
      v1 = v17;
      if ( !*(_BYTE *)(a1 + 32) )
        p_UnicodeString = &v15;
      v8 = SIPolicyPmWritePolicy(v9, p_UnicodeString, v17, v16);
      if ( v8 >= 0 )
        SIPolicyPmDeletePolicy(v11, &v13);
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v15);
  RtlFreeUnicodeString(&v13);
  LocalFree(v1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021e34  mov     [rsp-18h+arg_10], rbx
0x180021e39  mov     [rsp-18h+arg_18], rsi
0x180021e3e  push    rbp
0x180021e3f  push    rdi
0x180021e40  push    r14
0x180021e42  mov     rbp, rsp
0x180021e45  sub     rsp, 60h
0x180021e49  xor     edi, edi
0x180021e4b  mov     rsi, rcx
0x180021e4e  mov     rcx, [rcx]
0x180021e51  xorps   xmm0, xmm0
0x180021e54  xorps   xmm2, xmm2
0x180021e57  mov     [rbp+arg_8], rdi
0x180021e5b  movq    rax, xmm2
0x180021e60  mov     [rbp+arg_0], edi
0x180021e63  xorps   xmm1, xmm1
0x180021e66  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180021e6a  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x180021e6e  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x180021e72  sub     rcx, rax
0x180021e75  jnz     short loc_180021E88
0x180021e77  mov     rcx, [rsi+8]
0x180021e7b  psrldq  xmm2, 8
0x180021e80  movq    rax, xmm2
0x180021e85  sub     rcx, rax
0x180021e88  test    rcx, rcx
0x180021e8b  jnz     short loc_180021E95
0x180021e8d  xor     ebx, ebx
0x180021e8f  lea     r14, [rsi+10h]
0x180021e93  jmp     short loc_180021E9B
0x180021e95  xor     r14d, r14d
0x180021e98  mov     rbx, rsi
0x180021e9b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180021ea1  lea     rcx, [rbp+var_30]
0x180021ea5  mov     rdx, r14
0x180021ea8  mov     [rsp+60h+var_38], rcx
0x180021ead  lea     r9, [rbp+UnicodeString]
0x180021eb1  lea     rcx, [rbp+var_10]
0x180021eb5  mov     r8b, al
0x180021eb8  mov     [rsp+60h+var_40], rcx
0x180021ebd  mov     rcx, rbx
0x180021ec0  call    SIPolicyPmBuildPathFromPolicyID
0x180021ec5  mov     ebx, eax
0x180021ec7  test    eax, eax
0x180021ec9  js      short loc_180021F15
0x180021ecb  lea     r9, [rbp+arg_0]
0x180021ecf  lea     r8, [rbp+arg_8]
0x180021ed3  lea     rdx, [rbp+var_30]
0x180021ed7  call    SIPolicyPmReadPolicy
0x180021edc  mov     ebx, eax
0x180021ede  test    eax, eax
0x180021ee0  js      short loc_180021F11
0x180021ee2  cmp     [rsi+20h], dil
0x180021ee6  lea     rdx, [rbp+UnicodeString]
0x180021eea  mov     rdi, [rbp+arg_8]
0x180021eee  mov     r9d, [rbp+arg_0]
0x180021ef2  mov     r8, rdi
0x180021ef5  jnz     short loc_180021EFB
0x180021ef7  lea     rdx, [rbp+var_10]
0x180021efb  call    SIPolicyPmWritePolicy
0x180021f00  mov     ebx, eax
0x180021f02  test    eax, eax
0x180021f04  js      short loc_180021F15
0x180021f06  lea     rdx, [rbp+var_30]
0x180021f0a  call    SIPolicyPmDeletePolicy
0x180021f0f  jmp     short loc_180021F15
0x180021f11  mov     rdi, [rbp+arg_8]
0x180021f15  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180021f19  call    cs:__imp_RtlFreeUnicodeString
0x180021f1f  lea     rcx, [rbp+var_10]; UnicodeString
0x180021f23  call    cs:__imp_RtlFreeUnicodeString
0x180021f29  lea     rcx, [rbp+var_30]; UnicodeString
0x180021f2d  call    cs:__imp_RtlFreeUnicodeString
0x180021f33  mov     rcx, rdi; hMem
0x180021f36  call    cs:__imp_LocalFree
0x180021f3c  lea     r11, [rsp+60h+var_s0]
0x180021f41  mov     eax, ebx
0x180021f43  mov     rbx, [r11+30h]
0x180021f47  mov     rsi, [r11+38h]
0x180021f4b  mov     rsp, r11
0x180021f4e  pop     r14
0x180021f50  pop     rdi
0x180021f51  pop     rbp
0x180021f52  retn
```
