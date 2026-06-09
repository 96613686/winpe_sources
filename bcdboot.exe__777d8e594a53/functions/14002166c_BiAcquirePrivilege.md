# BiAcquirePrivilege

- ea: `0x14002166c`
- end: `0x1400216f6`
- name: `BiAcquirePrivilege`
- size: `138`
- prototype: `NTSTATUS __fastcall(unsigned int, __int64)`
- caller_count: `14`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001df18`
- `0x14001e648`
- `0x14001f570`
- `0x14001fe24`
- `0x1400218e4`
- `0x140023218`
- `0x140023448`
- `0x1400235bc`
- `0x140023824`
- `0x14002467c`
- `0x140024714`
- `0x14002483c`
- `0x140024a28`
- `0x140024b30`

## callees

- `0x14002166c`
- `0x1400216fc`

## import_xrefs

- `ntdll!RtlImpersonateSelf` at `0x140021696`
- `ntdll!RtlImpersonateSelf` at `0x140021696`
- `ntdll!NtSetInformationThread` at `0x1400216d7`
- `ntdll!NtSetInformationThread` at `0x1400216d7`

## pseudocode

```c
NTSTATUS __fastcall BiAcquirePrivilege(unsigned int a1, __int64 a2)
{
  ULONG IsImpersonating; // eax
  __int64 v3; // rdi
  char v5; // bl
  NTSTATUS result; // eax
  int v7; // esi
  __int64 ThreadInformation; // [rsp+60h] [rbp+18h] BYREF

  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  v3 = a2;
  LOBYTE(ThreadInformation) = 0;
  if ( IsImpersonating )
  {
    v5 = 1;
  }
  else
  {
    v5 = 0;
    result = RtlImpersonateSelf(SecurityImpersonation);
    if ( result < 0 )
      return result;
  }
  LOBYTE(a2) = 1;
  v7 = BiAdjustPrivilege(a1, a2, &ThreadInformation);
  if ( v7 >= 0 )
  {
    *(_BYTE *)(v3 + 4) = ThreadInformation;
    *(_BYTE *)(v3 + 5) = v5;
    *(_DWORD *)v3 = a1;
  }
  else if ( !v5 )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return v7;
}

```

## disassembly

```asm
0x14002166c  push    rbx
0x14002166e  push    rbp
0x14002166f  push    rsi
0x140021670  push    rdi
0x140021671  sub     rsp, 28h
0x140021675  mov     eax, gs:179Ch
0x14002167d  mov     rdi, rdx
0x140021680  mov     byte ptr [rsp+48h+ThreadInformation], 0
0x140021685  mov     ebp, ecx
0x140021687  test    eax, eax
0x140021689  jz      short loc_14002168F
0x14002168b  mov     bl, 1
0x14002168d  jmp     short loc_1400216A0
0x14002168f  mov     ecx, 2; ImpersonationLevel
0x140021694  xor     bl, bl
0x140021696  call    cs:__imp_RtlImpersonateSelf
0x14002169c  test    eax, eax
0x14002169e  js      short loc_1400216ED
0x1400216a0  lea     r8, [rsp+48h+ThreadInformation]
0x1400216a5  mov     dl, 1
0x1400216a7  mov     ecx, ebp
0x1400216a9  call    BiAdjustPrivilege
0x1400216ae  mov     esi, eax
0x1400216b0  test    eax, eax
0x1400216b2  jns     short loc_1400216DF
0x1400216b4  test    bl, bl
0x1400216b6  jnz     short loc_1400216EB
0x1400216b8  mov     r9d, 8; ThreadInformationLength
0x1400216be  mov     [rsp+48h+ThreadInformation], 0
0x1400216c7  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x1400216cc  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400216d3  lea     edx, [r9-3]; ThreadInformationClass
0x1400216d7  call    cs:__imp_NtSetInformationThread
0x1400216dd  jmp     short loc_1400216EB
0x1400216df  mov     al, byte ptr [rsp+48h+ThreadInformation]
0x1400216e3  mov     [rdi+4], al
0x1400216e6  mov     [rdi+5], bl
0x1400216e9  mov     [rdi], ebp
0x1400216eb  mov     eax, esi
0x1400216ed  add     rsp, 28h
0x1400216f1  pop     rdi
0x1400216f2  pop     rsi
0x1400216f3  pop     rbp
0x1400216f4  pop     rbx
0x1400216f5  retn
```
