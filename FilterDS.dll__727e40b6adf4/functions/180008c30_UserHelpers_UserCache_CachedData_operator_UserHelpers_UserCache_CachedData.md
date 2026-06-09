# UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)

- ea: `0x180008c30`
- end: `0x180008d90`
- name: `??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z`
- size: `352`
- prototype: `char *__fastcall(char *, char *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000be34`
- `0x180014c20`
- `0x1800153f0`
- `0x1800154f0`

## callees

- `0x180002332`
- `0x180008b9c`
- `0x180008c30`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008ccc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008d68`

## pseudocode

```c
char *__fastcall UserHelpers::UserCache::CachedData::operator=(char *a1, char *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rsi
  void **v7; // r14
  void **v8; // rsi
  HSTRING *v9; // rsi
  HSTRING *v10; // r14
  HSTRING v11; // r15
  HSTRING v12; // rbp
  DWORD LastError; // ebx
  char v15; // [rsp+20h] [rbp-48h] BYREF

  if ( a1 != a2 )
  {
    if ( &v15 == a2 )
    {
      v5 = 0;
      v4 = 0;
    }
    else
    {
      v4 = *((_QWORD *)a2 + 1);
      *((_QWORD *)a2 + 1) = 0;
      v5 = *(_QWORD *)a2;
      *(_QWORD *)a2 = 0;
    }
    v6 = (volatile signed __int32 *)*((_QWORD *)a1 + 1);
    *((_QWORD *)a1 + 1) = v4;
    *(_QWORD *)a1 = v5;
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( !_InterlockedDecrement(v6 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
  }
  v7 = (void **)(a2 + 16);
  v8 = (void **)(a1 + 16);
  if ( a1 + 16 != a2 + 16 )
  {
    if ( *((_QWORD *)a1 + 5) >= 8u )
      operator delete(*v8);
    *((_QWORD *)a1 + 5) = 7;
    *((_QWORD *)a1 + 4) = 0;
    *(_WORD *)v8 = 0;
    if ( *((_QWORD *)a2 + 5) >= 8u )
    {
      *v8 = *v7;
      *v7 = 0;
    }
    else if ( *((_QWORD *)a2 + 4) != -1 )
    {
      memmove_0(a1 + 16, a2 + 16, 2 * (*((_QWORD *)a2 + 4) + 1LL));
    }
    *((_QWORD *)a1 + 4) = *((_QWORD *)a2 + 4);
    *((_QWORD *)a1 + 5) = *((_QWORD *)a2 + 5);
    *((_QWORD *)a2 + 5) = 7;
    *((_QWORD *)a2 + 4) = 0;
    *(_WORD *)v7 = 0;
  }
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::operator=(
    a1 + 48,
    a2 + 48);
  v9 = (HSTRING *)(a2 + 64);
  v10 = (HSTRING *)(a1 + 64);
  if ( a1 + 64 != a2 + 64 )
  {
    v11 = *v9;
    v12 = *v10;
    if ( *v10 )
    {
      LastError = GetLastError();
      WindowsDeleteString(v12);
      SetLastError(LastError);
    }
    *v10 = v11;
    *v9 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180008c30  push    rbx
0x180008c32  push    rbp
0x180008c33  push    rsi
0x180008c34  push    rdi
0x180008c35  push    r14
0x180008c37  push    r15
0x180008c39  sub     rsp, 38h
0x180008c3d  mov     rbx, rdx
0x180008c40  mov     rdi, rcx
0x180008c43  cmp     rcx, rdx
0x180008c46  jz      short loc_180008CB5
0x180008c48  lea     rax, [rsp+68h+var_48]
0x180008c4d  cmp     rax, rdx
0x180008c50  jz      short loc_180008C6A
0x180008c52  mov     rax, [rdx+8]
0x180008c56  mov     qword ptr [rdx+8], 0
0x180008c5e  mov     rcx, [rdx]
0x180008c61  mov     qword ptr [rdx], 0
0x180008c68  jmp     short loc_180008C6E
0x180008c6a  xor     ecx, ecx
0x180008c6c  xor     eax, eax
0x180008c6e  mov     rsi, [rdi+8]
0x180008c72  mov     [rdi+8], rax
0x180008c76  mov     [rdi], rcx
0x180008c79  test    rsi, rsi
0x180008c7c  jz      short loc_180008CB5
0x180008c7e  or      ebp, 0FFFFFFFFh
0x180008c81  mov     eax, ebp
0x180008c83  lock xadd [rsi+8], eax
0x180008c88  add     eax, ebp
0x180008c8a  jnz     short loc_180008CB5
0x180008c8c  mov     rax, [rsi]
0x180008c8f  mov     rcx, rsi
0x180008c92  mov     rax, [rax]
0x180008c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9a  mov     eax, ebp
0x180008c9c  lock xadd [rsi+0Ch], eax
0x180008ca1  add     eax, ebp
0x180008ca3  jnz     short loc_180008CB5
0x180008ca5  mov     rax, [rsi]
0x180008ca8  mov     rcx, rsi
0x180008cab  mov     rax, [rax+8]
0x180008caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb4  nop
0x180008cb5  lea     r14, [rbx+10h]
0x180008cb9  lea     rsi, [rdi+10h]
0x180008cbd  cmp     rsi, r14
0x180008cc0  jz      short loc_180008D38
0x180008cc2  cmp     qword ptr [rsi+18h], 8
0x180008cc7  jb      short loc_180008CD2
0x180008cc9  mov     rcx, [rsi]
0x180008ccc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008cd2  mov     ebp, 7
0x180008cd7  mov     [rsi+18h], rbp
0x180008cdb  mov     qword ptr [rsi+10h], 0
0x180008ce3  xor     eax, eax
0x180008ce5  mov     [rsi], ax
0x180008ce8  cmp     qword ptr [r14+18h], 8
0x180008ced  jnb     short loc_180008D09
0x180008cef  mov     r8, [r14+10h]
0x180008cf3  add     r8, 1
0x180008cf7  jz      short loc_180008D16
0x180008cf9  add     r8, r8; Size
0x180008cfc  mov     rdx, r14; Src
0x180008cff  mov     rcx, rsi; void *
0x180008d02  call    memmove_0
0x180008d07  jmp     short loc_180008D16
0x180008d09  mov     rax, [r14]
0x180008d0c  mov     [rsi], rax
0x180008d0f  mov     qword ptr [r14], 0
0x180008d16  mov     rax, [r14+10h]
0x180008d1a  mov     [rsi+10h], rax
0x180008d1e  mov     rax, [r14+18h]
0x180008d22  mov     [rsi+18h], rax
0x180008d26  mov     [r14+18h], rbp
0x180008d2a  mov     qword ptr [r14+10h], 0
0x180008d32  xor     eax, eax
0x180008d34  mov     [r14], ax
0x180008d38  lea     rdx, [rbx+30h]
0x180008d3c  lea     rcx, [rdi+30h]
0x180008d40  call    ??4?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>>::operator=(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>> &&)
0x180008d45  lea     rsi, [rbx+40h]
0x180008d49  lea     r14, [rdi+40h]
0x180008d4d  cmp     r14, rsi
0x180008d50  jz      short loc_180008D80
0x180008d52  mov     r15, [rsi]
0x180008d55  mov     rbp, [r14]
0x180008d58  test    rbp, rbp
0x180008d5b  jz      short loc_180008D76
0x180008d5d  call    cs:__imp_GetLastError
0x180008d63  mov     ebx, eax
0x180008d65  mov     rcx, rbp; string
0x180008d68  call    cs:__imp_WindowsDeleteString
0x180008d6e  mov     ecx, ebx; dwErrCode
0x180008d70  call    cs:__imp_SetLastError
0x180008d76  mov     [r14], r15
0x180008d79  mov     qword ptr [rsi], 0
0x180008d80  mov     rax, rdi
0x180008d83  add     rsp, 38h
0x180008d87  pop     r15
0x180008d89  pop     r14
0x180008d8b  pop     rdi
0x180008d8c  pop     rsi
0x180008d8d  pop     rbp
0x180008d8e  pop     rbx
0x180008d8f  retn
```
