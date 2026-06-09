# FileReader::~FileReader(void)

- ea: `0x18000ae20`
- end: `0x18000ae3c`
- name: `??1FileReader@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(void **this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee9e`
- `0x18000eec2`
- `0x18000ef28`

## callees

- `0x18000ae20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ae31`

## pseudocode

```c
void __fastcall FileReader::~FileReader(void **this)
{
  char *v1; // rcx

  v1 = (char *)*this;
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
}

```

## disassembly

```asm
0x18000ae20  sub     rsp, 28h
0x18000ae24  mov     rcx, [rcx]; hObject
0x18000ae27  lea     rax, [rcx-1]
0x18000ae2b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ae2f  ja      short loc_18000AE37
0x18000ae31  call    cs:__imp_CloseHandle
0x18000ae37  add     rsp, 28h
0x18000ae3b  retn
```
