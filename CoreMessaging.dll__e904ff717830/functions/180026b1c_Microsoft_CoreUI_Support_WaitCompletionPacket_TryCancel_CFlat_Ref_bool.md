# Microsoft::CoreUI::Support::WaitCompletionPacket::TryCancel(CFlat::Ref<bool>)

- ea: `0x180026b1c`
- end: `0x180026bc9`
- name: `?TryCancel@WaitCompletionPacket@Support@CoreUI@Microsoft@@QEAA_NU?$Ref@_N@CFlat@@@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026a90`
- `0x18005b460`

## callees

- `0x180026b1c`
- `0x18008f3cc`
- `0x1800b9f24`

## import_xrefs

- `ntdll!NtCancelWaitCompletionPacket` at `0x180026b30`
- `ntdll!NtCancelWaitCompletionPacket` at `0x180026b57`
- `ntdll!NtCancelWaitCompletionPacket` at `0x180026b30`
- `ntdll!NtCancelWaitCompletionPacket` at `0x180026b57`

## pseudocode

```c
char __fastcall Microsoft::CoreUI::Support::WaitCompletionPacket::TryCancel(_QWORD *a1, char *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  int v6; // r9d
  int v7; // eax
  bool v8; // di
  char v9; // di

  v4 = NtCancelWaitCompletionPacket(*a1, 0);
  v6 = v4;
  if ( v4 == -1073741536 )
  {
    *a2 = 1;
LABEL_11:
    v8 = 1;
    goto LABEL_6;
  }
  if ( !v4 )
  {
    *a2 = 0;
    v8 = 0;
    goto LABEL_6;
  }
  if ( v4 != 259 )
    Cn::FailFast::ForNtStatus(v4);
  *a2 = 1;
  LOBYTE(v5) = 1;
  v7 = NtCancelWaitCompletionPacket(*a1, v5);
  v6 = v7;
  if ( v7 == 259 )
  {
    v6 = -1073741536;
    goto LABEL_11;
  }
  v8 = v7 == -1073741536;
  if ( v7 && v7 != -1073741536 )
    Cn::FailFast::ForNtStatus(v7);
LABEL_6:
  v9 = !v8;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 0x200) != 0 )
    McTemplateU0pqtt_EventWriteTransfer((unsigned __int8)*a2, v5, *a1, v6, *a2, v9);
  return v9;
}

```

## disassembly

```asm
0x180026b1c  push    rbx
0x180026b1e  push    rbp
0x180026b1f  push    rsi
0x180026b20  push    rdi
0x180026b21  sub     rsp, 38h
0x180026b25  mov     rbx, rdx
0x180026b28  mov     rsi, rcx
0x180026b2b  mov     rcx, [rcx]
0x180026b2e  xor     edx, edx
0x180026b30  call    cs:__imp_NtCancelWaitCompletionPacket
0x180026b36  mov     ebp, 0C0000120h
0x180026b3b  mov     r9d, eax
0x180026b3e  cmp     eax, ebp
0x180026b40  jz      short loc_180026B8F
0x180026b42  test    eax, eax
0x180026b44  jz      short loc_180026B87
0x180026b46  mov     edi, 103h
0x180026b4b  cmp     eax, edi
0x180026b4d  jnz     short loc_180026B97
0x180026b4f  mov     byte ptr [rbx], 1
0x180026b52  mov     dl, 1
0x180026b54  mov     rcx, [rsi]
0x180026b57  call    cs:__imp_NtCancelWaitCompletionPacket
0x180026b5d  mov     r9d, eax
0x180026b60  cmp     eax, edi
0x180026b62  jz      short loc_180026B9F
0x180026b64  cmp     eax, ebp
0x180026b66  setz    dil
0x180026b6a  test    eax, eax
0x180026b6c  jnz     short loc_180026BA4
0x180026b6e  xor     dil, 1
0x180026b72  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits+1, 2
0x180026b79  jnz     short loc_180026BB0
0x180026b7b  mov     al, dil
0x180026b7e  add     rsp, 38h
0x180026b82  pop     rdi
0x180026b83  pop     rsi
0x180026b84  pop     rbp
0x180026b85  pop     rbx
0x180026b86  retn
0x180026b87  mov     byte ptr [rbx], 0
0x180026b8a  xor     dil, dil
0x180026b8d  jmp     short loc_180026B6E
0x180026b8f  mov     byte ptr [rbx], 1
0x180026b92  mov     dil, 1
0x180026b95  jmp     short loc_180026B6E
0x180026b97  mov     ecx, eax; int
0x180026b99  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
0x180026b9f  mov     r9d, ebp
0x180026ba2  jmp     short loc_180026B92
0x180026ba4  cmp     eax, ebp
0x180026ba6  jz      short loc_180026B6E
0x180026ba8  mov     ecx, eax; int
0x180026baa  call    ?ForNtStatus@FailFast@Cn@@SAXH@Z; Cn::FailFast::ForNtStatus(int)
0x180026bb0  movzx   ecx, byte ptr [rbx]
0x180026bb3  mov     r8, [rsi]
0x180026bb6  movzx   eax, dil
0x180026bba  mov     [rsp+58h+var_30], eax
0x180026bbe  mov     [rsp+58h+var_38], ecx
0x180026bc2  call    McTemplateU0pqtt_EventWriteTransfer
0x180026bc7  jmp     short loc_180026B7B
```
