# GetFirstCorruptionInfo(ushort const *,ulong,FMIFS_CORRUPTION_INFO * *)

- ea: `0x1800070d0`
- end: `0x18000725e`
- name: `?GetFirstCorruptionInfo@@YAPEAXPEBGKPEAPEAUFMIFS_CORRUPTION_INFO@@@Z`
- size: `398`
- prototype: `void *__fastcall(LPCWSTR lpFileName, unsigned int, struct FMIFS_CORRUPTION_INFO **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180003ca0`
- `0x1800070d0`
- `0x180008720`
- `0x18000a010`

## import_xrefs

- `msvcrt!malloc` at `0x180007126`
- `msvcrt!malloc` at `0x180007126`
- `msvcrt!free` at `0x1800071cc`
- `msvcrt!free` at `0x1800071cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007249`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007249`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007175`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007175`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007197`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007197`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800071c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800071c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071f8`

## string_xrefs

- `0x180007190`: `untfs.dll`
- `0x1800071a6`: `CreateFormatCorruptionRecordContext`
- `0x1800071d7`: `DeleteFormatCorruptionRecordContext`

## pseudocode

```c
__int64 __fastcall GetFirstCorruptionInfo(LPCWSTR lpFileName, unsigned int a2, struct FMIFS_CORRUPTION_INFO **a3)
{
  void *v6; // rbx
  DWORD v7; // ecx
  HANDLE FileW; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v11; // rcx
  FARPROC v13; // rax
  FARPROC v14; // rax
  __int64 v15; // [rsp+40h] [rbp-38h] BYREF
  int v16; // [rsp+48h] [rbp-30h]

  v15 = 0;
  v16 = 0;
  if ( a3 && lpFileName && (unsigned __int8)QueryCorruptionState(lpFileName, &v15, 0) && (v15 & 0x200000000LL) != 0 )
  {
    v6 = malloc(0x38u);
    if ( v6 )
    {
      *(_OWORD *)v6 = 0;
      *((_OWORD *)v6 + 1) = 0;
      *((_OWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 6) = 0;
      FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      if ( FileW != (HANDLE)-1LL )
      {
        *(_QWORD *)v6 = FileW;
        *((_QWORD *)v6 + 1) = 0;
        Library = LoadLibraryExW(L"untfs.dll", 0, 0);
        *((_QWORD *)v6 + 2) = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "CreateFormatCorruptionRecordContext");
          v11 = (HMODULE)*((_QWORD *)v6 + 2);
          *((_QWORD *)v6 + 4) = ProcAddress;
          if ( ProcAddress )
          {
            v13 = GetProcAddress(v11, "DeleteFormatCorruptionRecordContext");
            v11 = (HMODULE)*((_QWORD *)v6 + 2);
            *((_QWORD *)v6 + 5) = v13;
            if ( v13 )
            {
              v14 = GetProcAddress(v11, "FormatCorruptionRecordW");
              *((_QWORD *)v6 + 6) = v14;
              if ( v14 && (*((int (__fastcall **)(__int64))v6 + 4))((__int64)v6 + 24) >= 0 )
              {
                if ( (unsigned __int8)GetNextCorruptionInfo(v6, a2, a3) )
                  return (__int64)v6;
                (*((void (__fastcall **)(_QWORD))v6 + 5))(*((_QWORD *)v6 + 3));
              }
              v11 = (HMODULE)*((_QWORD *)v6 + 2);
            }
          }
          FreeLibrary(v11);
        }
      }
      free(v6);
      return -1;
    }
    v7 = 8;
  }
  else
  {
    v7 = 87;
  }
  SetLastError(v7);
  return -1;
}

```

## disassembly

```asm
0x1800070d0  push    rbx
0x1800070d2  push    rbp
0x1800070d3  push    rsi
0x1800070d4  push    rdi
0x1800070d5  push    r14
0x1800070d7  sub     rsp, 50h
0x1800070db  xor     eax, eax
0x1800070dd  mov     rbp, r8
0x1800070e0  mov     [rsp+78h+var_38], rax
0x1800070e5  mov     r14d, edx
0x1800070e8  mov     [rsp+78h+var_30], eax
0x1800070ec  mov     rsi, rcx
0x1800070ef  test    r8, r8
0x1800070f2  jz      loc_180007244
0x1800070f8  test    rcx, rcx
0x1800070fb  jz      loc_180007244
0x180007101  xor     r8d, r8d
0x180007104  lea     rdx, [rsp+78h+var_38]
0x180007109  call    QueryCorruptionState
0x18000710e  test    al, al
0x180007110  jz      loc_180007244
0x180007116  test    byte ptr [rsp+78h+var_38+4], 2
0x18000711b  jz      loc_180007244
0x180007121  mov     ecx, 38h ; '8'; Size
0x180007126  call    cs:__imp_malloc
0x18000712c  mov     rbx, rax
0x18000712f  test    rax, rax
0x180007132  jnz     short loc_18000713C
0x180007134  lea     ecx, [rax+8]
0x180007137  jmp     loc_180007249
0x18000713c  xorps   xmm0, xmm0
0x18000713f  xor     eax, eax
0x180007141  movups  xmmword ptr [rbx], xmm0
0x180007144  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007148  xor     r9d, r9d; lpSecurityAttributes
0x18000714b  movups  xmmword ptr [rbx+10h], xmm0
0x18000714f  lea     r8d, [rax+3]; dwShareMode
0x180007153  mov     [rsp+78h+hTemplateFile], rdi; hTemplateFile
0x180007158  movups  xmmword ptr [rbx+20h], xmm0
0x18000715c  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007164  mov     edx, 0C0000000h; dwDesiredAccess
0x180007169  mov     rcx, rsi; lpFileName
0x18000716c  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x180007171  mov     [rbx+30h], rax
0x180007175  call    cs:__imp_CreateFileW
0x18000717b  cmp     rax, rdi
0x18000717e  jz      short loc_1800071C9
0x180007180  xor     r8d, r8d; dwFlags
0x180007183  mov     [rbx], rax
0x180007186  xor     edx, edx; hFile
0x180007188  mov     qword ptr [rbx+8], 0
0x180007190  lea     rcx, LibFileName; "untfs.dll"
0x180007197  call    cs:__imp_LoadLibraryExW
0x18000719d  mov     [rbx+10h], rax
0x1800071a1  test    rax, rax
0x1800071a4  jz      short loc_1800071C9
0x1800071a6  lea     rdx, ProcName; "CreateFormatCorruptionRecordContext"
0x1800071ad  mov     rcx, rax; hModule
0x1800071b0  call    cs:__imp_GetProcAddress
0x1800071b6  mov     rcx, [rbx+10h]; hModule
0x1800071ba  mov     [rbx+20h], rax
0x1800071be  test    rax, rax
0x1800071c1  jnz     short loc_1800071D7
0x1800071c3  call    cs:__imp_FreeLibrary
0x1800071c9  mov     rcx, rbx; Block
0x1800071cc  call    cs:__imp_free
0x1800071d2  mov     rax, rdi
0x1800071d5  jmp     short loc_180007253
0x1800071d7  lea     rdx, aDeleteformatco; "DeleteFormatCorruptionRecordContext"
0x1800071de  call    cs:__imp_GetProcAddress
0x1800071e4  mov     rcx, [rbx+10h]; hModule
0x1800071e8  mov     [rbx+28h], rax
0x1800071ec  test    rax, rax
0x1800071ef  jz      short loc_1800071C3
0x1800071f1  lea     rdx, aFormatcorrupti; "FormatCorruptionRecordW"
0x1800071f8  call    cs:__imp_GetProcAddress
0x1800071fe  mov     [rbx+30h], rax
0x180007202  test    rax, rax
0x180007205  jnz     short loc_18000720D
0x180007207  mov     rcx, [rbx+10h]
0x18000720b  jmp     short loc_1800071C3
0x18000720d  mov     rax, [rbx+20h]
0x180007211  lea     rcx, [rbx+18h]
0x180007215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000721a  test    eax, eax
0x18000721c  js      short loc_180007207
0x18000721e  mov     r8, rbp
0x180007221  mov     edx, r14d
0x180007224  mov     rcx, rbx
0x180007227  call    GetNextCorruptionInfo
0x18000722c  test    al, al
0x18000722e  jnz     short loc_18000723F
0x180007230  mov     rcx, [rbx+18h]
0x180007234  mov     rax, [rbx+28h]
0x180007238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000723d  jmp     short loc_180007207
0x18000723f  mov     rax, rbx
0x180007242  jmp     short loc_180007253
0x180007244  mov     ecx, 57h ; 'W'; dwErrCode
0x180007249  call    cs:__imp_SetLastError
0x18000724f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007253  add     rsp, 50h
0x180007257  pop     r14
0x180007259  pop     rdi
0x18000725a  pop     rsi
0x18000725b  pop     rbp
0x18000725c  pop     rbx
0x18000725d  retn
```
