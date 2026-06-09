# sub_1800ADDA4

- ea: `0x1800adda4`
- end: `0x1800adf6c`
- name: `sub_1800ADDA4`
- size: `456`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18006e720`
- `0x1800e45f8`
- `0x1800e4920`

## callees

- `0x180009534`
- `0x18000a69c`
- `0x1800106b8`
- `0x1800adda4`
- `0x1800f4270`
- `0x1800fea68`
- `0x18013b830`
- `0x18013b890`
- `0x18013bf50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ade0f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ade0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ade27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ade27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ade9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ade9e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800ade6f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800ade6f`

## string_xrefs

- `0x1800ade08`: `kernelbase.dll`
- `0x1800ade1d`: `GetTempPath2W`

## pseudocode

```c
__int64 __fastcall sub_1800ADDA4(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  __int64 v7; // rax
  __int64 v8; // r8
  __int128 *v9; // r9
  unsigned __int64 v10; // rdx
  __int64 v11; // rbx
  __int128 v13; // [rsp+20h] [rbp-E0h]
  __int128 v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v16; // [rsp+48h] [rbp-B8h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v17 = a1;
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = &off_180218888;
  sub_18013BF50(Buffer, 0, 520);
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTempPath2W");
    if ( ProcAddress )
    {
      if ( !((unsigned int (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer) )
      {
        LODWORD(v13) = 22;
        *((_QWORD *)&v13 + 1) = &off_18018C1A0;
        *(_OWORD *)a2 = v13;
      }
LABEL_8:
      FreeLibrary(v5);
      goto LABEL_9;
    }
  }
  if ( !GetTempPathW(0x104u, Buffer) )
  {
    LODWORD(v13) = 22;
    *((_QWORD *)&v13 + 1) = &off_18018C1A0;
    *(_OWORD *)a2 = v13;
  }
  if ( v5 )
    goto LABEL_8;
LABEL_9:
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v7 = sub_1800FEA68(Buffer);
  sub_180009534(&v14, Buffer, v7);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  if ( (__int128 *)a1 != &v14 )
  {
    v9 = &v14;
    if ( v16 > 7 )
      v9 = (__int128 *)v14;
    v10 = v15;
    if ( v15 > 7 )
    {
      _mm_lfence();
      LOBYTE(v8) = 0;
      sub_18000A69C(a1, v15, v8, v9);
    }
    else
    {
      *(_QWORD *)(a1 + 16) = v15;
      v11 = 2 * v10;
      sub_18013B890(a1, v9, 2 * v10);
      *(_WORD *)(v11 + a1) = 0;
    }
  }
  sub_1800106B8(&v14);
  return a1;
}

```

## disassembly

```asm
0x1800adda4  mov     [rsp-8+arg_10], rbx
0x1800adda9  mov     [rsp-8+arg_18], rsi
0x1800addae  push    rbp
0x1800addaf  push    rdi
0x1800addb0  push    r14
0x1800addb2  lea     rbp, [rsp-180h]
0x1800addba  sub     rsp, 280h
0x1800addc1  mov     rax, cs:__security_cookie
0x1800addc8  xor     rax, rsp
0x1800addcb  mov     [rbp+190h+var_20], rax
0x1800addd2  mov     rsi, rdx
0x1800addd5  mov     rdi, rcx
0x1800addd8  mov     [rsp+290h+var_238], rcx
0x1800adddd  xor     r14d, r14d
0x1800adde0  mov     [rdx], r14d
0x1800adde3  lea     rax, off_180218888
0x1800addea  mov     [rdx+8], rax
0x1800addee  xor     edx, edx
0x1800addf0  mov     r8d, 208h
0x1800addf6  lea     rcx, [rsp+290h+Buffer]
0x1800addfb  call    sub_18013BF50
0x1800ade00  xor     edx, edx; hFile
0x1800ade02  mov     r8d, 800h; dwFlags
0x1800ade08  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ade0f  call    cs:LoadLibraryExW
0x1800ade15  mov     rbx, rax
0x1800ade18  test    rax, rax
0x1800ade1b  jz      short loc_1800ADE65
0x1800ade1d  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800ade24  mov     rcx, rax; hModule
0x1800ade27  call    cs:__imp_GetProcAddress
0x1800ade2d  test    rax, rax
0x1800ade30  jz      short loc_1800ADE65
0x1800ade32  lea     rdx, [rsp+290h+Buffer]
0x1800ade37  mov     ecx, 104h
0x1800ade3c  call    cs:__guard_dispatch_icall_fptr
0x1800ade42  test    eax, eax
0x1800ade44  jnz     short loc_1800ADE9B
0x1800ade46  mov     dword ptr [rsp+290h+var_270], 16h
0x1800ade4e  lea     rax, off_18018C1A0
0x1800ade55  mov     qword ptr [rsp+290h+var_270+8], rax
0x1800ade5a  movups  xmm0, [rsp+290h+var_270]
0x1800ade5f  movdqu  xmmword ptr [rsi], xmm0
0x1800ade63  jmp     short loc_1800ADE9B
0x1800ade65  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x1800ade6a  mov     ecx, 104h; nBufferLength
0x1800ade6f  call    cs:GetTempPathW
0x1800ade75  test    eax, eax
0x1800ade77  jnz     short loc_1800ADE96
0x1800ade79  mov     dword ptr [rsp+290h+var_270], 16h
0x1800ade81  lea     rax, off_18018C1A0
0x1800ade88  mov     qword ptr [rsp+290h+var_270+8], rax
0x1800ade8d  movups  xmm0, [rsp+290h+var_270]
0x1800ade92  movdqu  xmmword ptr [rsi], xmm0
0x1800ade96  test    rbx, rbx
0x1800ade99  jz      short loc_1800ADEA4
0x1800ade9b  mov     rcx, rbx; hLibModule
0x1800ade9e  call    cs:__imp_FreeLibrary
0x1800adea4  xorps   xmm0, xmm0
0x1800adea7  movups  [rsp+290h+var_260], xmm0
0x1800adeac  mov     [rsp+290h+var_250], r14
0x1800adeb1  mov     [rsp+290h+var_248], r14
0x1800adeb6  lea     rcx, [rsp+290h+Buffer]
0x1800adebb  call    sub_1800FEA68
0x1800adec0  mov     r8, rax
0x1800adec3  lea     rdx, [rsp+290h+Buffer]
0x1800adec8  lea     rcx, [rsp+290h+var_260]
0x1800adecd  call    sub_180009534
0x1800aded2  nop
0x1800aded3  xorps   xmm0, xmm0
0x1800aded6  movups  xmmword ptr [rdi], xmm0
0x1800aded9  mov     [rdi+10h], r14
0x1800adedd  mov     qword ptr [rdi+18h], 7
0x1800adee5  mov     [rdi], r14w
0x1800adee9  lea     rax, [rsp+290h+var_260]
0x1800adeee  cmp     rdi, rax
0x1800adef1  jz      short loc_1800ADF38
0x1800adef3  lea     r9, [rsp+290h+var_260]
0x1800adef8  cmp     [rsp+290h+var_248], 7
0x1800adefe  cmova   r9, qword ptr [rsp+290h+var_260]
0x1800adf04  mov     rdx, [rsp+290h+var_250]
0x1800adf09  mov     rcx, rdi
0x1800adf0c  cmp     rdx, 7
0x1800adf10  ja      short loc_1800ADF2C
0x1800adf12  mov     [rdi+10h], rdx
0x1800adf16  lea     rbx, [rdx+rdx]
0x1800adf1a  mov     r8, rbx
0x1800adf1d  mov     rdx, r9
0x1800adf20  call    sub_18013B890
0x1800adf25  mov     [rbx+rdi], r14w
0x1800adf2a  jmp     short loc_1800ADF38
0x1800adf2c  lfence
0x1800adf2f  mov     r8b, r14b
0x1800adf32  call    sub_18000A69C
0x1800adf37  nop
0x1800adf38  lea     rcx, [rsp+290h+var_260]
0x1800adf3d  call    sub_1800106B8
0x1800adf42  mov     rax, rdi
0x1800adf45  mov     rcx, [rbp+190h+var_20]
0x1800adf4c  xor     rcx, rsp; StackCookie
0x1800adf4f  call    __security_check_cookie
0x1800adf54  lea     r11, [rsp+290h+var_10]
0x1800adf5c  mov     rbx, [r11+30h]
0x1800adf60  mov     rsi, [r11+38h]
0x1800adf64  mov     rsp, r11
0x1800adf67  pop     r14
0x1800adf69  pop     rdi
0x1800adf6a  pop     rbp
0x1800adf6b  retn
```
