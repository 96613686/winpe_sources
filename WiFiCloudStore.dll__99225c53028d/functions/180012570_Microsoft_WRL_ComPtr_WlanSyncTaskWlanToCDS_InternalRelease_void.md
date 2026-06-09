# Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)

- ea: `0x180012570`
- end: `0x18001258e`
- name: `?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011d88`
- `0x180011db8`
- `0x180011f8c`
- `0x1800121b0`
- `0x18001252c`
- `0x18001f998`
- `0x180028144`
- `0x180028748`

## callees

- `0x180012570`
- `0x180013bc0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  result = 0;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180012570  sub     rsp, 28h
0x180012574  mov     rdx, [rcx]
0x180012577  xor     eax, eax
0x180012579  test    rdx, rdx
0x18001257c  jz      short loc_180012589
0x18001257e  mov     [rcx], rax
0x180012581  mov     rcx, rdx
0x180012584  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x180012589  add     rsp, 28h
0x18001258d  retn
```
