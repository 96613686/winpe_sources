# Windows::StringUtil::Rtl::ConvertNtRegistryPathToNullTerminatedWin32RegistryPath<_LUNICODE_STRING>(_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x180011890`
- end: `0x180011952`
- name: `??$ConvertNtRegistryPathToNullTerminatedWin32RegistryPath@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int128 *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800177f8`

## callees

- `0x18000fafc`
- `0x180011890`
- `0x180023b4c`

## string_xrefs

- `0x1800118f8`: `onecore\base\lstring\path.cpp`
- `0x180011914`: `RtlConvertNtRegistryPathToWin32RegistryPath`

## pseudocode

```c
__int64 __fastcall Windows::StringUtil::Rtl::ConvertNtRegistryPathToNullTerminatedWin32RegistryPath<_LUNICODE_STRING>(
        __int128 *a1,
        _QWORD *a2)
{
  __int64 v3; // xmm1_8
  __int64 v4; // rbx
  __int64 result; // rax
  __int128 v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]
  __int64 v8; // [rsp+48h] [rbp-10h]

  v3 = *((_QWORD *)a1 + 2);
  v4 = 0;
  v6 = *a1;
  *a2 = 0;
  v7 = v3;
  while ( 1 )
  {
    LOBYTE(a1) = 1;
    result = anonymous_namespace_::TryReplaceUpperCasePrefix(
               (_DWORD)a1,
               (unsigned int)&v6,
               (unsigned int)off_1800358D0[2 * v4],
               (unsigned int)off_1800358D0[2 * v4 + 1],
               (__int64)a2);
    if ( (int)result < 0 )
      break;
    if ( *a2 )
      return 0;
    if ( (unsigned __int64)++v4 >= 4 )
    {
      v7 = 439;
      *(_QWORD *)&v6 = "onecore\\base\\lstring\\path.cpp";
      v8 = 0;
      *((_QWORD *)&v6 + 1) = "RtlConvertNtRegistryPathToWin32RegistryPath";
      RtlReportErrorOrigination(&v6, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225529LL);
      return 3221225529LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011890  mov     rax, rsp
0x180011893  mov     [rax+18h], rbx
0x180011897  mov     [rax+20h], rbp
0x18001189b  push    rdi
0x18001189c  sub     rsp, 50h
0x1800118a0  movups  xmm0, xmmword ptr [rcx]
0x1800118a3  lea     rbp, off_1800358D0
0x1800118aa  mov     rdi, rdx
0x1800118ad  movsd   xmm1, qword ptr [rcx+10h]
0x1800118b2  xor     ebx, ebx
0x1800118b4  movups  xmmword ptr [rax-28h], xmm0
0x1800118b8  mov     qword ptr [rdx], 0
0x1800118bf  movsd   qword ptr [rax-18h], xmm1
0x1800118c4  mov     r8, rbx
0x1800118c7  mov     [rsp+58h+var_38], rdi
0x1800118cc  add     r8, r8
0x1800118cf  lea     rdx, [rsp+58h+var_28]
0x1800118d4  mov     cl, 1
0x1800118d6  mov     r9, [rbp+r8*8+8]
0x1800118db  mov     r8, [rbp+r8*8+0]
0x1800118e0  call    _anonymous_namespace___TryReplaceUpperCasePrefix
0x1800118e5  test    eax, eax
0x1800118e7  js      short loc_180011942
0x1800118e9  cmp     qword ptr [rdi], 0
0x1800118ed  jnz     short loc_180011940
0x1800118ef  inc     rbx
0x1800118f2  cmp     rbx, 4
0x1800118f6  jb      short loc_1800118C4
0x1800118f8  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800118ff  mov     [rsp+58h+var_18], 1B7h
0x180011908  mov     [rsp+58h+var_28], rax
0x18001190d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180011914  lea     rax, aRtlconvertntre; "RtlConvertNtRegistryPathToWin32Registry"...
0x18001191b  mov     [rsp+58h+var_10], 0
0x180011924  mov     r8d, 0C0000039h
0x18001192a  mov     [rsp+58h+var_20], rax
0x18001192f  lea     rcx, [rsp+58h+var_28]
0x180011934  call    RtlReportErrorOrigination
0x180011939  mov     eax, 0C0000039h
0x18001193e  jmp     short loc_180011942
0x180011940  xor     eax, eax
0x180011942  mov     rbx, [rsp+58h+arg_10]
0x180011947  mov     rbp, [rsp+58h+arg_18]
0x18001194c  add     rsp, 50h
0x180011950  pop     rdi
0x180011951  retn
```
