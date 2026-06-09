# AlpcSection::Unmap(void *,void *,void *)

- ea: `0x18002b9d4`
- end: `0x18002ba3b`
- name: `?Unmap@AlpcSection@@CAJPEAX00@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *, void *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180024d9c`
- `0x180026448`

## callees

- `0x18002b9d4`

## import_xrefs

- `ntdll!NtAlpcDeletePortSection` at `0x18002ba1b`
- `ntdll!NtAlpcDeletePortSection` at `0x18002ba1b`
- `ntdll!NtAlpcDeleteSectionView` at `0x18002b9ec`
- `ntdll!NtAlpcDeleteSectionView` at `0x18002b9ec`

## pseudocode

```c
__int64 __fastcall AlpcSection::Unmap(void *a1, void *a2, void *a3)
{
  int v5; // ecx
  int v6; // ecx
  __int64 result; // rax

  v5 = NtAlpcDeleteSectionView(a2, 0, a1);
  if ( v5 >= 0 )
  {
    if ( !a3 )
      return 0;
    v5 = NtAlpcDeletePortSection(a2, 0, a3);
    if ( v5 >= 0 )
      return 0;
  }
  v6 = v5 | 0x10000000;
  result = 2147549183LL;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return result;
}

```

## disassembly

```asm
0x18002b9d4  mov     [rsp+arg_0], rbx
0x18002b9d9  push    rdi
0x18002b9da  sub     rsp, 20h
0x18002b9de  mov     rdi, rdx
0x18002b9e1  mov     rbx, r8
0x18002b9e4  mov     r8, rcx
0x18002b9e7  xor     edx, edx
0x18002b9e9  mov     rcx, rdi
0x18002b9ec  call    cs:__imp_NtAlpcDeleteSectionView
0x18002b9f3  nop     dword ptr [rax+rax+00h]
0x18002b9f8  mov     ecx, eax
0x18002b9fa  test    eax, eax
0x18002b9fc  jns     short loc_18002BA0E
0x18002b9fe  or      ecx, 10000000h
0x18002ba04  mov     eax, 8000FFFFh
0x18002ba09  cmovl   eax, ecx
0x18002ba0c  jmp     short loc_18002BA2F
0x18002ba0e  test    rbx, rbx
0x18002ba11  jz      short loc_18002BA2D
0x18002ba13  mov     r8, rbx
0x18002ba16  xor     edx, edx
0x18002ba18  mov     rcx, rdi
0x18002ba1b  call    cs:__imp_NtAlpcDeletePortSection
0x18002ba22  nop     dword ptr [rax+rax+00h]
0x18002ba27  mov     ecx, eax
0x18002ba29  test    eax, eax
0x18002ba2b  js      short loc_18002B9FE
0x18002ba2d  xor     eax, eax
0x18002ba2f  mov     rbx, [rsp+28h+arg_0]
0x18002ba34  add     rsp, 20h
0x18002ba38  pop     rdi
0x18002ba39  retn
```
