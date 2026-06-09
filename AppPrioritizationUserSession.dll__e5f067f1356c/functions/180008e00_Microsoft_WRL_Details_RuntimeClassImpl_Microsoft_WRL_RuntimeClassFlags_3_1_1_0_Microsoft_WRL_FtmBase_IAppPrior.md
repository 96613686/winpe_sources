# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::AddRef(void)

- ea: `0x180008e00`
- end: `0x180008e50`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `80`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e60`
- `0x180008e70`
- `0x180008e80`
- `0x180008e90`

## callees

- `0x180008e00`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  bool v5; // zf
  signed __int64 v6; // rax
  signed __int32 v7; // r9d

  v1 = *(_QWORD *)(a1 + 72);
  v3 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v3;
    v4 = v1 + 1;
    v6 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v1 + 1, v1);
    v5 = v1 == v6;
    v1 = v6;
    if ( v5 )
      return v4;
  }
  while ( 1 )
  {
    v7 = *(_DWORD *)(2 * v1 + 0x10);
    if ( v7 == 0x7FFFFFFF )
      break;
    if ( v7 == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v7 + 1, v7) )
      return (unsigned int)(v7 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x180008e00  mov     rdx, [rcx+48h]
0x180008e04  mov     r9, rcx
0x180008e07  mov     r8d, 7FFFFFFFh
0x180008e0d  test    rdx, rdx
0x180008e10  js      short loc_180008E3A
0x180008e12  cmp     edx, r8d
0x180008e15  jz      short loc_180008E4A
0x180008e17  lea     rcx, [rdx+1]
0x180008e1b  mov     rax, rdx
0x180008e1e  lock cmpxchg [r9+48h], rcx
0x180008e24  mov     rdx, rax
0x180008e27  jnz     short loc_180008E0D
0x180008e29  jmp     short loc_180008E4D
0x180008e2b  lea     ecx, [r9+1]
0x180008e2f  mov     eax, r9d
0x180008e32  lock cmpxchg [rdx+rdx+10h], ecx
0x180008e38  jz      short loc_180008E46
0x180008e3a  mov     r9d, [rdx+rdx+10h]
0x180008e3f  cmp     r9d, r8d
0x180008e42  jnz     short loc_180008E2B
0x180008e44  jmp     short loc_180008E4A
0x180008e46  lea     r8d, [r9+1]
0x180008e4a  mov     ecx, r8d
0x180008e4d  mov     eax, ecx
0x180008e4f  retn
```
