# sub_1800EAFE8

- ea: `0x1800eafe8`
- end: `0x1800eb1b0`
- name: `sub_1800EAFE8`
- size: `456`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18007b218`
- `0x18011edf0`
- `0x18011f238`

## callees

- `0x18000cad4`
- `0x18000d618`
- `0x180015994`
- `0x1800eafe8`
- `0x180141350`
- `0x18014ca78`
- `0x18018f7a0`
- `0x18018f800`
- `0x18018fec0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800eb053`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800eb053`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800eb0e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800eb0e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eb06b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800eb06b`
- `KERNEL32!GetTempPathW` at `0x1800eb0b3`
- `KERNEL32!GetTempPathW` at `0x1800eb0b3`

## string_xrefs

- `0x1800eb04c`: `kernelbase.dll`
- `0x1800eb061`: `GetTempPath2W`

## pseudocode

```c
__int64 __fastcall sub_1800EAFE8(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax
  unsigned __int64 v7; // rax
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
  *(_QWORD *)(a2 + 8) = &off_18027FB98;
  sub_18018FEC0(Buffer, 0, 520);
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
        *((_QWORD *)&v13 + 1) = &off_1801F3140;
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
    *((_QWORD *)&v13 + 1) = &off_1801F3140;
    *(_OWORD *)a2 = v13;
  }
  if ( v5 )
    goto LABEL_8;
LABEL_9:
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v7 = sub_18014CA78(Buffer);
  sub_18000CAD4((unsigned __int64 *)&v14, (__int64)Buffer, v7);
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
      sub_18000D618(a1, v15, v8, v9);
    }
    else
    {
      *(_QWORD *)(a1 + 16) = v15;
      v11 = 2 * v10;
      sub_18018F800(a1, v9, 2 * v10);
      *(_WORD *)(v11 + a1) = 0;
    }
  }
  sub_180015994((__int64 *)&v14);
  return a1;
}

```

## disassembly

```asm
0x1800eafe8  mov     [rsp-8+arg_10], rbx
0x1800eafed  mov     [rsp-8+arg_18], rsi
0x1800eaff2  push    rbp
0x1800eaff3  push    rdi
0x1800eaff4  push    r14
0x1800eaff6  lea     rbp, [rsp-180h]
0x1800eaffe  sub     rsp, 280h
0x1800eb005  mov     rax, cs:__security_cookie
0x1800eb00c  xor     rax, rsp
0x1800eb00f  mov     [rbp+190h+var_20], rax
0x1800eb016  mov     rsi, rdx
0x1800eb019  mov     rdi, rcx
0x1800eb01c  mov     [rsp+290h+var_238], rcx
0x1800eb021  xor     r14d, r14d
0x1800eb024  mov     [rdx], r14d
0x1800eb027  lea     rax, off_18027FB98
0x1800eb02e  mov     [rdx+8], rax
0x1800eb032  xor     edx, edx
0x1800eb034  mov     r8d, 208h
0x1800eb03a  lea     rcx, [rsp+290h+Buffer]
0x1800eb03f  call    sub_18018FEC0
0x1800eb044  xor     edx, edx; hFile
0x1800eb046  mov     r8d, 800h; dwFlags
0x1800eb04c  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800eb053  call    cs:LoadLibraryExW
0x1800eb059  mov     rbx, rax
0x1800eb05c  test    rax, rax
0x1800eb05f  jz      short loc_1800EB0A9
0x1800eb061  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800eb068  mov     rcx, rax; hModule
0x1800eb06b  call    cs:__imp_GetProcAddress
0x1800eb071  test    rax, rax
0x1800eb074  jz      short loc_1800EB0A9
0x1800eb076  lea     rdx, [rsp+290h+Buffer]
0x1800eb07b  mov     ecx, 104h
0x1800eb080  call    cs:__guard_dispatch_icall_fptr
0x1800eb086  test    eax, eax
0x1800eb088  jnz     short loc_1800EB0DF
0x1800eb08a  mov     dword ptr [rsp+290h+var_270], 16h
0x1800eb092  lea     rax, off_1801F3140
0x1800eb099  mov     qword ptr [rsp+290h+var_270+8], rax
0x1800eb09e  movups  xmm0, [rsp+290h+var_270]
0x1800eb0a3  movdqu  xmmword ptr [rsi], xmm0
0x1800eb0a7  jmp     short loc_1800EB0DF
0x1800eb0a9  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x1800eb0ae  mov     ecx, 104h; nBufferLength
0x1800eb0b3  call    cs:GetTempPathW
0x1800eb0b9  test    eax, eax
0x1800eb0bb  jnz     short loc_1800EB0DA
0x1800eb0bd  mov     dword ptr [rsp+290h+var_270], 16h
0x1800eb0c5  lea     rax, off_1801F3140
0x1800eb0cc  mov     qword ptr [rsp+290h+var_270+8], rax
0x1800eb0d1  movups  xmm0, [rsp+290h+var_270]
0x1800eb0d6  movdqu  xmmword ptr [rsi], xmm0
0x1800eb0da  test    rbx, rbx
0x1800eb0dd  jz      short loc_1800EB0E8
0x1800eb0df  mov     rcx, rbx; hLibModule
0x1800eb0e2  call    cs:__imp_FreeLibrary
0x1800eb0e8  xorps   xmm0, xmm0
0x1800eb0eb  movups  [rsp+290h+var_260], xmm0
0x1800eb0f0  mov     [rsp+290h+var_250], r14
0x1800eb0f5  mov     [rsp+290h+var_248], r14
0x1800eb0fa  lea     rcx, [rsp+290h+Buffer]
0x1800eb0ff  call    sub_18014CA78
0x1800eb104  mov     r8, rax
0x1800eb107  lea     rdx, [rsp+290h+Buffer]
0x1800eb10c  lea     rcx, [rsp+290h+var_260]
0x1800eb111  call    sub_18000CAD4
0x1800eb116  nop
0x1800eb117  xorps   xmm0, xmm0
0x1800eb11a  movups  xmmword ptr [rdi], xmm0
0x1800eb11d  mov     [rdi+10h], r14
0x1800eb121  mov     qword ptr [rdi+18h], 7
0x1800eb129  mov     [rdi], r14w
0x1800eb12d  lea     rax, [rsp+290h+var_260]
0x1800eb132  cmp     rdi, rax
0x1800eb135  jz      short loc_1800EB17C
0x1800eb137  lea     r9, [rsp+290h+var_260]
0x1800eb13c  cmp     [rsp+290h+var_248], 7
0x1800eb142  cmova   r9, qword ptr [rsp+290h+var_260]
0x1800eb148  mov     rdx, [rsp+290h+var_250]
0x1800eb14d  mov     rcx, rdi
0x1800eb150  cmp     rdx, 7
0x1800eb154  ja      short loc_1800EB170
0x1800eb156  mov     [rdi+10h], rdx
0x1800eb15a  lea     rbx, [rdx+rdx]
0x1800eb15e  mov     r8, rbx
0x1800eb161  mov     rdx, r9
0x1800eb164  call    sub_18018F800
0x1800eb169  mov     [rbx+rdi], r14w
0x1800eb16e  jmp     short loc_1800EB17C
0x1800eb170  lfence
0x1800eb173  mov     r8b, r14b
0x1800eb176  call    sub_18000D618
0x1800eb17b  nop
0x1800eb17c  lea     rcx, [rsp+290h+var_260]
0x1800eb181  call    sub_180015994
0x1800eb186  mov     rax, rdi
0x1800eb189  mov     rcx, [rbp+190h+var_20]
0x1800eb190  xor     rcx, rsp; StackCookie
0x1800eb193  call    __security_check_cookie
0x1800eb198  lea     r11, [rsp+290h+var_10]
0x1800eb1a0  mov     rbx, [r11+30h]
0x1800eb1a4  mov     rsi, [r11+38h]
0x1800eb1a8  mov     rsp, r11
0x1800eb1ab  pop     r14
0x1800eb1ad  pop     rdi
0x1800eb1ae  pop     rbp
0x1800eb1af  retn
```
