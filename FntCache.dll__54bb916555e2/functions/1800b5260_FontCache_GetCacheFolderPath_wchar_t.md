# FontCache::GetCacheFolderPath(wchar_t * *)

- ea: `0x1800b5260`
- end: `0x1800b52d8`
- name: `?GetCacheFolderPath@FontCache@@UEAAJPEAPEA_W@Z`
- size: `120`
- prototype: `__int64 __fastcall(FontCache *this, LPVOID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063950`

## callees

- `0x1800b5260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b52a2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b52a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b52af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b52af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5287`

## pseudocode

```c
__int64 __fastcall FontCache::GetCacheFolderPath(FontCache *this, LPVOID *a2)
{
  __int64 v4; // rsi
  wchar_t *v5; // rax
  __int64 result; // rax

  v4 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 5) + 4LL) + 1);
  v5 = (wchar_t *)CoTaskMemAlloc(2 * v4);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  result = _o_wcscpy_s(v5, (unsigned int)v4, *((_QWORD *)this + 5) + 8LL);
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
0x1800b5260  mov     [rsp+arg_0], rbx
0x1800b5265  mov     [rsp+arg_8], rsi
0x1800b526a  push    rdi
0x1800b526b  sub     rsp, 20h
0x1800b526f  mov     rax, [rcx+28h]
0x1800b5273  mov     rdi, rcx
0x1800b5276  mov     rbx, rdx
0x1800b5279  mov     r8d, [rax+4]
0x1800b527d  inc     r8d
0x1800b5280  mov     esi, r8d
0x1800b5283  lea     rcx, [r8+r8]; cb
0x1800b5287  call    cs:__imp_CoTaskMemAlloc
0x1800b528d  mov     [rbx], rax
0x1800b5290  test    rax, rax
0x1800b5293  jz      short loc_1800B52C3
0x1800b5295  mov     r8, [rdi+28h]
0x1800b5299  mov     edx, esi
0x1800b529b  add     r8, 8
0x1800b529f  mov     rcx, rax
0x1800b52a2  call    cs:__imp__o_wcscpy_s
0x1800b52a8  test    eax, eax
0x1800b52aa  jz      short loc_1800B52C8
0x1800b52ac  mov     rcx, [rbx]; pv
0x1800b52af  call    cs:__imp_CoTaskMemFree
0x1800b52b5  mov     eax, 80004005h
0x1800b52ba  mov     qword ptr [rbx], 0
0x1800b52c1  jmp     short loc_1800B52C8
0x1800b52c3  mov     eax, 8007000Eh
0x1800b52c8  mov     rbx, [rsp+28h+arg_0]
0x1800b52cd  mov     rsi, [rsp+28h+arg_8]
0x1800b52d2  add     rsp, 20h
0x1800b52d6  pop     rdi
0x1800b52d7  retn
```
