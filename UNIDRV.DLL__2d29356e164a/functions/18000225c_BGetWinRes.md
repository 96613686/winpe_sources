# BGetWinRes

- ea: `0x18000225c`
- end: `0x180002379`
- name: `BGetWinRes`
- size: `285`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002a00`
- `0x180021c40`
- `0x180026aa0`

## callees

- `0x18000225c`
- `0x18003ed80`
- `0x180044538`
- `0x180044bfc`

## import_xrefs

- `KERNEL32!FindResourceW` at `0x1800022b7`
- `KERNEL32!FindResourceW` at `0x1800022b7`
- `KERNEL32!LoadResource` at `0x1800022cb`
- `KERNEL32!LoadResource` at `0x1800022cb`
- `KERNEL32!LockResource` at `0x1800022d9`
- `KERNEL32!LockResource` at `0x1800022d9`
- `KERNEL32!SizeofResource` at `0x1800022ed`
- `KERNEL32!SizeofResource` at `0x1800022ed`
- `KERNEL32!SetLastError` at `0x180002347`
- `KERNEL32!SetLastError` at `0x18000235b`
- `KERNEL32!SetLastError` at `0x180002347`
- `KERNEL32!SetLastError` at `0x18000235b`

## string_xrefs

- `0x180002361`: `HGetModuleHandle:Can't find Resource DLL name in UIINFO.`

## pseudocode

```c
_BOOL8 __fastcall BGetWinRes(__int64 a1, unsigned __int16 *a2, __int64 a3, __int64 a4)
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

  v5 = (const WCHAR *)(int)a3;
  if ( (*(_DWORD *)a2 & 0x7FFFFFFF) == 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning("HGetModuleHandle", L"RCID_DMPAPER_SYSTEM_NAME  is not a valid qualified resource name.");
    return 0;
  }
  v7 = (const WCHAR *)*a2;
  if ( *((_BYTE *)a2 + 2) || (*((_BYTE *)a2 + 3) & 0x7F) != 0 )
  {
    v8 = *(HMODULE *)(a1 + 8LL * (*((_BYTE *)a2 + 3) & 0x7F) + 16);
    v14 = *((_BYTE *)a2 + 3) & 0x7F;
    if ( v8 )
      goto LABEL_7;
    v15 = (wchar_t *)PGetResourceDLL(*(_QWORD *)(a1 + 1560), (__int64)a2, a3);
    if ( !v15 )
    {
      SetLastError(0x57u);
      WriteDbgTraceWarning("HGetModuleHandle", L"HGetModuleHandle:Can't find Resource DLL name in UIINFO.");
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
0x18000225c  push    rbx
0x18000225e  push    rbp
0x18000225f  push    rsi
0x180002260  push    rdi
0x180002261  push    r14
0x180002263  push    r15
0x180002265  sub     rsp, 28h
0x180002269  mov     eax, [rdx]
0x18000226b  mov     rdi, rcx
0x18000226e  mov     ecx, 7FFFFFFFh
0x180002273  movsxd  r15, r8d
0x180002276  and     eax, ecx
0x180002278  mov     r14, r9
0x18000227b  cmp     eax, ecx
0x18000227d  jz      loc_180002342
0x180002283  movzx   eax, byte ptr [rdx+3]
0x180002287  movzx   ebp, word ptr [rdx]
0x18000228a  and     eax, 7Fh
0x18000228d  cmp     byte ptr [rdx+2], 0
0x180002291  jnz     short loc_180002301
0x180002293  test    eax, eax
0x180002295  jnz     short loc_180002301
0x180002297  mov     rbx, [rdi]
0x18000229a  test    rbx, rbx
0x18000229d  jnz     short loc_1800022AE
0x18000229f  xor     eax, eax
0x1800022a1  add     rsp, 28h
0x1800022a5  pop     r15
0x1800022a7  pop     r14
0x1800022a9  pop     rdi
0x1800022aa  pop     rsi
0x1800022ab  pop     rbp
0x1800022ac  pop     rbx
0x1800022ad  retn
0x1800022ae  mov     r8, r15; lpType
0x1800022b1  mov     rdx, rbp; lpName
0x1800022b4  mov     rcx, rbx; hModule
0x1800022b7  call    cs:__imp_FindResourceW
0x1800022bd  mov     rdi, rax
0x1800022c0  test    rax, rax
0x1800022c3  jz      short loc_18000229F
0x1800022c5  mov     rdx, rax; hResInfo
0x1800022c8  mov     rcx, rbx; hModule
0x1800022cb  call    cs:__imp_LoadResource
0x1800022d1  test    rax, rax
0x1800022d4  jz      short loc_18000229F
0x1800022d6  mov     rcx, rax; hResData
0x1800022d9  call    cs:__imp_LockResource
0x1800022df  mov     [r14], rax
0x1800022e2  test    rax, rax
0x1800022e5  jz      short loc_18000229F
0x1800022e7  mov     rdx, rdi; hResInfo
0x1800022ea  mov     rcx, rbx; hModule
0x1800022ed  call    cs:__imp_SizeofResource
0x1800022f3  mov     [r14+8], eax
0x1800022f7  xor     eax, eax
0x1800022f9  cmp     [r14], rax
0x1800022fc  setnz   al
0x1800022ff  jmp     short loc_1800022A1
0x180002301  mov     rbx, [rdi+rax*8+10h]
0x180002306  mov     esi, eax
0x180002308  test    rbx, rbx
0x18000230b  jnz     short loc_1800022AE
0x18000230d  mov     rcx, [rdi+618h]
0x180002314  call    PGetResourceDLL
0x180002319  test    rax, rax
0x18000231c  jz      short loc_180002356
0x18000231e  mov     rdx, rax
0x180002321  mov     rcx, rdi
0x180002324  call    HLoadResourceDLL
0x180002329  mov     rbx, rax
0x18000232c  test    rax, rax
0x18000232f  jz      loc_18000229A
0x180002335  mov     [rdi+rsi*8+10h], rax
0x18000233a  inc     dword ptr [rdi+8]
0x18000233d  jmp     loc_1800022AE
0x180002342  mov     ecx, 57h ; 'W'; dwErrCode
0x180002347  call    cs:__imp_SetLastError
0x18000234d  lea     rdx, aRcidDmpaperSys; "RCID_DMPAPER_SYSTEM_NAME  is not a vali"...
0x180002354  jmp     short loc_180002368
0x180002356  mov     ecx, 57h ; 'W'; dwErrCode
0x18000235b  call    cs:__imp_SetLastError
0x180002361  lea     rdx, aHgetmodulehand_0; "HGetModuleHandle:Can't find Resource DL"...
0x180002368  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x18000236f  call    WriteDbgTraceWarning
0x180002374  jmp     loc_18000229F
```
