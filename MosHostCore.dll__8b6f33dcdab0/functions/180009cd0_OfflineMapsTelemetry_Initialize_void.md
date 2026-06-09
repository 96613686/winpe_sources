# OfflineMapsTelemetry::Initialize(void)

- ea: `0x180009cd0`
- end: `0x180009cf4`
- name: `?Initialize@OfflineMapsTelemetry@@EEAAXXZ`
- size: `36`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009cd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180009cdd`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180009cdd`

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
0x180009cd0  push    rbx
0x180009cd2  sub     rsp, 20h
0x180009cd6  lea     rbx, [rcx+18h]
0x180009cda  mov     rcx, rbx; pguid
0x180009cdd  call    cs:__imp_CoCreateGuid
0x180009ce3  test    eax, eax
0x180009ce5  jns     short loc_180009CEE
0x180009ce7  xorps   xmm0, xmm0
0x180009cea  movdqu  xmmword ptr [rbx], xmm0
0x180009cee  add     rsp, 20h
0x180009cf2  pop     rbx
0x180009cf3  retn
```
