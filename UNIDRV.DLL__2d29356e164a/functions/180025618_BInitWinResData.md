# BInitWinResData

- ea: `0x180025618`
- end: `0x1800256c0`
- name: `BInitWinResData`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180025780`

## callees

- `0x180025618`
- `0x18003ed80`
- `0x180044538`
- `0x1800491dc`
- `0x180073060`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002567a`
- `KERNEL32!GetLastError` at `0x18002567a`

## string_xrefs

- `0x18002569b`: `BInitWinResData: pRootResDLLName is NULL.`
- `0x180025683`: `BInitWinResData:Failed to load root resource DLL '%ws': Error = %d`

## pseudocode

```c
__int64 __fastcall BInitWinResData(HMODULE *a1, HMODULE a2, HMODULE a3, int a4)
{
  unsigned int v8; // ebx
  wchar_t *v9; // rdi
  HMODULE v10; // rax
  DWORD LastError; // eax

  memset_0(a1, 0, 0x630u);
  a1[196] = a2;
  v8 = 1;
  if ( a4 )
    *((_DWORD *)a1 + 394) = 1;
  if ( !*((_DWORD *)a3 + 1) || (v9 = (wchar_t *)(*((unsigned int *)a3 + 1) + *((_QWORD *)a3 + 40))) == 0 )
  {
    WriteDbgTraceInfo("BInitWinResData", L"BInitWinResData: pRootResDLLName is NULL.");
    goto LABEL_8;
  }
  v10 = HLoadResourceDLL((__int64)a1, v9);
  *a1 = v10;
  if ( v10 )
  {
LABEL_8:
    a1[195] = a3;
    return v8;
  }
  v8 = 0;
  LastError = GetLastError();
  WriteDbgTraceWarning(
    "BInitWinResData",
    L"BInitWinResData:Failed to load root resource DLL '%ws': Error = %d",
    v9,
    LastError);
  return v8;
}

```

## disassembly

```asm
0x180025618  push    rbx
0x18002561a  push    rbp
0x18002561b  push    rsi
0x18002561c  push    rdi
0x18002561d  sub     rsp, 28h
0x180025621  mov     rbp, r8
0x180025624  mov     rbx, rdx
0x180025627  xor     edx, edx; Val
0x180025629  mov     r8d, 630h; Size
0x18002562f  mov     edi, r9d
0x180025632  mov     rsi, rcx
0x180025635  call    memset_0
0x18002563a  mov     [rsi+620h], rbx
0x180025641  mov     ebx, 1
0x180025646  test    edi, edi
0x180025648  jz      short loc_180025650
0x18002564a  mov     [rsi+628h], ebx
0x180025650  cmp     dword ptr [rbp+4], 0
0x180025654  jz      short loc_18002569B
0x180025656  mov     ecx, [rbp+4]
0x180025659  mov     rdi, [rbp+140h]
0x180025660  add     rdi, rcx
0x180025663  jz      short loc_18002569B
0x180025665  mov     rdx, rdi
0x180025668  mov     rcx, rsi
0x18002566b  call    HLoadResourceDLL
0x180025670  mov     [rsi], rax
0x180025673  test    rax, rax
0x180025676  jnz     short loc_1800256AE
0x180025678  xor     ebx, ebx
0x18002567a  call    cs:__imp_GetLastError
0x180025680  mov     r8, rdi
0x180025683  lea     rdx, aBinitwinresdat; "BInitWinResData:Failed to load root res"...
0x18002568a  mov     r9d, eax
0x18002568d  lea     rcx, aBinitwinresdat_0; "BInitWinResData"
0x180025694  call    WriteDbgTraceWarning
0x180025699  jmp     short loc_1800256B5
0x18002569b  lea     rdx, aBinitwinresdat_1; "BInitWinResData: pRootResDLLName is NUL"...
0x1800256a2  lea     rcx, aBinitwinresdat_0; "BInitWinResData"
0x1800256a9  call    WriteDbgTraceInfo
0x1800256ae  mov     [rsi+618h], rbp
0x1800256b5  mov     eax, ebx
0x1800256b7  add     rsp, 28h
0x1800256bb  pop     rdi
0x1800256bc  pop     rsi
0x1800256bd  pop     rbp
0x1800256be  pop     rbx
0x1800256bf  retn
```
