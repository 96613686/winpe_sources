# _wsplitpath_s

- ea: `0x1800240b0`
- end: `0x180024113`
- name: `_wsplitpath_s`
- size: `99`
- prototype: `errno_t __cdecl(const wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006590`

## callees

- `0x180023e3c`

## pseudocode

```c
errno_t __cdecl wsplitpath_s(
        const wchar_t *FullPath,
        wchar_t *Drive,
        size_t DriveCount,
        wchar_t *Dir,
        size_t DirCount,
        wchar_t *Filename,
        size_t FilenameCount,
        wchar_t *Ext,
        size_t ExtCount)
{
  _QWORD v10[9]; // [rsp+20h] [rbp-48h] BYREF

  v10[3] = DirCount;
  v10[4] = Filename;
  v10[5] = FilenameCount;
  v10[6] = Ext;
  v10[0] = Drive;
  v10[1] = DriveCount;
  v10[2] = Dir;
  v10[7] = ExtCount;
  return common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630_(
           (wchar_t *)FullPath,
           (wchar_t *)v10,
           0);
}

```

## disassembly

```asm
0x1800240b0  mov     r11, rsp
0x1800240b3  sub     rsp, 68h
0x1800240b7  mov     rax, [rsp+68h+DirCount]
0x1800240bf  mov     [r11-30h], rax
0x1800240c3  mov     rax, [rsp+68h+Filename]
0x1800240cb  mov     [r11-28h], rax
0x1800240cf  mov     rax, [rsp+68h+FilenameCount]
0x1800240d7  mov     [r11-20h], rax
0x1800240db  mov     rax, [rsp+68h+Ext]
0x1800240e3  mov     [r11-18h], rax
0x1800240e7  mov     rax, [rsp+68h+ExtCount]
0x1800240ef  mov     [r11-48h], rdx
0x1800240f3  lea     rdx, [r11-48h]
0x1800240f7  mov     [r11-40h], r8
0x1800240fb  xor     r8d, r8d
0x1800240fe  mov     [r11-38h], r9
0x180024102  xor     r9d, r9d
0x180024105  mov     [r11-10h], rax
0x180024109  call    common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630___; common_splitpath_internal_wchar_t__lambda_f4d89ce576adf8640f5662d60a8d4afb___lambda_b90d8f84996fccaedfcae156869b1630_
0x18002410e  add     rsp, 68h
0x180024112  retn
```
