# LicenseManagerCore::ContentIdMap<KeyEntry>::find(ContentIdString const &)

- ea: `0x1800360f8`
- end: `0x1800361aa`
- name: `?find@?$ContentIdMap@UKeyEntry@@@LicenseManagerCore@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@UKeyEntry@@@std@@@std@@@std@@@std@@AEBVContentIdString@@@Z`
- size: `178`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035c70`
- `0x18005a410`
- `0x18005fec0`
- `0x180067674`
- `0x1800700c0`
- `0x180074540`
- `0x180095e80`
- `0x180096680`
- `0x180096780`

## callees

- `0x1800360f8`
- `0x180076e64`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036152`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180036152`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18003619c`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18003619c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall LicenseManagerCore::ContentIdMap<KeyEntry>::find(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *i; // rbx
  _QWORD *v7; // rax
  const WCHAR *v8; // rbp
  __int64 v9; // r15
  __int64 v10; // r12
  const WCHAR *v11; // rcx
  int v12; // eax
  _QWORD *v14; // rcx

  for ( i = *(_QWORD **)a1; ; i += 6 )
  {
    v7 = *(_QWORD **)(a1 + 8);
    if ( i == v7 )
    {
      *a2 = v7;
      return a2;
    }
    v8 = a3[3] <= 7u ? (const WCHAR *)a3 : (const WCHAR *)*a3;
    v9 = a3[2];
    v10 = i[2];
    if ( (unsigned __int8)IsCompareContentIdPresent(a1) )
    {
      v14 = i[3] <= 7u ? i : (_QWORD *)*i;
      v12 = CompareContentId(v14, (unsigned int)v10, v8, (unsigned int)v9);
    }
    else
    {
      v11 = i[3] <= 7u ? (const WCHAR *)i : (const WCHAR *)*i;
      v12 = CompareStringOrdinal(v11, v10, v8, v9, 1) - 2;
    }
    if ( !v12 )
      break;
  }
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x1800360f8  push    rbx
0x1800360fa  push    rbp
0x1800360fb  push    rsi
0x1800360fc  push    rdi
0x1800360fd  push    r12
0x1800360ff  push    r14
0x180036101  push    r15
0x180036103  sub     rsp, 30h
0x180036107  mov     rsi, r8
0x18003610a  mov     rdi, rdx
0x18003610d  mov     r14, rcx
0x180036110  mov     rbx, [rcx]
0x180036113  mov     rax, [r14+8]
0x180036117  cmp     rbx, rax
0x18003611a  jz      short loc_180036165
0x18003611c  cmp     qword ptr [rsi+18h], 7
0x180036121  jbe     short loc_18003617A
0x180036123  mov     rbp, [rsi]
0x180036126  mov     r15, [rsi+10h]
0x18003612a  mov     r12, [rbx+10h]
0x18003612e  call    IsCompareContentIdPresent
0x180036133  test    al, al
0x180036135  jnz     short loc_180036189
0x180036137  cmp     qword ptr [rbx+18h], 7
0x18003613c  jbe     short loc_18003617F
0x18003613e  mov     rcx, [rbx]; lpString1
0x180036141  mov     r9d, r15d; cchCount2
0x180036144  mov     edx, r12d; cchCount1
0x180036147  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x18003614f  mov     r8, rbp; lpString2
0x180036152  call    cs:__imp_CompareStringOrdinal
0x180036158  sub     eax, 2
0x18003615b  test    eax, eax
0x18003615d  jz      short loc_180036184
0x18003615f  add     rbx, 30h ; '0'
0x180036163  jmp     short loc_180036113
0x180036165  mov     [rdi], rax
0x180036168  mov     rax, rdi
0x18003616b  add     rsp, 30h
0x18003616f  pop     r15
0x180036171  pop     r14
0x180036173  pop     r12
0x180036175  pop     rdi
0x180036176  pop     rsi
0x180036177  pop     rbp
0x180036178  pop     rbx
0x180036179  retn
0x18003617a  mov     rbp, rsi
0x18003617d  jmp     short loc_180036126
0x18003617f  mov     rcx, rbx
0x180036182  jmp     short loc_180036141
0x180036184  mov     [rdi], rbx
0x180036187  jmp     short loc_180036168
0x180036189  cmp     qword ptr [rbx+18h], 7
0x18003618e  jbe     short loc_1800361A4
0x180036190  mov     rcx, [rbx]
0x180036193  mov     r9d, r15d
0x180036196  mov     edx, r12d
0x180036199  mov     r8, rbp
0x18003619c  call    cs:__imp_CompareContentId
0x1800361a2  jmp     short loc_18003615B
0x1800361a4  mov     rcx, rbx
0x1800361a7  jmp     short loc_180036193
```
