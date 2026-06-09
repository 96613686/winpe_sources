# CpuInfo::ReloadCpuInfoImpl(void)

- ea: `0x180159128`
- end: `0x180159362`
- name: `?ReloadCpuInfoImpl@CpuInfo@@AEAAXXZ`
- size: `570`
- prototype: `void __fastcall(CpuInfo *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800751f0`
- `0x180159044`
- `0x180165f80`
- `0x1801662a0`
- `0x180166690`
- `0x18016a170`

## callees

- `0x180158f94`
- `0x180159128`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801591b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801591b8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801591d2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801591d2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801591a0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801591a0`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18015915d`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18015915d`

## string_xrefs

- `0x180159199`: `kernel32.dll`

## pseudocode

```c
void __fastcall CpuInfo::ReloadCpuInfoImpl(CpuInfo *this)
{
  __int16 DisabledFeaturesFromRegistry; // si
  __int64 v2; // rbx
  char v3; // di
  DWORD v4; // ecx
  char v5; // r8
  char v6; // r9
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  __int64 (*ProcAddress)(void); // rax
  char v24; // bl
  char v25; // cl
  bool v26; // al
  bool v27; // al
  bool v28; // al
  bool v29; // al
  bool v30; // al
  bool v31; // al
  bool v32; // al
  bool v33; // al
  bool v34; // al

  DisabledFeaturesFromRegistry = LoadDisabledFeaturesFromRegistry();
  if ( (~DisabledFeaturesFromRegistry & 0x3FF) != 0 )
  {
    v2 = 0;
    v3 = 1;
    do
    {
      v4 = CpuInfo::s_cpuInfo[2 * v2 + 2];
      if ( v4 != -1 )
        LOBYTE(CpuInfo::s_cpuInfo[2 * v2 + 1]) = IsProcessorFeaturePresent(v4);
      ++v2;
    }
    while ( v2 != 10 );
    v5 = 0;
    v6 = 0;
    byte_1802BBF6C = 0;
    byte_1802BBF74 = 0;
    byte_1802BBF84 = 0;
    if ( !byte_1802BC9B4 )
    {
      LibraryW = LoadLibraryW(L"kernel32.dll");
      v8 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "GetEnabledXStateFeatures");
        if ( ProcAddress )
          qword_1802BC9B8 = ProcAddress();
        FreeLibrary(v8);
      }
      v5 = byte_1802BBF74;
      v6 = byte_1802BBF6C;
      byte_1802BC9B4 = 1;
    }
    _RAX = 0;
    __asm { cpuid }
    if ( (int)_RAX >= 1 )
    {
      _RAX = 1;
      __asm { cpuid }
      v6 = (_RCX & 0x80000) != 0;
      v5 = (_RCX & 0x100000) != 0;
    }
    if ( (int)_RAX < 7 )
    {
      v25 = byte_1802BBF9C;
      v24 = byte_1802BBF8C;
    }
    else
    {
      _RAX = 7;
      __asm { cpuid }
      v24 = (_RBX & 0x20) != 0;
      v25 = (qword_1802BC9B8 & 0xE0) != 0 && (_RCX & 2) != 0;
    }
    v26 = byte_1802BBF54 && (DisabledFeaturesFromRegistry & 1) == 0;
    byte_1802BBF54 = v26;
    v27 = byte_1802BBF5C && (DisabledFeaturesFromRegistry & 2) == 0;
    byte_1802BBF5C = v27;
    v28 = byte_1802BBF64 && (DisabledFeaturesFromRegistry & 4) == 0;
    byte_1802BBF64 = v28;
    v29 = v6 && (DisabledFeaturesFromRegistry & 8) == 0;
    byte_1802BBF6C = v29;
    v30 = v5 && (DisabledFeaturesFromRegistry & 0x10) == 0;
    byte_1802BBF74 = v30;
    v31 = byte_1802BBF7C && (DisabledFeaturesFromRegistry & 0x20) == 0;
    byte_1802BBF7C = v31;
    v32 = (qword_1802BC9B8 & 4) != 0 && (DisabledFeaturesFromRegistry & 0x40) == 0;
    byte_1802BBF84 = v32;
    v33 = v24 && (DisabledFeaturesFromRegistry & 0x80u) == 0;
    byte_1802BBF8C = v33;
    v34 = (qword_1802BC9B8 & 0xE0) != 0 && (DisabledFeaturesFromRegistry & 0x100) == 0;
    byte_1802BBF94 = v34;
    if ( !v25 || (DisabledFeaturesFromRegistry & 0x200) != 0 )
      v3 = 0;
    byte_1802BBF9C = v3;
  }
}

```

## disassembly

```asm
0x180159128  push    rbx
0x18015912a  push    rbp
0x18015912b  push    rsi
0x18015912c  push    rdi
0x18015912d  sub     rsp, 38h
0x180159131  call    ?LoadDisabledFeaturesFromRegistry@@YAIXZ; LoadDisabledFeaturesFromRegistry(void)
0x180159136  mov     ecx, eax
0x180159138  mov     esi, eax
0x18015913a  not     ecx
0x18015913c  test    ecx, 3FFh
0x180159142  jz      loc_180159359
0x180159148  xor     ebx, ebx
0x18015914a  lea     rbp, ?s_cpuInfo@CpuInfo@@0V1@A; CpuInfo CpuInfo::s_cpuInfo
0x180159151  lea     edi, [rbx+1]
0x180159154  mov     ecx, [rbp+rbx*8+8]; ProcessorFeature
0x180159158  cmp     ecx, 0FFFFFFFFh
0x18015915b  jz      short loc_18015916C
0x18015915d  call    cs:__imp_IsProcessorFeaturePresent
0x180159163  test    eax, eax
0x180159165  setnz   al
0x180159168  mov     [rbp+rbx*8+4], al
0x18015916c  add     rbx, rdi
0x18015916f  cmp     rbx, 0Ah
0x180159173  jnz     short loc_180159154
0x180159175  xor     r8b, r8b
0x180159178  xor     r9b, r9b
0x18015917b  cmp     cs:byte_1802BC9B4, r8b
0x180159182  mov     cs:byte_1802BBF6C, r9b
0x180159189  mov     cs:byte_1802BBF74, r8b
0x180159190  mov     cs:byte_1802BBF84, r8b
0x180159197  jnz     short loc_1801591ED
0x180159199  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1801591a0  call    cs:__imp_LoadLibraryW
0x1801591a6  mov     rbx, rax
0x1801591a9  test    rax, rax
0x1801591ac  jz      short loc_1801591D8
0x1801591ae  lea     rdx, aGetenabledxsta; "GetEnabledXStateFeatures"
0x1801591b5  mov     rcx, rax; hModule
0x1801591b8  call    cs:__imp_GetProcAddress
0x1801591be  test    rax, rax
0x1801591c1  jz      short loc_1801591CF
0x1801591c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801591c8  mov     cs:qword_1802BC9B8, rax
0x1801591cf  mov     rcx, rbx; hLibModule
0x1801591d2  call    cs:__imp_FreeLibrary
0x1801591d8  mov     r8b, cs:byte_1802BBF74
0x1801591df  mov     r9b, cs:byte_1802BBF6C
0x1801591e6  mov     cs:byte_1802BC9B4, dil
0x1801591ed  mov     r10, cs:qword_1802BC9B8
0x1801591f4  mov     r11b, r10b
0x1801591f7  shr     r11b, 2
0x1801591fb  and     r11b, dil
0x1801591fe  and     r10d, 0E0h
0x180159205  setnz   bpl
0x180159209  xor     eax, eax
0x18015920b  xor     ecx, ecx
0x18015920d  cpuid
0x18015920f  cmp     eax, edi
0x180159211  jl      short loc_18015922D
0x180159213  xor     ecx, ecx
0x180159215  mov     eax, edi
0x180159217  cpuid
0x180159219  mov     r9d, ecx
0x18015921c  mov     r8d, ecx
0x18015921f  shr     r9d, 13h
0x180159223  and     r9b, dil
0x180159226  shr     r8d, 14h
0x18015922a  and     r8b, dil
0x18015922d  cmp     eax, 7
0x180159230  jl      short loc_180159254
0x180159232  xor     ecx, ecx
0x180159234  mov     eax, 7
0x180159239  cpuid
0x18015923b  shr     ebx, 5
0x18015923e  and     bl, dil
0x180159241  test    r10, r10
0x180159244  jz      short loc_180159250
0x180159246  test    cl, 2
0x180159249  jz      short loc_180159250
0x18015924b  mov     cl, dil
0x18015924e  jmp     short loc_180159260
0x180159250  xor     cl, cl
0x180159252  jmp     short loc_180159260
0x180159254  mov     cl, cs:byte_1802BBF9C
0x18015925a  mov     bl, cs:byte_1802BBF8C
0x180159260  cmp     cs:byte_1802BBF54, 0
0x180159267  jz      short loc_180159273
0x180159269  test    dil, sil
0x18015926c  jnz     short loc_180159273
0x18015926e  mov     al, dil
0x180159271  jmp     short loc_180159275
0x180159273  xor     al, al
0x180159275  cmp     cs:byte_1802BBF5C, 0
0x18015927c  mov     cs:byte_1802BBF54, al
0x180159282  jz      short loc_18015928F
0x180159284  test    sil, 2
0x180159288  jnz     short loc_18015928F
0x18015928a  mov     al, dil
0x18015928d  jmp     short loc_180159291
0x18015928f  xor     al, al
0x180159291  cmp     cs:byte_1802BBF64, 0
0x180159298  mov     cs:byte_1802BBF5C, al
0x18015929e  jz      short loc_1801592AB
0x1801592a0  test    sil, 4
0x1801592a4  jnz     short loc_1801592AB
0x1801592a6  mov     al, dil
0x1801592a9  jmp     short loc_1801592AD
0x1801592ab  xor     al, al
0x1801592ad  mov     cs:byte_1802BBF64, al
0x1801592b3  test    r9b, r9b
0x1801592b6  jz      short loc_1801592C3
0x1801592b8  test    sil, 8
0x1801592bc  jnz     short loc_1801592C3
0x1801592be  mov     al, dil
0x1801592c1  jmp     short loc_1801592C5
0x1801592c3  xor     al, al
0x1801592c5  mov     cs:byte_1802BBF6C, al
0x1801592cb  test    r8b, r8b
0x1801592ce  jz      short loc_1801592DB
0x1801592d0  test    sil, 10h
0x1801592d4  jnz     short loc_1801592DB
0x1801592d6  mov     al, dil
0x1801592d9  jmp     short loc_1801592DD
0x1801592db  xor     al, al
0x1801592dd  cmp     cs:byte_1802BBF7C, 0
0x1801592e4  mov     cs:byte_1802BBF74, al
0x1801592ea  jz      short loc_1801592F7
0x1801592ec  test    sil, 20h
0x1801592f0  jnz     short loc_1801592F7
0x1801592f2  mov     al, dil
0x1801592f5  jmp     short loc_1801592F9
0x1801592f7  xor     al, al
0x1801592f9  mov     cs:byte_1802BBF7C, al
0x1801592ff  test    r11b, r11b
0x180159302  jz      short loc_18015930F
0x180159304  test    sil, 40h
0x180159308  jnz     short loc_18015930F
0x18015930a  mov     al, dil
0x18015930d  jmp     short loc_180159311
0x18015930f  xor     al, al
0x180159311  mov     cs:byte_1802BBF84, al
0x180159317  test    bl, bl
0x180159319  jz      short loc_180159325
0x18015931b  test    sil, sil
0x18015931e  js      short loc_180159325
0x180159320  mov     al, dil
0x180159323  jmp     short loc_180159327
0x180159325  xor     al, al
0x180159327  mov     cs:byte_1802BBF8C, al
0x18015932d  test    bpl, bpl
0x180159330  jz      short loc_18015933D
0x180159332  bt      esi, 8
0x180159336  jb      short loc_18015933D
0x180159338  mov     al, dil
0x18015933b  jmp     short loc_18015933F
0x18015933d  xor     al, al
0x18015933f  mov     cs:byte_1802BBF94, al
0x180159345  test    cl, cl
0x180159347  jz      short loc_18015934F
0x180159349  bt      esi, 9
0x18015934d  jnb     short loc_180159352
0x18015934f  xor     dil, dil
0x180159352  mov     cs:byte_1802BBF9C, dil
0x180159359  add     rsp, 38h
0x18015935d  pop     rdi
0x18015935e  pop     rsi
0x18015935f  pop     rbp
0x180159360  pop     rbx
0x180159361  retn
```
