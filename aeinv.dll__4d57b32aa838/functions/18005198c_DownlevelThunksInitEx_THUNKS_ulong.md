# DownlevelThunksInitEx(THUNKS *,ulong)

- ea: `0x18005198c`
- end: `0x180051a0f`
- name: `?DownlevelThunksInitEx@@YAHPEAUTHUNKS@@K@Z`
- size: `131`
- prototype: `__int64 __fastcall(struct THUNKS *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031a40`
- `0x180045740`
- `0x180057730`
- `0x180058940`
- `0x180061a00`
- `0x1800629a0`

## callees

- `0x18005198c`
- `0x180070c98`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800519b9`
- `KERNEL32!LoadLibraryExW` at `0x1800519b9`
- `KERNEL32!GetProcAddress` at `0x1800519d1`
- `KERNEL32!GetProcAddress` at `0x1800519d1`

## pseudocode

```c
__int64 __fastcall DownlevelThunksInitEx(struct THUNKS *a1)
{
  __int64 i; // rbx
  HMODULE Library; // rax

  for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
  {
    Library = LoadLibraryExW((LPCWSTR)*(&g_ThunksInitRightAway + 5 * i), 0, 0x800u);
    *(&g_ThunksInitRightAway + 5 * i + 2) = (struct THUNKS near *)Library;
    if ( Library )
    {
      *(_QWORD *)*(&g_ThunksInitRightAway + 5 * i + 3) = GetProcAddress(
                                                           Library,
                                                           (LPCSTR)*(&g_ThunksInitRightAway + 5 * i + 1));
      if ( *(_QWORD *)*(&g_ThunksInitRightAway + 5 * i + 3) )
        continue;
    }
    DownlevelThunksFree();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18005198c  mov     [rsp+arg_0], rbx
0x180051991  mov     [rsp+arg_8], rsi
0x180051996  push    rdi
0x180051997  sub     rsp, 20h
0x18005199b  xor     ebx, ebx
0x18005199d  lea     rsi, ?g_ThunksInitRightAway@@3PAUTHUNKS@@A; THUNKS near * g_ThunksInitRightAway
0x1800519a4  cmp     ebx, 0Bh
0x1800519a7  jnb     short loc_1800519FA
0x1800519a9  lea     rdi, [rbx+rbx*4]
0x1800519ad  xor     edx, edx; hFile
0x1800519af  mov     rcx, [rsi+rdi*8]; lpLibFileName
0x1800519b3  mov     r8d, 800h; dwFlags
0x1800519b9  call    cs:__imp_LoadLibraryExW
0x1800519bf  mov     [rsi+rdi*8+10h], rax
0x1800519c4  test    rax, rax
0x1800519c7  jz      short loc_1800519F1
0x1800519c9  mov     rdx, [rsi+rdi*8+8]; lpProcName
0x1800519ce  mov     rcx, rax; hModule
0x1800519d1  call    cs:__imp_GetProcAddress
0x1800519d7  mov     rcx, rax
0x1800519da  mov     rax, [rsi+rdi*8+18h]
0x1800519df  mov     [rax], rcx
0x1800519e2  mov     rax, [rsi+rdi*8+18h]
0x1800519e7  cmp     qword ptr [rax], 0
0x1800519eb  jz      short loc_1800519F1
0x1800519ed  inc     ebx
0x1800519ef  jmp     short loc_1800519A4
0x1800519f1  call    ?DownlevelThunksFree@@YAXXZ; DownlevelThunksFree(void)
0x1800519f6  xor     eax, eax
0x1800519f8  jmp     short loc_1800519FF
0x1800519fa  mov     eax, 1
0x1800519ff  mov     rbx, [rsp+28h+arg_0]
0x180051a04  mov     rsi, [rsp+28h+arg_8]
0x180051a09  add     rsp, 20h
0x180051a0d  pop     rdi
0x180051a0e  retn
```
