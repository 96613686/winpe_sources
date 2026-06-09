# Dns_Allocate

- ea: `0x180012564`
- end: `0x1800125cc`
- name: `Dns_Allocate`
- size: `104`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x180004310`
- `0x1800054bc`
- `0x180005924`
- `0x18000604c`
- `0x180007988`
- `0x180007b64`
- `0x180008190`
- `0x180008cd0`
- `0x180008e40`
- `0x180009808`
- `0x180009e20`
- `0x18000b924`
- `0x18000bc50`
- `0x18000bfac`
- `0x18000c224`
- `0x18000c8a8`
- `0x18000cee8`
- `0x18000d0a0`
- `0x18000d1e0`
- `0x18000d308`
- `0x18000d5b4`
- `0x18000e080`
- `0x18000e3c8`
- `0x18000ea2c`
- `0x18000f9c8`
- `0x18001036c`
- `0x1800105c0`
- `0x180010c18`
- `0x180011858`
- `0x180011b68`
- `0x180011f68`
- `0x1800126d8`
- `0x180012838`

## callees

- `0x180012564`
- `0x1800169dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800125c5`

## pseudocode

```c
LPVOID __fastcall Dns_Allocate(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  if ( a1 < 0xFFFFFFFF )
  {
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    return HeapAlloc(ProcessHeap, 8u, a1);
  }
  else
  {
    if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
      WPP_SF_I(a1, 11, WPP_e22cb926269535d6dc55362815cfdfdf_Traceguids, a1);
    return 0;
  }
}

```

## disassembly

```asm
0x180012564  push    rbx
0x180012566  sub     rsp, 20h
0x18001256a  mov     eax, 0FFFFFFFFh
0x18001256f  mov     rbx, rcx
0x180012572  cmp     rcx, rax
0x180012575  jb      short loc_18001259C
0x180012577  test    byte ptr cs:xmmword_18001F260+1, 8
0x18001257e  jz      short loc_180012594
0x180012580  mov     edx, 0Bh
0x180012585  lea     r8, WPP_e22cb926269535d6dc55362815cfdfdf_Traceguids
0x18001258c  mov     r9, rcx
0x18001258f  call    WPP_SF_I
0x180012594  xor     eax, eax
0x180012596  add     rsp, 20h
0x18001259a  pop     rbx
0x18001259b  retn
0x18001259c  mov     rax, cs:g_hProcessHeap
0x1800125a3  test    rax, rax
0x1800125a6  jnz     short loc_1800125B5
0x1800125a8  call    cs:__imp_GetProcessHeap
0x1800125ae  mov     cs:g_hProcessHeap, rax
0x1800125b5  mov     r8, rbx
0x1800125b8  mov     edx, 8
0x1800125bd  mov     rcx, rax
0x1800125c0  add     rsp, 20h
0x1800125c4  pop     rbx
0x1800125c5  jmp     cs:__imp_HeapAlloc
```
