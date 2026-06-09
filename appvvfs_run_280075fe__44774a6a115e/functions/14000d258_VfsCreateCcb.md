# VfsCreateCcb

- ea: `0x14000d258`
- end: `0x14000d3ae`
- name: `VfsCreateCcb`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000f188`

## callees

- `0x14000d258`
- `0x140012acc`
- `0x140014000`

## import_xrefs

- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000d37f`
- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x14000d37f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d2f3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000d2f3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d278`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000d278`
- `FLTMGR!FltObjectReference` at `0x14000d2be`
- `FLTMGR!FltObjectReference` at `0x14000d2be`

## string_xrefs

- `0x14000d2da`: `VfsCreateCcb() - Failed to reference instance: %p\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateCcb(__int64 a1, __int64 a2, void *a3, __int64 a4, __int64 a5, char a6, _QWORD *a7)
{
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  NTSTATUS v14; // eax
  unsigned int v15; // r14d

  v11 = ExAllocateFromPagedLookasideList(&stru_14001F780);
  v12 = v11;
  if ( !v11 )
    return 3221225626LL;
  memset(v11, 0, 0x88u);
  *(_DWORD *)v12 = 8918663;
  v12[2] = v12 + 1;
  v12[1] = v12 + 1;
  v12[3] = a1;
  v14 = FltObjectReference(a3);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( a6 )
    {
      *((_DWORD *)v12 + 1) |= 4u;
      v12[5] = a3;
      v12[6] = a4;
      v12[7] = a5;
    }
    else
    {
      v12[8] = a3;
      v12[9] = a4;
      v12[10] = a5;
    }
    v12[12] = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 8LL);
    *((_DWORD *)v12 + 26) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) + 16LL);
    *((_DWORD *)v12 + 27) = *(unsigned __int16 *)(*(_QWORD *)(a2 + 16) + 42LL);
    *((_DWORD *)v12 + 28) = *(_DWORD *)(*(_QWORD *)(a2 + 16) + 32LL) & 0xFFFFFF;
    if ( a6 && !*(_BYTE *)(a2 + 80) )
    {
      if ( IoIsFileObjectIgnoringSharing(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 16) + 8LL)) )
        *((_DWORD *)v12 + 1) |= 0x10u;
    }
    *a7 = v12;
    return 0;
  }
  else
  {
    LogWrite(1, 0, L"VfsCreateCcb() - Failed to reference instance: %p\n Status: 0x%08X", a3, v14);
    ExFreeToPagedLookasideList(&stru_14001F780, v12);
    return v15;
  }
}

```

## disassembly

```asm
0x14000d258  push    rbx
0x14000d25a  push    rbp
0x14000d25b  push    rsi
0x14000d25c  push    rdi
0x14000d25d  push    r14
0x14000d25f  push    r15
0x14000d261  sub     rsp, 38h
0x14000d265  mov     r14, rcx
0x14000d268  mov     rbp, r9
0x14000d26b  lea     rcx, stru_14001F780; Lookaside
0x14000d272  mov     rsi, r8
0x14000d275  mov     rdi, rdx
0x14000d278  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000d27f  nop     dword ptr [rax+rax+00h]
0x14000d284  mov     rbx, rax
0x14000d287  test    rax, rax
0x14000d28a  jnz     short loc_14000D296
0x14000d28c  mov     eax, 0C000009Ah
0x14000d291  jmp     loc_14000D3A0
0x14000d296  xor     edx, edx; Val
0x14000d298  mov     r8d, 88h; Size
0x14000d29e  mov     rcx, rbx; void *
0x14000d2a1  call    memset
0x14000d2a6  lea     rax, [rbx+8]
0x14000d2aa  mov     dword ptr [rbx], 881687h
0x14000d2b0  mov     rcx, rsi; FltObject
0x14000d2b3  mov     [rax+8], rax
0x14000d2b7  mov     [rax], rax
0x14000d2ba  mov     [rbx+18h], r14
0x14000d2be  call    cs:__imp_FltObjectReference
0x14000d2c5  nop     dword ptr [rax+rax+00h]
0x14000d2ca  mov     r14d, eax
0x14000d2cd  test    eax, eax
0x14000d2cf  jns     short loc_14000D307
0x14000d2d1  xor     edx, edx
0x14000d2d3  mov     [rsp+68h+var_48], eax
0x14000d2d7  mov     r9, rsi
0x14000d2da  lea     r8, aVfscreateccbFa; "VfsCreateCcb() - Failed to reference in"...
0x14000d2e1  lea     ecx, [rdx+1]
0x14000d2e4  call    LogWrite
0x14000d2e9  mov     rdx, rbx; Entry
0x14000d2ec  lea     rcx, stru_14001F780; Lookaside
0x14000d2f3  call    cs:__imp_ExFreeToPagedLookasideList
0x14000d2fa  nop     dword ptr [rax+rax+00h]
0x14000d2ff  mov     eax, r14d
0x14000d302  jmp     loc_14000D3A0
0x14000d307  mov     dl, [rsp+68h+arg_28]
0x14000d30e  mov     rax, [rsp+68h+arg_20]
0x14000d316  test    dl, dl
0x14000d318  jz      short loc_14000D32C
0x14000d31a  or      dword ptr [rbx+4], 4
0x14000d31e  mov     [rbx+28h], rsi
0x14000d322  mov     [rbx+30h], rbp
0x14000d326  mov     [rbx+38h], rax
0x14000d32a  jmp     short loc_14000D338
0x14000d32c  mov     [rbx+40h], rsi
0x14000d330  mov     [rbx+48h], rbp
0x14000d334  mov     [rbx+50h], rax
0x14000d338  mov     rax, [rdi+10h]
0x14000d33c  mov     rcx, [rax+8]
0x14000d340  mov     [rbx+60h], rcx
0x14000d344  mov     rax, [rdi+10h]
0x14000d348  mov     rcx, [rax+18h]
0x14000d34c  mov     eax, [rcx+10h]
0x14000d34f  mov     [rbx+68h], eax
0x14000d352  mov     rax, [rdi+10h]
0x14000d356  movzx   ecx, word ptr [rax+2Ah]
0x14000d35a  mov     [rbx+6Ch], ecx
0x14000d35d  mov     rax, [rdi+10h]
0x14000d361  mov     ecx, [rax+20h]
0x14000d364  and     ecx, 0FFFFFFh
0x14000d36a  mov     [rbx+70h], ecx
0x14000d36d  test    dl, dl
0x14000d36f  jz      short loc_14000D393
0x14000d371  cmp     byte ptr [rdi+50h], 0
0x14000d375  jnz     short loc_14000D393
0x14000d377  mov     rcx, [rdi+10h]
0x14000d37b  mov     rcx, [rcx+8]; FileObject
0x14000d37f  call    cs:__imp_IoIsFileObjectIgnoringSharing
0x14000d386  nop     dword ptr [rax+rax+00h]
0x14000d38b  test    al, al
0x14000d38d  jz      short loc_14000D393
0x14000d38f  or      dword ptr [rbx+4], 10h
0x14000d393  mov     rax, [rsp+68h+arg_30]
0x14000d39b  mov     [rax], rbx
0x14000d39e  xor     eax, eax
0x14000d3a0  add     rsp, 38h
0x14000d3a4  pop     r15
0x14000d3a6  pop     r14
0x14000d3a8  pop     rdi
0x14000d3a9  pop     rsi
0x14000d3aa  pop     rbp
0x14000d3ab  pop     rbx
0x14000d3ac  retn
```
