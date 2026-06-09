# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(std::pair<ushort *,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> &&)

- ea: `0x180004df8`
- end: `0x180004e51`
- name: `??$?0PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@QEAA@$$QEAU?$pair@PEAGV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z`
- size: `89`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e250`

## callees

- `0x180004df8`
- `0x180005140`
- `0x180005750`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v2; // r8
  _QWORD *v3; // rdi
  __int64 v5; // r8

  v2 = *a2;
  v3 = a2 + 1;
  *(_QWORD *)(a1 + 24) = 7;
  std::wstring::_Eos(a1, 0, v2);
  std::wstring::assign(a1, v5);
  *(_QWORD *)(a1 + 40) = 0;
  if ( (_QWORD *)(a1 + 40) != v3 )
  {
    *(_QWORD *)(a1 + 40) = *v3;
    *v3 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180004df8  mov     [rsp+arg_0], rbx
0x180004dfd  push    rdi
0x180004dfe  sub     rsp, 20h
0x180004e02  mov     r8, [rdx]
0x180004e05  lea     rdi, [rdx+8]
0x180004e09  xor     edx, edx
0x180004e0b  mov     qword ptr [rcx+18h], 7
0x180004e13  mov     rbx, rcx
0x180004e16  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180004e1b  mov     rcx, rbx
0x180004e1e  mov     rdx, r8
0x180004e21  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180004e26  lea     rcx, [rbx+28h]
0x180004e2a  mov     qword ptr [rcx], 0
0x180004e31  cmp     rcx, rdi
0x180004e34  jz      short loc_180004E43
0x180004e36  mov     rax, [rdi]
0x180004e39  mov     [rcx], rax
0x180004e3c  mov     qword ptr [rdi], 0
0x180004e43  mov     rax, rbx
0x180004e46  mov     rbx, [rsp+28h+arg_0]
0x180004e4b  add     rsp, 20h
0x180004e4f  pop     rdi
0x180004e50  retn
```
