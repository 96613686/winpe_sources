# StartEtwKernelTracing

- ea: `0x1400594e4`
- end: `0x14005965f`
- name: `StartEtwKernelTracing`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400593c8`

## callees

- `0x140002490`
- `0x1400030c8`
- `0x1400030f8`
- `0x140059168`
- `0x1400594e4`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005954c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005954c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005952d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005952d`

## string_xrefs

- `0x140059520`: `api-ms-win-eventing-controller-l1-1-0.dll`

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
0x1400594e4  mov     [rsp-8+arg_8], rbx
0x1400594e9  mov     [rsp-8+arg_18], rsi
0x1400594ee  push    rbp
0x1400594ef  push    rdi
0x1400594f0  push    r14
0x1400594f2  lea     rbp, [rsp-20h]
0x1400594f7  sub     rsp, 120h
0x1400594fe  mov     rax, cs:__security_cookie
0x140059505  xor     rax, rsp
0x140059508  mov     [rbp+30h+var_20], rax
0x14005950c  mov     rsi, r8
0x14005950f  mov     [rsp+130h+var_110], 0
0x140059518  mov     r14d, edx
0x14005951b  mov     rbx, rcx
0x14005951e  xor     edx, edx; hFile
0x140059520  lea     rcx, aApiMsWinEventi_2; "api-ms-win-eventing-controller-l1-1-0.d"...
0x140059527  mov     r8d, 800h; dwFlags
0x14005952d  call    cs:__imp_LoadLibraryExW
0x140059534  nop     dword ptr [rax+rax+00h]
0x140059539  test    rax, rax
0x14005953c  jz      loc_140059635
0x140059542  lea     rdx, aStarttracew; "StartTraceW"
0x140059549  mov     rcx, rax; hModule
0x14005954c  call    cs:__imp_GetProcAddress
0x140059553  nop     dword ptr [rax+rax+00h]
0x140059558  mov     rdi, rax
0x14005955b  test    rax, rax
0x14005955e  jz      loc_140059635
0x140059564  xor     edx, edx; Val
0x140059566  lea     rcx, [rsp+130h+var_100]; void *
0x14005956b  mov     r8d, 0E0h; Size
0x140059571  call    memset_0
0x140059576  lea     r8, aMicrosoftOcaIp; "Microsoft-OCA-IPT"
0x14005957d  mov     [rsp+130h+var_100], 0E0h
0x140059585  mov     edx, 20h ; ' '; SizeInWords
0x14005958a  mov     [rsp+130h+var_D4], 20000h
0x140059592  lea     rcx, [rbp+30h+Destination]; Destination
0x140059596  mov     [rbp+30h+var_8C], 78h ; 'x'
0x14005959d  call    wcscpy_s
0x1400595a2  movups  xmm1, xmmword ptr [rsi+10h]
0x1400595a6  shr     ebx, 10h
0x1400595a9  mov     edx, 1
0x1400595ae  xorps   xmm0, xmm0
0x1400595b1  mov     [rsp+130h+var_B8], 80000000h
0x1400595b9  movups  [rbp+30h+var_44], xmm0
0x1400595bd  and     ebx, 0Fh
0x1400595c0  mov     eax, edx
0x1400595c2  movups  [rbp+30h+var_34], xmm0
0x1400595c6  mov     [rsp+130h+var_CC], edx
0x1400595ca  movups  xmm0, xmmword ptr [rsi]
0x1400595cd  lea     ecx, [rbx+0Ch]
0x1400595d0  mov     [rsp+130h+var_C0], 82000400h
0x1400595d8  shl     eax, cl
0x1400595da  shr     eax, 7
0x1400595dd  add     eax, 3FFh
0x1400595e2  mov     byte ptr [rsp+130h+var_B8+2], 0FFh
0x1400595e7  shr     eax, 0Ah
0x1400595ea  mov     [rsp+130h+var_D0], eax
0x1400595ee  mov     eax, 0B8h
0x1400595f3  mov     word ptr [rsp+130h+var_B8], ax
0x1400595f8  mov     [rbp+30h+var_48], 1000Ah
0x1400595ff  mov     dword ptr [rbp+30h+var_44], 10009h
0x140059606  movaps  [rbp+30h+var_44+4], xmm0
0x14005960a  movaps  [rbp+30h+var_34+4], xmm1
0x14005960e  cmp     r14d, edx
0x140059611  jbe     short loc_14005961D
0x140059613  lea     rcx, [rsp+130h+var_100]
0x140059618  call    SetupAutoLogger
0x14005961d  lea     r8, [rsp+130h+var_100]
0x140059622  mov     rax, rdi
0x140059625  lea     rdx, [rbp+30h+Destination]
0x140059629  lea     rcx, [rsp+130h+var_110]
0x14005962e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059633  jmp     short loc_14005963A
0x140059635  mov     eax, 32h ; '2'
0x14005963a  mov     rcx, [rbp+30h+var_20]
0x14005963e  xor     rcx, rsp; StackCookie
0x140059641  call    __security_check_cookie
0x140059646  lea     r11, [rsp+130h+var_10]
0x14005964e  mov     rbx, [r11+28h]
0x140059652  mov     rsi, [r11+38h]
0x140059656  mov     rsp, r11
0x140059659  pop     r14
0x14005965b  pop     rdi
0x14005965c  pop     rbp
0x14005965d  retn
```
