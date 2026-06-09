# SepSddlGetSidForString

- ea: `0x140017b18`
- end: `0x140017bc4`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140017758`

## callees

- `0x140017b18`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140017b9e`
- `ntoskrnl!_wcsnicmp` at `0x140017b4d`
- `ntoskrnl!_wcsnicmp` at `0x140017b4d`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140017b8a`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x140017b8a`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_140012150[3 * v6 + 1] + 2, HIDWORD(qword_140012150[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_140012150[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140012150[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140012150[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x140017b18  push    rbx
0x140017b1a  push    rsi
0x140017b1b  push    rdi
0x140017b1c  push    r12
0x140017b1e  push    r14
0x140017b20  push    r15
0x140017b22  sub     rsp, 28h
0x140017b26  mov     r15, r8
0x140017b29  lea     r12, qword_140012150
0x140017b30  mov     rdi, rdx
0x140017b33  mov     r14, rcx
0x140017b36  xor     ebx, ebx
0x140017b38  lea     rsi, [rbx+rbx*2]
0x140017b3c  mov     rcx, r14; Str1
0x140017b3f  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x140017b44  lea     rdx, [r12+0Ch]
0x140017b49  lea     rdx, [rdx+rsi*8]; Str2
0x140017b4d  call    cs:__imp__wcsnicmp
0x140017b54  nop     dword ptr [rax+rax+00h]
0x140017b59  test    eax, eax
0x140017b5b  jz      short loc_140017B72
0x140017b5d  inc     ebx
0x140017b5f  cmp     ebx, 0Eh
0x140017b62  jb      short loc_140017B38
0x140017b64  mov     qword ptr [rdi], 0
0x140017b6b  mov     eax, 0C0000073h
0x140017b70  jmp     short loc_140017BB5
0x140017b72  cmp     dword ptr [r12+rsi*8+8], 1
0x140017b78  mov     eax, [r12+rsi*8+14h]
0x140017b7d  lea     rdx, [r14+rax*2]
0x140017b81  mov     [r15], rdx
0x140017b84  jnz     short loc_140017B9E
0x140017b86  mov     dl, 20h ; ' '; MinorVersion
0x140017b88  mov     cl, 1; MajorVersion
0x140017b8a  call    cs:__imp_IoIsWdmVersionAvailable
0x140017b91  nop     dword ptr [rax+rax+00h]
0x140017b96  test    al, al
0x140017b98  jnz     short loc_140017B9E
0x140017b9a  xor     eax, eax
0x140017b9c  jmp     short loc_140017BB0
0x140017b9e  mov     rax, cs:__imp_SeExports
0x140017ba5  mov     rdx, [r12+rsi*8]
0x140017ba9  mov     rcx, [rax]
0x140017bac  mov     rax, [rdx+rcx]
0x140017bb0  mov     [rdi], rax
0x140017bb3  xor     eax, eax
0x140017bb5  add     rsp, 28h
0x140017bb9  pop     r15
0x140017bbb  pop     r14
0x140017bbd  pop     r12
0x140017bbf  pop     rdi
0x140017bc0  pop     rsi
0x140017bc1  pop     rbx
0x140017bc2  retn
```
