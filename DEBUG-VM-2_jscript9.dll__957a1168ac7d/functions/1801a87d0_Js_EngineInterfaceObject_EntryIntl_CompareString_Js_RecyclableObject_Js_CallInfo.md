# Js::EngineInterfaceObject::EntryIntl_CompareString(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1801a87d0`
- end: `0x1801a8a6a`
- name: `?EntryIntl_CompareString@EngineInterfaceObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1802bad90`

## callees

- `0x1800429ec`
- `0x18005e9d0`
- `0x1800dea90`
- `0x1801a87d0`
- `0x1801a8a70`
- `0x18030eeac`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `KERNEL32!CompareStringEx` at `0x1801a8a05`
- `KERNEL32!CompareStringEx` at `0x1801a8a05`
- `KERNEL32!GetUserDefaultLocaleName` at `0x1801a8976`
- `KERNEL32!GetUserDefaultLocaleName` at `0x1801a8976`
- `KERNEL32!GetLastError` at `0x1801a8980`
- `KERNEL32!GetLastError` at `0x1801a8a21`
- `KERNEL32!GetLastError` at `0x1801a8980`
- `KERNEL32!GetLastError` at `0x1801a8a21`

## pseudocode

```c
__int64 __fastcall Js::EngineInterfaceObject::EntryIntl_CompareString(
        __int64 a1,
        int a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        void *a6,
        void *a7,
        __int64 a8,
        __int64 a9)
{
  ThreadContext **v10; // r8
  struct Js::ScriptContext *v11; // r14
  __int64 v12; // r15
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v16; // rdx
  Js *v17; // rax
  const unsigned __int16 *v18; // rdx
  DWORD FlagsForSensitivity; // ebp
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  signed int LastError; // eax
  int cchCount2; // esi
  const WCHAR *lpString2; // rbx
  int v26; // edi
  const WCHAR *v27; // rax
  WCHAR *v28; // rcx
  int v29; // eax
  signed int v30; // eax
  WCHAR LocaleName[88]; // [rsp+60h] [rbp-F8h] BYREF

  v10 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  ThreadContext::ProbeStack(v10[148], 0x450u, (struct Js::ScriptContext *)v10, 0);
  v11 = *(struct Js::ScriptContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  if ( (a2 & 0xFFFFFFu) < 7 || !Js::JavascriptString::Is(a4) || !Js::JavascriptString::Is(a5) )
    return *(_QWORD *)(*(_QWORD *)v11 + 1056LL);
  v12 = 0;
  LocaleName[0] = 0;
  if ( a6 != *(void **)(*(_QWORD *)v11 + 1056LL) )
  {
    if ( !Js::JavascriptString::Is(a6) )
      return v14;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 704LL))(v13);
  }
  if ( a7 == *(void **)(*(_QWORD *)v11 + 1056LL) )
  {
    FlagsForSensitivity = 0x8000000;
  }
  else
  {
    if ( !Js::JavascriptString::Is(a7) )
      return v14;
    v17 = (Js *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 704LL))(v16);
    FlagsForSensitivity = Js::getFlagsForSensitivity(v17, v18);
  }
  v20 = *(_QWORD *)(*(_QWORD *)v11 + 1056LL);
  if ( a8 != v20 )
  {
    if ( (unsigned int)Js::JavascriptOperators::GetTypeId(a8) != 2 )
      return v20;
    if ( *(_BYTE *)(v21 + 16) )
      FlagsForSensitivity |= 4u;
  }
  if ( a9 != v20 )
  {
    if ( (unsigned int)Js::JavascriptOperators::GetTypeId(a9) != 2 )
      return v20;
    if ( *(_BYTE *)(v22 + 16) )
      FlagsForSensitivity |= 8u;
  }
  if ( !v12 && !GetUserDefaultLocaleName(LocaleName, 85) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Js::JavascriptError::MapAndThrowError(v11, LastError);
  }
  cchCount2 = a5[4];
  lpString2 = (const WCHAR *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a5 + 704LL))(a5);
  v26 = a4[4];
  v27 = (const WCHAR *)(*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a4 + 704LL))(a4);
  v28 = LocaleName;
  if ( v12 )
    v28 = (WCHAR *)v12;
  v29 = CompareStringEx(v28, FlagsForSensitivity, v27, v26, lpString2, cchCount2, 0, 0, 0);
  if ( !v29 )
  {
    v30 = GetLastError();
    if ( v30 > 0 )
      v30 = (unsigned __int16)v30 | 0x80070000;
    Js::JavascriptError::MapAndThrowError(v11, v30);
  }
  return (unsigned int)(v29 - 2) | 0x1000000000000LL;
}

```

## disassembly

```asm
0x1801a87d0  mov     r11, rsp
0x1801a87d3  mov     [r11+10h], rdx
0x1801a87d7  mov     [r11+8], rcx
0x1801a87db  mov     [r11+18h], r8
0x1801a87df  mov     [r11+20h], r9
0x1801a87e3  push    rbx
0x1801a87e4  push    rbp
0x1801a87e5  push    rsi
0x1801a87e6  push    rdi
0x1801a87e7  push    r12
0x1801a87e9  push    r14
0x1801a87eb  push    r15
0x1801a87ed  sub     rsp, 120h
0x1801a87f4  mov     rax, cs:__security_cookie
0x1801a87fb  xor     rax, rsp
0x1801a87fe  mov     [rsp+158h+var_48], rax
0x1801a8806  mov     rbx, [r11+8]
0x1801a880a  xor     r9d, r9d; void *
0x1801a880d  mov     edx, 450h; unsigned __int64
0x1801a8812  mov     rax, [rbx+8]
0x1801a8816  mov     rcx, [rax+8]
0x1801a881a  mov     rcx, [rcx+430h]
0x1801a8821  mov     r8, rcx; struct Js::ScriptContext *
0x1801a8824  mov     rcx, [rcx+4A0h]; this
0x1801a882b  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1801a8830  mov     rax, [rbx+8]
0x1801a8834  lea     rdi, [rsp+158h+arg_10]
0x1801a883c  mov     edx, [rsp+158h+arg_8]
0x1801a8843  and     edx, 0FFFFFFh
0x1801a8849  mov     [rsp+158h+var_108], 0
0x1801a8852  mov     rcx, [rax+8]
0x1801a8856  mov     r14, [rcx+430h]
0x1801a885d  cmp     edx, 7
0x1801a8860  jb      loc_1801A8A3E
0x1801a8866  mov     r12, [rdi+8]
0x1801a886a  mov     rcx, r12; void *
0x1801a886d  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801a8872  test    al, al
0x1801a8874  jz      loc_1801A8A3E
0x1801a887a  mov     rbx, [rdi+10h]
0x1801a887e  mov     rcx, rbx; void *
0x1801a8881  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801a8886  test    al, al
0x1801a8888  jz      loc_1801A8A3E
0x1801a888e  xor     eax, eax
0x1801a8890  xor     r15d, r15d
0x1801a8893  mov     [rsp+158h+LocaleName], ax
0x1801a8898  mov     rax, [r14]
0x1801a889b  mov     rdx, [rdi+18h]
0x1801a889f  mov     r8, [rax+420h]
0x1801a88a6  cmp     rdx, r8
0x1801a88a9  jz      short loc_1801A88D4
0x1801a88ab  mov     rcx, rdx; void *
0x1801a88ae  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801a88b3  test    al, al
0x1801a88b5  jnz     short loc_1801A88BF
0x1801a88b7  mov     rax, r8
0x1801a88ba  jmp     loc_1801A8A48
0x1801a88bf  mov     rax, [rdx]
0x1801a88c2  mov     rcx, rdx
0x1801a88c5  mov     rax, [rax+2C0h]
0x1801a88cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a88d1  mov     r15, rax
0x1801a88d4  mov     rcx, [r14]
0x1801a88d7  mov     rdx, [rdi+20h]
0x1801a88db  mov     r8, [rcx+420h]
0x1801a88e2  cmp     rdx, r8
0x1801a88e5  jz      short loc_1801A8911
0x1801a88e7  mov     rcx, rdx; void *
0x1801a88ea  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801a88ef  test    al, al
0x1801a88f1  jz      short loc_1801A88B7
0x1801a88f3  mov     rax, [rdx]
0x1801a88f6  mov     rcx, rdx
0x1801a88f9  mov     rax, [rax+2C0h]
0x1801a8900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8905  mov     rcx, rax; this
0x1801a8908  call    ?getFlagsForSensitivity@Js@@YAKPEBG@Z; Js::getFlagsForSensitivity(ushort const *)
0x1801a890d  mov     ebp, eax
0x1801a890f  jmp     short loc_1801A8916
0x1801a8911  mov     ebp, 8000000h
0x1801a8916  mov     rax, [r14]
0x1801a8919  mov     r8, [rdi+28h]
0x1801a891d  mov     rdx, [rax+420h]
0x1801a8924  cmp     r8, rdx
0x1801a8927  jz      short loc_1801A8940
0x1801a8929  mov     rcx, r8
0x1801a892c  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801a8931  cmp     eax, 2
0x1801a8934  jnz     short loc_1801A8956
0x1801a8936  cmp     byte ptr [r8+10h], 0
0x1801a893b  jz      short loc_1801A8940
0x1801a893d  or      ebp, 4
0x1801a8940  mov     r8, [rdi+30h]
0x1801a8944  cmp     r8, rdx
0x1801a8947  jz      short loc_1801A8968
0x1801a8949  mov     rcx, r8
0x1801a894c  call    ?GetTypeId@JavascriptOperators@Js@@SA?AW4TypeId@2@PEAX@Z; Js::JavascriptOperators::GetTypeId(void *)
0x1801a8951  cmp     eax, 2
0x1801a8954  jz      short loc_1801A895E
0x1801a8956  mov     rax, rdx
0x1801a8959  jmp     loc_1801A8A48
0x1801a895e  cmp     byte ptr [r8+10h], 0
0x1801a8963  jz      short loc_1801A8968
0x1801a8965  or      ebp, 8
0x1801a8968  test    r15, r15
0x1801a896b  jnz     short loc_1801A899D
0x1801a896d  lea     edx, [r15+55h]; cchLocaleName
0x1801a8971  lea     rcx, [rsp+158h+LocaleName]; lpLocaleName
0x1801a8976  call    cs:__imp_GetUserDefaultLocaleName
0x1801a897c  test    eax, eax
0x1801a897e  jnz     short loc_1801A899D
0x1801a8980  call    cs:__imp_GetLastError
0x1801a8986  test    eax, eax
0x1801a8988  jle     short loc_1801A8992
0x1801a898a  movzx   eax, ax
0x1801a898d  or      eax, 80070000h
0x1801a8992  mov     edx, eax; int
0x1801a8994  mov     rcx, r14; struct Js::ScriptContext *
0x1801a8997  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x1801a899d  mov     rax, [rbx]
0x1801a89a0  mov     rcx, rbx
0x1801a89a3  mov     esi, [rbx+10h]
0x1801a89a6  mov     rax, [rax+2C0h]
0x1801a89ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a89b2  mov     rdx, [r12]
0x1801a89b6  mov     rbx, rax
0x1801a89b9  mov     edi, [r12+10h]
0x1801a89be  mov     rcx, r12
0x1801a89c1  mov     rax, [rdx+2C0h]
0x1801a89c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a89cd  mov     [rsp+158h+lParam], 0; lParam
0x1801a89d6  lea     rcx, [rsp+158h+LocaleName]
0x1801a89db  mov     [rsp+158h+lpReserved], 0; lpReserved
0x1801a89e4  test    r15, r15
0x1801a89e7  mov     [rsp+158h+lpVersionInformation], 0; lpVersionInformation
0x1801a89f0  mov     r9d, edi; cchCount1
0x1801a89f3  cmovnz  rcx, r15; lpLocaleName
0x1801a89f7  mov     [rsp+158h+cchCount2], esi; cchCount2
0x1801a89fb  mov     r8, rax; lpString1
0x1801a89fe  mov     [rsp+158h+lpString2], rbx; lpString2
0x1801a8a03  mov     edx, ebp; dwCmpFlags
0x1801a8a05  call    cs:__imp_CompareStringEx
0x1801a8a0b  test    eax, eax
0x1801a8a0d  jz      short loc_1801A8A21
0x1801a8a0f  add     eax, 0FFFFFFFEh
0x1801a8a12  mov     rcx, 1000000000000h
0x1801a8a1c  or      rax, rcx
0x1801a8a1f  jmp     short loc_1801A8A48
0x1801a8a21  call    cs:__imp_GetLastError
0x1801a8a27  test    eax, eax
0x1801a8a29  jle     short loc_1801A8A33
0x1801a8a2b  movzx   eax, ax
0x1801a8a2e  or      eax, 80070000h
0x1801a8a33  mov     edx, eax; int
0x1801a8a35  mov     rcx, r14; struct Js::ScriptContext *
0x1801a8a38  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x1801a8a3e  mov     rax, [r14]
0x1801a8a41  mov     rax, [rax+420h]
0x1801a8a48  mov     rcx, [rsp+158h+var_48]
0x1801a8a50  xor     rcx, rsp; StackCookie
0x1801a8a53  call    __security_check_cookie
0x1801a8a58  add     rsp, 120h
0x1801a8a5f  pop     r15
0x1801a8a61  pop     r14
0x1801a8a63  pop     r12
0x1801a8a65  pop     rdi
0x1801a8a66  pop     rsi
0x1801a8a67  pop     rbp
0x1801a8a68  pop     rbx
0x1801a8a69  retn
```
