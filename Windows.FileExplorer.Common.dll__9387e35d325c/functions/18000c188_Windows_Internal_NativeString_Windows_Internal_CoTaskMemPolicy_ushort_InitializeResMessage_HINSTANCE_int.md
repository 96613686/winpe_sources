# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)

- ea: `0x18000c188`
- end: `0x18000c322`
- name: `?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bf50`

## callees

- `0x18000b9b0`
- `0x18000c188`
- `0x18000c330`
- `0x18000c450`
- `0x18000c668`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000c204`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000c204`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000c1f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000c1f2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000c1dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000c1dd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c299`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2ba`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
        __int64 a1,
        HMODULE a2,
        unsigned int a3,
        ...)
{
  char v4; // bp
  void *v6; // rdi
  int Error; // ebx
  HRSRC Resource; // rax
  HGLOBAL v9; // rax
  _WORD *v10; // rax
  unsigned int v11; // edx
  unsigned int v12; // ebp
  WCHAR *v13; // rdx
  int v14; // eax
  unsigned __int64 v15; // rcx
  unsigned __int64 v17; // rax
  WCHAR *lpBuffer; // [rsp+20h] [rbp-78h]
  DWORD nSize; // [rsp+28h] [rbp-70h]
  va_list Arguments; // [rsp+40h] [rbp-58h] BYREF
  LPCVOID lpSource[10]; // [rsp+48h] [rbp-50h] BYREF
  va_list va; // [rsp+B8h] [rbp+20h] BYREF

  va_start(va, a3);
  memset(lpSource, 0, 24);
  v4 = a3;
  v6 = 0;
  Error = -2147467259;
  Resource = FindResourceExW(a2, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  if ( Resource )
  {
    v9 = LoadResource(a2, Resource);
    if ( v9 )
    {
      v10 = LockResource(v9);
      if ( v10 )
      {
        v11 = 0;
        v12 = v4 & 0xF;
        if ( v12 )
        {
          do
          {
            ++v11;
            v10 += (unsigned __int16)*v10 + 1;
          }
          while ( v11 < v12 );
        }
        v13 = v10 + 1;
        if ( !*v10 )
          v13 = (WCHAR *)&String1;
        v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                (__int64)lpSource,
                v13,
                (unsigned __int16)*v10);
        v6 = (void *)lpSource[0];
        Error = v14;
        if ( v14 >= 0 )
        {
          Arguments = 0;
          v15 = 32;
          while ( 1 )
          {
            Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                      (void **)a1,
                      v15);
            if ( Error < 0 )
              break;
            nSize = *(_DWORD *)(a1 + 16);
            lpBuffer = *(WCHAR **)a1;
            va_copy(Arguments, va);
            if ( FormatMessageW(0x400u, v6, 0, 0, lpBuffer, nSize, &Arguments) )
            {
              Error = 0;
LABEL_12:
              if ( Error >= 0 )
              {
                *(_QWORD *)(a1 + 8) = -1;
                goto LABEL_14;
              }
              break;
            }
            Error = ResultFromKnownLastError();
            if ( Error != -2147024774 )
              goto LABEL_12;
            v17 = *(_QWORD *)(a1 + 16);
            v15 = v17 + 32;
            if ( v17 + 32 < v17 )
            {
              Error = -2147024362;
              break;
            }
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
        }
      }
    }
  }
LABEL_14:
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000c188  mov     rax, rsp
0x18000c18b  mov     [rax+18h], r8d
0x18000c18f  mov     [rax+20h], r9
0x18000c193  push    rbx
0x18000c194  push    rbp
0x18000c195  push    rsi
0x18000c196  push    rdi
0x18000c197  push    r12
0x18000c199  push    r14
0x18000c19b  push    r15
0x18000c19d  sub     rsp, 60h
0x18000c1a1  xor     r15d, r15d
0x18000c1a4  mov     r14, rdx
0x18000c1a7  mov     [rax-50h], r15
0x18000c1ab  mov     ebp, r8d
0x18000c1ae  mov     [rax-48h], r15
0x18000c1b2  mov     rsi, rcx
0x18000c1b5  mov     [rax-40h], r15
0x18000c1b9  xor     r9d, r9d; wLanguage
0x18000c1bc  mov     eax, r8d
0x18000c1bf  lea     r12d, [r15+1]
0x18000c1c3  shr     eax, 4
0x18000c1c6  lea     edx, [r15+6]; lpType
0x18000c1ca  add     ax, r12w
0x18000c1ce  mov     rcx, r14; hModule
0x18000c1d1  movzx   r8d, ax; lpName
0x18000c1d5  mov     edi, r15d
0x18000c1d8  mov     ebx, 80004005h
0x18000c1dd  call    cs:__imp_FindResourceExW
0x18000c1e3  test    rax, rax
0x18000c1e6  jz      loc_18000C2B2
0x18000c1ec  mov     rdx, rax; hResInfo
0x18000c1ef  mov     rcx, r14; hModule
0x18000c1f2  call    cs:__imp_LoadResource
0x18000c1f8  test    rax, rax
0x18000c1fb  jz      loc_18000C2B2
0x18000c201  mov     rcx, rax; hResData
0x18000c204  call    cs:__imp_LockResource
0x18000c20a  test    rax, rax
0x18000c20d  jz      loc_18000C2B2
0x18000c213  mov     edx, r15d
0x18000c216  and     ebp, 0Fh
0x18000c219  ja      loc_18000C30B
0x18000c21f  lea     rdx, [rax+2]
0x18000c223  cmp     [rax], r15w
0x18000c227  jz      loc_18000C2FF
0x18000c22d  movzx   r8d, word ptr [rax]
0x18000c231  lea     rcx, [rsp+98h+lpSource]
0x18000c236  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18000c23b  mov     rdi, [rsp+98h+lpSource]
0x18000c240  mov     ebx, eax
0x18000c242  test    eax, eax
0x18000c244  js      short loc_18000C2B2
0x18000c246  mov     [rsp+98h+var_58], r15
0x18000c24b  lea     rbp, [rsp+98h+arg_18]
0x18000c253  mov     ecx, 20h ; ' '
0x18000c258  mov     rdx, rcx
0x18000c25b  mov     rcx, rsi
0x18000c25e  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18000c263  mov     ebx, eax
0x18000c265  test    eax, eax
0x18000c267  js      loc_18000C2F5
0x18000c26d  mov     eax, [rsi+10h]
0x18000c270  lea     rcx, [rsp+98h+var_58]
0x18000c275  mov     [rsp+98h+Arguments], rcx; Arguments
0x18000c27a  xor     r9d, r9d; dwLanguageId
0x18000c27d  mov     [rsp+98h+nSize], eax; nSize
0x18000c281  xor     r8d, r8d; dwMessageId
0x18000c284  mov     rax, [rsi]
0x18000c287  mov     rdx, rdi; lpSource
0x18000c28a  mov     ecx, 400h; dwFlags
0x18000c28f  mov     [rsp+98h+lpBuffer], rax; lpBuffer
0x18000c294  mov     [rsp+98h+var_58], rbp
0x18000c299  call    cs:__imp_FormatMessageW
0x18000c29f  test    eax, eax
0x18000c2a1  jz      short loc_18000C2D1
0x18000c2a3  mov     ebx, r15d
0x18000c2a6  test    ebx, ebx
0x18000c2a8  js      short loc_18000C2F5
0x18000c2aa  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x18000c2b2  test    rdi, rdi
0x18000c2b5  jz      short loc_18000C2C0
0x18000c2b7  mov     rcx, rdi; pv
0x18000c2ba  call    cs:__imp_CoTaskMemFree
0x18000c2c0  mov     eax, ebx
0x18000c2c2  add     rsp, 60h
0x18000c2c6  pop     r15
0x18000c2c8  pop     r14
0x18000c2ca  pop     r12
0x18000c2cc  pop     rdi
0x18000c2cd  pop     rsi
0x18000c2ce  pop     rbp
0x18000c2cf  pop     rbx
0x18000c2d0  retn
0x18000c2d1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c2d6  mov     ebx, eax
0x18000c2d8  cmp     eax, 8007007Ah
0x18000c2dd  jnz     short loc_18000C2A6
0x18000c2df  mov     rax, [rsi+10h]
0x18000c2e3  lea     rcx, [rax+20h]
0x18000c2e7  cmp     rcx, rax
0x18000c2ea  jnb     loc_18000C258
0x18000c2f0  mov     ebx, 80070216h
0x18000c2f5  mov     rcx, rsi
0x18000c2f8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000c2fd  jmp     short loc_18000C2B2
0x18000c2ff  lea     rdx, String1
0x18000c306  jmp     loc_18000C22D
0x18000c30b  movzx   ecx, word ptr [rax]
0x18000c30e  add     edx, r12d
0x18000c311  lea     rax, [rax+rcx*2]
0x18000c315  add     rax, 2
0x18000c319  cmp     edx, ebp
0x18000c31b  jb      short loc_18000C30B
0x18000c31d  jmp     loc_18000C21F
```
