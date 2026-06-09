# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x18000774c`
- end: `0x1800077b3`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `103`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `69`
- callee_count: `3`
- tags: ``

## callers

- `0x180007524`
- `0x180007aac`
- `0x18000f98c`
- `0x18001512c`
- `0x180015bb8`
- `0x18001b664`
- `0x18001b704`
- `0x18001b7a4`
- `0x18001b848`
- `0x18001ba64`
- `0x18001bb08`
- `0x18001c294`
- `0x18001c36c`
- `0x18001c434`
- `0x18001c51c`
- `0x18001c5c0`
- `0x18001d6f0`
- `0x18001d788`
- `0x18001f87c`
- `0x18001f938`
- `0x18001f9f4`
- `0x18001fab4`
- `0x1800200c8`
- `0x18002017c`
- `0x180020238`
- `0x1800202f4`
- `0x1800203b0`
- `0x180020548`
- `0x1800205f8`
- `0x1800206ac`
- `0x180020768`
- `0x180020824`
- `0x1800208d4`
- `0x180020990`
- `0x180020a44`
- `0x180020b00`
- `0x180020bb0`
- `0x180020c60`
- `0x180021620`
- `0x180021ab0`
- `0x180021c0c`
- `0x180022578`
- `0x180022620`
- `0x1800226d8`
- `0x180022774`
- `0x180055e70`
- `0x180055f94`
- `0x1800560b8`
- `0x1800561dc`
- `0x180056300`

## callees

- `0x180006fe0`
- `0x18000774c`
- `0x18000fef0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000775f`
- `KERNEL32!GetLastError` at `0x18000775f`
- `KERNEL32!SetLastError` at `0x180007794`
- `KERNEL32!SetLastError` at `0x180007794`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd(__crt_cached_ptd_host *this)
{
  DWORD LastError; // eax
  bool v3; // zf
  __int64 v4; // rdx
  __int64 v5; // rax
  DWORD v6; // ecx
  __int64 v7; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
  {
    LastError = GetLastError();
    v3 = *((_BYTE *)this + 16) == 0;
    dwErrCode = LastError;
    if ( v3 )
    {
      *((_QWORD *)this + 1) = 0;
      v4 = 0;
      *((_BYTE *)this + 16) = 1;
    }
    else
    {
      v4 = *((_QWORD *)this + 1);
    }
    v5 = _acrt_getptd_noexit_explicit(&dwErrCode, v4);
    v6 = dwErrCode;
    v7 = v5;
    *(_QWORD *)this = v5;
    SetLastError(v6);
    if ( !v7 )
      abort();
  }
  return *(struct __acrt_ptd **)this;
}

```

## disassembly

```asm
0x18000774c  mov     [rsp+arg_8], rbx
0x180007751  push    rdi
0x180007752  sub     rsp, 20h
0x180007756  cmp     qword ptr [rcx], 0
0x18000775a  mov     rdi, rcx
0x18000775d  jnz     short loc_18000779F
0x18000775f  call    cs:__imp_GetLastError
0x180007765  cmp     byte ptr [rdi+10h], 0
0x180007769  mov     [rsp+28h+dwErrCode], eax
0x18000776d  jnz     short loc_18000777C
0x18000776f  and     qword ptr [rdi+8], 0
0x180007774  xor     edx, edx
0x180007776  mov     byte ptr [rdi+10h], 1
0x18000777a  jmp     short loc_180007780
0x18000777c  mov     rdx, [rdi+8]
0x180007780  lea     rcx, [rsp+28h+dwErrCode]
0x180007785  call    __acrt_getptd_noexit_explicit
0x18000778a  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x18000778e  mov     rbx, rax
0x180007791  mov     [rdi], rax
0x180007794  call    cs:__imp_SetLastError
0x18000779a  test    rbx, rbx
0x18000779d  jz      short loc_1800077AD
0x18000779f  mov     rax, [rdi]
0x1800077a2  mov     rbx, [rsp+28h+arg_8]
0x1800077a7  add     rsp, 20h
0x1800077ab  pop     rdi
0x1800077ac  retn
0x1800077ad  call    abort
```
