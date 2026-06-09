# Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::~HandleT<RpcBindingHandleTraits>(void)

- ea: `0x180006b58`
- end: `0x180006ba3`
- name: `??1?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800121c4`
- `0x180012231`
- `0x1800122b7`
- `0x180012445`
- `0x18001248d`
- `0x1800124f9`
- `0x180012553`

## callees

- `0x180006b58`
- `0x18000be00`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b89`

## pseudocode

```c
void **__fastcall Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::~HandleT<RpcBindingHandleTraits>(
        _QWORD *a1)
{
  bool v1; // zf
  void **result; // rax
  signed int LastError; // eax

  v1 = a1[1] == 0;
  result = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  *a1 = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  if ( !v1 )
  {
    result = (void **)Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(a1);
    if ( !(_BYTE)result )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError);
      JUMPOUT(0x180006BA2LL);
    }
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006b58  push    rbx
0x180006b5a  sub     rsp, 20h
0x180006b5e  cmp     qword ptr [rcx+8], 0
0x180006b63  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x180006b6a  mov     [rcx], rax
0x180006b6d  mov     rbx, rcx
0x180006b70  jz      short loc_180006B83
0x180006b72  call    ?InternalClose@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::InternalClose(void)
0x180006b77  test    al, al
0x180006b79  jz      short loc_180006B89
0x180006b7b  mov     qword ptr [rbx+8], 0
0x180006b83  add     rsp, 20h
0x180006b87  pop     rbx
0x180006b88  retn
0x180006b89  call    cs:__imp_GetLastError
0x180006b8f  test    eax, eax
0x180006b91  jle     short loc_180006B9B
0x180006b93  movzx   eax, ax
0x180006b96  or      eax, 80070000h
0x180006b9b  mov     ecx, eax; this
0x180006b9d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
