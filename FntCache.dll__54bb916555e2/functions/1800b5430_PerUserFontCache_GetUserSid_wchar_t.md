# PerUserFontCache::GetUserSid(wchar_t * *)

- ea: `0x1800b5430`
- end: `0x1800b54a8`
- name: `?GetUserSid@PerUserFontCache@@UEAAJPEAPEA_W@Z`
- size: `120`
- prototype: `__int64 __fastcall(PerUserFontCache *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063950`

## callees

- `0x1800b5430`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b5472`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800b5472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b547f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b547f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5457`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5457`

## pseudocode

```c
__int64 __fastcall PerUserFontCache::GetUserSid(PerUserFontCache *this, LPVOID *a2)
{
  __int64 v4; // rsi
  wchar_t *v5; // rax
  __int64 result; // rax

  v4 = (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 1) + 4LL) + 1);
  v5 = (wchar_t *)CoTaskMemAlloc(2 * v4);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  result = _o_wcscpy_s(v5, (unsigned int)v4, *((_QWORD *)this + 1) + 8LL);
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
0x1800b5430  mov     [rsp+arg_0], rbx
0x1800b5435  mov     [rsp+arg_8], rsi
0x1800b543a  push    rdi
0x1800b543b  sub     rsp, 20h
0x1800b543f  mov     rax, [rcx+8]
0x1800b5443  mov     rdi, rcx
0x1800b5446  mov     rbx, rdx
0x1800b5449  mov     r8d, [rax+4]
0x1800b544d  inc     r8d
0x1800b5450  mov     esi, r8d
0x1800b5453  lea     rcx, [r8+r8]; cb
0x1800b5457  call    cs:__imp_CoTaskMemAlloc
0x1800b545d  mov     [rbx], rax
0x1800b5460  test    rax, rax
0x1800b5463  jz      short loc_1800B5493
0x1800b5465  mov     r8, [rdi+8]
0x1800b5469  mov     edx, esi
0x1800b546b  add     r8, 8
0x1800b546f  mov     rcx, rax
0x1800b5472  call    cs:__imp__o_wcscpy_s
0x1800b5478  test    eax, eax
0x1800b547a  jz      short loc_1800B5498
0x1800b547c  mov     rcx, [rbx]; pv
0x1800b547f  call    cs:__imp_CoTaskMemFree
0x1800b5485  mov     eax, 80004005h
0x1800b548a  mov     qword ptr [rbx], 0
0x1800b5491  jmp     short loc_1800B5498
0x1800b5493  mov     eax, 8007000Eh
0x1800b5498  mov     rbx, [rsp+28h+arg_0]
0x1800b549d  mov     rsi, [rsp+28h+arg_8]
0x1800b54a2  add     rsp, 20h
0x1800b54a6  pop     rdi
0x1800b54a7  retn
```
