# ValidateMnc(ushort const *,ushort const *,int *)

- ea: `0x180007a30`
- end: `0x180007d62`
- name: `?ValidateMnc@@YAJPEBG0PEAH@Z`
- size: `818`
- prototype: `__int64 __fastcall(char *, char *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006e2c`
- `0x180007a30`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x180007ae6`
- `XmlLite!CreateXmlReader` at `0x180007ae6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180007ac7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180007ac7`

## pseudocode

```c
__int64 __fastcall ValidateMnc(char *a1, char *a2, int *a3)
{
  int v6; // ebx
  int v7; // edi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  int v10; // r9d
  int v11; // edx
  int v12; // esi
  int v13; // eax
  unsigned __int16 *v14; // rax
  int v15; // r8d
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  unsigned __int16 *v20; // rax
  int v21; // r8d
  int v22; // ecx
  void *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  int v25; // [rsp+28h] [rbp-D8h] BYREF
  IStream *ppstm; // [rsp+30h] [rbp-D0h] BYREF
  char *v27; // [rsp+38h] [rbp-C8h] BYREF
  char *v28; // [rsp+40h] [rbp-C0h] BYREF
  char *v29; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszFile[264]; // [rsp+50h] [rbp-B0h] BYREF

  ppstm = 0;
  ppvObject = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  *a3 = 0;
  v6 = MVGetMccLookupTablePath(pszFile);
  if ( v6 >= 0 )
  {
    v6 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
    if ( v6 >= 0 )
    {
      v6 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
        if ( v6 >= 0 )
        {
          v7 = 0;
          v6 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
          if ( v6 >= 0 )
          {
            while ( 1 )
            {
              v6 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v25);
              if ( v6 )
                break;
              if ( v25 == 1 )
              {
                v6 = (*(__int64 (__fastcall **)(void *, char **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                       ppvObject,
                       &v27,
                       0);
                if ( v6 < 0 )
                  break;
                v8 = (unsigned __int16 *)v27;
                v9 = (unsigned __int16 *)v27;
                do
                {
                  v10 = *(unsigned __int16 *)((char *)v9 + (char *)L"country" - v27);
                  v11 = *v9 - v10;
                  if ( v11 )
                    break;
                  ++v9;
                }
                while ( v10 );
                if ( v11 )
                {
                  do
                  {
                    v17 = *(unsigned __int16 *)((char *)v8 + (char *)L"mnc" - v27);
                    v18 = *v8 - v17;
                    if ( v18 )
                      break;
                    ++v8;
                  }
                  while ( v17 );
                  if ( !v18 && v7 )
                  {
                    v19 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppvObject
                                                                                              + 80LL))(
                            ppvObject,
                            L"id",
                            0);
                    v6 = v19;
                    if ( v19 < 0 )
                      break;
                    if ( v19 == 1 )
                    {
LABEL_34:
                      v6 = -2147024809;
                      break;
                    }
                    v6 = (*(__int64 (__fastcall **)(void *, char **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                           ppvObject,
                           &v29,
                           0);
                    if ( v6 < 0 )
                      break;
                    v20 = (unsigned __int16 *)v29;
                    do
                    {
                      v21 = *(unsigned __int16 *)((char *)v20 + a2 - v29);
                      v22 = *v20 - v21;
                      if ( v22 )
                        break;
                      ++v20;
                    }
                    while ( v21 );
                    if ( !v22 )
                    {
                      *a3 = 1;
                      v6 = 0;
                      break;
                    }
                  }
                }
                else
                {
                  v12 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
                  v13 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                          ppvObject,
                          L"mcc",
                          0);
                  v6 = v13;
                  if ( v13 < 0 )
                    break;
                  if ( v13 == 1 )
                    goto LABEL_34;
                  v6 = (*(__int64 (__fastcall **)(void *, char **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                         ppvObject,
                         &v28,
                         0);
                  if ( v6 < 0 )
                    break;
                  v14 = (unsigned __int16 *)v28;
                  v7 = 0;
                  do
                  {
                    v15 = *(unsigned __int16 *)((char *)v14 + a1 - v28);
                    v16 = *v14 - v15;
                    if ( v16 )
                      break;
                    ++v14;
                  }
                  while ( v15 );
                  if ( !v16 )
                  {
                    if ( v12 == 1 )
                      break;
                    v7 = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( ppstm )
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007a30  mov     [rsp-8+arg_0], rbx
0x180007a35  mov     [rsp-8+arg_8], rsi
0x180007a3a  push    rbp
0x180007a3b  push    rdi
0x180007a3c  push    r12
0x180007a3e  push    r14
0x180007a40  push    r15
0x180007a42  lea     rbp, [rsp-170h]
0x180007a4a  sub     rsp, 270h
0x180007a51  mov     rax, cs:__security_cookie
0x180007a58  xor     rax, rsp
0x180007a5b  mov     [rbp+190h+var_30], rax
0x180007a62  mov     r12, rcx
0x180007a65  mov     [rsp+290h+ppstm], 0
0x180007a6e  lea     rcx, [rsp+290h+pszFile]; unsigned __int16 *
0x180007a73  mov     [rsp+290h+ppvObject], 0
0x180007a7c  mov     r14, r8
0x180007a7f  mov     [rsp+290h+var_268], 0
0x180007a87  mov     r15, rdx
0x180007a8a  mov     [rsp+290h+var_258], 0
0x180007a93  mov     [rsp+290h+var_250], 0
0x180007a9c  mov     [rsp+290h+var_248], 0
0x180007aa5  mov     dword ptr [r8], 0
0x180007aac  call    ?MVGetMccLookupTablePath@@YAJPEAGK@Z; MVGetMccLookupTablePath(ushort *,ulong)
0x180007ab1  mov     ebx, eax
0x180007ab3  test    eax, eax
0x180007ab5  js      loc_180007D09
0x180007abb  lea     r8, [rsp+290h+ppstm]; ppstm
0x180007ac0  xor     edx, edx; grfMode
0x180007ac2  lea     rcx, [rsp+290h+pszFile]; pszFile
0x180007ac7  call    cs:__imp_SHCreateStreamOnFileW
0x180007acd  mov     ebx, eax
0x180007acf  test    eax, eax
0x180007ad1  js      loc_180007D09
0x180007ad7  xor     r8d, r8d; pMalloc
0x180007ada  lea     rdx, [rsp+290h+ppvObject]; ppvObject
0x180007adf  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x180007ae6  call    cs:__imp_CreateXmlReader
0x180007aec  mov     ebx, eax
0x180007aee  test    eax, eax
0x180007af0  js      loc_180007D09
0x180007af6  mov     rcx, [rsp+290h+ppvObject]
0x180007afb  xor     r8d, r8d
0x180007afe  mov     rax, [rcx]
0x180007b01  lea     edx, [r8+4]
0x180007b05  mov     rax, [rax+28h]
0x180007b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0e  mov     ebx, eax
0x180007b10  test    eax, eax
0x180007b12  js      loc_180007D09
0x180007b18  mov     rcx, [rsp+290h+ppvObject]
0x180007b1d  xor     edi, edi
0x180007b1f  mov     rdx, [rsp+290h+ppstm]
0x180007b24  mov     rax, [rcx]
0x180007b27  mov     rax, [rax+18h]
0x180007b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b30  mov     ebx, eax
0x180007b32  test    eax, eax
0x180007b34  js      loc_180007D09
0x180007b3a  mov     rcx, [rsp+290h+ppvObject]
0x180007b3f  lea     rdx, [rsp+290h+var_268]
0x180007b44  mov     rax, [rcx]
0x180007b47  mov     rax, [rax+30h]
0x180007b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b50  mov     ebx, eax
0x180007b52  test    eax, eax
0x180007b54  jnz     loc_180007D09
0x180007b5a  cmp     [rsp+290h+var_268], 1
0x180007b5f  jnz     short loc_180007B3A
0x180007b61  mov     rcx, [rsp+290h+ppvObject]
0x180007b66  lea     rdx, [rsp+290h+var_258]
0x180007b6b  xor     r8d, r8d
0x180007b6e  mov     rax, [rcx]
0x180007b71  mov     rax, [rax+70h]
0x180007b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7a  mov     ebx, eax
0x180007b7c  test    eax, eax
0x180007b7e  js      loc_180007D09
0x180007b84  mov     rax, [rsp+290h+var_258]
0x180007b89  lea     r8, ?gc_wszCountry@@3QBGB; "country"
0x180007b90  mov     rcx, rax
0x180007b93  sub     r8, rax
0x180007b96  movzx   edx, word ptr [rcx]
0x180007b99  movzx   r9d, word ptr [rcx+r8]
0x180007b9e  sub     edx, r9d
0x180007ba1  jnz     short loc_180007BAC
0x180007ba3  add     rcx, 2
0x180007ba7  test    r9d, r9d
0x180007baa  jnz     short loc_180007B96
0x180007bac  test    edx, edx
0x180007bae  jnz     loc_180007C5A
0x180007bb4  mov     rcx, [rsp+290h+ppvObject]
0x180007bb9  mov     rax, [rcx]
0x180007bbc  mov     rax, [rax+0A0h]
0x180007bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc8  mov     rcx, [rsp+290h+ppvObject]
0x180007bcd  mov     esi, eax
0x180007bcf  xor     r8d, r8d
0x180007bd2  mov     rdx, [rcx]
0x180007bd5  mov     rax, [rdx+50h]
0x180007bd9  lea     rdx, ?gc_wszMCC@@3QBGB; "mcc"
0x180007be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be5  mov     ebx, eax
0x180007be7  test    eax, eax
0x180007be9  js      loc_180007D09
0x180007bef  cmp     eax, 1
0x180007bf2  jz      loc_180007D04
0x180007bf8  mov     rcx, [rsp+290h+ppvObject]
0x180007bfd  lea     rdx, [rsp+290h+var_250]
0x180007c02  xor     r8d, r8d
0x180007c05  mov     rax, [rcx]
0x180007c08  mov     rax, [rax+80h]
0x180007c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c14  mov     ebx, eax
0x180007c16  test    eax, eax
0x180007c18  js      loc_180007D09
0x180007c1e  mov     rax, [rsp+290h+var_250]
0x180007c23  xor     edi, edi
0x180007c25  mov     rdx, r12
0x180007c28  sub     rdx, rax
0x180007c2b  movzx   ecx, word ptr [rax]
0x180007c2e  movzx   r8d, word ptr [rax+rdx]
0x180007c33  sub     ecx, r8d
0x180007c36  jnz     short loc_180007C41
0x180007c38  add     rax, 2
0x180007c3c  test    r8d, r8d
0x180007c3f  jnz     short loc_180007C2B
0x180007c41  test    ecx, ecx
0x180007c43  jnz     loc_180007B3A
0x180007c49  cmp     esi, 1
0x180007c4c  jz      loc_180007D09
0x180007c52  lea     edi, [rcx+1]
0x180007c55  jmp     loc_180007B3A
0x180007c5a  lea     r8, ?gc_wszMNC@@3QBGB; "mnc"
0x180007c61  sub     r8, rax
0x180007c64  movzx   ecx, word ptr [rax]
0x180007c67  movzx   edx, word ptr [rax+r8]
0x180007c6c  sub     ecx, edx
0x180007c6e  jnz     short loc_180007C78
0x180007c70  add     rax, 2
0x180007c74  test    edx, edx
0x180007c76  jnz     short loc_180007C64
0x180007c78  test    ecx, ecx
0x180007c7a  jnz     loc_180007B3A
0x180007c80  test    edi, edi
0x180007c82  jz      loc_180007B3A
0x180007c88  mov     rcx, [rsp+290h+ppvObject]
0x180007c8d  lea     rdx, ?gc_wszid@@3QBGB; "id"
0x180007c94  xor     r8d, r8d
0x180007c97  mov     rax, [rcx]
0x180007c9a  mov     rax, [rax+50h]
0x180007c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca3  mov     ebx, eax
0x180007ca5  test    eax, eax
0x180007ca7  js      short loc_180007D09
0x180007ca9  cmp     eax, 1
0x180007cac  jz      short loc_180007D04
0x180007cae  mov     rcx, [rsp+290h+ppvObject]
0x180007cb3  lea     rdx, [rsp+290h+var_248]
0x180007cb8  xor     r8d, r8d
0x180007cbb  mov     rax, [rcx]
0x180007cbe  mov     rax, [rax+80h]
0x180007cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cca  mov     ebx, eax
0x180007ccc  test    eax, eax
0x180007cce  js      short loc_180007D09
0x180007cd0  mov     rax, [rsp+290h+var_248]
0x180007cd5  mov     rdx, r15
0x180007cd8  sub     rdx, rax
0x180007cdb  movzx   ecx, word ptr [rax]
0x180007cde  movzx   r8d, word ptr [rax+rdx]
0x180007ce3  sub     ecx, r8d
0x180007ce6  jnz     short loc_180007CF1
0x180007ce8  add     rax, 2
0x180007cec  test    r8d, r8d
0x180007cef  jnz     short loc_180007CDB
0x180007cf1  test    ecx, ecx
0x180007cf3  jnz     loc_180007B3A
0x180007cf9  mov     dword ptr [r14], 1
0x180007d00  xor     ebx, ebx
0x180007d02  jmp     short loc_180007D09
0x180007d04  mov     ebx, 80070057h
0x180007d09  mov     rcx, [rsp+290h+ppvObject]
0x180007d0e  test    rcx, rcx
0x180007d11  jz      short loc_180007D1F
0x180007d13  mov     rax, [rcx]
0x180007d16  mov     rax, [rax+10h]
0x180007d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1f  mov     rcx, [rsp+290h+ppstm]
0x180007d24  test    rcx, rcx
0x180007d27  jz      short loc_180007D35
0x180007d29  mov     rax, [rcx]
0x180007d2c  mov     rax, [rax+10h]
0x180007d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d35  mov     eax, ebx
0x180007d37  mov     rcx, [rbp+190h+var_30]
0x180007d3e  xor     rcx, rsp; StackCookie
0x180007d41  call    __security_check_cookie
0x180007d46  lea     r11, [rsp+290h+var_20]
0x180007d4e  mov     rbx, [r11+30h]
0x180007d52  mov     rsi, [r11+38h]
0x180007d56  mov     rsp, r11
0x180007d59  pop     r15
0x180007d5b  pop     r14
0x180007d5d  pop     r12
0x180007d5f  pop     rdi
0x180007d60  pop     rbp
0x180007d61  retn
```
