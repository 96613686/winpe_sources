# CryptXmlClose

- ea: `0x1800125a0`
- end: `0x1800125f8`
- name: `CryptXmlClose`
- size: `88`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004f60`
- `0x1800125a0`

## pseudocode

```c
HRESULT __stdcall CryptXmlClose(HCRYPTXML hCryptXml)
{
  HRESULT result; // eax
  __int64 v3; // rcx

  if ( !hCryptXml )
    return -2147024809;
  v3 = *((_QWORD *)hCryptXml + 10);
  if ( !v3 )
    return I_CryptXmlRelease((__int64)hCryptXml);
  result = 1;
  if ( *(_DWORD *)hCryptXml == 1145324610 && *(int *)(v3 + 72) < 0 )
  {
    I_CryptXmlRelease((__int64)hCryptXml);
    return I_CryptXmlRelease(*((_QWORD *)hCryptXml + 10));
  }
  return result;
}

```

## disassembly

```asm
0x1800125a0  push    rbx
0x1800125a2  sub     rsp, 20h
0x1800125a6  mov     rbx, rcx
0x1800125a9  test    rcx, rcx
0x1800125ac  jnz     short loc_1800125BA
0x1800125ae  mov     eax, 80070057h
0x1800125b3  add     rsp, 20h
0x1800125b7  pop     rbx
0x1800125b8  retn
0x1800125ba  mov     rcx, [rcx+50h]
0x1800125be  test    rcx, rcx
0x1800125c1  jnz     short loc_1800125C8
0x1800125c3  mov     rcx, rbx
0x1800125c6  jmp     short loc_1800125E7
0x1800125c8  cmp     dword ptr [rbx], 44444442h
0x1800125ce  mov     eax, 1
0x1800125d3  jnz     short loc_1800125F1
0x1800125d5  cmp     dword ptr [rcx+48h], 0
0x1800125d9  jge     short loc_1800125F1
0x1800125db  mov     rcx, rbx
0x1800125de  call    I_CryptXmlRelease
0x1800125e3  mov     rcx, [rbx+50h]
0x1800125e7  add     rsp, 20h
0x1800125eb  pop     rbx
0x1800125ec  jmp     I_CryptXmlRelease
0x1800125f1  add     rsp, 20h
0x1800125f5  pop     rbx
0x1800125f6  retn
```
