# common_ftell_translated_utf8_nolock

- ea: `0x140062ba4`
- end: `0x140062d2a`
- name: `common_ftell_translated_utf8_nolock`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400628f8`

## callees

- `0x14003a5c0`
- `0x14003aab0`
- `0x140062ba4`
- `0x140068d78`
- `0x14007192c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140062c73`
- `KERNEL32!ReadFile` at `0x140062c73`

## pseudocode

```c
__int64 __fastcall common_ftell_translated_utf8_nolock(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // r14d
  __int64 v10; // kr00_8
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // r13
  __int64 v14; // rcx
  unsigned __int8 *v15; // rdx
  unsigned __int8 *v16; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+40h] [rbp-1048h] BYREF

  v6 = fileno((FILE *)a1);
  v7 = 0;
  v8 = v6;
  if ( !*(_DWORD *)(a1 + 16) )
    return a2;
  v10 = *(_QWORD *)a1 - *(_QWORD *)(a1 + 8);
  v11 = (__int64)v6 >> 6;
  v12 = v10 / 2;
  v13 = lseeki64_internal((unsigned int)v6, *(_QWORD *)(_pioinfo[v11] + 72LL * (v6 & 0x3F) + 48), 0, a3);
  v14 = _pioinfo[v11];
  if ( v13 != *(_QWORD *)(v14 + 72LL * (v8 & 0x3F) + 48) )
    return -1;
  NumberOfBytesRead = 0;
  if ( !ReadFile(*(HANDLE *)(v14 + 72LL * (v8 & 0x3F) + 40), Buffer, 0x1000u, &NumberOfBytesRead, 0)
    || lseeki64_internal(v8, a2, 0, a3) < 0
    || v12 > NumberOfBytesRead )
  {
    return -1;
  }
  v15 = &Buffer[NumberOfBytesRead];
  v16 = Buffer;
  if ( v12 )
  {
    do
    {
      if ( v16 >= v15 )
        break;
      if ( *v16 == 13 )
      {
        if ( v16 < v15 - 1 && v16[1] == 10 )
          ++v16;
      }
      else
      {
        v16 += *((char *)lookuptrailbytes + *v16);
      }
      ++v7;
      ++v16;
    }
    while ( v7 != v12 );
  }
  return v16 - Buffer + v13;
}

```

## disassembly

```asm
0x140062ba4  mov     [rsp+arg_0], rbx
0x140062ba9  push    rbp
0x140062baa  push    rsi
0x140062bab  push    rdi
0x140062bac  push    r12
0x140062bae  push    r13
0x140062bb0  push    r14
0x140062bb2  push    r15
0x140062bb4  mov     eax, 1050h
0x140062bb9  call    _alloca_probe
0x140062bbe  sub     rsp, rax
0x140062bc1  mov     rax, cs:__security_cookie
0x140062bc8  xor     rax, rsp
0x140062bcb  mov     [rsp+1088h+var_48], rax
0x140062bd3  mov     r15, r8
0x140062bd6  mov     rbp, rdx
0x140062bd9  mov     rbx, rcx
0x140062bdc  call    _fileno
0x140062be1  xor     edi, edi
0x140062be3  movsxd  r14, eax
0x140062be6  cmp     [rbx+10h], edi
0x140062be9  jnz     short loc_140062BF3
0x140062beb  mov     rax, rbp
0x140062bee  jmp     loc_140062CFF
0x140062bf3  mov     rax, [rbx]
0x140062bf6  mov     rcx, r14
0x140062bf9  sub     rax, [rbx+8]
0x140062bfd  and     ecx, 3Fh
0x140062c00  cqo
0x140062c02  mov     rbx, r14
0x140062c05  sub     rax, rdx
0x140062c08  sar     rbx, 6
0x140062c0c  sar     rax, 1
0x140062c0f  mov     r9, r15
0x140062c12  lea     r12, [rcx+rcx*8]
0x140062c16  mov     rsi, rax
0x140062c19  lea     rax, cs:140000000h
0x140062c20  xor     r8d, r8d
0x140062c23  mov     rdx, rva __pioinfo[rax+rbx*8]
0x140062c2b  mov     ecx, r14d
0x140062c2e  mov     rdx, [rdx+r12*8+30h]
0x140062c33  call    _lseeki64_internal
0x140062c38  mov     r13, rax
0x140062c3b  lea     rax, cs:140000000h
0x140062c42  mov     rcx, rva __pioinfo[rax+rbx*8]
0x140062c4a  cmp     r13, [rcx+r12*8+30h]
0x140062c4f  jnz     loc_140062CFB
0x140062c55  mov     [rsp+1088h+NumberOfBytesRead], edi
0x140062c59  lea     r9, [rsp+1088h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140062c5e  mov     rcx, [rcx+r12*8+28h]; hFile
0x140062c63  lea     rdx, [rsp+1088h+Buffer]; lpBuffer
0x140062c68  mov     r8d, 1000h; nNumberOfBytesToRead
0x140062c6e  mov     [rsp+1088h+lpOverlapped], rdi; lpOverlapped
0x140062c73  call    cs:__imp_ReadFile
0x140062c79  test    eax, eax
0x140062c7b  jz      short loc_140062CFB
0x140062c7d  mov     r9, r15
0x140062c80  xor     r8d, r8d
0x140062c83  mov     rdx, rbp
0x140062c86  mov     ecx, r14d
0x140062c89  call    _lseeki64_internal
0x140062c8e  test    rax, rax
0x140062c91  js      short loc_140062CFB
0x140062c93  mov     eax, [rsp+1088h+NumberOfBytesRead]
0x140062c97  cmp     rsi, rax
0x140062c9a  jg      short loc_140062CFB
0x140062c9c  lea     rdx, [rsp+1088h+Buffer]
0x140062ca1  add     rdx, rax
0x140062ca4  lea     rcx, [rsp+1088h+Buffer]
0x140062ca9  test    rsi, rsi
0x140062cac  jz      short loc_140062CED
0x140062cae  lea     r8, cs:140000000h
0x140062cb5  cmp     rcx, rdx
0x140062cb8  jnb     short loc_140062CED
0x140062cba  cmp     byte ptr [rcx], 0Dh
0x140062cbd  jnz     short loc_140062CD3
0x140062cbf  lea     rax, [rdx-1]
0x140062cc3  cmp     rcx, rax
0x140062cc6  jnb     short loc_140062CE2
0x140062cc8  cmp     byte ptr [rcx+1], 0Ah
0x140062ccc  jnz     short loc_140062CE2
0x140062cce  inc     rcx
0x140062cd1  jmp     short loc_140062CE2
0x140062cd3  movzx   eax, byte ptr [rcx]
0x140062cd6  movsx   rax, byte ptr [rax+r8+1D8FB0h]
0x140062cdf  add     rcx, rax
0x140062ce2  inc     rdi
0x140062ce5  inc     rcx
0x140062ce8  cmp     rdi, rsi
0x140062ceb  jnz     short loc_140062CB5
0x140062ced  lea     rax, [rsp+1088h+Buffer]
0x140062cf2  sub     rcx, rax
0x140062cf5  lea     rax, [rcx+r13]
0x140062cf9  jmp     short loc_140062CFF
0x140062cfb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140062cff  mov     rcx, [rsp+1088h+var_48]
0x140062d07  xor     rcx, rsp; StackCookie
0x140062d0a  call    __security_check_cookie
0x140062d0f  mov     rbx, [rsp+1088h+arg_0]
0x140062d17  add     rsp, 1050h
0x140062d1e  pop     r15
0x140062d20  pop     r14
0x140062d22  pop     r13
0x140062d24  pop     r12
0x140062d26  pop     rdi
0x140062d27  pop     rsi
0x140062d28  pop     rbp
0x140062d29  retn
```
