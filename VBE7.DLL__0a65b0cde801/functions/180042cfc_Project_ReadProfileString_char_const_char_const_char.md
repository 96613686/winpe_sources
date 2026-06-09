# Project::ReadProfileString(char const *,char const *,char * *)

- ea: `0x180042cfc`
- end: `0x180042faf`
- name: `?ReadProfileString@Project@@QEAAHPEBD0PEAPEAD@Z`
- size: `691`
- prototype: `__int64 __fastcall(Project *__hidden this, const char *, const char *, char **)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180046cb8`
- `0x18007918c`
- `0x18009846c`

## callees

- `0x180020c90`
- `0x180042cfc`
- `0x1800c2104`
- `0x1800c23fc`
- `0x1800c2428`
- `0x1800c24bc`
- `0x1800c2870`
- `0x1800c28fc`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!malloc` at `0x180042de7`
- `MSVCR100!malloc` at `0x180042f07`
- `MSVCR100!malloc` at `0x180042f59`
- `MSVCR100!malloc` at `0x180042de7`
- `MSVCR100!malloc` at `0x180042f07`
- `MSVCR100!malloc` at `0x180042f59`
- `MSVCR100!realloc` at `0x180042dae`
- `MSVCR100!realloc` at `0x180042eca`
- `MSVCR100!realloc` at `0x180042dae`
- `MSVCR100!realloc` at `0x180042eca`
- `MSVCR100!_msize` at `0x180042d88`
- `MSVCR100!_msize` at `0x180042ea3`
- `MSVCR100!_msize` at `0x180042d88`
- `MSVCR100!_msize` at `0x180042ea3`
- `KERNEL32!lstrlenA` at `0x180042d74`
- `KERNEL32!lstrlenA` at `0x180042ddc`
- `KERNEL32!lstrlenA` at `0x180042e90`
- `KERNEL32!lstrlenA` at `0x180042efc`
- `KERNEL32!lstrlenA` at `0x180042d74`
- `KERNEL32!lstrlenA` at `0x180042ddc`
- `KERNEL32!lstrlenA` at `0x180042e90`
- `KERNEL32!lstrlenA` at `0x180042efc`
- `KERNEL32!RaiseException` at `0x180042da2`
- `KERNEL32!RaiseException` at `0x180042ebe`
- `KERNEL32!RaiseException` at `0x180042da2`
- `KERNEL32!RaiseException` at `0x180042ebe`
- `KERNEL32!lstrcpyA` at `0x180042dff`
- `KERNEL32!lstrcpyA` at `0x180042dff`
- `KERNEL32!lstrcatA` at `0x180042dc6`
- `KERNEL32!lstrcatA` at `0x180042dd4`
- `KERNEL32!lstrcatA` at `0x180042e1f`
- `KERNEL32!lstrcatA` at `0x180042ee6`
- `KERNEL32!lstrcatA` at `0x180042ef4`
- `KERNEL32!lstrcatA` at `0x180042dc6`
- `KERNEL32!lstrcatA` at `0x180042dd4`
- `KERNEL32!lstrcatA` at `0x180042e1f`
- `KERNEL32!lstrcatA` at `0x180042ee6`
- `KERNEL32!lstrcatA` at `0x180042ef4`

## pseudocode

```c
__int64 __fastcall Project::ReadProfileString(Project *this, const char *a2, const char *a3, char **a4)
{
  CProjProfSection *v6; // rsi
  unsigned int v7; // ebp
  int v8; // eax
  void *v9; // r14
  const ULONG_PTR *v10; // r9
  char *v11; // rax
  char *v12; // rax
  struct CProjProfSection *Section; // rax
  CProjProfKeyVal *v15; // rsi
  unsigned int v16; // ebp
  int v17; // eax
  void *v18; // r14
  const ULONG_PTR *v19; // rax
  char *v20; // rax
  char *v21; // rax
  CProjProfKeyVal *Key; // rax
  CProjProfKeyVal *v23; // rsi
  int ValueLen; // eax
  char *v25; // rbp
  int v26; // eax
  unsigned int v27; // [rsp+20h] [rbp-158h]
  CHAR String[256]; // [rsp+30h] [rbp-148h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    Section = CProjProfiles::FindSection((Project *)((char *)this + 640), a2);
    if ( Section )
    {
      if ( !a3 )
      {
        v15 = (CProjProfKeyVal *)*((_QWORD *)Section + 2);
        if ( v15 )
        {
          v16 = v27;
          while ( CProjProfKeyVal::GetKeyName(v15, String, 0x100u) )
          {
            if ( *a4 )
            {
              v17 = lstrlenA(String);
              v18 = *a4;
              v16 += v17 + 1;
              v19 = (const ULONG_PTR *)_msize(*a4);
              if ( (const ULONG_PTR *)(unsigned int)v19 != v19 )
                RaiseException(0xC0000095, 1u, 1u, v19);
              v20 = (char *)realloc(v18, v16);
              if ( !v20 )
                return 0;
              *a4 = v20;
              lstrcatA(v20, " ");
              lstrcatA(*a4, String);
            }
            else
            {
              v16 = lstrlenA(String) + 1;
              v21 = (char *)malloc(v16);
              if ( !v21 )
                return 0;
              *a4 = v21;
              lstrncpyz(v21, String, v16);
            }
            v15 = (CProjProfKeyVal *)*((_QWORD *)v15 + 1);
            if ( !v15 )
              return 1;
          }
          return 0;
        }
        return 1;
      }
      Key = CProjProfSection::FindKey(Section, a3);
      v23 = Key;
      if ( Key )
      {
        ValueLen = CProjProfKeyVal::GetValueLen(Key);
        v25 = (char *)malloc((unsigned int)(ValueLen + 1));
        if ( v25 )
        {
          v26 = CProjProfKeyVal::GetValueLen(v23);
          if ( CProjProfKeyVal::GetValue((char **)v23, v25, v26 + 1) )
          {
            *a4 = v25;
            return 1;
          }
        }
      }
    }
    return 0;
  }
  v6 = (CProjProfSection *)*((_QWORD *)this + 81);
  if ( v6 )
  {
    v7 = v27;
    while ( CProjProfSection::GetTitle(v6, String, 0x100u) )
    {
      if ( *a4 )
      {
        v8 = lstrlenA(String);
        v9 = *a4;
        v7 += v8 + 3;
        v10 = (const ULONG_PTR *)_msize(*a4);
        if ( (const ULONG_PTR *)(unsigned int)v10 != v10 )
          RaiseException(0xC0000095, 1u, 1u, v10);
        v11 = (char *)realloc(v9, v7);
        if ( !v11 )
          return 0;
        *a4 = v11;
        lstrcatA(v11, " [");
        lstrcatA(*a4, String);
      }
      else
      {
        v7 = lstrlenA(String) + 3;
        v12 = (char *)malloc(v7);
        if ( !v12 )
          return 0;
        *a4 = v12;
        lstrcpyA(v12, "[");
        lstrncpyz(*a4, String, v7);
      }
      lstrcatA(*a4, "]");
      v6 = (CProjProfSection *)*((_QWORD *)v6 + 1);
      if ( !v6 )
        return 1;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180042cfc  push    rbx
0x180042cfe  push    rbp
0x180042cff  push    rsi
0x180042d00  push    rdi
0x180042d01  push    r14
0x180042d03  push    r15
0x180042d05  mov     eax, 148h
0x180042d0a  call    _alloca_probe
0x180042d0f  sub     rsp, rax
0x180042d12  mov     rax, cs:__security_cookie
0x180042d19  xor     rax, rsp
0x180042d1c  mov     [rsp+178h+var_48], rax
0x180042d24  and     qword ptr [r9], 0
0x180042d28  mov     rbx, r9
0x180042d2b  mov     rsi, r8
0x180042d2e  test    rdx, rdx
0x180042d31  jnz     loc_180042E3E
0x180042d37  mov     rsi, [rcx+288h]
0x180042d3e  lea     edi, [rdx+1]
0x180042d41  test    rsi, rsi
0x180042d44  jz      loc_180042F8D
0x180042d4a  mov     ebp, [rsp+178h+var_158]
0x180042d4e  lea     rdx, [rsp+178h+String]; char *
0x180042d53  mov     r8d, 100h; unsigned int
0x180042d59  mov     rcx, rsi; this
0x180042d5c  call    ?GetTitle@CProjProfSection@@QEAAKPEADK@Z; CProjProfSection::GetTitle(char *,ulong)
0x180042d61  test    eax, eax
0x180042d63  jz      loc_180042E37
0x180042d69  cmp     qword ptr [rbx], 0
0x180042d6d  lea     rcx, [rsp+178h+String]; lpString
0x180042d72  jz      short loc_180042DDC
0x180042d74  call    cs:__imp_lstrlenA
0x180042d7a  mov     r14, [rbx]
0x180042d7d  add     eax, 3
0x180042d80  mov     rcx, r14; Block
0x180042d83  add     ebp, eax
0x180042d85  mov     r15d, ebp
0x180042d88  call    cs:__imp__msize
0x180042d8e  mov     r9, rax; lpArguments
0x180042d91  mov     eax, eax
0x180042d93  cmp     rax, r9
0x180042d96  jz      short loc_180042DA8
0x180042d98  mov     r8d, edi; nNumberOfArguments
0x180042d9b  mov     edx, edi; dwExceptionFlags
0x180042d9d  mov     ecx, 0C0000095h; dwExceptionCode
0x180042da2  call    cs:__imp_RaiseException
0x180042da8  mov     rdx, r15; Size
0x180042dab  mov     rcx, r14; Block
0x180042dae  call    cs:__imp_realloc
0x180042db4  test    rax, rax
0x180042db7  jz      short loc_180042E37
0x180042db9  lea     rdx, asc_1803B318C; " ["
0x180042dc0  mov     rcx, rax; lpString1
0x180042dc3  mov     [rbx], rax
0x180042dc6  call    cs:__imp_lstrcatA
0x180042dcc  mov     rcx, [rbx]; lpString1
0x180042dcf  lea     rdx, [rsp+178h+String]; lpString2
0x180042dd4  call    cs:__imp_lstrcatA
0x180042dda  jmp     short loc_180042E15
0x180042ddc  call    cs:__imp_lstrlenA
0x180042de2  lea     ebp, [rax+3]
0x180042de5  mov     ecx, ebp; Size
0x180042de7  call    cs:__imp_malloc
0x180042ded  test    rax, rax
0x180042df0  jz      short loc_180042E37
0x180042df2  lea     rdx, asc_1803A40DC; "["
0x180042df9  mov     rcx, rax; lpString1
0x180042dfc  mov     [rbx], rax
0x180042dff  call    cs:__imp_lstrcpyA
0x180042e05  mov     rcx, [rbx]; char *
0x180042e08  lea     rdx, [rsp+178h+String]; char *
0x180042e0d  mov     r8d, ebp; unsigned int
0x180042e10  call    ?lstrncpyz@@YAIPEAD0I@Z; lstrncpyz(char *,char *,uint)
0x180042e15  mov     rcx, [rbx]; lpString1
0x180042e18  lea     rdx, asc_1803B3190; "]"
0x180042e1f  call    cs:__imp_lstrcatA
0x180042e25  mov     rsi, [rsi+8]
0x180042e29  test    rsi, rsi
0x180042e2c  jz      loc_180042F8D
0x180042e32  jmp     loc_180042D4E
0x180042e37  xor     eax, eax
0x180042e39  jmp     loc_180042F8F
0x180042e3e  add     rcx, 280h; this
0x180042e45  call    ?FindSection@CProjProfiles@@QEAAPEAVCProjProfSection@@PEBD@Z; CProjProfiles::FindSection(char const *)
0x180042e4a  test    rax, rax
0x180042e4d  jz      short loc_180042E37
0x180042e4f  mov     edi, 1
0x180042e54  test    rsi, rsi
0x180042e57  jnz     loc_180042F37
0x180042e5d  mov     rsi, [rax+10h]
0x180042e61  test    rsi, rsi
0x180042e64  jz      loc_180042F8D
0x180042e6a  mov     ebp, [rsp+178h+var_158]
0x180042e6e  lea     rdx, [rsp+178h+String]; char *
0x180042e73  mov     r8d, 100h; unsigned int
0x180042e79  mov     rcx, rsi; this
0x180042e7c  call    ?GetKeyName@CProjProfKeyVal@@QEAAKPEADK@Z; CProjProfKeyVal::GetKeyName(char *,ulong)
0x180042e81  test    eax, eax
0x180042e83  jz      short loc_180042E37
0x180042e85  cmp     qword ptr [rbx], 0
0x180042e89  lea     rcx, [rsp+178h+String]; lpString
0x180042e8e  jz      short loc_180042EFC
0x180042e90  call    cs:__imp_lstrlenA
0x180042e96  mov     r14, [rbx]
0x180042e99  inc     eax
0x180042e9b  mov     rcx, r14; Block
0x180042e9e  add     ebp, eax
0x180042ea0  mov     r15d, ebp
0x180042ea3  call    cs:__imp__msize
0x180042ea9  mov     r8d, eax
0x180042eac  cmp     r8, rax
0x180042eaf  jz      short loc_180042EC4
0x180042eb1  mov     r9, rax; lpArguments
0x180042eb4  mov     r8d, edi; nNumberOfArguments
0x180042eb7  mov     edx, edi; dwExceptionFlags
0x180042eb9  mov     ecx, 0C0000095h; dwExceptionCode
0x180042ebe  call    cs:__imp_RaiseException
0x180042ec4  mov     rdx, r15; Size
0x180042ec7  mov     rcx, r14; Block
0x180042eca  call    cs:__imp_realloc
0x180042ed0  test    rax, rax
0x180042ed3  jz      loc_180042E37
0x180042ed9  lea     rdx, asc_1803A37AC; " "
0x180042ee0  mov     rcx, rax; lpString1
0x180042ee3  mov     [rbx], rax
0x180042ee6  call    cs:__imp_lstrcatA
0x180042eec  mov     rcx, [rbx]; lpString1
0x180042eef  lea     rdx, [rsp+178h+String]; lpString2
0x180042ef4  call    cs:__imp_lstrcatA
0x180042efa  jmp     short loc_180042F29
0x180042efc  call    cs:__imp_lstrlenA
0x180042f02  lea     ebp, [rdi+rax]
0x180042f05  mov     ecx, ebp; Size
0x180042f07  call    cs:__imp_malloc
0x180042f0d  test    rax, rax
0x180042f10  jz      loc_180042E37
0x180042f16  lea     rdx, [rsp+178h+String]; char *
0x180042f1b  mov     r8d, ebp; unsigned int
0x180042f1e  mov     rcx, rax; char *
0x180042f21  mov     [rbx], rax
0x180042f24  call    ?lstrncpyz@@YAIPEAD0I@Z; lstrncpyz(char *,char *,uint)
0x180042f29  mov     rsi, [rsi+8]
0x180042f2d  test    rsi, rsi
0x180042f30  jz      short loc_180042F8D
0x180042f32  jmp     loc_180042E6E
0x180042f37  mov     rdx, rsi; char *
0x180042f3a  mov     rcx, rax; this
0x180042f3d  call    ?FindKey@CProjProfSection@@QEAAPEAVCProjProfKeyVal@@PEBD@Z; CProjProfSection::FindKey(char const *)
0x180042f42  mov     rsi, rax
0x180042f45  test    rax, rax
0x180042f48  jz      loc_180042E37
0x180042f4e  mov     rcx, rax; this
0x180042f51  call    ?GetValueLen@CProjProfKeyVal@@QEAAKXZ; CProjProfKeyVal::GetValueLen(void)
0x180042f56  lea     ecx, [rdi+rax]; Size
0x180042f59  call    cs:__imp_malloc
0x180042f5f  mov     rbp, rax
0x180042f62  test    rax, rax
0x180042f65  jz      loc_180042E37
0x180042f6b  mov     rcx, rsi; this
0x180042f6e  call    ?GetValueLen@CProjProfKeyVal@@QEAAKXZ; CProjProfKeyVal::GetValueLen(void)
0x180042f73  mov     rdx, rbp; char *
0x180042f76  mov     rcx, rsi; this
0x180042f79  lea     r8d, [rdi+rax]; unsigned int
0x180042f7d  call    ?GetValue@CProjProfKeyVal@@QEAAKPEADK@Z; CProjProfKeyVal::GetValue(char *,ulong)
0x180042f82  test    eax, eax
0x180042f84  jz      loc_180042E37
0x180042f8a  mov     [rbx], rbp
0x180042f8d  mov     eax, edi
0x180042f8f  mov     rcx, [rsp+178h+var_48]
0x180042f97  xor     rcx, rsp; StackCookie
0x180042f9a  call    __security_check_cookie
0x180042f9f  add     rsp, 148h
0x180042fa6  pop     r15
0x180042fa8  pop     r14
0x180042faa  pop     rdi
0x180042fab  pop     rsi
0x180042fac  pop     rbp
0x180042fad  pop     rbx
0x180042fae  retn
```
