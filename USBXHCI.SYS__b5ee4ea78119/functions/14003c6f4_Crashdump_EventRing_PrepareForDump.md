# Crashdump_EventRing_PrepareForDump

- ea: `0x14003c6f4`
- end: `0x14003c80d`
- name: `Crashdump_EventRing_PrepareForDump`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140051fcc`

## callees

- `0x14003c6f4`
- `0x14003c814`
- `0x140059d80`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14003c7fa`
- `ntoskrnl!DbgPrintEx` at `0x14003c7fa`

## string_xrefs

- `0x14003c7e9`: `XHCIDUMP: Installed new Event Ring\n`

## pseudocode

```c
ULONG __fastcall Crashdump_EventRing_PrepareForDump(__int64 a1)
{
  __int64 v1; // r8
  __int64 v3; // rdx
  __int64 v4; // rax
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  size_t v7; // r8
  void *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  signed __int32 v13[10]; // [rsp+0h] [rbp-28h] BYREF

  v1 = a1 + 112;
  *(_QWORD *)(a1 + 120) = a1 + 112;
  *(_QWORD *)(a1 + 112) = a1 + 112;
  v3 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 72) = v3;
  *(_QWORD *)(v4 + 16) = v3;
  *(_QWORD *)(*(_QWORD *)(a1 + 104) + 24LL) = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(*(_QWORD *)(a1 + 104) + 40LL) = *(_DWORD *)(a1 + 64);
  v5 = *(_QWORD **)(a1 + 120);
  if ( *v5 != v1 )
    __fastfail(3u);
  v6 = *(_QWORD **)(a1 + 104);
  *v6 = v1;
  v6[1] = v5;
  *v5 = v6;
  *(_QWORD *)(v1 + 8) = v6;
  v7 = *(unsigned int *)(a1 + 40);
  v8 = *(void **)(a1 + 32);
  *(_DWORD *)(a1 + 84) = *(_DWORD *)(a1 + 64) >> 4;
  *(_QWORD *)(a1 + 88) = 1;
  *(_DWORD *)(a1 + 80) = 1;
  *(_DWORD *)(a1 + 96) = 0;
  memset(v8, 0, v7);
  memset(*(void **)(a1 + 56), 0, *(unsigned int *)(a1 + 64));
  *(_DWORD *)(*(_QWORD *)(a1 + 16) + 8LL) = 1;
  _InterlockedOr(v13, 0);
  Crashdump_EventRing_UpdateDequeuePointer(a1);
  v9 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)v9 = *(_QWORD *)(a1 + 48);
  *(_WORD *)(v9 + 8) = *(_WORD *)(a1 + 84);
  v10 = *(_QWORD *)(a1 + 24);
  v11 = *(_QWORD *)(a1 + 16);
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 8) + 8LL) & 1) != 0 )
  {
    *(_DWORD *)(v11 + 16) = v10;
    _InterlockedOr(v13, 0);
    *(_DWORD *)(v11 + 20) = HIDWORD(v10);
  }
  else
  {
    *(_QWORD *)(v11 + 16) = v10;
  }
  _InterlockedOr(v13, 0);
  return DbgPrintEx(0x93u, 3u, "XHCIDUMP: Installed new Event Ring\n");
}

```

## disassembly

```asm
0x14003c6f4  push    rbx
0x14003c6f6  sub     rsp, 20h
0x14003c6fa  lea     r8, [rcx+70h]
0x14003c6fe  mov     rbx, rcx
0x14003c701  mov     [r8+8], r8
0x14003c705  mov     [r8], r8
0x14003c708  mov     rdx, [rcx+38h]
0x14003c70c  mov     rax, [rcx+68h]
0x14003c710  mov     [rcx+48h], rdx
0x14003c714  mov     [rax+10h], rdx
0x14003c718  mov     rax, [rcx+30h]
0x14003c71c  mov     rdx, [rcx+68h]
0x14003c720  mov     [rdx+18h], rax
0x14003c724  mov     rcx, [rcx+68h]
0x14003c728  mov     eax, [rbx+40h]
0x14003c72b  mov     [rcx+28h], eax
0x14003c72e  mov     rcx, [r8+8]
0x14003c732  cmp     [rcx], r8
0x14003c735  jz      short loc_14003C73E
0x14003c737  mov     ecx, 3
0x14003c73c  int     29h; Win8: RtlFailFast(ecx)
0x14003c73e  mov     rax, [rbx+68h]
0x14003c742  xor     edx, edx; Val
0x14003c744  mov     [rax], r8
0x14003c747  mov     [rax+8], rcx
0x14003c74b  mov     [rcx], rax
0x14003c74e  mov     [r8+8], rax
0x14003c752  mov     eax, [rbx+40h]
0x14003c755  mov     r8d, [rbx+28h]; Size
0x14003c759  mov     rcx, [rbx+20h]; void *
0x14003c75d  shr     eax, 4
0x14003c760  mov     [rbx+54h], eax
0x14003c763  mov     qword ptr [rbx+58h], 1
0x14003c76b  mov     dword ptr [rbx+50h], 1
0x14003c772  mov     dword ptr [rbx+60h], 0
0x14003c779  call    memset
0x14003c77e  mov     r8d, [rbx+40h]; Size
0x14003c782  xor     edx, edx; Val
0x14003c784  mov     rcx, [rbx+38h]; void *
0x14003c788  call    memset
0x14003c78d  mov     rax, [rbx+10h]
0x14003c791  mov     dword ptr [rax+8], 1
0x14003c798  lock or [rsp+28h+var_28], 0
0x14003c79d  mov     rcx, rbx
0x14003c7a0  call    Crashdump_EventRing_UpdateDequeuePointer
0x14003c7a5  mov     rax, [rbx+30h]
0x14003c7a9  mov     rdx, [rbx+20h]
0x14003c7ad  mov     [rdx], rax
0x14003c7b0  movzx   eax, word ptr [rbx+54h]
0x14003c7b4  mov     [rdx+8], ax
0x14003c7b8  mov     rax, [rbx+8]
0x14003c7bc  mov     rdx, [rbx+18h]
0x14003c7c0  mov     r8, [rbx+10h]
0x14003c7c4  test    byte ptr [rax+8], 1
0x14003c7c8  jnz     short loc_14003C7D0
0x14003c7ca  mov     [r8+10h], rdx
0x14003c7ce  jmp     short loc_14003C7E4
0x14003c7d0  mov     rax, rdx
0x14003c7d3  mov     [r8+10h], edx
0x14003c7d7  shr     rax, 20h
0x14003c7db  lock or [rsp+28h+var_28], 0
0x14003c7e0  mov     [r8+14h], eax
0x14003c7e4  lock or [rsp+28h+var_28], 0
0x14003c7e9  lea     r8, aXhcidumpInstal; "XHCIDUMP: Installed new Event Ring\n"
0x14003c7f0  mov     edx, 3; Level
0x14003c7f5  mov     ecx, 93h; ComponentId
0x14003c7fa  call    cs:__imp_DbgPrintEx
0x14003c801  nop     dword ptr [rax+rax+00h]
0x14003c806  add     rsp, 20h
0x14003c80a  pop     rbx
0x14003c80b  retn
```
