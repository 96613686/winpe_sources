# NPCompareUnicodeString(_UNICODE_STRING const &,_UNICODE_STRING const &,bool)

- ea: `0x1400024e8`
- end: `0x14000258a`
- name: `?NPCompareUnicodeString@@YA_NAEBU_UNICODE_STRING@@0_N@Z`
- size: `162`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002590`

## callees

- `0x1400024e8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140002512`
- `ntoskrnl!RtlCompareMemory` at `0x140002512`

## pseudocode

```c
bool __fastcall NPCompareUnicodeString(const struct _UNICODE_STRING *a1, const struct _UNICODE_STRING *a2, char a3)
{
  unsigned __int16 v4; // r10
  unsigned __int16 v5; // r9
  wchar_t *Buffer; // r11
  wchar_t *v7; // rbx
  wchar_t v8; // cx
  wchar_t v9; // r8
  wchar_t v10; // dx
  wchar_t v11; // cx

  if ( a1->Length != a2->Length )
    return 0;
  if ( a3 )
    return a1->Length == RtlCompareMemory(a1->Buffer, a2->Buffer, a1->Length);
  v4 = 0;
  v5 = a1->Length >> 1;
  if ( v5 )
  {
    Buffer = a2->Buffer;
    v7 = a1->Buffer;
    do
    {
      v8 = Buffer[v4];
      v9 = v7[v4];
      v10 = v8 + 32;
      if ( (unsigned __int16)(v8 - 65) > 0x19u )
        v10 = Buffer[v4];
      v11 = v9 + 32;
      if ( (unsigned __int16)(v9 - 65) > 0x19u )
        v11 = v7[v4];
      if ( v11 != v10 )
        break;
      ++v4;
    }
    while ( v4 < v5 );
  }
  return v4 >= v5;
}

```

## disassembly

```asm
0x1400024e8  push    rbx
0x1400024ea  sub     rsp, 20h
0x1400024ee  movzx   r9d, word ptr [rcx]
0x1400024f2  mov     rbx, rcx
0x1400024f5  cmp     r9w, [rdx]
0x1400024f9  jz      short loc_140002502
0x1400024fb  xor     al, al
0x1400024fd  jmp     loc_140002583
0x140002502  test    r8b, r8b
0x140002505  jz      short loc_140002529
0x140002507  mov     rdx, [rdx+8]; Source2
0x14000250b  mov     r8, r9; Length
0x14000250e  mov     rcx, [rcx+8]; Source1
0x140002512  call    cs:__imp_RtlCompareMemory
0x140002519  nop     dword ptr [rax+rax+00h]
0x14000251e  movzx   ecx, word ptr [rbx]
0x140002521  cmp     rcx, rax
0x140002524  setz    al
0x140002527  jmp     short loc_140002583
0x140002529  xor     r10d, r10d
0x14000252c  shr     r9w, 1
0x140002530  xor     eax, eax
0x140002532  cmp     ax, r9w
0x140002536  jnb     short loc_14000257C
0x140002538  mov     r11, [rdx+8]
0x14000253c  mov     rbx, [rcx+8]
0x140002540  movzx   eax, r10w
0x140002544  movzx   ecx, word ptr [r11+rax*2]
0x140002549  movzx   r8d, word ptr [rbx+rax*2]
0x14000254e  lea     eax, [rcx-41h]
0x140002551  cmp     ax, 19h
0x140002555  lea     edx, [rcx+20h]
0x140002558  lea     eax, [r8-41h]
0x14000255c  cmova   dx, cx
0x140002560  cmp     ax, 19h
0x140002564  lea     ecx, [r8+20h]
0x140002568  cmova   cx, r8w
0x14000256d  cmp     cx, dx
0x140002570  jnz     short loc_14000257C
0x140002572  inc     r10w
0x140002576  cmp     r10w, r9w
0x14000257a  jb      short loc_140002540
0x14000257c  cmp     r10w, r9w
0x140002580  setnb   al
0x140002583  add     rsp, 20h
0x140002587  pop     rbx
0x140002588  retn
```
