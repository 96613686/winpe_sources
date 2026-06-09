# HGetModuleHandle

- ea: `0x180021c54`
- end: `0x180021d23`
- name: `HGetModuleHandle`
- size: `207`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180021794`
- `0x180021874`

## callees

- `0x180021c54`
- `0x18003fe9c`
- `0x1800457e8`
- `0x180045ecc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180021c78`
- `KERNEL32!SetLastError` at `0x180021cf0`
- `KERNEL32!SetLastError` at `0x180021c78`
- `KERNEL32!SetLastError` at `0x180021cf0`

## string_xrefs

- `0x180021cfc`: `HGetModuleHandle:Can't find Resource DLL name in UIINFO.`

## pseudocode

```c
HMODULE __fastcall HGetModuleHandle(__int64 a1, __int64 a2)
{
  HMODULE v4; // rdi
  __int64 v5; // rsi
  wchar_t *v6; // rax
  HMODULE v7; // rax

  if ( (*(_DWORD *)a2 & 0x7FFFFFFF) == 0x7FFFFFFF )
  {
    SetLastError(0x57u);
    WriteDbgTraceWarning(
      (__int64)"HGetModuleHandle",
      (__int64)L"RCID_DMPAPER_SYSTEM_NAME  is not a valid qualified resource name.");
    return 0;
  }
  else
  {
    if ( !*(_BYTE *)(a2 + 2) && (*(_BYTE *)(a2 + 3) & 0x7F) == 0 )
      return *(HMODULE *)a1;
    v4 = *(HMODULE *)(a1 + 8LL * (*(_BYTE *)(a2 + 3) & 0x7F) + 16);
    v5 = *(_BYTE *)(a2 + 3) & 0x7F;
    if ( !v4 )
    {
      v6 = (wchar_t *)PGetResourceDLL(*(_QWORD *)(a1 + 1560));
      if ( v6 )
      {
        v7 = HLoadResourceDLL(a1, v6);
        v4 = v7;
        if ( v7 )
        {
          *(_QWORD *)(a1 + 8 * v5 + 16) = v7;
          ++*(_DWORD *)(a1 + 8);
        }
      }
      else
      {
        SetLastError(0x57u);
        WriteDbgTraceWarning(
          (__int64)"HGetModuleHandle",
          (__int64)L"HGetModuleHandle:Can't find Resource DLL name in UIINFO.");
      }
    }
    return v4;
  }
}

```

## disassembly

```asm
0x180021c54  mov     [rsp+arg_0], rbx
0x180021c59  mov     [rsp+arg_8], rsi
0x180021c5e  push    rdi
0x180021c5f  sub     rsp, 20h
0x180021c63  mov     eax, [rdx]
0x180021c65  mov     rbx, rcx
0x180021c68  mov     ecx, 7FFFFFFFh
0x180021c6d  and     eax, ecx
0x180021c6f  cmp     eax, ecx
0x180021c71  jnz     short loc_180021C9B
0x180021c73  mov     ecx, 57h ; 'W'; dwErrCode
0x180021c78  call    cs:__imp_SetLastError
0x180021c7f  nop     dword ptr [rax+rax+00h]
0x180021c84  lea     rdx, aRcidDmpaperSys; "RCID_DMPAPER_SYSTEM_NAME  is not a vali"...
0x180021c8b  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x180021c92  call    WriteDbgTraceWarning
0x180021c97  xor     eax, eax
0x180021c99  jmp     short loc_180021D12
0x180021c9b  movzx   eax, byte ptr [rdx+3]
0x180021c9f  and     eax, 7Fh
0x180021ca2  cmp     byte ptr [rdx+2], 0
0x180021ca6  jnz     short loc_180021CB1
0x180021ca8  test    eax, eax
0x180021caa  jnz     short loc_180021CB1
0x180021cac  mov     rdi, [rbx]
0x180021caf  jmp     short loc_180021D0F
0x180021cb1  mov     rdi, [rbx+rax*8+10h]
0x180021cb6  mov     esi, eax
0x180021cb8  test    rdi, rdi
0x180021cbb  jnz     short loc_180021D0F
0x180021cbd  mov     rcx, [rbx+618h]
0x180021cc4  call    PGetResourceDLL
0x180021cc9  test    rax, rax
0x180021ccc  jz      short loc_180021CEB
0x180021cce  mov     rdx, rax
0x180021cd1  mov     rcx, rbx
0x180021cd4  call    HLoadResourceDLL
0x180021cd9  mov     rdi, rax
0x180021cdc  test    rax, rax
0x180021cdf  jz      short loc_180021D0F
0x180021ce1  mov     [rbx+rsi*8+10h], rax
0x180021ce6  inc     dword ptr [rbx+8]
0x180021ce9  jmp     short loc_180021D0F
0x180021ceb  mov     ecx, 57h ; 'W'; dwErrCode
0x180021cf0  call    cs:__imp_SetLastError
0x180021cf7  nop     dword ptr [rax+rax+00h]
0x180021cfc  lea     rdx, aHgetmodulehand_0; "HGetModuleHandle:Can't find Resource DL"...
0x180021d03  lea     rcx, aHgetmodulehand; "HGetModuleHandle"
0x180021d0a  call    WriteDbgTraceWarning
0x180021d0f  mov     rax, rdi
0x180021d12  mov     rbx, [rsp+28h+arg_0]
0x180021d17  mov     rsi, [rsp+28h+arg_8]
0x180021d1c  add     rsp, 20h
0x180021d20  pop     rdi
0x180021d21  retn
```
