# DevUtilsMarkDeviceForReinstall

- ea: `0x140027670`
- end: `0x1400276ef`
- name: `DevUtilsMarkDeviceForReinstall`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140011a78`
- `0x1400187a0`
- `0x14001c718`
- `0x14001e944`

## callees

- `0x140027124`
- `0x140027670`
- `0x1400276f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400276b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400276b6`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400276d7`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400276d7`

## string_xrefs

- `0x1400276bc`: `Unable to mark device for reinstall. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall DevUtilsMarkDeviceForReinstall(__int64 a1, __int64 a2)
{
  DWORD LastError; // ebx
  unsigned int v4; // edi
  char v5; // dl
  int v7; // [rsp+50h] [rbp+18h] BYREF

  LastError = 0;
  v7 = 0;
  v4 = a1;
  if ( (unsigned int)DevUtilsGetConfigFlags(a1, &v7) )
  {
    v5 = v7;
  }
  else
  {
    v5 = 0;
    v7 = 0;
  }
  if ( (v5 & 0x20) == 0 && !(unsigned int)DevUtilsSetConfigFlags(v4) )
  {
    LastError = GetLastError();
    DevRtlWriteTextLog(a2, 512, 2, "Unable to mark device for reinstall. Error = 0x%08X", LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x140027670  mov     rax, rsp
0x140027673  mov     [rax+8], rbx
0x140027677  mov     [rax+10h], rsi
0x14002767b  push    rdi
0x14002767c  sub     rsp, 30h
0x140027680  mov     rsi, rdx
0x140027683  xor     ebx, ebx
0x140027685  lea     rdx, [rax+18h]
0x140027689  mov     [rax+18h], ebx
0x14002768c  mov     edi, ecx
0x14002768e  call    DevUtilsGetConfigFlags
0x140027693  test    eax, eax
0x140027695  jnz     short loc_14002769F
0x140027697  xor     edx, edx
0x140027699  mov     [rsp+38h+arg_10], edx
0x14002769d  jmp     short loc_1400276A3
0x14002769f  mov     edx, [rsp+38h+arg_10]
0x1400276a3  test    dl, 20h
0x1400276a6  jnz     short loc_1400276DD
0x1400276a8  or      edx, 20h
0x1400276ab  mov     ecx, edi
0x1400276ad  call    DevUtilsSetConfigFlags
0x1400276b2  test    eax, eax
0x1400276b4  jnz     short loc_1400276DD
0x1400276b6  call    cs:__imp_GetLastError
0x1400276bc  lea     r9, aUnableToMarkDe_0; "Unable to mark device for reinstall. Er"...
0x1400276c3  mov     edx, 200h
0x1400276c8  mov     r8d, 2
0x1400276ce  mov     [rsp+38h+var_18], eax
0x1400276d2  mov     rcx, rsi
0x1400276d5  mov     ebx, eax
0x1400276d7  call    cs:__imp_DevRtlWriteTextLog
0x1400276dd  mov     rsi, [rsp+38h+arg_8]
0x1400276e2  mov     eax, ebx
0x1400276e4  mov     rbx, [rsp+38h+arg_0]
0x1400276e9  add     rsp, 30h
0x1400276ed  pop     rdi
0x1400276ee  retn
```
