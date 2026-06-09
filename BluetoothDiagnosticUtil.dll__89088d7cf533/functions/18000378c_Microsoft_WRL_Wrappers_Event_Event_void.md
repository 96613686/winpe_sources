# Microsoft::WRL::Wrappers::Event::~Event(void)

- ea: `0x18000378c`
- end: `0x1800037de`
- name: `??1Event@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::Event *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d9`
- `0x18000a76b`

## callees

- `0x18000378c`
- `0x180005d90`
- `0x180006c6c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800037be`
- `KERNEL32!GetLastError` at `0x1800037be`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::Event::~Event(Microsoft::WRL::Wrappers::Event *this)
{
  bool v1; // zf
  signed int LastError; // eax

  v1 = *((_QWORD *)this + 1) == 0;
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( !v1 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(this) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError);
      JUMPOUT(0x1800037DDLL);
    }
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000378c  push    rbx
0x18000378e  sub     rsp, 20h
0x180003792  cmp     qword ptr [rcx+8], 0
0x180003797  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000379e  mov     [rcx], rax
0x1800037a1  mov     rbx, rcx
0x1800037a4  jz      short loc_1800037B7
0x1800037a6  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1800037ab  test    al, al
0x1800037ad  jz      short loc_1800037BE
0x1800037af  mov     qword ptr [rbx+8], 0
0x1800037b7  add     rsp, 20h
0x1800037bb  pop     rbx
0x1800037bc  retn
0x1800037be  call    cs:__imp_GetLastError
0x1800037c5  nop     dword ptr [rax+rax+00h]
0x1800037ca  test    eax, eax
0x1800037cc  jle     short loc_1800037D6
0x1800037ce  movzx   eax, ax
0x1800037d1  or      eax, 80070000h
0x1800037d6  mov     ecx, eax; this
0x1800037d8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
