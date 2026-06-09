# BfLogPathTierNode

- ea: `0x14000fda0`
- end: `0x14000ff51`
- name: `BfLogPathTierNode`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f230`
- `0x14000f308`

## callees

- `0x140004cc0`
- `0x14000fda0`
- `0x1400172f0`
- `0x14001d130`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000feaa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000feaa`

## pseudocode

```c
__int64 __fastcall BfLogPathTierNode(__int64 a1, __int64 a2)
{
  NTSTATUS appended; // edi
  char v3; // al
  __int64 v6; // r9
  unsigned __int16 v7; // r8
  unsigned __int16 v8; // r14
  __int64 *v9; // rcx
  __int16 v10; // ax
  int v11; // r15d
  __int64 v12; // rcx
  unsigned int v13; // edx
  const void *v14; // rdx
  size_t v15; // r8
  unsigned int v16; // eax
  void *v17; // rcx
  int v18; // r12d
  int v19; // r13d
  int v20; // r15d
  __int64 *i; // r14
  __int64 result; // rax
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-38h] BYREF
  __int128 v28; // [rsp+30h] [rbp-28h]

  appended = 0;
  v3 = *(_DWORD *)a1 & 3;
  Destination = 0;
  if ( v3 == 1 )
  {
    v6 = *(_QWORD *)(a1 + 72);
    v7 = 0;
    v8 = 0;
    v9 = *(__int64 **)(v6 + 64);
    while ( v9 != (__int64 *)(v6 + 64) )
    {
      v10 = *((_WORD *)v9 + 12);
      v8 += 8;
      v9 = (__int64 *)*v9;
      v7 += v10 + 8;
    }
    v11 = *(unsigned __int16 *)(a1 + 56);
    v12 = *(unsigned int *)(a2 + 12);
    v13 = v11 + v7;
    if ( *(_BYTE *)a2 )
    {
      ++*(_DWORD *)(a2 + 4);
      *(_DWORD *)(a2 + 12) = v13 + v12 + 20;
    }
    else if ( *(_DWORD *)(a2 + 8) - (int)v12 >= v13 )
    {
      v14 = *(const void **)(a1 + 64);
      v15 = *(unsigned __int16 *)(a1 + 56);
      v16 = *(_DWORD *)(v6 + 8);
      DWORD1(v28) = *(_DWORD *)(a2 + 12);
      v17 = (void *)(*(_QWORD *)(a2 + 16) + v12);
      *((_QWORD *)&v28 + 1) = v16;
      LODWORD(v28) = (unsigned __int16)v11;
      memmove(v17, v14, v15);
      *(_DWORD *)(a2 + 12) += v11;
      v18 = 0;
      v19 = *(_DWORD *)(a2 + 12);
      v20 = v19 + v8;
      for ( i = *(__int64 **)(*(_QWORD *)(a1 + 72) + 64LL); i != (__int64 *)(*(_QWORD *)(a1 + 72) + 64LL); i = (__int64 *)*i )
      {
        Destination.MaximumLength = *((_WORD *)i + 12);
        result = BfAllocateUnicodeString(Destination.MaximumLength, &Destination);
        if ( (int)result < 0 )
          return result;
        appended = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(i + 3));
        if ( appended < 0 )
          goto LABEL_15;
        v23 = *(unsigned int *)(a2 + 12);
        v24 = *(_QWORD *)(a2 + 16);
        *(_WORD *)(v23 + v24) = Destination.Length;
        *(_DWORD *)(v23 + v24 + 4) = v20;
        *(_DWORD *)(a2 + 12) += 8;
        memmove(
          (void *)(*(_QWORD *)(a2 + 16) + *(unsigned int *)(v23 + v24 + 4)),
          Destination.Buffer,
          Destination.Length);
        v20 += Destination.Length;
        BfFreeUnicodeString(&Destination);
        Destination.Buffer = 0;
        ++v18;
      }
      v25 = *(_QWORD *)(a2 + 16);
      *(_DWORD *)(a2 + 12) = v20;
      HIDWORD(v28) = v18;
      v26 = 5LL * *(unsigned int *)(v25 + 8);
      *(_OWORD *)(v25 + 4 * v26 + 12) = v28;
      *(_DWORD *)(v25 + 4 * v26 + 28) = v19;
      ++*(_DWORD *)(v25 + 8);
    }
    else
    {
      appended = -1073741789;
    }
  }
LABEL_15:
  BfFreeUnicodeString(&Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000fda0  push    rbp
0x14000fda2  push    rbx
0x14000fda3  push    rsi
0x14000fda4  push    rdi
0x14000fda5  push    r12
0x14000fda7  push    r13
0x14000fda9  push    r14
0x14000fdab  push    r15
0x14000fdad  mov     rbp, rsp
0x14000fdb0  sub     rsp, 58h
0x14000fdb4  mov     eax, [rcx]
0x14000fdb6  xor     edi, edi
0x14000fdb8  and     al, 3
0x14000fdba  xorps   xmm0, xmm0
0x14000fdbd  mov     rbx, rdx
0x14000fdc0  mov     rsi, rcx
0x14000fdc3  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x14000fdc7  cmp     al, 1
0x14000fdc9  jnz     loc_14000FF34
0x14000fdcf  mov     r9, [rcx+48h]
0x14000fdd3  lea     r10d, [rdi+8]
0x14000fdd7  xor     r8d, r8d
0x14000fdda  xor     r14d, r14d
0x14000fddd  lea     rdx, [r9+40h]
0x14000fde1  mov     rcx, [rdx]
0x14000fde4  jmp     short loc_14000FDF9
0x14000fde6  movzx   eax, word ptr [rcx+18h]
0x14000fdea  add     r14w, r10w
0x14000fdee  mov     rcx, [rcx]
0x14000fdf1  add     ax, r10w
0x14000fdf5  add     r8w, ax
0x14000fdf9  cmp     rcx, rdx
0x14000fdfc  jnz     short loc_14000FDE6
0x14000fdfe  movzx   r15d, word ptr [rsi+38h]
0x14000fe03  mov     ecx, [rbx+0Ch]
0x14000fe06  movzx   edx, r8w
0x14000fe0a  add     edx, r15d
0x14000fe0d  cmp     [rbx], dil
0x14000fe10  jz      short loc_14000FE22
0x14000fe12  lea     eax, [rcx+14h]
0x14000fe15  add     eax, edx
0x14000fe17  inc     dword ptr [rbx+4]
0x14000fe1a  mov     [rbx+0Ch], eax
0x14000fe1d  jmp     loc_14000FF34
0x14000fe22  mov     eax, [rbx+8]
0x14000fe25  sub     eax, ecx
0x14000fe27  cmp     eax, edx
0x14000fe29  jnb     short loc_14000FE35
0x14000fe2b  mov     edi, 0C0000023h
0x14000fe30  jmp     loc_14000FF34
0x14000fe35  mov     rdx, [rsi+40h]; Src
0x14000fe39  xor     eax, eax
0x14000fe3b  mov     word ptr [rbp+var_28+2], ax
0x14000fe3f  mov     r8, r15; Size
0x14000fe42  mov     dword ptr [rbp+var_28+0Ch], eax
0x14000fe45  mov     eax, [r9+8]
0x14000fe49  mov     dword ptr [rbp+var_28+4], ecx
0x14000fe4c  add     rcx, [rbx+10h]; void *
0x14000fe50  mov     dword ptr [rbp+var_28+8], eax
0x14000fe53  mov     word ptr [rbp+var_28], r15w
0x14000fe58  call    memmove
0x14000fe5d  add     [rbx+0Ch], r15d
0x14000fe61  xor     r12d, r12d
0x14000fe64  mov     rax, [rsi+48h]
0x14000fe68  mov     r13d, [rbx+0Ch]
0x14000fe6c  movzx   r15d, r14w
0x14000fe70  add     r15d, r13d
0x14000fe73  mov     r14, [rax+40h]
0x14000fe77  mov     rax, [rsi+48h]
0x14000fe7b  add     rax, 40h ; '@'
0x14000fe7f  cmp     r14, rax
0x14000fe82  jz      loc_14000FF10
0x14000fe88  movzx   ecx, word ptr [r14+18h]
0x14000fe8d  lea     rdx, [rbp+Destination]
0x14000fe91  mov     [rbp+Destination.MaximumLength], cx
0x14000fe95  call    BfAllocateUnicodeString
0x14000fe9a  test    eax, eax
0x14000fe9c  js      loc_14000FF3F
0x14000fea2  lea     rdx, [r14+18h]; Source
0x14000fea6  lea     rcx, [rbp+Destination]; Destination
0x14000feaa  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000feb1  nop     dword ptr [rax+rax+00h]
0x14000feb6  mov     edi, eax
0x14000feb8  test    eax, eax
0x14000feba  js      short loc_14000FF34
0x14000febc  mov     r9d, [rbx+0Ch]
0x14000fec0  mov     rdx, [rbx+10h]
0x14000fec4  movzx   ecx, [rbp+Destination.Length]
0x14000fec8  mov     [r9+rdx], cx
0x14000fecd  mov     [r9+rdx+4], r15d
0x14000fed2  add     dword ptr [rbx+0Ch], 8
0x14000fed6  mov     ecx, [r9+rdx+4]
0x14000fedb  add     rcx, [rbx+10h]; void *
0x14000fedf  movzx   r8d, [rbp+Destination.Length]; Size
0x14000fee4  mov     rdx, [rbp+Destination.Buffer]; Src
0x14000fee8  call    memmove
0x14000feed  movzx   eax, [rbp+Destination.Length]
0x14000fef1  lea     rcx, [rbp+Destination]
0x14000fef5  add     r15d, eax
0x14000fef8  call    BfFreeUnicodeString
0x14000fefd  mov     [rbp+Destination.Buffer], 0
0x14000ff05  inc     r12d
0x14000ff08  mov     r14, [r14]
0x14000ff0b  jmp     loc_14000FE77
0x14000ff10  mov     rdx, [rbx+10h]
0x14000ff14  mov     [rbx+0Ch], r15d
0x14000ff18  mov     dword ptr [rbp+var_28+0Ch], r12d
0x14000ff1c  movups  xmm0, [rbp+var_28]
0x14000ff20  mov     eax, [rdx+8]
0x14000ff23  lea     rcx, [rax+rax*4]
0x14000ff27  movups  xmmword ptr [rdx+rcx*4+0Ch], xmm0
0x14000ff2c  mov     [rdx+rcx*4+1Ch], r13d
0x14000ff31  inc     dword ptr [rdx+8]
0x14000ff34  lea     rcx, [rbp+Destination]
0x14000ff38  call    BfFreeUnicodeString
0x14000ff3d  mov     eax, edi
0x14000ff3f  add     rsp, 58h
0x14000ff43  pop     r15
0x14000ff45  pop     r14
0x14000ff47  pop     r13
0x14000ff49  pop     r12
0x14000ff4b  pop     rdi
0x14000ff4c  pop     rsi
0x14000ff4d  pop     rbx
0x14000ff4e  pop     rbp
0x14000ff4f  retn
```
