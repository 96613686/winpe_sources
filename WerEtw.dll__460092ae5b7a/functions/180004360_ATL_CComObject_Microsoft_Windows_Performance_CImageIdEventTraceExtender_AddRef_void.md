# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::AddRef(void)

- ea: `0x180004360`
- end: `0x180004373`
- name: `?AddRef@?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004360`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 24);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 24) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180004360  mov     edx, [rcx+18h]
0x180004363  mov     eax, 7FFFFFFFh
0x180004368  cmp     edx, eax
0x18000436a  jz      short locret_180004372
0x18000436c  lea     eax, [rdx+1]
0x18000436f  mov     [rcx+18h], eax
0x180004372  retn
```
