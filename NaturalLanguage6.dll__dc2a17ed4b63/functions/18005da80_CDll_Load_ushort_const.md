# CDll::Load(ushort const *)

- ea: `0x18005da80`
- end: `0x18005daf1`
- name: `?Load@CDll@@UEAAHPEBG@Z`
- size: `113`
- prototype: `int(CDll *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003b5c0`

## callees

- `0x1800162e4`
- `0x18005da80`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005dac2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005dac2`

## pseudocode

```c
__int64 __fastcall CDll::Load(CDll *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  HMODULE LibraryW; // rax

  if ( !a2 )
    return 0;
  (*(void (__fastcall **)(CDll *))(*(_QWORD *)this + 40LL))(this);
  if ( StringCchCopyW((unsigned __int16 *)this + 10, 0x104u, a2) >= 0
    && (LibraryW = LoadLibraryW(a2), (*((_QWORD *)this + 1) = LibraryW) != 0) )
  {
    result = 1;
    ++*((_DWORD *)this + 4);
  }
  else
  {
    result = 0;
    *((_WORD *)this + 10) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18005da80  mov     [rsp+arg_0], rbx
0x18005da85  mov     [rsp+arg_8], rsi
0x18005da8a  push    rdi
0x18005da8b  sub     rsp, 20h
0x18005da8f  mov     rdi, rdx
0x18005da92  mov     rbx, rcx
0x18005da95  test    rdx, rdx
0x18005da98  jnz     short loc_18005DA9E
0x18005da9a  xor     eax, eax
0x18005da9c  jmp     short loc_18005DAE1
0x18005da9e  mov     rax, [rcx]
0x18005daa1  mov     rax, [rax+28h]
0x18005daa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daaa  mov     r8, rdi; unsigned __int16 *
0x18005daad  lea     rcx, [rbx+14h]; unsigned __int16 *
0x18005dab1  mov     edx, 104h; unsigned __int64
0x18005dab6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005dabb  test    eax, eax
0x18005dabd  js      short loc_18005DADB
0x18005dabf  mov     rcx, rdi; lpLibFileName
0x18005dac2  call    cs:__imp_LoadLibraryW
0x18005dac8  mov     [rbx+8], rax
0x18005dacc  test    rax, rax
0x18005dacf  jz      short loc_18005DADB
0x18005dad1  mov     eax, 1
0x18005dad6  add     [rbx+10h], eax
0x18005dad9  jmp     short loc_18005DAE1
0x18005dadb  xor     eax, eax
0x18005dadd  mov     [rbx+14h], ax
0x18005dae1  mov     rbx, [rsp+28h+arg_0]
0x18005dae6  mov     rsi, [rsp+28h+arg_8]
0x18005daeb  add     rsp, 20h
0x18005daef  pop     rdi
0x18005daf0  retn
```
