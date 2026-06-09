# Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(void)

- ea: `0x1800266a8`
- end: `0x180026726`
- name: `??1?$AutoGenericHandleBase@UUninstallFeaturesResult@@$03V?$AutoGenericHandle@UUninstallFeaturesResult@@$03$1?CloseWithFreeUninstallFeaturesResult@@YAXU1@@Z@Windows@@@Windows@@QEAA@XZ`
- size: `126`
- prototype: `int __fastcall(__int128 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180026f3c`

## callees

- `0x1800040f4`
- `0x1800266a8`

## import_xrefs

- `ServicingUAPI!FreeUninstallFeaturesResult` at `0x180026706`
- `ServicingUAPI!FreeUninstallFeaturesResult` at `0x180026706`

## pseudocode

```c
int __fastcall Windows::AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>::~AutoGenericHandleBase<UninstallFeaturesResult,4,Windows::AutoGenericHandle<UninstallFeaturesResult,4,&void CloseWithFreeUninstallFeaturesResult(UninstallFeaturesResult)>>(
        __int128 *a1)
{
  int result; // eax
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 Buf2; // [rsp+20h] [rbp-48h] BYREF
  __int128 v6; // [rsp+30h] [rbp-38h]
  __int128 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-18h]

  Buf2 = 0;
  v8 = 0;
  v6 = 0;
  v7 = 0;
  result = memcmp_0(a1, &Buf2, 0x38u);
  if ( result )
  {
    v3 = a1[1];
    Buf2 = *a1;
    v4 = a1[2];
    v6 = v3;
    *(_QWORD *)&v3 = *((_QWORD *)a1 + 6);
    v7 = v4;
    v8 = v3;
    FreeUninstallFeaturesResult(&Buf2);
    result = 0;
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    *((_QWORD *)a1 + 6) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800266a8  push    rbx
0x1800266aa  sub     rsp, 60h
0x1800266ae  xorps   xmm0, xmm0
0x1800266b1  lea     rdx, [rsp+68h+Buf2]; Buf2
0x1800266b6  xor     eax, eax
0x1800266b8  mov     rbx, rcx
0x1800266bb  movups  [rsp+68h+Buf2], xmm0
0x1800266c0  mov     [rsp+68h+var_18], rax
0x1800266c5  movups  [rsp+68h+var_38], xmm0
0x1800266ca  lea     r8d, [rax+38h]; Size
0x1800266ce  movups  [rsp+68h+var_28], xmm0
0x1800266d3  call    memcmp_0
0x1800266d8  test    eax, eax
0x1800266da  jz      short loc_180026720
0x1800266dc  movups  xmm0, xmmword ptr [rbx]
0x1800266df  lea     rcx, [rsp+68h+Buf2]
0x1800266e4  movups  xmm1, xmmword ptr [rbx+10h]
0x1800266e8  movaps  [rsp+68h+Buf2], xmm0
0x1800266ed  movups  xmm0, xmmword ptr [rbx+20h]
0x1800266f1  movaps  [rsp+68h+var_38], xmm1
0x1800266f6  movsd   xmm1, qword ptr [rbx+30h]
0x1800266fb  movaps  [rsp+68h+var_28], xmm0
0x180026700  movsd   [rsp+68h+var_18], xmm1
0x180026706  call    cs:__imp_FreeUninstallFeaturesResult
0x18002670c  xorps   xmm0, xmm0
0x18002670f  xor     eax, eax
0x180026711  movups  xmmword ptr [rbx], xmm0
0x180026714  movups  xmmword ptr [rbx+10h], xmm0
0x180026718  movups  xmmword ptr [rbx+20h], xmm0
0x18002671c  mov     [rbx+30h], rax
0x180026720  add     rsp, 60h
0x180026724  pop     rbx
0x180026725  retn
```
