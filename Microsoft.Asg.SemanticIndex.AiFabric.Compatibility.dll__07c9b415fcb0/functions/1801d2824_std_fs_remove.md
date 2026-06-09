# __std_fs_remove

- ea: `0x1801d2824`
- end: `0x1801d2a51`
- name: `__std_fs_remove`
- size: `557`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003c3f0`
- `0x1800567e0`

## callees

- `0x1801d219c`
- `0x1801d27cc`
- `0x1801d2824`
- `0x1801f7110`
- `0x180206a58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801d2914`
- `KERNEL32!GetLastError` at `0x1801d296e`
- `KERNEL32!GetLastError` at `0x1801d2a06`
- `KERNEL32!GetLastError` at `0x1801d2914`
- `KERNEL32!GetLastError` at `0x1801d296e`
- `KERNEL32!GetLastError` at `0x1801d2a06`
- `KERNEL32!CloseHandle` at `0x1801d28e0`
- `KERNEL32!CloseHandle` at `0x1801d2984`
- `KERNEL32!CloseHandle` at `0x1801d28e0`
- `KERNEL32!CloseHandle` at `0x1801d2984`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d288e`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d29b0`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d29e4`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d288e`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d29b0`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d29e4`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1801d2960`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1801d2960`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(__int64 a1)
{
  char v2; // di
  int v3; // eax
  int v4; // ecx
  HANDLE v5; // rbx
  HANDLE v6; // rcx
  int v7; // eax
  DWORD LastError; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v4 = v3;
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v16) = 0;
    v11 = v3 - 2;
    if ( !v11
      || (v12 = v11 - 1) == 0
      || (v13 = v12 - 50) == 0
      || (v14 = v13 - 11) == 0
      || (v15 = v14 - 59) == 0
      || v15 == 144 )
    {
      v4 = 0;
    }
    HIDWORD(v16) = v4;
LABEL_10:
    v6 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v16;
LABEL_11:
    if ( !CloseHandle(v6) )
      abort();
    return v16;
  }
  v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
  if ( v7 )
  {
    LOBYTE(v16) = 0;
    HIDWORD(v16) = v7;
    goto LABEL_10;
  }
LABEL_3:
  v5 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    LOBYTE(v16) = 1;
    HIDWORD(v16) = 0;
LABEL_5:
    if ( v5 == (HANDLE)-1LL )
      return v16;
    v6 = v5;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v16) = 0;
    goto LABEL_17;
  }
  if ( GetFileInformationByHandleEx(v5, FileBasicInfo, v19, 0x28u) )
  {
    if ( (v20 & 1) == 0 )
    {
      LOBYTE(v16) = 0;
      goto LABEL_33;
    }
    v20 ^= 1u;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
      goto LABEL_22;
    v10 = anonymous_namespace_::_Set_delete_flag(v5);
    if ( !v10 )
    {
      LOBYTE(v16) = 1;
      HIDWORD(v16) = 0;
      goto LABEL_24;
    }
    if ( v10 == 5 )
    {
      v20 |= 1u;
      LOBYTE(v16) = 0;
      if ( !SetFileInformationByHandle(v5, FileBasicInfo, v19, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v16) = 5;
      goto LABEL_24;
    }
    LOBYTE(v16) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v16) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v16) = 0;
LABEL_23:
  HIDWORD(v16) = GetLastError();
LABEL_24:
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    abort();
  return v16;
}

```

## disassembly

```asm
0x1801d2824  mov     [rsp-8+arg_8], rbx
0x1801d2829  mov     [rsp-8+arg_10], rsi
0x1801d282e  mov     [rsp-8+arg_18], rdi
0x1801d2833  push    rbp
0x1801d2834  mov     rbp, rsp
0x1801d2837  sub     rsp, 70h
0x1801d283b  mov     rax, cs:__security_cookie
0x1801d2842  xor     rax, rsp
0x1801d2845  mov     [rbp+var_10], rax
0x1801d2849  mov     rbx, rcx
0x1801d284c  mov     rdx, rcx
0x1801d284f  xor     esi, esi
0x1801d2851  lea     rcx, [rbp+hFile]
0x1801d2855  mov     r9d, 2200000h
0x1801d285b  mov     r8d, 10180h
0x1801d2861  mov     dil, sil
0x1801d2864  call    __std_fs_open_handle
0x1801d2869  mov     ecx, eax
0x1801d286b  test    eax, eax
0x1801d286d  jnz     short loc_1801D28AA
0x1801d286f  mov     dil, 1
0x1801d2872  mov     rbx, [rbp+hFile]
0x1801d2876  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1801d287a  mov     r9d, 4; dwBufferSize
0x1801d2880  mov     [rbp+FileInformation], 13h
0x1801d2887  mov     rcx, rbx; hFile
0x1801d288a  lea     edx, [r9+11h]; FileInformationClass
0x1801d288e  call    cs:__imp_SetFileInformationByHandle
0x1801d2894  test    eax, eax
0x1801d2896  jz      short loc_1801D2914
0x1801d2898  mov     byte ptr [rbp+var_50], 1
0x1801d289c  mov     dword ptr [rbp+var_50+4], esi
0x1801d289f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801d28a3  jz      short loc_1801D28EE
0x1801d28a5  mov     rcx, rbx
0x1801d28a8  jmp     short loc_1801D28E0
0x1801d28aa  cmp     eax, 5
0x1801d28ad  jnz     loc_1801D2A17
0x1801d28b3  mov     r9d, 2200000h
0x1801d28b9  lea     rcx, [rbp+hFile]
0x1801d28bd  mov     r8d, 10000h
0x1801d28c3  mov     rdx, rbx
0x1801d28c6  call    __std_fs_open_handle
0x1801d28cb  test    eax, eax
0x1801d28cd  jz      short loc_1801D2872
0x1801d28cf  mov     byte ptr [rbp+var_50], sil
0x1801d28d3  mov     dword ptr [rbp+var_50+4], eax
0x1801d28d6  mov     rcx, [rbp+hFile]; hObject
0x1801d28da  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801d28de  jz      short loc_1801D28EE
0x1801d28e0  call    cs:__imp_CloseHandle
0x1801d28e6  test    eax, eax
0x1801d28e8  jz      loc_1801D2A45
0x1801d28ee  mov     rax, [rbp+var_50]
0x1801d28f2  mov     rcx, [rbp+var_10]
0x1801d28f6  xor     rcx, rsp; StackCookie
0x1801d28f9  call    __security_check_cookie
0x1801d28fe  lea     r11, [rsp+70h+var_s0]
0x1801d2903  mov     rbx, [r11+18h]
0x1801d2907  mov     rsi, [r11+20h]
0x1801d290b  mov     rdi, [r11+28h]
0x1801d290f  mov     rsp, r11
0x1801d2912  pop     rbp
0x1801d2913  retn
0x1801d2914  call    cs:__imp_GetLastError
0x1801d291a  mov     ecx, eax
0x1801d291c  sub     ecx, 1
0x1801d291f  jz      short loc_1801D2937
0x1801d2921  sub     ecx, 31h ; '1'
0x1801d2924  jz      short loc_1801D2937
0x1801d2926  cmp     ecx, 25h ; '%'
0x1801d2929  jz      short loc_1801D2937
0x1801d292b  mov     byte ptr [rbp+var_50], sil
0x1801d292f  mov     dword ptr [rbp+var_50+4], eax
0x1801d2932  jmp     loc_1801D289F
0x1801d2937  mov     rcx, rbx; hFile
0x1801d293a  call    _anonymous_namespace____Set_delete_flag
0x1801d293f  test    eax, eax
0x1801d2941  jz      loc_1801D2898
0x1801d2947  cmp     eax, 5
0x1801d294a  jnz     short loc_1801D292B
0x1801d294c  test    dil, dil
0x1801d294f  jz      short loc_1801D292B
0x1801d2951  lea     edi, [rax+23h]
0x1801d2954  xor     edx, edx; FileInformationClass
0x1801d2956  mov     r9d, edi; dwBufferSize
0x1801d2959  lea     r8, [rbp+var_38]; lpFileInformation
0x1801d295d  mov     rcx, rbx; hFile
0x1801d2960  call    cs:__imp_GetFileInformationByHandleEx
0x1801d2966  test    eax, eax
0x1801d2968  jnz     short loc_1801D2997
0x1801d296a  mov     byte ptr [rbp+var_50], sil
0x1801d296e  call    cs:__imp_GetLastError
0x1801d2974  mov     dword ptr [rbp+var_50+4], eax
0x1801d2977  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801d297b  jz      loc_1801D28EE
0x1801d2981  mov     rcx, rbx; hObject
0x1801d2984  call    cs:__imp_CloseHandle
0x1801d298a  test    eax, eax
0x1801d298c  jz      loc_1801D2A4B
0x1801d2992  jmp     loc_1801D28EE
0x1801d2997  mov     eax, [rbp+var_18]
0x1801d299a  test    al, 1
0x1801d299c  jz      short loc_1801D2A11
0x1801d299e  xor     eax, 1
0x1801d29a1  lea     r8, [rbp+var_38]; lpFileInformation
0x1801d29a5  mov     r9d, edi; dwBufferSize
0x1801d29a8  mov     [rbp+var_18], eax
0x1801d29ab  xor     edx, edx; FileInformationClass
0x1801d29ad  mov     rcx, rbx; hFile
0x1801d29b0  call    cs:__imp_SetFileInformationByHandle
0x1801d29b6  test    eax, eax
0x1801d29b8  jz      short loc_1801D296A
0x1801d29ba  mov     rcx, rbx; hFile
0x1801d29bd  call    _anonymous_namespace____Set_delete_flag
0x1801d29c2  test    eax, eax
0x1801d29c4  jnz     short loc_1801D29CF
0x1801d29c6  mov     byte ptr [rbp+var_50], 1
0x1801d29ca  mov     dword ptr [rbp+var_50+4], esi
0x1801d29cd  jmp     short loc_1801D2977
0x1801d29cf  cmp     eax, 5
0x1801d29d2  jnz     short loc_1801D2A02
0x1801d29d4  or      [rbp+var_18], 1
0x1801d29d8  lea     r8, [rbp+var_38]; lpFileInformation
0x1801d29dc  mov     r9d, edi; dwBufferSize
0x1801d29df  xor     edx, edx; FileInformationClass
0x1801d29e1  mov     rcx, rbx; hFile
0x1801d29e4  call    cs:__imp_SetFileInformationByHandle
0x1801d29ea  mov     byte ptr [rbp+var_50], sil
0x1801d29ee  test    eax, eax
0x1801d29f0  jz      loc_1801D296E
0x1801d29f6  mov     dword ptr [rbp+var_50+4], 5
0x1801d29fd  jmp     loc_1801D2977
0x1801d2a02  mov     byte ptr [rbp+var_50], sil
0x1801d2a06  call    cs:__imp_GetLastError
0x1801d2a0c  jmp     loc_1801D292F
0x1801d2a11  mov     byte ptr [rbp+var_50], sil
0x1801d2a15  jmp     short loc_1801D29F6
0x1801d2a17  mov     byte ptr [rbp+var_50], sil
0x1801d2a1b  sub     eax, 2
0x1801d2a1e  jz      short loc_1801D2A3B
0x1801d2a20  sub     eax, 1
0x1801d2a23  jz      short loc_1801D2A3B
0x1801d2a25  sub     eax, 32h ; '2'
0x1801d2a28  jz      short loc_1801D2A3B
0x1801d2a2a  sub     eax, 0Bh
0x1801d2a2d  jz      short loc_1801D2A3B
0x1801d2a2f  sub     eax, 3Bh ; ';'
0x1801d2a32  jz      short loc_1801D2A3B
0x1801d2a34  cmp     eax, 90h
0x1801d2a39  jnz     short loc_1801D2A3D
0x1801d2a3b  mov     ecx, esi
0x1801d2a3d  mov     dword ptr [rbp+var_50+4], ecx
0x1801d2a40  jmp     loc_1801D28D6
0x1801d2a45  call    abort
0x1801d2a4b  call    abort
```
