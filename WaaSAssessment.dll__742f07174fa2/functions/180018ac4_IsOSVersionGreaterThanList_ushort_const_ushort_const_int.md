# IsOSVersionGreaterThanList(ushort const *,ushort const *,int &)

- ea: `0x180018ac4`
- end: `0x180018b86`
- name: `?IsOSVersionGreaterThanList@@YAJPEBG0AEAH@Z`
- size: `194`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b50`

## callees

- `0x180006e28`
- `0x180018ac4`
- `0x180019068`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180018b59`
- `msvcrt!wcstok_s` at `0x180018b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b76`

## pseudocode

```c
__int64 __fastcall IsOSVersionGreaterThanList(unsigned __int16 *a1, unsigned __int16 *a2, int *a3)
{
  void *v6; // rbx
  unsigned int v7; // edi
  wchar_t *i; // rcx
  int v9; // ecx
  wchar_t *v10; // rax
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v13; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp+20h] BYREF

  Context = 0;
  *a3 = 1;
  v13 = 0;
  CSpDynamicString::operator=(&v13, a1);
  pv = 0;
  CSpDynamicString::operator=(&pv, a2);
  v6 = v13;
  if ( a1 )
  {
    v7 = 0;
    if ( v13 )
    {
      for ( i = (wchar_t *)v13; ; i = 0 )
      {
        v10 = wcstok_s(i, L" ;:,", &Context);
        if ( !v10 )
          break;
        v9 = VersionCompare(v10, pv);
        if ( ((v9 - 1) & 0xFFFFFFFC) == 0 && v9 != 3 )
        {
          *a3 = 0;
          break;
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v6);
  return v7;
}

```

## disassembly

```asm
0x180018ac4  push    rbx
0x180018ac6  push    rsi
0x180018ac7  push    rdi
0x180018ac8  sub     rsp, 20h
0x180018acc  mov     rbx, rdx
0x180018acf  mov     [rsp+38h+Context], 0
0x180018ad8  mov     rdx, rcx
0x180018adb  mov     dword ptr [r8], 1
0x180018ae2  mov     rdi, rcx
0x180018ae5  mov     [rsp+38h+arg_10], 0
0x180018aee  lea     rcx, [rsp+38h+arg_10]
0x180018af3  mov     rsi, r8
0x180018af6  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180018afb  mov     rdx, rbx
0x180018afe  mov     [rsp+38h+pv], 0
0x180018b07  lea     rcx, [rsp+38h+pv]
0x180018b0c  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x180018b11  mov     rbx, [rsp+38h+arg_10]
0x180018b16  test    rdi, rdi
0x180018b19  jnz     short loc_180018B22
0x180018b1b  mov     edi, 80070057h
0x180018b20  jmp     short loc_180018B68
0x180018b22  xor     edi, edi
0x180018b24  test    rbx, rbx
0x180018b27  jz      short loc_180018B68
0x180018b29  mov     rcx, rbx
0x180018b2c  jmp     short loc_180018B4D
0x180018b2e  mov     rdx, [rsp+38h+pv]
0x180018b33  mov     rcx, rax
0x180018b36  call    ?VersionCompare@@YA?AW4VersionCompareResult@@PEBG0@Z; VersionCompare(ushort const *,ushort const *)
0x180018b3b  mov     ecx, eax
0x180018b3d  dec     eax
0x180018b3f  test    eax, 0FFFFFFFCh
0x180018b44  jnz     short loc_180018B4B
0x180018b46  cmp     ecx, 3
0x180018b49  jnz     short loc_180018B66
0x180018b4b  xor     ecx, ecx; String
0x180018b4d  lea     r8, [rsp+38h+Context]; Context
0x180018b52  lea     rdx, Delimiter; " ;:,"
0x180018b59  call    cs:__imp_wcstok_s
0x180018b5f  test    rax, rax
0x180018b62  jnz     short loc_180018B2E
0x180018b64  jmp     short loc_180018B68
0x180018b66  mov     [rsi], edi
0x180018b68  mov     rcx, [rsp+38h+pv]; pv
0x180018b6d  call    cs:__imp_CoTaskMemFree
0x180018b73  mov     rcx, rbx; pv
0x180018b76  call    cs:__imp_CoTaskMemFree
0x180018b7c  mov     eax, edi
0x180018b7e  add     rsp, 20h
0x180018b82  pop     rdi
0x180018b83  pop     rsi
0x180018b84  pop     rbx
0x180018b85  retn
```
