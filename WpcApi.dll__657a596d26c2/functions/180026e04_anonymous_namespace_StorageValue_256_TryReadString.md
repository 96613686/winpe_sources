# _anonymous_namespace_::StorageValue_256_::TryReadString

- ea: `0x180026e04`
- end: `0x180026f84`
- name: `_anonymous_namespace_::StorageValue_256_::TryReadString`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180026df0`

## callees

- `0x1800032a0`
- `0x180005f9c`
- `0x18001b270`
- `0x18001fa1c`
- `0x180026e04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026e82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026f1f`
- `ADVAPI32!RegGetValueW` at `0x180026e6f`
- `ADVAPI32!RegGetValueW` at `0x180026f08`
- `ADVAPI32!RegGetValueW` at `0x180026e6f`
- `ADVAPI32!RegGetValueW` at `0x180026f08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::StorageValue_256_::TryReadString(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rdi
  const WCHAR *v5; // r8
  LSTATUS ValueW; // eax
  PVOID *pvData; // rax
  LSTATUS v8; // edi
  DWORD pcbData[4]; // [rsp+40h] [rbp-9h] BYREF
  PVOID *v11; // [rsp+50h] [rbp+7h] BYREF
  char v12; // [rsp+58h] [rbp+Fh]
  PVOID Src[2]; // [rsp+60h] [rbp+17h] BYREF
  __m128i si128; // [rsp+70h] [rbp+27h]

  pcbData[1] = HIDWORD(a2);
  pcbData[0] = 0;
  v4 = (const WCHAR *)(a1 - 56);
  if ( *(_QWORD *)(a1 - 56 + 24) <= 7u )
    v5 = (const WCHAR *)(a1 - 56);
  else
    v5 = *(const WCHAR **)v4;
  ValueW = RegGetValueW(*(HKEY *)(a1 - 24), 0, v5, 2u, 0, 0, pcbData);
  if ( !ValueW || ValueW == 234 )
  {
    *(_OWORD *)Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src[0]) = 0;
    v11 = Src;
    v12 = 1;
    std::wstring::resize(Src);
    pvData = Src;
    if ( si128.m128i_i64[1] > 7uLL )
      pvData = (PVOID *)Src[0];
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(const WCHAR **)v4;
    v8 = RegGetValueW(*(HKEY *)(a1 - 24), 0, v4, 2u, 0, pvData, pcbData);
    Private::Buffer<unsigned short>::~Buffer<unsigned short>(&v11);
    if ( v8 )
    {
      SetLastError(v8);
      *(_QWORD *)(a2 + 40) = 0;
    }
    else
    {
      *(_OWORD *)(a2 + 8) = *(_OWORD *)Src;
      *(__m128i *)(a2 + 24) = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(Src[0]) = 0;
      *(_QWORD *)(a2 + 40) = a2 + 8;
    }
    std::wstring::~wstring((char **)Src);
  }
  else
  {
    SetLastError(ValueW);
    *(_QWORD *)(a2 + 40) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180026e04  mov     [rsp-8+arg_10], rbx
0x180026e09  push    rbp
0x180026e0a  push    rsi
0x180026e0b  push    rdi
0x180026e0c  lea     rbp, [rsp-47h]
0x180026e11  sub     rsp, 90h
0x180026e18  mov     rax, cs:__security_cookie
0x180026e1f  xor     rax, rsp
0x180026e22  mov     [rbp+57h+var_20], rax
0x180026e26  mov     rbx, rdx
0x180026e29  mov     rsi, rcx
0x180026e2c  mov     qword ptr [rbp+57h+var_60], rdx
0x180026e30  mov     [rbp+57h+var_60], 0
0x180026e37  lea     rdi, [rcx-38h]
0x180026e3b  cmp     qword ptr [rdi+18h], 7
0x180026e40  jbe     short loc_180026E47
0x180026e42  mov     r8, [rdi]
0x180026e45  jmp     short loc_180026E4A
0x180026e47  mov     r8, rdi; lpValue
0x180026e4a  lea     rax, [rbp+57h+var_60]
0x180026e4e  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180026e53  mov     [rsp+0A0h+pvData], 0; pvData
0x180026e5c  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180026e65  xor     edx, edx; lpSubKey
0x180026e67  lea     r9d, [rdx+2]; dwFlags
0x180026e6b  mov     rcx, [rcx-18h]; hkey
0x180026e6f  call    cs:__imp_RegGetValueW
0x180026e75  test    eax, eax
0x180026e77  jz      short loc_180026E95
0x180026e79  cmp     eax, 0EAh
0x180026e7e  jz      short loc_180026E95
0x180026e80  mov     ecx, eax; dwErrCode
0x180026e82  call    cs:__imp_SetLastError
0x180026e88  mov     qword ptr [rbx+28h], 0
0x180026e90  jmp     loc_180026F62
0x180026e95  xorps   xmm0, xmm0
0x180026e98  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180026e9c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180026ea4  movdqu  [rbp+57h+var_30], xmm1
0x180026ea9  xor     eax, eax
0x180026eab  mov     word ptr [rbp+57h+Src], ax
0x180026eaf  lea     rax, [rbp+57h+Src]
0x180026eb3  mov     [rbp+57h+var_50], rax
0x180026eb7  mov     [rbp+57h+var_48], 1
0x180026ebb  mov     edx, [rbp+57h+var_60]
0x180026ebe  shr     rdx, 1
0x180026ec1  lea     rcx, [rbp+57h+Src]; Src
0x180026ec5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180026eca  lea     rax, [rbp+57h+Src]
0x180026ece  cmp     qword ptr [rbp+57h+var_30+8], 7
0x180026ed3  cmova   rax, [rbp+57h+Src]
0x180026ed8  cmp     qword ptr [rdi+18h], 7
0x180026edd  jbe     short loc_180026EE2
0x180026edf  mov     rdi, [rdi]
0x180026ee2  lea     rcx, [rbp+57h+var_60]
0x180026ee6  mov     [rsp+0A0h+pcbData], rcx; pcbData
0x180026eeb  mov     [rsp+0A0h+pvData], rax; pvData
0x180026ef0  mov     [rsp+0A0h+pdwType], 0; pdwType
0x180026ef9  mov     r9d, 2; dwFlags
0x180026eff  mov     r8, rdi; lpValue
0x180026f02  xor     edx, edx; lpSubKey
0x180026f04  mov     rcx, [rsi-18h]; hkey
0x180026f08  call    cs:__imp_RegGetValueW
0x180026f0e  mov     edi, eax
0x180026f10  lea     rcx, [rbp+57h+var_50]
0x180026f14  call    ??1?$Buffer@G@Private@@QEAA@XZ; Private::Buffer<ushort>::~Buffer<ushort>(void)
0x180026f19  test    edi, edi
0x180026f1b  jz      short loc_180026F2F
0x180026f1d  mov     ecx, edi; dwErrCode
0x180026f1f  call    cs:__imp_SetLastError
0x180026f25  mov     qword ptr [rbx+28h], 0
0x180026f2d  jmp     short loc_180026F59
0x180026f2f  lea     rcx, [rbx+8]
0x180026f33  movups  xmm0, xmmword ptr [rbp+57h+Src]
0x180026f37  movups  xmmword ptr [rcx], xmm0
0x180026f3a  movups  xmm1, [rbp+57h+var_30]
0x180026f3e  movups  xmmword ptr [rcx+10h], xmm1
0x180026f42  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180026f4a  movdqu  [rbp+57h+var_30], xmm0
0x180026f4f  xor     eax, eax
0x180026f51  mov     word ptr [rbp+57h+Src], ax
0x180026f55  mov     [rbx+28h], rcx
0x180026f59  lea     rcx, [rbp+57h+Src]
0x180026f5d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026f62  mov     rax, rbx
0x180026f65  mov     rcx, [rbp+57h+var_20]
0x180026f69  xor     rcx, rsp; StackCookie
0x180026f6c  call    __security_check_cookie
0x180026f71  mov     rbx, [rsp+0A0h+arg_10]
0x180026f79  add     rsp, 90h
0x180026f80  pop     rdi
0x180026f81  pop     rsi
0x180026f82  pop     rbp
0x180026f83  retn
```
