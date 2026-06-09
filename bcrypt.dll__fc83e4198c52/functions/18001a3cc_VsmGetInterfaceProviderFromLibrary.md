# VsmGetInterfaceProviderFromLibrary

- ea: `0x18001a3cc`
- end: `0x18001a54b`
- name: `VsmGetInterfaceProviderFromLibrary`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a61c`

## callees

- `0x180005060`
- `0x180009430`
- `0x18000a3e8`
- `0x18001a3cc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001a3fc`
- `ntdll!RtlInitUnicodeString` at `0x18001a3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a4f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a4f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a434`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001a434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a448`

## string_xrefs

- `0x18001a518`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18001a3e5`: `bcryptprimitives.dll`

## pseudocode

```c
__int64 __fastcall VsmGetInterfaceProviderFromLibrary(int a1, FARPROC *a2, HMODULE *a3)
{
  int ImagePath; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rcx
  HMODULE Library; // rax
  DWORD LastError; // eax
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  const CHAR *v19; // rdx
  FARPROC ProcAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+78h] [rbp+20h] BYREF

  lpLibFileName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"bcryptprimitives.dll");
  ImagePath = GetImagePath((const void **)&DestinationString, (WCHAR **)&lpLibFileName);
  v7 = ImagePath;
  if ( ImagePath >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    *a3 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v7 = -1073741515;
      v8 = 2205;
      if ( LastError != 126 )
        v7 = -1073741701;
      v9 = v7;
      goto LABEL_26;
    }
    v12 = a1 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  if ( v18 != 1 )
                  {
                    v7 = -1073741637;
                    v8 = 2223;
                    v9 = 3221225659LL;
                    goto LABEL_26;
                  }
                  v19 = "GetKeyEncapsulationInterface";
                }
                else
                {
                  v19 = "GetKeyDerivationInterface";
                }
              }
              else
              {
                v19 = "GetRngInterface";
              }
            }
            else
            {
              v19 = "GetSignatureInterface";
            }
          }
          else
          {
            v19 = "GetSecretAgreementInterface";
          }
        }
        else
        {
          v19 = "GetAsymmetricEncryptionInterface";
        }
      }
      else
      {
        v19 = "GetHashInterface";
      }
    }
    else
    {
      v19 = "GetCipherInterface";
    }
    ProcAddress = GetProcAddress(Library, v19);
    *a2 = ProcAddress;
    if ( ProcAddress )
      goto LABEL_27;
    v7 = -1073741511;
    v8 = 2233;
    v9 = 3221225785LL;
  }
  else
  {
    v8 = 2197;
    v9 = (unsigned int)ImagePath;
  }
LABEL_26:
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v8);
LABEL_27:
  if ( lpLibFileName )
    MSCryptFree((void *)lpLibFileName);
  return v7;
}

```

## disassembly

```asm
0x18001a3cc  push    rbx
0x18001a3ce  push    rdi
0x18001a3cf  push    r14
0x18001a3d1  push    r15
0x18001a3d3  sub     rsp, 38h
0x18001a3d7  mov     r15, rdx
0x18001a3da  mov     [rsp+58h+lpLibFileName], 0
0x18001a3e3  mov     ebx, ecx
0x18001a3e5  lea     rdx, aBcryptprimitiv_0; "bcryptprimitives.dll"
0x18001a3ec  xorps   xmm0, xmm0
0x18001a3ef  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18001a3f4  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18001a3f9  mov     r14, r8
0x18001a3fc  call    cs:__imp_RtlInitUnicodeString
0x18001a403  nop     dword ptr [rax+rax+00h]
0x18001a408  lea     rdx, [rsp+58h+lpLibFileName]
0x18001a40d  lea     rcx, [rsp+58h+DestinationString]
0x18001a412  call    _GetImagePath
0x18001a417  mov     edi, eax
0x18001a419  test    eax, eax
0x18001a41b  jns     short loc_18001A42A
0x18001a41d  mov     r9d, 895h
0x18001a423  mov     ecx, eax
0x18001a425  jmp     loc_18001A518
0x18001a42a  mov     rcx, [rsp+58h+lpLibFileName]; lpLibFileName
0x18001a42f  xor     r8d, r8d; dwFlags
0x18001a432  xor     edx, edx; hFile
0x18001a434  call    cs:__imp_LoadLibraryExW
0x18001a43b  nop     dword ptr [rax+rax+00h]
0x18001a440  mov     [r14], rax
0x18001a443  test    rax, rax
0x18001a446  jnz     short loc_18001A471
0x18001a448  call    cs:__imp_GetLastError
0x18001a44f  nop     dword ptr [rax+rax+00h]
0x18001a454  mov     ecx, 0C000007Bh
0x18001a459  mov     edi, 0C0000135h
0x18001a45e  cmp     eax, 7Eh ; '~'
0x18001a461  mov     r9d, 89Dh
0x18001a467  cmovnz  edi, ecx
0x18001a46a  mov     ecx, edi
0x18001a46c  jmp     loc_18001A518
0x18001a471  sub     ebx, 1
0x18001a474  jz      short loc_18001A4EA
0x18001a476  sub     ebx, 1
0x18001a479  jz      short loc_18001A4E1
0x18001a47b  sub     ebx, 1
0x18001a47e  jz      short loc_18001A4D8
0x18001a480  sub     ebx, 1
0x18001a483  jz      short loc_18001A4CF
0x18001a485  sub     ebx, 1
0x18001a488  jz      short loc_18001A4C6
0x18001a48a  sub     ebx, 1
0x18001a48d  jz      short loc_18001A4BD
0x18001a48f  sub     ebx, 1
0x18001a492  jz      short loc_18001A4B4
0x18001a494  cmp     ebx, 1
0x18001a497  jz      short loc_18001A4AB
0x18001a499  mov     edi, 0C00000BBh
0x18001a49e  mov     r9d, 8AFh
0x18001a4a4  mov     ecx, 0C00000BBh
0x18001a4a9  jmp     short loc_18001A518
0x18001a4ab  lea     rdx, aGetkeyencapsul_0; "GetKeyEncapsulationInterface"
0x18001a4b2  jmp     short loc_18001A4F1
0x18001a4b4  lea     rdx, aGetkeyderivati_0; "GetKeyDerivationInterface"
0x18001a4bb  jmp     short loc_18001A4F1
0x18001a4bd  lea     rdx, aGetrnginterfac_0; "GetRngInterface"
0x18001a4c4  jmp     short loc_18001A4F1
0x18001a4c6  lea     rdx, aGetsignaturein_0; "GetSignatureInterface"
0x18001a4cd  jmp     short loc_18001A4F1
0x18001a4cf  lea     rdx, aGetsecretagree_0; "GetSecretAgreementInterface"
0x18001a4d6  jmp     short loc_18001A4F1
0x18001a4d8  lea     rdx, aGetasymmetrice_0; "GetAsymmetricEncryptionInterface"
0x18001a4df  jmp     short loc_18001A4F1
0x18001a4e1  lea     rdx, ProcName; "GetHashInterface"
0x18001a4e8  jmp     short loc_18001A4F1
0x18001a4ea  lea     rdx, aGetcipherinter_0; "GetCipherInterface"
0x18001a4f1  mov     rcx, rax; hModule
0x18001a4f4  call    cs:__imp_GetProcAddress
0x18001a4fb  nop     dword ptr [rax+rax+00h]
0x18001a500  mov     [r15], rax
0x18001a503  test    rax, rax
0x18001a506  jnz     short loc_18001A52B
0x18001a508  mov     edi, 0C0000139h
0x18001a50d  mov     r9d, 8B9h
0x18001a513  mov     ecx, 0C0000139h
0x18001a518  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001a51f  lea     rdx, aStatus; "Status"
0x18001a526  call    DebugTraceError
0x18001a52b  cmp     [rsp+58h+lpLibFileName], 0
0x18001a531  jz      short loc_18001A53D
0x18001a533  mov     rcx, [rsp+58h+lpLibFileName]
0x18001a538  call    MSCryptFree
0x18001a53d  mov     eax, edi
0x18001a53f  add     rsp, 38h
0x18001a543  pop     r15
0x18001a545  pop     r14
0x18001a547  pop     rdi
0x18001a548  pop     rbx
0x18001a549  retn
```
