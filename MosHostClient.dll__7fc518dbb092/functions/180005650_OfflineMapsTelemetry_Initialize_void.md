# OfflineMapsTelemetry::Initialize(void)

- ea: `0x180005650`
- end: `0x180005674`
- name: `?Initialize@OfflineMapsTelemetry@@EEAAXXZ`
- size: `36`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000565d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000565d`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::Initialize(OfflineMapsTelemetry *this)
{
  _OWORD *v1; // rbx

  v1 = (_OWORD *)((char *)this + 24);
  if ( CoCreateGuid((GUID *)((char *)this + 24)) < 0 )
    *v1 = 0;
}

```

## disassembly

```asm
0x180005650  push    rbx
0x180005652  sub     rsp, 20h
0x180005656  lea     rbx, [rcx+18h]
0x18000565a  mov     rcx, rbx; pguid
0x18000565d  call    cs:__imp_CoCreateGuid
0x180005663  test    eax, eax
0x180005665  jns     short loc_18000566E
0x180005667  xorps   xmm0, xmm0
0x18000566a  movdqu  xmmword ptr [rbx], xmm0
0x18000566e  add     rsp, 20h
0x180005672  pop     rbx
0x180005673  retn
```
