# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x180009f00`
- end: `0x180009f4e`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticInvoker@Diagnostics@System@Windows@@UIDiagnosticInvoker2@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `78`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009f60`
- `0x180009f70`
- `0x180009f80`

## callees

- `0x180009f00`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rdx
  unsigned int v2; // r8d
  unsigned int v3; // r9d
  bool v4; // zf
  signed __int64 v5; // rax
  signed __int32 v6; // r9d

  v1 = *(_QWORD *)(a1 + 64);
  v2 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v2;
    v3 = v1 + 1;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v1 + 1, v1);
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
0x180009f00  mov     rdx, [rcx+40h]
0x180009f04  mov     r8d, 7FFFFFFFh
0x180009f0a  test    rdx, rdx
0x180009f0d  js      short loc_180009F37
0x180009f0f  cmp     edx, r8d
0x180009f12  jz      short loc_180009F47
0x180009f14  lea     r9, [rdx+1]
0x180009f18  mov     rax, rdx
0x180009f1b  lock cmpxchg [rcx+40h], r9
0x180009f21  mov     rdx, rax
0x180009f24  jnz     short loc_180009F0A
0x180009f26  jmp     short loc_180009F4A
0x180009f28  lea     ecx, [r9+1]
0x180009f2c  mov     eax, r9d
0x180009f2f  lock cmpxchg [rdx+rdx+10h], ecx
0x180009f35  jz      short loc_180009F43
0x180009f37  mov     r9d, [rdx+rdx+10h]
0x180009f3c  cmp     r9d, r8d
0x180009f3f  jnz     short loc_180009F28
0x180009f41  jmp     short loc_180009F47
0x180009f43  lea     r8d, [r9+1]
0x180009f47  mov     r9d, r8d
0x180009f4a  mov     eax, r9d
0x180009f4d  retn
```
