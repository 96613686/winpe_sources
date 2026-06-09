# SepSddlGetSidForString

- ea: `0x14000db84`
- end: `0x14000dc35`
- name: `SepSddlGetSidForString`
- size: `177`
- prototype: `__int64 __fastcall(wchar_t *Str1)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d7c8`

## callees

- `0x14000db84`

## import_xrefs

- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000dbea`
- `ntoskrnl!IoIsWdmVersionAvailable` at `0x14000dbea`
- `ntoskrnl!_wcsnicmp` at `0x14000dbbe`
- `ntoskrnl!_wcsnicmp` at `0x14000dbbe`
- `ntoskrnl!SeExports` at `0x14000dc01`

## pseudocode

```c
__int64 __fastcall SepSddlGetSidForString(wchar_t *Str1, _QWORD *a2, _QWORD *a3)
{
  __int64 i; // rbx
  bool v7; // zf
  __int64 v8; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0xE )
    {
      *a2 = 0;
      return 3221225587LL;
    }
    if ( !_wcsnicmp(Str1, (const wchar_t *)&qword_140007210[3 * i + 1] + 2, HIDWORD(qword_140007210[3 * i + 2])) )
      break;
  }
  v7 = LODWORD(qword_140007210[3 * i + 1]) == 1;
  *a3 = &Str1[HIDWORD(qword_140007210[3 * i + 2])];
  if ( !v7 || IoIsWdmVersionAvailable(1u, 0x20u) )
  {
    _mm_lfence();
    v8 = *(__int64 *)((char *)&SeExports->SeCreateTokenPrivilege + qword_140007210[3 * i]);
  }
  else
  {
    v8 = 0;
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x14000db84  push    rbx
0x14000db86  push    rsi
0x14000db87  push    rdi
0x14000db88  push    r12
0x14000db8a  push    r14
0x14000db8c  push    r15
0x14000db8e  sub     rsp, 28h
0x14000db92  mov     r15, r8
0x14000db95  lea     r12, qword_140007210
0x14000db9c  mov     rdi, rdx
0x14000db9f  mov     r14, rcx
0x14000dba2  xor     ebx, ebx
0x14000dba4  cmp     ebx, 0Eh
0x14000dba7  jnb     short loc_14000DC1A
0x14000dba9  lea     rsi, [rbx+rbx*2]
0x14000dbad  mov     rcx, r14; Str1
0x14000dbb0  mov     r8d, [r12+rsi*8+14h]; MaxCount
0x14000dbb5  lea     rdx, [r12+0Ch]
0x14000dbba  lea     rdx, [rdx+rsi*8]; Str2
0x14000dbbe  call    cs:__imp__wcsnicmp
0x14000dbc5  nop     dword ptr [rax+rax+00h]
0x14000dbca  test    eax, eax
0x14000dbcc  jz      short loc_14000DBD2
0x14000dbce  inc     ebx
0x14000dbd0  jmp     short loc_14000DBA4
0x14000dbd2  cmp     dword ptr [r12+rsi*8+8], 1
0x14000dbd8  mov     eax, [r12+rsi*8+14h]
0x14000dbdd  lea     rdx, [r14+rax*2]
0x14000dbe1  mov     [r15], rdx
0x14000dbe4  jnz     short loc_14000DBFE
0x14000dbe6  mov     dl, 20h ; ' '; MinorVersion
0x14000dbe8  mov     cl, 1; MajorVersion
0x14000dbea  call    cs:__imp_IoIsWdmVersionAvailable
0x14000dbf1  nop     dword ptr [rax+rax+00h]
0x14000dbf6  test    al, al
0x14000dbf8  jnz     short loc_14000DBFE
0x14000dbfa  xor     eax, eax
0x14000dbfc  jmp     short loc_14000DC13
0x14000dbfe  lfence
0x14000dc01  mov     rax, cs:__imp_SeExports
0x14000dc08  mov     rdx, [r12+rsi*8]
0x14000dc0c  mov     rcx, [rax]
0x14000dc0f  mov     rax, [rdx+rcx]
0x14000dc13  mov     [rdi], rax
0x14000dc16  xor     eax, eax
0x14000dc18  jmp     short loc_14000DC26
0x14000dc1a  mov     qword ptr [rdi], 0
0x14000dc21  mov     eax, 0C0000073h
0x14000dc26  add     rsp, 28h
0x14000dc2a  pop     r15
0x14000dc2c  pop     r14
0x14000dc2e  pop     r12
0x14000dc30  pop     rdi
0x14000dc31  pop     rsi
0x14000dc32  pop     rbx
0x14000dc33  retn
```
