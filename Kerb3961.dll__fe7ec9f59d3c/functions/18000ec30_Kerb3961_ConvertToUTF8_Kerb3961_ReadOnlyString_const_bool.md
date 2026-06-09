# Kerb3961::ConvertToUTF8(Kerb3961::ReadOnlyString const &,bool)

- ea: `0x18000ec30`
- end: `0x18000ed78`
- name: `?ConvertToUTF8@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyString@1@_N@Z`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180016e60`
- `0x18001c130`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x18000901c`
- `0x18000ec30`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ecae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ed41`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ecae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000ed41`

## pseudocode

```c
__int64 __fastcall Kerb3961::ConvertToUTF8(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  DWORD v5; // ebp
  const char *v6; // rdx
  int cbMultiByte; // r15d
  int v8; // r8d
  int v9; // esi
  LPSTR v10; // rcx
  LPSTR v11; // rdi
  const unsigned __int16 *v12; // rdx
  __int64 v14; // [rsp+40h] [rbp-58h] BYREF
  LPSTR lpMultiByteStr; // [rsp+48h] [rbp-50h]
  char *v16; // [rsp+50h] [rbp-48h]

  if ( *(_QWORD *)a2 <= 0x7FFFFFFFu )
  {
    if ( *(_QWORD *)a2 )
    {
      v5 = (a3 ^ 1) << 7;
      cbMultiByte = WideCharToMultiByte(0xFDE9u, v5, *(LPCWCH *)(a2 + 8), *(_DWORD *)a2, 0, 0, 0, 0);
      if ( cbMultiByte )
      {
        Kerb3961::MakeBuffer(&v14);
        v9 = (int)v16;
        if ( (int)v16 >= 0 )
        {
          v11 = lpMultiByteStr;
          if ( cbMultiByte != WideCharToMultiByte(
                                0xFDE9u,
                                v5,
                                *(LPCWCH *)(a2 + 8),
                                *(_DWORD *)a2,
                                lpMultiByteStr,
                                cbMultiByte,
                                0,
                                0) )
            Kerb3961::ConsistencyFail((Kerb3961 *)L"WideCharToMultiByte yielded different lengths for same data", v12);
          *(_QWORD *)a1 = v14;
          *(_DWORD *)(a1 + 16) = v9;
          *(_QWORD *)(a1 + 8) = v11;
        }
        else
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"result",
            (const char *)(unsigned int)v16,
            v8);
          v10 = lpMultiByteStr;
          *(_QWORD *)a1 = 0;
          *(_QWORD *)(a1 + 8) = 0;
          *(_DWORD *)(a1 + 16) = v9;
          if ( v10 )
            operator delete(v10, 0);
        }
      }
      else
      {
        Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"length != 0", v6);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = -1073740009;
      }
    }
    else
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 0;
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"static_cast<size_t>(string.length) <= static_cast<size_t>(unsigned(utl::numeric_limit"
                                   "s<int32_t>::max()))",
      (const char *)a2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741675;
  }
  return a1;
}

```

## disassembly

```asm
0x18000ec30  push    rbx
0x18000ec32  push    rbp
0x18000ec33  push    rsi
0x18000ec34  push    rdi
0x18000ec35  push    r14
0x18000ec37  push    r15
0x18000ec39  sub     rsp, 68h
0x18000ec3d  cmp     qword ptr [rdx], 7FFFFFFFh
0x18000ec44  mov     r14, rdx
0x18000ec47  mov     rbx, rcx
0x18000ec4a  jbe     short loc_18000EC6D
0x18000ec4c  lea     rcx, aStaticCastSize_5; "static_cast<size_t>(string.length) <= s"...
0x18000ec53  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ec58  xor     edi, edi
0x18000ec5a  mov     [rbx], rdi
0x18000ec5d  mov     [rbx+8], rdi
0x18000ec61  mov     dword ptr [rbx+10h], 0C0000095h
0x18000ec68  jmp     loc_18000ED5B
0x18000ec6d  xor     edi, edi
0x18000ec6f  cmp     [rdx], rdi
0x18000ec72  jnz     short loc_18000EC83
0x18000ec74  mov     [rcx], rdi
0x18000ec77  mov     [rcx+8], rdi
0x18000ec7b  mov     [rcx+10h], edi
0x18000ec7e  jmp     loc_18000ED5B
0x18000ec83  mov     r9d, [rdx]; cchWideChar
0x18000ec86  mov     ecx, 0FDE9h; CodePage
0x18000ec8b  movzx   ebp, r8b
0x18000ec8f  mov     r8, [rdx+8]; lpWideCharStr
0x18000ec93  xor     ebp, 1
0x18000ec96  mov     [rsp+98h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000ec9b  mov     [rsp+98h+lpDefaultChar], rdi; lpDefaultChar
0x18000eca0  shl     ebp, 7
0x18000eca3  mov     edx, ebp; dwFlags
0x18000eca5  mov     [rsp+98h+cbMultiByte], edi; cbMultiByte
0x18000eca9  mov     [rsp+98h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000ecae  call    cs:__imp_WideCharToMultiByte
0x18000ecb4  mov     r15d, eax
0x18000ecb7  test    eax, eax
0x18000ecb9  jnz     short loc_18000ECDA
0x18000ecbb  lea     rcx, aLength0; "length != 0"
0x18000ecc2  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ecc7  mov     [rbx], rdi
0x18000ecca  mov     [rbx+8], rdi
0x18000ecce  mov     dword ptr [rbx+10h], 0C0000717h
0x18000ecd5  jmp     loc_18000ED5B
0x18000ecda  mov     rdx, r15
0x18000ecdd  lea     rcx, [rsp+98h+var_58]
0x18000ece2  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000ece7  mov     esi, dword ptr [rsp+98h+var_48]
0x18000eceb  test    esi, esi
0x18000eced  jns     short loc_18000ED1A
0x18000ecef  mov     edx, esi; char *
0x18000ecf1  lea     rcx, aResult; "result"
0x18000ecf8  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ecfd  mov     rcx, [rsp+98h+var_50]; void *
0x18000ed02  mov     [rbx], rdi
0x18000ed05  mov     [rbx+8], rdi
0x18000ed09  mov     [rbx+10h], esi
0x18000ed0c  test    rcx, rcx
0x18000ed0f  jz      short loc_18000ED5B
0x18000ed11  xor     edx, edx; struct std::nothrow_t *
0x18000ed13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ed18  jmp     short loc_18000ED5B
0x18000ed1a  mov     r9d, [r14]; cchWideChar
0x18000ed1d  mov     edx, ebp; dwFlags
0x18000ed1f  mov     r8, [r14+8]; lpWideCharStr
0x18000ed23  mov     ecx, 0FDE9h; CodePage
0x18000ed28  mov     [rsp+98h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18000ed2d  mov     [rsp+98h+lpDefaultChar], rdi; lpDefaultChar
0x18000ed32  mov     rdi, [rsp+98h+var_50]
0x18000ed37  mov     [rsp+98h+cbMultiByte], r15d; cbMultiByte
0x18000ed3c  mov     [rsp+98h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000ed41  call    cs:__imp_WideCharToMultiByte
0x18000ed47  cmp     r15d, eax
0x18000ed4a  jnz     short loc_18000ED6B
0x18000ed4c  mov     rax, [rsp+98h+var_58]
0x18000ed51  mov     [rbx], rax
0x18000ed54  mov     [rbx+10h], esi
0x18000ed57  mov     [rbx+8], rdi
0x18000ed5b  mov     rax, rbx
0x18000ed5e  add     rsp, 68h
0x18000ed62  pop     r15
0x18000ed64  pop     r14
0x18000ed66  pop     rdi
0x18000ed67  pop     rsi
0x18000ed68  pop     rbp
0x18000ed69  pop     rbx
0x18000ed6a  retn
0x18000ed6b  lea     rcx, aWidechartomult; "WideCharToMultiByte yielded different l"...
0x18000ed72  call    ?ConsistencyFail@Kerb3961@@YAXPEBG@Z; Kerb3961::ConsistencyFail(ushort const *)
```
