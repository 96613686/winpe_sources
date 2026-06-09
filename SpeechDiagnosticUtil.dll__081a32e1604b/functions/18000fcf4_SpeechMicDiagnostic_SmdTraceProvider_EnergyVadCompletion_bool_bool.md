# SpeechMicDiagnostic::SmdTraceProvider::EnergyVadCompletion<bool &>(bool &)

- ea: `0x18000fcf4`
- end: `0x18000fd6d`
- name: `??$EnergyVadCompletion@AEA_N@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEA_N@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ff2c`

## callees

- `0x180001640`
- `0x180002910`
- `0x1800068cc`
- `0x18000fcf4`

## pseudocode

```c
ULONG __fastcall SpeechMicDiagnostic::SmdTraceProvider::EnergyVadCompletion<bool &>(char *a1)
{
  ULONG *v2; // rcx
  ULONG result; // eax
  char v4; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+38h] [rbp-40h] BYREF
  char *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  v2 = (ULONG *)*((_QWORD *)SpeechMicDiagnostic::SmdTraceProvider::Instance() + 1);
  result = *v2;
  if ( *v2 > 5 )
  {
    v4 = *a1;
    v7 = 1;
    v6 = &v4;
    return tlgWriteTransfer_EventWriteTransfer((__int64)v2, (unsigned __int8 *)&unk_180015D18, 0, 0, 3u, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x18000fcf4  push    rbx
0x18000fcf6  sub     rsp, 70h
0x18000fcfa  mov     rax, cs:__security_cookie
0x18000fd01  xor     rax, rsp
0x18000fd04  mov     [rsp+78h+var_10], rax
0x18000fd09  mov     rbx, rcx
0x18000fd0c  call    ?Instance@SmdTraceProvider@SpeechMicDiagnostic@@KAPEAV12@XZ; SpeechMicDiagnostic::SmdTraceProvider::Instance(void)
0x18000fd11  mov     rcx, [rax+8]
0x18000fd15  mov     eax, [rcx]
0x18000fd17  cmp     eax, 5
0x18000fd1a  jbe     short loc_18000FD59
0x18000fd1c  mov     al, [rbx]
0x18000fd1e  lea     rdx, unk_180015D18
0x18000fd25  mov     [rsp+78h+var_48], al
0x18000fd29  xor     r9d, r9d
0x18000fd2c  lea     rax, [rsp+78h+var_48]
0x18000fd31  mov     [rsp+78h+var_18], 1
0x18000fd3a  mov     [rsp+78h+var_20], rax
0x18000fd3f  xor     r8d, r8d
0x18000fd42  lea     rax, [rsp+78h+var_40]
0x18000fd47  mov     [rsp+78h+var_50], rax
0x18000fd4c  mov     [rsp+78h+var_58], 3
0x18000fd54  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fd59  mov     rcx, [rsp+78h+var_10]
0x18000fd5e  xor     rcx, rsp; StackCookie
0x18000fd61  call    __security_check_cookie
0x18000fd66  add     rsp, 70h
0x18000fd6a  pop     rbx
0x18000fd6b  retn
```
