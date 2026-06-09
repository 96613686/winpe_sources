# _AfxCreateMemoryStream(void)

- ea: `0x1800c3ab0`
- end: `0x1800c3b03`
- name: `?_AfxCreateMemoryStream@@YAPEAUIStream@@XZ`
- size: `83`
- prototype: `struct IStream *(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800c3360`
- `0x1800c3e30`
- `0x1800c3ecc`

## callees

- `0x1800c3ab0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c3ae1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c3ae1`
- `KERNEL32!GlobalFree` at `0x1800c3aee`
- `KERNEL32!GlobalFree` at `0x1800c3aee`
- `KERNEL32!GlobalAlloc` at `0x1800c3ac6`
- `KERNEL32!GlobalAlloc` at `0x1800c3ac6`

## pseudocode

```c
LPSTREAM _AfxCreateMemoryStream(void)
{
  HGLOBAL v0; // rax
  void *v1; // rbx
  LPSTREAM ppstm; // [rsp+30h] [rbp+8h] BYREF

  ppstm = 0;
  v0 = GlobalAlloc(0x2002u, 0);
  v1 = v0;
  if ( !v0 )
    return 0;
  if ( CreateStreamOnHGlobal(v0, 1, &ppstm) < 0 )
  {
    GlobalFree(v1);
    return 0;
  }
  return ppstm;
}

```

## disassembly

```asm
0x1800c3ab0  push    rbx
0x1800c3ab2  sub     rsp, 20h
0x1800c3ab6  xor     edx, edx; dwBytes
0x1800c3ab8  mov     [rsp+28h+ppstm], 0
0x1800c3ac1  mov     ecx, 2002h; uFlags
0x1800c3ac6  call    cs:__imp_GlobalAlloc
0x1800c3acc  mov     rbx, rax
0x1800c3acf  test    rax, rax
0x1800c3ad2  jz      short loc_1800C3AF4
0x1800c3ad4  lea     r8, [rsp+28h+ppstm]; ppstm
0x1800c3ad9  mov     edx, 1; fDeleteOnRelease
0x1800c3ade  mov     rcx, rax; hGlobal
0x1800c3ae1  call    cs:__imp_CreateStreamOnHGlobal
0x1800c3ae7  test    eax, eax
0x1800c3ae9  jns     short loc_1800C3AFC
0x1800c3aeb  mov     rcx, rbx; hMem
0x1800c3aee  call    cs:__imp_GlobalFree
0x1800c3af4  xor     eax, eax
0x1800c3af6  add     rsp, 20h
0x1800c3afa  pop     rbx
0x1800c3afb  retn
0x1800c3afc  mov     rax, [rsp+28h+ppstm]
0x1800c3b01  jmp     short loc_1800C3AF6
```
