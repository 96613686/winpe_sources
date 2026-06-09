# BrowseForDir(HWND__ *,ushort const *,ushort *,ulong)

- ea: `0x1800042f8`
- end: `0x180004490`
- name: `?BrowseForDir@@YAHPEAUHWND__@@PEBGPEAGK@Z`
- size: `408`
- prototype: `_BOOL8 __fastcall(HWND hWnd, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800056d0`

## callees

- `0x1800022bc`
- `0x180002c74`
- `0x1800042f8`
- `0x180008a6c`
- `0x18001b94e`
- `0x18001c010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004439`
- `KERNEL32!FreeLibrary` at `0x180004452`
- `KERNEL32!FreeLibrary` at `0x180004439`
- `KERNEL32!FreeLibrary` at `0x180004452`
- `KERNEL32!LoadLibraryExW` at `0x180004329`
- `KERNEL32!LoadLibraryExW` at `0x180004329`
- `KERNEL32!GetProcAddress` at `0x180004348`
- `KERNEL32!GetProcAddress` at `0x180004362`
- `KERNEL32!GetProcAddress` at `0x18000437e`
- `KERNEL32!GetProcAddress` at `0x180004348`
- `KERNEL32!GetProcAddress` at `0x180004362`
- `KERNEL32!GetProcAddress` at `0x18000437e`

## string_xrefs

- `0x180004374`: `SHGetPathFromIDListW`
- `0x18000431c`: `SHELL32.DLL`

## pseudocode

```c
_BOOL8 __fastcall BrowseForDir(HWND hWnd, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // r14
  FARPROC v7; // rsi
  FARPROC v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rdi
  UINT v12; // edx
  _QWORD v13[4]; // [rsp+30h] [rbp-78h] BYREF
  int v14; // [rsp+50h] [rbp-58h]
  __int64 (__fastcall *v15)(HWND, unsigned int, __int64, __int64); // [rsp+58h] [rbp-50h]
  unsigned __int16 *v16; // [rsp+60h] [rbp-48h]

  memset_0(v13, 0, 0x40u);
  Library = LoadLibraryExW(L"SHELL32.DLL", 0, 0x800u);
  v5 = Library;
  if ( !Library )
  {
    v12 = 1107;
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(Library, "SHBrowseForFolderW");
  if ( !ProcAddress
    || (v7 = GetProcAddress(v5, (LPCSTR)0xC3)) == 0
    || (v8 = GetProcAddress(v5, "SHGetPathFromIDListW")) == 0 )
  {
    FreeLibrary(v5);
    v12 = 1106;
LABEL_14:
    MsgBox2Param(hWnd, v12, 0, 0, 0x10u, 0);
    return 0;
  }
  if ( !word_180025800 )
    GetProgramFilesDir(&word_180025800, 0x104u);
  String = 0;
  v13[3] = &Buffer;
  v13[0] = hWnd;
  v15 = BrowseCallback;
  v13[1] = 0;
  v13[2] = 0;
  v14 = 1;
  v16 = &word_180025800;
  v9 = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v13);
  v10 = v9;
  if ( v9 )
  {
    ((void (__fastcall *)(__int64, unsigned __int16 *))v8)(v9, &word_180025800);
    if ( word_180025800 )
      StringCchCopyW(&String, 0x104u, &word_180025800);
    ((void (__fastcall *)(__int64))v7)(v10);
  }
  FreeLibrary(v5);
  return String != 0;
}

```

## disassembly

```asm
0x1800042f8  push    rbx
0x1800042fa  push    rbp
0x1800042fb  push    rsi
0x1800042fc  push    rdi
0x1800042fd  push    r12
0x1800042ff  push    r14
0x180004301  push    r15
0x180004303  sub     rsp, 70h
0x180004307  xor     edx, edx; Val
0x180004309  mov     rdi, rcx
0x18000430c  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004311  lea     r8d, [rdx+40h]; Size
0x180004315  call    memset_0
0x18000431a  xor     edx, edx; hFile
0x18000431c  lea     rcx, LibFileName; "SHELL32.DLL"
0x180004323  mov     r8d, 800h; dwFlags
0x180004329  call    cs:__imp_LoadLibraryExW
0x18000432f  xor     r15d, r15d
0x180004332  mov     rbx, rax
0x180004335  test    rax, rax
0x180004338  jz      loc_18000445F
0x18000433e  lea     rdx, ProcName; "SHBrowseForFolderW"
0x180004345  mov     rcx, rax; hModule
0x180004348  call    cs:__imp_GetProcAddress
0x18000434e  mov     r14, rax
0x180004351  test    rax, rax
0x180004354  jz      loc_18000444F
0x18000435a  mov     edx, 0C3h; lpProcName
0x18000435f  mov     rcx, rbx; hModule
0x180004362  call    cs:__imp_GetProcAddress
0x180004368  mov     rsi, rax
0x18000436b  test    rax, rax
0x18000436e  jz      loc_18000444F
0x180004374  lea     rdx, aShgetpathfromi; "SHGetPathFromIDListW"
0x18000437b  mov     rcx, rbx; hModule
0x18000437e  call    cs:__imp_GetProcAddress
0x180004384  mov     rbp, rax
0x180004387  test    rax, rax
0x18000438a  jz      loc_18000444F
0x180004390  cmp     cs:word_180025800, r15w
0x180004398  lea     r12, word_180025800
0x18000439f  jnz     short loc_1800043AE
0x1800043a1  mov     edx, 104h; unsigned int
0x1800043a6  mov     rcx, r12; unsigned __int16 *
0x1800043a9  call    ?GetProgramFilesDir@@YAHPEAGK@Z; GetProgramFilesDir(ushort *,ulong)
0x1800043ae  lea     rax, Buffer
0x1800043b5  mov     cs:String, r15w
0x1800043bd  mov     [rsp+0A8h+var_60], rax
0x1800043c2  lea     rcx, [rsp+0A8h+var_78]
0x1800043c7  lea     rax, ?BrowseCallback@@YAHPEAUHWND__@@I_J1@Z; BrowseCallback(HWND__ *,uint,__int64,__int64)
0x1800043ce  mov     [rsp+0A8h+var_78], rdi
0x1800043d3  mov     [rsp+0A8h+var_50], rax
0x1800043d8  mov     rax, r14
0x1800043db  mov     [rsp+0A8h+var_70], r15
0x1800043e0  mov     [rsp+0A8h+var_68], r15
0x1800043e5  mov     [rsp+0A8h+var_58], 1
0x1800043ed  mov     [rsp+0A8h+var_48], r12
0x1800043f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f7  mov     rdi, rax
0x1800043fa  test    rax, rax
0x1800043fd  jz      short loc_180004436
0x1800043ff  mov     rcx, rax
0x180004402  mov     rdx, r12
0x180004405  mov     rax, rbp
0x180004408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000440d  cmp     cs:word_180025800, r15w
0x180004415  jz      short loc_18000442B
0x180004417  mov     r8, r12; unsigned __int16 *
0x18000441a  lea     rcx, String; unsigned __int16 *
0x180004421  mov     edx, 104h; unsigned __int64
0x180004426  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000442b  mov     rcx, rdi
0x18000442e  mov     rax, rsi
0x180004431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004436  mov     rcx, rbx; hLibModule
0x180004439  call    cs:__imp_FreeLibrary
0x18000443f  cmp     cs:String, r15w
0x180004447  mov     eax, r15d
0x18000444a  setnz   al
0x18000444d  jmp     short loc_180004481
0x18000444f  mov     rcx, rbx; hLibModule
0x180004452  call    cs:__imp_FreeLibrary
0x180004458  mov     edx, 452h
0x18000445d  jmp     short loc_180004464
0x18000445f  mov     edx, 453h; uID
0x180004464  mov     [rsp+0A8h+var_80], r15d; unsigned int
0x180004469  xor     r9d, r9d; unsigned __int16 *
0x18000446c  xor     r8d, r8d; unsigned __int16 *
0x18000446f  mov     [rsp+0A8h+var_88], 10h; unsigned int
0x180004477  mov     rcx, rdi; hWnd
0x18000447a  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000447f  xor     eax, eax
0x180004481  add     rsp, 70h
0x180004485  pop     r15
0x180004487  pop     r14
0x180004489  pop     r12
0x18000448b  pop     rdi
0x18000448c  pop     rsi
0x18000448d  pop     rbp
0x18000448e  pop     rbx
0x18000448f  retn
```
