# CabCallback(ushort const *,void *)

- ea: `0x18000ed20`
- end: `0x18000ed94`
- name: `?CabCallback@@YA?AW4CAB_COMMAND@@PEBGPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(const WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ed20`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ed54`
- `msvcrt!_wcsicmp` at `0x18000ed54`
- `SHLWAPI!PathFindFileNameW` at `0x18000ed39`
- `SHLWAPI!PathFindFileNameW` at `0x18000ed39`

## pseudocode

```c
__int64 __fastcall CabCallback(const WCHAR *a1, __int64 a2)
{
  __int64 v2; // rbx
  const wchar_t *v4; // rsi
  LPWSTR FileNameW; // rax
  __int64 result; // rax

  v2 = *(_QWORD *)(a2 + 8);
  v4 = a1;
  FileNameW = PathFindFileNameW(a1);
  if ( FileNameW )
    v4 = FileNameW;
  while ( *(_QWORD *)v2 )
  {
    if ( !*(_DWORD *)(v2 + 12) && !_wcsicmp(v4, *(const wchar_t **)v2) )
    {
      *(_DWORD *)(v2 + 12) = 1;
      result = 2;
      ++*(_DWORD *)(a2 + 4);
      if ( *(_DWORD *)(v2 + 8) )
        return result;
      return 1;
    }
    v2 += 16;
  }
  return 1;
}

```

## disassembly

```asm
0x18000ed20  mov     [rsp+arg_0], rbx
0x18000ed25  mov     [rsp+arg_8], rsi
0x18000ed2a  push    rdi
0x18000ed2b  sub     rsp, 20h
0x18000ed2f  mov     rbx, [rdx+8]
0x18000ed33  mov     rdi, rdx
0x18000ed36  mov     rsi, rcx
0x18000ed39  call    cs:__imp_PathFindFileNameW
0x18000ed3f  test    rax, rax
0x18000ed42  cmovnz  rsi, rax
0x18000ed46  jmp     short loc_18000ED62
0x18000ed48  cmp     dword ptr [rbx+0Ch], 0
0x18000ed4c  jnz     short loc_18000ED5E
0x18000ed4e  mov     rdx, [rbx]; String2
0x18000ed51  mov     rcx, rsi; String1
0x18000ed54  call    cs:__imp__wcsicmp
0x18000ed5a  test    eax, eax
0x18000ed5c  jz      short loc_18000ED6A
0x18000ed5e  add     rbx, 10h
0x18000ed62  cmp     qword ptr [rbx], 0
0x18000ed66  jnz     short loc_18000ED48
0x18000ed68  jmp     short loc_18000ED7F
0x18000ed6a  mov     dword ptr [rbx+0Ch], 1
0x18000ed71  mov     eax, 2
0x18000ed76  inc     dword ptr [rdi+4]
0x18000ed79  cmp     dword ptr [rbx+8], 0
0x18000ed7d  jnz     short loc_18000ED84
0x18000ed7f  mov     eax, 1
0x18000ed84  mov     rbx, [rsp+28h+arg_0]
0x18000ed89  mov     rsi, [rsp+28h+arg_8]
0x18000ed8e  add     rsp, 20h
0x18000ed92  pop     rdi
0x18000ed93  retn
```
