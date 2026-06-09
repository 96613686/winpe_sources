# SrvWriteConsoleOutputString

- ea: `0x1400206a0`
- end: `0x140020745`
- name: `SrvWriteConsoleOutputString`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1400206a0`
- `0x140021738`
- `0x140021890`
- `0x1400219e4`
- `0x140021e10`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020734`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020734`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400206c3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400206c3`

## pseudocode

```c
__int64 __fastcall SrvWriteConsoleOutputString(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v4; // edi
  NTSTATUS v5; // eax

  v1 = *(_QWORD *)(a1 + 328);
  if ( !v1 )
    return 3221225480LL;
  RtlAcquireSRWLockExclusive(a1 + 48);
  switch ( *(_DWORD *)(a1 + 364) )
  {
    case 1:
      v5 = CspWriteOutputCharacterA(a1, v1 + 24);
LABEL_11:
      v4 = v5;
      if ( v5 >= 0 && v1 == *(_QWORD *)(a1 + 96) )
        CspTriggerScreenRedraw(a1, a1 + 216, 0);
      goto LABEL_14;
    case 2:
      goto LABEL_9;
    case 3:
      v5 = CspWriteOutputAttribute(a1, v1 + 24);
      goto LABEL_11;
    case 4:
LABEL_9:
      v5 = CspWriteOutputCharacter(a1, v1 + 24);
      goto LABEL_11;
  }
  v4 = -1073741811;
LABEL_14:
  RtlReleaseSRWLockExclusive(a1 + 48);
  return v4;
}

```

## disassembly

```asm
0x1400206a0  push    rbx
0x1400206a2  push    rbp
0x1400206a3  push    rsi
0x1400206a4  push    rdi
0x1400206a5  sub     rsp, 28h
0x1400206a9  mov     rsi, [rcx+148h]
0x1400206b0  mov     rbx, rcx
0x1400206b3  test    rsi, rsi
0x1400206b6  jnz     short loc_1400206BF
0x1400206b8  mov     eax, 0C0000008h
0x1400206bd  jmp     short loc_14002073C
0x1400206bf  add     rcx, 30h ; '0'
0x1400206c3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400206c9  mov     ecx, [rbx+16Ch]
0x1400206cf  sub     ecx, 1
0x1400206d2  jz      short loc_140020706
0x1400206d4  sub     ecx, 1
0x1400206d7  jz      short loc_1400206F8
0x1400206d9  sub     ecx, 1
0x1400206dc  jz      short loc_1400206EA
0x1400206de  cmp     ecx, 1
0x1400206e1  jz      short loc_1400206F8
0x1400206e3  mov     edi, 0C000000Dh
0x1400206e8  jmp     short loc_140020730
0x1400206ea  lea     rdx, [rsi+18h]
0x1400206ee  mov     rcx, rbx
0x1400206f1  call    CspWriteOutputAttribute
0x1400206f6  jmp     short loc_140020712
0x1400206f8  lea     rdx, [rsi+18h]
0x1400206fc  mov     rcx, rbx
0x1400206ff  call    CspWriteOutputCharacter
0x140020704  jmp     short loc_140020712
0x140020706  lea     rdx, [rsi+18h]
0x14002070a  mov     rcx, rbx
0x14002070d  call    CspWriteOutputCharacterA
0x140020712  mov     edi, eax
0x140020714  test    eax, eax
0x140020716  js      short loc_140020730
0x140020718  cmp     rsi, [rbx+60h]
0x14002071c  jnz     short loc_140020730
0x14002071e  lea     rdx, [rbx+0D8h]
0x140020725  xor     r8d, r8d
0x140020728  mov     rcx, rbx
0x14002072b  call    CspTriggerScreenRedraw
0x140020730  lea     rcx, [rbx+30h]
0x140020734  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14002073a  mov     eax, edi
0x14002073c  add     rsp, 28h
0x140020740  pop     rdi
0x140020741  pop     rsi
0x140020742  pop     rbp
0x140020743  pop     rbx
0x140020744  retn
```
