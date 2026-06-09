# __crt_state_management::dual_state_global<void (*)(wchar_t const *,wchar_t const *,wchar_t const *,uint,unsigned __int64)>::value(__crt_cached_ptd_host &)

- ea: `0x14000622c`
- end: `0x140006278`
- name: `?value@?$dual_state_global@P6AXPEB_W00I_K@Z@__crt_state_management@@QEAAAEAP6AXPEB_W00I_K@ZAEAV__crt_cached_ptd_host@@@Z`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000648c`

## callees

- `0x14000622c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006248`
- `KERNEL32!GetLastError` at `0x140006248`
- `KERNEL32!SetLastError` at `0x140006258`
- `KERNEL32!SetLastError` at `0x140006258`

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
0x14000622c  mov     [rsp+arg_0], rbx
0x140006231  mov     [rsp+arg_8], rsi
0x140006236  push    rdi
0x140006237  sub     rsp, 20h
0x14000623b  xor     ebx, ebx
0x14000623d  mov     rdi, rdx
0x140006240  mov     rsi, rcx
0x140006243  cmp     [rdx+10h], bl
0x140006246  jnz     short loc_140006260
0x140006248  call    cs:GetLastError
0x14000624e  mov     ecx, eax; dwErrCode
0x140006250  mov     [rdi+8], rbx
0x140006254  mov     byte ptr [rdi+10h], 1
0x140006258  call    cs:SetLastError
0x14000625e  jmp     short loc_140006264
0x140006260  mov     rbx, [rdx+8]
0x140006264  lea     rax, [rsi+rbx*8]
0x140006268  mov     rbx, [rsp+28h+arg_0]
0x14000626d  mov     rsi, [rsp+28h+arg_8]
0x140006272  add     rsp, 20h
0x140006276  pop     rdi
0x140006277  retn
```
