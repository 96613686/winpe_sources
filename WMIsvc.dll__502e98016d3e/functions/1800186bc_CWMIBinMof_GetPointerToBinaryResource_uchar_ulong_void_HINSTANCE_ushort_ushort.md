# CWMIBinMof::GetPointerToBinaryResource(uchar * &,ulong &,void * &,HINSTANCE__ * &,ushort *,ushort *)

- ea: `0x1800186bc`
- end: `0x1800187cd`
- name: `?GetPointerToBinaryResource@CWMIBinMof@@AEAAHAEAPEAEAEAKAEAPEAXAEAPEAUHINSTANCE__@@PEAG4@Z`
- size: `273`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this, unsigned __int8 **, unsigned int *, void **, HINSTANCE *, LPCWSTR lpName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002a5c`

## callees

- `0x18000ca20`
- `0x180010df0`
- `0x18001855c`
- `0x1800186bc`
- `0x180019520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018719`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180018719`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800187a6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800187a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018774`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018774`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180018796`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180018796`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018785`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180018785`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180018763`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180018763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001877a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001877a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWMIBinMof::GetPointerToBinaryResource(
        CWMIBinMof *this,
        LPVOID *a2,
        unsigned int *a3,
        void **a4,
        HINSTANCE *a5,
        unsigned __int16 *lpName,
        unsigned __int16 *a7)
{
  unsigned int v10; // esi
  __int64 v11; // rcx
  unsigned __int16 *v12; // rbx
  HMODULE Library; // rax
  wchar_t *v14; // rcx
  HMODULE *v15; // rdi
  WORD v16; // r9
  HRSRC Resource; // rax
  HRSRC v18; // rbx
  HMODULE v19; // rcx
  HGLOBAL v20; // rax
  LPCWSTR lpLibFileName[9]; // [rsp+20h] [rbp-48h] BYREF
  CWMIBinMof *v23; // [rsp+70h] [rbp+8h] BYREF

  v23 = this;
  v10 = 0;
  CWbemTime::CWbemTime((CWbemTime *)lpLibFileName);
  if ( (unsigned int)CWMIBinMof::ExtractFileNameFromKey(v11, lpLibFileName, a7) )
  {
    v12 = lpName;
    if ( lpName )
    {
      Library = LoadLibraryExW(lpLibFileName[0], 0, 2u);
      v15 = a5;
      *a5 = Library;
      if ( Library )
      {
        LOWORD(v23) = 0;
        if ( (unsigned int)CWMIBinMof::UseDefaultLocaleId(v14, v12, (unsigned __int16 *)&v23) )
          v16 = 0;
        else
          v16 = (unsigned __int16)v23;
        Resource = FindResourceExW(*v15, L"MOFDATA", v12, v16);
        v18 = Resource;
        v19 = *v15;
        if ( Resource )
        {
          v20 = LoadResource(v19, Resource);
          *a4 = v20;
          if ( v20 )
          {
            *a2 = LockResource(v20);
            *a3 = SizeofResource(*v15, v18);
            v10 = 1;
          }
        }
        else
        {
          FreeLibrary(v19);
          GetLastError();
        }
      }
    }
  }
  CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(lpLibFileName);
  return v10;
}

```

## disassembly

```asm
0x1800186bc  mov     [rsp+arg_0], rcx
0x1800186c1  push    rbx
0x1800186c2  push    rbp
0x1800186c3  push    rsi
0x1800186c4  push    rdi
0x1800186c5  push    r14
0x1800186c7  push    r15
0x1800186c9  sub     rsp, 38h
0x1800186cd  mov     r14, r9
0x1800186d0  mov     r15, r8
0x1800186d3  mov     rbp, rdx
0x1800186d6  xor     esi, esi
0x1800186d8  lea     rcx, [rsp+68h+lpLibFileName]; this
0x1800186dd  call    ??0CWbemTime@@QEAA@XZ; CWbemTime::CWbemTime(void)
0x1800186e2  nop
0x1800186e3  mov     r8, [rsp+68h+arg_30]
0x1800186eb  lea     rdx, [rsp+68h+lpLibFileName]
0x1800186f0  call    ?ExtractFileNameFromKey@CWMIBinMof@@AEAAHAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@PEAG@Z; CWMIBinMof::ExtractFileNameFromKey(std::unique_ptr<ushort [0]> &,ushort *)
0x1800186f5  test    eax, eax
0x1800186f7  jz      loc_1800187B4
0x1800186fd  mov     rbx, [rsp+68h+lpName]
0x180018705  test    rbx, rbx
0x180018708  jz      loc_1800187B4
0x18001870e  xor     edx, edx; hFile
0x180018710  lea     r8d, [rsi+2]; dwFlags
0x180018714  mov     rcx, [rsp+68h+lpLibFileName]; lpLibFileName
0x180018719  call    cs:__imp_LoadLibraryExW
0x18001871f  mov     rdi, [rsp+68h+arg_20]
0x180018727  mov     [rdi], rax
0x18001872a  test    rax, rax
0x18001872d  jz      loc_1800187B4
0x180018733  xor     eax, eax
0x180018735  mov     word ptr [rsp+68h+arg_0], ax
0x18001873a  lea     r8, [rsp+68h+arg_0]; unsigned __int16 *
0x18001873f  mov     rdx, rbx; unsigned __int16 *
0x180018742  call    ?UseDefaultLocaleId@CWMIBinMof@@AEAAHPEAGAEAG@Z; CWMIBinMof::UseDefaultLocaleId(ushort *,ushort &)
0x180018747  mov     r8, rbx; lpName
0x18001874a  lea     rdx, Type; "MOFDATA"
0x180018751  mov     rcx, [rdi]; hModule
0x180018754  test    eax, eax
0x180018756  jz      short loc_18001875D
0x180018758  xor     r9d, r9d
0x18001875b  jmp     short loc_180018763
0x18001875d  movzx   r9d, word ptr [rsp+68h+arg_0]; wLanguage
0x180018763  call    cs:__imp_FindResourceExW
0x180018769  mov     rbx, rax
0x18001876c  mov     rcx, [rdi]; hModule
0x18001876f  test    rax, rax
0x180018772  jnz     short loc_180018782
0x180018774  call    cs:__imp_FreeLibrary
0x18001877a  call    cs:__imp_GetLastError
0x180018780  jmp     short loc_1800187B4
0x180018782  mov     rdx, rbx; hResInfo
0x180018785  call    cs:__imp_LoadResource
0x18001878b  mov     [r14], rax
0x18001878e  test    rax, rax
0x180018791  jz      short loc_1800187B4
0x180018793  mov     rcx, rax; hResData
0x180018796  call    cs:__imp_LockResource
0x18001879c  mov     [rbp+0], rax
0x1800187a0  mov     rdx, rbx; hResInfo
0x1800187a3  mov     rcx, [rdi]; hModule
0x1800187a6  call    cs:__imp_SizeofResource
0x1800187ac  mov     [r15], eax
0x1800187af  mov     esi, 1
0x1800187b4  lea     rcx, [rsp+68h+lpLibFileName]
0x1800187b9  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x1800187be  mov     eax, esi
0x1800187c0  add     rsp, 38h
0x1800187c4  pop     r15
0x1800187c6  pop     r14
0x1800187c8  pop     rdi
0x1800187c9  pop     rsi
0x1800187ca  pop     rbp
0x1800187cb  pop     rbx
0x1800187cc  retn
```
