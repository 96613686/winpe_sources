# SepSddlGetSidForString

- ea: `0x140025078`
- end: `0x140025124`
- name: `SepSddlGetSidForString`
- size: `172`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140024cb8`

## callees

- `0x140025078`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400250ea`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x1400250ea`
- `ntoskrnl!_wcsnicmp` at `0x1400250ad`
- `ntoskrnl!_wcsnicmp` at `0x1400250ad`
- `ntoskrnl!SeExports` at `0x1400250fe`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  bool v8; // zf
  __int64 v9; // rax

  v6 = 0;
  while ( _wcsnicmp(Str1, (const wchar_t *)&qword_14001F1E0[3 * v6 + 1] + 2, HIDWORD(qword_14001F1E0[3 * v6 + 2])) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
  }
  v8 = LODWORD(qword_14001F1E0[3 * v6 + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_14001F1E0[3 * v6 + 2])];
  if ( !v8 || IoIsWdmVersionAvailable(1u, 0x20u) )
    v9 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_14001F1E0[3 * v6]);
  else
    v9 = 0;
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x140025078  push    rbx
0x14002507a  push    rsi
0x14002507b  push    rdi
0x14002507c  push    r12
0x14002507e  push    r14
0x140025080  push    r15
0x140025082  sub     rsp, 28h
0x140025086  mov     r15, r8
0x140025089  lea     r12, qword_14001F1E0
0x140025090  mov     rdi, rdx
0x140025093  mov     r14, rcx
0x140025096  xor     ebx, ebx
0x140025098  lea     rsi, [rbx+rbx*2]
0x14002509c  mov     rcx, r14; Str1
0x14002509f  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x1400250a4  lea     rdx, [r12+0Ch]
0x1400250a9  lea     rdx, [rdx+rsi*8]; Str2
0x1400250ad  call    cs:__imp__wcsnicmp
0x1400250b4  nop     dword ptr [rax+rax+00h]
0x1400250b9  test    eax, eax
0x1400250bb  jz      short loc_1400250D2
0x1400250bd  inc     ebx
0x1400250bf  cmp     ebx, 0Eh
0x1400250c2  jb      short loc_140025098
0x1400250c4  mov     qword ptr [rdi], 0
0x1400250cb  mov     eax, 0C0000073h
0x1400250d0  jmp     short loc_140025115
0x1400250d2  cmp     dword ptr [r12+rsi*8+8], 1
0x1400250d8  mov     eax, [r12+rsi*8+14h]
0x1400250dd  lea     rdx, [r14+rax*2]
0x1400250e1  mov     [r15], rdx
0x1400250e4  jnz     short loc_1400250FE
0x1400250e6  mov     dl, 20h ; ' '; MinorVersion
0x1400250e8  mov     cl, 1; MajorVersion
0x1400250ea  call    cs:__imp_IoIsWdmVersionAvailable
0x1400250f1  nop     dword ptr [rax+rax+00h]
0x1400250f6  test    al, al
0x1400250f8  jnz     short loc_1400250FE
0x1400250fa  xor     eax, eax
0x1400250fc  jmp     short loc_140025110
0x1400250fe  mov     rax, cs:__imp_SeExports
0x140025105  mov     rdx, [r12+rsi*8]
0x140025109  mov     rcx, [rax]
0x14002510c  mov     rax, [rdx+rcx]
0x140025110  mov     [rdi], rax
0x140025113  xor     eax, eax
0x140025115  add     rsp, 28h
0x140025119  pop     r15
0x14002511b  pop     r14
0x14002511d  pop     r12
0x14002511f  pop     rdi
0x140025120  pop     rsi
0x140025121  pop     rbx
0x140025122  retn
```
