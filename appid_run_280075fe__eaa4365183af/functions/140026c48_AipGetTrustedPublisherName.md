# AipGetTrustedPublisherName

- ea: `0x140026c48`
- end: `0x140026e3b`
- name: `AipGetTrustedPublisherName`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140025560`
- `0x140025964`
- `0x140028bbc`

## callees

- `0x140006b20`
- `0x140026c48`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140026df8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140026df8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026e1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026e1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026ca7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026ca7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026cbc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140026cbc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026e0f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140026e0f`

## pseudocode

```c
__int64 __fastcall AipGetTrustedPublisherName(__int64 a1, unsigned __int64 *a2, struct _UNICODE_STRING *a3, _DWORD *a4)
{
  unsigned int v7; // ebp
  __int64 v8; // rax
  unsigned int *v9; // rcx
  const void *v10; // r13
  size_t v11; // r14
  __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  int v14; // eax
  unsigned __int64 v15; // rax
  _QWORD **v16; // rax
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rax
  PWSTR Buffer; // rcx
  __int64 v20; // rax

  if ( a4 )
    *a4 = 1;
  v7 = -2;
  if ( !*(_DWORD *)a1 )
    return v7;
  v8 = *(_QWORD *)(a1 + 16);
  if ( !v8 )
    return v7;
  if ( !*(_DWORD *)(v8 + 16) )
    return v7;
  v9 = *(unsigned int **)(v8 + 8);
  if ( !v9 )
    return v7;
  v10 = (const void *)*((_QWORD *)v9 + 1);
  v11 = *v9;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&qword_1400195D8, 0);
  v12 = AipCertificateStore;
  v13 = 0;
  while ( v12 )
  {
    if ( (unsigned int)v11 < *(_DWORD *)(v12 + 56) )
      goto LABEL_13;
    if ( (unsigned int)v11 > *(_DWORD *)(v12 + 56) )
      goto LABEL_23;
    v14 = memcmp(v10, *(const void **)(v12 + 64), v11);
    if ( v14 < 0 )
      goto LABEL_13;
    if ( v14 > 0 )
    {
LABEL_23:
      v12 = *(_QWORD *)(v12 + 8);
    }
    else
    {
      v13 = v12;
LABEL_13:
      v12 = *(_QWORD *)v12;
    }
  }
  while ( v13 )
  {
    if ( !*(_DWORD *)(v13 + 88) )
    {
      if ( a4 )
        *a4 = 0;
      if ( !*(_DWORD *)(v13 + 92) )
      {
        if ( !a2
          || (!*(_DWORD *)(v13 + 96) ? (v15 = *a2) : (v15 = MEMORY[0xFFFFF78000000014]),
              v15 >= *(_QWORD *)(v13 + 72) && v15 <= *(_QWORD *)(v13 + 80)) )
        {
          if ( a3 )
          {
            Buffer = a3->Buffer;
            if ( !Buffer || a3->MaximumLength < *(_WORD *)(v13 + 42) )
            {
              AiFree(Buffer);
              v20 = AiAlloc(*(unsigned __int16 *)(v13 + 42));
              a3->Buffer = (PWSTR)v20;
              if ( !v20 )
              {
                v7 = -1073741801;
                break;
              }
              a3->MaximumLength = *(_WORD *)(v13 + 42);
            }
            RtlCopyUnicodeString(a3, (PCUNICODE_STRING)(v13 + 40));
          }
          v7 = 0;
          break;
        }
      }
    }
    v16 = *(_QWORD ***)(v13 + 8);
    if ( v16 )
    {
      v17 = *v16;
      if ( *v16 )
      {
        do
        {
          v13 = (unsigned __int64)v17;
          v17 = (_QWORD *)*v17;
        }
        while ( v17 );
      }
      else
      {
        v13 = *(_QWORD *)(v13 + 8);
      }
    }
    else
    {
      do
      {
        v18 = v13;
        v13 = *(_QWORD *)(v13 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
      }
      while ( v13 && *(_QWORD *)v13 != v18 );
    }
    if ( !v13 )
      break;
    if ( (unsigned int)v11 < *(_DWORD *)(v13 + 56)
      || (unsigned int)v11 > *(_DWORD *)(v13 + 56)
      || memcmp(v10, *(const void **)(v13 + 64), v11) )
    {
      v13 = 0;
    }
  }
  ExReleasePushLockSharedEx(&qword_1400195D8, 0);
  KeLeaveCriticalRegion();
  return v7;
}

```

## disassembly

```asm
0x140026c48  push    rbx
0x140026c4a  push    rbp
0x140026c4b  push    rsi
0x140026c4c  push    rdi
0x140026c4d  push    r12
0x140026c4f  push    r13
0x140026c51  push    r14
0x140026c53  push    r15
0x140026c55  sub     rsp, 28h
0x140026c59  mov     r15, r9
0x140026c5c  mov     rsi, r8
0x140026c5f  mov     r12, rdx
0x140026c62  test    r9, r9
0x140026c65  jz      short loc_140026C6E
0x140026c67  mov     dword ptr [r9], 1
0x140026c6e  cmp     dword ptr [rcx], 0
0x140026c71  mov     ebp, 0FFFFFFFEh
0x140026c76  jz      loc_140026E27
0x140026c7c  mov     rax, [rcx+10h]
0x140026c80  test    rax, rax
0x140026c83  jz      loc_140026E27
0x140026c89  cmp     dword ptr [rax+10h], 0
0x140026c8d  jz      loc_140026E27
0x140026c93  mov     rcx, [rax+8]
0x140026c97  test    rcx, rcx
0x140026c9a  jz      loc_140026E27
0x140026ca0  mov     r13, [rcx+8]
0x140026ca4  mov     r14d, [rcx]
0x140026ca7  call    cs:__imp_KeEnterCriticalRegion
0x140026cae  nop     dword ptr [rax+rax+00h]
0x140026cb3  xor     edx, edx
0x140026cb5  lea     rcx, qword_1400195D8
0x140026cbc  call    cs:__imp_ExAcquirePushLockSharedEx
0x140026cc3  nop     dword ptr [rax+rax+00h]
0x140026cc8  mov     rdi, cs:AipCertificateStore
0x140026ccf  xor     ebx, ebx
0x140026cd1  jmp     short loc_140026CF6
0x140026cd3  cmp     r14d, [rdi+38h]
0x140026cd7  jb      short loc_140026CF3
0x140026cd9  ja      short loc_140026D3A
0x140026cdb  mov     rdx, [rdi+40h]; Buf2
0x140026cdf  mov     r8, r14; Size
0x140026ce2  mov     rcx, r13; Buf1
0x140026ce5  call    memcmp
0x140026cea  test    eax, eax
0x140026cec  js      short loc_140026CF3
0x140026cee  jg      short loc_140026D3A
0x140026cf0  mov     rbx, rdi
0x140026cf3  mov     rdi, [rdi]
0x140026cf6  test    rdi, rdi
0x140026cf9  jnz     short loc_140026CD3
0x140026cfb  test    rbx, rbx
0x140026cfe  jz      loc_140026E06
0x140026d04  cmp     dword ptr [rbx+58h], 0
0x140026d08  jnz     short loc_140026D50
0x140026d0a  test    r15, r15
0x140026d0d  jz      short loc_140026D16
0x140026d0f  mov     dword ptr [r15], 0
0x140026d16  cmp     dword ptr [rbx+5Ch], 0
0x140026d1a  jnz     short loc_140026D50
0x140026d1c  test    r12, r12
0x140026d1f  jz      loc_140026DB3
0x140026d25  cmp     dword ptr [rbx+60h], 0
0x140026d29  jz      short loc_140026D40
0x140026d2b  mov     rax, 0FFFFF78000000014h
0x140026d35  mov     rax, [rax]
0x140026d38  jmp     short loc_140026D44
0x140026d3a  mov     rdi, [rdi+8]
0x140026d3e  jmp     short loc_140026CF6
0x140026d40  mov     rax, [r12]
0x140026d44  cmp     rax, [rbx+48h]
0x140026d48  jb      short loc_140026D50
0x140026d4a  cmp     rax, [rbx+50h]
0x140026d4e  jbe     short loc_140026DB3
0x140026d50  mov     rax, [rbx+8]
0x140026d54  test    rax, rax
0x140026d57  jz      short loc_140026D7B
0x140026d59  mov     rcx, [rax]
0x140026d5c  test    rcx, rcx
0x140026d5f  jz      short loc_140026D71
0x140026d61  mov     rax, [rcx]
0x140026d64  mov     rbx, rcx
0x140026d67  mov     rcx, rax
0x140026d6a  test    rax, rax
0x140026d6d  jnz     short loc_140026D61
0x140026d6f  jmp     short loc_140026D88
0x140026d71  mov     rbx, rax
0x140026d74  jmp     short loc_140026D88
0x140026d76  cmp     [rbx], rax
0x140026d79  jz      short loc_140026D88
0x140026d7b  mov     rax, rbx
0x140026d7e  mov     rbx, [rbx+10h]
0x140026d82  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140026d86  jnz     short loc_140026D76
0x140026d88  test    rbx, rbx
0x140026d8b  jz      short loc_140026E06
0x140026d8d  cmp     r14d, [rbx+38h]
0x140026d91  jb      short loc_140026DAC
0x140026d93  ja      short loc_140026DAC
0x140026d95  mov     rdx, [rbx+40h]; Buf2
0x140026d99  mov     r8, r14; Size
0x140026d9c  mov     rcx, r13; Buf1
0x140026d9f  call    memcmp
0x140026da4  test    eax, eax
0x140026da6  jz      loc_140026CFB
0x140026dac  xor     ebx, ebx
0x140026dae  jmp     loc_140026CFB
0x140026db3  test    rsi, rsi
0x140026db6  jz      short loc_140026E04
0x140026db8  mov     rcx, [rsi+8]
0x140026dbc  test    rcx, rcx
0x140026dbf  jz      short loc_140026DCB
0x140026dc1  movzx   eax, word ptr [rbx+2Ah]
0x140026dc5  cmp     [rsi+2], ax
0x140026dc9  jnb     short loc_140026DF1
0x140026dcb  call    AiFree
0x140026dd0  movzx   ecx, word ptr [rbx+2Ah]
0x140026dd4  call    AiAlloc
0x140026dd9  mov     [rsi+8], rax
0x140026ddd  test    rax, rax
0x140026de0  jnz     short loc_140026DE9
0x140026de2  mov     ebp, 0C0000017h
0x140026de7  jmp     short loc_140026E06
0x140026de9  movzx   eax, word ptr [rbx+2Ah]
0x140026ded  mov     [rsi+2], ax
0x140026df1  lea     rdx, [rbx+28h]; SourceString
0x140026df5  mov     rcx, rsi; DestinationString
0x140026df8  call    cs:__imp_RtlCopyUnicodeString
0x140026dff  nop     dword ptr [rax+rax+00h]
0x140026e04  xor     ebp, ebp
0x140026e06  xor     edx, edx
0x140026e08  lea     rcx, qword_1400195D8
0x140026e0f  call    cs:__imp_ExReleasePushLockSharedEx
0x140026e16  nop     dword ptr [rax+rax+00h]
0x140026e1b  call    cs:__imp_KeLeaveCriticalRegion
0x140026e22  nop     dword ptr [rax+rax+00h]
0x140026e27  mov     eax, ebp
0x140026e29  add     rsp, 28h
0x140026e2d  pop     r15
0x140026e2f  pop     r14
0x140026e31  pop     r13
0x140026e33  pop     r12
0x140026e35  pop     rdi
0x140026e36  pop     rsi
0x140026e37  pop     rbp
0x140026e38  pop     rbx
0x140026e39  retn
```
