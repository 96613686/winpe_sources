# OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(void)

- ea: `0x1800080cc`
- end: `0x180008195`
- name: `??$Start@$$V@ClientOpenConnectionActivity@OfflineMapsTelemetry@@SA?AV01@XZ`
- size: `201`
- prototype: `OfflineMapsTelemetry::ClientOpenConnectionActivity *__fastcall(OfflineMapsTelemetry::ClientOpenConnectionActivity *this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a810`
- `0x18000d760`
- `0x18000f0c0`
- `0x18000fdb0`

## callees

- `0x180002fc4`
- `0x18000b28c`

## string_xrefs

- `0x1800080f1`: `ClientOpenConnectionActivity`

## pseudocode

```c
OfflineMapsTelemetry::ClientOpenConnectionActivity *__fastcall OfflineMapsTelemetry::ClientOpenConnectionActivity::Start<>(
        OfflineMapsTelemetry::ClientOpenConnectionActivity *this)
{
  char *v2; // rbx
  _QWORD *v3; // rcx

  v2 = (char *)this + 8;
  *((_DWORD *)this + 2) = 0;
  *((_BYTE *)this + 12) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = "ClientOpenConnectionActivity";
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 20) = 0;
  v3 = (_QWORD *)((char *)this + 88);
  v3[19] = 0;
  v3[20] = 0;
  memset_0(v3, 0, 0x98u);
  *((_DWORD *)v2 + 62) = 1;
  *((_QWORD *)v2 + 32) = 0;
  *((_QWORD *)this + 34) = v2;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = this;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = (char *)this + 48;
  *((_BYTE *)this + 328) = 0;
  *(_QWORD *)this = &OfflineMapsTelemetry::ClientOpenConnectionActivity::`vftable';
  OfflineMapsTelemetry::ClientOpenConnectionActivity::StartActivity(this);
  return this;
}

```

## disassembly

```asm
0x1800080cc  mov     [rsp+arg_0], rbx
0x1800080d1  mov     [rsp+arg_8], rsi
0x1800080d6  push    rdi
0x1800080d7  sub     rsp, 20h
0x1800080db  mov     rdi, rcx
0x1800080de  lea     rbx, [rcx+8]
0x1800080e2  xor     esi, esi
0x1800080e4  mov     [rbx], esi
0x1800080e6  mov     [rbx+4], sil
0x1800080ea  mov     [rbx+40h], sil
0x1800080ee  mov     [rbx+28h], esi
0x1800080f1  lea     rax, aClientopenconn; "ClientOpenConnectionActivity"
0x1800080f8  mov     [rbx+30h], rax
0x1800080fc  mov     [rbx+38h], rsi
0x180008100  mov     [rbx+48h], esi
0x180008103  lea     rcx, [rbx+50h]; void *
0x180008107  mov     [rcx+98h], rsi
0x18000810e  mov     [rcx+0A0h], rsi
0x180008115  xor     edx, edx; Val
0x180008117  mov     r8d, 98h; Size
0x18000811d  call    memset_0
0x180008122  mov     dword ptr [rbx+0F8h], 1
0x18000812c  xor     eax, eax
0x18000812e  mov     [rbx+100h], rax
0x180008135  mov     [rdi+110h], rbx
0x18000813c  mov     [rdi+118h], rsi
0x180008143  mov     [rdi+120h], rsi
0x18000814a  mov     [rdi+128h], rdi
0x180008151  mov     [rdi+130h], rsi
0x180008158  mov     [rdi+138h], esi
0x18000815e  lea     rax, [rdi+30h]
0x180008162  mov     [rdi+140h], rax
0x180008169  mov     [rdi+148h], sil
0x180008170  lea     rax, ??_7ClientOpenConnectionActivity@OfflineMapsTelemetry@@6B@; const OfflineMapsTelemetry::ClientOpenConnectionActivity::`vftable'
0x180008177  mov     [rdi], rax
0x18000817a  mov     rcx, rdi; this
0x18000817d  call    ?StartActivity@ClientOpenConnectionActivity@OfflineMapsTelemetry@@QEAAXXZ; OfflineMapsTelemetry::ClientOpenConnectionActivity::StartActivity(void)
0x180008182  mov     rax, rdi
0x180008185  mov     rbx, [rsp+28h+arg_0]
0x18000818a  mov     rsi, [rsp+28h+arg_8]
0x18000818f  add     rsp, 20h
0x180008193  pop     rdi
0x180008194  retn
```
