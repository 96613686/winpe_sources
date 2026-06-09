# CreateTempFile

- ea: `0x18000a9f0`
- end: `0x18000ab6d`
- name: `CreateTempFile`
- size: `381`
- prototype: `__int64 __fastcall(char *, char *, CHAR **, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800015a0`
- `0x1800092d4`
- `0x180009378`
- `0x18000a9f0`
- `0x18000ab80`
- `0x180011fec`
- `0x180012fc0`
- `0x180014010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ab07`
- `KERNEL32!CloseHandle` at `0x18000ab07`
- `KERNEL32!DeleteFileW` at `0x18000ab10`
- `KERNEL32!DeleteFileW` at `0x18000ab10`

## pseudocode

```c
__int64 __fastcall CreateTempFile(char *a1, char *a2, CHAR **a3, _QWORD *a4)
{
  unsigned int v8; // r9d
  __int64 v9; // rsi
  __int64 v10; // r8
  int appended; // edi
  WCHAR *v12; // rcx
  CHAR *v13; // rax
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v18[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v19[264]; // [rsp+280h] [rbp+180h] BYREF

  STRW::STRW((STRW *)&v16, v18, 0x104u);
  STRW::STRW((STRW *)&v15, v19, 0x104u);
  v9 = -1;
  if ( !a1 )
    goto LABEL_17;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  appended = STRW::AppendA_CCH_CP((STRW *)&v16, a1, v10, v8);
  if ( appended >= 0 )
  {
LABEL_17:
    if ( !a2 )
      goto LABEL_8;
    do
      ++v9;
    while ( a2[v9] );
    appended = STRW::AppendA_CCH_CP((STRW *)&v15, a2, v9, v8);
    if ( appended >= 0 )
    {
LABEL_8:
      v12 = (WCHAR *)&ExistingFileName;
      if ( v16 )
        v12 = v17;
      appended = CreateTempFileW(v12);
      if ( appended >= 0 )
      {
        v13 = PszToANSI(0, 0);
        *a3 = v13;
        if ( v13 )
        {
          *a4 = -1;
        }
        else
        {
          CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
          DeleteFileW(0);
          appended = -2147024882;
        }
      }
    }
  }
  STRW::~STRW((STRW *)&v15);
  STRW::~STRW((STRW *)&v16);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000a9f0  push    rbp
0x18000a9f2  push    rbx
0x18000a9f3  push    rsi
0x18000a9f4  push    rdi
0x18000a9f5  push    r12
0x18000a9f7  push    r14
0x18000a9f9  push    r15
0x18000a9fb  lea     rbp, [rsp-3A0h]
0x18000aa03  sub     rsp, 4A0h
0x18000aa0a  mov     rax, cs:__security_cookie
0x18000aa11  xor     rax, rsp
0x18000aa14  mov     [rbp+3D0h+var_40], rax
0x18000aa1b  mov     r12, r8
0x18000aa1e  mov     rdi, rcx
0x18000aa21  mov     ebx, 104h
0x18000aa26  lea     rcx, [rsp+4D0h+var_480]; this
0x18000aa2b  mov     r14, rdx
0x18000aa2e  mov     r8d, ebx; unsigned int
0x18000aa31  lea     rdx, [rsp+4D0h+var_460]; unsigned __int16 *
0x18000aa36  mov     r15, r9
0x18000aa39  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000aa3e  mov     r8d, ebx; unsigned int
0x18000aa41  lea     rcx, [rsp+4D0h+var_4A0]; this
0x18000aa46  lea     rdx, [rbp+3D0h+var_250]; unsigned __int16 *
0x18000aa4d  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000aa52  xor     ebx, ebx
0x18000aa54  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000aa58  mov     [rsp+4D0h+lpFileName], rbx
0x18000aa5d  mov     [rsp+4D0h+hObject], rsi
0x18000aa62  test    rdi, rdi
0x18000aa65  jz      short loc_18000AA8A
0x18000aa67  mov     r8, rsi
0x18000aa6a  inc     r8; unsigned int
0x18000aa6d  cmp     [rdi+r8], bl
0x18000aa71  jnz     short loc_18000AA6A
0x18000aa73  mov     rdx, rdi; char *
0x18000aa76  lea     rcx, [rsp+4D0h+var_480]; this
0x18000aa7b  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000aa80  mov     edi, eax
0x18000aa82  test    eax, eax
0x18000aa84  js      loc_18000AB1B
0x18000aa8a  test    r14, r14
0x18000aa8d  jz      short loc_18000AAB2
0x18000aa8f  inc     rsi
0x18000aa92  cmp     [r14+rsi], bl
0x18000aa96  jnz     short loc_18000AA8F
0x18000aa98  mov     r8d, esi; unsigned int
0x18000aa9b  lea     rcx, [rsp+4D0h+var_4A0]; this
0x18000aaa0  mov     rdx, r14; char *
0x18000aaa3  call    ?AppendA_CCH_CP@STRW@@QEAAJPEBDKI@Z; STRW::AppendA_CCH_CP(char const *,ulong,uint)
0x18000aaa8  mov     edi, eax
0x18000aaaa  test    eax, eax
0x18000aaac  js      loc_18000AB36
0x18000aab2  cmp     [rsp+4D0h+var_4A0], ebx
0x18000aab6  lea     rcx, ExistingFileName
0x18000aabd  mov     rdx, rcx
0x18000aac0  lea     r9, [rsp+4D0h+hObject]
0x18000aac5  cmovnz  rdx, [rsp+4D0h+var_498]
0x18000aacb  lea     r8, [rsp+4D0h+lpFileName]
0x18000aad0  cmp     [rsp+4D0h+var_480], ebx
0x18000aad4  cmovnz  rcx, [rsp+4D0h+var_478]; unsigned __int16 *
0x18000aada  call    CreateTempFileW
0x18000aadf  mov     rbx, [rsp+4D0h+lpFileName]
0x18000aae4  mov     edi, eax
0x18000aae6  test    eax, eax
0x18000aae8  js      short loc_18000AB1B
0x18000aaea  mov     rdx, rbx; lpWideCharStr
0x18000aaed  xor     ecx, ecx; CodePage
0x18000aaef  call    PszToANSI
0x18000aaf4  mov     rcx, [rsp+4D0h+hObject]; hObject
0x18000aaf9  mov     [r12], rax
0x18000aafd  test    rax, rax
0x18000ab00  jz      short loc_18000AB07
0x18000ab02  mov     [r15], rcx
0x18000ab05  jmp     short loc_18000AB1B
0x18000ab07  call    cs:__imp_CloseHandle
0x18000ab0d  mov     rcx, rbx; lpFileName
0x18000ab10  call    cs:__imp_DeleteFileW
0x18000ab16  mov     edi, 8007000Eh
0x18000ab1b  test    rbx, rbx
0x18000ab1e  jz      short loc_18000AB36
0x18000ab20  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000ab27  mov     rdx, rbx
0x18000ab2a  mov     rax, [rcx]
0x18000ab2d  mov     rax, [rax+28h]
0x18000ab31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab36  lea     rcx, [rsp+4D0h+var_4A0]; this
0x18000ab3b  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000ab40  lea     rcx, [rsp+4D0h+var_480]; this
0x18000ab45  call    ??1STRW@@QEAA@XZ; STRW::~STRW(void)
0x18000ab4a  mov     eax, edi
0x18000ab4c  mov     rcx, [rbp+3D0h+var_40]
0x18000ab53  xor     rcx, rsp; StackCookie
0x18000ab56  call    __security_check_cookie
0x18000ab5b  add     rsp, 4A0h
0x18000ab62  pop     r15
0x18000ab64  pop     r14
0x18000ab66  pop     r12
0x18000ab68  pop     rdi
0x18000ab69  pop     rsi
0x18000ab6a  pop     rbx
0x18000ab6b  pop     rbp
0x18000ab6c  retn
```
