# StructuredQuery1::CSchemaFromPropertySystem::LocalizeString(wchar_t const *,_GUID const &,void * *)

- ea: `0x180051368`
- end: `0x180051531`
- name: `?LocalizeString@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WAEBU_GUID@@PEAPEAX@Z`
- size: `457`
- prototype: `__int64 __fastcall(StructuredQuery1::CSchemaFromPropertySystem *this, __int64, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180050efc`
- `0x180051028`

## callees

- `0x18003c580`
- `0x180051368`
- `0x180051538`
- `0x180059920`
- `0x18005daf0`
- `0x18005e85c`
- `0x18008416c`
- `0x180084e10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800513b9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800513b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051509`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051509`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800514de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800514de`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800514b1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800514b1`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::LocalizeString(
        StructuredQuery1::CSchemaFromPropertySystem *this,
        __int64 a2,
        const struct _GUID *a3,
        void **a4)
{
  int Error; // ebx
  const WCHAR *v7; // r15
  WCHAR *v8; // rsi
  wchar_t *v9; // rax
  wchar_t *v10; // rbp
  int v11; // eax
  UINT v12; // r14d
  __int64 v13; // rbp
  HINSTANCE MUILibraryW; // rax
  int StringW; // eax
  int v17; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR Buffer[4096]; // [rsp+40h] [rbp-2048h] BYREF

  if ( a2 )
  {
    Error = 0;
    if ( *(_WORD *)a2 == 64 )
    {
      v7 = (const WCHAR *)(a2 + 2);
      v8 = 0;
      v9 = wcschr((const wchar_t *)(a2 + 2), 0x2Cu);
      v10 = v9;
      if ( v9 && (v17 = 0, v11 = swscanf(v9, L",%ld", &v17), a2 = 1, v11 == 1) && v17 < 0 )
      {
        v12 = -v17;
        v13 = v10 - v7;
        if ( !*((_QWORD *)this + 73) )
          goto LABEL_28;
        if ( CompareStringW(0x7Fu, 1u, v7, v13, (PCNZWCH)this + 32, -1) != 2 )
        {
          FreeLibrary(*((HMODULE *)this + 73));
          *((_QWORD *)this + 73) = 0;
        }
        if ( !*((_QWORD *)this + 73) )
        {
LABEL_28:
          Error = StringCchCopyNW((wchar_t *)this + 32, 0x104u, v7, v13);
          if ( Error < 0 )
            goto LABEL_20;
          MUILibraryW = LoadMUILibraryW((PCWSTR)this + 32, 8u, 0);
          *((_QWORD *)this + 73) = MUILibraryW;
          if ( !MUILibraryW )
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              goto LABEL_20;
          }
        }
        StringW = LoadStringW(*((HINSTANCE *)this + 73), v12, Buffer, 4096);
        if ( StringW <= 0 )
        {
          if ( !StringW )
          {
            Error = -2147467259;
            goto LABEL_20;
          }
          Error = ResultFromKnownLastError();
        }
        else
        {
          v8 = Buffer;
        }
      }
      else
      {
        Error = -2147467259;
      }
    }
    else
    {
      v8 = (WCHAR *)a2;
    }
    if ( Error < 0 )
    {
LABEL_20:
      *a4 = 0;
      return (unsigned int)Error;
    }
  }
  else
  {
    v8 = (WCHAR *)&cchOriginalDestLength;
  }
  return (unsigned int)StructuredQuery1::MnemonicsCollection::CreateInstance(v8, (const struct _GUID *)a2, a4);
}

```

## disassembly

```asm
0x180051368  push    rbx
0x18005136a  push    rbp
0x18005136b  push    rsi
0x18005136c  push    rdi
0x18005136d  push    r12
0x18005136f  push    r14
0x180051371  push    r15
0x180051373  mov     eax, 2050h
0x180051378  call    _alloca_probe
0x18005137d  sub     rsp, rax
0x180051380  mov     rax, cs:__security_cookie
0x180051387  xor     rax, rsp
0x18005138a  mov     [rsp+2088h+var_48], rax
0x180051392  mov     r12, r9
0x180051395  mov     rdi, rcx
0x180051398  test    rdx, rdx
0x18005139b  jz      loc_18005145D
0x1800513a1  xor     ebx, ebx
0x1800513a3  cmp     word ptr [rdx], 40h ; '@'
0x1800513a7  jnz     loc_18005152C
0x1800513ad  lea     r15, [rdx+2]
0x1800513b1  xor     esi, esi
0x1800513b3  mov     rcx, r15; Str
0x1800513b6  lea     edx, [rbx+2Ch]; Ch
0x1800513b9  call    cs:__imp_wcschr
0x1800513bf  mov     rbp, rax
0x1800513c2  test    rax, rax
0x1800513c5  jz      loc_180051525
0x1800513cb  lea     r8, [rsp+2088h+var_2058]
0x1800513d0  mov     [rsp+2088h+var_2058], ebx
0x1800513d4  lea     rdx, aLd_0; ",%ld"
0x1800513db  mov     rcx, rax; Buffer
0x1800513de  call    swscanf
0x1800513e3  lea     edx, [rbx+1]; dwCmpFlags
0x1800513e6  cmp     eax, edx
0x1800513e8  jnz     loc_180051525
0x1800513ee  mov     r14d, [rsp+2088h+var_2058]
0x1800513f3  test    r14d, r14d
0x1800513f6  jns     loc_180051525
0x1800513fc  sub     rbp, r15
0x1800513ff  neg     r14d
0x180051402  sar     rbp, 1
0x180051405  cmp     [rdi+248h], rbx
0x18005140c  jnz     loc_180051495
0x180051412  mov     r9, rbp; unsigned __int64
0x180051415  lea     rcx, [rdi+40h]; wchar_t *
0x180051419  mov     r8, r15; wchar_t *
0x18005141c  mov     edx, 104h; unsigned __int64
0x180051421  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180051426  mov     ebx, eax
0x180051428  test    eax, eax
0x18005142a  js      loc_1800514F5
0x180051430  xor     r8d, r8d; LangID
0x180051433  lea     rcx, [rdi+40h]; pszFullModuleName
0x180051437  lea     edx, [r8+8]; dwLangConvention
0x18005143b  call    LoadMUILibraryW
0x180051440  mov     [rdi+248h], rax
0x180051447  test    rax, rax
0x18005144a  jnz     short loc_1800514C9
0x18005144c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180051451  mov     ebx, eax
0x180051453  test    eax, eax
0x180051455  js      loc_1800514F5
0x18005145b  jmp     short loc_1800514C9
0x18005145d  lea     rsi, cchOriginalDestLength
0x180051464  mov     r8, r12; void **
0x180051467  mov     rcx, rsi; wchar_t *
0x18005146a  call    ?CreateInstance@MnemonicsCollection@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::MnemonicsCollection::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x18005146f  mov     ebx, eax
0x180051471  mov     eax, ebx
0x180051473  mov     rcx, [rsp+2088h+var_48]
0x18005147b  xor     rcx, rsp; StackCookie
0x18005147e  call    __security_check_cookie
0x180051483  add     rsp, 2050h
0x18005148a  pop     r15
0x18005148c  pop     r14
0x18005148e  pop     r12
0x180051490  pop     rdi
0x180051491  pop     rsi
0x180051492  pop     rbp
0x180051493  pop     rbx
0x180051494  retn
0x180051495  lea     rax, [rdi+40h]
0x180051499  mov     [rsp+2088h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800514a1  mov     r9d, ebp; cchCount1
0x1800514a4  mov     [rsp+2088h+lpString2], rax; lpString2
0x1800514a9  mov     r8, r15; lpString1
0x1800514ac  mov     ecx, 7Fh; Locale
0x1800514b1  call    cs:__imp_CompareStringW
0x1800514b7  cmp     eax, 2
0x1800514ba  jnz     short loc_180051502
0x1800514bc  cmp     [rdi+248h], rbx
0x1800514c3  jz      loc_180051412
0x1800514c9  mov     rcx, [rdi+248h]; hInstance
0x1800514d0  lea     r8, [rsp+2088h+Buffer]; lpBuffer
0x1800514d5  mov     r9d, 1000h; cchBufferMax
0x1800514db  mov     edx, r14d; uID
0x1800514de  call    cs:__imp_LoadStringW
0x1800514e4  test    eax, eax
0x1800514e6  jle     short loc_180051518
0x1800514e8  lea     rsi, [rsp+2088h+Buffer]
0x1800514ed  test    ebx, ebx
0x1800514ef  jns     loc_180051464
0x1800514f5  mov     qword ptr [r12], 0
0x1800514fd  jmp     loc_180051471
0x180051502  mov     rcx, [rdi+248h]; hLibModule
0x180051509  call    cs:__imp_FreeLibrary
0x18005150f  mov     [rdi+248h], rbx
0x180051516  jmp     short loc_1800514BC
0x180051518  jnz     loc_18008AAC0
0x18005151e  mov     ebx, 80004005h
0x180051523  jmp     short loc_1800514F5
0x180051525  mov     ebx, 80004005h
0x18005152a  jmp     short loc_1800514ED
0x18005152c  mov     rsi, rdx
0x18005152f  jmp     short loc_1800514ED
0x18008aac0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18008aac5  mov     ebx, eax
0x18008aac7  jmp     loc_1800514ED
```
