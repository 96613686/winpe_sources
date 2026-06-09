# IsOSVersionPresentInList(ushort const *,ushort const *,int &,int &)

- ea: `0x180018b8c`
- end: `0x180018c6b`
- name: `?IsOSVersionPresentInList@@YAJPEBG0AEAH1@Z`
- size: `223`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006eb0`
- `0x180009a40`
- `0x180009b60`
- `0x180009c30`

## callees

- `0x180006e28`
- `0x180018b8c`
- `0x180019068`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180018c2d`
- `msvcrt!wcstok_s` at `0x180018c2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018c55`

## pseudocode

```c
__int64 __fastcall IsOSVersionPresentInList(unsigned __int16 *a1, unsigned __int16 *a2, int *a3, int *a4)
{
  wchar_t *v8; // rbx
  unsigned int v9; // edi
  wchar_t *i; // rcx
  int v11; // eax
  wchar_t *v12; // rax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v15; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp+20h] BYREF

  Context = 0;
  *a3 = 0;
  v15 = 0;
  CSpDynamicString::operator=(&v15, a1);
  pv = 0;
  CSpDynamicString::operator=(&pv, a2);
  v8 = (wchar_t *)v15;
  *a4 = 0;
  if ( a1 )
  {
    v9 = 0;
    if ( v8 )
    {
      for ( i = v8; ; i = 0 )
      {
        v12 = wcstok_s(i, L" ;:,", &Context);
        if ( !v12 )
          break;
        v11 = VersionCompare(v12, pv);
        if ( !v11 )
        {
          *a3 = 1;
          *a4 = 1;
          break;
        }
        if ( v11 == 2 )
          *a4 = 1;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v8);
  return v9;
}

```

## disassembly

```asm
0x180018b8c  mov     rax, rsp
0x180018b8f  mov     [rax+10h], rbx
0x180018b93  push    rsi
0x180018b94  push    rdi
0x180018b95  push    r14
0x180018b97  sub     rsp, 20h
0x180018b9b  mov     rbx, rdx
0x180018b9e  mov     qword ptr [rax+20h], 0
0x180018ba6  mov     rdx, rcx
0x180018ba9  mov     dword ptr [r8], 0
0x180018bb0  mov     rdi, rcx
0x180018bb3  mov     qword ptr [rax+18h], 0
0x180018bbb  lea     rcx, [rax+18h]
0x180018bbf  mov     rsi, r9
0x180018bc2  mov     r14, r8
0x180018bc5  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180018bca  mov     rdx, rbx
0x180018bcd  mov     [rsp+38h+pv], 0
0x180018bd6  lea     rcx, [rsp+38h+pv]
0x180018bdb  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180018be0  mov     rbx, [rsp+38h+arg_10]
0x180018be5  mov     dword ptr [rsi], 0
0x180018beb  test    rdi, rdi
0x180018bee  jnz     short loc_180018BF7
0x180018bf0  mov     edi, 80070057h
0x180018bf5  jmp     short loc_180018C47
0x180018bf7  xor     edi, edi
0x180018bf9  test    rbx, rbx
0x180018bfc  jz      short loc_180018C47
0x180018bfe  mov     rcx, rbx
0x180018c01  jmp     short loc_180018C21
0x180018c03  mov     rdx, [rsp+38h+pv]
0x180018c08  mov     rcx, rax
0x180018c0b  call    ?VersionCompare@@YA?AW4VersionCompareResult@@PEBG0@Z; VersionCompare(ushort const *,ushort const *)
0x180018c10  test    eax, eax
0x180018c12  jz      short loc_180018C3A
0x180018c14  cmp     eax, 2
0x180018c17  jnz     short loc_180018C1F
0x180018c19  mov     dword ptr [rsi], 1
0x180018c1f  xor     ecx, ecx; String
0x180018c21  lea     r8, [rsp+38h+Context]; Context
0x180018c26  lea     rdx, Delimiter; " ;:,"
0x180018c2d  call    cs:__imp_wcstok_s
0x180018c33  test    rax, rax
0x180018c36  jnz     short loc_180018C03
0x180018c38  jmp     short loc_180018C47
0x180018c3a  mov     dword ptr [r14], 1
0x180018c41  mov     dword ptr [rsi], 1
0x180018c47  mov     rcx, [rsp+38h+pv]; pv
0x180018c4c  call    cs:__imp_CoTaskMemFree
0x180018c52  mov     rcx, rbx; pv
0x180018c55  call    cs:__imp_CoTaskMemFree
0x180018c5b  mov     rbx, [rsp+38h+arg_8]
0x180018c60  mov     eax, edi
0x180018c62  add     rsp, 20h
0x180018c66  pop     r14
0x180018c68  pop     rdi
0x180018c69  pop     rsi
0x180018c6a  retn
```
