# OfflineMapsTelemetry::Initialize(void)

- ea: `0x180008210`
- end: `0x180008234`
- name: `?Initialize@OfflineMapsTelemetry@@EEAAXXZ`
- size: `36`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000821d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000821d`

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
0x180008210  push    rbx
0x180008212  sub     rsp, 20h
0x180008216  lea     rbx, [rcx+18h]
0x18000821a  mov     rcx, rbx; pguid
0x18000821d  call    cs:__imp_CoCreateGuid
0x180008223  test    eax, eax
0x180008225  jns     short loc_18000822E
0x180008227  xorps   xmm0, xmm0
0x18000822a  movdqu  xmmword ptr [rbx], xmm0
0x18000822e  add     rsp, 20h
0x180008232  pop     rbx
0x180008233  retn
```
