# ForbidBinDir(_HTTP_FILTER_CONTEXT *,_HTTP_FILTER_URL_MAP_EX *)

- ea: `0x18000120c`
- end: `0x180001330`
- name: `?ForbidBinDir@@YAKPEAU_HTTP_FILTER_CONTEXT@@PEAU_HTTP_FILTER_URL_MAP_EX@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, struct _HTTP_FILTER_URL_MAP_EX *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001ba0`

## callees

- `0x18000120c`
- `0x180001430`
- `0x180001568`
- `0x1800038f0`
- `0x180003950`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800012cc`
- `KERNEL32!lstrlenA` at `0x1800012cc`
- `KERNEL32!SetLastError` at `0x18000129c`
- `KERNEL32!SetLastError` at `0x18000129c`
- `KERNEL32!GetLastError` at `0x180001272`
- `KERNEL32!GetLastError` at `0x180001272`

## string_xrefs

- `0x180001261`: `APPL_MD_PATH`
- `0x1800012b5`: `APPL_MD_PATH`

## pseudocode

```c
__int64 __fastcall ForbidBinDir(struct _HTTP_FILTER_CONTEXT *a1, struct _HTTP_FILTER_URL_MAP_EX *a2)
{
  bool v2; // zf
  char *v3; // rbx
  __int64 v6; // rax
  DWORD v7; // ecx
  char *v9; // rax
  _DWORD v10[4]; // [rsp+30h] [rbp-1028h] BYREF
  CHAR String[4096]; // [rsp+40h] [rbp-1018h] BYREF

  v2 = (a2->dwFlags & 4) == 0;
  v3 = String;
  v10[0] = 4096;
  if ( v2 )
  {
    if ( !((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, CHAR *, _DWORD *))a1->GetServerVariable)(
            a1,
            "APPL_MD_PATH",
            String,
            v10) )
    {
      if ( GetLastError() != 122 )
        return 134217732;
      v6 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, v10[0], 0);
      v3 = (char *)v6;
      if ( !v6 )
      {
        v7 = 14;
LABEL_6:
        SetLastError(v7);
        return 134217732;
      }
      if ( !((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, _DWORD *))a1->GetServerVariable)(
              a1,
              "APPL_MD_PATH",
              v6,
              v10) )
        return 134217732;
    }
    if ( lstrlenA(v3) )
    {
      v9 = RemoveAppPrefix((char *)a2->pszURL, v3);
      if ( v9 )
      {
        if ( *v9 == 47 && (unsigned int)PathMatches(v9 + 1, "bin") )
        {
          v7 = 2;
          goto LABEL_6;
        }
      }
    }
  }
  return 134217730;
}

```

## disassembly

```asm
0x18000120c  mov     [rsp+arg_10], rbx
0x180001211  mov     [rsp+arg_18], rsi
0x180001216  push    rdi
0x180001217  mov     eax, 1050h
0x18000121c  call    _alloca_probe
0x180001221  sub     rsp, rax
0x180001224  mov     rax, cs:__security_cookie
0x18000122b  xor     rax, rsp
0x18000122e  mov     [rsp+1058h+var_18], rax
0x180001236  test    byte ptr [rdx+14h], 4
0x18000123a  lea     rbx, [rsp+1058h+String]
0x18000123f  mov     rsi, rdx
0x180001242  mov     [rsp+1058h+var_1028], 1000h
0x18000124a  mov     rdi, rcx
0x18000124d  jnz     loc_180001306
0x180001253  mov     rax, [rcx+20h]
0x180001257  lea     r9, [rsp+1058h+var_1028]
0x18000125c  lea     r8, [rsp+1058h+String]
0x180001261  lea     rdx, aApplMdPath; "APPL_MD_PATH"
0x180001268  call    cs:__guard_dispatch_icall_fptr
0x18000126e  test    eax, eax
0x180001270  jnz     short loc_1800012C9
0x180001272  call    cs:__imp_GetLastError
0x180001278  cmp     eax, 7Ah ; 'z'
0x18000127b  jnz     short loc_1800012A2
0x18000127d  mov     edx, [rsp+1058h+var_1028]
0x180001281  xor     r8d, r8d
0x180001284  mov     rax, [rdi+38h]
0x180001288  mov     rcx, rdi
0x18000128b  call    cs:__guard_dispatch_icall_fptr
0x180001291  mov     rbx, rax
0x180001294  test    rax, rax
0x180001297  jnz     short loc_1800012A9
0x180001299  lea     ecx, [rax+0Eh]; dwErrCode
0x18000129c  call    cs:__imp_SetLastError
0x1800012a2  mov     eax, 8000004h
0x1800012a7  jmp     short loc_18000130B
0x1800012a9  mov     r8, rax
0x1800012ac  lea     r9, [rsp+1058h+var_1028]
0x1800012b1  mov     rax, [rdi+20h]
0x1800012b5  lea     rdx, aApplMdPath; "APPL_MD_PATH"
0x1800012bc  mov     rcx, rdi
0x1800012bf  call    cs:__guard_dispatch_icall_fptr
0x1800012c5  test    eax, eax
0x1800012c7  jz      short loc_1800012A2
0x1800012c9  mov     rcx, rbx; lpString
0x1800012cc  call    cs:__imp_lstrlenA
0x1800012d2  test    eax, eax
0x1800012d4  jz      short loc_180001306
0x1800012d6  mov     rcx, [rsi]; char *
0x1800012d9  mov     rdx, rbx; char *
0x1800012dc  call    ?RemoveAppPrefix@@YAPEADPEAD0@Z; RemoveAppPrefix(char *,char *)
0x1800012e1  test    rax, rax
0x1800012e4  jz      short loc_180001306
0x1800012e6  cmp     byte ptr [rax], 2Fh ; '/'
0x1800012e9  jnz     short loc_180001306
0x1800012eb  lea     rcx, [rax+1]; String1
0x1800012ef  lea     rdx, aBin; "bin"
0x1800012f6  call    ?PathMatches@@YAHPEBD0@Z; PathMatches(char const *,char const *)
0x1800012fb  test    eax, eax
0x1800012fd  jz      short loc_180001306
0x1800012ff  mov     ecx, 2
0x180001304  jmp     short loc_18000129C
0x180001306  mov     eax, 8000002h
0x18000130b  mov     rcx, [rsp+1058h+var_18]
0x180001313  xor     rcx, rsp; StackCookie
0x180001316  call    __security_check_cookie
0x18000131b  lea     r11, [rsp+1058h+var_8]
0x180001323  mov     rbx, [r11+20h]
0x180001327  mov     rsi, [r11+28h]
0x18000132b  mov     rsp, r11
0x18000132e  pop     rdi
0x18000132f  retn
```
