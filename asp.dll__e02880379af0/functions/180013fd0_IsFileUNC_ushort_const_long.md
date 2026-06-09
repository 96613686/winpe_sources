# IsFileUNC(ushort const *,long &)

- ea: `0x180013fd0`
- end: `0x18001408b`
- name: `?IsFileUNC@@YAHPEBGAEAJ@Z`
- size: `187`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013d7c`
- `0x18001650c`

## callees

- `0x180013fd0`
- `0x180023d86`
- `0x180023dd0`
- `0x180062344`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180014050`
- `msvcrt!_wcsnicmp` at `0x180014050`
- `KERNEL32!SetLastError` at `0x18002c023`
- `KERNEL32!SetLastError` at `0x18002c023`
- `iisutil!MakePathCanonicalizationProof` at `0x180014025`
- `iisutil!MakePathCanonicalizationProof` at `0x180014025`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014062`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180014062`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001403a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001403a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014017`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180014017`

## pseudocode

```c
_BOOL8 __fastcall IsFileUNC(const unsigned __int16 *a1, int *a2)
{
  int PathCanonicalizationProof; // eax
  const wchar_t *Str; // rax
  BOOL v6; // ebx
  DWORD v8; // eax
  _BYTE v9[64]; // [rsp+20h] [rbp-268h] BYREF
  unsigned __int16 v10[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(v10, 0, 0x208u);
  STRU::STRU((STRU *)v9, v10, 0x104u);
  PathCanonicalizationProof = MakePathCanonicalizationProof(a1, (struct STRU *)v9);
  *a2 = PathCanonicalizationProof;
  if ( PathCanonicalizationProof < 0 )
  {
    v8 = WIN32_FROM_HRESULT(PathCanonicalizationProof);
    SetLastError(v8);
    v6 = 1;
  }
  else
  {
    Str = STRU::QueryStr((STRU *)v9);
    v6 = _wcsnicmp(Str, L"\\\\?\\UNC\\", 8u) == 0;
  }
  STRU::~STRU((STRU *)v9);
  return v6;
}

```

## disassembly

```asm
0x180013fd0  mov     [rsp+arg_10], rbx
0x180013fd5  push    rdi
0x180013fd6  sub     rsp, 280h
0x180013fdd  mov     rax, cs:__security_cookie
0x180013fe4  xor     rax, rsp
0x180013fe7  mov     [rsp+288h+var_18], rax
0x180013fef  mov     rdi, rdx
0x180013ff2  mov     rbx, rcx
0x180013ff5  xor     edx, edx; Val
0x180013ff7  lea     rcx, [rsp+288h+var_228]; void *
0x180013ffc  mov     r8d, 208h; Size
0x180014002  call    memset_0
0x180014007  mov     r8d, 104h
0x18001400d  lea     rdx, [rsp+288h+var_228]
0x180014012  lea     rcx, [rsp+288h+var_268]
0x180014017  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001401d  lea     rdx, [rsp+288h+var_268]
0x180014022  mov     rcx, rbx
0x180014025  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18001402b  mov     [rdi], eax
0x18001402d  test    eax, eax
0x18001402f  js      loc_18002C01A
0x180014035  lea     rcx, [rsp+288h+var_268]
0x18001403a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180014040  mov     r8d, 8; MaxCount
0x180014046  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x18001404d  mov     rcx, rax; String1
0x180014050  call    cs:__imp__wcsnicmp
0x180014056  xor     ebx, ebx
0x180014058  test    eax, eax
0x18001405a  setz    bl
0x18001405d  lea     rcx, [rsp+288h+var_268]
0x180014062  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180014068  mov     eax, ebx
0x18001406a  mov     rcx, [rsp+288h+var_18]
0x180014072  xor     rcx, rsp; StackCookie
0x180014075  call    __security_check_cookie
0x18001407a  mov     rbx, [rsp+288h+arg_10]
0x180014082  add     rsp, 280h
0x180014089  pop     rdi
0x18001408a  retn
0x18002c01a  mov     ecx, eax; int
0x18002c01c  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18002c021  mov     ecx, eax; dwErrCode
0x18002c023  call    cs:__imp_SetLastError
0x18002c029  mov     ebx, 1
0x18002c02e  jmp     loc_18001405D
```
