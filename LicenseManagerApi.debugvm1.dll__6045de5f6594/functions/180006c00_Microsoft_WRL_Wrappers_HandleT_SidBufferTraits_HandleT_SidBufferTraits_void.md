# Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::~HandleT<SidBufferTraits>(void)

- ea: `0x180006c00`
- end: `0x180006c4b`
- name: `??1?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800121f3`

## callees

- `0x180006c00`
- `0x18000be60`
- `0x18000e9c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c31`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::~HandleT<SidBufferTraits>(_QWORD *a1)
{
  bool v1; // zf
  void **v2; // rax
  signed int LastError; // eax
  int v5; // edx
  unsigned int v6; // r8d

  v1 = a1[1] == 0;
  v2 = &Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable';
  *a1 = &Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable';
  if ( !v1 )
  {
    LOBYTE(v2) = Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose((__int64)a1);
    if ( !(_BYTE)v2 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v5, v6);
      JUMPOUT(0x180006C4ALL);
    }
    a1[1] = 0;
  }
  return (char)v2;
}

```

## disassembly

```asm
0x180006c00  push    rbx
0x180006c02  sub     rsp, 20h
0x180006c06  cmp     qword ptr [rcx+8], 0
0x180006c0b  lea     rax, ??_7?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::`vftable'
0x180006c12  mov     [rcx], rax
0x180006c15  mov     rbx, rcx
0x180006c18  jz      short loc_180006C2B
0x180006c1a  call    ?InternalClose@?$HandleT@USidBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<SidBufferTraits>::InternalClose(void)
0x180006c1f  test    al, al
0x180006c21  jz      short loc_180006C31
0x180006c23  mov     qword ptr [rbx+8], 0
0x180006c2b  add     rsp, 20h
0x180006c2f  pop     rbx
0x180006c30  retn
0x180006c31  call    cs:__imp_GetLastError
0x180006c37  test    eax, eax
0x180006c39  jle     short loc_180006C43
0x180006c3b  movzx   eax, ax
0x180006c3e  or      eax, 80070000h
0x180006c43  mov     ecx, eax; this
0x180006c45  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
