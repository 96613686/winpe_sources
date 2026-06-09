# HciModel::Parse(ushort const *,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &)

- ea: `0x18001fa7c`
- end: `0x18001fc8b`
- name: `?Parse@HciModel@@AEAAJPEBGAEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f914`

## callees

- `0x18000466c`
- `0x180005340`
- `0x18001f734`
- `0x18001fa7c`
- `0x18002d1fa`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001faec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001faec`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001fad0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001fad0`

## string_xrefs

- `0x18001fbd4`: `Accommodation`
- `0x18001fac9`: `xmllite.dll`
- `0x18001fae2`: `CreateXmlReader`

## pseudocode

```c
__int64 __fastcall HciModel::Parse(HMODULE *a1, __int64 a2, __int64 a3)
{
  int v5; // ebx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  char v8; // r14
  int v9; // ebx
  int v10; // edi
  int v11; // r13d
  __int64 v12; // rsi
  int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-28h] BYREF
  __int64 v16; // [rsp+28h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+30h] [rbp-18h] BYREF
  __int64 v18; // [rsp+38h] [rbp-10h] BYREF
  int v19; // [rsp+A8h] [rbp+60h] BYREF

  v16 = 0;
  v5 = HciModel::CreateStream(a1, &v16, a2);
  if ( v5 < 0 )
    goto LABEL_27;
  LibraryW = *a1;
  v5 = -2147467259;
  v15 = 0;
  if ( !LibraryW && (LibraryW = LoadLibraryW(L"xmllite.dll"), (*a1 = LibraryW) == 0)
    || (ProcAddress = GetProcAddress(LibraryW, "CreateXmlReader")) == 0
    || (v5 = ((__int64 (__fastcall *)(GUID *, __int64 *, _QWORD))ProcAddress)(
               &GUID_7279fc81_709d_4095_b63d_69fe4b0d9030,
               &v15,
               0),
        v5 < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
LABEL_27:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    return (unsigned int)v5;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 24LL))(v15, v16);
  v8 = 0;
  v19 = 0;
  v9 = 0;
  String1 = 0;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 48LL))(v15, &v19);
    if ( v10 )
      break;
    if ( v19 == 1 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 160LL))(v15);
      v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v15 + 112LL))(v15, &String1, 0);
      if ( v9 )
      {
        if ( v9 == 1 && !wcscmp_0(String1, L"Accommodation") )
        {
          v12 = v15;
          v18 = 0;
          if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v15 + 80LL))(
                  v15,
                  L"type",
                  0)
            && (*(int (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v12 + 128LL))(v12, &v18, 0) >= 0 )
          {
            ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
              a3,
              v18);
          }
        }
      }
      else if ( !v8 )
      {
        if ( wcscmp_0(String1, L"HCIModel") )
        {
          v10 = -2147467259;
          break;
        }
        v8 = 1;
      }
      v13 = v9++;
      if ( v11 )
        v9 = v13;
      if ( v10 < 0 )
        break;
    }
    else if ( v19 == 15 )
    {
      --v9;
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001fa7c  push    rbp
0x18001fa7e  push    rbx
0x18001fa7f  push    rsi
0x18001fa80  push    rdi
0x18001fa81  push    r12
0x18001fa83  push    r13
0x18001fa85  push    r14
0x18001fa87  push    r15
0x18001fa89  mov     rbp, rsp
0x18001fa8c  sub     rsp, 48h
0x18001fa90  mov     r12, r8
0x18001fa93  mov     [rbp+var_20], 0
0x18001fa9b  mov     r8, rdx
0x18001fa9e  mov     rdi, rcx
0x18001faa1  lea     rdx, [rbp+var_20]
0x18001faa5  call    ?CreateStream@HciModel@@AEAAJAEAV?$CComPtr@UIStream@@@ATL@@PEBG@Z; HciModel::CreateStream(ATL::CComPtr<IStream> &,ushort const *)
0x18001faaa  mov     ebx, eax
0x18001faac  test    eax, eax
0x18001faae  js      loc_18001FC6F
0x18001fab4  mov     rax, [rdi]
0x18001fab7  mov     ebx, 80004005h
0x18001fabc  mov     [rbp+var_28], 0
0x18001fac4  test    rax, rax
0x18001fac7  jnz     short loc_18001FAE2
0x18001fac9  lea     rcx, LibFileName; "xmllite.dll"
0x18001fad0  call    cs:__imp_LoadLibraryW
0x18001fad6  mov     [rdi], rax
0x18001fad9  test    rax, rax
0x18001fadc  jz      loc_18001FC66
0x18001fae2  lea     rdx, aCreatexmlreade; "CreateXmlReader"
0x18001fae9  mov     rcx, rax; hModule
0x18001faec  call    cs:__imp_GetProcAddress
0x18001faf2  test    rax, rax
0x18001faf5  jz      loc_18001FC66
0x18001fafb  xor     r8d, r8d
0x18001fafe  lea     rdx, [rbp+var_28]
0x18001fb02  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030
0x18001fb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb0e  mov     ebx, eax
0x18001fb10  test    eax, eax
0x18001fb12  js      loc_18001FC66
0x18001fb18  mov     rcx, [rbp+var_28]
0x18001fb1c  mov     rdx, [rbp+var_20]
0x18001fb20  mov     rax, [rcx]
0x18001fb23  mov     rax, [rax+18h]
0x18001fb27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb2c  xor     r14b, r14b
0x18001fb2f  mov     [rbp+arg_18], 0
0x18001fb36  xor     ebx, ebx
0x18001fb38  mov     [rbp+String1], rbx
0x18001fb3c  mov     rcx, [rbp+var_28]
0x18001fb40  lea     rdx, [rbp+arg_18]
0x18001fb44  mov     rax, [rcx]
0x18001fb47  mov     rax, [rax+30h]
0x18001fb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb50  mov     edi, eax
0x18001fb52  test    eax, eax
0x18001fb54  jnz     loc_18001FC50
0x18001fb5a  mov     ecx, [rbp+arg_18]
0x18001fb5d  sub     ecx, 1
0x18001fb60  jz      short loc_18001FB6B
0x18001fb62  cmp     ecx, 0Eh
0x18001fb65  jnz     short loc_18001FB3C
0x18001fb67  dec     ebx
0x18001fb69  jmp     short loc_18001FB3C
0x18001fb6b  mov     rcx, [rbp+var_28]
0x18001fb6f  mov     rax, [rcx]
0x18001fb72  mov     rax, [rax+0A0h]
0x18001fb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb7e  mov     rcx, [rbp+var_28]
0x18001fb82  lea     r15d, [rbx+1]
0x18001fb86  mov     r13d, eax
0x18001fb89  xor     r8d, r8d
0x18001fb8c  mov     rdx, [rcx]
0x18001fb8f  mov     rax, [rdx+70h]
0x18001fb93  lea     rdx, [rbp+String1]
0x18001fb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb9c  mov     edi, eax
0x18001fb9e  cmp     r15d, 1
0x18001fba2  jnz     short loc_18001FBCA
0x18001fba4  test    r14b, r14b
0x18001fba7  jnz     loc_18001FC36
0x18001fbad  mov     rcx, [rbp+String1]; String1
0x18001fbb1  lea     rdx, aHcimodel; "HCIModel"
0x18001fbb8  call    wcscmp_0
0x18001fbbd  test    eax, eax
0x18001fbbf  jnz     loc_18001FC4B
0x18001fbc5  mov     r14b, r15b
0x18001fbc8  jmp     short loc_18001FC36
0x18001fbca  cmp     r15d, 2
0x18001fbce  jnz     short loc_18001FC36
0x18001fbd0  mov     rcx, [rbp+String1]; String1
0x18001fbd4  lea     rdx, aAccommodation; "Accommodation"
0x18001fbdb  call    wcscmp_0
0x18001fbe0  test    eax, eax
0x18001fbe2  jnz     short loc_18001FC36
0x18001fbe4  mov     rsi, [rbp+var_28]
0x18001fbe8  lea     rdx, aType; "type"
0x18001fbef  xor     r8d, r8d
0x18001fbf2  mov     [rbp+var_10], 0
0x18001fbfa  mov     rcx, rsi
0x18001fbfd  mov     rax, [rsi]
0x18001fc00  mov     rax, [rax+50h]
0x18001fc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc09  test    eax, eax
0x18001fc0b  jnz     short loc_18001FC36
0x18001fc0d  mov     rax, [rsi]
0x18001fc10  lea     rdx, [rbp+var_10]
0x18001fc14  xor     r8d, r8d
0x18001fc17  mov     rcx, rsi
0x18001fc1a  mov     rax, [rax+80h]
0x18001fc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc26  test    eax, eax
0x18001fc28  js      short loc_18001FC36
0x18001fc2a  mov     rdx, [rbp+var_10]
0x18001fc2e  mov     rcx, r12
0x18001fc31  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x18001fc36  mov     eax, ebx
0x18001fc38  test    r13d, r13d
0x18001fc3b  mov     ebx, r15d
0x18001fc3e  cmovnz  ebx, eax
0x18001fc41  test    edi, edi
0x18001fc43  jns     loc_18001FB3C
0x18001fc49  jmp     short loc_18001FC50
0x18001fc4b  mov     edi, 80004005h
0x18001fc50  lea     rcx, [rbp+var_28]
0x18001fc54  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fc59  lea     rcx, [rbp+var_20]
0x18001fc5d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fc62  mov     eax, edi
0x18001fc64  jmp     short loc_18001FC7A
0x18001fc66  lea     rcx, [rbp+var_28]
0x18001fc6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fc6f  lea     rcx, [rbp+var_20]
0x18001fc73  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fc78  mov     eax, ebx
0x18001fc7a  add     rsp, 48h
0x18001fc7e  pop     r15
0x18001fc80  pop     r14
0x18001fc82  pop     r13
0x18001fc84  pop     r12
0x18001fc86  pop     rdi
0x18001fc87  pop     rsi
0x18001fc88  pop     rbx
0x18001fc89  pop     rbp
0x18001fc8a  retn
```
