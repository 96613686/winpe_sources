# SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::VtblMethodSwap(unsigned __int64 *,long (*)(void *,_GUID const &,void * *))

- ea: `0x180008af0`
- end: `0x180008b8f`
- name: `?VtblMethodSwap@?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@IEAA_NPEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@Z`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800070b8`
- `0x1800076b0`

## callees

- `0x180008af0`
- `0x180008bf0`
- `0x180008ff8`

## import_xrefs

- `KERNEL32!VirtualQuery` at `0x180008b23`
- `KERNEL32!VirtualQuery` at `0x180008b23`
- `KERNEL32!VirtualProtect` at `0x180008b4e`
- `KERNEL32!VirtualProtect` at `0x180008b78`
- `KERNEL32!VirtualProtect` at `0x180008b4e`
- `KERNEL32!VirtualProtect` at `0x180008b78`

## pseudocode

```c
bool __fastcall SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::VtblMethodSwap(
        __int64 a1,
        int (**a2)(void *, const struct _GUID *, void **),
        __int64 a3)
{
  BOOL v4; // eax
  __int64 v5; // rcx
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+20h] [rbp-38h] BYREF
  __int64 flOldProtect; // [rsp+70h] [rbp+18h] BYREF

  flOldProtect = a3;
  if ( *a2 == HookedIUnknown_QueryInterface )
  {
    LOBYTE(v4) = 1;
  }
  else
  {
    LODWORD(flOldProtect) = 0;
    VirtualQuery(a2, &Buffer, 0x30u);
    if ( (Buffer.Protect & 2) == 0
      && (Buffer.Protect & 0x20) == 0
      && (Buffer.Protect & 0x10) == 0
      && (Buffer.Protect & 1) == 0
      || (v4 = VirtualProtect(a2, 8u, 0x40u, (PDWORD)&flOldProtect)) )
    {
      SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::WriteVtblEntry(v5, a2);
      if ( (flOldProtect & 0x33) != 0 )
        VirtualProtect(a2, 8u, flOldProtect, (PDWORD)&flOldProtect);
      LOBYTE(v4) = 1;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180008af0  mov     [rsp+flOldProtect], r8
0x180008af5  push    rbx
0x180008af6  sub     rsp, 50h
0x180008afa  mov     rbx, rdx
0x180008afd  lea     rax, ?HookedIUnknown_QueryInterface@@YAJPEAXAEBU_GUID@@PEAPEAX@Z; HookedIUnknown_QueryInterface(void *,_GUID const &,void * *)
0x180008b04  cmp     [rdx], rax
0x180008b07  jnz     short loc_180008B0D
0x180008b09  mov     al, 1
0x180008b0b  jmp     short loc_180008B89
0x180008b0d  mov     dword ptr [rsp+58h+flOldProtect], 0
0x180008b15  mov     r8d, 30h ; '0'; dwLength
0x180008b1b  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180008b20  mov     rcx, rbx; lpAddress
0x180008b23  call    cs:__imp_VirtualQuery
0x180008b29  mov     eax, [rsp+58h+Buffer.Protect]
0x180008b2d  test    al, 2
0x180008b2f  jnz     short loc_180008B3D
0x180008b31  test    al, 20h
0x180008b33  jnz     short loc_180008B3D
0x180008b35  test    al, 10h
0x180008b37  jnz     short loc_180008B3D
0x180008b39  test    al, 1
0x180008b3b  jz      short loc_180008B58
0x180008b3d  lea     r9, [rsp+58h+flOldProtect]; lpflOldProtect
0x180008b42  mov     edx, 8; dwSize
0x180008b47  lea     r8d, [rdx+38h]; flNewProtect
0x180008b4b  mov     rcx, rbx; lpAddress
0x180008b4e  call    cs:__imp_VirtualProtect
0x180008b54  test    eax, eax
0x180008b56  jz      short loc_180008B89
0x180008b58  mov     rdx, rbx
0x180008b5b  call    ?WriteVtblEntry@?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@IEAAXPEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@Z; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>::WriteVtblEntry(unsigned __int64 *,long (*)(void *,_GUID const &,void * *))
0x180008b60  mov     r8d, dword ptr [rsp+58h+flOldProtect]; flNewProtect
0x180008b65  test    r8b, 33h
0x180008b69  jz      short loc_180008B7E
0x180008b6b  lea     r9, [rsp+58h+flOldProtect]; lpflOldProtect
0x180008b70  mov     edx, 8; dwSize
0x180008b75  mov     rcx, rbx; lpAddress
0x180008b78  call    cs:__imp_VirtualProtect
0x180008b7e  mov     al, 1
0x180008b80  jmp     short loc_180008B89
0x180008b82  call    ??$LogLineFormat@$0DM@@@YAXW4Severity@Logging@Mso@@AEAY0DM@$$CB_W@Z; LogLineFormat<60>(Mso::Logging::Severity,wchar_t const (&)[60])
0x180008b87  xor     al, al
0x180008b89  add     rsp, 50h
0x180008b8d  pop     rbx
0x180008b8e  retn
0x18002bfac  push    rbp
0x18002bfae  sub     rsp, 20h
0x18002bfb2  mov     rbp, rdx
0x18002bfb5  mov     rax, [rcx]
0x18002bfb8  xor     ecx, ecx
0x18002bfba  cmp     dword ptr [rax], 0C0000005h
0x18002bfc0  setz    cl
0x18002bfc3  mov     eax, ecx
0x18002bfc5  add     rsp, 20h
0x18002bfc9  pop     rbp
0x18002bfca  retn
```
