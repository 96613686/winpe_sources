# RtlConvertWin32RegistryPathToNtRegistryPathWithSid

- ea: `0x1800242a8`
- end: `0x1800243d8`
- name: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001a5b4`

## callees

- `0x18000fafc`
- `0x1800238e8`
- `0x180023b4c`
- `0x1800242a8`

## string_xrefs

- `0x1800242d4`: `onecore\base\lstring\path.cpp`
- `0x180024322`: `onecore\base\lstring\path.cpp`
- `0x180024399`: `onecore\base\lstring\path.cpp`
- `0x1800242f2`: `Not-null check failed: PathIn`
- `0x180024340`: `Not-null check failed: PathOut`
- `0x1800243b7`: `PathOut->Length != 0`
- `0x1800242e7`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x180024335`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`
- `0x1800243ac`: `RtlConvertWin32RegistryPathToNtRegistryPathWithSid`

## pseudocode

```c
__int64 __fastcall RtlConvertWin32RegistryPathToNtRegistryPathWithSid(
        __int64 a1,
        const struct _LUNICODE_STRING *a2,
        const struct _LUNICODE_STRING *a3,
        struct _LUNICODE_STRING *a4)
{
  const char *v6; // rax
  __int64 result; // rax
  __int64 v8; // rdi
  const char *v9; // [rsp+30h] [rbp-20h] BYREF
  const char *v10; // [rsp+38h] [rbp-18h]
  __int64 v11; // [rsp+40h] [rbp-10h]
  const char *v12; // [rsp+48h] [rbp-8h]

  if ( a4 )
    *(_QWORD *)a4 = 0;
  if ( !a3 )
  {
    v11 = 168;
    v9 = "onecore\\base\\lstring\\path.cpp";
    v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
    v6 = "Not-null check failed: PathIn";
LABEL_5:
    v12 = v6;
    RtlReportErrorOrigination(&v9, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a4 )
  {
    v11 = 169;
    v9 = "onecore\\base\\lstring\\path.cpp";
    v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
    v6 = "Not-null check failed: PathOut";
    goto LABEL_5;
  }
  v8 = 0;
  while ( 1 )
  {
    result = off_1800357F0[3 * v8 + 2] == (__int64 (*)[2])-2147483647LL
           ? RtlConvertWin32RegistryPathToNtRegistryPathUser(a1, a2, a3, a4)
           : anonymous_namespace_::TryReplaceUpperCasePrefix(
               0,
               (_DWORD)a3,
               (unsigned int)off_1800357F0[3 * v8],
               (unsigned int)off_1800357F0[3 * v8 + 1],
               (__int64)a4);
    if ( (int)result < 0 )
      return result;
    if ( *(_QWORD *)a4 )
      return 0;
    if ( (unsigned __int64)++v8 >= 9 )
    {
      v11 = 188;
      v9 = "onecore\\base\\lstring\\path.cpp";
      v10 = "RtlConvertWin32RegistryPathToNtRegistryPathWithSid";
      v6 = "PathOut->Length != 0";
      goto LABEL_5;
    }
  }
}

```

## disassembly

```asm
0x1800242a8  mov     [rsp-18h+arg_0], rbx
0x1800242ad  mov     [rsp-18h+arg_8], rsi
0x1800242b2  push    rbp
0x1800242b3  push    rdi
0x1800242b4  push    r14
0x1800242b6  mov     rbp, rsp
0x1800242b9  sub     rsp, 50h
0x1800242bd  mov     rbx, r9
0x1800242c0  mov     rsi, r8
0x1800242c3  test    r9, r9
0x1800242c6  jz      short loc_1800242CF
0x1800242c8  mov     qword ptr [r9], 0
0x1800242cf  test    rsi, rsi
0x1800242d2  jnz     short loc_18002431D
0x1800242d4  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800242db  mov     [rbp+var_10], 0A8h
0x1800242e3  mov     [rbp+var_20], rax
0x1800242e7  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32RegistryPathToNtRegistry"...
0x1800242ee  mov     [rbp+var_18], rax
0x1800242f2  lea     rax, aNotNullCheckFa_3; "Not-null check failed: PathIn"
0x1800242f9  mov     r8d, 0C000000Dh
0x1800242ff  mov     [rbp+var_8], rax
0x180024303  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002430a  lea     rcx, [rbp+var_20]
0x18002430e  call    RtlReportErrorOrigination
0x180024313  mov     eax, 0C000000Dh
0x180024318  jmp     loc_1800243C5
0x18002431d  test    rbx, rbx
0x180024320  jnz     short loc_180024349
0x180024322  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180024329  mov     [rbp+var_10], 0A9h
0x180024331  mov     [rbp+var_20], rax
0x180024335  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32RegistryPathToNtRegistry"...
0x18002433c  mov     [rbp+var_18], rax
0x180024340  lea     rax, aNotNullCheckFa_0; "Not-null check failed: PathOut"
0x180024347  jmp     short loc_1800242F9
0x180024349  xor     edi, edi
0x18002434b  lea     r14, off_1800357F0
0x180024352  lea     r8, [rdi+rdi*2]
0x180024356  cmp     qword ptr [r14+r8*8+10h], 0FFFFFFFF80000001h
0x18002435f  jnz     short loc_18002436E
0x180024361  mov     r9, rbx; struct _LUNICODE_STRING *
0x180024364  mov     r8, rsi; struct _LUNICODE_STRING *
0x180024367  call    ?RtlConvertWin32RegistryPathToNtRegistryPathUser@@YAJKPEBU_LUNICODE_STRING@@0PEAU1@@Z; RtlConvertWin32RegistryPathToNtRegistryPathUser(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING const *,_LUNICODE_STRING *)
0x18002436c  jmp     short loc_180024386
0x18002436e  mov     r9, [r14+r8*8+8]
0x180024373  mov     rdx, rsi
0x180024376  mov     r8, [r14+r8*8]
0x18002437a  xor     ecx, ecx
0x18002437c  mov     [rsp+50h+var_30], rbx
0x180024381  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x180024386  test    eax, eax
0x180024388  js      short loc_1800243C5
0x18002438a  cmp     qword ptr [rbx], 0
0x18002438e  jnz     short loc_1800243C3
0x180024390  inc     rdi
0x180024393  cmp     rdi, 9
0x180024397  jb      short loc_180024352
0x180024399  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800243a0  mov     [rbp+var_10], 0BCh
0x1800243a8  mov     [rbp+var_20], rax
0x1800243ac  lea     rax, aRtlconvertwin3_1; "RtlConvertWin32RegistryPathToNtRegistry"...
0x1800243b3  mov     [rbp+var_18], rax
0x1800243b7  lea     rax, aPathoutLength0; "PathOut->Length != 0"
0x1800243be  jmp     loc_1800242F9
0x1800243c3  xor     eax, eax
0x1800243c5  mov     rbx, [rsp+50h+arg_0]
0x1800243ca  mov     rsi, [rsp+50h+arg_8]
0x1800243cf  add     rsp, 50h
0x1800243d3  pop     r14
0x1800243d5  pop     rdi
0x1800243d6  pop     rbp
0x1800243d7  retn
```
