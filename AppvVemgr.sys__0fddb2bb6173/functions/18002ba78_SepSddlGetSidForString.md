# SepSddlGetSidForString

- ea: `0x18002ba78`
- end: `0x18002bb24`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002b6b8`

## callees

- `0x18002ba78`

## import_xrefs

- `ntoskrnl!SeExports` at `0x18002bafe`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x18002baea`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x18002baea`
- `ntoskrnl!_wcsnicmp` at `0x18002baad`
- `ntoskrnl!_wcsnicmp` at `0x18002baad`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_180027230[3 * v6 + 1] + 2, HIDWORD(qword_180027230[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_180027230[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_180027230[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_180027230[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x18002ba78  push    rbx
0x18002ba7a  push    rsi
0x18002ba7b  push    rdi
0x18002ba7c  push    r12
0x18002ba7e  push    r14
0x18002ba80  push    r15
0x18002ba82  sub     rsp, 28h
0x18002ba86  mov     r15, r8
0x18002ba89  lea     r12, qword_180027230
0x18002ba90  mov     rdi, rdx
0x18002ba93  mov     r14, rcx
0x18002ba96  xor     ebx, ebx
0x18002ba98  lea     rsi, [rbx+rbx*2]
0x18002ba9c  mov     rcx, r14; Str1
0x18002ba9f  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x18002baa4  lea     rdx, [r12+0Ch]
0x18002baa9  lea     rdx, [rdx+rsi*8]; Str2
0x18002baad  call    cs:__imp__wcsnicmp
0x18002bab4  nop     dword ptr [rax+rax+00h]
0x18002bab9  test    eax, eax
0x18002babb  jz      short loc_18002BAD2
0x18002babd  inc     ebx
0x18002babf  cmp     ebx, 0Eh
0x18002bac2  jb      short loc_18002BA98
0x18002bac4  mov     qword ptr [rdi], 0
0x18002bacb  mov     eax, 0C0000073h
0x18002bad0  jmp     short loc_18002BB15
0x18002bad2  cmp     dword ptr [r12+rsi*8+8], 1
0x18002bad8  mov     eax, [r12+rsi*8+14h]
0x18002badd  lea     rdx, [r14+rax*2]
0x18002bae1  mov     [r15], rdx
0x18002bae4  jnz     short loc_18002BAFE
0x18002bae6  mov     dl, 20h ; ' '; MinorVersion
0x18002bae8  mov     cl, 1; MajorVersion
0x18002baea  call    cs:__imp_IoIsWdmVersionAvailable
0x18002baf1  nop     dword ptr [rax+rax+00h]
0x18002baf6  test    al, al
0x18002baf8  jnz     short loc_18002BAFE
0x18002bafa  xor     eax, eax
0x18002bafc  jmp     short loc_18002BB10
0x18002bafe  mov     rax, cs:__imp_SeExports
0x18002bb05  mov     rdx, [r12+rsi*8]
0x18002bb09  mov     rcx, [rax]
0x18002bb0c  mov     rax, [rdx+rcx]
0x18002bb10  mov     [rdi], rax
0x18002bb13  xor     eax, eax
0x18002bb15  add     rsp, 28h
0x18002bb19  pop     r15
0x18002bb1b  pop     r14
0x18002bb1d  pop     r12
0x18002bb1f  pop     rdi
0x18002bb20  pop     rsi
0x18002bb21  pop     rbx
0x18002bb22  retn
```
