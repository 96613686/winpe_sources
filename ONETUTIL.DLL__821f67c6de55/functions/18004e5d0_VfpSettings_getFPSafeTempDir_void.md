# VfpSettings::getFPSafeTempDir(void)

- ea: `0x18004e5d0`
- end: `0x18004e7f3`
- name: `?getFPSafeTempDir@VfpSettings@@SA?AVVstring@@XZ`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800920c0`
- `0x1800c83e0`

## callees

- `0x180040c10`
- `0x18004e380`
- `0x18004e5d0`
- `0x1800838f0`
- `0x180090610`
- `0x180092190`
- `0x1800938a0`
- `0x180095100`
- `0x180133d30`
- `0x180134070`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6e7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e76f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e7c1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e6e7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e76f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18004e7c1`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18004e63c`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18004e63c`

## string_xrefs

- `0x18004e654`: `WebTempDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall VfpSettings::getFPSafeTempDir(_QWORD *a1)
{
  int *v2; // rcx
  int *v3; // rcx
  struct Vstatus *DirTree; // rax
  int *v5; // rcx
  Vstring *FPTempDir; // rax
  int *v7; // rcx
  __int64 v9; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v10; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v11[3]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v12[4]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+78h] [rbp-90h] BYREF

  v12[1] = -2;
  v12[2] = a1;
  *a1 = dword_1802AFD5C;
  _InterlockedIncrement(&dword_1802AFD50);
  if ( SHGetSpecialFolderPathW(0, pszPath, 32, 0) )
  {
    RWCString::RWCString((RWCString *)&v10, "WebTempDir");
    Vstring::Vstring((Vstring *)&v9, pszPath);
    Vpath::Vpath((Vpath *)v11, (const struct Vstring *)&v9, (const struct Vstring *)&v10, Class);
    v2 = (int *)(v9 - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v9 - 12)) && v2 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v2);
      else
        free(v2);
    }
    v3 = (int *)(v10 - 12);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v10 - 12)) && v3 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v3);
      else
        free(v3);
    }
    if ( Vpath::isDir((Vpath *)v11) || (DirTree = Vpath::createDirTree((Vpath *)v11, 0, 0)) == 0 )
      RWCString::operator=(a1, v11);
    else
      (**(void (__fastcall ***)(struct Vstatus *, __int64))DirTree)(DirTree, 1);
    Vpath::ClearStat((Vpath *)v11);
    v12[3] = v11;
    v5 = (int *)(v11[0] - 12LL);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v11[0] - 12LL)) && v5 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v5);
      else
        free(v5);
    }
  }
  if ( !*(_DWORD *)(*a1 - 4LL) )
  {
    FPTempDir = VfpSettings::getFPTempDir((Vstring *)v12, 1);
    RWCString::operator=(a1, FPTempDir);
    v7 = (int *)(v12[0] - 12LL);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v12[0] - 12LL)) && v7 != &dword_1802AFD50 )
    {
      if ( dword_1802B0018 )
        COWSAllocator::Free(v7);
      else
        free(v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004e5d0  mov     rax, rsp
0x18004e5d3  push    rbp
0x18004e5d4  lea     rbp, [rax-198h]
0x18004e5db  sub     rsp, 290h
0x18004e5e2  mov     [rsp+290h+var_238], 0FFFFFFFFFFFFFFFEh
0x18004e5eb  mov     [rax+10h], rbx
0x18004e5ef  mov     [rax+18h], rsi
0x18004e5f3  mov     [rax+20h], r14
0x18004e5f7  mov     rax, cs:__security_cookie
0x18004e5fe  xor     rax, rsp
0x18004e601  mov     [rbp+190h+var_10], rax
0x18004e608  mov     rbx, rcx
0x18004e60b  mov     [rsp+290h+var_230], rcx
0x18004e610  and     dword ptr [rsp+290h+var_270], 0
0x18004e615  lea     rax, dword_1802AFD5C
0x18004e61c  mov     [rcx], rax
0x18004e61f  lock inc cs:dword_1802AFD50
0x18004e626  mov     dword ptr [rsp+290h+var_270], 1
0x18004e62e  xor     r9d, r9d; fCreate
0x18004e631  lea     r8d, [r9+20h]; csidl
0x18004e635  lea     rdx, [rsp+290h+pszPath]; pszPath
0x18004e63a  xor     ecx, ecx; hwnd
0x18004e63c  call    cs:SHGetSpecialFolderPathW
0x18004e642  or      esi, 0FFFFFFFFh
0x18004e645  lea     r14, dword_1802AFD50
0x18004e64c  test    eax, eax
0x18004e64e  jz      loc_18004E775
0x18004e654  lea     rdx, aWebtempdir; "WebTempDir"
0x18004e65b  lea     rcx, [rsp+290h+var_260]; this
0x18004e660  call    ??0RWCString@@QEAA@PEBD@Z; RWCString::RWCString(char const *)
0x18004e665  nop
0x18004e666  lea     rdx, [rsp+290h+pszPath]; wchar_t *
0x18004e66b  lea     rcx, [rsp+290h+var_268]; this
0x18004e670  call    ??0Vstring@@QEAA@PEB_W@Z; Vstring::Vstring(wchar_t const *)
0x18004e675  nop
0x18004e676  lea     r9, Class; char *
0x18004e67d  lea     r8, [rsp+290h+var_260]; struct Vstring *
0x18004e682  lea     rdx, [rsp+290h+var_268]; struct Vstring *
0x18004e687  lea     rcx, [rsp+290h+var_258]; this
0x18004e68c  call    ??0Vpath@@QEAA@AEBVVstring@@0PEBD@Z; Vpath::Vpath(Vstring const &,Vstring const &,char const *)
0x18004e691  nop
0x18004e692  mov     rcx, [rsp+290h+var_268]
0x18004e697  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e69b  mov     eax, esi
0x18004e69d  lock xadd [rcx], eax
0x18004e6a1  add     eax, esi
0x18004e6a3  jnz     short loc_18004E6C0
0x18004e6a5  cmp     rcx, r14
0x18004e6a8  jz      short loc_18004E6C0
0x18004e6aa  cmp     cs:dword_1802B0018, eax
0x18004e6b0  jz      short loc_18004E6B9
0x18004e6b2  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e6b7  jmp     short loc_18004E6C0
0x18004e6b9  call    cs:free
0x18004e6bf  nop
0x18004e6c0  mov     rcx, [rsp+290h+var_260]
0x18004e6c5  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e6c9  mov     eax, esi
0x18004e6cb  lock xadd [rcx], eax
0x18004e6cf  add     eax, esi
0x18004e6d1  jnz     short loc_18004E6ED
0x18004e6d3  cmp     rcx, r14
0x18004e6d6  jz      short loc_18004E6ED
0x18004e6d8  cmp     cs:dword_1802B0018, eax
0x18004e6de  jz      short loc_18004E6E7
0x18004e6e0  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e6e5  jmp     short loc_18004E6ED
0x18004e6e7  call    cs:free
0x18004e6ed  lea     rcx, [rsp+290h+var_258]; this
0x18004e6f2  call    ?isDir@Vpath@@QEAADXZ; Vpath::isDir(void)
0x18004e6f7  test    al, al
0x18004e6f9  jnz     short loc_18004E725
0x18004e6fb  xor     r8d, r8d; unsigned int *
0x18004e6fe  xor     edx, edx; struct Vstring *
0x18004e700  lea     rcx, [rsp+290h+var_258]; this
0x18004e705  call    ?createDirTree@Vpath@@QEAAPEAVVstatus@@PEAVVstring@@PEAK@Z; Vpath::createDirTree(Vstring *,ulong *)
0x18004e70a  mov     rcx, rax
0x18004e70d  test    rax, rax
0x18004e710  jz      short loc_18004E725
0x18004e712  mov     rax, [rax]
0x18004e715  mov     edx, 1
0x18004e71a  mov     rax, [rax]
0x18004e71d  call    cs:__guard_dispatch_icall_fptr
0x18004e723  jmp     short loc_18004E733
0x18004e725  lea     rdx, [rsp+290h+var_258]
0x18004e72a  mov     rcx, rbx
0x18004e72d  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004e732  nop
0x18004e733  lea     rcx, [rsp+290h+var_258]; this
0x18004e738  call    ?ClearStat@Vpath@@QEAAXXZ; Vpath::ClearStat(void)
0x18004e73d  nop
0x18004e73e  lea     rax, [rsp+290h+var_258]
0x18004e743  mov     qword ptr [rsp+290h+var_228], rax
0x18004e748  mov     rcx, [rsp+290h+var_258]
0x18004e74d  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e751  mov     eax, esi
0x18004e753  lock xadd [rcx], eax
0x18004e757  add     eax, esi
0x18004e759  jnz     short loc_18004E775
0x18004e75b  cmp     rcx, r14
0x18004e75e  jz      short loc_18004E775
0x18004e760  cmp     cs:dword_1802B0018, eax
0x18004e766  jz      short loc_18004E76F
0x18004e768  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e76d  jmp     short loc_18004E775
0x18004e76f  call    cs:free
0x18004e775  mov     rax, [rbx]
0x18004e778  cmp     dword ptr [rax-4], 0
0x18004e77c  jnz     short loc_18004E7C7
0x18004e77e  mov     edx, 1
0x18004e783  lea     rcx, [rsp+290h+var_240]
0x18004e788  call    ?getFPTempDir@VfpSettings@@SA?AVVstring@@W4Vencoding@@@Z; VfpSettings::getFPTempDir(Vencoding)
0x18004e78d  nop
0x18004e78e  mov     rdx, rax
0x18004e791  mov     rcx, rbx
0x18004e794  call    ??4RWCString@@QEAAAEAV0@AEBV0@@Z; RWCString::operator=(RWCString const &)
0x18004e799  nop
0x18004e79a  mov     rcx, [rsp+290h+var_240]
0x18004e79f  add     rcx, 0FFFFFFFFFFFFFFF4h; void *
0x18004e7a3  mov     eax, esi
0x18004e7a5  lock xadd [rcx], eax
0x18004e7a9  add     eax, esi
0x18004e7ab  jnz     short loc_18004E7C7
0x18004e7ad  cmp     rcx, r14
0x18004e7b0  jz      short loc_18004E7C7
0x18004e7b2  cmp     cs:dword_1802B0018, eax
0x18004e7b8  jz      short loc_18004E7C1
0x18004e7ba  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18004e7bf  jmp     short loc_18004E7C7
0x18004e7c1  call    cs:free
0x18004e7c7  mov     rax, rbx
0x18004e7ca  mov     rcx, [rbp+190h+var_10]
0x18004e7d1  xor     rcx, rsp
0x18004e7d4  call    sub_1801503E0
0x18004e7d9  lea     r11, [rsp+290h+var_s0]
0x18004e7e1  mov     rbx, [r11+18h]
0x18004e7e5  mov     rsi, [r11+20h]
0x18004e7e9  mov     r14, [r11+28h]
0x18004e7ed  mov     rsp, r11
0x18004e7f0  pop     rbp
0x18004e7f1  retn
```
