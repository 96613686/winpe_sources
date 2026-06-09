# CempHostInfoInitialize

- ea: `0x18000c9c0`
- end: `0x18000ca69`
- name: `CempHostInfoInitialize`
- size: `169`
- prototype: `__int64 __fastcall(_WORD *, void *, int, int, __int64, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c420`

## callees

- `0x18000c9c0`
- `0x18001ae8e`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000ca40`
- `ntdll!RtlCopySid` at `0x18000ca40`

## pseudocode

```c
__int64 __fastcall CempHostInfoInitialize(_WORD *a1, void *a2, int a3, int a4, __int64 a5, char *a6)
{
  __int64 v10; // r10
  __int64 v11; // r11
  _WORD *v12; // rcx
  _WORD *v13; // rax
  __int64 result; // rax

  memset_0(a6, 0, 0x228u);
  v10 = 2147483646;
  v11 = 232;
  v12 = a6;
  do
  {
    if ( !v10 )
      break;
    if ( !*a1 )
      break;
    *v12++ = *a1++;
    --v10;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  RtlCopySid(0x44u, a6 + 464, a2);
  result = a5;
  *((_QWORD *)a6 + 68) = a5;
  *((_DWORD *)a6 + 133) = a3;
  *((_DWORD *)a6 + 134) = a4;
  return result;
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  push    rbp
0x18000c9c3  push    rsi
0x18000c9c4  push    rdi
0x18000c9c5  push    r14
0x18000c9c7  sub     rsp, 20h
0x18000c9cb  mov     rdi, [rsp+48h+arg_28]
0x18000c9d0  mov     ebp, r8d
0x18000c9d3  mov     r14, rdx
0x18000c9d6  mov     rbx, rcx
0x18000c9d9  mov     rcx, rdi; void *
0x18000c9dc  xor     edx, edx; Val
0x18000c9de  mov     r8d, 228h; Size
0x18000c9e4  mov     esi, r9d
0x18000c9e7  call    memset_0
0x18000c9ec  mov     r10d, 7FFFFFFEh
0x18000c9f2  mov     r11d, 0E8h
0x18000c9f8  mov     rcx, rdi
0x18000c9fb  nop     dword ptr [rax+rax+00h]
0x18000ca00  test    r10, r10
0x18000ca03  jz      short loc_18000CA21
0x18000ca05  movzx   eax, word ptr [rbx]
0x18000ca08  test    ax, ax
0x18000ca0b  jz      short loc_18000CA21
0x18000ca0d  mov     [rcx], ax
0x18000ca10  add     rbx, 2
0x18000ca14  add     rcx, 2
0x18000ca18  dec     r10
0x18000ca1b  sub     r11, 1
0x18000ca1f  jnz     short loc_18000CA00
0x18000ca21  lea     rax, [rcx-2]
0x18000ca25  test    r11, r11
0x18000ca28  lea     rdx, [rdi+1D0h]; DestinationSid
0x18000ca2f  mov     r8, r14; SourceSid
0x18000ca32  cmovnz  rax, rcx
0x18000ca36  xor     ecx, ecx
0x18000ca38  mov     [rax], cx
0x18000ca3b  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000ca40  call    cs:__imp_RtlCopySid
0x18000ca46  mov     rax, [rsp+48h+arg_20]
0x18000ca4b  mov     [rdi+220h], rax
0x18000ca52  mov     [rdi+214h], ebp
0x18000ca58  mov     [rdi+218h], esi
0x18000ca5e  add     rsp, 20h
0x18000ca62  pop     r14
0x18000ca64  pop     rdi
0x18000ca65  pop     rsi
0x18000ca66  pop     rbp
0x18000ca67  pop     rbx
0x18000ca68  retn
```
