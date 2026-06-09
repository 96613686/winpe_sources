# IntroduceReader(ulong,ushort const *,ushort const *)

- ea: `0x180031df0`
- end: `0x180031f70`
- name: `?IntroduceReader@@YAXKPEBG0@Z`
- size: `384`
- prototype: `void __fastcall(ulong, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029f78`

## callees

- `0x180015690`
- `0x180017664`
- `0x1800176a8`
- `0x18001a328`
- `0x180031df0`
- `0x180031f78`
- `0x180032284`
- `0x180032308`
- `0x18003261b`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180031e63`
- `msvcrt!wcspbrk` at `0x180031e63`

## string_xrefs

- `0x180031ecd`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
void __fastcall IntroduceReader(ulong a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v5; // ecx
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // r9d
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // r8
  unsigned int v10; // r9d
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+30h] [rbp-11h]
  HKEY phkResult[5]; // [rsp+38h] [rbp-9h] BYREF
  int v13; // [rsp+60h] [rbp+1Fh]
  _BYTE v14[48]; // [rsp+68h] [rbp+27h] BYREF
  ulong pExceptionObject; // [rsp+A8h] [rbp+67h] BYREF

  pExceptionObject = a1;
  phkResult[2] = (HKEY)&CBuffer::`vftable';
  phkResult[3] = 0;
  phkResult[4] = 0;
  phkResult[0] = 0;
  v13 = 1010;
  if ( !*a2 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  if ( wcspbrk(a2, L"\\?") )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  v5 = 0;
  while ( LODWORD(qword_180042120[2 * v5]) != 2 )
  {
    if ( ++v5 >= 2 )
    {
      pExceptionObject = -2146435055;
      throw &pExceptionObject;
    }
  }
  CRegistry::Open(
    (DWORD *)phkResult,
    (HKEY)qword_180042120[2 * v5 + 1],
    L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
    4u,
    0);
  CRegistry::Status((CRegistry *)phkResult, 0);
  CRegistry::CRegistry((CRegistry *)v14, phkResult[0], a2, 2u, 0, v11);
  if ( CRegistry::GetDisposition((CRegistry *)v14) == 2 )
  {
    pExceptionObject = -2146435045;
    throw &pExceptionObject;
  }
  CRegistry::SetValue((CRegistry *)v14, v6, a3, v7);
  CRegistry::SetMultiStringValue((CRegistry *)v14, v8, v9, v10);
  CRegistry::~CRegistry((CRegistry *)v14);
  CRegistry::~CRegistry((CRegistry *)phkResult);
}

```

## disassembly

```asm
0x180031df0  mov     rax, rsp
0x180031df3  mov     [rax+10h], rbx
0x180031df7  mov     [rax+18h], rdi
0x180031dfb  mov     [rax+8], ecx
0x180031dfe  push    rbp
0x180031dff  lea     rbp, [rax-5Fh]
0x180031e03  sub     rsp, 90h
0x180031e0a  mov     rdi, r8
0x180031e0d  mov     rbx, rdx
0x180031e10  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x180031e17  mov     [rbp+57h+var_50], rax
0x180031e1b  mov     [rbp+57h+var_48], 0
0x180031e23  mov     [rbp+57h+var_40], 0
0x180031e2b  mov     [rbp+57h+phkResult], 0
0x180031e33  mov     [rbp+57h+var_38], 3F2h
0x180031e3a  xor     eax, eax
0x180031e3c  cmp     ax, [rdx]
0x180031e3f  jnz     short loc_180031E59
0x180031e41  mov     [rbp+57h+pExceptionObject], 80100011h
0x180031e48  lea     rdx, _TI1K; pThrowInfo
0x180031e4f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031e53  call    _CxxThrowException_0
0x180031e59  lea     rdx, Control; "\\?"
0x180031e60  mov     rcx, rbx; String
0x180031e63  call    cs:__imp_wcspbrk
0x180031e69  test    rax, rax
0x180031e6c  jz      short loc_180031E86
0x180031e6e  mov     [rbp+57h+pExceptionObject], 80100011h
0x180031e75  lea     rdx, _TI1K; pThrowInfo
0x180031e7c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031e80  call    _CxxThrowException_0
0x180031e86  xor     ecx, ecx
0x180031e88  lea     r10, qword_180042120
0x180031e8f  mov     eax, ecx
0x180031e91  add     rax, rax
0x180031e94  cmp     dword ptr [r10+rax*8], 2
0x180031e99  jz      short loc_180031EBA
0x180031e9b  inc     ecx
0x180031e9d  cmp     ecx, 2
0x180031ea0  jb      short loc_180031E8F
0x180031ea2  mov     [rbp+57h+pExceptionObject], 80100011h
0x180031ea9  lea     rdx, _TI1K; pThrowInfo
0x180031eb0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031eb4  call    _CxxThrowException_0
0x180031eba  mov     edx, ecx
0x180031ebc  add     rdx, rdx
0x180031ebf  mov     [rsp+90h+dwOptions], 0; dwOptions
0x180031ec7  mov     r9d, 4; samDesired
0x180031ecd  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x180031ed4  mov     rdx, [r10+rdx*8+8]; hKey
0x180031ed9  lea     rcx, [rbp+57h+phkResult]; phkResult
0x180031edd  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x180031ee2  xor     edx, edx; int
0x180031ee4  lea     rcx, [rbp+57h+phkResult]; this
0x180031ee8  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x180031eed  mov     [rsp+90h+dwOptions], 0; DWORD
0x180031ef5  mov     r9d, 2; unsigned int
0x180031efb  mov     r8, rbx; unsigned __int16 *
0x180031efe  mov     rdx, [rbp+57h+phkResult]; HKEY
0x180031f02  lea     rcx, [rbp+57h+var_30]; this
0x180031f06  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x180031f0b  nop
0x180031f0c  lea     rcx, [rbp+57h+var_30]; this
0x180031f10  call    ?GetDisposition@CRegistry@@QEBAKXZ; CRegistry::GetDisposition(void)
0x180031f15  cmp     eax, 2
0x180031f18  jnz     short loc_180031F32
0x180031f1a  mov     [rbp+57h+pExceptionObject], 8010001Bh
0x180031f21  lea     rdx, _TI1K; pThrowInfo
0x180031f28  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031f2c  call    _CxxThrowException_0
0x180031f32  mov     r8, rdi; unsigned __int16 *
0x180031f35  lea     rcx, [rbp+57h+var_30]; this
0x180031f39  call    ?SetValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetValue(ushort const *,ushort const *,ulong)
0x180031f3e  lea     rcx, [rbp+57h+var_30]; this
0x180031f42  call    ?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)
0x180031f47  nop
0x180031f48  lea     rcx, [rbp+57h+var_30]; this
0x180031f4c  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180031f51  nop
0x180031f52  lea     rcx, [rbp+57h+phkResult]; this
0x180031f56  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180031f5b  lea     r11, [rsp+90h+var_s0]
0x180031f63  mov     rbx, [r11+18h]
0x180031f67  mov     rdi, [r11+20h]
0x180031f6b  mov     rsp, r11
0x180031f6e  pop     rbp
0x180031f6f  retn
```
