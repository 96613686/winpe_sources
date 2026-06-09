# SiIsValidDiskDevice

- ea: `0x140032364`
- end: `0x140032431`
- name: `SiIsValidDiskDevice`
- size: `205`
- prototype: `char __fastcall(wchar_t *Str1, wchar_t *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140032438`

## callees

- `0x140032364`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140032380`
- `ntoskrnl!_wcsicmp` at `0x14003239c`
- `ntoskrnl!_wcsicmp` at `0x140032380`
- `ntoskrnl!_wcsicmp` at `0x14003239c`
- `ntoskrnl!_wcsnicmp` at `0x1400323bc`
- `ntoskrnl!_wcsnicmp` at `0x1400323bc`

## string_xrefs

- `0x140032376`: `Directory`
- `0x140032392`: `SymbolicLink`

## pseudocode

```c
char __fastcall SiIsValidDiskDevice(wchar_t *Str1, wchar_t *a2, int *a3)
{
  wchar_t *v6; // r8
  wchar_t v7; // dx
  int v8; // ecx
  __int16 v10; // r9

  if ( _wcsicmp(a2, L"Directory") && _wcsicmp(a2, L"SymbolicLink") )
    return 0;
  if ( _wcsnicmp(Str1, L"Harddisk", 8u) )
    return 0;
  v6 = Str1 + 8;
  v7 = Str1[8];
  if ( !v7 )
    return 0;
  v8 = 0;
  if ( v7 != 48 )
  {
    v10 = 0;
    while ( v7 )
    {
      if ( (unsigned __int16)(v7 - 48) > 9u )
        return 0;
      if ( (unsigned __int16)++v10 > 0xAu )
        return 0;
      ++v6;
      v8 = v7 + 2 * (5 * v8 - 24);
      v7 = *v6;
    }
    goto LABEL_7;
  }
  if ( Str1[9] )
    return 0;
LABEL_7:
  if ( a3 )
    *a3 = v8;
  return 1;
}

```

## disassembly

```asm
0x140032364  push    rbx
0x140032366  push    rbp
0x140032367  push    rsi
0x140032368  push    rdi
0x140032369  sub     rsp, 28h
0x14003236d  mov     rsi, rdx
0x140032370  mov     rbx, rcx
0x140032373  mov     rcx, rsi; Str1
0x140032376  lea     rdx, aDirectory; "Directory"
0x14003237d  mov     rdi, r8
0x140032380  call    cs:__imp__wcsicmp
0x140032387  nop     dword ptr [rax+rax+00h]
0x14003238c  xor     ebp, ebp
0x14003238e  test    eax, eax
0x140032390  jz      short loc_1400323AC
0x140032392  lea     rdx, aSymboliclink; "SymbolicLink"
0x140032399  mov     rcx, rsi; Str1
0x14003239c  call    cs:__imp__wcsicmp
0x1400323a3  nop     dword ptr [rax+rax+00h]
0x1400323a8  test    eax, eax
0x1400323aa  jnz     short loc_140032425
0x1400323ac  mov     r8d, 8; MaxCount
0x1400323b2  lea     rdx, aHarddisk; "Harddisk"
0x1400323b9  mov     rcx, rbx; Str1
0x1400323bc  call    cs:__imp__wcsnicmp
0x1400323c3  nop     dword ptr [rax+rax+00h]
0x1400323c8  test    eax, eax
0x1400323ca  jnz     short loc_140032425
0x1400323cc  lea     r8, [rbx+10h]
0x1400323d0  movzx   edx, word ptr [r8]
0x1400323d4  test    dx, dx
0x1400323d7  jz      short loc_140032425
0x1400323d9  mov     ecx, ebp
0x1400323db  cmp     dx, 30h ; '0'
0x1400323df  jnz     short loc_1400323F3
0x1400323e1  cmp     [r8+2], bp
0x1400323e6  jnz     short loc_140032425
0x1400323e8  test    rdi, rdi
0x1400323eb  jz      short loc_1400323EF
0x1400323ed  mov     [rdi], ecx
0x1400323ef  mov     al, 1
0x1400323f1  jmp     short loc_140032427
0x1400323f3  mov     r9d, ebp
0x1400323f6  test    dx, dx
0x1400323f9  jz      short loc_1400323E8
0x1400323fb  lea     eax, [rdx-30h]
0x1400323fe  cmp     ax, 9
0x140032402  ja      short loc_140032425
0x140032404  inc     r9w
0x140032408  cmp     r9w, 0Ah
0x14003240d  ja      short loc_140032425
0x14003240f  movzx   eax, dx
0x140032412  lea     ecx, [rcx+rcx*4]
0x140032415  add     r8, 2
0x140032419  lea     ecx, [rcx-18h]
0x14003241c  lea     ecx, [rax+rcx*2]
0x14003241f  movzx   edx, word ptr [r8]
0x140032423  jmp     short loc_1400323F6
0x140032425  xor     al, al
0x140032427  add     rsp, 28h
0x14003242b  pop     rdi
0x14003242c  pop     rsi
0x14003242d  pop     rbp
0x14003242e  pop     rbx
0x14003242f  retn
```
