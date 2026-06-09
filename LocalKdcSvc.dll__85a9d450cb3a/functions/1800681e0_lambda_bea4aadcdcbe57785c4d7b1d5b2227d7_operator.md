# _lambda_bea4aadcdcbe57785c4d7b1d5b2227d7_::operator()

- ea: `0x1800681e0`
- end: `0x18006824c`
- name: `_lambda_bea4aadcdcbe57785c4d7b1d5b2227d7_::operator()`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180068f30`

## callees

- `0x1800681e0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18006821b`
- `ntdll!RtlEqualSid` at `0x18006821b`

## pseudocode

```c
bool __fastcall lambda_bea4aadcdcbe57785c4d7b1d5b2227d7_::operator()(__int64 a1, __int64 a2, void *a3)
{
  unsigned int v5; // edi

  if ( (*(_BYTE *)(a2 + 168) & 0x20) == 0 || !*(_DWORD *)(a2 + 272) )
    return 0;
  v5 = 0;
  while ( !RtlEqualSid(*(PSID *)(*(_QWORD *)(a2 + 280) + 16LL * v5), a3) )
  {
    if ( ++v5 >= *(_DWORD *)(a2 + 272) )
      return 0;
  }
  return (*(_DWORD *)(*(_QWORD *)(a2 + 280) + 16LL * v5 + 8) & 4) != 0;
}

```

## disassembly

```asm
0x1800681e0  push    rbx
0x1800681e2  push    rbp
0x1800681e3  push    rsi
0x1800681e4  push    rdi
0x1800681e5  sub     rsp, 28h
0x1800681e9  test    byte ptr [rdx+0A8h], 20h
0x1800681f0  mov     rbp, r8
0x1800681f3  mov     rbx, rdx
0x1800681f6  jz      short loc_18006822F
0x1800681f8  mov     eax, [rdx+110h]
0x1800681fe  test    eax, eax
0x180068200  jz      short loc_18006822F
0x180068202  xor     edi, edi
0x180068204  test    eax, eax
0x180068206  jz      short loc_18006822F
0x180068208  mov     rcx, [rbx+118h]
0x18006820f  mov     rdx, rbp; Sid2
0x180068212  mov     esi, edi
0x180068214  add     rsi, rsi
0x180068217  mov     rcx, [rcx+rsi*8]; Sid1
0x18006821b  call    cs:__imp_RtlEqualSid
0x180068221  test    al, al
0x180068223  jnz     short loc_18006823A
0x180068225  inc     edi
0x180068227  cmp     edi, [rbx+110h]
0x18006822d  jb      short loc_180068208
0x18006822f  xor     al, al
0x180068231  add     rsp, 28h
0x180068235  pop     rdi
0x180068236  pop     rsi
0x180068237  pop     rbp
0x180068238  pop     rbx
0x180068239  retn
0x18006823a  mov     rax, [rbx+118h]
0x180068241  mov     eax, [rax+rsi*8+8]
0x180068245  shr     eax, 2
0x180068248  and     al, 1
0x18006824a  jmp     short loc_180068231
```
