# CConflictFolder::_GetConflictParsingName(CConflictFolder::tagIDCONFLICT const *,ushort * *)

- ea: `0x1800365cc`
- end: `0x1800367c6`
- name: `?_GetConflictParsingName@CConflictFolder@@AEAAJPEFBUtagIDCONFLICT@1@PEAPEAG@Z`
- size: `506`
- prototype: `__int64 __fastcall(CConflictFolder *this, const struct CConflictFolder::tagIDCONFLICT *, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033290`

## callees

- `0x180008584`
- `0x180023860`
- `0x180032dc4`
- `0x1800365cc`
- `0x180036ba8`
- `0x1800387b4`
- `0x180052950`

## import_xrefs

- `SHLWAPI!__imp_ualstrlenW` at `0x1800366cc`
- `SHLWAPI!__imp_ualstrlenW` at `0x1800366cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036794`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003678b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036779`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036782`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003678b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366f7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800366f7`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_GetConflictParsingName(
        CConflictFolder *this,
        const struct CConflictFolder::tagIDCONFLICT *a2,
        unsigned __int16 **a3,
        unsigned int a4)
{
  int Name; // ebx
  WCHAR *v7; // r13
  LPCWSTR v8; // rax
  int v9; // eax
  ASSOCKEY v10; // edx
  const WCHAR *v11; // r8
  const WCHAR *v12; // r9
  WCHAR *v13; // r14
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rdi
  int v17; // eax
  WCHAR *v18; // r12
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // rdx
  WCHAR *v24; // rdi
  HKEY *v26; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpString; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v28; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v31; // [rsp+68h] [rbp-98h]
  WCHAR String[264]; // [rsp+70h] [rbp-90h] BYREF

  *a3 = 0;
  Name = CConflictFolder::_GetName(this, a2, String, a4);
  if ( Name >= 0 )
  {
    v28 = 0;
    lpString = 0;
    Name = CConflictFolder::tagIDCONFLICT::GetAlignedIdAndExtra(
             a2,
             (struct _BYTE_BLOB **)&v28,
             (struct _BYTE_BLOB **)&lpString);
    if ( Name >= 0 )
    {
      v7 = (WCHAR *)v28;
      v29[0] = *((unsigned __int16 *)a2 + 68);
      v29[1] = v28 + 2;
      v30[0] = *((unsigned __int16 *)a2 + 69);
      v30[1] = 0;
      v8 = lpString + 2;
      lpString = 0;
      v31 = v8;
      Name = BlobToText(v29, &lpString);
      if ( Name >= 0 )
      {
        v28 = 0;
        v9 = BlobToText(v30, &v28);
        v13 = (WCHAR *)lpString;
        Name = v9;
        if ( v9 >= 0 )
        {
          v29[0] = (char *)a2 + 8;
          LODWORD(v14) = ualstrlenW((_DWORD)a2 + 8, v10, v11, v12, v26);
          v15 = v14;
          v16 = lstrlenW(String);
          v17 = lstrlenW(v13);
          v18 = (WCHAR *)v28;
          v19 = v17;
          v20 = lstrlenW(v28);
          lpString = 0;
          v21 = v19 + v20;
          v22 = v21 + v16;
          Name = _AllocArray<unsigned short,CTLocalAllocPolicy>(v21, 64, v22 + v15 + 8, &lpString);
          if ( Name >= 0 )
          {
            v23 = v22 + 8;
            v24 = (WCHAR *)lpString;
            Name = StringCchPrintfW(
                     (unsigned __int16 *)lpString,
                     v15 + v23,
                     L"%ws::%ws:%ws:%ws:%ws",
                     L"CF",
                     v29[0],
                     String,
                     v13,
                     v18);
            if ( Name < 0 )
              LocalFree(v24);
            else
              *a3 = v24;
          }
          LocalFree(v18);
        }
        LocalFree(v13);
      }
      CoTaskMemFree(v7);
    }
  }
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x1800365cc  mov     [rsp-8+arg_0], rbx
0x1800365d1  push    rbp
0x1800365d2  push    rsi
0x1800365d3  push    rdi
0x1800365d4  push    r12
0x1800365d6  push    r13
0x1800365d8  push    r14
0x1800365da  push    r15
0x1800365dc  lea     rbp, [rsp-190h]
0x1800365e4  sub     rsp, 290h
0x1800365eb  mov     rax, cs:__security_cookie
0x1800365f2  xor     rax, rsp
0x1800365f5  mov     [rbp+1C0h+var_40], rax
0x1800365fc  mov     r15, r8
0x1800365ff  xor     esi, esi
0x180036601  mov     [r8], rsi
0x180036604  mov     rdi, rdx
0x180036607  lea     r8, [rsp+2C0h+String]; unsigned __int16 *
0x18003660c  call    ?_GetName@CConflictFolder@@AEAAJPEFBUtagIDCONFLICT@1@PEAGI@Z; CConflictFolder::_GetName(CConflictFolder::tagIDCONFLICT const *,ushort *,uint)
0x180036611  mov     ebx, eax
0x180036613  test    eax, eax
0x180036615  js      loc_18003679A
0x18003661b  lea     r8, [rsp+2C0h+lpString]; struct _BYTE_BLOB **
0x180036620  mov     [rsp+2C0h+var_278], rsi
0x180036625  lea     rdx, [rsp+2C0h+var_278]; struct _BYTE_BLOB **
0x18003662a  mov     [rsp+2C0h+lpString], rsi
0x18003662f  mov     rcx, rdi; this
0x180036632  call    ?GetAlignedIdAndExtra@tagIDCONFLICT@CConflictFolder@@QEBAJPEAPEAU_BYTE_BLOB@@0@Z; CConflictFolder::tagIDCONFLICT::GetAlignedIdAndExtra(_BYTE_BLOB * *,_BYTE_BLOB * *)
0x180036637  mov     ebx, eax
0x180036639  test    eax, eax
0x18003663b  js      loc_18003679A
0x180036641  movzx   eax, word ptr [rdi+88h]
0x180036648  lea     rdx, [rsp+2C0h+lpString]
0x18003664d  mov     r13, [rsp+2C0h+var_278]
0x180036652  lea     rcx, [rsp+2C0h+var_270]
0x180036657  mov     dword ptr [rsp+2C0h+var_270], eax
0x18003665b  xor     eax, eax
0x18003665d  mov     dword ptr [rsp+2C0h+var_270+4], eax
0x180036661  lea     rax, [r13+4]
0x180036665  mov     [rsp+2C0h+var_268], rax
0x18003666a  movzx   eax, word ptr [rdi+8Ah]
0x180036671  mov     [rsp+2C0h+var_260], eax
0x180036675  xor     eax, eax
0x180036677  mov     [rsp+2C0h+var_25C], eax
0x18003667b  mov     rax, [rsp+2C0h+lpString]
0x180036680  add     rax, 4
0x180036684  mov     [rsp+2C0h+lpString], rsi
0x180036689  mov     [rsp+2C0h+var_258], rax
0x18003668e  call    BlobToText
0x180036693  mov     ebx, eax
0x180036695  test    eax, eax
0x180036697  js      loc_180036791
0x18003669d  lea     rdx, [rsp+2C0h+var_278]
0x1800366a2  mov     [rsp+2C0h+var_278], rsi
0x1800366a7  lea     rcx, [rsp+2C0h+var_260]
0x1800366ac  call    BlobToText
0x1800366b1  mov     r14, [rsp+2C0h+lpString]
0x1800366b6  mov     ebx, eax
0x1800366b8  test    eax, eax
0x1800366ba  js      loc_180036788
0x1800366c0  lea     rax, [rdi+8]
0x1800366c4  mov     rcx, rax; flags
0x1800366c7  mov     [rsp+2C0h+var_270], rax
0x1800366cc  call    cs:__imp_ualstrlenW
0x1800366d2  lea     rcx, [rsp+2C0h+String]; lpString
0x1800366d7  mov     rsi, rax
0x1800366da  call    cs:__imp_lstrlenW
0x1800366e0  mov     rcx, r14; lpString
0x1800366e3  movsxd  rdi, eax
0x1800366e6  call    cs:__imp_lstrlenW
0x1800366ec  mov     r12, [rsp+2C0h+var_278]
0x1800366f1  mov     rcx, r12; lpString
0x1800366f4  movsxd  rbx, eax
0x1800366f7  call    cs:__imp_lstrlenW
0x1800366fd  lea     r8, [rsi+8]
0x180036701  mov     [rsp+2C0h+lpString], 0
0x18003670a  movsxd  rcx, eax
0x18003670d  lea     r9, [rsp+2C0h+lpString]
0x180036712  add     rcx, rbx
0x180036715  mov     edx, 40h ; '@'
0x18003671a  add     rdi, rcx
0x18003671d  add     r8, rdi
0x180036720  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180036725  mov     ebx, eax
0x180036727  test    eax, eax
0x180036729  js      short loc_18003677F
0x18003672b  mov     [rsp+2C0h+var_288], r12
0x180036730  lea     rax, [rsp+2C0h+String]
0x180036735  mov     [rsp+2C0h+var_290], r14
0x18003673a  lea     rdx, [rdi+8]
0x18003673e  mov     rdi, [rsp+2C0h+lpString]
0x180036743  lea     r9, psz2; "CF"
0x18003674a  mov     [rsp+2C0h+var_298], rax
0x18003674f  lea     r8, aWsWsWsWsWs; "%ws::%ws:%ws:%ws:%ws"
0x180036756  mov     rax, [rsp+2C0h+var_270]
0x18003675b  add     rdx, rsi; unsigned __int64
0x18003675e  mov     rcx, rdi; unsigned __int16 *
0x180036761  mov     [rsp+2C0h+var_2A0], rax
0x180036766  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003676b  mov     ebx, eax
0x18003676d  test    eax, eax
0x18003676f  js      short loc_180036776
0x180036771  mov     [r15], rdi
0x180036774  jmp     short loc_18003677F
0x180036776  mov     rcx, rdi; hMem
0x180036779  call    cs:__imp_LocalFree
0x18003677f  mov     rcx, r12; hMem
0x180036782  call    cs:__imp_LocalFree
0x180036788  mov     rcx, r14; hMem
0x18003678b  call    cs:__imp_LocalFree
0x180036791  mov     rcx, r13; pv
0x180036794  call    cs:__imp_CoTaskMemFree
0x18003679a  mov     eax, ebx
0x18003679c  mov     rcx, [rbp+1C0h+var_40]
0x1800367a3  xor     rcx, rsp; StackCookie
0x1800367a6  call    __security_check_cookie
0x1800367ab  mov     rbx, [rsp+2C0h+arg_0]
0x1800367b3  add     rsp, 290h
0x1800367ba  pop     r15
0x1800367bc  pop     r14
0x1800367be  pop     r13
0x1800367c0  pop     r12
0x1800367c2  pop     rdi
0x1800367c3  pop     rsi
0x1800367c4  pop     rbp
0x1800367c5  retn
```
