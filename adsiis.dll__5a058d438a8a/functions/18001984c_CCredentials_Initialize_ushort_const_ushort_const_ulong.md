# CCredentials::Initialize(ushort const *,ushort const *,ulong)

- ea: `0x18001984c`
- end: `0x1800198ab`
- name: `?Initialize@CCredentials@@AEAAJPEBG0K@Z`
- size: `95`
- prototype: `__int64 __fastcall(CCredentials *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c20`
- `0x180001cc0`
- `0x180001d44`
- `0x180002710`
- `0x180002950`
- `0x180003bb8`
- `0x1800040b0`
- `0x18000816c`
- `0x1800085a0`
- `0x180008900`
- `0x180009068`
- `0x180009154`
- `0x18000ce28`
- `0x18000d638`
- `0x18000fe60`
- `0x1800197b4`

## callees

- `0x18001984c`
- `0x1800198b4`
- `0x180019948`

## pseudocode

```c
__int64 __fastcall CCredentials::Initialize(
        CCredentials *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v7; // edi

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = CCredentials::SetUserName(this, a2);
  if ( v7 >= 0 )
  {
    v7 = CCredentials::SetPassword(this, a3);
    if ( v7 < 0 )
      CCredentials::SetUserName(this, 0);
    else
      *((_DWORD *)this + 4) = a4;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001984c  push    rbx
0x18001984e  push    rbp
0x18001984f  push    rsi
0x180019850  push    rdi
0x180019851  sub     rsp, 28h
0x180019855  mov     esi, r9d
0x180019858  mov     qword ptr [rcx], 0
0x18001985f  mov     rbp, r8
0x180019862  mov     qword ptr [rcx+8], 0
0x18001986a  mov     rbx, rcx
0x18001986d  mov     qword ptr [rcx+10h], 0
0x180019875  call    ?SetUserName@CCredentials@@QEAAJPEBG@Z; CCredentials::SetUserName(ushort const *)
0x18001987a  mov     edi, eax
0x18001987c  test    eax, eax
0x18001987e  js      short loc_1800198A0
0x180019880  mov     rdx, rbp; unsigned __int16 *
0x180019883  mov     rcx, rbx; this
0x180019886  call    ?SetPassword@CCredentials@@QEAAJPEBG@Z; CCredentials::SetPassword(ushort const *)
0x18001988b  mov     edi, eax
0x18001988d  test    eax, eax
0x18001988f  js      short loc_180019896
0x180019891  mov     [rbx+10h], esi
0x180019894  jmp     short loc_1800198A0
0x180019896  xor     edx, edx; unsigned __int16 *
0x180019898  mov     rcx, rbx; this
0x18001989b  call    ?SetUserName@CCredentials@@QEAAJPEBG@Z; CCredentials::SetUserName(ushort const *)
0x1800198a0  mov     eax, edi
0x1800198a2  add     rsp, 28h
0x1800198a6  pop     rdi
0x1800198a7  pop     rsi
0x1800198a8  pop     rbp
0x1800198a9  pop     rbx
0x1800198aa  retn
```
