# IsServerMediaFromConfigFile(ushort const *,int *)

- ea: `0x140011d18`
- end: `0x140011efd`
- name: `?IsServerMediaFromConfigFile@@YAJPEBGPEAH@Z`
- size: `485`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140013894`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x140011d18`
- `0x1400135b8`
- `0x140027950`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140011eda`
- `KERNEL32!CloseHandle` at `0x140011eda`
- `KERNEL32!HeapFree` at `0x140011e92`
- `KERNEL32!HeapFree` at `0x140011eb9`
- `KERNEL32!HeapFree` at `0x140011e92`
- `KERNEL32!HeapFree` at `0x140011eb9`
- `KERNEL32!GetProcessHeap` at `0x140011e7e`
- `KERNEL32!GetProcessHeap` at `0x140011ea4`
- `KERNEL32!GetProcessHeap` at `0x140011e7e`
- `KERNEL32!GetProcessHeap` at `0x140011ea4`
- `KERNEL32!GetLastError` at `0x140011de1`
- `KERNEL32!GetLastError` at `0x140011de1`
- `KERNEL32!CreateFileW` at `0x140011dc4`
- `KERNEL32!CreateFileW` at `0x140011dc4`
- `KERNEL32!CompareStringW` at `0x140011e57`
- `KERNEL32!CompareStringW` at `0x140011e57`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsServerMediaFromConfigFile(const unsigned __int16 *a1, int *a2)
{
  __int64 FileW; // rdi
  WCHAR *v4; // rbx
  int v5; // ecx
  unsigned int v6; // esi
  int v7; // eax
  signed int LastError; // eax
  const WCHAR *Str; // rax
  HANDLE ProcessHeap; // rax

  FileW = -1;
  v4 = 0;
  if ( !a1 || !a2 )
  {
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_16;
  }
  v7 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)a1, (__int64)L"inf\\setup.cfg", 0);
  v6 = v7;
  if ( v7 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_16;
  }
  FileW = (__int64)CreateFileW(0, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    FileW = -1;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    goto LABEL_12;
  }
  Str = (const WCHAR *)IniGetStr(0);
  v4 = (WCHAR *)Str;
  if ( !Str )
  {
    v6 = -2147024883;
LABEL_12:
    v5 = v6;
    goto LABEL_3;
  }
  *a2 = CompareStringW(0x409u, 1u, L"server", -1, Str, -1) == 2;
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return v6;
}

```

## disassembly

```asm
0x140011d18  mov     rax, rsp
0x140011d1b  push    rbp
0x140011d1c  push    rsi
0x140011d1d  push    rdi
0x140011d1e  push    r14
0x140011d20  push    r15
0x140011d22  sub     rsp, 50h
0x140011d26  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140011d2e  mov     [rax+10h], rbx
0x140011d32  mov     r14, rdx
0x140011d35  or      r15, 0FFFFFFFFFFFFFFFFh
0x140011d39  mov     rdi, r15
0x140011d3c  xor     ebp, ebp
0x140011d3e  mov     [rax+8], rbp
0x140011d42  xor     ebx, ebx
0x140011d44  mov     [rax+18h], rbx
0x140011d48  test    rcx, rcx
0x140011d4b  jnz     short loc_140011D5E
0x140011d4d  mov     ecx, 80070057h
0x140011d52  mov     esi, ecx
0x140011d54  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140011d59  jmp     loc_140011E71
0x140011d5e  test    r14, r14
0x140011d61  jz      short loc_140011D4D
0x140011d63  lea     r9, [rsp+78h+lpFileName]
0x140011d6b  xor     r8d, r8d
0x140011d6e  lea     rdx, aInfSetupCfg; "inf\\setup.cfg"
0x140011d75  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x140011d7a  mov     esi, eax
0x140011d7c  test    eax, eax
0x140011d7e  jns     short loc_140011D94
0x140011d80  mov     ecx, eax
0x140011d82  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140011d87  mov     rbp, [rsp+78h+lpFileName]
0x140011d8f  jmp     loc_140011E71
0x140011d94  mov     rbp, [rsp+78h+lpFileName]
0x140011d9c  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x140011da5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140011dad  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x140011db5  xor     r9d, r9d; lpSecurityAttributes
0x140011db8  mov     edx, 80000000h; dwDesiredAccess
0x140011dbd  lea     r8d, [r9+1]; dwShareMode
0x140011dc1  mov     rcx, rbp; lpFileName
0x140011dc4  call    cs:__imp_CreateFileW
0x140011dcb  nop     dword ptr [rax+rax+00h]
0x140011dd0  mov     rdi, rax
0x140011dd3  inc     rax
0x140011dd6  test    rax, 0FFFFFFFFFFFFFFFEh
0x140011ddc  jnz     short loc_140011E0C
0x140011dde  mov     rdi, r15
0x140011de1  call    cs:__imp_GetLastError
0x140011de8  nop     dword ptr [rax+rax+00h]
0x140011ded  mov     esi, eax
0x140011def  test    eax, eax
0x140011df1  jnz     short loc_140011DFA
0x140011df3  mov     esi, 80004005h
0x140011df8  jmp     short loc_140011E05
0x140011dfa  jle     short loc_140011E05
0x140011dfc  movzx   esi, ax
0x140011dff  or      esi, 80070000h
0x140011e05  mov     ecx, esi
0x140011e07  jmp     loc_140011D54
0x140011e0c  mov     [rsp+78h+arg_18], rdi
0x140011e14  lea     r9, aClient; "client"
0x140011e1b  lea     r8, aType; "type"
0x140011e22  mov     rcx, rbp; lpFileName
0x140011e25  call    IniGetStr
0x140011e2a  mov     rbx, rax
0x140011e2d  test    rax, rax
0x140011e30  jnz     short loc_140011E39
0x140011e32  mov     esi, 8007000Dh
0x140011e37  jmp     short loc_140011E05
0x140011e39  mov     [rsp+78h+dwFlagsAndAttributes], r15d; cchCount2
0x140011e3e  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpString2
0x140011e43  mov     r9d, r15d; cchCount1
0x140011e46  lea     r8, aServer_0; "server"
0x140011e4d  mov     edx, 1; dwCmpFlags
0x140011e52  mov     ecx, 409h; Locale
0x140011e57  call    cs:__imp_CompareStringW
0x140011e5e  nop     dword ptr [rax+rax+00h]
0x140011e63  cmp     eax, 2
0x140011e66  mov     ecx, 0
0x140011e6b  setz    cl
0x140011e6e  mov     [r14], ecx
0x140011e71  mov     ecx, esi
0x140011e73  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011e78  nop
0x140011e79  test    rbx, rbx
0x140011e7c  jz      short loc_140011E9F
0x140011e7e  call    cs:__imp_GetProcessHeap
0x140011e85  nop     dword ptr [rax+rax+00h]
0x140011e8a  mov     rcx, rax; hHeap
0x140011e8d  mov     r8, rbx; lpMem
0x140011e90  xor     edx, edx; dwFlags
0x140011e92  call    cs:__imp_HeapFree
0x140011e99  nop     dword ptr [rax+rax+00h]
0x140011e9e  nop
0x140011e9f  test    rbp, rbp
0x140011ea2  jz      short loc_140011ECD
0x140011ea4  call    cs:__imp_GetProcessHeap
0x140011eab  nop     dword ptr [rax+rax+00h]
0x140011eb0  mov     rcx, rax; hHeap
0x140011eb3  lea     r8, [rbp-4]; lpMem
0x140011eb7  xor     edx, edx; dwFlags
0x140011eb9  call    cs:__imp_HeapFree
0x140011ec0  nop     dword ptr [rax+rax+00h]
0x140011ec5  xor     ecx, ecx
0x140011ec7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140011ecc  nop
0x140011ecd  lea     rax, [rdi-1]
0x140011ed1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140011ed5  ja      short loc_140011EE6
0x140011ed7  mov     rcx, rdi; hObject
0x140011eda  call    cs:__imp_CloseHandle
0x140011ee1  nop     dword ptr [rax+rax+00h]
0x140011ee6  mov     eax, esi
0x140011ee8  mov     rbx, [rsp+78h+arg_8]
0x140011ef0  add     rsp, 50h
0x140011ef4  pop     r15
0x140011ef6  pop     r14
0x140011ef8  pop     rdi
0x140011ef9  pop     rsi
0x140011efa  pop     rbp
0x140011efb  retn
```
