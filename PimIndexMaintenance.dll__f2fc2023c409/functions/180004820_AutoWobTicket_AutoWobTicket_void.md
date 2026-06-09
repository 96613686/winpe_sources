# AutoWobTicket::~AutoWobTicket(void)

- ea: `0x180004820`
- end: `0x180004852`
- name: `??1AutoWobTicket@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(AutoWobTicket *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180007968`

## callees

- `0x180002da8`
- `0x180004820`

## import_xrefs

- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180004829`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x180004829`

## string_xrefs

- `0x180004837`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
void __fastcall AutoWobTicket::~AutoWobTicket(AutoWobTicket *this)
{
  int v1; // eax

  if ( *(_BYTE *)this )
  {
    v1 = RtlClearThreadWorkOnBehalfTicket();
    if ( v1 < 0 )
      Log_HREvent(
        v1 | 0x10000000u,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        92);
  }
}

```

## disassembly

```asm
0x180004820  sub     rsp, 38h
0x180004824  cmp     byte ptr [rcx], 0
0x180004827  jz      short loc_18000484D
0x180004829  call    cs:__imp_RtlClearThreadWorkOnBehalfTicket
0x18000482f  test    eax, eax
0x180004831  jns     short loc_18000484D
0x180004833  bts     eax, 1Ch
0x180004837  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000483e  mov     ecx, eax
0x180004840  mov     r9d, 5Ch ; '\'
0x180004846  xor     edx, edx
0x180004848  call    Log_HREvent
0x18000484d  add     rsp, 38h
0x180004851  retn
```
