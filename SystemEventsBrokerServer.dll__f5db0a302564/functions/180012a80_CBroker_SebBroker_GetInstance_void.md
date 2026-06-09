# CBroker::SebBroker::GetInstance(void)

- ea: `0x180012a80`
- end: `0x180012b1a`
- name: `?GetInstance@SebBroker@CBroker@@SA?AV?$shared_ptr@VSebBroker@CBroker@@@std@@XZ`
- size: `154`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800197fc`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001fd50`
- `0x18001fea0`
- `0x180020bac`

## callees

- `0x180012a80`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012abc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012abc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012ace`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012ace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ac2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012ac2`

## pseudocode

```c
_QWORD *__fastcall CBroker::SebBroker::GetInstance(_QWORD *a1)
{
  CBroker::SebBroker *v1; // rdi
  _QWORD *result; // rax
  char *v4; // rsi
  char v5; // di
  __int64 v6; // rcx

  v1 = CBroker::SebBroker::Instance;
  if ( CBroker::SebBroker::Instance
    && (v4 = (char *)CBroker::SebBroker::Instance + 8,
        RtlAcquireSRWLockExclusive((char *)CBroker::SebBroker::Instance + 8),
        GetCurrentThreadId(),
        v5 = *(_BYTE *)v1,
        RtlReleaseSRWLockExclusive(v4),
        v5) )
  {
    v6 = (__int64)*(&CBroker::SebBroker::Instance + 1);
    *a1 = 0;
    a1[1] = 0;
    if ( v6 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
      v6 = (__int64)*(&CBroker::SebBroker::Instance + 1);
    }
    *a1 = CBroker::SebBroker::Instance;
    result = a1;
    a1[1] = v6;
  }
  else
  {
    a1[1] = 0;
    *a1 = 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180012a80  mov     [rsp+arg_8], rbx
0x180012a85  push    rdi
0x180012a86  sub     rsp, 20h
0x180012a8a  mov     rdi, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180012a91  mov     rbx, rcx
0x180012a94  test    rdi, rdi
0x180012a97  jnz     short loc_180012AB0
0x180012a99  xor     eax, eax
0x180012a9b  mov     [rbx+8], rax
0x180012a9f  mov     [rbx], rax
0x180012aa2  mov     rax, rbx
0x180012aa5  mov     rbx, [rsp+28h+arg_8]
0x180012aaa  add     rsp, 20h
0x180012aae  pop     rdi
0x180012aaf  retn
0x180012ab0  mov     [rsp+28h+arg_0], rsi
0x180012ab5  lea     rsi, [rdi+8]
0x180012ab9  mov     rcx, rsi
0x180012abc  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012ac2  call    cs:__imp_GetCurrentThreadId
0x180012ac8  movzx   edi, byte ptr [rdi]
0x180012acb  mov     rcx, rsi
0x180012ace  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012ad4  mov     rsi, [rsp+28h+arg_0]
0x180012ad9  test    dil, dil
0x180012adc  jz      short loc_180012A99
0x180012ade  mov     rcx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180012ae5  xor     eax, eax
0x180012ae7  mov     [rbx], rax
0x180012aea  mov     [rbx+8], rax
0x180012aee  test    rcx, rcx
0x180012af1  jz      short loc_180012AFE
0x180012af3  lock inc dword ptr [rcx+8]
0x180012af7  mov     rcx, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A+8; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180012afe  mov     rax, qword ptr cs:?Instance@SebBroker@CBroker@@0V?$shared_ptr@VSebBroker@CBroker@@@std@@A; std::shared_ptr<CBroker::SebBroker> CBroker::SebBroker::Instance
0x180012b05  mov     [rbx], rax
0x180012b08  mov     rax, rbx
0x180012b0b  mov     [rbx+8], rcx
0x180012b0f  mov     rbx, [rsp+28h+arg_8]
0x180012b14  add     rsp, 20h
0x180012b18  pop     rdi
0x180012b19  retn
```
