# WimFileHashReadLoop(CFile &,unsigned __int64,CCryptHash &,uchar *,ulong)

- ea: `0x180002edc`
- end: `0x180002f96`
- name: `?WimFileHashReadLoop@@YA_NAEAVCFile@@_KAEAVCCryptHash@@PEAEK@Z`
- size: `186`
- prototype: `char __fastcall(struct CFile *this, unsigned __int64, HCRYPTHASH *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b10`

## callees

- `0x180002a80`
- `0x180002da0`
- `0x180002edc`

## import_xrefs

- `ADVAPI32!CryptHashData` at `0x180002f72`
- `ADVAPI32!CryptHashData` at `0x180002f72`

## pseudocode

```c
char __fastcall WimFileHashReadLoop(struct CFile *this, unsigned __int64 a2, HCRYPTHASH *a3, unsigned __int8 *a4)
{
  unsigned __int64 v6; // rdi
  int v8; // ebp
  unsigned int v9; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v6 = a2;
  if ( !a2 )
    return 1;
  v8 = 1;
  while ( 1 )
  {
    v9 = 0x10000;
    if ( v6 < 0x10000 )
      v9 = v6;
    if ( !CFile::Read(this, v9, a4) )
      break;
    if ( v8 )
    {
      if ( v9 < 0xD0 )
        return 0;
      v12 = *(_QWORD *)(a4 + 188);
      v10 = v12;
      *(_OWORD *)(a4 + 180) = 0;
      if ( !v10 )
      {
        if ( !GetHashDataOffset((struct _WIMHEADER_V1_PACKED *)a4, &v12) )
          return 0;
        v10 = v12;
      }
      v8 = 0;
      *(_QWORD *)(a4 + 188) = v10;
    }
    if ( !CryptHashData(*a3, a4, v9, 0) )
      break;
    v6 -= v9;
    if ( !v6 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180002edc  push    rbx
0x180002ede  push    rbp
0x180002edf  push    rsi
0x180002ee0  push    rdi
0x180002ee1  push    r14
0x180002ee3  push    r15
0x180002ee5  sub     rsp, 28h
0x180002ee9  mov     rsi, r9
0x180002eec  mov     r15, r8
0x180002eef  mov     rdi, rdx
0x180002ef2  mov     r14, rcx
0x180002ef5  test    rdx, rdx
0x180002ef8  jz      loc_180002F83
0x180002efe  mov     ebp, 1
0x180002f03  mov     ebx, 10000h
0x180002f08  cmp     rdi, rbx
0x180002f0b  jnb     short loc_180002F0F
0x180002f0d  mov     ebx, edi
0x180002f0f  mov     r8, rsi; void *
0x180002f12  mov     edx, ebx; unsigned int
0x180002f14  mov     rcx, r14; this
0x180002f17  call    ?Read@CFile@@QEBA_NKPEAX@Z; CFile::Read(ulong,void *)
0x180002f1c  test    al, al
0x180002f1e  jz      short loc_180002F92
0x180002f20  test    ebp, ebp
0x180002f22  jz      short loc_180002F66
0x180002f24  cmp     ebx, 0D0h
0x180002f2a  jb      short loc_180002F92
0x180002f2c  mov     rax, [rsi+0BCh]
0x180002f33  xorps   xmm0, xmm0
0x180002f36  mov     [rsp+58h+arg_8], rax
0x180002f3b  movups  xmmword ptr [rsi+0B4h], xmm0
0x180002f42  test    rax, rax
0x180002f45  jnz     short loc_180002F5D
0x180002f47  lea     rdx, [rsp+58h+arg_8]; unsigned __int64 *
0x180002f4c  mov     rcx, rsi; struct _WIMHEADER_V1_PACKED *
0x180002f4f  call    ?GetHashDataOffset@@YA_NPEAU_WIMHEADER_V1_PACKED@@PEA_K@Z; GetHashDataOffset(_WIMHEADER_V1_PACKED *,unsigned __int64 *)
0x180002f54  test    al, al
0x180002f56  jz      short loc_180002F92
0x180002f58  mov     rax, [rsp+58h+arg_8]
0x180002f5d  xor     ebp, ebp
0x180002f5f  mov     [rsi+0BCh], rax
0x180002f66  mov     rcx, [r15]; hHash
0x180002f69  xor     r9d, r9d; dwFlags
0x180002f6c  mov     r8d, ebx; dwDataLen
0x180002f6f  mov     rdx, rsi; pbData
0x180002f72  call    cs:__imp_CryptHashData
0x180002f78  test    eax, eax
0x180002f7a  jz      short loc_180002F92
0x180002f7c  mov     eax, ebx
0x180002f7e  sub     rdi, rax
0x180002f81  jnz     short loc_180002F03
0x180002f83  mov     al, 1
0x180002f85  add     rsp, 28h
0x180002f89  pop     r15
0x180002f8b  pop     r14
0x180002f8d  pop     rdi
0x180002f8e  pop     rsi
0x180002f8f  pop     rbp
0x180002f90  pop     rbx
0x180002f91  retn
0x180002f92  xor     al, al
0x180002f94  jmp     short loc_180002F85
```
