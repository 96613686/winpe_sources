# wil::details::lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___::_lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___

- ea: `0x1800139b4`
- end: `0x180013a0a`
- name: `wil::details::lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___::_lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18009a160`

## callees

- `0x1800139b4`
- `0x18007db8c`
- `0x18007dbe8`

## import_xrefs

- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800139cd`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800139cd`
- `SAMSRV!SamrCloseHandle` at `0x1800139d7`
- `SAMSRV!SamrCloseHandle` at `0x1800139d7`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800139e1`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800139e1`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___::_lambda_call__lambda_69d2db8f95e5be7727df75cb1ead3841___(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
  {
    *(_BYTE *)(a1 + 32) = 0;
    SamIFree_UserInternal6Information(**(_QWORD **)a1);
    SamrCloseHandle(*(_QWORD *)(a1 + 8));
    SamIFreeSidAndAttributesList(*(_QWORD *)(a1 + 16));
    v2 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(v2 + 8) )
      KerbFreePrincipalName(v2);
    return KerbFreeRealm(*(_QWORD *)(a1 + 24) + 16LL);
  }
  return result;
}

```

## disassembly

```asm
0x1800139b4  push    rbx
0x1800139b6  sub     rsp, 20h
0x1800139ba  cmp     byte ptr [rcx+20h], 0
0x1800139be  mov     rbx, rcx
0x1800139c1  jz      short loc_180013A04
0x1800139c3  mov     byte ptr [rcx+20h], 0
0x1800139c7  mov     rcx, [rcx]
0x1800139ca  mov     rcx, [rcx]
0x1800139cd  call    cs:__imp_SamIFree_UserInternal6Information
0x1800139d3  mov     rcx, [rbx+8]
0x1800139d7  call    cs:__imp_SamrCloseHandle
0x1800139dd  mov     rcx, [rbx+10h]
0x1800139e1  call    cs:__imp_SamIFreeSidAndAttributesList
0x1800139e7  mov     rcx, [rbx+18h]
0x1800139eb  cmp     qword ptr [rcx+8], 0
0x1800139f0  jz      short loc_1800139F7
0x1800139f2  call    KerbFreePrincipalName
0x1800139f7  mov     rcx, [rbx+18h]
0x1800139fb  add     rcx, 10h
0x1800139ff  call    KerbFreeRealm
0x180013a04  add     rsp, 20h
0x180013a08  pop     rbx
0x180013a09  retn
```
