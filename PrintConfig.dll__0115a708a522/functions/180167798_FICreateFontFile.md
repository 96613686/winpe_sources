# FICreateFontFile

- ea: `0x180167798`
- end: `0x180167a6d`
- name: `FICreateFontFile`
- size: `725`
- prototype: `wchar_t *__fastcall(__int64, void *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180125868`
- `0x1801267b4`
- `0x180126940`

## callees

- `0x180003400`
- `0x18000be68`
- `0x180167274`
- `0x180167798`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016784f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016784f`
- `KERNEL32!CreateDirectoryW` at `0x180167882`
- `KERNEL32!CreateDirectoryW` at `0x180167882`
- `KERNEL32!HeapAlloc` at `0x1801677e7`
- `KERNEL32!HeapAlloc` at `0x180167979`
- `KERNEL32!HeapAlloc` at `0x1801679af`
- `KERNEL32!HeapAlloc` at `0x1801679e5`
- `KERNEL32!HeapAlloc` at `0x1801677e7`
- `KERNEL32!HeapAlloc` at `0x180167979`
- `KERNEL32!HeapAlloc` at `0x1801679af`
- `KERNEL32!HeapAlloc` at `0x1801679e5`
- `KERNEL32!CreateFileW` at `0x18016792a`
- `KERNEL32!CreateFileW` at `0x18016792a`
- `RPCRT4!UuidCreate` at `0x18016789b`
- `RPCRT4!UuidCreate` at `0x18016789b`
- `RPCRT4!RpcStringFreeW` at `0x1801678f4`
- `RPCRT4!RpcStringFreeW` at `0x1801678f4`
- `RPCRT4!UuidToStringW` at `0x1801678b9`
- `RPCRT4!UuidToStringW` at `0x1801678b9`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180167833`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180167833`

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
    StringCchCatW(v8, 260, L"\\unifont\\");
    if ( !CreateDirectoryW(v8, 0) )
      goto LABEL_16;
    if ( UuidCreate(&Uuid) )
      goto LABEL_16;
    if ( UuidToStringW(&Uuid, &StringUuid) )
      goto LABEL_16;
    StringCchCatW(v8, 260, StringUuid);
    StringCchCatW(v8, 260, L".UFF");
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
0x180167798  mov     [rsp+arg_0], rbx
0x18016779d  push    rbp
0x18016779e  push    rsi
0x18016779f  push    rdi
0x1801677a0  push    r12
0x1801677a2  push    r15
0x1801677a4  sub     rsp, 70h
0x1801677a8  mov     rax, cs:__security_cookie
0x1801677af  xor     rax, rsp
0x1801677b2  mov     [rsp+98h+var_38], rax
0x1801677b7  mov     rsi, rdx
0x1801677ba  mov     ebp, r8d
0x1801677bd  mov     rdi, rcx
0x1801677c0  mov     [rsp+98h+StringUuid], 0
0x1801677c9  xorps   xmm0, xmm0
0x1801677cc  mov     [rsp+98h+var_58], 0
0x1801677d4  mov     rcx, rsi; hHeap
0x1801677d7  mov     edx, 8; dwFlags
0x1801677dc  mov     r8d, 258h; dwBytes
0x1801677e2  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x1801677e7  call    cs:__imp_HeapAlloc
0x1801677ee  nop     dword ptr [rax+rax+00h]
0x1801677f3  mov     rbx, rax
0x1801677f6  test    rax, rax
0x1801677f9  jz      loc_180167A4B
0x1801677ff  mov     [rax+8], rdi
0x180167803  mov     ecx, 208h
0x180167808  lea     rdi, [rax+18h]
0x18016780c  mov     dword ptr [rax], 666E7469h
0x180167812  mov     [rax+10h], rsi
0x180167816  xor     edx, edx; pEnvironment
0x180167818  lea     rax, [rsp+98h+var_58]
0x18016781d  mov     [rsp+98h+var_58], ecx
0x180167821  mov     [rsp+98h+pcbNeeded], rax; pcbNeeded
0x180167826  mov     r9, rdi; pDriverDirectory
0x180167829  mov     [rsp+98h+cbBuf], ecx; cbBuf
0x18016782d  xor     ecx, ecx; pName
0x18016782f  lea     r8d, [rdx+1]; Level
0x180167833  call    cs:__imp_GetPrinterDriverDirectoryW
0x18016783a  nop     dword ptr [rax+rax+00h]
0x18016783f  test    eax, eax
0x180167841  jz      loc_180167A3E
0x180167847  mov     edx, 5Ch ; '\'; Ch
0x18016784c  mov     rcx, rdi; Str
0x18016784f  call    cs:__imp_wcsrchr
0x180167856  nop     dword ptr [rax+rax+00h]
0x18016785b  test    rax, rax
0x18016785e  jz      short loc_180167865
0x180167860  xor     ecx, ecx
0x180167862  mov     [rax], cx
0x180167865  mov     r15d, 104h
0x18016786b  lea     r8, aUnifont; "\\unifont\\"
0x180167872  mov     edx, r15d; unsigned __int64
0x180167875  mov     rcx, rdi; unsigned __int16 *
0x180167878  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18016787d  xor     edx, edx; lpSecurityAttributes
0x18016787f  mov     rcx, rdi; lpPathName
0x180167882  call    cs:__imp_CreateDirectoryW
0x180167889  nop     dword ptr [rax+rax+00h]
0x18016788e  test    eax, eax
0x180167890  jz      loc_180167A3E
0x180167896  lea     rcx, [rsp+98h+Uuid]; Uuid
0x18016789b  call    cs:__imp_UuidCreate
0x1801678a2  nop     dword ptr [rax+rax+00h]
0x1801678a7  test    eax, eax
0x1801678a9  jnz     loc_180167A3E
0x1801678af  lea     rdx, [rsp+98h+StringUuid]; StringUuid
0x1801678b4  lea     rcx, [rsp+98h+Uuid]; Uuid
0x1801678b9  call    cs:__imp_UuidToStringW
0x1801678c0  nop     dword ptr [rax+rax+00h]
0x1801678c5  test    eax, eax
0x1801678c7  jnz     loc_180167A3E
0x1801678cd  mov     r8, [rsp+98h+StringUuid]; unsigned __int16 *
0x1801678d2  mov     edx, r15d; unsigned __int64
0x1801678d5  mov     rcx, rdi; unsigned __int16 *
0x1801678d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801678dd  lea     r8, aUff; ".UFF"
0x1801678e4  mov     edx, r15d; unsigned __int64
0x1801678e7  mov     rcx, rdi; unsigned __int16 *
0x1801678ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801678ef  lea     rcx, [rsp+98h+StringUuid]; String
0x1801678f4  call    cs:__imp_RpcStringFreeW
0x1801678fb  nop     dword ptr [rax+rax+00h]
0x180167900  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180167909  mov     r15d, 2
0x18016790f  mov     dword ptr [rsp+98h+pcbNeeded], 10100000h; dwFlagsAndAttributes
0x180167917  xor     r9d, r9d; lpSecurityAttributes
0x18016791a  xor     r8d, r8d; dwShareMode
0x18016791d  mov     [rsp+98h+cbBuf], r15d; dwCreationDisposition
0x180167922  mov     edx, 40000000h; dwDesiredAccess
0x180167927  mov     rcx, rdi; lpFileName
0x18016792a  call    cs:__imp_CreateFileW
0x180167931  nop     dword ptr [rax+rax+00h]
0x180167936  mov     [rbx+220h], rax
0x18016793d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180167941  jz      loc_180167A3E
0x180167947  lea     rax, ds:0[rbp*8]
0x18016794f  mov     [rbx+23Ch], r15d
0x180167956  mov     r12d, 0FFFFFFFFh
0x18016795c  mov     dword ptr [rbx+238h], 0
0x180167966  cmp     rax, r12
0x180167969  ja      loc_180167A3E
0x18016796f  mov     r8d, eax; dwBytes
0x180167972  lea     edx, [r15+6]; dwFlags
0x180167976  mov     rcx, rsi; hHeap
0x180167979  call    cs:__imp_HeapAlloc
0x180167980  nop     dword ptr [rax+rax+00h]
0x180167985  mov     [rbx+248h], rax
0x18016798c  test    rax, rax
0x18016798f  jz      loc_180167A3E
0x180167995  mov     r15d, 30h ; '0'
0x18016799b  mov     dword ptr [rbx+250h], 0
0x1801679a5  mov     r8d, r15d; dwBytes
0x1801679a8  mov     rcx, rsi; hHeap
0x1801679ab  lea     edx, [r15-28h]; dwFlags
0x1801679af  call    cs:__imp_HeapAlloc
0x1801679b6  nop     dword ptr [rax+rax+00h]
0x1801679bb  mov     [rbx+228h], rax
0x1801679c2  test    rax, rax
0x1801679c5  jz      short loc_180167A3E
0x1801679c7  lea     rax, ds:0[rbp*8]
0x1801679cf  add     rax, rbp
0x1801679d2  shl     rax, 2
0x1801679d6  cmp     rax, r12
0x1801679d9  ja      short loc_180167A3E
0x1801679db  mov     r8d, eax; dwBytes
0x1801679de  lea     edx, [r15-28h]; dwFlags
0x1801679e2  mov     rcx, rsi; hHeap
0x1801679e5  call    cs:__imp_HeapAlloc
0x1801679ec  nop     dword ptr [rax+rax+00h]
0x1801679f1  mov     [rbx+230h], rax
0x1801679f8  test    rax, rax
0x1801679fb  jz      short loc_180167A3E
0x1801679fd  mov     rax, [rbx+228h]
0x180167a04  mov     dword ptr [rax], 31464655h
0x180167a0a  mov     rax, [rbx+228h]
0x180167a11  mov     dword ptr [rax+4], 10001h
0x180167a18  mov     rax, [rbx+228h]
0x180167a1f  mov     [rax+8], r15d
0x180167a23  mov     rax, [rbx+228h]
0x180167a2a  mov     [rax+0Ch], ebp
0x180167a2d  test    ebp, ebp
0x180167a2f  jz      short loc_180167A48
0x180167a31  mov     rax, [rbx+228h]
0x180167a38  mov     [rax+18h], r15d
0x180167a3c  jmp     short loc_180167A48
0x180167a3e  mov     rcx, rbx; lpMem
0x180167a41  call    FICloseFontFile
0x180167a46  xor     ebx, ebx
0x180167a48  mov     rax, rbx
0x180167a4b  mov     rcx, [rsp+98h+var_38]
0x180167a50  xor     rcx, rsp; StackCookie
0x180167a53  call    __security_check_cookie
0x180167a58  mov     rbx, [rsp+98h+arg_0]
0x180167a60  add     rsp, 70h
0x180167a64  pop     r15
0x180167a66  pop     r12
0x180167a68  pop     rdi
0x180167a69  pop     rsi
0x180167a6a  pop     rbp
0x180167a6b  retn
```
