# WebAuthNPluginAuthenticatorFreeCredentialDetailsArray

- ea: `0x1800bbdd0`
- end: `0x1800bbe6b`
- name: `WebAuthNPluginAuthenticatorFreeCredentialDetailsArray`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18004685c`
- `0x1800bbdd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bbe5a`

## pseudocode

```c
void __fastcall WebAuthNPluginAuthenticatorFreeCredentialDetailsArray(unsigned int a1, LPVOID *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rbp
  void *v6; // rcx

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl)
    && a2 )
  {
    v4 = 0;
    if ( a1 )
    {
      v5 = 0;
      do
      {
        CoTaskMemFree(a2[8 * v5 + 1]);
        CoTaskMemFree(a2[8 * v5 + 5]);
        CoTaskMemFree(a2[8 * v5 + 2]);
        CoTaskMemFree(a2[8 * v5 + 3]);
        CoTaskMemFree(a2[8 * v5 + 6]);
        v6 = a2[8 * v5 + 7];
        if ( v6 )
          CoTaskMemFree(v6);
        ++v4;
        ++v5;
      }
      while ( v4 < a1 );
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x1800bbdd0  push    rbx
0x1800bbdd2  push    rbp
0x1800bbdd3  push    rsi
0x1800bbdd4  push    rdi
0x1800bbdd5  push    r14
0x1800bbdd7  sub     rsp, 20h
0x1800bbddb  mov     rdi, rdx
0x1800bbdde  mov     r14d, ecx
0x1800bbde1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl(void)'::`2'::impl
0x1800bbde8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPluginAuthenticators@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(void)
0x1800bbded  test    al, al
0x1800bbdef  jz      short loc_1800BBE60
0x1800bbdf1  test    rdi, rdi
0x1800bbdf4  jz      short loc_1800BBE60
0x1800bbdf6  xor     esi, esi
0x1800bbdf8  test    r14d, r14d
0x1800bbdfb  jz      short loc_1800BBE57
0x1800bbdfd  xor     ebp, ebp
0x1800bbdff  mov     rbx, rbp
0x1800bbe02  shl     rbx, 6
0x1800bbe06  mov     rcx, [rbx+rdi+8]; pv
0x1800bbe0b  call    cs:__imp_CoTaskMemFree
0x1800bbe11  mov     rcx, [rbx+rdi+28h]; pv
0x1800bbe16  call    cs:__imp_CoTaskMemFree
0x1800bbe1c  mov     rcx, [rbx+rdi+10h]; pv
0x1800bbe21  call    cs:__imp_CoTaskMemFree
0x1800bbe27  mov     rcx, [rbx+rdi+18h]; pv
0x1800bbe2c  call    cs:__imp_CoTaskMemFree
0x1800bbe32  mov     rcx, [rbx+rdi+30h]; pv
0x1800bbe37  call    cs:__imp_CoTaskMemFree
0x1800bbe3d  mov     rcx, [rbx+rdi+38h]; pv
0x1800bbe42  test    rcx, rcx
0x1800bbe45  jz      short loc_1800BBE4D
0x1800bbe47  call    cs:__imp_CoTaskMemFree
0x1800bbe4d  inc     esi
0x1800bbe4f  inc     rbp
0x1800bbe52  cmp     esi, r14d
0x1800bbe55  jb      short loc_1800BBDFF
0x1800bbe57  mov     rcx, rdi; pv
0x1800bbe5a  call    cs:__imp_CoTaskMemFree
0x1800bbe60  add     rsp, 20h
0x1800bbe64  pop     r14
0x1800bbe66  pop     rdi
0x1800bbe67  pop     rsi
0x1800bbe68  pop     rbp
0x1800bbe69  pop     rbx
0x1800bbe6a  retn
```
