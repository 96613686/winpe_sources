# MultiSourceMatcher::~MultiSourceMatcher(void)

- ea: `0x1800ceb78`
- end: `0x1800cec00`
- name: `??1MultiSourceMatcher@@EEAA@XZ`
- size: `136`
- prototype: `void __fastcall(MultiSourceMatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800ceda0`

## callees

- `0x1800095c8`
- `0x18000a460`
- `0x180018e9c`
- `0x1800ceb78`
- `0x1800d0aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cebd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cebe4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cebd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cebe4`

## pseudocode

```c
void __fastcall MultiSourceMatcher::~MultiSourceMatcher(MultiSourceMatcher *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9

  *(_QWORD *)this = &MultiSourceMatcher::`vftable';
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids, this);
  MultiSourceMatcher::_Reset(this);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 200);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16, v2, v3, v4);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800ceb78  push    rbx
0x1800ceb7a  sub     rsp, 20h
0x1800ceb7e  lea     rax, ??_7MultiSourceMatcher@@6B@; const MultiSourceMatcher::`vftable'
0x1800ceb85  mov     rbx, rcx
0x1800ceb88  mov     [rcx], rax
0x1800ceb8b  cmp     cs:byte_18010EC4D, 8
0x1800ceb92  jb      short loc_1800CEBB6
0x1800ceb94  mov     r9, rcx
0x1800ceb97  lea     r8, WPP_e8cfc9bd2e5b37e85ccd5ec8033fc744_Traceguids
0x1800ceb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceba5  mov     edx, 0Fh
0x1800cebaa  mov     rcx, [rcx+0D8h]
0x1800cebb1  call    WPP_SF_q
0x1800cebb6  mov     rcx, rbx; this
0x1800cebb9  call    ?_Reset@MultiSourceMatcher@@AEAAXXZ; MultiSourceMatcher::_Reset(void)
0x1800cebbe  lea     rcx, [rbx+0C8h]; void *
0x1800cebc5  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800cebca  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800cebd1  call    cs:__imp_DeleteCriticalSection
0x1800cebd7  lea     rcx, [rbx+40h]; void *
0x1800cebdb  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800cebe0  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800cebe4  call    cs:__imp_DeleteCriticalSection
0x1800cebea  lea     rcx, [rbx+10h]
0x1800cebee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cebf3  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800cebfa  add     rsp, 20h
0x1800cebfe  pop     rbx
0x1800cebff  retn
```
