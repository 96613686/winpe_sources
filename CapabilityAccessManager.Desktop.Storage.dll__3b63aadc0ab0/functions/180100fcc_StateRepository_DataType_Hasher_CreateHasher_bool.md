# StateRepository::DataType::Hasher::CreateHasher(bool)

- ea: `0x180100fcc`
- end: `0x1801011a4`
- name: `?CreateHasher@Hasher@DataType@StateRepository@@AEAAJ_N@Z`
- size: `472`
- prototype: `__int64 __fastcall(Common::CryptoProvider **this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800fe310`

## callees

- `0x1800038f0`
- `0x180003b30`
- `0x180003b80`
- `0x1800e4c4c`
- `0x1800eabf4`
- `0x180100fcc`
- `0x1801092e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101019`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180101019`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101137`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180101137`

## string_xrefs

- `0x18010117c`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-hasher.cpp`
- `0x180101168`: `onecore\base\appmodel\common\cryptoprovider.cpp`
- `0x180101010`: `Bcrypt.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::DataType::Hasher::CreateHasher(Common::CryptoProvider **this)
{
  Common::CryptoProvider *v1; // rbx
  HMODULE Library; // rdi
  signed int LastError_0; // eax
  signed int v5; // ebx
  __int64 v6; // rbx
  FARPROC ProcAddress_0; // rax
  _QWORD *v8; // rax
  bool v10; // sf
  __int64 v11; // rdx
  int v12[4]; // [rsp+20h] [rbp-48h]
  __int128 v13; // [rsp+30h] [rbp-38h]
  __int128 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = *this;
  if ( *this )
  {
    Common::CryptoProvider::~CryptoProvider(*this);
    operator delete(v1);
    *this = 0;
  }
  if ( Common::BcryptLibrary::bcryptModule )
    goto LABEL_11;
  Library = LoadLibraryExW(L"Bcrypt.dll", 0, 0);
  if ( !Library )
  {
    LastError_0 = GetLastError_0();
    v5 = LastError_0;
    if ( LastError_0 <= 0 )
    {
LABEL_16:
      v10 = v5 < 0;
      goto LABEL_17;
    }
    v5 = (unsigned __int16)LastError_0;
LABEL_15:
    v5 |= 0x80070000;
    goto LABEL_16;
  }
  *(_OWORD *)v12 = 0;
  v15 = 0;
  v6 = 0;
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    ProcAddress_0 = GetProcAddress_0(Library, (LPCSTR)(&Common::BcryptLibrary::functionNames)[v6]);
    *(_QWORD *)&v12[2 * v6] = ProcAddress_0;
    if ( !ProcAddress_0 )
      break;
    if ( (unsigned __int64)++v6 >= 7 )
    {
      *(_OWORD *)&Common::BcryptLibrary::functions = *(_OWORD *)v12;
      xmmword_180140620 = v13;
      xmmword_180140630 = v14;
      qword_180140640 = v15;
      Common::BcryptLibrary::bcryptModule = Library;
      goto LABEL_11;
    }
  }
  v5 = GetLastError_0();
  FreeLibrary(Library);
  v10 = v5 < 0;
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5;
    goto LABEL_15;
  }
LABEL_17:
  if ( v10 )
  {
    v11 = 57;
    goto LABEL_20;
  }
LABEL_11:
  v8 = operator new(0x350u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    v8[3] = 0;
    *((_DWORD *)v8 + 4) = 0;
    *((_DWORD *)v8 + 8) = 0;
    v8[6] = 0;
    *((_DWORD *)v8 + 10) = 0;
    *((_DWORD *)v8 + 14) = 0;
    *v8 = 0;
    v8[1] = 0;
    v8[105] = 0;
    *((_DWORD *)v8 + 208) = 0;
    *this = (Common::CryptoProvider *)v8;
    return 0;
  }
  v5 = -2147024882;
  v11 = 60;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\appmodel\\common\\cryptoprovider.cpp",
    (const char *)(unsigned int)v5,
    v12[0]);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-hasher.cpp",
    (const char *)(unsigned int)v5,
    v12[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180100fcc  mov     [rsp+arg_8], rbx
0x180100fd1  mov     [rsp+arg_10], rsi
0x180100fd6  push    rdi
0x180100fd7  sub     rsp, 60h
0x180100fdb  mov     rbx, [rcx]
0x180100fde  mov     rsi, rcx
0x180100fe1  test    rbx, rbx
0x180100fe4  jz      short loc_180100FFD
0x180100fe6  mov     rcx, rbx; this
0x180100fe9  call    ??1CryptoProvider@Common@@QEAA@XZ; Common::CryptoProvider::~CryptoProvider(void)
0x180100fee  mov     rcx, rbx; Block
0x180100ff1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180100ff6  mov     qword ptr [rsi], 0
0x180100ffd  mov     rax, cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA; void * Common::BcryptLibrary::bcryptModule
0x180101004  test    rax, rax
0x180101007  jnz     loc_1801010BC
0x18010100d  xor     r8d, r8d; dwFlags
0x180101010  lea     rcx, LibFileName; "Bcrypt.dll"
0x180101017  xor     edx, edx; hFile
0x180101019  call    cs:__imp_LoadLibraryExW
0x18010101f  mov     rdi, rax
0x180101022  test    rax, rax
0x180101025  jnz     short loc_18010103E
0x180101027  call    GetLastError_0
0x18010102c  mov     ebx, eax
0x18010102e  test    eax, eax
0x180101030  jle     loc_18010114A
0x180101036  movzx   ebx, ax
0x180101039  jmp     loc_180101144
0x18010103e  xorps   xmm0, xmm0
0x180101041  xor     eax, eax
0x180101043  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x180101048  mov     [rsp+68h+var_18], rax
0x18010104d  xor     ebx, ebx
0x18010104f  movups  [rsp+68h+var_38], xmm0
0x180101054  movups  [rsp+68h+var_28], xmm0
0x180101059  lea     rdx, ?functionNames@BcryptLibrary@Common@@0PAPEBDA; char const * near * Common::BcryptLibrary::functionNames
0x180101060  mov     rcx, rdi; hModule
0x180101063  mov     rdx, [rdx+rbx*8]; lpProcName
0x180101067  call    GetProcAddress_0
0x18010106c  mov     qword ptr [rsp+rbx*8+68h+var_48], rax; int
0x180101071  test    rax, rax
0x180101074  jz      loc_18010112D
0x18010107a  inc     rbx
0x18010107d  cmp     rbx, 7
0x180101081  jb      short loc_180101059
0x180101083  movups  xmm0, xmmword ptr [rsp+68h+var_48]
0x180101088  movups  xmm1, [rsp+68h+var_38]
0x18010108d  movups  cs:?functions@BcryptLibrary@Common@@0PAP6A_JXZA, xmm0; __int64 (*near * Common::BcryptLibrary::functions)(void)
0x180101094  movups  xmm0, [rsp+68h+var_28]
0x180101099  movups  cs:xmmword_180140620, xmm1
0x1801010a0  movsd   xmm1, [rsp+68h+var_18]
0x1801010a6  movups  cs:xmmword_180140630, xmm0
0x1801010ad  movsd   cs:qword_180140640, xmm1
0x1801010b5  mov     cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA, rdi; void * Common::BcryptLibrary::bcryptModule
0x1801010bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801010c3  mov     ecx, 350h; unsigned __int64
0x1801010c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801010cd  test    rax, rax
0x1801010d0  jz      loc_180101159
0x1801010d6  mov     qword ptr [rax+18h], 0
0x1801010de  mov     dword ptr [rax+10h], 0
0x1801010e5  mov     dword ptr [rax+20h], 0
0x1801010ec  mov     qword ptr [rax+30h], 0
0x1801010f4  mov     dword ptr [rax+28h], 0
0x1801010fb  mov     dword ptr [rax+38h], 0
0x180101102  mov     qword ptr [rax], 0
0x180101109  mov     qword ptr [rax+8], 0
0x180101111  mov     qword ptr [rax+348h], 0
0x18010111c  mov     dword ptr [rax+340h], 0
0x180101126  mov     [rsi], rax
0x180101129  xor     eax, eax
0x18010112b  jmp     short loc_180101192
0x18010112d  call    GetLastError_0
0x180101132  mov     rcx, rdi; hLibModule
0x180101135  mov     ebx, eax
0x180101137  call    cs:__imp_FreeLibrary
0x18010113d  test    ebx, ebx
0x18010113f  jle     short loc_18010114C
0x180101141  movzx   ebx, bx
0x180101144  or      ebx, 80070000h
0x18010114a  test    ebx, ebx
0x18010114c  jns     loc_1801010BC
0x180101152  mov     edx, 39h ; '9'
0x180101157  jmp     short loc_180101163
0x180101159  mov     ebx, 8007000Eh
0x18010115e  mov     edx, 3Ch ; '<'; void *
0x180101163  mov     rcx, [rsp+68h]; this
0x180101168  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\crypto"...
0x18010116f  mov     r9d, ebx; char *
0x180101172  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101177  mov     rcx, [rsp+68h]; this
0x18010117c  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x180101183  mov     r9d, ebx; char *
0x180101186  mov     edx, 8Eh; void *
0x18010118b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101190  mov     eax, ebx
0x180101192  lea     r11, [rsp+68h+var_8]
0x180101197  mov     rbx, [r11+18h]
0x18010119b  mov     rsi, [r11+20h]
0x18010119f  mov     rsp, r11
0x1801011a2  pop     rdi
0x1801011a3  retn
```
