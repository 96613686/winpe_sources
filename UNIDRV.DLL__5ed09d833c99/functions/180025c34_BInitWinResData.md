# BInitWinResData

- ea: `0x180025c34`
- end: `0x180025ce3`
- name: `BInitWinResData`
- size: `175`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180025dc0`

## callees

- `0x180025c34`
- `0x18003fe9c`
- `0x1800457e8`
- `0x18004a71c`
- `0x1800750f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025c96`
- `KERNEL32!GetLastError` at `0x180025c96`

## string_xrefs

- `0x180025cbd`: `BInitWinResData: pRootResDLLName is NULL.`
- `0x180025ca5`: `BInitWinResData:Failed to load root resource DLL '%ws': Error = %d`

## pseudocode

```c
__int64 __fastcall BInitWinResData(HMODULE *a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v8; // ebx
  wchar_t *v9; // rdi
  HMODULE v10; // rax
  DWORD LastError; // eax

  memset_0(a1, 0, 0x630u);
  a1[196] = (HMODULE)a2;
  v8 = 1;
  if ( a4 )
    *((_DWORD *)a1 + 394) = 1;
  if ( !*(_DWORD *)(a3 + 4) || (v9 = (wchar_t *)(*(unsigned int *)(a3 + 4) + *(_QWORD *)(a3 + 320))) == 0 )
  {
    WriteDbgTraceInfo((__int64)"BInitWinResData", L"BInitWinResData: pRootResDLLName is NULL.");
    goto LABEL_8;
  }
  v10 = HLoadResourceDLL((__int64)a1, v9);
  *a1 = v10;
  if ( v10 )
  {
LABEL_8:
    a1[195] = (HMODULE)a3;
    return v8;
  }
  v8 = 0;
  LastError = GetLastError();
  WriteDbgTraceWarning(
    (__int64)"BInitWinResData",
    (__int64)L"BInitWinResData:Failed to load root resource DLL '%ws': Error = %d",
    v9,
    LastError);
  return v8;
}

```

## disassembly

```asm
0x180025c34  push    rbx
0x180025c36  push    rbp
0x180025c37  push    rsi
0x180025c38  push    rdi
0x180025c39  sub     rsp, 28h
0x180025c3d  mov     rbp, r8
0x180025c40  mov     rbx, rdx
0x180025c43  xor     edx, edx; Val
0x180025c45  mov     r8d, 630h; Size
0x180025c4b  mov     edi, r9d
0x180025c4e  mov     rsi, rcx
0x180025c51  call    memset_0
0x180025c56  mov     [rsi+620h], rbx
0x180025c5d  mov     ebx, 1
0x180025c62  test    edi, edi
0x180025c64  jz      short loc_180025C6C
0x180025c66  mov     [rsi+628h], ebx
0x180025c6c  cmp     dword ptr [rbp+4], 0
0x180025c70  jz      short loc_180025CBD
0x180025c72  mov     ecx, [rbp+4]
0x180025c75  mov     rdi, [rbp+140h]
0x180025c7c  add     rdi, rcx
0x180025c7f  jz      short loc_180025CBD
0x180025c81  mov     rdx, rdi
0x180025c84  mov     rcx, rsi
0x180025c87  call    HLoadResourceDLL
0x180025c8c  mov     [rsi], rax
0x180025c8f  test    rax, rax
0x180025c92  jnz     short loc_180025CD0
0x180025c94  xor     ebx, ebx
0x180025c96  call    cs:__imp_GetLastError
0x180025c9d  nop     dword ptr [rax+rax+00h]
0x180025ca2  mov     r8, rdi
0x180025ca5  lea     rdx, aBinitwinresdat; "BInitWinResData:Failed to load root res"...
0x180025cac  mov     r9d, eax
0x180025caf  lea     rcx, aBinitwinresdat_0; "BInitWinResData"
0x180025cb6  call    WriteDbgTraceWarning
0x180025cbb  jmp     short loc_180025CD7
0x180025cbd  lea     rdx, aBinitwinresdat_1; "BInitWinResData: pRootResDLLName is NUL"...
0x180025cc4  lea     rcx, aBinitwinresdat_0; "BInitWinResData"
0x180025ccb  call    WriteDbgTraceInfo
0x180025cd0  mov     [rsi+618h], rbp
0x180025cd7  mov     eax, ebx
0x180025cd9  add     rsp, 28h
0x180025cdd  pop     rdi
0x180025cde  pop     rsi
0x180025cdf  pop     rbp
0x180025ce0  pop     rbx
0x180025ce1  retn
```
