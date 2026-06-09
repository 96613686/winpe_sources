# IncomingMessageRegistrationEvent::FreeEaEventHandle(void *)

- ea: `0x180009b70`
- end: `0x180009b9b`
- name: `?FreeEaEventHandle@IncomingMessageRegistrationEvent@@CAXPEAX@Z`
- size: `43`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009aec`
- `0x180009e58`

## callees

- `0x180009b70`
- `0x180009bc4`

## import_xrefs

- `EventAggregation!EaDeleteAggregation` at `0x180009b79`
- `EventAggregation!EaDeleteAggregation` at `0x180009b79`

## pseudocode

```c
void __fastcall IncomingMessageRegistrationEvent::FreeEaEventHandle(void *a1)
{
  int v1; // eax
  __int64 v2; // r8

  if ( a1 )
  {
    v1 = EaDeleteAggregation();
    if ( v1 < 0 )
      Log_HREvent_5(v1 | 0x10000000u, 0, v2, 185);
  }
}

```

## disassembly

```asm
0x180009b70  sub     rsp, 38h
0x180009b74  test    rcx, rcx
0x180009b77  jz      short loc_180009B96
0x180009b79  call    cs:__imp_EaDeleteAggregation
0x180009b7f  test    eax, eax
0x180009b81  jns     short loc_180009B96
0x180009b83  bts     eax, 1Ch
0x180009b87  xor     edx, edx
0x180009b89  mov     ecx, eax
0x180009b8b  mov     r9d, 0B9h
0x180009b91  call    Log_HREvent_5
0x180009b96  add     rsp, 38h
0x180009b9a  retn
```
