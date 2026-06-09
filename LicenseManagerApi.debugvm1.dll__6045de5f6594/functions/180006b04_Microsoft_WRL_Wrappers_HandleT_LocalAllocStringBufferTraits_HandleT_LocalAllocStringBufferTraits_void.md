# Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::~HandleT<LocalAllocStringBufferTraits>(void)

- ea: `0x180006b04`
- end: `0x180006b4f`
- name: `??1?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800121a0`
- `0x180012205`
- `0x18001237f`
- `0x180012391`
- `0x1800123fd`
- `0x18001249f`
- `0x1800124e7`
- `0x18001250b`

## callees

- `0x180006b04`
- `0x18000bde0`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b35`

## pseudocode

```c
void **__fastcall Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::~HandleT<LocalAllocStringBufferTraits>(
        _QWORD *a1)
{
  bool v1; // zf
  void **result; // rax
  signed int LastError; // eax

  v1 = a1[1] == 0;
  result = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  *a1 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  if ( !v1 )
  {
    result = (void **)Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(a1);
    if ( !(_BYTE)result )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError);
      JUMPOUT(0x180006B4ELL);
    }
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006b04  push    rbx
0x180006b06  sub     rsp, 20h
0x180006b0a  cmp     qword ptr [rcx+8], 0
0x180006b0f  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x180006b16  mov     [rcx], rax
0x180006b19  mov     rbx, rcx
0x180006b1c  jz      short loc_180006B2F
0x180006b1e  call    ?InternalClose@?$HandleT@ULocalAllocMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<LocalAllocMemBufferTraits>::InternalClose(void)
0x180006b23  test    al, al
0x180006b25  jz      short loc_180006B35
0x180006b27  mov     qword ptr [rbx+8], 0
0x180006b2f  add     rsp, 20h
0x180006b33  pop     rbx
0x180006b34  retn
0x180006b35  call    cs:__imp_GetLastError
0x180006b3b  test    eax, eax
0x180006b3d  jle     short loc_180006B47
0x180006b3f  movzx   eax, ax
0x180006b42  or      eax, 80070000h
0x180006b47  mov     ecx, eax; this
0x180006b49  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
