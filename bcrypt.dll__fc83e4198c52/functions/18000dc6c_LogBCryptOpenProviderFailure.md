# _LogBCryptOpenProviderFailure

- ea: `0x18000dc6c`
- end: `0x18000dc9c`
- name: `_LogBCryptOpenProviderFailure`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800070d0`

## callees

- `0x18000dc6c`
- `0x18000dca4`

## pseudocode

```c
__int64 __fastcall LogBCryptOpenProviderFailure(const wchar_t *a1, const wchar_t *a2, char a3, char a4, char a5)
{
  __int64 result; // rax

  if ( (Microsoft_Windows_Crypto_BCryptEnableBits & 1) != 0 )
    return McTemplateU0zzqdq_USE_EtwEventWrite((__int64)a1, (__int64)a2, a1, a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x18000dc6c  sub     rsp, 48h
0x18000dc70  test    cs:Microsoft_Windows_Crypto_BCryptEnableBits, 1
0x18000dc77  jz      short loc_18000DC96
0x18000dc79  mov     eax, [rsp+48h+arg_20]
0x18000dc7d  mov     [rsp+48h+var_18], eax
0x18000dc81  mov     [rsp+48h+var_20], r9d
0x18000dc86  mov     r9, rdx
0x18000dc89  mov     [rsp+48h+var_28], r8d
0x18000dc8e  mov     r8, rcx
0x18000dc91  call    McTemplateU0zzqdq_USE_EtwEventWrite
0x18000dc96  add     rsp, 48h
0x18000dc9a  retn
```
