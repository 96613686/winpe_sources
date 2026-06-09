# ReadWildcards(String const &)

- ea: `0x180009530`
- end: `0x1800096b6`
- name: `?ReadWildcards@@YAXAEBVString@@@Z`
- size: `390`
- prototype: `void __fastcall(const struct String *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008e40`

## callees

- `0x180002498`
- `0x180009530`
- `0x1800097a8`
- `0x1800099f8`
- `0x180009ab4`

## import_xrefs

- `msvcrt!strpbrk` at `0x1800095fc`
- `msvcrt!strpbrk` at `0x1800095fc`
- `msvcrt!free` at `0x1800095ae`
- `msvcrt!free` at `0x180009693`
- `msvcrt!free` at `0x1800095ae`
- `msvcrt!free` at `0x180009693`
- `KERNEL32!ReleaseMutex` at `0x1800096a0`
- `KERNEL32!ReleaseMutex` at `0x1800096a0`
- `KERNEL32!GetPrivateProfileSectionNamesA` at `0x180009598`
- `KERNEL32!GetPrivateProfileSectionNamesA` at `0x1800095db`
- `KERNEL32!GetPrivateProfileSectionNamesA` at `0x180009598`
- `KERNEL32!GetPrivateProfileSectionNamesA` at `0x1800095db`
- `KERNEL32!WaitForMultipleObjects` at `0x180009557`
- `KERNEL32!WaitForMultipleObjects` at `0x180009557`
- `USER32!CharNextA` at `0x180009671`
- `USER32!CharNextA` at `0x180009671`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ReadWildcards(const struct String *a1)
{
  unsigned __int64 v2; // rdi
  CHAR *v3; // rax
  LPSTR v4; // rbx
  DWORD PrivateProfileSectionNamesA; // ecx
  CHAR *v6; // rax
  LPSTR v7; // rdi
  bool v8; // r8
  _BYTE *v9; // rcx
  __int64 v10; // rax
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  WaitForMultipleObjects(2u, &Handles, 1, 0xFFFFFFFF);
  if ( qword_180012980 == qword_180012978 )
  {
    LODWORD(v2) = 0x4000;
    v3 = (CHAR *)operator new(0x4000u);
    v4 = v3;
    if ( !v3 )
      return;
    *v3 = 0;
    PrivateProfileSectionNamesA = GetPrivateProfileSectionNamesA(v3, 0x4000u, *(LPCSTR *)(*(_QWORD *)a1 + 32LL));
    if ( PrivateProfileSectionNamesA == 16382 )
    {
      do
      {
        if ( !PrivateProfileSectionNamesA )
          break;
        free(v4);
        v2 = (unsigned int)(2 * v2);
        v6 = (CHAR *)operator new(v2);
        v4 = v6;
        if ( !v6 )
          return;
        *v6 = 0;
        PrivateProfileSectionNamesA = GetPrivateProfileSectionNamesA(v6, v2, *(LPCSTR *)(*(_QWORD *)a1 + 32LL));
      }
      while ( PrivateProfileSectionNamesA == (_DWORD)v2 - 2 );
    }
    v7 = v4;
    while ( *v4 )
    {
      if ( strpbrk(v4, "[*?") )
      {
        String::String((String *)v11, v4, v8);
        v9 = qword_180012980;
        if ( (((_BYTE *)qword_180012980 - (_BYTE *)qword_180012978) >> 4) + 1 >= (unsigned __int64)qword_180012970 )
        {
          TVector<String>::growSpace();
          v9 = qword_180012980;
        }
        v10 = v11[0];
        *(_QWORD *)v9 = v11[0];
        if ( v10 )
          _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
        v9[8] = 1;
        qword_180012980 = (char *)qword_180012980 + 16;
        TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v11);
      }
      for ( ; *v4; v4 = CharNextA(v4) )
        ;
      ++v4;
    }
    if ( v7 )
      free(v7);
  }
  ReleaseMutex(hMutex);
}

```

## disassembly

```asm
0x180009530  mov     [rsp+arg_0], rbx
0x180009535  mov     [rsp+arg_8], rsi
0x18000953a  push    rdi
0x18000953b  sub     rsp, 30h
0x18000953f  mov     rsi, rcx
0x180009542  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180009546  mov     r8d, 1; bWaitAll
0x18000954c  lea     rdx, Handles; lpHandles
0x180009553  lea     ecx, [r8+1]; nCount
0x180009557  call    cs:__imp_WaitForMultipleObjects
0x18000955d  mov     rax, cs:qword_180012980
0x180009564  cmp     rax, cs:qword_180012978
0x18000956b  jnz     loc_180009699
0x180009571  mov     edi, 4000h
0x180009576  mov     ecx, edi; unsigned __int64
0x180009578  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000957d  mov     rbx, rax
0x180009580  test    rax, rax
0x180009583  jz      loc_1800096A6
0x180009589  mov     byte ptr [rax], 0
0x18000958c  mov     r8, [rsi]
0x18000958f  mov     r8, [r8+20h]; lpFileName
0x180009593  mov     edx, edi; nSize
0x180009595  mov     rcx, rax; lpszReturnBuffer
0x180009598  call    cs:__imp_GetPrivateProfileSectionNamesA
0x18000959e  mov     ecx, eax
0x1800095a0  cmp     eax, 3FFEh
0x1800095a5  jnz     short loc_1800095EA
0x1800095a7  test    ecx, ecx
0x1800095a9  jz      short loc_1800095EA
0x1800095ab  mov     rcx, rbx; Block
0x1800095ae  call    cs:__imp_free
0x1800095b4  lea     eax, [rdi+rdi]
0x1800095b7  mov     edi, eax
0x1800095b9  mov     ecx, eax; unsigned __int64
0x1800095bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800095c0  mov     rbx, rax
0x1800095c3  test    rax, rax
0x1800095c6  jz      loc_1800096A6
0x1800095cc  mov     byte ptr [rax], 0
0x1800095cf  mov     r8, [rsi]
0x1800095d2  mov     r8, [r8+20h]; lpFileName
0x1800095d6  mov     edx, edi; nSize
0x1800095d8  mov     rcx, rax; lpszReturnBuffer
0x1800095db  call    cs:__imp_GetPrivateProfileSectionNamesA
0x1800095e1  mov     ecx, eax
0x1800095e3  lea     eax, [rdi-2]
0x1800095e6  cmp     ecx, eax
0x1800095e8  jz      short loc_1800095A7
0x1800095ea  mov     rdi, rbx
0x1800095ed  jmp     loc_180009682
0x1800095f2  lea     rdx, Control; "[*?"
0x1800095f9  mov     rcx, rbx; Str
0x1800095fc  call    cs:__imp_strpbrk
0x180009602  test    rax, rax
0x180009605  jz      short loc_180009669
0x180009607  mov     rdx, rbx; char *
0x18000960a  lea     rcx, [rsp+38h+var_18]; this
0x18000960f  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x180009614  nop
0x180009615  mov     rcx, cs:qword_180012980
0x18000961c  mov     rax, rcx
0x18000961f  sub     rax, cs:qword_180012978
0x180009626  sar     rax, 4
0x18000962a  inc     rax
0x18000962d  cmp     rax, cs:qword_180012970
0x180009634  jb      short loc_180009642
0x180009636  call    ?growSpace@?$TVector@VString@@@@AEAAX_K@Z; TVector<String>::growSpace(unsigned __int64)
0x18000963b  mov     rcx, cs:qword_180012980
0x180009642  mov     rax, [rsp+38h+var_18]
0x180009647  mov     [rcx], rax
0x18000964a  test    rax, rax
0x18000964d  jz      short loc_180009653
0x18000964f  lock inc dword ptr [rax+8]
0x180009653  mov     byte ptr [rcx+8], 1
0x180009657  add     cs:qword_180012980, 10h
0x18000965f  lea     rcx, [rsp+38h+var_18]
0x180009664  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180009669  cmp     byte ptr [rbx], 0
0x18000966c  jz      short loc_18000967F
0x18000966e  mov     rcx, rbx; lpsz
0x180009671  call    cs:__imp_CharNextA
0x180009677  mov     rbx, rax
0x18000967a  cmp     byte ptr [rax], 0
0x18000967d  jnz     short loc_18000966E
0x18000967f  inc     rbx
0x180009682  cmp     byte ptr [rbx], 0
0x180009685  jnz     loc_1800095F2
0x18000968b  test    rdi, rdi
0x18000968e  jz      short loc_180009699
0x180009690  mov     rcx, rdi; Block
0x180009693  call    cs:__imp_free
0x180009699  mov     rcx, cs:hMutex; hMutex
0x1800096a0  call    cs:__imp_ReleaseMutex
0x1800096a6  mov     rbx, [rsp+38h+arg_0]
0x1800096ab  mov     rsi, [rsp+38h+arg_8]
0x1800096b0  add     rsp, 30h
0x1800096b4  pop     rdi
0x1800096b5  retn
```
