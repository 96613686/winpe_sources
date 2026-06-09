# LoadRawBinaryData

- ea: `0x18005dd18`
- end: `0x18005dddd`
- name: `LoadRawBinaryData`
- size: `197`
- prototype: `_DWORD *__fastcall(wchar_t *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004240`

## callees

- `0x1800567ec`
- `0x1800581bc`
- `0x18005dd18`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005ddbb`
- `KERNEL32!LocalFree` at `0x18005ddbb`
- `USER32!GetAppCompatFlags2` at `0x18005dd9d`
- `USER32!GetAppCompatFlags2` at `0x18005dd9d`

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
0x18005dd18  mov     [rsp+arg_0], rbx
0x18005dd1d  mov     [rsp+arg_8], rsi
0x18005dd22  push    rdi
0x18005dd23  sub     rsp, 20h
0x18005dd27  mov     esi, edx
0x18005dd29  mov     rdi, rcx
0x18005dd2c  test    rcx, rcx
0x18005dd2f  jz      loc_18005DDC7
0x18005dd35  call    PpdLoadCachedBinaryData
0x18005dd3a  mov     rbx, rax
0x18005dd3d  test    rax, rax
0x18005dd40  jnz     short loc_18005DD54
0x18005dd42  mov     edx, esi
0x18005dd44  mov     rcx, rdi
0x18005dd47  call    PpdParseTextFile
0x18005dd4c  mov     rbx, rax
0x18005dd4f  test    rax, rax
0x18005dd52  jz      short loc_18005DDC9
0x18005dd54  cmp     dword ptr [rbx+38h], 0
0x18005dd58  jz      short loc_18005DD62
0x18005dd5a  mov     edi, [rbx+38h]
0x18005dd5d  add     rdi, rbx
0x18005dd60  jmp     short loc_18005DD64
0x18005dd62  xor     edi, edi
0x18005dd64  cmp     dword ptr [rbx+3Ch], 0
0x18005dd68  jz      short loc_18005DD72
0x18005dd6a  mov     eax, [rbx+3Ch]
0x18005dd6d  add     rax, rbx
0x18005dd70  jmp     short loc_18005DD74
0x18005dd72  xor     eax, eax
0x18005dd74  test    rdi, rdi
0x18005dd77  jz      short loc_18005DDB8
0x18005dd79  test    rax, rax
0x18005dd7c  jz      short loc_18005DDB8
0x18005dd7e  mov     qword ptr [rbx+28h], 0
0x18005dd86  mov     ecx, 400h
0x18005dd8b  mov     [rbx+30h], rbx
0x18005dd8f  mov     [rdi+140h], rbx
0x18005dd96  mov     [rdi+148h], rbx
0x18005dd9d  call    cs:__imp_GetAppCompatFlags2
0x18005dda4  nop     dword ptr [rax+rax+00h]
0x18005dda9  bt      eax, 0Ch
0x18005ddad  jnb     short loc_18005DDC9
0x18005ddaf  and     dword ptr [rdi+8Ch], 0FFFFFFDFh
0x18005ddb6  jmp     short loc_18005DDC9
0x18005ddb8  mov     rcx, rbx; hMem
0x18005ddbb  call    cs:__imp_LocalFree
0x18005ddc2  nop     dword ptr [rax+rax+00h]
0x18005ddc7  xor     ebx, ebx
0x18005ddc9  mov     rsi, [rsp+28h+arg_8]
0x18005ddce  mov     rax, rbx
0x18005ddd1  mov     rbx, [rsp+28h+arg_0]
0x18005ddd6  add     rsp, 20h
0x18005ddda  pop     rdi
0x18005dddb  retn
```
