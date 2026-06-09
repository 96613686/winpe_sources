# CopyResourceToBuffer(ushort const *,int,CBuffer &)

- ea: `0x180002854`
- end: `0x180002a28`
- name: `?CopyResourceToBuffer@@YAJPEBGHAEAVCBuffer@@@Z`
- size: `468`
- prototype: `int(const unsigned __int16 *, int, struct CBuffer *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002a30`

## callees

- `0x180002854`
- `0x180003fc0`
- `0x18000e3d0`
- `0x180012650`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002874`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180002874`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180002923`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180002923`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000294c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000294c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000297b`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000297b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000292e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000295a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002887`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800028f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000292e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000295a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002987`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028b9`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028d1`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028e9`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028b9`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028d1`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800028e9`

## pseudocode

```c
__int64 __fastcall CopyResourceToBuffer(const unsigned __int16 *a1, unsigned __int16 a2, struct CBuffer *a3)
{
  ulong v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  int v8; // r14d
  unsigned int v9; // r15d
  HRSRC ResourceW; // rsi
  HGLOBAL Resource; // rax
  const unsigned __int8 *v12; // r15
  DWORD v13; // esi
  __int64 result; // rax
  ulong pExceptionObject; // [rsp+20h] [rbp-78h] BYREF
  ulong LastError; // [rsp+24h] [rbp-74h] BYREF
  int v17; // [rsp+28h] [rbp-70h]
  ulong v18; // [rsp+2Ch] [rbp-6Ch] BYREF
  ulong v19; // [rsp+30h] [rbp-68h] BYREF
  ulong v20; // [rsp+34h] [rbp-64h] BYREF
  unsigned __int8 v21[8]; // [rsp+38h] [rbp-60h] BYREF
  __int16 v22; // [rsp+40h] [rbp-58h]
  int v23; // [rsp+42h] [rbp-56h]
  HMODULE v24; // [rsp+48h] [rbp-50h]
  ulong v25; // [rsp+50h] [rbp-48h] BYREF
  ulong v26; // [rsp+B8h] [rbp+20h]

  v5 = 0;
  v24 = 0;
  try
  {
    Library = LoadLibraryExW(a1, 0, 0x20u);
    v7 = Library;
    v24 = Library;
    if ( !Library )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v8 = 0;
    v17 = 0;
    v9 = a2;
    ResourceW = FindResourceW(Library, (LPCWSTR)a2, (LPCWSTR)3);
    if ( !ResourceW )
    {
      ResourceW = FindResourceW(v7, (LPCWSTR)v9, (LPCWSTR)0xE);
      if ( !ResourceW )
      {
        ResourceW = FindResourceW(v7, (LPCWSTR)v9, (LPCWSTR)2);
        if ( !ResourceW )
        {
          LastError = GetLastError();
          throw &LastError;
        }
        v8 = 1;
        v17 = 1;
      }
    }
    Resource = LoadResource(v7, ResourceW);
    if ( !Resource )
    {
      v18 = GetLastError();
      throw &v18;
    }
    v12 = (const unsigned __int8 *)LockResource(Resource);
    if ( !v12 )
    {
      v19 = GetLastError();
      throw &v19;
    }
    v13 = SizeofResource(v7, ResourceW);
    if ( !v13 )
    {
      v20 = GetLastError();
      throw &v20;
    }
    CBuffer::Clear(a3);
    if ( v8 )
    {
      *(_WORD *)&v21[6] = 0;
      v22 = 0;
      *(_WORD *)v21 = 19778;
      *(_DWORD *)&v21[2] = v13 + 14;
      v23 = 54;
      CBuffer::Set(a3, v21, 0xEu);
    }
    CBuffer::Append(a3, v12, v13);
  }
  catch ( ulong v25 )
  {
    v26 = v25;
    goto LABEL_18;
  }
  catch ( ... )
  {
    v26 = -2146435068;
LABEL_18:
    v7 = v24;
    v5 = v26;
    if ( v24 )
      goto LABEL_19;
LABEL_20:
    result = v5;
  }
LABEL_19:
  FreeLibrary(v7);
  goto LABEL_20;
}

```

## disassembly

```asm
0x180002854  push    rbx
0x180002856  push    rsi
0x180002857  push    rdi
0x180002858  push    r12
0x18000285a  push    r14
0x18000285c  push    r15
0x18000285e  sub     rsp, 68h
0x180002862  mov     r12, r8
0x180002865  mov     esi, edx
0x180002867  xor     ebx, ebx
0x180002869  mov     [rsp+98h+var_50], rbx
0x18000286e  xor     edx, edx; hFile
0x180002870  lea     r8d, [rbx+20h]; dwFlags
0x180002874  call    cs:__imp_LoadLibraryExW
0x18000287a  mov     rdi, rax
0x18000287d  mov     [rsp+98h+var_50], rax
0x180002882  test    rax, rax
0x180002885  jnz     short loc_1800028A2
0x180002887  call    cs:__imp_GetLastError
0x18000288d  mov     [rsp+98h+pExceptionObject], eax
0x180002891  lea     rdx, _TI1K; pThrowInfo
0x180002898  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000289d  call    _CxxThrowException_0
0x1800028a2  mov     r14d, ebx
0x1800028a5  mov     [rsp+98h+var_70], ebx
0x1800028a9  movzx   r15d, si
0x1800028ad  mov     r8d, 3; lpType
0x1800028b3  mov     edx, r15d; lpName
0x1800028b6  mov     rcx, rdi; hModule
0x1800028b9  call    cs:__imp_FindResourceW
0x1800028bf  mov     rsi, rax
0x1800028c2  test    rax, rax
0x1800028c5  jnz     short loc_18000291D
0x1800028c7  lea     r8d, [rax+0Eh]; lpType
0x1800028cb  mov     edx, r15d; lpName
0x1800028ce  mov     rcx, rdi; hModule
0x1800028d1  call    cs:__imp_FindResourceW
0x1800028d7  mov     rsi, rax
0x1800028da  test    rax, rax
0x1800028dd  jnz     short loc_18000291D
0x1800028df  lea     r8d, [rax+2]; lpType
0x1800028e3  mov     edx, r15d; lpName
0x1800028e6  mov     rcx, rdi; hModule
0x1800028e9  call    cs:__imp_FindResourceW
0x1800028ef  mov     rsi, rax
0x1800028f2  test    rax, rax
0x1800028f5  jnz     short loc_180002912
0x1800028f7  call    cs:__imp_GetLastError
0x1800028fd  mov     [rsp+98h+var_74], eax
0x180002901  lea     rdx, _TI1K; pThrowInfo
0x180002908  lea     rcx, [rsp+98h+var_74]; pExceptionObject
0x18000290d  call    _CxxThrowException_0
0x180002912  mov     r14d, 1
0x180002918  mov     [rsp+98h+var_70], r14d
0x18000291d  mov     rdx, rsi; hResInfo
0x180002920  mov     rcx, rdi; hModule
0x180002923  call    cs:__imp_LoadResource
0x180002929  test    rax, rax
0x18000292c  jnz     short loc_180002949
0x18000292e  call    cs:__imp_GetLastError
0x180002934  mov     [rsp+98h+var_6C], eax
0x180002938  lea     rdx, _TI1K; pThrowInfo
0x18000293f  lea     rcx, [rsp+98h+var_6C]; pExceptionObject
0x180002944  call    _CxxThrowException_0
0x180002949  mov     rcx, rax; hResData
0x18000294c  call    cs:__imp_LockResource
0x180002952  mov     r15, rax
0x180002955  test    rax, rax
0x180002958  jnz     short loc_180002975
0x18000295a  call    cs:__imp_GetLastError
0x180002960  mov     [rsp+98h+var_68], eax
0x180002964  lea     rdx, _TI1K; pThrowInfo
0x18000296b  lea     rcx, [rsp+98h+var_68]; pExceptionObject
0x180002970  call    _CxxThrowException_0
0x180002975  mov     rdx, rsi; hResInfo
0x180002978  mov     rcx, rdi; hModule
0x18000297b  call    cs:__imp_SizeofResource
0x180002981  mov     esi, eax
0x180002983  test    eax, eax
0x180002985  jnz     short loc_1800029A2
0x180002987  call    cs:__imp_GetLastError
0x18000298d  mov     [rsp+98h+var_64], eax
0x180002991  lea     rdx, _TI1K; pThrowInfo
0x180002998  lea     rcx, [rsp+98h+var_64]; pExceptionObject
0x18000299d  call    _CxxThrowException_0
0x1800029a2  mov     rcx, r12; this
0x1800029a5  call    ?Clear@CBuffer@@QEAAXXZ; CBuffer::Clear(void)
0x1800029aa  test    r14d, r14d
0x1800029ad  jz      short loc_1800029EB
0x1800029af  xor     eax, eax
0x1800029b1  mov     qword ptr [rsp+98h+var_60], rax
0x1800029b6  mov     [rsp+98h+var_58], eax
0x1800029ba  mov     [rsp+98h+var_54], ax
0x1800029bf  mov     eax, 4D42h
0x1800029c4  mov     word ptr [rsp+98h+var_60], ax
0x1800029c9  lea     eax, [rsi+0Eh]
0x1800029cc  mov     dword ptr [rsp+98h+var_60+2], eax
0x1800029d0  mov     [rsp+98h+var_58+2], 36h ; '6'
0x1800029d8  mov     r8d, 0Eh; unsigned int
0x1800029de  lea     rdx, [rsp+98h+var_60]; unsigned __int8 *
0x1800029e3  mov     rcx, r12; this
0x1800029e6  call    ?Set@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Set(uchar const * const,ulong)
0x1800029eb  mov     r8d, esi; unsigned int
0x1800029ee  mov     rdx, r15; unsigned __int8 *
0x1800029f1  mov     rcx, r12; this
0x1800029f4  call    ?Append@CBuffer@@QEAAPEAEQEBEK@Z; CBuffer::Append(uchar const * const,ulong)
0x1800029f9  nop
0x1800029fa  jmp     short loc_180002A0F
0x1800029fc  jmp     short $+2
0x1800029fe  mov     rdi, [rsp+98h+var_50]
0x180002a03  mov     ebx, [rsp+98h+arg_18]
0x180002a0a  test    rdi, rdi
0x180002a0d  jz      short loc_180002A18
0x180002a0f  mov     rcx, rdi; hLibModule
0x180002a12  call    cs:__imp_FreeLibrary
0x180002a18  mov     eax, ebx
0x180002a1a  add     rsp, 68h
0x180002a1e  pop     r15
0x180002a20  pop     r14
0x180002a22  pop     r12
0x180002a24  pop     rdi
0x180002a25  pop     rsi
0x180002a26  pop     rbx
0x180002a27  retn
```
