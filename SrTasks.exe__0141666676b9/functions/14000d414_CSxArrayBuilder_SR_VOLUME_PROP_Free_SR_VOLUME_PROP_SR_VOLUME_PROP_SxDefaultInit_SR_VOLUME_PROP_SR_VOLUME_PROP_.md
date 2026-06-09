# CSxArrayBuilder<_SR_VOLUME_PROP,&Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::~CSxArrayBuilder<_SR_VOLUME_PROP,&Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>(void)

- ea: `0x14000d414`
- end: `0x14000d470`
- name: `??1?$CSxArrayBuilder@U_SR_VOLUME_PROP@@$1?Free_SR_VOLUME_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SR_VOLUME_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SR_VOLUME_PROP@@@@YAX00@Z@@AEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000d688`

## callees

- `0x14000d2a4`
- `0x14000d414`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000d44b`
- `ole32!CoTaskMemFree` at `0x14000d44b`

## pseudocode

```c
void __fastcall CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>::~CSxArrayBuilder<_SR_VOLUME_PROP,&void Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *),&void SxDefaultInit<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *),&void SxDefaultTransfer<_SR_VOLUME_PROP>(_SR_VOLUME_PROP *,_SR_VOLUME_PROP *)>(
        __int64 a1)
{
  __int64 v1; // rsi
  LPVOID *i; // rbx

  v1 = 0;
  for ( i = (LPVOID *)(a1 + 8); (unsigned int)v1 < *(_DWORD *)(a1 + 16); v1 = (unsigned int)(v1 + 1) )
    Free_SR_VOLUME_PROP((struct _SR_VOLUME_PROP *)((char *)*i + 48 * v1));
  CoTaskMemFree(*i);
  *i = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x14000d414  mov     [rsp+arg_0], rbx
0x14000d419  mov     [rsp+arg_8], rsi
0x14000d41e  push    rdi
0x14000d41f  sub     rsp, 20h
0x14000d423  xor     esi, esi
0x14000d425  lea     rbx, [rcx+8]
0x14000d429  mov     rdi, rcx
0x14000d42c  cmp     [rcx+10h], esi
0x14000d42f  jbe     short loc_14000D448
0x14000d431  lea     rcx, [rsi+rsi*2]
0x14000d435  shl     rcx, 4
0x14000d439  add     rcx, [rbx]; struct _SR_VOLUME_PROP *
0x14000d43c  call    ?Free_SR_VOLUME_PROP@@YAXPEAU_SR_VOLUME_PROP@@@Z; Free_SR_VOLUME_PROP(_SR_VOLUME_PROP *)
0x14000d441  inc     esi
0x14000d443  cmp     esi, [rdi+10h]
0x14000d446  jb      short loc_14000D431
0x14000d448  mov     rcx, [rbx]; pv
0x14000d44b  call    cs:__imp_CoTaskMemFree
0x14000d451  mov     rsi, [rsp+28h+arg_8]
0x14000d456  mov     qword ptr [rbx], 0
0x14000d45d  mov     rbx, [rsp+28h+arg_0]
0x14000d462  mov     qword ptr [rdi+10h], 0
0x14000d46a  add     rsp, 20h
0x14000d46e  pop     rdi
0x14000d46f  retn
```
