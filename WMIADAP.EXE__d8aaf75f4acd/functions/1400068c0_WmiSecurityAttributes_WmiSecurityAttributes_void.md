# WmiSecurityAttributes::~WmiSecurityAttributes(void)

- ea: `0x1400068c0`
- end: `0x140006910`
- name: `??1WmiSecurityAttributes@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(WmiSecurityAttributes *this, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400076bc`
- `0x14000b2e4`
- `0x1400153e1`
- `0x14001598f`

## callees

- `0x1400067e8`
- `0x140006820`
- `0x1400068c0`
- `0x140006a18`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400068ef`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400068ef`

## pseudocode

```c
void __fastcall WmiSecurityAttributes::~WmiSecurityAttributes(WmiSecurityAttributes *this, unsigned int a2)
{
  WmiSecurity *v3; // rcx
  void *v4; // rcx
  unsigned int v5; // edx

  v3 = (WmiSecurity *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    WmiSecurity::`scalar deleting destructor'(v3, a2);
  v4 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  CWin32DefaultArena::WbemMemFree(v4);
  __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>((_QWORD *)this + 2, v5);
  __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(this);
}

```

## disassembly

```asm
0x1400068c0  mov     [rsp+arg_0], rbx
0x1400068c5  push    rdi
0x1400068c6  sub     rsp, 20h
0x1400068ca  mov     rbx, rcx
0x1400068cd  mov     rcx, [rcx+18h]; this
0x1400068d1  mov     qword ptr [rbx+18h], 0
0x1400068d9  test    rcx, rcx
0x1400068dc  jz      short loc_1400068E3
0x1400068de  call    ??_GWmiSecurity@@QEAAPEAXI@Z; WmiSecurity::`scalar deleting destructor'(uint)
0x1400068e3  mov     rcx, [rbx+8]
0x1400068e7  mov     qword ptr [rbx+8], 0
0x1400068ef  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400068f5  lea     rcx, [rbx+10h]
0x1400068f9  call    ??1?$__Wrapper@VWmiSecurity@@@@UEAA@XZ; __Wrapper<WmiSecurity>::~__Wrapper<WmiSecurity>(void)
0x1400068fe  mov     rcx, rbx
0x140006901  mov     rbx, [rsp+28h+arg_0]
0x140006906  add     rsp, 20h
0x14000690a  pop     rdi
0x14000690b  jmp     ??1?$__Wrapper@U_SECURITY_ATTRIBUTES@@@@UEAA@XZ; __Wrapper<_SECURITY_ATTRIBUTES>::~__Wrapper<_SECURITY_ATTRIBUTES>(void)
```
