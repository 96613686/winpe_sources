# AfxCreateDC(void *,void *)

- ea: `0x18005aaf0`
- end: `0x18005ab7c`
- name: `?AfxCreateDC@@YAPEAUHDC__@@PEAX0@Z`
- size: `140`
- prototype: `HDC __fastcall(HGLOBAL hMem, HGLOBAL)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18005ac00`
- `0x18005ac20`
- `0x180071690`

## callees

- `0x18005aaf0`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x18005ab51`
- `KERNEL32!GlobalUnlock` at `0x18005ab5f`
- `KERNEL32!GlobalUnlock` at `0x18005ab51`
- `KERNEL32!GlobalUnlock` at `0x18005ab5f`
- `KERNEL32!GlobalLock` at `0x18005ab0a`
- `KERNEL32!GlobalLock` at `0x18005ab1b`
- `KERNEL32!GlobalLock` at `0x18005ab0a`
- `KERNEL32!GlobalLock` at `0x18005ab1b`
- `GDI32!CreateDCW` at `0x18005ab45`
- `GDI32!CreateDCW` at `0x18005ab45`

## pseudocode

```c
HDC __fastcall AfxCreateDC(HGLOBAL hMem, HGLOBAL a2)
{
  unsigned __int16 *v4; // rdi
  const DEVMODEW *v5; // r9
  HDC DCW; // rdi

  if ( !hMem )
    return 0;
  v4 = (unsigned __int16 *)GlobalLock(hMem);
  v5 = a2 ? (const DEVMODEW *)GlobalLock(a2) : 0LL;
  if ( !v4 )
    return 0;
  DCW = CreateDCW(&v4[*v4], &v4[v4[1]], &v4[v4[2]], v5);
  GlobalUnlock(hMem);
  if ( a2 )
    GlobalUnlock(a2);
  return DCW;
}

```

## disassembly

```asm
0x18005aaf0  mov     [rsp+arg_0], rbx
0x18005aaf5  mov     [rsp+arg_8], rsi
0x18005aafa  push    rdi
0x18005aafb  sub     rsp, 20h
0x18005aaff  mov     rbx, rdx
0x18005ab02  mov     rsi, rcx
0x18005ab05  test    rcx, rcx
0x18005ab08  jz      short loc_18005AB6A
0x18005ab0a  call    cs:__imp_GlobalLock
0x18005ab10  mov     rdi, rax
0x18005ab13  test    rbx, rbx
0x18005ab16  jz      short loc_18005AB26
0x18005ab18  mov     rcx, rbx; hMem
0x18005ab1b  call    cs:__imp_GlobalLock
0x18005ab21  mov     r9, rax
0x18005ab24  jmp     short loc_18005AB29
0x18005ab26  xor     r9d, r9d; pdm
0x18005ab29  test    rdi, rdi
0x18005ab2c  jz      short loc_18005AB6A
0x18005ab2e  movzx   eax, word ptr [rdi+4]
0x18005ab32  lea     r8, [rdi+rax*2]; pszPort
0x18005ab36  movzx   eax, word ptr [rdi+2]
0x18005ab3a  lea     rdx, [rdi+rax*2]; pwszDevice
0x18005ab3e  movzx   eax, word ptr [rdi]
0x18005ab41  lea     rcx, [rdi+rax*2]; pwszDriver
0x18005ab45  call    cs:__imp_CreateDCW
0x18005ab4b  mov     rcx, rsi; hMem
0x18005ab4e  mov     rdi, rax
0x18005ab51  call    cs:__imp_GlobalUnlock
0x18005ab57  test    rbx, rbx
0x18005ab5a  jz      short loc_18005AB65
0x18005ab5c  mov     rcx, rbx; hMem
0x18005ab5f  call    cs:__imp_GlobalUnlock
0x18005ab65  mov     rax, rdi
0x18005ab68  jmp     short loc_18005AB6C
0x18005ab6a  xor     eax, eax
0x18005ab6c  mov     rbx, [rsp+28h+arg_0]
0x18005ab71  mov     rsi, [rsp+28h+arg_8]
0x18005ab76  add     rsp, 20h
0x18005ab7a  pop     rdi
0x18005ab7b  retn
```
