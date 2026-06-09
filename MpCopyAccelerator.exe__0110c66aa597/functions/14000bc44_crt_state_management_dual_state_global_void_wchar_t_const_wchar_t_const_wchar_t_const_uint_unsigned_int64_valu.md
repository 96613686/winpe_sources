# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x14000bc44`
- end: `0x14000bc90`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bea4`

## callees

- `0x14000bc44`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000bc70`
- `KERNEL32!SetLastError` at `0x14000bc70`
- `KERNEL32!GetLastError` at `0x14000bc60`
- `KERNEL32!GetLastError` at `0x14000bc60`

## pseudocode

```c
__int64 __fastcall __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,unsigned int,unsigned __int64)>::value(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  DWORD LastError; // eax

  v2 = 0;
  if ( *(_BYTE *)(a2 + 16) )
  {
    v2 = *(_QWORD *)(a2 + 8);
  }
  else
  {
    LastError = GetLastError();
    *(_QWORD *)(a2 + 8) = 0;
    *(_BYTE *)(a2 + 16) = 1;
    SetLastError(LastError);
  }
  return a1 + 8 * v2;
}

```

## disassembly

```asm
0x14000bc44  mov     [rsp+arg_0], rbx
0x14000bc49  mov     [rsp+arg_8], rsi
0x14000bc4e  push    rdi
0x14000bc4f  sub     rsp, 20h
0x14000bc53  xor     ebx, ebx
0x14000bc55  mov     rdi, rdx
0x14000bc58  mov     rsi, rcx
0x14000bc5b  cmp     [rdx+10h], bl
0x14000bc5e  jnz     short loc_14000BC78
0x14000bc60  call    cs:__imp_GetLastError
0x14000bc66  mov     ecx, eax; dwErrCode
0x14000bc68  mov     [rdi+8], rbx
0x14000bc6c  mov     byte ptr [rdi+10h], 1
0x14000bc70  call    cs:__imp_SetLastError
0x14000bc76  jmp     short loc_14000BC7C
0x14000bc78  mov     rbx, [rdx+8]
0x14000bc7c  lea     rax, [rsi+rbx*8]
0x14000bc80  mov     rbx, [rsp+28h+arg_0]
0x14000bc85  mov     rsi, [rsp+28h+arg_8]
0x14000bc8a  add     rsp, 20h
0x14000bc8e  pop     rdi
0x14000bc8f  retn
```
