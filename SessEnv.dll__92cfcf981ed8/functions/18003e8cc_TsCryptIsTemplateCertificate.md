# TsCryptIsTemplateCertificate

- ea: `0x18003e8cc`
- end: `0x18003ea3c`
- name: `TsCryptIsTemplateCertificate`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002a414`
- `0x18003e5f8`

## callees

- `0x18003e8cc`
- `0x18003f3dc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ea1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ea1a`
- `CRYPT32!CertFindExtension` at `0x18003e91e`
- `CRYPT32!CertFindExtension` at `0x18003e9ab`
- `CRYPT32!CertFindExtension` at `0x18003e91e`
- `CRYPT32!CertFindExtension` at `0x18003e9ab`

## pseudocode

```c
__int64 __fastcall TsCryptIsTemplateCertificate(__int64 a1, unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  HLOCAL v4; // rbx
  int v9; // esi
  PCERT_EXTENSION Extension; // rax
  unsigned __int8 *v11; // rcx
  __int64 v12; // rbp
  int v13; // r8d
  int v14; // edx
  PCERT_EXTENSION v15; // rax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // eax
  unsigned int v20; // [rsp+20h] [rbp-38h]
  DWORD v21; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  hMem = 0;
  v21 = 0;
  *a4 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  Extension = CertFindExtension(
                "1.3.6.1.4.1.311.21.7",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( Extension && a3 )
  {
    v9 = TsCryptDecodeObject(
           *(_DWORD *)a1,
           "1.3.6.1.4.1.311.21.7",
           Extension->Value.pbData,
           Extension->Value.cbData,
           v20,
           &hMem,
           &v21);
    if ( v9 >= 0 )
    {
      v4 = hMem;
      v11 = *(unsigned __int8 **)hMem;
      v12 = a3 - *(_QWORD *)hMem;
      do
      {
        v13 = v11[v12];
        v14 = *v11 - v13;
        if ( v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( v14 )
        goto LABEL_19;
      goto LABEL_10;
    }
    goto LABEL_22;
  }
  v15 = CertFindExtension(
          "1.3.6.1.4.1.311.20.2",
          *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( !v15 || !a2 )
  {
LABEL_18:
    v9 = 0;
    goto LABEL_19;
  }
  v9 = TsCryptDecodeObject(*(_DWORD *)a1, (LPCSTR)0x18, v15->Value.pbData, v15->Value.cbData, v20, &hMem, &v21);
  if ( v9 >= 0 )
  {
    v4 = hMem;
    v16 = *((_QWORD *)hMem + 2) - (_QWORD)a2;
    do
    {
      v17 = *(unsigned __int16 *)((char *)a2 + v16);
      v18 = *a2 - v17;
      if ( v18 )
        break;
      ++a2;
    }
    while ( v17 );
    if ( !v18 )
    {
LABEL_10:
      *a4 = 1;
      goto LABEL_19;
    }
    goto LABEL_18;
  }
LABEL_22:
  v4 = hMem;
LABEL_19:
  if ( v4 )
    LocalFree(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003e8cc  mov     rax, rsp
0x18003e8cf  mov     [rax+10h], rbx
0x18003e8d3  mov     [rax+18h], rbp
0x18003e8d7  push    rsi
0x18003e8d8  push    rdi
0x18003e8d9  push    r14
0x18003e8db  sub     rsp, 40h
0x18003e8df  xor     ebx, ebx
0x18003e8e1  mov     r14, r9
0x18003e8e4  mov     [rax+20h], rbx
0x18003e8e8  mov     rbp, r8
0x18003e8eb  mov     [rax+8], ebx
0x18003e8ee  mov     rdi, rdx
0x18003e8f1  mov     [r9], ebx
0x18003e8f4  mov     rsi, rcx
0x18003e8f7  test    rcx, rcx
0x18003e8fa  jnz     short loc_18003E906
0x18003e8fc  mov     esi, 80070057h
0x18003e901  jmp     loc_18003EA20
0x18003e906  mov     rdx, [rcx+18h]
0x18003e90a  lea     rcx, szStructType; "1.3.6.1.4.1.311.21.7"
0x18003e911  mov     r8, [rdx+0C8h]; rgExtensions
0x18003e918  mov     edx, [rdx+0C0h]; cExtensions
0x18003e91e  call    cs:__imp_CertFindExtension
0x18003e924  test    rax, rax
0x18003e927  jz      short loc_18003E993
0x18003e929  test    rbp, rbp
0x18003e92c  jz      short loc_18003E993
0x18003e92e  mov     r9d, [rax+10h]; cbEncoded
0x18003e932  lea     rcx, [rsp+58h+arg_0]
0x18003e937  mov     r8, [rax+18h]; pbEncoded
0x18003e93b  lea     rdx, szStructType; "1.3.6.1.4.1.311.21.7"
0x18003e942  mov     [rsp+58h+var_28], rcx; DWORD *
0x18003e947  lea     rcx, [rsp+58h+hMem]
0x18003e94c  mov     [rsp+58h+var_30], rcx; void **
0x18003e951  mov     ecx, [rsi]; dwCertEncodingType
0x18003e953  call    ?TsCryptDecodeObject@@YAJKPEBDPEBEKKPEAPEAXPEAK@Z; TsCryptDecodeObject(ulong,char const *,uchar const *,ulong,ulong,void * *,ulong *)
0x18003e958  mov     esi, eax
0x18003e95a  test    eax, eax
0x18003e95c  js      loc_18003EA35
0x18003e962  mov     rbx, [rsp+58h+hMem]
0x18003e967  mov     rcx, [rbx]
0x18003e96a  sub     rbp, rcx
0x18003e96d  movzx   edx, byte ptr [rcx]
0x18003e970  movzx   r8d, byte ptr [rcx+rbp]
0x18003e975  sub     edx, r8d
0x18003e978  jnz     short loc_18003E982
0x18003e97a  inc     rcx
0x18003e97d  test    r8d, r8d
0x18003e980  jnz     short loc_18003E96D
0x18003e982  test    edx, edx
0x18003e984  jnz     loc_18003EA12
0x18003e98a  mov     dword ptr [r14], 1
0x18003e991  jmp     short loc_18003EA12
0x18003e993  mov     rdx, [rsi+18h]
0x18003e997  lea     rcx, a136141311202; "1.3.6.1.4.1.311.20.2"
0x18003e99e  mov     r8, [rdx+0C8h]; rgExtensions
0x18003e9a5  mov     edx, [rdx+0C0h]; cExtensions
0x18003e9ab  call    cs:__imp_CertFindExtension
0x18003e9b1  test    rax, rax
0x18003e9b4  jz      short loc_18003EA10
0x18003e9b6  test    rdi, rdi
0x18003e9b9  jz      short loc_18003EA10
0x18003e9bb  mov     r9d, [rax+10h]; cbEncoded
0x18003e9bf  lea     rcx, [rsp+58h+arg_0]
0x18003e9c4  mov     r8, [rax+18h]; pbEncoded
0x18003e9c8  mov     edx, 18h; lpszStructType
0x18003e9cd  mov     [rsp+58h+var_28], rcx; DWORD *
0x18003e9d2  lea     rcx, [rsp+58h+hMem]
0x18003e9d7  mov     [rsp+58h+var_30], rcx; void **
0x18003e9dc  mov     ecx, [rsi]; dwCertEncodingType
0x18003e9de  call    ?TsCryptDecodeObject@@YAJKPEBDPEBEKKPEAPEAXPEAK@Z; TsCryptDecodeObject(ulong,char const *,uchar const *,ulong,ulong,void * *,ulong *)
0x18003e9e3  mov     esi, eax
0x18003e9e5  test    eax, eax
0x18003e9e7  js      short loc_18003EA35
0x18003e9e9  mov     rbx, [rsp+58h+hMem]
0x18003e9ee  mov     rdx, [rbx+10h]
0x18003e9f2  sub     rdx, rdi
0x18003e9f5  movzx   eax, word ptr [rdi]
0x18003e9f8  movzx   ecx, word ptr [rdi+rdx]
0x18003e9fc  sub     eax, ecx
0x18003e9fe  jnz     short loc_18003EA08
0x18003ea00  add     rdi, 2
0x18003ea04  test    ecx, ecx
0x18003ea06  jnz     short loc_18003E9F5
0x18003ea08  test    eax, eax
0x18003ea0a  jz      loc_18003E98A
0x18003ea10  xor     esi, esi
0x18003ea12  test    rbx, rbx
0x18003ea15  jz      short loc_18003EA20
0x18003ea17  mov     rcx, rbx; hMem
0x18003ea1a  call    cs:__imp_LocalFree
0x18003ea20  mov     rbx, [rsp+58h+arg_8]
0x18003ea25  mov     eax, esi
0x18003ea27  mov     rbp, [rsp+58h+arg_10]
0x18003ea2c  add     rsp, 40h
0x18003ea30  pop     r14
0x18003ea32  pop     rdi
0x18003ea33  pop     rsi
0x18003ea34  retn
0x18003ea35  mov     rbx, [rsp+58h+hMem]
0x18003ea3a  jmp     short loc_18003EA12
```
