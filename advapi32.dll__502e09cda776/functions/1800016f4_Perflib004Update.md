# Perflib004Update

- ea: `0x1800016f4`
- end: `0x180001972`
- name: `Perflib004Update`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18003c6c8`

## callees

- `0x1800016f4`
- `0x180001978`
- `0x1800028d8`
- `0x180002e40`
- `0x180032954`
- `0x180064484`

## import_xrefs

- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800017ff`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180001859`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800017ff`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180001859`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001755`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001794`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001755`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180001794`
- `KERNEL32!LocalFree` at `0x18000172f`
- `KERNEL32!LocalFree` at `0x1800018b6`
- `KERNEL32!LocalFree` at `0x18000172f`
- `KERNEL32!LocalFree` at `0x1800018b6`
- `KERNEL32!SearchPathW` at `0x1800017ca`
- `KERNEL32!SearchPathW` at `0x180001919`
- `KERNEL32!SearchPathW` at `0x1800017ca`
- `KERNEL32!SearchPathW` at `0x180001919`

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
0x1800016f4  mov     [rsp+arg_0], rbx
0x1800016f9  push    rbp
0x1800016fa  push    rsi
0x1800016fb  push    rdi
0x1800016fc  push    r12
0x1800016fe  push    r13
0x180001700  push    r14
0x180001702  push    r15
0x180001704  sub     rsp, 30h
0x180001708  xor     r13d, r13d
0x18000170b  mov     ebx, r13d
0x18000170e  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180001713  mov     [rsp+68h+arg_8], r13d
0x180001718  mov     edi, eax
0x18000171a  mov     [rsp+68h+arg_10], r13d
0x180001722  cmp     eax, 4
0x180001725  jz      short loc_180001751
0x180001727  cmp     eax, 16h
0x18000172a  jz      short loc_180001751
0x18000172c  mov     rcx, rbx; hMem
0x18000172f  call    cs:__imp_LocalFree
0x180001736  nop     dword ptr [rax+rax+00h]
0x18000173b  mov     rbx, [rsp+68h+arg_0]
0x180001740  add     rsp, 30h
0x180001744  pop     r15
0x180001746  pop     r14
0x180001748  pop     r13
0x18000174a  pop     r12
0x18000174c  pop     rdi
0x18000174d  pop     rsi
0x18000174e  pop     rbp
0x18000174f  retn
0x180001751  xor     edx, edx; uSize
0x180001753  xor     ecx, ecx; lpBuffer
0x180001755  call    cs:__imp_GetSystemDirectoryW
0x18000175c  nop     dword ptr [rax+rax+00h]
0x180001761  mov     esi, eax
0x180001763  test    eax, eax
0x180001765  jz      short loc_18000172C
0x180001767  mov     r14d, 2
0x18000176d  lea     ecx, [rsi+14h]
0x180001770  mov     eax, r14d
0x180001773  mul     rcx
0x180001776  lea     rcx, [r14-3]
0x18000177a  cmovb   rax, rcx
0x18000177e  mov     rcx, rax
0x180001781  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180001786  mov     rbx, rax
0x180001789  test    rax, rax
0x18000178c  jz      short loc_18000172C
0x18000178e  lea     edx, [rsi+1]; uSize
0x180001791  mov     rcx, rax; lpBuffer
0x180001794  call    cs:__imp_GetSystemDirectoryW
0x18000179b  nop     dword ptr [rax+rax+00h]
0x1800017a0  test    eax, eax
0x1800017a2  jz      short loc_18000172C
0x1800017a4  xor     r9d, r9d; nBufferLength
0x1800017a7  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x1800017ac  xor     r8d, r8d; lpExtension
0x1800017af  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x1800017b4  lea     rdx, aPerfc004Dat; "perfc004.dat"
0x1800017bb  mov     rcx, rbx; lpPath
0x1800017be  cmp     edi, 4
0x1800017c1  jz      short loc_1800017CA
0x1800017c3  lea     rdx, FileName; "perfc016.dat"
0x1800017ca  call    cs:__imp_SearchPathW
0x1800017d1  nop     dword ptr [rax+rax+00h]
0x1800017d6  test    eax, eax
0x1800017d8  jz      loc_18000172C
0x1800017de  lea     rax, [rsi+1]
0x1800017e2  xor     r8d, r8d
0x1800017e5  lea     r9, [rsp+68h+arg_8]
0x1800017ea  mov     r15d, edi
0x1800017ed  lea     rdx, [rsp+68h+arg_10]
0x1800017f5  lea     rbp, [rbx+rax*2]
0x1800017f9  lea     esi, [r8+24h]
0x1800017fd  mov     ecx, esi
0x1800017ff  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180001806  nop     dword ptr [rax+rax+00h]
0x18000180b  test    eax, eax
0x18000180d  jz      short loc_18000181A
0x18000180f  cmp     eax, 0C0000023h
0x180001814  jnz     loc_1800018C2
0x18000181a  mov     ecx, [rsp+68h+arg_8]
0x18000181e  test    ecx, ecx
0x180001820  jz      loc_1800018C2
0x180001826  mov     rax, r14
0x180001829  mul     rcx
0x18000182c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001833  cmovb   rax, rcx
0x180001837  mov     rcx, rax
0x18000183a  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000183f  mov     r14, rax
0x180001842  test    rax, rax
0x180001845  jz      short loc_1800018C2
0x180001847  lea     r9, [rsp+68h+arg_8]
0x18000184c  mov     r8, rax
0x18000184f  lea     rdx, [rsp+68h+arg_10]
0x180001857  mov     ecx, esi
0x180001859  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180001860  nop     dword ptr [rax+rax+00h]
0x180001865  cmp     [rsp+68h+arg_10], r13d
0x18000186d  jbe     short loc_1800018B3
0x18000186f  movzx   eax, word ptr [r14]
0x180001873  test    ax, ax
0x180001876  jz      short loc_1800018B3
0x180001878  mov     rsi, r14
0x18000187b  test    ax, ax
0x18000187e  jz      short loc_1800018B3
0x180001880  mov     rcx, rsi; unsigned __int16 *
0x180001883  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180001888  movzx   ecx, ax
0x18000188b  and     ecx, 3FFh
0x180001891  cmp     ecx, edi
0x180001893  jz      short loc_1800018B0
0x180001895  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001899  inc     rax
0x18000189c  cmp     [rsi+rax*2], r13w
0x1800018a1  jnz     short loc_180001899
0x1800018a3  lea     rsi, [rsi+rax*2]
0x1800018a7  add     rsi, 2
0x1800018ab  movzx   eax, word ptr [rsi]
0x1800018ae  jmp     short loc_18000187B
0x1800018b0  mov     r15d, eax
0x1800018b3  mov     rcx, r14; hMem
0x1800018b6  call    cs:__imp_LocalFree
0x1800018bd  nop     dword ptr [rax+rax+00h]
0x1800018c2  mov     r9d, 5; unsigned int
0x1800018c8  mov     r8, rbp; unsigned __int16 *
0x1800018cb  xor     edx, edx; unsigned __int8
0x1800018cd  mov     ecx, r15d; unsigned int
0x1800018d0  call    ?PerfGetLangId@@YAXKEPEAGK@Z; PerfGetLangId(ulong,uchar,ushort *,ulong)
0x1800018d5  lea     r8, aDat; ".dat"
0x1800018dc  mov     edx, 0Eh; unsigned __int64
0x1800018e1  mov     [rsp+68h+lpFilePart], r8
0x1800018e6  lea     r9, aPrfc; "prfc"
0x1800018ed  lea     r8, aWsWsWs; "%ws%ws%ws"
0x1800018f4  mov     [rsp+68h+lpBuffer], rbp
0x1800018f9  lea     rcx, [rbp+0Ah]; unsigned __int16 *
0x1800018fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001902  xor     r9d, r9d; nBufferLength
0x180001905  mov     [rsp+68h+lpFilePart], r13; lpFilePart
0x18000190a  xor     r8d, r8d; lpExtension
0x18000190d  mov     [rsp+68h+lpBuffer], r13; lpBuffer
0x180001912  lea     rdx, [rbp+0Ah]; lpFileName
0x180001916  mov     rcx, rbx; lpPath
0x180001919  call    cs:__imp_SearchPathW
0x180001920  nop     dword ptr [rax+rax+00h]
0x180001925  test    eax, eax
0x180001927  jz      loc_18000172C
0x18000192d  mov     r9b, 1
0x180001930  mov     r8, rbp
0x180001933  mov     edx, edi
0x180001935  mov     rcx, rbx
0x180001938  call    PerflibRename004File
0x18000193d  xor     r9d, r9d
0x180001940  mov     r8, rbp
0x180001943  mov     edx, edi
0x180001945  mov     rcx, rbx
0x180001948  call    PerflibRename004File
0x18000194d  mov     r9b, 1
0x180001950  xor     r8d, r8d
0x180001953  mov     edx, edi
0x180001955  mov     rcx, rbx
0x180001958  call    PerflibRename004File
0x18000195d  xor     r9d, r9d
0x180001960  xor     r8d, r8d
0x180001963  mov     edx, edi
0x180001965  mov     rcx, rbx
0x180001968  call    PerflibRename004File
0x18000196d  jmp     loc_18000172C
```
