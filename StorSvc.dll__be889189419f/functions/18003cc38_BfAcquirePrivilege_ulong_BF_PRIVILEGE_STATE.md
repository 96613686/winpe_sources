# BfAcquirePrivilege(ulong,_BF_PRIVILEGE_STATE *)

- ea: `0x18003cc38`
- end: `0x18003ccd7`
- name: `?BfAcquirePrivilege@@YAJKPEAU_BF_PRIVILEGE_STATE@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned int, struct _BF_PRIVILEGE_STATE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003cae4`

## callees

- `0x18003cc38`
- `0x18003cce0`

## import_xrefs

- `ntdll!RtlImpersonateSelf` at `0x18003cc69`
- `ntdll!RtlImpersonateSelf` at `0x18003cc69`
- `ntdll!NtSetInformationThread` at `0x18003ccad`
- `ntdll!NtSetInformationThread` at `0x18003ccad`

## pseudocode

```c
NTSTATUS __fastcall BfAcquirePrivilege(int a1, struct _BF_PRIVILEGE_STATE *a2)
{
  char v3; // bl
  NTSTATUS result; // eax
  int v5; // esi
  int v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp+18h] BYREF

  v6 = a1;
  LOBYTE(v6) = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    result = RtlImpersonateSelf(SecurityImpersonation);
    if ( result < 0 )
      return result;
  }
  v5 = BfAdjustPrivilege(0x16u, 1, (bool *)&v6);
  if ( v5 >= 0 )
  {
    *((_BYTE *)a2 + 4) = v6;
    *((_BYTE *)a2 + 5) = v3;
    *(_DWORD *)a2 = 22;
  }
  else if ( !v3 )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  return v5;
}

```

## disassembly

```asm
0x18003cc38  mov     rax, rsp
0x18003cc3b  mov     [rax+10h], rbx
0x18003cc3f  mov     [rax+20h], rsi
0x18003cc43  mov     [rax+8], ecx
0x18003cc46  push    rdi
0x18003cc47  sub     rsp, 20h
0x18003cc4b  mov     byte ptr [rax+8], 0
0x18003cc4f  mov     rdi, rdx
0x18003cc52  mov     eax, gs:179Ch
0x18003cc5a  test    eax, eax
0x18003cc5c  jz      short loc_18003CC62
0x18003cc5e  mov     bl, 1
0x18003cc60  jmp     short loc_18003CC73
0x18003cc62  mov     ecx, 2; ImpersonationLevel
0x18003cc67  xor     bl, bl
0x18003cc69  call    cs:__imp_RtlImpersonateSelf
0x18003cc6f  test    eax, eax
0x18003cc71  js      short loc_18003CCC7
0x18003cc73  lea     r8, [rsp+28h+arg_0]; unsigned __int8 *
0x18003cc78  mov     dl, 1; unsigned __int8
0x18003cc7a  mov     ecx, 16h; unsigned int
0x18003cc7f  call    ?BfAdjustPrivilege@@YAJKEPEAE@Z; BfAdjustPrivilege(ulong,uchar,uchar *)
0x18003cc84  mov     esi, eax
0x18003cc86  test    eax, eax
0x18003cc88  jns     short loc_18003CCB5
0x18003cc8a  test    bl, bl
0x18003cc8c  jnz     short loc_18003CCC5
0x18003cc8e  mov     r9d, 8; ThreadInformationLength
0x18003cc94  mov     [rsp+28h+ThreadInformation], 0
0x18003cc9d  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x18003cca2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18003cca9  lea     edx, [r9-3]; ThreadInformationClass
0x18003ccad  call    cs:__imp_NtSetInformationThread
0x18003ccb3  jmp     short loc_18003CCC5
0x18003ccb5  mov     al, byte ptr [rsp+28h+arg_0]
0x18003ccb9  mov     [rdi+4], al
0x18003ccbc  mov     [rdi+5], bl
0x18003ccbf  mov     dword ptr [rdi], 16h
0x18003ccc5  mov     eax, esi
0x18003ccc7  mov     rbx, [rsp+28h+arg_8]
0x18003cccc  mov     rsi, [rsp+28h+arg_18]
0x18003ccd1  add     rsp, 20h
0x18003ccd5  pop     rdi
0x18003ccd6  retn
```
