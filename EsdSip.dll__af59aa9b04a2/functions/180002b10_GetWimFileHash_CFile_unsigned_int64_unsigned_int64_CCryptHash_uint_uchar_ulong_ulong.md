# GetWimFileHash(CFile &,unsigned __int64,unsigned __int64,CCryptHash &,uint,uchar *,ulong,ulong *)

- ea: `0x180002b10`
- end: `0x180002c02`
- name: `?GetWimFileHash@@YAHAEAVCFile@@_K1AEAVCCryptHash@@IPEAEKPEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned __int64, HCRYPTPROV hProv, HCRYPTHASH *, ALG_ID Algid, BYTE *pbData, DWORD pdwDataLen, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800019e0`
- `0x180002360`

## callees

- `0x180002b10`
- `0x180002edc`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x180002b3e`
- `ADVAPI32!CryptCreateHash` at `0x180002b3e`
- `ADVAPI32!CryptGetHashParam` at `0x180002bbf`
- `ADVAPI32!CryptGetHashParam` at `0x180002bbf`
- `KERNEL32!VirtualFree` at `0x180002bef`
- `KERNEL32!VirtualFree` at `0x180002bef`
- `KERNEL32!VirtualAlloc` at `0x180002b5d`
- `KERNEL32!VirtualAlloc` at `0x180002b5d`
- `KERNEL32!SetFilePointerEx` at `0x180002b7b`
- `KERNEL32!SetFilePointerEx` at `0x180002b7b`

## pseudocode

```c
__int64 __fastcall GetWimFileHash(
        HANDLE *this,
        unsigned __int64 a2,
        HCRYPTPROV hProv,
        HCRYPTHASH *a4,
        ALG_ID Algid,
        BYTE *pbData,
        DWORD pdwDataLen,
        unsigned int *a8)
{
  unsigned int v11; // ebx
  unsigned __int8 *v12; // rdi
  HCRYPTHASH v13; // rcx
  unsigned int phHash; // [rsp+20h] [rbp-38h]

  v11 = 0;
  if ( CryptCreateHash(hProv, Algid, 0, 0, a4) )
  {
    v12 = (unsigned __int8 *)VirtualAlloc(0, 0x10000u, 0x1000u, 4u);
    if ( v12 )
    {
      if ( SetFilePointerEx(this[1], 0, 0, 0) )
      {
        if ( WimFileHashReadLoop((struct CFile *)this, a2, (struct CCryptHash *)a4, v12, phHash) )
        {
          v13 = *a4;
          pdwDataLen = 1024;
          if ( CryptGetHashParam(v13, 2u, pbData, &pdwDataLen, 0) )
          {
            if ( a8 )
              *a8 = pdwDataLen;
            v11 = 1;
          }
        }
      }
      VirtualFree(v12, 0, 0x8000u);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180002b10  push    rbx
0x180002b12  push    rbp
0x180002b13  push    rsi
0x180002b14  push    rdi
0x180002b15  push    r14
0x180002b17  sub     rsp, 30h
0x180002b1b  mov     rax, r8
0x180002b1e  mov     qword ptr [rsp+58h+phHash], r9; unsigned int
0x180002b23  mov     rsi, r9
0x180002b26  mov     r14, rdx
0x180002b29  mov     edx, [rsp+58h+Algid]; Algid
0x180002b30  mov     rbp, rcx
0x180002b33  mov     rcx, rax; hProv
0x180002b36  xor     r9d, r9d; dwFlags
0x180002b39  xor     r8d, r8d; hKey
0x180002b3c  xor     ebx, ebx
0x180002b3e  call    cs:__imp_CryptCreateHash
0x180002b44  test    eax, eax
0x180002b46  jz      loc_180002BF5
0x180002b4c  mov     edx, 10000h; dwSize
0x180002b51  lea     r9d, [rbx+4]; flProtect
0x180002b55  xor     ecx, ecx; lpAddress
0x180002b57  mov     r8d, 1000h; flAllocationType
0x180002b5d  call    cs:__imp_VirtualAlloc
0x180002b63  mov     rdi, rax
0x180002b66  test    rax, rax
0x180002b69  jz      loc_180002BF5
0x180002b6f  mov     rcx, [rbp+8]; hFile
0x180002b73  xor     edx, edx; liDistanceToMove
0x180002b75  xor     r9d, r9d; dwMoveMethod
0x180002b78  xor     r8d, r8d; lpNewFilePointer
0x180002b7b  call    cs:__imp_SetFilePointerEx
0x180002b81  test    eax, eax
0x180002b83  jz      short loc_180002BE4
0x180002b85  mov     r9, rdi; unsigned __int8 *
0x180002b88  mov     r8, rsi; struct CCryptHash *
0x180002b8b  mov     rdx, r14; unsigned __int64
0x180002b8e  mov     rcx, rbp; this
0x180002b91  call    ?WimFileHashReadLoop@@YA_NAEAVCFile@@_KAEAVCCryptHash@@PEAEK@Z; WimFileHashReadLoop(CFile &,unsigned __int64,CCryptHash &,uchar *,ulong)
0x180002b96  test    al, al
0x180002b98  jz      short loc_180002BE4
0x180002b9a  mov     r8, [rsp+58h+pbData]; pbData
0x180002ba2  lea     r9, [rsp+58h+pdwDataLen]; pdwDataLen
0x180002baa  mov     rcx, [rsi]; hHash
0x180002bad  lea     edx, [rbx+2]; dwParam
0x180002bb0  mov     [rsp+58h+pdwDataLen], 400h
0x180002bbb  mov     [rsp+58h+phHash], ebx; dwFlags
0x180002bbf  call    cs:__imp_CryptGetHashParam
0x180002bc5  test    eax, eax
0x180002bc7  jz      short loc_180002BE4
0x180002bc9  mov     rcx, [rsp+58h+arg_38]
0x180002bd1  test    rcx, rcx
0x180002bd4  jz      short loc_180002BDF
0x180002bd6  mov     eax, [rsp+58h+pdwDataLen]
0x180002bdd  mov     [rcx], eax
0x180002bdf  mov     ebx, 1
0x180002be4  xor     edx, edx; dwSize
0x180002be6  mov     r8d, 8000h; dwFreeType
0x180002bec  mov     rcx, rdi; lpAddress
0x180002bef  call    cs:__imp_VirtualFree
0x180002bf5  mov     eax, ebx
0x180002bf7  add     rsp, 30h
0x180002bfb  pop     r14
0x180002bfd  pop     rdi
0x180002bfe  pop     rsi
0x180002bff  pop     rbp
0x180002c00  pop     rbx
0x180002c01  retn
```
