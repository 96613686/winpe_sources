# RunCommandsSections(ushort const *,ushort const *,ushort const *,ushort const *,ulong,int)

- ea: `0x18000a0c0`
- end: `0x18000a244`
- name: `?RunCommandsSections@@YAJPEBG000KH@Z`
- size: `388`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x180006af8`
- `0x180007454`
- `0x180009c14`
- `0x18000a0c0`
- `0x18001b980`

## import_xrefs

- `msvcrt!_wtol` at `0x18000a19e`
- `msvcrt!_wtol` at `0x18000a19e`
- `USER32!CharNextW` at `0x18000a182`
- `USER32!CharNextW` at `0x18000a182`
- `USER32!CharPrevW` at `0x18000a191`
- `USER32!CharPrevW` at `0x18000a191`
- `KERNEL32!CompareStringW` at `0x18000a1d2`
- `KERNEL32!CompareStringW` at `0x18000a1d2`
- `SHLWAPI!StrChrW` at `0x18000a16e`
- `SHLWAPI!StrChrW` at `0x18000a16e`

## string_xrefs

- `0x18000a1b6`: `RunPostSetupCommands`

## pseudocode

```c
__int64 __fastcall RunCommandsSections(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int16 a5,
        int a6)
{
  unsigned int v9; // ebx
  unsigned __int16 *StringField; // rdi
  char v11; // bl
  const WCHAR *v12; // rax
  const WCHAR *v13; // rbx
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v16[256]; // [rsp+40h] [rbp-258h] BYREF

  v16[0] = 0;
  v15[0] = v16;
  if ( (int)GetTranslatedString(lpFileName, a2, a3, v16, 0x100u, 0) < 0 )
    v16[0] = 0;
  v9 = 0;
  StringField = GetStringField(v15, L",", 34, 1);
  do
  {
    if ( !StringField || !*StringField )
      break;
    v11 = 0;
    v12 = StrChrW(StringField, 0x3Au);
    if ( v12 && *v12 == 58 )
    {
      v13 = CharNextW(v12);
      *CharPrevW(StringField, v13) = 0;
      v11 = _wtol(v13);
    }
    if ( (a5 & 0x400) != 0 && CompareStringW(0x7Fu, 1u, a3, -1, L"RunPostSetupCommands", -1) == 2 )
      v11 |= 4u;
    v9 = RunCommands(lpFileName, StringField, a4, v11, a6);
    StringField = GetStringField(v15, L",", 34, 1);
  }
  while ( !v9 );
  return v9;
}

```

## disassembly

```asm
0x18000a0c0  push    rbx
0x18000a0c2  push    rbp
0x18000a0c3  push    rsi
0x18000a0c4  push    rdi
0x18000a0c5  push    r12
0x18000a0c7  push    r13
0x18000a0c9  push    r14
0x18000a0cb  push    r15
0x18000a0cd  sub     rsp, 258h
0x18000a0d4  mov     rax, cs:__security_cookie
0x18000a0db  xor     rax, rsp
0x18000a0de  mov     [rsp+298h+var_58], rax
0x18000a0e6  xor     r12d, r12d
0x18000a0e9  lea     rax, [rsp+298h+var_258]
0x18000a0ee  mov     r15, r9
0x18000a0f1  mov     qword ptr [rsp+298h+cchCount2], r12; unsigned int *
0x18000a0f6  lea     r9, [rsp+298h+var_258]; unsigned __int16 *
0x18000a0fb  mov     dword ptr [rsp+298h+lpString2], 100h; unsigned int
0x18000a103  mov     rsi, r8
0x18000a106  mov     [rsp+298h+var_258], r12w
0x18000a10c  mov     rbp, rcx
0x18000a10f  mov     [rsp+298h+var_268], rax
0x18000a114  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000a119  test    eax, eax
0x18000a11b  jns     short loc_18000A123
0x18000a11d  mov     [rsp+298h+var_258], r12w
0x18000a123  mov     r8d, 22h ; '"'; unsigned __int16
0x18000a129  lea     rdx, asc_18001E134; ","
0x18000a130  lea     rcx, [rsp+298h+var_268]; unsigned __int16 **
0x18000a135  mov     ebx, r12d
0x18000a138  lea     r9d, [r8-21h]; int
0x18000a13c  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000a141  mov     r14d, [rsp+298h+arg_28]
0x18000a149  mov     rdi, rax
0x18000a14c  mov     r13d, 3Ah ; ':'
0x18000a152  test    rdi, rdi
0x18000a155  jz      loc_18000A21E
0x18000a15b  cmp     [rdi], r12w
0x18000a15f  jz      loc_18000A21E
0x18000a165  mov     edx, r13d; wMatch
0x18000a168  mov     rcx, rdi; pszStart
0x18000a16b  mov     ebx, r12d
0x18000a16e  call    cs:__imp_StrChrW
0x18000a174  test    rax, rax
0x18000a177  jz      short loc_18000A1A6
0x18000a179  cmp     [rax], r13w
0x18000a17d  jnz     short loc_18000A1A6
0x18000a17f  mov     rcx, rax; lpsz
0x18000a182  call    cs:__imp_CharNextW
0x18000a188  mov     rdx, rax; lpszCurrent
0x18000a18b  mov     rcx, rdi; lpszStart
0x18000a18e  mov     rbx, rax
0x18000a191  call    cs:__imp_CharPrevW
0x18000a197  mov     rcx, rbx; String
0x18000a19a  mov     [rax], r12w
0x18000a19e  call    cs:__imp__wtol
0x18000a1a4  mov     ebx, eax
0x18000a1a6  test    dword ptr [rsp+298h+arg_20], 400h
0x18000a1b1  jz      short loc_18000A1E0
0x18000a1b3  or      ecx, 0FFFFFFFFh
0x18000a1b6  lea     rax, aRunpostsetupco; "RunPostSetupCommands"
0x18000a1bd  mov     [rsp+298h+cchCount2], ecx; cchCount2
0x18000a1c1  mov     r9d, ecx; cchCount1
0x18000a1c4  mov     r8, rsi; lpString1
0x18000a1c7  mov     [rsp+298h+lpString2], rax; lpString2
0x18000a1cc  lea     edx, [rcx+2]; dwCmpFlags
0x18000a1cf  lea     ecx, [rdx+7Eh]; Locale
0x18000a1d2  call    cs:__imp_CompareStringW
0x18000a1d8  cmp     eax, 2
0x18000a1db  jnz     short loc_18000A1E0
0x18000a1dd  or      ebx, 4
0x18000a1e0  mov     r9d, ebx; unsigned int
0x18000a1e3  mov     dword ptr [rsp+298h+lpString2], r14d; int
0x18000a1e8  mov     r8, r15; unsigned __int16 *
0x18000a1eb  mov     rdx, rdi; lpAppName
0x18000a1ee  mov     rcx, rbp; lpFileName
0x18000a1f1  call    ?RunCommands@@YAJPEBG00KH@Z; RunCommands(ushort const *,ushort const *,ushort const *,ulong,int)
0x18000a1f6  mov     r8d, 22h ; '"'; unsigned __int16
0x18000a1fc  lea     rdx, asc_18001E134; ","
0x18000a203  lea     rcx, [rsp+298h+var_268]; unsigned __int16 **
0x18000a208  mov     ebx, eax
0x18000a20a  lea     r9d, [r8-21h]; int
0x18000a20e  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000a213  mov     rdi, rax
0x18000a216  test    ebx, ebx
0x18000a218  jz      loc_18000A152
0x18000a21e  mov     eax, ebx
0x18000a220  mov     rcx, [rsp+298h+var_58]
0x18000a228  xor     rcx, rsp; StackCookie
0x18000a22b  call    __security_check_cookie
0x18000a230  add     rsp, 258h
0x18000a237  pop     r15
0x18000a239  pop     r14
0x18000a23b  pop     r13
0x18000a23d  pop     r12
0x18000a23f  pop     rdi
0x18000a240  pop     rsi
0x18000a241  pop     rbp
0x18000a242  pop     rbx
0x18000a243  retn
```
