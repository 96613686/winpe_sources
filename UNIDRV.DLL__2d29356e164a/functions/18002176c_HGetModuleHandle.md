# HGetModuleHandle

- ea: `0x18002176c`
- end: `0x18002182e`
- name: `HGetModuleHandle`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800212f4`
- `0x1800213bc`

## callees

- `0x18002176c`
- `0x18003ed80`
- `0x180044538`
- `0x180044bfc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180021790`
- `KERNEL32!SetLastError` at `0x180021802`
- `KERNEL32!SetLastError` at `0x180021790`
- `KERNEL32!SetLastError` at `0x180021802`

## string_xrefs

- `0x180021808`: `HGetModuleHandle:Can't find Resource DLL name in UIINFO.`

## pseudocode

```c
HMODULE __fastcall HGetModuleHandle(__int64 a1, __int64 a2, __int64 a3)
{
  HMODULE v5; // rdi
  __int64 v6; // rsi
  wchar_t *v7; // rax
  HMODULE v8; // rax

  if ( (*(_DWORD *)a2 & 0x7FFFFFFF) == 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning("HGetModuleHandle", L"RCID_DMPAPER_SYSTEM_NAME  is not a valid qualified resource name.");
    return 0;
  }
  else
  {
    if ( !*(_BYTE *)(a2 + 2) && (*(_BYTE *)(a2 + 3) & 0x7F) == 0 )
      return *(HMODULE *)a1;
    v5 = *(HMODULE *)(a1 + 8LL * (*(_BYTE *)(a2 + 3) & 0x7F) + 16);
    v6 = *(_BYTE *)(a2 + 3) & 0x7F;
    if ( !v5 )
    {
      v7 = (wchar_t *)PGetResourceDLL(*(_QWORD *)(a1 + 1560), a2, a3);
      if ( v7 )
      {
        v8 = HLoadResourceDLL(a1, v7);
        v5 = v8;
        if ( v8 )
        {
          *(_QWORD *)(a1 + 8 * v6 + 16) = v8;
          ++*(_DWORD *)(a1 + 8);
        }
      }
      else
      {
        SetLastError(0x57u);
        WriteDbgTraceWarning("HGetModuleHandle", L"HGetModuleHandle:Can't find Resource DLL name in UIINFO.");
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x18002176c  mov     [rsp+arg_0], rbx
0x180021771  mov     [rsp+arg_8], rsi
0x180021776  push    rdi
0x180021777  sub     rsp, 20h
0x18002177b  mov     eax, [rdx]
0x18002177d  mov     rbx, rcx
0x180021780  mov     ecx, 7FFFFFFFh
0x180021785  and     eax, ecx
0x180021787  cmp     eax, ecx
0x180021789  jnz     short loc_1800217AD
0x18002178b  mov     ecx, 57h ; 'W'; dwErrCode
0x180021790  call    cs:__imp_SetLastError
0x180021796  lea     rdx, aRcidDmpaperSys; "RCID_DMPAPER_SYSTEM_NAME  is not a vali"...
0x18002179d  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x1800217a4  call    WriteDbgTraceWarning
0x1800217a9  xor     eax, eax
0x1800217ab  jmp     short loc_18002181E
0x1800217ad  movzx   eax, byte ptr [rdx+3]
0x1800217b1  and     eax, 7Fh
0x1800217b4  cmp     byte ptr [rdx+2], 0
0x1800217b8  jnz     short loc_1800217C3
0x1800217ba  test    eax, eax
0x1800217bc  jnz     short loc_1800217C3
0x1800217be  mov     rdi, [rbx]
0x1800217c1  jmp     short loc_18002181B
0x1800217c3  mov     rdi, [rbx+rax*8+10h]
0x1800217c8  mov     esi, eax
0x1800217ca  test    rdi, rdi
0x1800217cd  jnz     short loc_18002181B
0x1800217cf  mov     rcx, [rbx+618h]
0x1800217d6  call    PGetResourceDLL
0x1800217db  test    rax, rax
0x1800217de  jz      short loc_1800217FD
0x1800217e0  mov     rdx, rax
0x1800217e3  mov     rcx, rbx
0x1800217e6  call    HLoadResourceDLL
0x1800217eb  mov     rdi, rax
0x1800217ee  test    rax, rax
0x1800217f1  jz      short loc_18002181B
0x1800217f3  mov     [rbx+rsi*8+10h], rax
0x1800217f8  inc     dword ptr [rbx+8]
0x1800217fb  jmp     short loc_18002181B
0x1800217fd  mov     ecx, 57h ; 'W'; dwErrCode
0x180021802  call    cs:__imp_SetLastError
0x180021808  lea     rdx, aHgetmodulehand_0; "HGetModuleHandle:Can't find Resource DL"...
0x18002180f  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x180021816  call    WriteDbgTraceWarning
0x18002181b  mov     rax, rdi
0x18002181e  mov     rbx, [rsp+28h+arg_0]
0x180021823  mov     rsi, [rsp+28h+arg_8]
0x180021828  add     rsp, 20h
0x18002182c  pop     rdi
0x18002182d  retn
```
