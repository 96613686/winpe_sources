# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x180011df0`
- end: `0x180011e3e`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `78`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011e50`
- `0x180011e60`
- `0x180011e70`
- `0x180011e80`

## callees

- `0x180011df0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v2; // r8d
  unsigned int v3; // r9d
  bool v4; // zf
  signed __int64 v5; // rax
  signed __int32 v6; // r9d

  v1 = *(_QWORD *)(a1 + 72);
  v2 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v2;
    v3 = v1 + 1;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v1 + 1, v1);
    v4 = v1 == v5;
    v1 = v5;
    if ( v4 )
      return v3;
  }
  while ( 1 )
  {
    v6 = *(_DWORD *)(2 * v1 + 0x10);
    if ( v6 == 0x7FFFFFFF )
      break;
    if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v6 + 1, v6) )
      return (unsigned int)(v6 + 1);
  }
  return v2;
}

```

## disassembly

```asm
0x180011df0  mov     rdx, [rcx+48h]
0x180011df4  mov     r8d, 7FFFFFFFh
0x180011dfa  test    rdx, rdx
0x180011dfd  js      short loc_180011E27
0x180011dff  cmp     edx, r8d
0x180011e02  jz      short loc_180011E37
0x180011e04  lea     r9, [rdx+1]
0x180011e08  mov     rax, rdx
0x180011e0b  lock cmpxchg [rcx+48h], r9
0x180011e11  mov     rdx, rax
0x180011e14  jnz     short loc_180011DFA
0x180011e16  jmp     short loc_180011E3A
0x180011e18  lea     ecx, [r9+1]
0x180011e1c  mov     eax, r9d
0x180011e1f  lock cmpxchg [rdx+rdx+10h], ecx
0x180011e25  jz      short loc_180011E33
0x180011e27  mov     r9d, [rdx+rdx+10h]
0x180011e2c  cmp     r9d, r8d
0x180011e2f  jnz     short loc_180011E18
0x180011e31  jmp     short loc_180011E37
0x180011e33  lea     r8d, [r9+1]
0x180011e37  mov     r9d, r8d
0x180011e3a  mov     eax, r9d
0x180011e3d  retn
```
