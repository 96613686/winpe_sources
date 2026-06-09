# IISCryptoExportHashBlob

- ea: `0x180006ad8`
- end: `0x180006bc5`
- name: `IISCryptoExportHashBlob`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180005bd8`

## callees

- `0x18000478c`
- `0x180004808`
- `0x180004870`
- `0x180006ad8`

## import_xrefs

- `ADVAPI32!CryptGetHashParam` at `0x180006b46`
- `ADVAPI32!CryptGetHashParam` at `0x180006b92`
- `ADVAPI32!CryptGetHashParam` at `0x180006b46`
- `ADVAPI32!CryptGetHashParam` at `0x180006b92`
- `ole32!CoTaskMemFree` at `0x180006ba6`
- `ole32!CoTaskMemFree` at `0x180006ba6`

## pseudocode

```c
__int64 __fastcall IISCryptoExportHashBlob(struct _IC_BLOB **a1, HCRYPTHASH a2)
{
  unsigned int LastError; // ebx
  struct _IC_BLOB *Blob; // rax
  struct _IC_BLOB *v7; // rdi
  DWORD pbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD pdwDataLen; // [rsp+58h] [rbp+20h] BYREF

  pbData = 0;
  if ( dword_18000FC34 )
  {
    pdwDataLen = 4;
    if ( CryptGetHashParam(a2, 4u, (BYTE *)&pbData, &pdwDataLen, 0) )
    {
      Blob = IcpCreateBlob(1648911177, pbData, 0);
      v7 = Blob;
      if ( Blob )
      {
        if ( CryptGetHashParam(a2, 2u, (BYTE *)Blob + 16, &pbData, 0) )
        {
          *a1 = v7;
          return 0;
        }
        LastError = IcpGetLastError();
        CoTaskMemFree(v7);
      }
      else
      {
        return (unsigned int)-2147024888;
      }
    }
    else
    {
      return (unsigned int)IcpGetLastError();
    }
    return LastError;
  }
  if ( a2 == 1750294856 )
    return IISCryptoCreateCleartextBlob(a1, &word_18000C47E, 1u);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180006ad8  mov     [rsp+arg_0], rbx
0x180006add  mov     [rsp+arg_8], rsi
0x180006ae2  push    rdi
0x180006ae3  sub     rsp, 30h
0x180006ae7  cmp     cs:dword_18000FC34, 0
0x180006aee  mov     rbx, rdx
0x180006af1  mov     rsi, rcx
0x180006af4  mov     [rsp+38h+pbData], 0
0x180006afc  jnz     short loc_180006B28
0x180006afe  cmp     rdx, 68536148h
0x180006b05  jnz     short loc_180006B1E
0x180006b07  mov     r8d, 1
0x180006b0d  lea     rdx, word_18000C47E
0x180006b14  call    IISCryptoCreateCleartextBlob
0x180006b19  jmp     loc_180006BB5
0x180006b1e  mov     eax, 80070057h
0x180006b23  jmp     loc_180006BB5
0x180006b28  mov     edx, 4; dwParam
0x180006b2d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180006b35  lea     r9, [rsp+38h+pdwDataLen]; pdwDataLen
0x180006b3a  mov     [rsp+38h+pdwDataLen], edx
0x180006b3e  lea     r8, [rsp+38h+pbData]; pbData
0x180006b43  mov     rcx, rbx; hHash
0x180006b46  call    cs:__imp_CryptGetHashParam
0x180006b4c  test    eax, eax
0x180006b4e  jnz     short loc_180006B59
0x180006b50  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006b55  mov     ebx, eax
0x180006b57  jmp     short loc_180006BAC
0x180006b59  mov     edx, [rsp+38h+pbData]; unsigned int
0x180006b5d  xor     r8d, r8d; unsigned int
0x180006b60  mov     ecx, 62486349h; unsigned int
0x180006b65  call    ?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z; IcpCreateBlob(ulong,ulong,ulong)
0x180006b6a  mov     rdi, rax
0x180006b6d  test    rax, rax
0x180006b70  jnz     short loc_180006B79
0x180006b72  mov     ebx, 80070008h
0x180006b77  jmp     short loc_180006BAC
0x180006b79  lea     r8, [rax+10h]; pbData
0x180006b7d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180006b85  lea     r9, [rsp+38h+pbData]; pdwDataLen
0x180006b8a  mov     edx, 2; dwParam
0x180006b8f  mov     rcx, rbx; hHash
0x180006b92  call    cs:__imp_CryptGetHashParam
0x180006b98  test    eax, eax
0x180006b9a  jnz     short loc_180006BB0
0x180006b9c  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x180006ba1  mov     ebx, eax
0x180006ba3  mov     rcx, rdi; pv
0x180006ba6  call    cs:__imp_CoTaskMemFree
0x180006bac  mov     eax, ebx
0x180006bae  jmp     short loc_180006BB5
0x180006bb0  mov     [rsi], rdi
0x180006bb3  xor     eax, eax
0x180006bb5  mov     rbx, [rsp+38h+arg_0]
0x180006bba  mov     rsi, [rsp+38h+arg_8]
0x180006bbf  add     rsp, 30h
0x180006bc3  pop     rdi
0x180006bc4  retn
```
