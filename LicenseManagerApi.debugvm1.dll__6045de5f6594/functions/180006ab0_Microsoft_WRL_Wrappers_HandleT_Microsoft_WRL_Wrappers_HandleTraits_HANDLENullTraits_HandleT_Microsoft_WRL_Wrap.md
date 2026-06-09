# Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::~HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>(void)

- ea: `0x180006ab0`
- end: `0x180006afb`
- name: `??1?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012293`
- `0x1800122db`
- `0x1800122ed`
- `0x1800123a3`
- `0x180012565`

## callees

- `0x180006ab0`
- `0x18000bdc0`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ae1`

## pseudocode

```c
void **__fastcall Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::~HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>(
        _QWORD *a1)
{
  bool v1; // zf
  void **result; // rax
  signed int LastError; // eax

  v1 = a1[1] == 0;
  result = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( !v1 )
  {
    result = (void **)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(a1);
    if ( !(_BYTE)result )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError);
      JUMPOUT(0x180006AFALL);
    }
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180006ab0  push    rbx
0x180006ab2  sub     rsp, 20h
0x180006ab6  cmp     qword ptr [rcx+8], 0
0x180006abb  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180006ac2  mov     [rcx], rax
0x180006ac5  mov     rbx, rcx
0x180006ac8  jz      short loc_180006ADB
0x180006aca  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180006acf  test    al, al
0x180006ad1  jz      short loc_180006AE1
0x180006ad3  mov     qword ptr [rbx+8], 0
0x180006adb  add     rsp, 20h
0x180006adf  pop     rbx
0x180006ae0  retn
0x180006ae1  call    cs:__imp_GetLastError
0x180006ae7  test    eax, eax
0x180006ae9  jle     short loc_180006AF3
0x180006aeb  movzx   eax, ax
0x180006aee  or      eax, 80070000h
0x180006af3  mov     ecx, eax; this
0x180006af5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
