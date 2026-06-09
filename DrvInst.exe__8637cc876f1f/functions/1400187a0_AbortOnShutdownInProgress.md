# AbortOnShutdownInProgress

- ea: `0x1400187a0`
- end: `0x140018835`
- name: `AbortOnShutdownInProgress`
- size: `149`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140019148`

## callees

- `0x1400187a0`
- `0x140027670`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x1400187d8`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400187fe`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400187d8`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400187fe`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400187ac`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x1400187ac`

## string_xrefs

- `0x1400187c5`: `Detected system shutdown in progress, continuing device install...`
- `0x1400187e9`: `Detected system shutdown in progress, deferring device install...`

## pseudocode

```c
__int64 __fastcall AbortOnShutdownInProgress(unsigned int a1)
{
  __int64 ThreadLogToken; // rax
  unsigned int v3; // edi

  ThreadLogToken = DevRtlGetThreadLogToken();
  if ( g_BootCriticalDevice )
  {
    v3 = 0;
    if ( dword_140063FA4 )
      return v3;
    DevRtlWriteTextLog(ThreadLogToken, 1, 1048578, "Detected system shutdown in progress, continuing device install...");
  }
  else
  {
    if ( !dword_140063FA4 )
      DevRtlWriteTextLog(
        ThreadLogToken,
        1,
        1048578,
        "Detected system shutdown in progress, deferring device install...");
    v3 = 1;
  }
  if ( !dword_140063FA4 )
  {
    DevUtilsMarkDeviceForReinstall(a1, 1);
    dword_140063FA4 = 1;
  }
  return v3;
}

```

## disassembly

```asm
0x1400187a0  mov     [rsp+arg_0], rsi
0x1400187a5  push    rdi
0x1400187a6  sub     rsp, 20h
0x1400187aa  mov     esi, ecx
0x1400187ac  call    cs:__imp_DevRtlGetThreadLogToken
0x1400187b2  cmp     cs:g_BootCriticalDevice, 0
0x1400187b9  jz      short loc_1400187E0
0x1400187bb  xor     edi, edi
0x1400187bd  cmp     cs:dword_140063FA4, edi
0x1400187c3  jnz     short loc_140018828
0x1400187c5  lea     r9, aDetectedSystem_0; "Detected system shutdown in progress, c"...
0x1400187cc  mov     r8d, 100002h
0x1400187d2  lea     edx, [rdi+1]
0x1400187d5  mov     rcx, rax
0x1400187d8  call    cs:__imp_DevRtlWriteTextLog
0x1400187de  jmp     short loc_140018809
0x1400187e0  cmp     cs:dword_140063FA4, 0
0x1400187e7  jnz     short loc_140018804
0x1400187e9  lea     r9, aDetectedSystem; "Detected system shutdown in progress, d"...
0x1400187f0  mov     edx, 1
0x1400187f5  mov     r8d, 100002h
0x1400187fb  mov     rcx, rax
0x1400187fe  call    cs:__imp_DevRtlWriteTextLog
0x140018804  mov     edi, 1
0x140018809  cmp     cs:dword_140063FA4, 0
0x140018810  jnz     short loc_140018828
0x140018812  mov     edx, 1
0x140018817  mov     ecx, esi
0x140018819  call    DevUtilsMarkDeviceForReinstall
0x14001881e  mov     cs:dword_140063FA4, 1
0x140018828  mov     rsi, [rsp+28h+arg_0]
0x14001882d  mov     eax, edi
0x14001882f  add     rsp, 20h
0x140018833  pop     rdi
0x140018834  retn
```
