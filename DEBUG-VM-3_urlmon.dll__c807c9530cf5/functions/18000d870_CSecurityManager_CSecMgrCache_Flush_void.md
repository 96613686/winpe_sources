# CSecurityManager::CSecMgrCache::Flush(void)

- ea: `0x18000d870`
- end: `0x18000da26`
- name: `?Flush@CSecMgrCache@CSecurityManager@@QEAAXXZ`
- size: `438`
- prototype: `void __fastcall(CSecurityManager::CSecMgrCache *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d6d4`
- `0x18000e214`
- `0x180010970`
- `0x180012e20`
- `0x180013730`
- `0x18001d500`
- `0x18004721c`
- `0x1800473dc`
- `0x180062f7c`

## callees

- `0x18000d870`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d99d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da16`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d9e3`

## pseudocode

```c
void __fastcall CSecurityManager::CSecMgrCache::Flush(CSecurityManager::CSecMgrCache *this)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  char *v8; // rdi
  OLECHAR *v9; // r14
  OLECHAR *v10; // r14
  DWORD LastError; // ebx
  DWORD v12; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = 0;
  v3 = 0;
  do
  {
    v4 = *(_QWORD *)((char *)this + v3 + 48);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *(_QWORD *)((char *)this + v3 + 48) = 0;
    }
    v5 = *(void **)((char *)this + v3 + 96);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)((char *)this + v3 + 96) = 0;
    }
    v6 = *(void **)((char *)this + v3 + 56);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)((char *)this + v3 + 56) = 0;
    }
    v7 = *(void **)((char *)this + v3 + 88);
    *(_DWORD *)((char *)this + v3 + 64) = 0;
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *(_QWORD *)((char *)this + v3 + 88) = 0;
    }
    *(_DWORD *)((char *)this + v3 + 68) = -1;
    v8 = (char *)this + 32 * v2;
    *(_DWORD *)((char *)this + v3 + 76) = -1;
    *(_DWORD *)((char *)this + v3 + 80) = 0;
    v9 = (OLECHAR *)*((_QWORD *)v8 + 231);
    if ( v9 )
    {
      LastError = GetLastError();
      SysFreeString(v9);
      SetLastError(LastError);
    }
    *((_QWORD *)v8 + 231) = 0;
    v10 = (OLECHAR *)*((_QWORD *)v8 + 233);
    if ( v10 )
    {
      v12 = GetLastError();
      SysFreeString(v10);
      SetLastError(v12);
    }
    *((_QWORD *)v8 + 233) = 0;
    ++v2;
    v3 += 56;
    *((_DWORD *)v8 + 468) = -1;
    *((_DWORD *)v8 + 464) = 0;
    *((_DWORD *)v8 + 465) = -2147024891;
  }
  while ( v2 != 32 );
  *((_DWORD *)this + 460) = 0;
  *((_DWORD *)this + 718) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18000d870  push    r12
0x18000d872  push    r13
0x18000d874  push    r15
0x18000d876  sub     rsp, 30h
0x18000d87a  mov     [rsp+48h+arg_8], rbp
0x18000d87f  mov     r15, rcx
0x18000d882  mov     [rsp+48h+arg_10], rsi
0x18000d887  add     rcx, 8; lpCriticalSection
0x18000d88b  mov     [rsp+48h+var_20], rdi
0x18000d890  mov     [rsp+48h+var_28], r14
0x18000d895  call    cs:__imp_EnterCriticalSection
0x18000d89b  xor     r13d, r13d
0x18000d89e  mov     [rsp+48h+arg_0], rbx
0x18000d8a3  mov     esi, r13d
0x18000d8a6  mov     ebp, r13d
0x18000d8a9  nop     dword ptr [rax+00000000h]
0x18000d8b0  mov     rcx, [r15+rbp+30h]
0x18000d8b5  test    rcx, rcx
0x18000d8b8  jnz     loc_18000D9A4
0x18000d8be  mov     rcx, [r15+rbp+60h]; pv
0x18000d8c3  test    rcx, rcx
0x18000d8c6  jnz     loc_18000DA06
0x18000d8cc  mov     rcx, [r15+rbp+38h]; pv
0x18000d8d1  test    rcx, rcx
0x18000d8d4  jnz     loc_18000D9F6
0x18000d8da  mov     rcx, [r15+rbp+58h]; pv
0x18000d8df  mov     [r15+rbp+40h], r13d
0x18000d8e4  test    rcx, rcx
0x18000d8e7  jnz     loc_18000DA16
0x18000d8ed  mov     rdi, rsi
0x18000d8f0  mov     dword ptr [r15+rbp+44h], 0FFFFFFFFh
0x18000d8f9  shl     rdi, 5
0x18000d8fd  add     rdi, r15
0x18000d900  mov     dword ptr [r15+rbp+4Ch], 0FFFFFFFFh
0x18000d909  mov     [r15+rbp+50h], r13d
0x18000d90e  mov     r14, [rdi+738h]
0x18000d915  test    r14, r14
0x18000d918  jnz     loc_18000D9BA
0x18000d91e  mov     [rdi+738h], r13
0x18000d925  mov     r14, [rdi+748h]
0x18000d92c  test    r14, r14
0x18000d92f  jnz     loc_18000D9D8
0x18000d935  mov     [rdi+748h], r13
0x18000d93c  inc     rsi
0x18000d93f  add     rbp, 38h ; '8'
0x18000d943  mov     dword ptr [rdi+750h], 0FFFFFFFFh
0x18000d94d  mov     [rdi+740h], r13d
0x18000d954  mov     dword ptr [rdi+744h], 80070005h
0x18000d95e  cmp     rsi, 20h ; ' '
0x18000d962  jnz     loc_18000D8B0
0x18000d968  mov     r14, [rsp+48h+var_28]
0x18000d96d  lea     rcx, [r15+8]
0x18000d971  mov     rdi, [rsp+48h+var_20]
0x18000d976  mov     rsi, [rsp+48h+arg_10]
0x18000d97b  mov     rbp, [rsp+48h+arg_8]
0x18000d980  mov     rbx, [rsp+48h+arg_0]
0x18000d985  mov     [r15+730h], r13d
0x18000d98c  mov     [r15+0B38h], r13d
0x18000d993  add     rsp, 30h
0x18000d997  pop     r15
0x18000d999  pop     r13
0x18000d99b  pop     r12
0x18000d99d  jmp     cs:__imp_LeaveCriticalSection
0x18000d9a4  mov     rax, [rcx]
0x18000d9a7  mov     rax, [rax+10h]
0x18000d9ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b0  mov     [r15+rbp+30h], r13
0x18000d9b5  jmp     loc_18000D8BE
0x18000d9ba  call    cs:__imp_GetLastError
0x18000d9c0  mov     rcx, r14; bstrString
0x18000d9c3  mov     ebx, eax
0x18000d9c5  call    cs:__imp_SysFreeString
0x18000d9cb  mov     ecx, ebx; dwErrCode
0x18000d9cd  call    cs:__imp_SetLastError
0x18000d9d3  jmp     loc_18000D91E
0x18000d9d8  call    cs:__imp_GetLastError
0x18000d9de  mov     rcx, r14; bstrString
0x18000d9e1  mov     ebx, eax
0x18000d9e3  call    cs:__imp_SysFreeString
0x18000d9e9  mov     ecx, ebx; dwErrCode
0x18000d9eb  call    cs:__imp_SetLastError
0x18000d9f1  jmp     loc_18000D935
0x18000d9f6  call    cs:__imp_CoTaskMemFree
0x18000d9fc  mov     [r15+rbp+38h], r13
0x18000da01  jmp     loc_18000D8DA
0x18000da06  call    cs:__imp_CoTaskMemFree
0x18000da0c  mov     [r15+rbp+60h], r13
0x18000da11  jmp     loc_18000D8CC
0x18000da16  call    cs:__imp_CoTaskMemFree
0x18000da1c  mov     [r15+rbp+58h], r13
0x18000da21  jmp     loc_18000D8ED
```
