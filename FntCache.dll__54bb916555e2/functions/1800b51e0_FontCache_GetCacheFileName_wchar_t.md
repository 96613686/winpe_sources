# FontCache::GetCacheFileName(wchar_t * *)

- ea: `0x1800b51e0`
- end: `0x1800b5258`
- name: `?GetCacheFileName@FontCache@@UEAAJPEAPEA_W@Z`
- size: `120`
- prototype: `__int64 __fastcall(FontCache *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063950`

## callees

- `0x1800b51e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b5222`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b5222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b522f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b522f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5207`

## pseudocode

```c
__int64 __fastcall FontCache::GetCacheFileName(FontCache *this, LPVOID *a2)
{
  __int64 v4; // rsi
  wchar_t *v5; // rax
  __int64 result; // rax

  v4 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 6) + 4LL) + 1);
  v5 = (wchar_t *)CoTaskMemAlloc(2 * v4);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  result = _o_wcscpy_s(v5, (unsigned int)v4, *((_QWORD *)this + 6) + 8LL);
  if ( (_DWORD)result )
  {
    CoTaskMemFree(*a2);
    result = 2147500037LL;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b51e0  mov     [rsp+arg_0], rbx
0x1800b51e5  mov     [rsp+arg_8], rsi
0x1800b51ea  push    rdi
0x1800b51eb  sub     rsp, 20h
0x1800b51ef  mov     rax, [rcx+30h]
0x1800b51f3  mov     rdi, rcx
0x1800b51f6  mov     rbx, rdx
0x1800b51f9  mov     r8d, [rax+4]
0x1800b51fd  inc     r8d
0x1800b5200  mov     esi, r8d
0x1800b5203  lea     rcx, [r8+r8]; cb
0x1800b5207  call    cs:__imp_CoTaskMemAlloc
0x1800b520d  mov     [rbx], rax
0x1800b5210  test    rax, rax
0x1800b5213  jz      short loc_1800B5243
0x1800b5215  mov     r8, [rdi+30h]
0x1800b5219  mov     edx, esi
0x1800b521b  add     r8, 8
0x1800b521f  mov     rcx, rax
0x1800b5222  call    cs:__imp__o_wcscpy_s
0x1800b5228  test    eax, eax
0x1800b522a  jz      short loc_1800B5248
0x1800b522c  mov     rcx, [rbx]; pv
0x1800b522f  call    cs:__imp_CoTaskMemFree
0x1800b5235  mov     eax, 80004005h
0x1800b523a  mov     qword ptr [rbx], 0
0x1800b5241  jmp     short loc_1800B5248
0x1800b5243  mov     eax, 8007000Eh
0x1800b5248  mov     rbx, [rsp+28h+arg_0]
0x1800b524d  mov     rsi, [rsp+28h+arg_8]
0x1800b5252  add     rsp, 20h
0x1800b5256  pop     rdi
0x1800b5257  retn
```
