# LoadRawBinaryData

- ea: `0x18005c098`
- end: `0x18005c150`
- name: `LoadRawBinaryData`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800041a0`

## callees

- `0x180054dec`
- `0x1800564d8`
- `0x18005c098`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005c135`
- `KERNEL32!LocalFree` at `0x18005c135`
- `USER32!GetAppCompatFlags2` at `0x18005c11d`
- `USER32!GetAppCompatFlags2` at `0x18005c11d`

## pseudocode

```c
_DWORD *__fastcall LoadRawBinaryData(wchar_t *a1, int a2)
{
  _DWORD *CachedBinaryData; // rbx
  char *v5; // rdi
  char *v6; // rax

  if ( !a1 )
    return 0;
  CachedBinaryData = PpdLoadCachedBinaryData(a1);
  if ( !CachedBinaryData )
  {
    CachedBinaryData = PpdParseTextFile(a1, a2);
    if ( !CachedBinaryData )
      return CachedBinaryData;
  }
  if ( CachedBinaryData[14] )
    v5 = (char *)CachedBinaryData + (unsigned int)CachedBinaryData[14];
  else
    v5 = 0;
  if ( CachedBinaryData[15] )
    v6 = (char *)CachedBinaryData + (unsigned int)CachedBinaryData[15];
  else
    v6 = 0;
  if ( !v5 || !v6 )
  {
    LocalFree(CachedBinaryData);
    return 0;
  }
  *((_QWORD *)CachedBinaryData + 5) = 0;
  *((_QWORD *)CachedBinaryData + 6) = CachedBinaryData;
  *((_QWORD *)v5 + 40) = CachedBinaryData;
  *((_QWORD *)v5 + 41) = CachedBinaryData;
  if ( (GetAppCompatFlags2(1024) & 0x1000) != 0 )
    *((_DWORD *)v5 + 35) &= ~0x20u;
  return CachedBinaryData;
}

```

## disassembly

```asm
0x18005c098  mov     [rsp+arg_0], rbx
0x18005c09d  mov     [rsp+arg_8], rsi
0x18005c0a2  push    rdi
0x18005c0a3  sub     rsp, 20h
0x18005c0a7  mov     esi, edx
0x18005c0a9  mov     rdi, rcx
0x18005c0ac  test    rcx, rcx
0x18005c0af  jz      loc_18005C13B
0x18005c0b5  call    PpdLoadCachedBinaryData
0x18005c0ba  mov     rbx, rax
0x18005c0bd  test    rax, rax
0x18005c0c0  jnz     short loc_18005C0D4
0x18005c0c2  mov     edx, esi
0x18005c0c4  mov     rcx, rdi
0x18005c0c7  call    PpdParseTextFile
0x18005c0cc  mov     rbx, rax
0x18005c0cf  test    rax, rax
0x18005c0d2  jz      short loc_18005C13D
0x18005c0d4  cmp     dword ptr [rbx+38h], 0
0x18005c0d8  jz      short loc_18005C0E2
0x18005c0da  mov     edi, [rbx+38h]
0x18005c0dd  add     rdi, rbx
0x18005c0e0  jmp     short loc_18005C0E4
0x18005c0e2  xor     edi, edi
0x18005c0e4  cmp     dword ptr [rbx+3Ch], 0
0x18005c0e8  jz      short loc_18005C0F2
0x18005c0ea  mov     eax, [rbx+3Ch]
0x18005c0ed  add     rax, rbx
0x18005c0f0  jmp     short loc_18005C0F4
0x18005c0f2  xor     eax, eax
0x18005c0f4  test    rdi, rdi
0x18005c0f7  jz      short loc_18005C132
0x18005c0f9  test    rax, rax
0x18005c0fc  jz      short loc_18005C132
0x18005c0fe  mov     qword ptr [rbx+28h], 0
0x18005c106  mov     ecx, 400h
0x18005c10b  mov     [rbx+30h], rbx
0x18005c10f  mov     [rdi+140h], rbx
0x18005c116  mov     [rdi+148h], rbx
0x18005c11d  call    cs:__imp_GetAppCompatFlags2
0x18005c123  bt      eax, 0Ch
0x18005c127  jnb     short loc_18005C13D
0x18005c129  and     dword ptr [rdi+8Ch], 0FFFFFFDFh
0x18005c130  jmp     short loc_18005C13D
0x18005c132  mov     rcx, rbx; hMem
0x18005c135  call    cs:__imp_LocalFree
0x18005c13b  xor     ebx, ebx
0x18005c13d  mov     rsi, [rsp+28h+arg_8]
0x18005c142  mov     rax, rbx
0x18005c145  mov     rbx, [rsp+28h+arg_0]
0x18005c14a  add     rsp, 20h
0x18005c14e  pop     rdi
0x18005c14f  retn
```
