# IntroduceReader(ulong,ushort const *,ushort const *)

- ea: `0x18002b0ec`
- end: `0x18002b269`
- name: `?IntroduceReader@@YAXKPEBG0@Z`
- size: `381`
- prototype: `void(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025b30`
- `0x180027c50`

## callees

- `0x180002180`
- `0x180002220`
- `0x180013c90`
- `0x180015ac0`
- `0x18002a600`
- `0x18002a65c`
- `0x18002a6dc`
- `0x18002b0ec`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18002b158`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18002b158`

## string_xrefs

- `0x18002b239`: `SCard$DefaultReaders`
- `0x18002b1c1`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall IntroduceReader(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // ecx
  ulong v7; // r9d
  const unsigned __int16 *v8; // rdx
  ulong v9; // r9d
  HKEY hKey[5]; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+58h] [rbp-1h]
  _DWORD phkResult[20]; // [rsp+60h] [rbp+7h] BYREF
  ulong pExceptionObject; // [rsp+C8h] [rbp+6Fh] BYREF

  hKey[2] = (HKEY)&CBuffer::`vftable';
  hKey[3] = 0;
  hKey[4] = 0;
  hKey[0] = 0;
  v11 = 1010;
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
  v6 = 0;
  while ( dword_180039DB0[4 * v6] != a1 )
  {
    if ( (unsigned int)++v6 >= 2 )
    {
      pExceptionObject = -2146435055;
      throw &pExceptionObject;
    }
  }
  CRegistry::Open(
    hKey,
    *(HKEY *)&dword_180039DB0[4 * v6 + 2],
    L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
    4u,
    0);
  CRegistry::Status((CRegistry *)hKey, 0);
  CRegistry::CRegistry(phkResult, hKey[0], a2, 2u, 0);
  if ( CRegistry::GetDisposition((CRegistry *)phkResult) == 2 )
  {
    pExceptionObject = -2146435045;
    throw &pExceptionObject;
  }
  CRegistry::SetValue((CRegistry *)phkResult, L"Device", a3, v7);
  CRegistry::SetMultiStringValue((CRegistry *)phkResult, v8, L"SCard$DefaultReaders", v9);
  CRegistry::~CRegistry((CRegistry *)phkResult);
  CRegistry::~CRegistry((CRegistry *)hKey);
}

```

## disassembly

```asm
0x18002b0ec  push    rbp
0x18002b0ee  push    rbx
0x18002b0ef  push    rsi
0x18002b0f0  push    rdi
0x18002b0f1  lea     rbp, [rsp-3Fh]
0x18002b0f6  sub     rsp, 98h
0x18002b0fd  mov     rsi, r8
0x18002b100  mov     rbx, rdx
0x18002b103  mov     edi, ecx
0x18002b105  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002b10c  mov     [rbp+57h+var_70], rax
0x18002b110  mov     [rbp+57h+var_68], 0
0x18002b118  mov     [rbp+57h+var_60], 0
0x18002b120  mov     [rbp+57h+hKey], 0
0x18002b128  mov     [rbp+57h+var_58], 3F2h
0x18002b12f  xor     eax, eax
0x18002b131  cmp     ax, [rdx]
0x18002b134  jnz     short loc_18002B14E
0x18002b136  mov     [rbp+57h+pExceptionObject], 80100011h
0x18002b13d  lea     rdx, _TI1K; pThrowInfo
0x18002b144  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b148  call    _CxxThrowException_0
0x18002b14e  lea     rdx, Control; "\\?"
0x18002b155  mov     rcx, rbx; String
0x18002b158  call    cs:__imp_wcspbrk
0x18002b15e  test    rax, rax
0x18002b161  jz      short loc_18002B17B
0x18002b163  mov     [rbp+57h+pExceptionObject], 80100011h
0x18002b16a  lea     rdx, _TI1K; pThrowInfo
0x18002b171  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b175  call    _CxxThrowException_0
0x18002b17b  xor     ecx, ecx
0x18002b17d  lea     r10, dword_180039DB0
0x18002b184  mov     eax, ecx
0x18002b186  add     rax, rax
0x18002b189  cmp     [r10+rax*8], edi
0x18002b18d  jz      short loc_18002B1AE
0x18002b18f  inc     ecx
0x18002b191  cmp     ecx, 2
0x18002b194  jb      short loc_18002B184
0x18002b196  mov     [rbp+57h+pExceptionObject], 80100011h
0x18002b19d  lea     rdx, _TI1K; pThrowInfo
0x18002b1a4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b1a8  call    _CxxThrowException_0
0x18002b1ae  mov     edx, ecx
0x18002b1b0  add     rdx, rdx
0x18002b1b3  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18002b1bb  mov     r9d, 4; samDesired
0x18002b1c1  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002b1c8  mov     rdx, [r10+rdx*8+8]; hKey
0x18002b1cd  lea     rcx, [rbp+57h+hKey]; phkResult
0x18002b1d1  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002b1d6  xor     edx, edx; int
0x18002b1d8  lea     rcx, [rbp+57h+hKey]; this
0x18002b1dc  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002b1e1  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18002b1e9  mov     r9d, 2; samDesired
0x18002b1ef  mov     r8, rbx; lpSubKey
0x18002b1f2  mov     rdx, [rbp+57h+hKey]; hKey
0x18002b1f6  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18002b1fa  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002b1ff  nop
0x18002b200  lea     rcx, [rbp+57h+phkResult]; this
0x18002b204  call    ?GetDisposition@CRegistry@@QEBAKXZ; CRegistry::GetDisposition(void)
0x18002b209  cmp     eax, 2
0x18002b20c  jnz     short loc_18002B226
0x18002b20e  mov     [rbp+57h+pExceptionObject], 8010001Bh
0x18002b215  lea     rdx, _TI1K; pThrowInfo
0x18002b21c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002b220  call    _CxxThrowException_0
0x18002b226  mov     r8, rsi; unsigned __int16 *
0x18002b229  lea     rdx, aDevice_1; "Device"
0x18002b230  lea     rcx, [rbp+57h+phkResult]; this
0x18002b234  call    ?SetValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetValue(ushort const *,ushort const *,ulong)
0x18002b239  lea     r8, aScardDefaultre; "SCard$DefaultReaders"
0x18002b240  lea     rcx, [rbp+57h+phkResult]; this
0x18002b244  call    ?SetMultiStringValue@CRegistry@@QEBAXPEBG0K@Z; CRegistry::SetMultiStringValue(ushort const *,ushort const *,ulong)
0x18002b249  nop
0x18002b24a  lea     rcx, [rbp+57h+phkResult]; this
0x18002b24e  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002b253  nop
0x18002b254  lea     rcx, [rbp+57h+hKey]; this
0x18002b258  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002b25d  add     rsp, 98h
0x18002b264  pop     rdi
0x18002b265  pop     rsi
0x18002b266  pop     rbx
0x18002b267  pop     rbp
0x18002b268  retn
```
