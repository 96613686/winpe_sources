# Microsoft::Resources::EnumeratedScaleQualifierType::ValidateSingleQualifierValue(ushort const *)

- ea: `0x1800790a0`
- end: `0x1800792d8`
- name: `?ValidateSingleQualifierValue@EnumeratedScaleQualifierType@Resources@Microsoft@@MEBAJPEBG@Z`
- size: `568`
- prototype: `int(Microsoft::Resources::EnumeratedScaleQualifierType *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180019570`
- `0x180028ad0`
- `0x180042f70`
- `0x1800790a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800790da`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079103`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007912c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079155`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007917e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800791a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800791d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800790da`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079103`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007912c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180079155`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18007917e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800791a7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800791d0`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::EnumeratedScaleQualifierType::ValidateSingleQualifierValue(
        Microsoft::Resources::EnumeratedScaleQualifierType *this,
        const unsigned __int16 *a2)
{
  const WCHAR *v3; // rcx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax

  if ( (unsigned __int8)DefString_IsEmpty(a2) )
    return 2147957514LL;
  v4 = CompareStringOrdinal(v3, -1, L"500", -1, 1);
  if ( (unsigned int)IntToComparison((unsigned int)(v4 - 2))
    && (v5 = CompareStringOrdinal(a2, -1, L"400", -1, 1), (unsigned int)IntToComparison((unsigned int)(v5 - 2)))
    && (v6 = CompareStringOrdinal(a2, -1, L"300", -1, 1), (unsigned int)IntToComparison((unsigned int)(v6 - 2)))
    && (v7 = CompareStringOrdinal(a2, -1, L"250", -1, 1), (unsigned int)IntToComparison((unsigned int)(v7 - 2)))
    && (v8 = CompareStringOrdinal(a2, -1, L"240", -1, 1), (unsigned int)IntToComparison((unsigned int)(v8 - 2)))
    && (v9 = CompareStringOrdinal(a2, -1, L"225", -1, 1), (unsigned int)IntToComparison((unsigned int)(v9 - 2)))
    && (v10 = CompareStringOrdinal(a2, -1, L"220", -1, 1), (unsigned int)IntToComparison((unsigned int)(v10 - 2)))
    && (unsigned int)DefString_CompareWithOptions(a2, L"200", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"180", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"160", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"150", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"140", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"125", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"120", 1)
    && (unsigned int)DefString_CompareWithOptions(a2, L"100", 1) )
  {
    return (unsigned int)DefString_CompareWithOptions(a2, L"80", 1) != 0 ? 0x80073B0A : 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800790a0  mov     [rsp+arg_0], rbx
0x1800790a5  mov     [rsp+arg_8], rsi
0x1800790aa  push    rdi
0x1800790ab  sub     rsp, 30h
0x1800790af  mov     rcx, rdx
0x1800790b2  mov     rbx, rdx
0x1800790b5  call    DefString_IsEmpty
0x1800790ba  test    al, al
0x1800790bc  jnz     loc_1800792C3
0x1800790c2  or      esi, 0FFFFFFFFh
0x1800790c5  lea     r8, a500; "500"
0x1800790cc  mov     edi, 1
0x1800790d1  mov     r9d, esi; cchCount2
0x1800790d4  mov     edx, esi; cchCount1
0x1800790d6  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x1800790da  call    cs:__imp_CompareStringOrdinal
0x1800790e0  lea     ecx, [rax-2]
0x1800790e3  call    _IntToComparison
0x1800790e8  test    eax, eax
0x1800790ea  jz      loc_1800792BF
0x1800790f0  mov     r9d, esi; cchCount2
0x1800790f3  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x1800790f7  lea     r8, a400; "400"
0x1800790fe  mov     edx, esi; cchCount1
0x180079100  mov     rcx, rbx; lpString1
0x180079103  call    cs:__imp_CompareStringOrdinal
0x180079109  lea     ecx, [rax-2]
0x18007910c  call    _IntToComparison
0x180079111  test    eax, eax
0x180079113  jz      loc_1800792BF
0x180079119  mov     r9d, esi; cchCount2
0x18007911c  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x180079120  lea     r8, a300; "300"
0x180079127  mov     edx, esi; cchCount1
0x180079129  mov     rcx, rbx; lpString1
0x18007912c  call    cs:__imp_CompareStringOrdinal
0x180079132  lea     ecx, [rax-2]
0x180079135  call    _IntToComparison
0x18007913a  test    eax, eax
0x18007913c  jz      loc_1800792BF
0x180079142  mov     r9d, esi; cchCount2
0x180079145  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x180079149  lea     r8, a250; "250"
0x180079150  mov     edx, esi; cchCount1
0x180079152  mov     rcx, rbx; lpString1
0x180079155  call    cs:__imp_CompareStringOrdinal
0x18007915b  lea     ecx, [rax-2]
0x18007915e  call    _IntToComparison
0x180079163  test    eax, eax
0x180079165  jz      loc_1800792BF
0x18007916b  mov     r9d, esi; cchCount2
0x18007916e  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x180079172  lea     r8, a240; "240"
0x180079179  mov     edx, esi; cchCount1
0x18007917b  mov     rcx, rbx; lpString1
0x18007917e  call    cs:__imp_CompareStringOrdinal
0x180079184  lea     ecx, [rax-2]
0x180079187  call    _IntToComparison
0x18007918c  test    eax, eax
0x18007918e  jz      loc_1800792BF
0x180079194  mov     r9d, esi; cchCount2
0x180079197  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18007919b  lea     r8, a225; "225"
0x1800791a2  mov     edx, esi; cchCount1
0x1800791a4  mov     rcx, rbx; lpString1
0x1800791a7  call    cs:__imp_CompareStringOrdinal
0x1800791ad  lea     ecx, [rax-2]
0x1800791b0  call    _IntToComparison
0x1800791b5  test    eax, eax
0x1800791b7  jz      loc_1800792BF
0x1800791bd  mov     r9d, esi; cchCount2
0x1800791c0  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x1800791c4  lea     r8, a220; "220"
0x1800791cb  mov     edx, esi; cchCount1
0x1800791cd  mov     rcx, rbx; lpString1
0x1800791d0  call    cs:__imp_CompareStringOrdinal
0x1800791d6  lea     ecx, [rax-2]
0x1800791d9  call    _IntToComparison
0x1800791de  test    eax, eax
0x1800791e0  jz      loc_1800792BF
0x1800791e6  mov     r8d, edi
0x1800791e9  lea     rdx, a200; "200"
0x1800791f0  mov     rcx, rbx
0x1800791f3  call    DefString_CompareWithOptions
0x1800791f8  test    eax, eax
0x1800791fa  jz      loc_1800792BF
0x180079200  mov     r8d, edi
0x180079203  lea     rdx, a180; "180"
0x18007920a  mov     rcx, rbx
0x18007920d  call    DefString_CompareWithOptions
0x180079212  test    eax, eax
0x180079214  jz      loc_1800792BF
0x18007921a  mov     r8d, edi
0x18007921d  lea     rdx, a160; "160"
0x180079224  mov     rcx, rbx
0x180079227  call    DefString_CompareWithOptions
0x18007922c  test    eax, eax
0x18007922e  jz      loc_1800792BF
0x180079234  mov     r8d, edi
0x180079237  lea     rdx, a150; "150"
0x18007923e  mov     rcx, rbx
0x180079241  call    DefString_CompareWithOptions
0x180079246  test    eax, eax
0x180079248  jz      short loc_1800792BF
0x18007924a  mov     r8d, edi
0x18007924d  lea     rdx, a140; "140"
0x180079254  mov     rcx, rbx
0x180079257  call    DefString_CompareWithOptions
0x18007925c  test    eax, eax
0x18007925e  jz      short loc_1800792BF
0x180079260  mov     r8d, edi
0x180079263  lea     rdx, a125; "125"
0x18007926a  mov     rcx, rbx
0x18007926d  call    DefString_CompareWithOptions
0x180079272  test    eax, eax
0x180079274  jz      short loc_1800792BF
0x180079276  mov     r8d, edi
0x180079279  lea     rdx, a120; "120"
0x180079280  mov     rcx, rbx
0x180079283  call    DefString_CompareWithOptions
0x180079288  test    eax, eax
0x18007928a  jz      short loc_1800792BF
0x18007928c  mov     r8d, edi
0x18007928f  lea     rdx, a100; "100"
0x180079296  mov     rcx, rbx
0x180079299  call    DefString_CompareWithOptions
0x18007929e  test    eax, eax
0x1800792a0  jz      short loc_1800792BF
0x1800792a2  mov     r8d, edi
0x1800792a5  lea     rdx, a80; "80"
0x1800792ac  mov     rcx, rbx
0x1800792af  call    DefString_CompareWithOptions
0x1800792b4  neg     eax
0x1800792b6  sbb     eax, eax
0x1800792b8  and     eax, 80073B0Ah
0x1800792bd  jmp     short loc_1800792C8
0x1800792bf  xor     eax, eax
0x1800792c1  jmp     short loc_1800792C8
0x1800792c3  mov     eax, 80073B0Ah
0x1800792c8  mov     rbx, [rsp+38h+arg_0]
0x1800792cd  mov     rsi, [rsp+38h+arg_8]
0x1800792d2  add     rsp, 30h
0x1800792d6  pop     rdi
0x1800792d7  retn
```
