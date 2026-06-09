# UnconfigureRootDevices

- ea: `0x1400147d4`
- end: `0x140014859`
- name: `UnconfigureRootDevices`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140013220`

## callees

- `0x1400147d4`
- `0x1400149e0`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x14001481f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001481f`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400147e9`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400147e9`
- `drvstore!DriverStoreUnreflectW` at `0x1400147fe`
- `drvstore!DriverStoreUnreflectW` at `0x1400147fe`

## string_xrefs

- `0x14001480a`: `Unable to unconfigure driver package. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall UnconfigureRootDevices(__int64 a1, WCHAR *a2)
{
  __int64 ThreadLogToken; // rsi
  __int64 result; // rax

  ThreadLogToken = DevRtlGetThreadLogToken();
  result = DriverStoreUnreflectW(0, a1, 32);
  if ( (_DWORD)result )
    result = DevRtlWriteTextLog(ThreadLogToken, 1, 2, "Unable to unconfigure driver package. Error = 0x%08X", result);
  while ( *a2 )
  {
    UninstallRootDevice(a2);
    result = -1;
    do
      ++result;
    while ( a2[result] );
    a2 += result + 1;
  }
  return result;
}

```

## disassembly

```asm
0x1400147d4  mov     [rsp+arg_0], rbx
0x1400147d9  mov     [rsp+arg_8], rsi
0x1400147de  push    rdi
0x1400147df  sub     rsp, 30h
0x1400147e3  mov     rdi, rdx
0x1400147e6  mov     rbx, rcx
0x1400147e9  call    cs:__imp_DevRtlGetThreadLogToken
0x1400147ef  xor     r9d, r9d
0x1400147f2  mov     rdx, rbx
0x1400147f5  xor     ecx, ecx
0x1400147f7  mov     rsi, rax
0x1400147fa  lea     r8d, [r9+20h]
0x1400147fe  call    cs:__imp_DriverStoreUnreflectW
0x140014804  xor     ebx, ebx
0x140014806  test    eax, eax
0x140014808  jz      short loc_140014844
0x14001480a  lea     r9, aUnableToUnconf; "Unable to unconfigure driver package. E"...
0x140014811  mov     [rsp+38h+var_18], eax
0x140014815  lea     edx, [rbx+1]
0x140014818  mov     rcx, rsi
0x14001481b  lea     r8d, [rbx+2]
0x14001481f  call    cs:__imp_DevRtlWriteTextLog
0x140014825  jmp     short loc_140014844
0x140014827  mov     rcx, rdi; int
0x14001482a  call    UninstallRootDevice
0x14001482f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014833  inc     rax
0x140014836  cmp     [rdi+rax*2], bx
0x14001483a  jnz     short loc_140014833
0x14001483c  lea     rdi, [rdi+rax*2]
0x140014840  add     rdi, 2
0x140014844  cmp     [rdi], bx
0x140014847  jnz     short loc_140014827
0x140014849  mov     rbx, [rsp+38h+arg_0]
0x14001484e  mov     rsi, [rsp+38h+arg_8]
0x140014853  add     rsp, 30h
0x140014857  pop     rdi
0x140014858  retn
```
