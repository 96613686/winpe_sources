# CallerIdentity::CheckCapabilityFromImpersonationToken(void *,ushort const *,bool *)

- ea: `0x18001aff4`
- end: `0x18001b036`
- name: `?CheckCapabilityFromImpersonationToken@CallerIdentity@@YAJPEAXPEBGPEA_N@Z`
- size: `66`
- prototype: `int(CallerIdentity *__hidden this, void *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800141d8`

## callees

- `0x18001aff4`
- `0x18001b03c`

## import_xrefs

- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001b00b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001b00b`

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
  char v11; // [rsp+40h] [rbp+18h] BYREF

  *(_BYTE *)a3 = 0;
  v11 = 0;
  v5 = CapabilityCheck(this, a2, &v11, a4);
  if ( v5 < 0 )
    return wil::details::in1diag3::Return_NtStatus(retaddr, v6, v7, (const char *)(unsigned int)v5, v9);
  *(_BYTE *)a3 = v11 != 0;
  return 0;
}

```

## disassembly

```asm
0x18001aff4  push    rbx; int
0x18001aff6  sub     rsp, 20h
0x18001affa  mov     rbx, r8
0x18001affd  mov     byte ptr [r8], 0
0x18001b001  lea     r8, [rsp+28h+arg_10]
0x18001b006  mov     [rsp+28h+arg_10], 0
0x18001b00b  call    cs:__imp_CapabilityCheck
0x18001b011  test    eax, eax
0x18001b013  jns     short loc_18001B024
0x18001b015  mov     rcx, [rsp+28h]; this
0x18001b01a  mov     r9d, eax; char *
0x18001b01d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b022  jmp     short loc_18001B030
0x18001b024  cmp     [rsp+28h+arg_10], 0
0x18001b029  setnz   al
0x18001b02c  mov     [rbx], al
0x18001b02e  xor     eax, eax
0x18001b030  add     rsp, 20h
0x18001b034  pop     rbx
0x18001b035  retn
```
