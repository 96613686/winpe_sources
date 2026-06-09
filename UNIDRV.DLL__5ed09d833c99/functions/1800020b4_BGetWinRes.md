# BGetWinRes

- ea: `0x1800020b4`
- end: `0x1800021fe`
- name: `BGetWinRes`
- size: `330`
- prototype: `_BOOL8 __fastcall(__int64, unsigned __int16 *, int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002990`
- `0x18002213c`
- `0x18002719c`

## callees

- `0x1800020b4`
- `0x18003fe9c`
- `0x1800457e8`
- `0x180045ecc`

## import_xrefs

- `KERNEL32!FindResourceW` at `0x180002118`
- `KERNEL32!FindResourceW` at `0x180002118`
- `KERNEL32!LoadResource` at `0x180002132`
- `KERNEL32!LoadResource` at `0x180002132`
- `KERNEL32!LockResource` at `0x180002146`
- `KERNEL32!LockResource` at `0x180002146`
- `KERNEL32!SizeofResource` at `0x180002160`
- `KERNEL32!SizeofResource` at `0x180002160`
- `KERNEL32!SetLastError` at `0x1800021c0`
- `KERNEL32!SetLastError` at `0x1800021da`
- `KERNEL32!SetLastError` at `0x1800021c0`
- `KERNEL32!SetLastError` at `0x1800021da`

## string_xrefs

- `0x1800021e6`: `HGetModuleHandle:Can't find Resource DLL name in UIINFO.`

## pseudocode

```c
_BOOL8 __fastcall BGetWinRes(__int64 a1, unsigned __int16 *a2, int a3, __int64 a4)
{
  const WCHAR *v5; // r15
  const WCHAR *v7; // rbp
  HMODULE v8; // rbx
  HRSRC ResourceW; // rax
  HRSRC v11; // rdi
  HGLOBAL Resource; // rax
  LPVOID v13; // rax
  __int64 v14; // rsi
  wchar_t *v15; // rax
  HMODULE v16; // rax

  v5 = (const WCHAR *)a3;
  if ( (*(_DWORD *)a2 & 0x7FFFFFFF) == 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning(
      (__int64)"HGetModuleHandle",
      (__int64)L"RCID_DMPAPER_SYSTEM_NAME  is not a valid qualified resource name.");
    return 0;
  }
  v7 = (const WCHAR *)*a2;
  if ( *((_BYTE *)a2 + 2) || (*((_BYTE *)a2 + 3) & 0x7F) != 0 )
  {
    v8 = *(HMODULE *)(a1 + 8LL * (*((_BYTE *)a2 + 3) & 0x7F) + 16);
    v14 = *((_BYTE *)a2 + 3) & 0x7F;
    if ( v8 )
      goto LABEL_7;
    v15 = (wchar_t *)PGetResourceDLL(*(_QWORD *)(a1 + 1560));
    if ( !v15 )
    {
      SetLastError(0x57u);
      WriteDbgTraceWarning(
        (__int64)"HGetModuleHandle",
        (__int64)L"HGetModuleHandle:Can't find Resource DLL name in UIINFO.");
      return 0;
    }
    v16 = HLoadResourceDLL(a1, v15);
    v8 = v16;
    if ( v16 )
    {
      *(_QWORD *)(a1 + 8 * v14 + 16) = v16;
      ++*(_DWORD *)(a1 + 8);
      goto LABEL_7;
    }
  }
  else
  {
    v8 = *(HMODULE *)a1;
  }
  if ( !v8 )
    return 0;
LABEL_7:
  ResourceW = FindResourceW(v8, v7, v5);
  v11 = ResourceW;
  if ( !ResourceW )
    return 0;
  Resource = LoadResource(v8, ResourceW);
  if ( !Resource )
    return 0;
  v13 = LockResource(Resource);
  *(_QWORD *)a4 = v13;
  if ( !v13 )
    return 0;
  *(_DWORD *)(a4 + 8) = SizeofResource(v8, v11);
  return *(_QWORD *)a4 != 0;
}

```

## disassembly

```asm
0x1800020b4  push    rbx
0x1800020b6  push    rbp
0x1800020b7  push    rsi
0x1800020b8  push    rdi
0x1800020b9  push    r14
0x1800020bb  push    r15
0x1800020bd  sub     rsp, 28h
0x1800020c1  mov     eax, [rdx]
0x1800020c3  mov     rdi, rcx
0x1800020c6  mov     ecx, 7FFFFFFFh
0x1800020cb  movsxd  r15, r8d
0x1800020ce  and     eax, ecx
0x1800020d0  mov     r14, r9
0x1800020d3  cmp     eax, ecx
0x1800020d5  jz      loc_1800021BB
0x1800020db  movzx   eax, byte ptr [rdx+3]
0x1800020df  movzx   ebp, word ptr [rdx]
0x1800020e2  and     eax, 7Fh
0x1800020e5  cmp     byte ptr [rdx+2], 0
0x1800020e9  jnz     loc_18000217A
0x1800020ef  test    eax, eax
0x1800020f1  jnz     loc_18000217A
0x1800020f7  mov     rbx, [rdi]
0x1800020fa  test    rbx, rbx
0x1800020fd  jnz     short loc_18000210F
0x1800020ff  xor     eax, eax
0x180002101  add     rsp, 28h
0x180002105  pop     r15
0x180002107  pop     r14
0x180002109  pop     rdi
0x18000210a  pop     rsi
0x18000210b  pop     rbp
0x18000210c  pop     rbx
0x18000210d  retn
0x18000210f  mov     r8, r15; lpType
0x180002112  mov     rdx, rbp; lpName
0x180002115  mov     rcx, rbx; hModule
0x180002118  call    cs:__imp_FindResourceW
0x18000211f  nop     dword ptr [rax+rax+00h]
0x180002124  mov     rdi, rax
0x180002127  test    rax, rax
0x18000212a  jz      short loc_1800020FF
0x18000212c  mov     rdx, rax; hResInfo
0x18000212f  mov     rcx, rbx; hModule
0x180002132  call    cs:__imp_LoadResource
0x180002139  nop     dword ptr [rax+rax+00h]
0x18000213e  test    rax, rax
0x180002141  jz      short loc_1800020FF
0x180002143  mov     rcx, rax; hResData
0x180002146  call    cs:__imp_LockResource
0x18000214d  nop     dword ptr [rax+rax+00h]
0x180002152  mov     [r14], rax
0x180002155  test    rax, rax
0x180002158  jz      short loc_1800020FF
0x18000215a  mov     rdx, rdi; hResInfo
0x18000215d  mov     rcx, rbx; hModule
0x180002160  call    cs:__imp_SizeofResource
0x180002167  nop     dword ptr [rax+rax+00h]
0x18000216c  mov     [r14+8], eax
0x180002170  xor     eax, eax
0x180002172  cmp     [r14], rax
0x180002175  setnz   al
0x180002178  jmp     short loc_180002101
0x18000217a  mov     rbx, [rdi+rax*8+10h]
0x18000217f  mov     esi, eax
0x180002181  test    rbx, rbx
0x180002184  jnz     short loc_18000210F
0x180002186  mov     rcx, [rdi+618h]
0x18000218d  call    PGetResourceDLL
0x180002192  test    rax, rax
0x180002195  jz      short loc_1800021D5
0x180002197  mov     rdx, rax
0x18000219a  mov     rcx, rdi
0x18000219d  call    HLoadResourceDLL
0x1800021a2  mov     rbx, rax
0x1800021a5  test    rax, rax
0x1800021a8  jz      loc_1800020FA
0x1800021ae  mov     [rdi+rsi*8+10h], rax
0x1800021b3  inc     dword ptr [rdi+8]
0x1800021b6  jmp     loc_18000210F
0x1800021bb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800021c0  call    cs:__imp_SetLastError
0x1800021c7  nop     dword ptr [rax+rax+00h]
0x1800021cc  lea     rdx, aRcidDmpaperSys; "RCID_DMPAPER_SYSTEM_NAME  is not a vali"...
0x1800021d3  jmp     short loc_1800021ED
0x1800021d5  mov     ecx, 57h ; 'W'; dwErrCode
0x1800021da  call    cs:__imp_SetLastError
0x1800021e1  nop     dword ptr [rax+rax+00h]
0x1800021e6  lea     rdx, aHgetmodulehand_0; "HGetModuleHandle:Can't find Resource DL"...
0x1800021ed  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x1800021f4  call    WriteDbgTraceWarning
0x1800021f9  jmp     loc_1800020FF
```
