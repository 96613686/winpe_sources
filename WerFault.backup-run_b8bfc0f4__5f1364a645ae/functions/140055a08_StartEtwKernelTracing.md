# StartEtwKernelTracing

- ea: `0x140055a08`
- end: `0x140055b76`
- name: `StartEtwKernelTracing`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400558fc`

## callees

- `0x140002470`
- `0x140003078`
- `0x1400030a8`
- `0x1400556d8`
- `0x140055a08`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140055a6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140055a6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140055a51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140055a51`

## string_xrefs

- `0x140055a44`: `api-ms-win-eventing-controller-l1-1-0.dll`

## pseudocode

```c
__int64 __fastcall StartEtwKernelTracing(int a1, unsigned int a2, __int128 *a3)
{
  char v5; // ebx^2
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v12[18]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+A4h] [rbp-5Ch]
  wchar_t Destination[32]; // [rsp+A8h] [rbp-58h] BYREF
  int v16; // [rsp+E8h] [rbp-18h]
  _BYTE v17[36]; // [rsp+ECh] [rbp-14h] BYREF

  v11 = 0;
  v5 = BYTE2(a1);
  Library = LoadLibraryExW(L"api-ms-win-eventing-controller-l1-1-0.dll", 0, 0x800u);
  if ( !Library )
    return 50;
  ProcAddress = GetProcAddress(Library, "StartTraceW");
  if ( !ProcAddress )
    return 50;
  memset_0(v12, 0, 0xE0u);
  v12[0] = 224;
  v12[11] = 0x20000;
  v14 = 120;
  wcscpy_s(Destination, 0x20u, L"Microsoft-OCA-IPT");
  v8 = a3[1];
  v13 = 0x80000000;
  memset(v17, 0, 32);
  v12[13] = 1;
  v9 = *a3;
  v12[16] = -2113928192;
  BYTE2(v13) = -1;
  v12[12] = (((unsigned int)(1 << ((v5 & 0xF) + 12)) >> 7) + 1023) >> 10;
  LOWORD(v13) = 184;
  v16 = 65546;
  *(_DWORD *)v17 = 65545;
  *(_OWORD *)&v17[4] = v9;
  *(_OWORD *)&v17[20] = v8;
  if ( a2 > 1 )
    SetupAutoLogger((unsigned __int16 *)v12);
  return ((__int64 (__fastcall *)(__int64 *, wchar_t *, _DWORD *))ProcAddress)(&v11, Destination, v12);
}

```

## disassembly

```asm
0x140055a08  mov     [rsp-8+arg_8], rbx
0x140055a0d  mov     [rsp-8+arg_18], rsi
0x140055a12  push    rbp
0x140055a13  push    rdi
0x140055a14  push    r14
0x140055a16  lea     rbp, [rsp-20h]
0x140055a1b  sub     rsp, 120h
0x140055a22  mov     rax, cs:__security_cookie
0x140055a29  xor     rax, rsp
0x140055a2c  mov     [rbp+30h+var_20], rax
0x140055a30  mov     rsi, r8
0x140055a33  mov     [rsp+130h+var_110], 0
0x140055a3c  mov     r14d, edx
0x140055a3f  mov     rbx, rcx
0x140055a42  xor     edx, edx; hFile
0x140055a44  lea     rcx, aApiMsWinEventi_2; "api-ms-win-eventing-controller-l1-1-0.d"...
0x140055a4b  mov     r8d, 800h; dwFlags
0x140055a51  call    cs:__imp_LoadLibraryExW
0x140055a57  test    rax, rax
0x140055a5a  jz      loc_140055B4D
0x140055a60  lea     rdx, aStarttracew; "StartTraceW"
0x140055a67  mov     rcx, rax; hModule
0x140055a6a  call    cs:__imp_GetProcAddress
0x140055a70  mov     rdi, rax
0x140055a73  test    rax, rax
0x140055a76  jz      loc_140055B4D
0x140055a7c  xor     edx, edx; Val
0x140055a7e  lea     rcx, [rsp+130h+var_100]; void *
0x140055a83  mov     r8d, 0E0h; Size
0x140055a89  call    memset_0
0x140055a8e  lea     r8, aMicrosoftOcaIp; "Microsoft-OCA-IPT"
0x140055a95  mov     [rsp+130h+var_100], 0E0h
0x140055a9d  mov     edx, 20h ; ' '; SizeInWords
0x140055aa2  mov     [rsp+130h+var_D4], 20000h
0x140055aaa  lea     rcx, [rbp+30h+Destination]; Destination
0x140055aae  mov     [rbp+30h+var_8C], 78h ; 'x'
0x140055ab5  call    wcscpy_s
0x140055aba  movups  xmm1, xmmword ptr [rsi+10h]
0x140055abe  shr     ebx, 10h
0x140055ac1  mov     edx, 1
0x140055ac6  xorps   xmm0, xmm0
0x140055ac9  mov     [rsp+130h+var_B8], 80000000h
0x140055ad1  movups  [rbp+30h+var_44], xmm0
0x140055ad5  and     ebx, 0Fh
0x140055ad8  mov     eax, edx
0x140055ada  movups  [rbp+30h+var_34], xmm0
0x140055ade  mov     [rsp+130h+var_CC], edx
0x140055ae2  movups  xmm0, xmmword ptr [rsi]
0x140055ae5  lea     ecx, [rbx+0Ch]
0x140055ae8  mov     [rsp+130h+var_C0], 82000400h
0x140055af0  shl     eax, cl
0x140055af2  shr     eax, 7
0x140055af5  add     eax, 3FFh
0x140055afa  mov     byte ptr [rsp+130h+var_B8+2], 0FFh
0x140055aff  shr     eax, 0Ah
0x140055b02  mov     [rsp+130h+var_D0], eax
0x140055b06  mov     eax, 0B8h
0x140055b0b  mov     word ptr [rsp+130h+var_B8], ax
0x140055b10  mov     [rbp+30h+var_48], 1000Ah
0x140055b17  mov     dword ptr [rbp+30h+var_44], 10009h
0x140055b1e  movaps  [rbp+30h+var_44+4], xmm0
0x140055b22  movaps  [rbp+30h+var_34+4], xmm1
0x140055b26  cmp     r14d, edx
0x140055b29  jbe     short loc_140055B35
0x140055b2b  lea     rcx, [rsp+130h+var_100]
0x140055b30  call    SetupAutoLogger
0x140055b35  lea     r8, [rsp+130h+var_100]
0x140055b3a  mov     rax, rdi
0x140055b3d  lea     rdx, [rbp+30h+Destination]
0x140055b41  lea     rcx, [rsp+130h+var_110]
0x140055b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b4b  jmp     short loc_140055B52
0x140055b4d  mov     eax, 32h ; '2'
0x140055b52  mov     rcx, [rbp+30h+var_20]
0x140055b56  xor     rcx, rsp; StackCookie
0x140055b59  call    __security_check_cookie
0x140055b5e  lea     r11, [rsp+130h+var_10]
0x140055b66  mov     rbx, [r11+28h]
0x140055b6a  mov     rsi, [r11+38h]
0x140055b6e  mov     rsp, r11
0x140055b71  pop     r14
0x140055b73  pop     rdi
0x140055b74  pop     rbp
0x140055b75  retn
```
