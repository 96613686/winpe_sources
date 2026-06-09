# Perflib004Update

- ea: `0x18002b984`
- end: `0x18002bbd1`
- name: `Perflib004Update`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180038490`

## callees

- `0x180017100`
- `0x1800175c8`
- `0x18002b984`
- `0x18002bbd8`
- `0x18002eb70`
- `0x180058334`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002ba76`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002baca`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002ba76`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002baca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002b9de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002ba17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002b9de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002ba17`
- `KERNEL32!LocalFree` at `0x18002b9bf`
- `KERNEL32!LocalFree` at `0x18002bb21`
- `KERNEL32!LocalFree` at `0x18002b9bf`
- `KERNEL32!LocalFree` at `0x18002bb21`
- `KERNEL32!SearchPathW` at `0x18002ba47`
- `KERNEL32!SearchPathW` at `0x18002bb7e`
- `KERNEL32!SearchPathW` at `0x18002ba47`
- `KERNEL32!SearchPathW` at `0x18002bb7e`

## pseudocode

```c
HLOCAL __fastcall Perflib004Update(const unsigned __int16 *a1)
{
  WCHAR *v1; // rbx
  unsigned int LangIdFromSzLang; // eax
  unsigned int v3; // edi
  UINT SystemDirectoryW; // eax
  __int64 v6; // rsi
  WCHAR *v7; // rax
  const WCHAR *v8; // rdx
  unsigned int v9; // r15d
  unsigned __int16 *v10; // rbp
  int ThreadPreferredUILanguages; // eax
  __int64 v12; // rax
  unsigned __int16 *v13; // r14
  unsigned __int16 v14; // ax
  const unsigned __int16 *v15; // rsi
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // r9
  unsigned int v20; // [rsp+78h] [rbp+10h] BYREF
  int v21; // [rsp+80h] [rbp+18h] BYREF

  v1 = 0;
  LangIdFromSzLang = GetLangIdFromSzLang(a1);
  v20 = 0;
  v3 = LangIdFromSzLang;
  v21 = 0;
  if ( LangIdFromSzLang == 4 || LangIdFromSzLang == 22 )
  {
    SystemDirectoryW = GetSystemDirectoryW(0, 0);
    v6 = SystemDirectoryW;
    if ( SystemDirectoryW )
    {
      v7 = (WCHAR *)operator new(saturated_mul(SystemDirectoryW + 20, 2u));
      v1 = v7;
      if ( v7 )
      {
        if ( GetSystemDirectoryW(v7, v6 + 1) )
        {
          v8 = L"perfc004.dat";
          if ( v3 != 4 )
            v8 = L"perfc016.dat";
          if ( SearchPathW(v1, v8, 0, 0, 0, 0) )
          {
            v9 = v3;
            v10 = &v1[v6 + 1];
            ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v21, 0, &v20);
            if ( !ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789 )
            {
              if ( v20 )
              {
                v12 = operator new(saturated_mul(v20, 2u));
                v13 = (unsigned __int16 *)v12;
                if ( v12 )
                {
                  RtlGetThreadPreferredUILanguages(36, &v21, v12, &v20);
                  if ( v21 )
                  {
                    v14 = *v13;
                    if ( *v13 )
                    {
                      v15 = v13;
                      while ( v14 )
                      {
                        v16 = GetLangIdFromSzLang(v15);
                        if ( (v16 & 0x3FF) == v3 )
                        {
                          v9 = v16;
                          break;
                        }
                        v17 = -1;
                        do
                          ++v17;
                        while ( v15[v17] );
                        v15 += v17 + 1;
                        v14 = *v15;
                      }
                    }
                  }
                  LocalFree(v13);
                }
              }
            }
            PerfGetLangId(v9, 0, v10, 5u);
            StringCchPrintfW(v10 + 5, 0xEu, L"%ws%ws%ws", L"prfc", v10, L".dat");
            if ( SearchPathW(v1, v10 + 5, 0, 0, 0, 0) )
            {
              LOBYTE(v18) = 1;
              PerflibRename004File(v1, v3, v10, v18);
              PerflibRename004File(v1, v3, v10, 0);
              LOBYTE(v19) = 1;
              PerflibRename004File(v1, v3, 0, v19);
              PerflibRename004File(v1, v3, 0, 0);
            }
          }
        }
      }
    }
  }
  return LocalFree(v1);
}

```

## disassembly

```asm
0x18002b984  mov     [rsp+arg_0], rbx
0x18002b989  push    rbp
0x18002b98a  push    rsi
0x18002b98b  push    rdi
0x18002b98c  push    r12
0x18002b98e  push    r13
0x18002b990  push    r14
0x18002b992  push    r15
0x18002b994  sub     rsp, 30h
0x18002b998  xor     r13d, r13d
0x18002b99b  mov     ebx, r13d
0x18002b99e  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18002b9a3  mov     [rsp+68h+arg_8], r13d
0x18002b9a8  mov     edi, eax
0x18002b9aa  mov     [rsp+68h+arg_10], r13d
0x18002b9b2  cmp     eax, 4
0x18002b9b5  jz      short loc_18002B9DA
0x18002b9b7  cmp     eax, 16h
0x18002b9ba  jz      short loc_18002B9DA
0x18002b9bc  mov     rcx, rbx; hMem
0x18002b9bf  call    cs:__imp_LocalFree
0x18002b9c5  mov     rbx, [rsp+68h+arg_0]
0x18002b9ca  add     rsp, 30h
0x18002b9ce  pop     r15
0x18002b9d0  pop     r14
0x18002b9d2  pop     r13
0x18002b9d4  pop     r12
0x18002b9d6  pop     rdi
0x18002b9d7  pop     rsi
0x18002b9d8  pop     rbp
0x18002b9d9  retn
0x18002b9da  xor     edx, edx; uSize
0x18002b9dc  xor     ecx, ecx; lpBuffer
0x18002b9de  call    cs:__imp_GetSystemDirectoryW
0x18002b9e4  mov     esi, eax
0x18002b9e6  test    eax, eax
0x18002b9e8  jz      short loc_18002B9BC
0x18002b9ea  mov     r14d, 2
0x18002b9f0  lea     ecx, [rsi+14h]
0x18002b9f3  mov     eax, r14d
0x18002b9f6  mul     rcx
0x18002b9f9  lea     rcx, [r14-3]
0x18002b9fd  cmovb   rax, rcx
0x18002ba01  mov     rcx, rax
0x18002ba04  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18002ba09  mov     rbx, rax
0x18002ba0c  test    rax, rax
0x18002ba0f  jz      short loc_18002B9BC
0x18002ba11  lea     edx, [rsi+1]; uSize
0x18002ba14  mov     rcx, rax; lpBuffer
0x18002ba17  call    cs:__imp_GetSystemDirectoryW
0x18002ba1d  test    eax, eax
0x18002ba1f  jz      short loc_18002B9BC
0x18002ba21  xor     r9d, r9d; nBufferLength
0x18002ba24  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x18002ba29  xor     r8d, r8d; lpExtension
0x18002ba2c  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x18002ba31  lea     rdx, aPerfc004Dat; "perfc004.dat"
0x18002ba38  mov     rcx, rbx; lpPath
0x18002ba3b  cmp     edi, 4
0x18002ba3e  jz      short loc_18002BA47
0x18002ba40  lea     rdx, FileName; "perfc016.dat"
0x18002ba47  call    cs:__imp_SearchPathW
0x18002ba4d  test    eax, eax
0x18002ba4f  jz      loc_18002B9BC
0x18002ba55  lea     rax, [rsi+1]
0x18002ba59  xor     r8d, r8d
0x18002ba5c  lea     r9, [rsp+68h+arg_8]
0x18002ba61  mov     r15d, edi
0x18002ba64  lea     rdx, [rsp+68h+arg_10]
0x18002ba6c  lea     rbp, [rbx+rax*2]
0x18002ba70  lea     esi, [r8+24h]
0x18002ba74  mov     ecx, esi
0x18002ba76  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18002ba7c  test    eax, eax
0x18002ba7e  jz      short loc_18002BA8B
0x18002ba80  cmp     eax, 0C0000023h
0x18002ba85  jnz     loc_18002BB27
0x18002ba8b  mov     ecx, [rsp+68h+arg_8]
0x18002ba8f  test    ecx, ecx
0x18002ba91  jz      loc_18002BB27
0x18002ba97  mov     rax, r14
0x18002ba9a  mul     rcx
0x18002ba9d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002baa4  cmovb   rax, rcx
0x18002baa8  mov     rcx, rax
0x18002baab  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18002bab0  mov     r14, rax
0x18002bab3  test    rax, rax
0x18002bab6  jz      short loc_18002BB27
0x18002bab8  lea     r9, [rsp+68h+arg_8]
0x18002babd  mov     r8, rax
0x18002bac0  lea     rdx, [rsp+68h+arg_10]
0x18002bac8  mov     ecx, esi
0x18002baca  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18002bad0  cmp     [rsp+68h+arg_10], r13d
0x18002bad8  jbe     short loc_18002BB1E
0x18002bada  movzx   eax, word ptr [r14]
0x18002bade  test    ax, ax
0x18002bae1  jz      short loc_18002BB1E
0x18002bae3  mov     rsi, r14
0x18002bae6  test    ax, ax
0x18002bae9  jz      short loc_18002BB1E
0x18002baeb  mov     rcx, rsi; unsigned __int16 *
0x18002baee  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18002baf3  movzx   ecx, ax
0x18002baf6  and     ecx, 3FFh
0x18002bafc  cmp     ecx, edi
0x18002bafe  jz      short loc_18002BB1B
0x18002bb00  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002bb04  inc     rax
0x18002bb07  cmp     [rsi+rax*2], r13w
0x18002bb0c  jnz     short loc_18002BB04
0x18002bb0e  lea     rsi, [rsi+rax*2]
0x18002bb12  add     rsi, 2
0x18002bb16  movzx   eax, word ptr [rsi]
0x18002bb19  jmp     short loc_18002BAE6
0x18002bb1b  mov     r15d, eax
0x18002bb1e  mov     rcx, r14; hMem
0x18002bb21  call    cs:__imp_LocalFree
0x18002bb27  mov     r9d, 5; unsigned int
0x18002bb2d  mov     r8, rbp; unsigned __int16 *
0x18002bb30  xor     edx, edx; unsigned __int8
0x18002bb32  mov     ecx, r15d; unsigned int
0x18002bb35  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x18002bb3a  lea     r8, aDat; ".dat"
0x18002bb41  mov     edx, 0Eh; unsigned __int64
0x18002bb46  mov     [rsp+68h+lpFilePart], r8
0x18002bb4b  lea     r9, aPrfc; "prfc"
0x18002bb52  lea     r8, aWsWsWs; "%ws%ws%ws"
0x18002bb59  mov     [rsp+68h+lpBuffer], rbp
0x18002bb5e  lea     rcx, [rbp+0Ah]; unsigned __int16 *
0x18002bb62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb67  xor     r9d, r9d; nBufferLength
0x18002bb6a  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x18002bb6f  xor     r8d, r8d; lpExtension
0x18002bb72  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x18002bb77  lea     rdx, [rbp+0Ah]; lpFileName
0x18002bb7b  mov     rcx, rbx; lpPath
0x18002bb7e  call    cs:__imp_SearchPathW
0x18002bb84  test    eax, eax
0x18002bb86  jz      loc_18002B9BC
0x18002bb8c  mov     r9b, 1
0x18002bb8f  mov     r8, rbp
0x18002bb92  mov     edx, edi
0x18002bb94  mov     rcx, rbx
0x18002bb97  call    PerflibRename004File
0x18002bb9c  xor     r9d, r9d
0x18002bb9f  mov     r8, rbp
0x18002bba2  mov     edx, edi
0x18002bba4  mov     rcx, rbx
0x18002bba7  call    PerflibRename004File
0x18002bbac  mov     r9b, 1
0x18002bbaf  xor     r8d, r8d
0x18002bbb2  mov     edx, edi
0x18002bbb4  mov     rcx, rbx
0x18002bbb7  call    PerflibRename004File
0x18002bbbc  xor     r9d, r9d
0x18002bbbf  xor     r8d, r8d
0x18002bbc2  mov     edx, edi
0x18002bbc4  mov     rcx, rbx
0x18002bbc7  call    PerflibRename004File
0x18002bbcc  jmp     loc_18002B9BC
```
