# FICreateFontFile

- ea: `0x180160038`
- end: `0x1801602ca`
- name: `FICreateFontFile`
- size: `658`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1801201d4`
- `0x180120f44`
- `0x1801210d0`

## callees

- `0x1800032e0`
- `0x18000be0c`
- `0x18015fb54`
- `0x180160038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801600e3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801600e3`
- `KERNEL32!CreateDirectoryW` at `0x180160110`
- `KERNEL32!CreateDirectoryW` at `0x180160110`
- `KERNEL32!HeapAlloc` at `0x180160087`
- `KERNEL32!HeapAlloc` at `0x1801601e9`
- `KERNEL32!HeapAlloc` at `0x180160219`
- `KERNEL32!HeapAlloc` at `0x180160249`
- `KERNEL32!HeapAlloc` at `0x180160087`
- `KERNEL32!HeapAlloc` at `0x1801601e9`
- `KERNEL32!HeapAlloc` at `0x180160219`
- `KERNEL32!HeapAlloc` at `0x180160249`
- `KERNEL32!CreateFileW` at `0x1801601a0`
- `KERNEL32!CreateFileW` at `0x1801601a0`
- `RPCRT4!UuidCreate` at `0x180160123`
- `RPCRT4!UuidCreate` at `0x180160123`
- `RPCRT4!RpcStringFreeW` at `0x180160170`
- `RPCRT4!RpcStringFreeW` at `0x180160170`
- `RPCRT4!UuidToStringW` at `0x18016013b`
- `RPCRT4!UuidToStringW` at `0x18016013b`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1801600cd`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1801600cd`

## pseudocode

```c
wchar_t *__fastcall FICreateFontFile(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v4; // rbp
  wchar_t *result; // rax
  wchar_t *v7; // rbx
  wchar_t *v8; // rdi
  wchar_t *v9; // rax
  HANDLE FileW; // rax
  LPVOID v11; // rax
  LPVOID v12; // rax
  LPVOID v13; // rax
  DWORD pcbNeeded; // [rsp+40h] [rbp-58h] BYREF
  RPC_WSTR StringUuid; // [rsp+48h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-48h] BYREF

  v4 = a3;
  StringUuid = 0;
  pcbNeeded = 0;
  Uuid = 0;
  result = (wchar_t *)HeapAlloc(a2, 8u, 0x258u);
  v7 = result;
  if ( result )
  {
    *((_QWORD *)result + 1) = a1;
    v8 = result + 12;
    *(_DWORD *)result = 1718514793;
    *((_QWORD *)result + 2) = a2;
    pcbNeeded = 520;
    if ( !GetPrinterDriverDirectoryW(0, 0, 1u, (LPBYTE)result + 24, 0x208u, &pcbNeeded) )
      goto LABEL_16;
    v9 = wcsrchr(v8, 0x5Cu);
    if ( v9 )
      *v9 = 0;
    StringCchCatW(v8, 0x104u, L"\\unifont\\");
    if ( !CreateDirectoryW(v8, 0) )
      goto LABEL_16;
    if ( UuidCreate(&Uuid) )
      goto LABEL_16;
    if ( UuidToStringW(&Uuid, &StringUuid) )
      goto LABEL_16;
    StringCchCatW(v8, 0x104u, StringUuid);
    StringCchCatW(v8, 0x104u, L".UFF");
    RpcStringFreeW(&StringUuid);
    FileW = CreateFileW(v8, 0x40000000u, 0, 0, 2u, 0x10100000u, 0);
    *((_QWORD *)v7 + 68) = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_16;
    *((_DWORD *)v7 + 143) = 2;
    *((_DWORD *)v7 + 142) = 0;
    if ( (unsigned __int64)(8 * v4) > 0xFFFFFFFF )
      goto LABEL_16;
    v11 = HeapAlloc(a2, 8u, (unsigned int)(8 * v4));
    *((_QWORD *)v7 + 73) = v11;
    if ( v11
      && (*((_DWORD *)v7 + 148) = 0, v12 = HeapAlloc(a2, 8u, 0x30u), (*((_QWORD *)v7 + 69) = v12) != 0)
      && (unsigned __int64)(36 * v4) <= 0xFFFFFFFF
      && (v13 = HeapAlloc(a2, 8u, (unsigned int)(36 * v4)), (*((_QWORD *)v7 + 70) = v13) != 0) )
    {
      **((_DWORD **)v7 + 69) = 826689109;
      *(_DWORD *)(*((_QWORD *)v7 + 69) + 4LL) = 65537;
      *(_DWORD *)(*((_QWORD *)v7 + 69) + 8LL) = 48;
      *(_DWORD *)(*((_QWORD *)v7 + 69) + 12LL) = v4;
      if ( (_DWORD)v4 )
        *(_DWORD *)(*((_QWORD *)v7 + 69) + 24LL) = 48;
    }
    else
    {
LABEL_16:
      FICloseFontFile(v7);
      return 0;
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180160038  mov     [rsp+arg_0], rbx
0x18016003d  push    rbp
0x18016003e  push    rsi
0x18016003f  push    rdi
0x180160040  push    r12
0x180160042  push    r15
0x180160044  sub     rsp, 70h
0x180160048  mov     rax, cs:__security_cookie
0x18016004f  xor     rax, rsp
0x180160052  mov     [rsp+98h+var_38], rax
0x180160057  mov     rsi, rdx
0x18016005a  mov     ebp, r8d
0x18016005d  mov     rdi, rcx
0x180160060  mov     [rsp+98h+StringUuid], 0
0x180160069  xorps   xmm0, xmm0
0x18016006c  mov     [rsp+98h+var_58], 0
0x180160074  mov     rcx, rsi; hHeap
0x180160077  mov     edx, 8; dwFlags
0x18016007c  mov     r8d, 258h; dwBytes
0x180160082  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x180160087  call    cs:__imp_HeapAlloc
0x18016008d  mov     rbx, rax
0x180160090  test    rax, rax
0x180160093  jz      loc_1801602A9
0x180160099  mov     [rax+8], rdi
0x18016009d  mov     ecx, 208h
0x1801600a2  lea     rdi, [rax+18h]
0x1801600a6  mov     dword ptr [rax], 666E7469h
0x1801600ac  mov     [rax+10h], rsi
0x1801600b0  xor     edx, edx; pEnvironment
0x1801600b2  lea     rax, [rsp+98h+var_58]
0x1801600b7  mov     [rsp+98h+var_58], ecx
0x1801600bb  mov     [rsp+98h+pcbNeeded], rax; pcbNeeded
0x1801600c0  mov     r9, rdi; pDriverDirectory
0x1801600c3  mov     [rsp+98h+cbBuf], ecx; cbBuf
0x1801600c7  xor     ecx, ecx; pName
0x1801600c9  lea     r8d, [rdx+1]; Level
0x1801600cd  call    cs:__imp_GetPrinterDriverDirectoryW
0x1801600d3  test    eax, eax
0x1801600d5  jz      loc_18016029C
0x1801600db  mov     edx, 5Ch ; '\'; Ch
0x1801600e0  mov     rcx, rdi; Str
0x1801600e3  call    cs:__imp_wcsrchr
0x1801600e9  test    rax, rax
0x1801600ec  jz      short loc_1801600F3
0x1801600ee  xor     ecx, ecx
0x1801600f0  mov     [rax], cx
0x1801600f3  mov     r15d, 104h
0x1801600f9  lea     r8, aUnifont; "\\unifont\\"
0x180160100  mov     edx, r15d; unsigned __int64
0x180160103  mov     rcx, rdi; unsigned __int16 *
0x180160106  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18016010b  xor     edx, edx; lpSecurityAttributes
0x18016010d  mov     rcx, rdi; lpPathName
0x180160110  call    cs:__imp_CreateDirectoryW
0x180160116  test    eax, eax
0x180160118  jz      loc_18016029C
0x18016011e  lea     rcx, [rsp+98h+Uuid]; Uuid
0x180160123  call    cs:__imp_UuidCreate
0x180160129  test    eax, eax
0x18016012b  jnz     loc_18016029C
0x180160131  lea     rdx, [rsp+98h+StringUuid]; StringUuid
0x180160136  lea     rcx, [rsp+98h+Uuid]; Uuid
0x18016013b  call    cs:__imp_UuidToStringW
0x180160141  test    eax, eax
0x180160143  jnz     loc_18016029C
0x180160149  mov     r8, [rsp+98h+StringUuid]; unsigned __int16 *
0x18016014e  mov     edx, r15d; unsigned __int64
0x180160151  mov     rcx, rdi; unsigned __int16 *
0x180160154  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180160159  lea     r8, aUff; ".UFF"
0x180160160  mov     edx, r15d; unsigned __int64
0x180160163  mov     rcx, rdi; unsigned __int16 *
0x180160166  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18016016b  lea     rcx, [rsp+98h+StringUuid]; String
0x180160170  call    cs:__imp_RpcStringFreeW
0x180160176  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18016017f  mov     r15d, 2
0x180160185  mov     dword ptr [rsp+98h+pcbNeeded], 10100000h; dwFlagsAndAttributes
0x18016018d  xor     r9d, r9d; lpSecurityAttributes
0x180160190  xor     r8d, r8d; dwShareMode
0x180160193  mov     [rsp+98h+cbBuf], r15d; dwCreationDisposition
0x180160198  mov     edx, 40000000h; dwDesiredAccess
0x18016019d  mov     rcx, rdi; lpFileName
0x1801601a0  call    cs:__imp_CreateFileW
0x1801601a6  mov     [rbx+220h], rax
0x1801601ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801601b1  jz      loc_18016029C
0x1801601b7  lea     rax, ds:0[rbp*8]
0x1801601bf  mov     [rbx+23Ch], r15d
0x1801601c6  mov     r12d, 0FFFFFFFFh
0x1801601cc  mov     dword ptr [rbx+238h], 0
0x1801601d6  cmp     rax, r12
0x1801601d9  ja      loc_18016029C
0x1801601df  mov     r8d, eax; dwBytes
0x1801601e2  lea     edx, [r15+6]; dwFlags
0x1801601e6  mov     rcx, rsi; hHeap
0x1801601e9  call    cs:__imp_HeapAlloc
0x1801601ef  mov     [rbx+248h], rax
0x1801601f6  test    rax, rax
0x1801601f9  jz      loc_18016029C
0x1801601ff  mov     r15d, 30h ; '0'
0x180160205  mov     dword ptr [rbx+250h], 0
0x18016020f  mov     r8d, r15d; dwBytes
0x180160212  mov     rcx, rsi; hHeap
0x180160215  lea     edx, [r15-28h]; dwFlags
0x180160219  call    cs:__imp_HeapAlloc
0x18016021f  mov     [rbx+228h], rax
0x180160226  test    rax, rax
0x180160229  jz      short loc_18016029C
0x18016022b  lea     rax, ds:0[rbp*8]
0x180160233  add     rax, rbp
0x180160236  shl     rax, 2
0x18016023a  cmp     rax, r12
0x18016023d  ja      short loc_18016029C
0x18016023f  mov     r8d, eax; dwBytes
0x180160242  lea     edx, [r15-28h]; dwFlags
0x180160246  mov     rcx, rsi; hHeap
0x180160249  call    cs:__imp_HeapAlloc
0x18016024f  mov     [rbx+230h], rax
0x180160256  test    rax, rax
0x180160259  jz      short loc_18016029C
0x18016025b  mov     rax, [rbx+228h]
0x180160262  mov     dword ptr [rax], 31464655h
0x180160268  mov     rax, [rbx+228h]
0x18016026f  mov     dword ptr [rax+4], 10001h
0x180160276  mov     rax, [rbx+228h]
0x18016027d  mov     [rax+8], r15d
0x180160281  mov     rax, [rbx+228h]
0x180160288  mov     [rax+0Ch], ebp
0x18016028b  test    ebp, ebp
0x18016028d  jz      short loc_1801602A6
0x18016028f  mov     rax, [rbx+228h]
0x180160296  mov     [rax+18h], r15d
0x18016029a  jmp     short loc_1801602A6
0x18016029c  mov     rcx, rbx; lpMem
0x18016029f  call    FICloseFontFile
0x1801602a4  xor     ebx, ebx
0x1801602a6  mov     rax, rbx
0x1801602a9  mov     rcx, [rsp+98h+var_38]
0x1801602ae  xor     rcx, rsp; StackCookie
0x1801602b1  call    __security_check_cookie
0x1801602b6  mov     rbx, [rsp+98h+arg_0]
0x1801602be  add     rsp, 70h
0x1801602c2  pop     r15
0x1801602c4  pop     r12
0x1801602c6  pop     rdi
0x1801602c7  pop     rsi
0x1801602c8  pop     rbp
0x1801602c9  retn
```
