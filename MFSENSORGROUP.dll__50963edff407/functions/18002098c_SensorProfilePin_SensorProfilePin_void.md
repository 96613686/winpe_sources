# SensorProfilePin::~SensorProfilePin(void)

- ea: `0x18002098c`
- end: `0x1800209f8`
- name: `??1SensorProfilePin@@MEAA@XZ`
- size: `108`
- prototype: `void __fastcall(SensorProfilePin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020950`

## callees

- `0x1800093b0`
- `0x18000aa08`
- `0x18002098c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800209c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800209c1`

## pseudocode

```c
void __fastcall SensorProfilePin::~SensorProfilePin(SensorProfilePin *this)
{
  *(_QWORD *)this = &SensorProfilePin::`vftable';
  if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_2cbe30c99f7430a33b5237d33388f6ca_Traceguids, this);
  CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>((char *)this + 144);
  CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _InterlockedDecrement(&mfsensorgroup_utils::g_cRefModule);
}

```

## disassembly

```asm
0x18002098c  push    rbx
0x18002098e  sub     rsp, 20h
0x180020992  lea     rax, ??_7SensorProfilePin@@6B@; const SensorProfilePin::`vftable'
0x180020999  mov     rbx, rcx
0x18002099c  mov     [rcx], rax
0x18002099f  cmp     cs:byte_18008D62D, 10h
0x1800209a6  jnb     short loc_1800209D4
0x1800209a8  lea     rcx, [rbx+90h]
0x1800209af  call    ??1?$CTUnkArray@UIMFSensorProfileBlockedControl@@@@QEAA@XZ; CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>(void)
0x1800209b4  lea     rcx, [rbx+78h]
0x1800209b8  call    ??1?$CTUnkArray@UIMFSensorProfileBlockedControl@@@@QEAA@XZ; CTUnkArray<IMFSensorProfileBlockedControl>::~CTUnkArray<IMFSensorProfileBlockedControl>(void)
0x1800209bd  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800209c1  call    cs:__imp_DeleteCriticalSection
0x1800209c7  lock dec cs:?g_cRefModule@mfsensorgroup_utils@@3JA; long mfsensorgroup_utils::g_cRefModule
0x1800209ce  add     rsp, 20h
0x1800209d2  pop     rbx
0x1800209d3  retn
0x1800209d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800209db  lea     r8, WPP_2cbe30c99f7430a33b5237d33388f6ca_Traceguids
0x1800209e2  mov     edx, 17h
0x1800209e7  mov     r9, rbx
0x1800209ea  mov     rcx, [rcx+0D8h]
0x1800209f1  call    WPP_SF_q
0x1800209f6  jmp     short loc_1800209A8
```
