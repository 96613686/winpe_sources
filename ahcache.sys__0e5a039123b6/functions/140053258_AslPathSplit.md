# AslPathSplit

- ea: `0x140053258`
- end: `0x140053444`
- name: `AslPathSplit`
- size: `492`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PWSTR, int, NTSTRSAFE_PWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140039624`

## callees

- `0x1400012f0`
- `0x140001848`
- `0x1400043eb`
- `0x1400079f0`
- `0x14003e364`
- `0x140053258`

## string_xrefs

- `0x1400533f7`: `RtlStringCchCopyW failed [%x]`
- `0x14005340a`: `RtlStringCchCopyW failed [%x]`
- `0x140053435`: `RtlStringCchCopyW failed [%x]`
- `0x1400533dc`: `AslPathSplit`
- `0x1400533d1`: `RtlStringCchCopyNW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslPathSplit(
        STRSAFE_PCNZWCH pszSrc,
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        NTSTRSAFE_PWSTR a4,
        int a5,
        NTSTRSAFE_PWSTR pszDesta)
{
  unsigned int v8; // ebp
  wchar_t *v10; // rax
  STRSAFE_PCNZWCH v11; // rdi
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  _WORD *v14; // rcx
  wchar_t *v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  wchar_t *v19; // rax
  const wchar_t *v20; // rbp
  size_t v21; // rdi
  __int64 v23; // r8
  const char *v24; // r9
  wchar_t Str[264]; // [rsp+30h] [rbp-258h] BYREF

  *pszDest = 0;
  v8 = cchDest;
  Str[0] = 0;
  *pszDesta = 0;
  *a4 = 0;
  v10 = wcsrchr_0(pszSrc, 0x5Cu);
  v11 = v10;
  if ( v10 )
  {
    v12 = RtlStringCchCopyNW(pszDest, v8, pszSrc, v10 - pszSrc + 1);
    v13 = v12;
    if ( v12 < 0 )
    {
      v23 = 1231;
LABEL_17:
      v24 = "RtlStringCchCopyNW failed [%x]";
      goto LABEL_18;
    }
  }
  else
  {
    v11 = pszSrc;
  }
  v14 = v11 + 1;
  v15 = Str;
  v16 = 2147483646;
  v17 = 261;
  if ( *v11 != 92 )
    v14 = v11;
  do
  {
    if ( !v16 )
      break;
    if ( !*v14 )
      break;
    *v15++ = *v14++;
    --v16;
    --v17;
  }
  while ( v17 );
  v18 = v15 - 1;
  v13 = v17 == 0 ? 0x80000005 : 0;
  if ( v17 )
    v18 = v15;
  *v18 = 0;
  if ( !v17 )
  {
    AslLogCallPrintf(1, "AslPathSplit", 1251, "RtlStringCchCopyW failed [%x]", -2147483643);
    return v13;
  }
  v19 = wcsrchr_0(Str, 0x2Eu);
  v20 = v19;
  if ( !v19 )
  {
    v12 = RtlStringCchCopyW(a4, 0x104u, Str);
    v13 = v12;
    if ( v12 >= 0 )
      return 0;
    v24 = "RtlStringCchCopyW failed [%x]";
    v23 = 1278;
LABEL_18:
    AslLogCallPrintf(1, "AslPathSplit", v23, v24, v12);
    return v13;
  }
  v21 = v19 - Str;
  v12 = RtlStringCchCopyNW(a4, 0x104u, Str, v21);
  v13 = v12;
  if ( v12 < 0 )
  {
    v23 = 1264;
    goto LABEL_17;
  }
  a4[v21] = 0;
  v12 = RtlStringCchCopyW(pszDesta, 0x104u, v20);
  v13 = v12;
  if ( v12 < 0 )
  {
    v24 = "RtlStringCchCopyW failed [%x]";
    v23 = 1271;
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x140053258  push    rbx
0x14005325a  push    rbp
0x14005325b  push    rsi
0x14005325c  push    rdi
0x14005325d  push    r12
0x14005325f  push    r14
0x140053261  push    r15
0x140053263  sub     rsp, 250h
0x14005326a  mov     rax, cs:__security_cookie
0x140053271  xor     rax, rsp
0x140053274  mov     [rsp+288h+var_48], rax
0x14005327c  mov     r15, [rsp+288h+pszDest]
0x140053284  xor     r12d, r12d
0x140053287  mov     [rdx], r12w
0x14005328b  mov     rsi, rdx
0x14005328e  mov     r14, r9
0x140053291  mov     ebp, r8d
0x140053294  mov     rbx, rcx
0x140053297  mov     [rsp+288h+Str], r12w
0x14005329d  mov     [r15], r12w
0x1400532a1  lea     edx, [r12+5Ch]; Ch
0x1400532a6  mov     [r9], r12w
0x1400532aa  call    wcsrchr_0
0x1400532af  mov     rdi, rax
0x1400532b2  test    rax, rax
0x1400532b5  jz      loc_140053419
0x1400532bb  mov     r9, rax
0x1400532be  mov     edx, ebp; cchDest
0x1400532c0  sub     r9, rbx
0x1400532c3  mov     r8, rbx; pszSrc
0x1400532c6  sar     r9, 1
0x1400532c9  mov     rcx, rsi; pszDest
0x1400532cc  inc     r9; cchToCopy
0x1400532cf  call    RtlStringCchCopyNW
0x1400532d4  mov     ebx, eax
0x1400532d6  test    eax, eax
0x1400532d8  js      loc_1400533CB
0x1400532de  mov     edx, 5Ch ; '\'
0x1400532e3  lea     rcx, [rdi+2]
0x1400532e7  cmp     [rdi], dx
0x1400532ea  lea     r8, [rsp+288h+Str]
0x1400532ef  mov     r9d, 7FFFFFFEh
0x1400532f5  mov     edx, 105h
0x1400532fa  cmovnz  rcx, rdi
0x1400532fe  test    r9, r9
0x140053301  jz      short loc_140053320
0x140053303  movzx   eax, word ptr [rcx]
0x140053306  test    ax, ax
0x140053309  jz      short loc_140053320
0x14005330b  mov     [r8], ax
0x14005330f  add     rcx, 2
0x140053313  add     r8, 2
0x140053317  dec     r9
0x14005331a  sub     rdx, 1
0x14005331e  jnz     short loc_1400532FE
0x140053320  mov     rax, rdx
0x140053323  lea     rcx, [r8-2]
0x140053327  neg     rax
0x14005332a  sbb     ebx, ebx
0x14005332c  not     ebx
0x14005332e  and     ebx, 80000005h
0x140053334  test    rdx, rdx
0x140053337  cmovnz  rcx, r8
0x14005333b  mov     [rcx], r12w
0x14005333f  jz      loc_140053406
0x140053345  mov     edx, 2Eh ; '.'; Ch
0x14005334a  lea     rcx, [rsp+288h+Str]; Str
0x14005334f  call    wcsrchr_0
0x140053354  lea     r8, [rsp+288h+Str]; pszSrc
0x140053359  mov     rbp, rax
0x14005335c  mov     rcx, r14; pszDest
0x14005335f  test    rax, rax
0x140053362  jz      loc_140053421
0x140053368  lea     rax, [rsp+288h+Str]
0x14005336d  mov     rdi, rbp
0x140053370  sub     rdi, rax
0x140053373  mov     esi, 104h
0x140053378  sar     rdi, 1
0x14005337b  mov     edx, esi; cchDest
0x14005337d  mov     r9, rdi; cchToCopy
0x140053380  call    RtlStringCchCopyNW
0x140053385  mov     ebx, eax
0x140053387  test    eax, eax
0x140053389  js      short loc_1400533EF
0x14005338b  mov     r8, rbp; pszSrc
0x14005338e  mov     [r14+rdi*2], r12w
0x140053393  mov     edx, esi; cchDest
0x140053395  mov     rcx, r15; pszDest
0x140053398  call    RtlStringCchCopyW
0x14005339d  mov     ebx, eax
0x14005339f  test    eax, eax
0x1400533a1  js      short loc_1400533F7
0x1400533a3  mov     ebx, r12d
0x1400533a6  mov     eax, ebx
0x1400533a8  mov     rcx, [rsp+288h+var_48]
0x1400533b0  xor     rcx, rsp; StackCookie
0x1400533b3  call    __security_check_cookie
0x1400533b8  add     rsp, 250h
0x1400533bf  pop     r15
0x1400533c1  pop     r14
0x1400533c3  pop     r12
0x1400533c5  pop     rdi
0x1400533c6  pop     rsi
0x1400533c7  pop     rbp
0x1400533c8  pop     rbx
0x1400533c9  retn
0x1400533cb  mov     r8d, 4CFh
0x1400533d1  lea     r9, aRtlstringcchco_2; "RtlStringCchCopyNW failed [%x]"
0x1400533d8  mov     [rsp+288h+var_268], eax
0x1400533dc  lea     rdx, aAslpathsplit; "AslPathSplit"
0x1400533e3  mov     ecx, 1
0x1400533e8  call    AslLogCallPrintf
0x1400533ed  jmp     short loc_1400533A6
0x1400533ef  mov     r8d, 4F0h
0x1400533f5  jmp     short loc_1400533D1
0x1400533f7  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x1400533fe  mov     r8d, 4F7h
0x140053404  jmp     short loc_1400533D8
0x140053406  mov     [rsp+288h+var_268], ebx
0x14005340a  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140053411  mov     r8d, 4E3h
0x140053417  jmp     short loc_1400533DC
0x140053419  mov     rdi, rbx
0x14005341c  jmp     loc_1400532DE
0x140053421  mov     edx, 104h; cchDest
0x140053426  call    RtlStringCchCopyW
0x14005342b  mov     ebx, eax
0x14005342d  test    eax, eax
0x14005342f  jns     loc_1400533A3
0x140053435  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14005343c  mov     r8d, 4FEh
0x140053442  jmp     short loc_1400533D8
```
