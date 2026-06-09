# SafeRpcServerUnregisterIf

- ea: `0x1800270d0`
- end: `0x180027242`
- name: `SafeRpcServerUnregisterIf`
- size: `370`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180027248`
- `0x180027740`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x1800270d0`
- `0x18003e010`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x18002720d`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002720d`
- `KERNEL32!LoadLibraryW` at `0x18002711e`
- `KERNEL32!LoadLibraryW` at `0x18002711e`
- `KERNEL32!FreeLibrary` at `0x180027223`
- `KERNEL32!FreeLibrary` at `0x180027223`
- `KERNEL32!GetProcAddress` at `0x18002713c`
- `KERNEL32!GetProcAddress` at `0x18002713c`
- `KERNEL32!GetLastError` at `0x180027180`
- `KERNEL32!GetLastError` at `0x1800271aa`
- `KERNEL32!GetLastError` at `0x180027180`
- `KERNEL32!GetLastError` at `0x1800271aa`

## string_xrefs

- `0x180027117`: `RPCRT4.DLL`

## pseudocode

```c
__int64 SafeRpcServerUnregisterIf()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
  }
  LibraryW = LoadLibraryW(L"RPCRT4.DLL");
  v1 = LibraryW;
  if ( !LibraryW )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    LastError = GetLastError();
    v6 = 12;
    goto LABEL_16;
  }
  ProcAddress = GetProcAddress(LibraryW, "RpcServerUnregisterIfEx");
  if ( ProcAddress )
  {
    v3 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD))ProcAddress)(qword_180041B80, 0, 0);
LABEL_22:
    FreeLibrary(v1);
    return v3;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_17:
      if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x1000) != 0 && *((_BYTE *)v4 + 25) >= 3u )
        WPP_SF_(v4[2], 13, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids);
      goto LABEL_21;
    }
    LastError = GetLastError();
    v6 = 11;
LABEL_16:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids, LastError);
    v4 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
LABEL_21:
  v3 = RpcServerUnregisterIf(qword_180041B80, 0, 0);
  if ( v1 )
    goto LABEL_22;
  return v3;
}

```

## disassembly

```asm
0x1800270d0  mov     [rsp+arg_0], rbx
0x1800270d5  mov     [rsp+arg_8], rsi
0x1800270da  push    rdi
0x1800270db  sub     rsp, 20h
0x1800270df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270e6  lea     rsi, WPP_GLOBAL_Control
0x1800270ed  mov     edi, 1000h
0x1800270f2  cmp     rcx, rsi
0x1800270f5  jz      short loc_180027117
0x1800270f7  test    [rcx+1Ch], edi
0x1800270fa  jz      short loc_180027117
0x1800270fc  cmp     byte ptr [rcx+19h], 5
0x180027100  jb      short loc_180027117
0x180027102  mov     rcx, [rcx+10h]
0x180027106  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x18002710d  mov     edx, 0Ah
0x180027112  call    WPP_SF_
0x180027117  lea     rcx, LibFileName; "RPCRT4.DLL"
0x18002711e  call    cs:__imp_LoadLibraryW
0x180027125  nop     dword ptr [rax+rax+00h]
0x18002712a  mov     rbx, rax
0x18002712d  test    rax, rax
0x180027130  jz      short loc_180027193
0x180027132  lea     rdx, aRpcserverunreg; "RpcServerUnregisterIfEx"
0x180027139  mov     rcx, rax; hModule
0x18002713c  call    cs:__imp_GetProcAddress
0x180027143  nop     dword ptr [rax+rax+00h]
0x180027148  test    rax, rax
0x18002714b  jz      short loc_180027165
0x18002714d  xor     r8d, r8d
0x180027150  lea     rcx, qword_180041B80
0x180027157  xor     edx, edx
0x180027159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002715e  mov     edi, eax
0x180027160  jmp     loc_180027220
0x180027165  mov     rcx, cs:WPP_GLOBAL_Control
0x18002716c  cmp     rcx, rsi
0x18002716f  jz      loc_180027201
0x180027175  test    [rcx+1Ch], edi
0x180027178  jz      short loc_1800271DC
0x18002717a  cmp     byte ptr [rcx+19h], 2
0x18002717e  jb      short loc_1800271DC
0x180027180  call    cs:__imp_GetLastError
0x180027187  nop     dword ptr [rax+rax+00h]
0x18002718c  mov     edx, 0Bh
0x180027191  jmp     short loc_1800271BB
0x180027193  mov     rcx, cs:WPP_GLOBAL_Control
0x18002719a  cmp     rcx, rsi
0x18002719d  jz      short loc_180027201
0x18002719f  test    [rcx+1Ch], edi
0x1800271a2  jz      short loc_1800271DC
0x1800271a4  cmp     byte ptr [rcx+19h], 2
0x1800271a8  jb      short loc_1800271DC
0x1800271aa  call    cs:__imp_GetLastError
0x1800271b1  nop     dword ptr [rax+rax+00h]
0x1800271b6  mov     edx, 0Ch
0x1800271bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271c2  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x1800271c9  mov     r9d, eax
0x1800271cc  mov     rcx, [rcx+10h]
0x1800271d0  call    WPP_SF_d
0x1800271d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271dc  cmp     rcx, rsi
0x1800271df  jz      short loc_180027201
0x1800271e1  test    [rcx+1Ch], edi
0x1800271e4  jz      short loc_180027201
0x1800271e6  cmp     byte ptr [rcx+19h], 3
0x1800271ea  jb      short loc_180027201
0x1800271ec  mov     rcx, [rcx+10h]
0x1800271f0  lea     r8, WPP_6e3acdab872831c35b7514c03928d94f_Traceguids
0x1800271f7  mov     edx, 0Dh
0x1800271fc  call    WPP_SF_
0x180027201  xor     r8d, r8d; WaitForCallsToComplete
0x180027204  lea     rcx, qword_180041B80; IfSpec
0x18002720b  xor     edx, edx; MgrTypeUuid
0x18002720d  call    cs:__imp_RpcServerUnregisterIf
0x180027214  nop     dword ptr [rax+rax+00h]
0x180027219  mov     edi, eax
0x18002721b  test    rbx, rbx
0x18002721e  jz      short loc_18002722F
0x180027220  mov     rcx, rbx; hLibModule
0x180027223  call    cs:__imp_FreeLibrary
0x18002722a  nop     dword ptr [rax+rax+00h]
0x18002722f  mov     rbx, [rsp+28h+arg_0]
0x180027234  mov     eax, edi
0x180027236  mov     rsi, [rsp+28h+arg_8]
0x18002723b  add     rsp, 20h
0x18002723f  pop     rdi
0x180027240  retn
```
