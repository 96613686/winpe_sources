# FormatVolume(ushort const *,ushort const *,ushort const *,ushort *)

- ea: `0x14001dedc`
- end: `0x14001e0a7`
- name: `?FormatVolume@@YAHPEBG00PEAG@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14001a714`

## callees

- `0x14001cde8`
- `0x14001dedc`
- `0x14001e0dc`
- `0x140020010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001e000`
- `KERNEL32!CloseHandle` at `0x14001e000`
- `KERNEL32!LoadLibraryExW` at `0x14001df29`
- `KERNEL32!LoadLibraryExW` at `0x14001df29`
- `KERNEL32!SleepEx` at `0x14001e023`
- `KERNEL32!SleepEx` at `0x14001e023`
- `KERNEL32!FreeLibrary` at `0x14001e060`
- `KERNEL32!FreeLibrary` at `0x14001e060`
- `KERNEL32!GetProcAddress` at `0x14001df52`
- `KERNEL32!GetProcAddress` at `0x14001df52`
- `KERNEL32!SetLastError` at `0x14001e010`
- `KERNEL32!SetLastError` at `0x14001e08b`
- `KERNEL32!SetLastError` at `0x14001e010`
- `KERNEL32!SetLastError` at `0x14001e08b`
- `KERNEL32!GetLastError` at `0x14001df39`
- `KERNEL32!GetLastError` at `0x14001dfac`
- `KERNEL32!GetLastError` at `0x14001dff1`
- `KERNEL32!GetLastError` at `0x14001e008`
- `KERNEL32!GetLastError` at `0x14001e055`
- `KERNEL32!GetLastError` at `0x14001e06d`
- `KERNEL32!GetLastError` at `0x14001df39`
- `KERNEL32!GetLastError` at `0x14001dfac`
- `KERNEL32!GetLastError` at `0x14001dff1`
- `KERNEL32!GetLastError` at `0x14001e008`
- `KERNEL32!GetLastError` at `0x14001e055`
- `KERNEL32!GetLastError` at `0x14001e06d`
- `KERNEL32!CreateFileW` at `0x14001dfdf`
- `KERNEL32!CreateFileW` at `0x14001dfdf`

## string_xrefs

- `0x14001df07`: `fmifs.dll`

## pseudocode

```c
__int64 __fastcall FormatVolume(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HMODULE Library; // rax
  HMODULE v9; // r13
  unsigned int v10; // ebx
  DWORD v11; // edi
  int v12; // esi
  FARPROC ProcAddress; // rax
  int v14; // edi
  DWORD LastError; // eax
  char *FileW; // r12
  DWORD v17; // eax
  BOOL v18; // r14d
  void (__fastcall *v20)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-29h]
  __int128 v21; // [rsp+48h] [rbp-21h] BYREF
  __int128 v22; // [rsp+58h] [rbp-11h]
  __int128 v23; // [rsp+68h] [rbp-1h]
  __int64 v24; // [rsp+78h] [rbp+Fh]

  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  Library = LoadLibraryExW(L"fmifs.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    v12 = 0;
    ProcAddress = GetProcAddress(Library, "FormatEx2");
    v20 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( !ProcAddress )
      goto LABEL_14;
    v14 = 30;
    *(_QWORD *)&v21 = 0x500000002LL;
    v22 = 0;
    *((_QWORD *)&v21 + 1) = a3;
    LODWORD(v22) = 0;
    v23 = 0;
    v24 = 0;
    ((void (__fastcall *)(const unsigned __int16 *, _QWORD, const unsigned __int16 *, __int128 *, __int64 (__fastcall *)()))ProcAddress)(
      a1,
      0,
      a2,
      &v21,
      FormatVolume_FormatterCallback);
    while ( 1 )
    {
      LastError = GetLastError();
      if ( LastError != 87 )
        break;
      if ( !v14 )
        goto LABEL_14;
      FileW = (char *)CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
      v10 = FileW + 1 != 0;
      v17 = GetLastError();
      if ( FileW != (char *)-1LL )
      {
        v10 = CloseHandle(FileW);
        v17 = GetLastError();
      }
      SetLastError(v17);
      if ( !v10 )
        goto LABEL_15;
      --v14;
      SleepEx(0x3E8u, 0);
      v20(a1, 0, a2, &v21, FormatVolume_FormatterCallback);
    }
    if ( LastError )
    {
LABEL_14:
      v10 = 0;
    }
    else
    {
      v12 = 1;
      v10 = 1;
      if ( a4 )
        v10 = AssignAccessLetter(a1, a4);
    }
LABEL_15:
    v11 = GetLastError();
    v18 = FreeLibrary(v9);
    if ( !v10 || (v10 = v18, v11 = GetLastError(), !v18) )
    {
      if ( v12 )
        FormatVolume_ZeroVolume(a1);
    }
  }
  else
  {
    v10 = 0;
    v11 = GetLastError();
  }
  SetLastError(v11);
  return v10;
}

```

## disassembly

```asm
0x14001dedc  mov     [rsp-8+arg_8], rdx
0x14001dee1  push    rbp
0x14001dee2  push    rbx
0x14001dee3  push    rsi
0x14001dee4  push    rdi
0x14001dee5  push    r12
0x14001dee7  push    r13
0x14001dee9  push    r14
0x14001deeb  push    r15
0x14001deed  lea     rbp, [rsp-1Fh]
0x14001def2  sub     rsp, 88h
0x14001def9  xorps   xmm0, xmm0
0x14001defc  mov     rbx, r8
0x14001deff  mov     r12, rdx
0x14001df02  mov     r15, rcx
0x14001df05  xor     eax, eax
0x14001df07  lea     rcx, LibFileName; "fmifs.dll"
0x14001df0e  xor     edx, edx; hFile
0x14001df10  mov     [rbp+57h+var_48], rax
0x14001df14  mov     r8d, 800h; dwFlags
0x14001df1a  mov     r14, r9
0x14001df1d  movups  [rbp+57h+var_78], xmm0
0x14001df21  movups  [rbp+57h+var_68], xmm0
0x14001df25  movups  [rbp+57h+var_58], xmm0
0x14001df29  call    cs:__imp_LoadLibraryExW
0x14001df2f  mov     r13, rax
0x14001df32  test    rax, rax
0x14001df35  jnz     short loc_14001DF46
0x14001df37  xor     ebx, ebx
0x14001df39  call    cs:__imp_GetLastError
0x14001df3f  mov     edi, eax
0x14001df41  jmp     loc_14001E089
0x14001df46  lea     rdx, ProcName; "FormatEx2"
0x14001df4d  mov     rcx, r13; hModule
0x14001df50  xor     esi, esi
0x14001df52  call    cs:__imp_GetProcAddress
0x14001df58  mov     [rbp+57h+var_80], rax
0x14001df5c  test    rax, rax
0x14001df5f  jz      loc_14001E053
0x14001df65  xorps   xmm0, xmm0
0x14001df68  lea     edi, [rsi+1Eh]
0x14001df6b  movups  [rbp+57h+var_78], xmm0
0x14001df6f  xor     ecx, ecx
0x14001df71  mov     byte ptr [rbp+57h+var_78], 2
0x14001df75  movups  [rbp+57h+var_68], xmm0
0x14001df79  mov     dword ptr [rbp+57h+var_78+4], 5
0x14001df80  mov     qword ptr [rbp+57h+var_78+8], rbx
0x14001df84  mov     dword ptr [rbp+57h+var_68], ecx
0x14001df87  movups  [rbp+57h+var_58], xmm0
0x14001df8b  mov     [rbp+57h+var_48], rcx
0x14001df8f  lea     rcx, FormatVolume_FormatterCallback
0x14001df96  mov     r8, r12
0x14001df99  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x14001df9e  lea     r9, [rbp+57h+var_78]
0x14001dfa2  mov     rcx, r15
0x14001dfa5  xor     edx, edx
0x14001dfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dfac  call    cs:__imp_GetLastError
0x14001dfb2  cmp     eax, 57h ; 'W'
0x14001dfb5  jnz     short loc_14001E036
0x14001dfb7  test    edi, edi
0x14001dfb9  jz      loc_14001E053
0x14001dfbf  mov     [rsp+0C0h+hTemplateFile], rsi; hTemplateFile
0x14001dfc4  lea     r8d, [rax-54h]; dwShareMode
0x14001dfc8  mov     [rsp+0C0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x14001dfcc  xor     r9d, r9d; lpSecurityAttributes
0x14001dfcf  mov     edx, 20000h; dwDesiredAccess
0x14001dfd4  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x14001dfdc  mov     rcx, r15; lpFileName
0x14001dfdf  call    cs:__imp_CreateFileW
0x14001dfe5  mov     r12, rax
0x14001dfe8  xor     ebx, ebx
0x14001dfea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001dfee  setnz   bl
0x14001dff1  call    cs:__imp_GetLastError
0x14001dff7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14001dffb  jz      short loc_14001E00E
0x14001dffd  mov     rcx, r12; hObject
0x14001e000  call    cs:__imp_CloseHandle
0x14001e006  mov     ebx, eax
0x14001e008  call    cs:__imp_GetLastError
0x14001e00e  mov     ecx, eax; dwErrCode
0x14001e010  call    cs:__imp_SetLastError
0x14001e016  test    ebx, ebx
0x14001e018  jz      short loc_14001E055
0x14001e01a  dec     edi
0x14001e01c  xor     edx, edx; bAlertable
0x14001e01e  mov     ecx, 3E8h; dwMilliseconds
0x14001e023  call    cs:__imp_SleepEx
0x14001e029  mov     rax, [rbp+57h+var_80]
0x14001e02d  mov     r12, [rbp+57h+arg_8]
0x14001e031  jmp     loc_14001DF8F
0x14001e036  test    eax, eax
0x14001e038  jnz     short loc_14001E053
0x14001e03a  lea     esi, [rax+1]
0x14001e03d  mov     ebx, esi
0x14001e03f  test    r14, r14
0x14001e042  jz      short loc_14001E055
0x14001e044  mov     rdx, r14; unsigned __int16 *
0x14001e047  mov     rcx, r15; unsigned __int16 *
0x14001e04a  call    ?AssignAccessLetter@@YAHPEBGPEAG@Z; AssignAccessLetter(ushort const *,ushort *)
0x14001e04f  mov     ebx, eax
0x14001e051  jmp     short loc_14001E055
0x14001e053  xor     ebx, ebx
0x14001e055  call    cs:__imp_GetLastError
0x14001e05b  mov     rcx, r13; hLibModule
0x14001e05e  mov     edi, eax
0x14001e060  call    cs:__imp_FreeLibrary
0x14001e066  mov     r14d, eax
0x14001e069  test    ebx, ebx
0x14001e06b  jz      short loc_14001E07D
0x14001e06d  call    cs:__imp_GetLastError
0x14001e073  mov     ebx, r14d
0x14001e076  mov     edi, eax
0x14001e078  test    r14d, r14d
0x14001e07b  jnz     short loc_14001E089
0x14001e07d  test    esi, esi
0x14001e07f  jz      short loc_14001E089
0x14001e081  mov     rcx, r15; lpFileName
0x14001e084  call    FormatVolume_ZeroVolume
0x14001e089  mov     ecx, edi; dwErrCode
0x14001e08b  call    cs:__imp_SetLastError
0x14001e091  mov     eax, ebx
0x14001e093  add     rsp, 88h
0x14001e09a  pop     r15
0x14001e09c  pop     r14
0x14001e09e  pop     r13
0x14001e0a0  pop     r12
0x14001e0a2  pop     rdi
0x14001e0a3  pop     rsi
0x14001e0a4  pop     rbx
0x14001e0a5  pop     rbp
0x14001e0a6  retn
```
