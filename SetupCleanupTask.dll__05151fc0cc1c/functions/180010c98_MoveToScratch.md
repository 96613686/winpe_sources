# MoveToScratch

- ea: `0x180010c98`
- end: `0x180010d75`
- name: `MoveToScratch`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180010950`
- `0x180010ae0`

## callees

- `0x18000638c`
- `0x180010c98`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cec`
- `WDSCORE!CurrentIP` at `0x180010cf4`
- `WDSCORE!CurrentIP` at `0x180010cf4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010d5d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010d5d`

## string_xrefs

- `0x180010d46`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180010d1c`: `MoveToScratch`
- `0x180010cfd`: `MoveToScratch: Failed to move [%s] to Scratch Reserve. hr = 0x%08X`

## pseudocode

```c
__int64 __fastcall MoveToScratch(const char *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 result; // rax
  unsigned int v5; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax

  if ( !a2 || !a1 )
    return 2147942487LL;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v3 + 88LL))(v3, 6, 6, a1);
  v5 = result;
  if ( (int)result < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(0x2000000, "MoveToScratch: Failed to move [%s] to Scratch Reserve. hr = 0x%08X", a1, v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      683,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"MoveToScratch",
      v7,
      LastError,
      0,
      0);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180010c98  push    rbx
0x180010c9a  push    rbp
0x180010c9b  push    rsi
0x180010c9c  push    rdi
0x180010c9d  sub     rsp, 68h
0x180010ca1  mov     rsi, rcx
0x180010ca4  test    rdx, rdx
0x180010ca7  jz      loc_180010D67
0x180010cad  test    rcx, rcx
0x180010cb0  jz      loc_180010D67
0x180010cb6  mov     rax, [rdx]
0x180010cb9  mov     rcx, rdx
0x180010cbc  mov     rax, [rax+8]
0x180010cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc5  mov     r10, rax
0x180010cc8  mov     edx, 6
0x180010ccd  mov     r9, rsi
0x180010cd0  mov     r8d, edx
0x180010cd3  mov     rcx, [rax]
0x180010cd6  mov     rax, [rcx+58h]
0x180010cda  mov     rcx, r10
0x180010cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce2  mov     ebp, eax
0x180010ce4  test    eax, eax
0x180010ce6  jns     loc_180010D6C
0x180010cec  call    cs:__imp_GetLastError
0x180010cf2  mov     edi, eax
0x180010cf4  call    cs:__imp_CurrentIP
0x180010cfa  mov     r9d, ebp
0x180010cfd  lea     rdx, aMovetoscratchF; "MoveToScratch: Failed to move [%s] to S"...
0x180010d04  mov     r8, rsi
0x180010d07  mov     ecx, 2000000h; unsigned int
0x180010d0c  mov     rbx, rax
0x180010d0f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180010d14  mov     [rsp+88h+var_38], 0
0x180010d1c  lea     rcx, aMovetoscratch; "MoveToScratch"
0x180010d23  mov     [rsp+88h+var_40], 0
0x180010d2c  lea     r8, aD_0; "D"
0x180010d33  mov     [rsp+88h+var_48], edi
0x180010d37  xor     r9d, r9d
0x180010d3a  mov     [rsp+88h+var_50], rbx
0x180010d3f  xor     edx, edx
0x180010d41  mov     [rsp+88h+var_58], rcx
0x180010d46  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180010d4d  mov     [rsp+88h+var_60], rcx
0x180010d52  mov     rcx, rax
0x180010d55  mov     [rsp+88h+var_68], 2ABh
0x180010d5d  call    cs:__imp_WdsSetupLogMessageW
0x180010d63  mov     eax, ebp
0x180010d65  jmp     short loc_180010D6C
0x180010d67  mov     eax, 80070057h
0x180010d6c  add     rsp, 68h
0x180010d70  pop     rdi
0x180010d71  pop     rsi
0x180010d72  pop     rbp
0x180010d73  pop     rbx
0x180010d74  retn
```
