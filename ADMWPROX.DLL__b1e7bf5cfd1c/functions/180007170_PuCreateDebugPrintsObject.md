# PuCreateDebugPrintsObject

- ea: `0x180007170`
- end: `0x18000722b`
- name: `PuCreateDebugPrintsObject`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002400`

## callees

- `0x180007170`
- `0x1800083de`

## import_xrefs

- `msvcrt!strcpy_s` at `0x1800071a1`
- `msvcrt!strcpy_s` at `0x1800071a1`
- `KERNEL32!GetStdHandle` at `0x1800071e6`
- `KERNEL32!GetStdHandle` at `0x1800071e6`
- `KERNEL32!GlobalAlloc` at `0x180007180`
- `KERNEL32!GlobalAlloc` at `0x180007180`

## pseudocode

```c
char *PuCreateDebugPrintsObject()
{
  char *v0; // rax
  char *v1; // rbx
  HANDLE StdHandle; // rax

  v0 = (char *)GlobalAlloc(0x40u, 0x298u);
  v1 = v0;
  if ( v0 )
  {
    strcpy_s(v0, 0x64u, "admwprox");
    memset_0(v1 + 100, 0, 0x104u);
    memset_0(v1 + 360, 0, 0x104u);
    *((_QWORD *)v1 + 78) = -1;
    *((_DWORD *)v1 + 162) = 1;
    StdHandle = GetStdHandle(0xFFFFFFF4);
    *((_QWORD *)v1 + 79) = StdHandle;
    if ( !StdHandle )
      *((_QWORD *)v1 + 79) = -1;
    *((_DWORD *)v1 + 160) = 1;
    *((_DWORD *)v1 + 161) = 1;
    *((_QWORD *)v1 + 82) = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x180007170  push    rbx
0x180007172  sub     rsp, 20h
0x180007176  mov     edx, 298h; dwBytes
0x18000717b  mov     ecx, 40h ; '@'; uFlags
0x180007180  call    cs:__imp_GlobalAlloc
0x180007186  mov     rbx, rax
0x180007189  test    rax, rax
0x18000718c  jz      loc_180007222
0x180007192  lea     r8, Source; "admwprox"
0x180007199  mov     edx, 64h ; 'd'; SizeInBytes
0x18000719e  mov     rcx, rax; Destination
0x1800071a1  call    cs:__imp_strcpy_s
0x1800071a7  lea     rcx, [rbx+64h]; void *
0x1800071ab  xor     edx, edx; Val
0x1800071ad  mov     r8d, 104h; Size
0x1800071b3  call    memset_0
0x1800071b8  lea     rcx, [rbx+168h]; void *
0x1800071bf  xor     edx, edx; Val
0x1800071c1  mov     r8d, 104h; Size
0x1800071c7  call    memset_0
0x1800071cc  mov     ecx, 0FFFFFFF4h; nStdHandle
0x1800071d1  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x1800071dc  mov     dword ptr [rbx+288h], 1
0x1800071e6  call    cs:__imp_GetStdHandle
0x1800071ec  mov     [rbx+278h], rax
0x1800071f3  test    rax, rax
0x1800071f6  jnz     short loc_180007203
0x1800071f8  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x180007203  mov     dword ptr [rbx+280h], 1
0x18000720d  mov     dword ptr [rbx+284h], 1
0x180007217  mov     qword ptr [rbx+290h], 0
0x180007222  mov     rax, rbx
0x180007225  add     rsp, 20h
0x180007229  pop     rbx
0x18000722a  retn
```
