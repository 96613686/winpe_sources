# CStackDlg::DoModal(void)

- ea: `0x180089b60`
- end: `0x180089c9b`
- name: `?DoModal@CStackDlg@@QEAA_JXZ`
- size: `315`
- prototype: `__int64 __fastcall(CStackDlg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180089378`

## callees

- `0x1800240b0`
- `0x1800240f0`
- `0x1800899d8`
- `0x180089b60`
- `0x180089ca4`
- `0x180089f1c`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089bef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180089bef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180089c29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180089c29`

## string_xrefs

- `0x180089be4`: `comres.dll`

## pseudocode

```c
__int64 __fastcall CStackDlg::DoModal(CStackDlg *this)
{
  HMODULE *v2; // rax
  CUser32Api *v3; // rbx
  HMODULE Library; // rbx
  __int64 v5; // rdi

  if ( !qword_18015DBA8 )
  {
    v2 = (HMODULE *)operator new(0x88u);
    v3 = (CUser32Api *)v2;
    if ( v2 )
    {
      *v2 = 0;
      if ( !CUser32Api::Initialize(v2) || _InterlockedCompareExchange64(&qword_18015DBA8, (signed __int64)v3, 0) )
      {
        CUser32Api::~CUser32Api(v3);
        operator delete(v3);
      }
    }
    if ( !qword_18015DBA8 )
      return -1;
  }
  if ( !CStackDlg::SwitchToInteractiveDesktop(this) )
    return -1;
  Library = LoadLibraryExW(L"comres.dll", 0, 2u);
  v5 = (*(__int64 (__fastcall **)(HMODULE, __int64, _QWORD, __int64 (__fastcall *)(HWND, unsigned int, unsigned __int64, __int64), _QWORD))(qword_18015DBA8 + 8))(
         Library,
         601,
         0,
         CStackDlg::StackDlgProc,
         *((_QWORD *)this + 1));
  FreeLibrary(Library);
  (*(void (__fastcall **)(_QWORD))(qword_18015DBA8 + 80))(*((_QWORD *)this + 5));
  (*(void (__fastcall **)(_QWORD))(qword_18015DBA8 + 112))(*((_QWORD *)this + 2));
  (*(void (__fastcall **)(_QWORD))(qword_18015DBA8 + 96))(*((_QWORD *)this + 6));
  (*(void (__fastcall **)(_QWORD))(qword_18015DBA8 + 128))(*((_QWORD *)this + 4));
  return v5;
}

```

## disassembly

```asm
0x180089b60  mov     [rsp+arg_0], rbx
0x180089b65  mov     [rsp+arg_10], rsi
0x180089b6a  push    rdi
0x180089b6b  sub     rsp, 30h
0x180089b6f  xor     edi, edi
0x180089b71  mov     rsi, rcx
0x180089b74  cmp     cs:qword_18015DBA8, rdi
0x180089b7b  jnz     short loc_180089BD2
0x180089b7d  mov     ecx, 88h; Size
0x180089b82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180089b87  mov     [rsp+38h+arg_8], rax
0x180089b8c  mov     rbx, rax
0x180089b8f  test    rax, rax
0x180089b92  jz      short loc_180089BC5
0x180089b94  mov     [rax], rdi
0x180089b97  test    rax, rax
0x180089b9a  jz      short loc_180089BC5
0x180089b9c  mov     rcx, rax; this
0x180089b9f  call    ?Initialize@CUser32Api@@QEAA_NXZ; CUser32Api::Initialize(void)
0x180089ba4  test    al, al
0x180089ba6  jz      short loc_180089BB5
0x180089ba8  xor     eax, eax
0x180089baa  lock cmpxchg cs:qword_18015DBA8, rbx
0x180089bb3  jz      short loc_180089BC5
0x180089bb5  mov     rcx, rbx; this
0x180089bb8  call    ??1CUser32Api@@QEAA@XZ; CUser32Api::~CUser32Api(void)
0x180089bbd  mov     rcx, rbx; Block
0x180089bc0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180089bc5  cmp     cs:qword_18015DBA8, rdi
0x180089bcc  jz      loc_180089C87
0x180089bd2  mov     rcx, rsi; this
0x180089bd5  call    ?SwitchToInteractiveDesktop@CStackDlg@@AEAAHXZ; CStackDlg::SwitchToInteractiveDesktop(void)
0x180089bda  test    eax, eax
0x180089bdc  jz      loc_180089C87
0x180089be2  xor     edx, edx; hFile
0x180089be4  lea     rcx, aComresDll_0; "comres.dll"
0x180089beb  lea     r8d, [rdx+2]; dwFlags
0x180089bef  call    cs:__imp_LoadLibraryExW
0x180089bf5  mov     rcx, cs:qword_18015DBA8
0x180089bfc  lea     r9, ?StackDlgProc@CStackDlg@@SA_JPEAUHWND__@@I_K_J@Z; CStackDlg::StackDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180089c03  mov     rbx, rax
0x180089c06  xor     r8d, r8d
0x180089c09  mov     edx, 259h
0x180089c0e  mov     rax, [rcx+8]
0x180089c12  mov     rcx, [rsi+8]
0x180089c16  mov     [rsp+38h+var_18], rcx
0x180089c1b  mov     rcx, rbx
0x180089c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c23  mov     rcx, rbx; hLibModule
0x180089c26  mov     rdi, rax
0x180089c29  call    cs:__imp_FreeLibrary
0x180089c2f  mov     rcx, cs:qword_18015DBA8
0x180089c36  mov     rax, [rcx+50h]
0x180089c3a  mov     rcx, [rsi+28h]
0x180089c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c43  mov     rcx, cs:qword_18015DBA8
0x180089c4a  mov     rax, [rcx+70h]
0x180089c4e  mov     rcx, [rsi+10h]
0x180089c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c57  mov     rax, cs:qword_18015DBA8
0x180089c5e  mov     rcx, [rsi+30h]
0x180089c62  mov     rax, [rax+60h]
0x180089c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c6b  mov     rax, cs:qword_18015DBA8
0x180089c72  mov     rcx, [rsi+20h]
0x180089c76  mov     rax, [rax+80h]
0x180089c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c82  mov     rax, rdi
0x180089c85  jmp     short loc_180089C8B
0x180089c87  or      rax, 0FFFFFFFFFFFFFFFFh
0x180089c8b  mov     rbx, [rsp+38h+arg_0]
0x180089c90  mov     rsi, [rsp+38h+arg_10]
0x180089c95  add     rsp, 30h
0x180089c99  pop     rdi
0x180089c9a  retn
```
