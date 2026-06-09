# __acrt_WideCharToMultiByte

- ea: `0x1800138a4`
- end: `0x180013951`
- name: `__acrt_WideCharToMultiByte`
- size: `173`
- prototype: `int __fastcall(UINT, int, const WCHAR *, int, CHAR *, int, const CHAR *, BOOL *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180010818`
- `0x1800122bc`
- `0x180012af4`
- `0x180013954`
- `0x180017a54`
- `0x180017ff8`
- `0x180018704`

## callees

- `0x1800138a4`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18001394a`

## pseudocode

```c
int __fastcall _acrt_WideCharToMultiByte(
        UINT a1,
        int a2,
        const WCHAR *a3,
        int a4,
        CHAR *a5,
        int a6,
        const CHAR *a7,
        BOOL *a8)
{
  int v10; // r8d
  bool v11; // zf
  DWORD v12; // edx
  BOOL *v14; // r8

  if ( a1 <= 0xC435 )
  {
    if ( a1 - 50220 <= 9 )
    {
      v10 = 679;
      if ( _bittest(&v10, a1 - 50220) )
        goto LABEL_12;
    }
    v11 = a1 == 42;
    goto LABEL_10;
  }
  if ( a1 == 54936 )
    goto LABEL_12;
  if ( a1 > 0xDEA9 )
  {
    if ( a1 <= 0xDEB3 || a1 == 65000 )
      goto LABEL_12;
    v11 = a1 == 65001;
LABEL_10:
    if ( !v11 )
      goto LABEL_11;
LABEL_12:
    v12 = 0;
    goto LABEL_13;
  }
LABEL_11:
  v12 = a2 & 0xFFFFFF7F;
LABEL_13:
  v14 = a8;
  if ( a1 - 65000 <= 1 )
  {
    v14 = 0;
    a7 = 0;
    if ( a8 )
      *a8 = 0;
  }
  return WideCharToMultiByte(a1, v12, a3, a4, a5, a6, a7, v14);
}

```

## disassembly

```asm
0x1800138a4  mov     [rsp+arg_0], rbx
0x1800138a9  push    rdi
0x1800138aa  lea     eax, [rcx-0FDE8h]
0x1800138b0  mov     r11d, r9d
0x1800138b3  cmp     eax, 1
0x1800138b6  mov     rbx, r8
0x1800138b9  setbe   r10b
0x1800138bd  xor     edi, edi
0x1800138bf  cmp     ecx, 0C435h
0x1800138c5  ja      short loc_1800138E3
0x1800138c7  lea     eax, [rcx-0C42Ch]
0x1800138cd  cmp     eax, 9
0x1800138d0  ja      short loc_1800138DE
0x1800138d2  mov     r8d, 2A7h
0x1800138d8  bt      r8d, eax
0x1800138dc  jb      short loc_180013911
0x1800138de  cmp     ecx, 2Ah ; '*'
0x1800138e1  jmp     short loc_180013909
0x1800138e3  cmp     ecx, 0D698h
0x1800138e9  jz      short loc_180013911
0x1800138eb  cmp     ecx, 0DEA9h
0x1800138f1  jbe     short loc_18001390B
0x1800138f3  cmp     ecx, 0DEB3h
0x1800138f9  jbe     short loc_180013911
0x1800138fb  cmp     ecx, 0FDE8h
0x180013901  jz      short loc_180013911
0x180013903  cmp     ecx, 0FDE9h
0x180013909  jz      short loc_180013911
0x18001390b  btr     edx, 7
0x18001390f  jmp     short loc_180013913
0x180013911  mov     edx, edi
0x180013913  mov     rax, [rsp+8+arg_38]
0x180013918  test    r10b, r10b
0x18001391b  mov     r9, [rsp+8+arg_30]
0x180013920  mov     r8, rax
0x180013923  cmovnz  r8, rdi
0x180013927  cmovnz  r9, rdi
0x18001392b  jz      short loc_180013934
0x18001392d  test    rax, rax
0x180013930  jz      short loc_180013934
0x180013932  mov     [rax], edi
0x180013934  mov     [rsp+8+arg_38], r8
0x180013939  mov     r8, rbx
0x18001393c  mov     [rsp+8+arg_30], r9
0x180013941  mov     r9d, r11d
0x180013944  mov     rbx, [rsp+8+arg_0]
0x180013949  pop     rdi
0x18001394a  jmp     cs:__imp_WideCharToMultiByte
```
