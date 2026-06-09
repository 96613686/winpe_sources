# CopyWLogFontToTLogFont

- ea: `0x180034994`
- end: `0x180034a63`
- name: `CopyWLogFontToTLogFont`
- size: `207`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034bc0`

## callees

- `0x180034994`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800349f2`
- `KERNEL32!SetLastError` at `0x1800349f2`

## pseudocode

```c
__int64 __fastcall CopyWLogFontToTLogFont(__int64 a1, __int64 a2)
{
  _WORD *v4; // rbx
  _WORD *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  _WORD *v8; // rcx
  __int64 result; // rax

  *(_DWORD *)a2 = *(_DWORD *)a1;
  *(_DWORD *)(a2 + 4) = *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 16);
  *(_BYTE *)(a2 + 20) = *(_BYTE *)(a1 + 20);
  *(_BYTE *)(a2 + 21) = *(_BYTE *)(a1 + 21);
  *(_BYTE *)(a2 + 22) = *(_BYTE *)(a1 + 22);
  *(_BYTE *)(a2 + 23) = *(_BYTE *)(a1 + 23);
  *(_BYTE *)(a2 + 24) = *(_BYTE *)(a1 + 24);
  *(_BYTE *)(a2 + 25) = *(_BYTE *)(a1 + 25);
  *(_BYTE *)(a2 + 26) = *(_BYTE *)(a1 + 26);
  *(_BYTE *)(a2 + 27) = *(_BYTE *)(a1 + 27);
  SetLastError(0);
  v4 = (_WORD *)(a1 + 28);
  v5 = (_WORD *)(a2 + 28);
  v6 = 2147483646;
  v7 = 32;
  do
  {
    if ( !v6 )
      break;
    if ( !*v4 )
      break;
    *v5++ = *v4++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v5 - 1;
  if ( v7 )
    v8 = v5;
  result = v7 == 0 ? 0x7A : 0;
  *v8 = 0;
  if ( v7 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180034994  mov     [rsp+arg_0], rbx
0x180034999  push    rdi
0x18003499a  sub     rsp, 20h
0x18003499e  mov     eax, [rcx]
0x1800349a0  mov     rbx, rcx
0x1800349a3  mov     [rdx], eax
0x1800349a5  mov     rdi, rdx
0x1800349a8  mov     eax, [rcx+4]
0x1800349ab  mov     [rdx+4], eax
0x1800349ae  mov     eax, [rcx+8]
0x1800349b1  mov     [rdx+8], eax
0x1800349b4  mov     eax, [rcx+0Ch]
0x1800349b7  mov     [rdx+0Ch], eax
0x1800349ba  mov     eax, [rcx+10h]
0x1800349bd  mov     [rdx+10h], eax
0x1800349c0  mov     al, [rcx+14h]
0x1800349c3  mov     [rdx+14h], al
0x1800349c6  mov     al, [rcx+15h]
0x1800349c9  mov     [rdx+15h], al
0x1800349cc  mov     al, [rcx+16h]
0x1800349cf  mov     [rdx+16h], al
0x1800349d2  mov     al, [rcx+17h]
0x1800349d5  mov     [rdx+17h], al
0x1800349d8  mov     al, [rcx+18h]
0x1800349db  mov     [rdx+18h], al
0x1800349de  mov     al, [rcx+19h]
0x1800349e1  mov     [rdx+19h], al
0x1800349e4  mov     al, [rcx+1Ah]
0x1800349e7  mov     [rdx+1Ah], al
0x1800349ea  mov     al, [rcx+1Bh]
0x1800349ed  xor     ecx, ecx; dwErrCode
0x1800349ef  mov     [rdx+1Bh], al
0x1800349f2  call    cs:__imp_SetLastError
0x1800349f9  nop     dword ptr [rax+rax+00h]
0x1800349fe  add     rbx, 1Ch
0x180034a02  add     rdi, 1Ch
0x180034a06  xor     r8d, r8d
0x180034a09  mov     eax, 7FFFFFFEh
0x180034a0e  mov     edx, 20h ; ' '
0x180034a13  test    rax, rax
0x180034a16  jz      short loc_180034A34
0x180034a18  movzx   ecx, word ptr [rbx]
0x180034a1b  test    cx, cx
0x180034a1e  jz      short loc_180034A34
0x180034a20  mov     [rdi], cx
0x180034a23  add     rbx, 2
0x180034a27  add     rdi, 2
0x180034a2b  dec     rax
0x180034a2e  sub     rdx, 1
0x180034a32  jnz     short loc_180034A13
0x180034a34  mov     rbx, [rsp+28h+arg_0]
0x180034a39  lea     rcx, [rdi-2]
0x180034a3d  test    rdx, rdx
0x180034a40  mov     rax, rdx
0x180034a43  cmovnz  rcx, rdi
0x180034a47  neg     rax
0x180034a4a  sbb     eax, eax
0x180034a4c  not     eax
0x180034a4e  and     eax, 7Ah
0x180034a51  mov     [rcx], r8w
0x180034a55  test    rdx, rdx
0x180034a58  cmovnz  eax, r8d
0x180034a5c  add     rsp, 20h
0x180034a60  pop     rdi
0x180034a61  retn
```
