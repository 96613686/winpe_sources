# Microsoft::WRL::ComPtr<FileFolder>::~ComPtr<FileFolder>(void)

- ea: `0x1800058f4`
- end: `0x180005914`
- name: `??1?$ComPtr@VFileFolder@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001789d`

## callees

- `0x1800058f4`
- `0x180006fe0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::ComPtr<FileFolder>::~ComPtr<FileFolder>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<FileFolder,RfbShellFolderBase,1>>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x1800058f4  sub     rsp, 28h
0x1800058f8  mov     rax, [rcx]
0x1800058fb  test    rax, rax
0x1800058fe  jz      short loc_18000590F
0x180005900  mov     qword ptr [rcx], 0
0x180005907  mov     rcx, rax
0x18000590a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$MixIn@VFileFolder@@VRfbShellFolderBase@@$00@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::MixIn<FileFolder,RfbShellFolderBase,1>>::Release(void)
0x18000590f  add     rsp, 28h
0x180005913  retn
```
