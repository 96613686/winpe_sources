# std::make_pair<DX_FEATURE_LEVEL &,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(DX_FEATURE_LEVEL &,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &)

- ea: `0x180016908`
- end: `0x180016984`
- name: `??$make_pair@AEAW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@YA?AU?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@0@AEAW4DX_FEATURE_LEVEL@@AEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180001250`
- `0x180016908`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::make_pair<enum DX_FEATURE_LEVEL &,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  __int64 v5; // rbx
  __int64 v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v7[1] = -2;
  v7[0] = *a3;
  v5 = v7[0];
  if ( v7[0] )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7[0] + 8LL))(v7[0]);
  *(_DWORD *)a1 = *a2;
  *(_QWORD *)(a1 + 8) = 0;
  if ( (__int64 *)(a1 + 8) != v7 )
  {
    *(_QWORD *)(a1 + 8) = v5;
    v7[0] = 0;
  }
  Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v7);
  return a1;
}

```

## disassembly

```asm
0x180016908  mov     rax, rsp
0x18001690b  push    rdi
0x18001690c  sub     rsp, 30h
0x180016910  mov     qword ptr [rax-10h], 0FFFFFFFFFFFFFFFEh
0x180016918  mov     [rax+8], rbx
0x18001691c  mov     [rax+10h], rsi
0x180016920  mov     rsi, rdx
0x180016923  mov     rdi, rcx
0x180016926  mov     rbx, [r8]
0x180016929  mov     [rax-18h], rbx
0x18001692d  test    rbx, rbx
0x180016930  jz      short loc_180016942
0x180016932  mov     rax, [rbx]
0x180016935  mov     rcx, rbx
0x180016938  mov     rax, [rax+8]
0x18001693c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016941  nop
0x180016942  mov     eax, [rsi]
0x180016944  mov     [rdi], eax
0x180016946  lea     rax, [rdi+8]
0x18001694a  mov     qword ptr [rax], 0
0x180016951  lea     rcx, [rsp+38h+var_18]
0x180016956  cmp     rax, rcx
0x180016959  jz      short loc_180016967
0x18001695b  mov     [rax], rbx
0x18001695e  mov     [rsp+38h+var_18], 0
0x180016967  lea     rcx, [rsp+38h+var_18]
0x18001696c  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180016971  mov     rax, rdi
0x180016974  mov     rbx, [rsp+38h+arg_0]
0x180016979  mov     rsi, [rsp+38h+arg_8]
0x18001697e  add     rsp, 30h
0x180016982  pop     rdi
0x180016983  retn
```
