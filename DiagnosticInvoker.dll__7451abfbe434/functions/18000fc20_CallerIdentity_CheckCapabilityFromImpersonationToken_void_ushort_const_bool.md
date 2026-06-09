# CallerIdentity::CheckCapabilityFromImpersonationToken(void *,ushort const *,bool *)

- ea: `0x18000fc20`
- end: `0x18000fc6d`
- name: `?CheckCapabilityFromImpersonationToken@CallerIdentity@@YAJPEAXPEBGPEA_N@Z`
- size: `77`
- prototype: `int __fastcall(CallerIdentity *this, void *, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fc74`

## callees

- `0x18000fc20`
- `0x18000fd50`

## import_xrefs

- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000fc42`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18000fc42`

## pseudocode

```c
int __fastcall CallerIdentity::CheckCapabilityFromImpersonationToken(
        CallerIdentity *this,
        void *a2,
        unsigned __int16 *a3,
        bool *a4)
{
  int v5; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v11; // [rsp+38h] [rbp+10h] BYREF

  v11 = a2;
  *(_BYTE *)a3 = 0;
  LOBYTE(v11) = 0;
  v5 = CapabilityCheck(this, L"diagnostics", &v11, a4);
  if ( v5 < 0 )
    return wil::details::in1diag3::Return_NtStatus(retaddr, v6, v7, (const char *)(unsigned int)v5, v9);
  *(_BYTE *)a3 = (_BYTE)v11 != 0;
  return 0;
}

```

## disassembly

```asm
0x18000fc20  mov     [rsp+arg_8], rdx
0x18000fc25  push    rbx; int
0x18000fc26  sub     rsp, 20h
0x18000fc2a  mov     rbx, r8
0x18000fc2d  mov     byte ptr [r8], 0
0x18000fc31  lea     r8, [rsp+28h+arg_8]
0x18000fc36  mov     byte ptr [rsp+28h+arg_8], 0
0x18000fc3b  lea     rdx, aDiagnostics; "diagnostics"
0x18000fc42  call    cs:__imp_CapabilityCheck
0x18000fc48  test    eax, eax
0x18000fc4a  jns     short loc_18000FC5B
0x18000fc4c  mov     rcx, [rsp+28h]; this
0x18000fc51  mov     r9d, eax; char *
0x18000fc54  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000fc59  jmp     short loc_18000FC67
0x18000fc5b  cmp     byte ptr [rsp+28h+arg_8], 0
0x18000fc60  setnz   al
0x18000fc63  mov     [rbx], al
0x18000fc65  xor     eax, eax
0x18000fc67  add     rsp, 20h
0x18000fc6b  pop     rbx
0x18000fc6c  retn
```
