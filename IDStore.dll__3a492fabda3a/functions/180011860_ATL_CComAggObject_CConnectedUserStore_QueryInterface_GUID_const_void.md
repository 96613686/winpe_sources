# ATL::CComAggObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011860`
- end: `0x1800118ad`
- name: `?QueryInterface@?$CComAggObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000bc50`
- `0x18000d450`
- `0x180011860`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CConnectedUserStore>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  _QWORD *v5; // r8
  __int64 v6; // r9

  v3 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( ATL::InlineIsEqualUnknown(a2) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  }
  else
  {
    return (unsigned int)ATL::CComObject<CConnectedUserStore>::QueryInterface(v6 + 24);
  }
  return v3;
}

```

## disassembly

```asm
0x180011860  push    rbx
0x180011862  sub     rsp, 20h
0x180011866  xor     ebx, ebx
0x180011868  mov     r9, rcx
0x18001186b  test    r8, r8
0x18001186e  jnz     short loc_180011877
0x180011870  mov     eax, 80004003h
0x180011875  jmp     short loc_1800118A7
0x180011877  mov     rcx, rdx; struct _GUID *
0x18001187a  mov     [r8], rbx
0x18001187d  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180011882  test    eax, eax
0x180011884  jz      short loc_18001189A
0x180011886  mov     [r8], r9
0x180011889  mov     rcx, r9
0x18001188c  mov     rax, [r9]
0x18001188f  mov     rax, [rax+8]
0x180011893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011898  jmp     short loc_1800118A5
0x18001189a  lea     rcx, [r9+18h]
0x18001189e  call    ?QueryInterface@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CConnectedUserStore>::QueryInterface(_GUID const &,void * *)
0x1800118a3  mov     ebx, eax
0x1800118a5  mov     eax, ebx
0x1800118a7  add     rsp, 20h
0x1800118ab  pop     rbx
0x1800118ac  retn
```
