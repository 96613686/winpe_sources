# DecodeSIPVersion(_CRYPTOAPI_BLOB *,ulong *)

- ea: `0x1800018c8`
- end: `0x1800019d9`
- name: `?DecodeSIPVersion@@YAHPEAU_CRYPTOAPI_BLOB@@PEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002360`

## callees

- `0x1800018c8`

## import_xrefs

- `CRYPT32!CryptDecodeObject` at `0x180001921`
- `CRYPT32!CryptDecodeObject` at `0x180001983`
- `CRYPT32!CryptDecodeObject` at `0x180001921`
- `CRYPT32!CryptDecodeObject` at `0x180001983`
- `KERNEL32!SetLastError` at `0x1800019be`
- `KERNEL32!SetLastError` at `0x1800019be`
- `KERNEL32!LocalFree` at `0x1800019b2`
- `KERNEL32!LocalFree` at `0x1800019b2`
- `KERNEL32!GetLastError` at `0x18000192b`
- `KERNEL32!GetLastError` at `0x18000198d`
- `KERNEL32!GetLastError` at `0x18000192b`
- `KERNEL32!GetLastError` at `0x18000198d`
- `KERNEL32!LocalAlloc` at `0x180001947`
- `KERNEL32!LocalAlloc` at `0x180001947`

## pseudocode

```c
__int64 __fastcall DecodeSIPVersion(struct _CRYPTOAPI_BLOB *a1, unsigned int *a2)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  BYTE *pbData; // rbx
  DWORD cbData; // ebp
  unsigned int *pvStructInfo; // rsi
  DWORD pcbStructInfo; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  pcbStructInfo = 0;
  if ( !a1 )
    goto LABEL_2;
  pbData = a1->pbData;
  cbData = a1->cbData;
  if ( !CryptDecodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", pbData, a1->cbData, 1u, 0, &pcbStructInfo) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  if ( !pcbStructInfo )
  {
LABEL_2:
    LastError = 11;
LABEL_14:
    SetLastError(LastError);
    return v2;
  }
  pvStructInfo = (unsigned int *)LocalAlloc(0x40u, pcbStructInfo);
  if ( !pvStructInfo )
  {
    LastError = 8;
    goto LABEL_14;
  }
  if ( CryptDecodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", pbData, cbData, 1u, pvStructInfo, &pcbStructInfo) )
  {
    if ( pcbStructInfo < 0x28 )
    {
      LastError = 11;
    }
    else
    {
      LastError = 0;
      *a2 = *pvStructInfo;
      v2 = 1;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  LocalFree(pvStructInfo);
  if ( !v2 )
    goto LABEL_14;
  return v2;
}

```

## disassembly

```asm
0x1800018c8  mov     [rsp+arg_8], rbx
0x1800018cd  mov     [rsp+arg_10], rbp
0x1800018d2  push    rsi
0x1800018d3  push    rdi
0x1800018d4  push    r14
0x1800018d6  sub     rsp, 40h
0x1800018da  xor     edi, edi
0x1800018dc  mov     r14, rdx
0x1800018df  mov     [rsp+58h+arg_0], edi
0x1800018e3  test    rcx, rcx
0x1800018e6  jnz     short loc_1800018F2
0x1800018e8  mov     ebx, 0Bh
0x1800018ed  jmp     loc_1800019BC
0x1800018f2  mov     rbx, [rcx+8]
0x1800018f6  lea     rax, [rsp+58h+arg_0]
0x1800018fb  mov     ebp, [rcx]
0x1800018fd  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x180001904  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x180001909  mov     r9d, ebp; cbEncoded
0x18000190c  mov     [rsp+58h+pvStructInfo], rdi; pvStructInfo
0x180001911  mov     r8, rbx; pbEncoded
0x180001914  mov     ecx, 10001h; dwCertEncodingType
0x180001919  mov     [rsp+58h+dwFlags], 1; dwFlags
0x180001921  call    cs:__imp_CryptDecodeObject
0x180001927  test    eax, eax
0x180001929  jnz     short loc_180001938
0x18000192b  call    cs:__imp_GetLastError
0x180001931  mov     ebx, eax
0x180001933  jmp     loc_1800019BC
0x180001938  mov     eax, [rsp+58h+arg_0]
0x18000193c  test    eax, eax
0x18000193e  jz      short loc_1800018E8
0x180001940  mov     edx, eax; uBytes
0x180001942  mov     ecx, 40h ; '@'; uFlags
0x180001947  call    cs:__imp_LocalAlloc
0x18000194d  mov     rsi, rax
0x180001950  test    rax, rax
0x180001953  jnz     short loc_18000195A
0x180001955  lea     ebx, [rax+8]
0x180001958  jmp     short loc_1800019BC
0x18000195a  lea     rax, [rsp+58h+arg_0]
0x18000195f  mov     r9d, ebp; cbEncoded
0x180001962  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x180001967  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x18000196e  mov     [rsp+58h+pvStructInfo], rsi; pvStructInfo
0x180001973  mov     r8, rbx; pbEncoded
0x180001976  mov     ecx, 10001h; dwCertEncodingType
0x18000197b  mov     [rsp+58h+dwFlags], 1; dwFlags
0x180001983  call    cs:__imp_CryptDecodeObject
0x180001989  test    eax, eax
0x18000198b  jnz     short loc_180001997
0x18000198d  call    cs:__imp_GetLastError
0x180001993  mov     ebx, eax
0x180001995  jmp     short loc_1800019AF
0x180001997  cmp     [rsp+58h+arg_0], 28h ; '('
0x18000199c  jb      short loc_1800019AA
0x18000199e  mov     eax, [rsi]
0x1800019a0  xor     ebx, ebx
0x1800019a2  mov     [r14], eax
0x1800019a5  lea     edi, [rbx+1]
0x1800019a8  jmp     short loc_1800019AF
0x1800019aa  mov     ebx, 0Bh
0x1800019af  mov     rcx, rsi; hMem
0x1800019b2  call    cs:__imp_LocalFree
0x1800019b8  test    edi, edi
0x1800019ba  jnz     short loc_1800019C4
0x1800019bc  mov     ecx, ebx; dwErrCode
0x1800019be  call    cs:__imp_SetLastError
0x1800019c4  mov     rbx, [rsp+58h+arg_8]
0x1800019c9  mov     eax, edi
0x1800019cb  mov     rbp, [rsp+58h+arg_10]
0x1800019d0  add     rsp, 40h
0x1800019d4  pop     r14
0x1800019d6  pop     rdi
0x1800019d7  pop     rsi
0x1800019d8  retn
```
