# xgc::GDIExporter::GDIExporter(xpsrdr::RenderState &)

- ea: `0x1800166d8`
- end: `0x18001678d`
- name: `??0GDIExporter@xgc@@QEAA@AEAURenderState@xpsrdr@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(xgc::GDIExporter *__hidden this, struct xpsrdr::RenderState *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e25c`

## callees

- `0x180008854`
- `0x18000e15c`
- `0x18000e174`
- `0x180016048`
- `0x18001d1ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180016778`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x180016778`
- `KERNEL32!GetTickCount64` at `0x180016766`
- `KERNEL32!GetTickCount64` at `0x180016766`
- `KERNEL32!GetCurrentThreadId` at `0x18001676f`
- `KERNEL32!GetCurrentThreadId` at `0x18001676f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
xgc::GDIExporter *__fastcall xgc::GDIExporter::GDIExporter(xgc::GDIExporter *this, struct xpsrdr::RenderState *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdx
  DWORD CurrentThreadId; // eax
  _QWORD *v8; // [rsp+38h] [rbp+10h]

  *(_QWORD *)this = 0;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>((char *)this + 8);
  *((_QWORD *)this + 3) = v4;
  std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>((char *)this + 32);
  xgc::GDIFonts::GDIFonts((BYTE *)this + 48);
  v8 = operator new(0x40u);
  *v8 = a2;
  std::vector<CCoordinate>::vector<CCoordinate>(v8 + 1, v8);
  *(_DWORD *)(v5 + 32) = 1065353216;
  *(_DWORD *)(v5 + 36) = 1065353216;
  *(_DWORD *)(v5 + 40) = 1;
  *(_QWORD *)(v5 + 48) = 0;
  *(_DWORD *)(v5 + 56) = 0;
  std::shared_ptr<SolidPathCluster>::shared_ptr<SolidPathCluster>((char *)this + 88);
  *((_QWORD *)this + 10) = 0;
  LODWORD(a2) = GetTickCount64();
  CurrentThreadId = GetCurrentThreadId();
  _o_srand((unsigned int)a2 + CurrentThreadId);
  return this;
}

```

## disassembly

```asm
0x1800166d8  mov     [rsp+arg_10], rbx
0x1800166dd  mov     [rsp+arg_0], rcx
0x1800166e2  push    rdi
0x1800166e3  sub     rsp, 20h
0x1800166e7  mov     rbx, rdx
0x1800166ea  mov     rdi, rcx
0x1800166ed  mov     qword ptr [rcx], 0
0x1800166f4  add     rcx, 8
0x1800166f8  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x1800166fd  nop
0x1800166fe  mov     [rdi+18h], rdx
0x180016702  lea     rcx, [rdi+20h]
0x180016706  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x18001670b  nop
0x18001670c  lea     rcx, [rdi+30h]; this
0x180016710  call    ??0GDIFonts@xgc@@QEAA@XZ; xgc::GDIFonts::GDIFonts(void)
0x180016715  nop
0x180016716  mov     ecx, 40h ; '@'; Size
0x18001671b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016720  mov     rdx, rax
0x180016723  mov     [rsp+28h+arg_8], rax
0x180016728  mov     [rax], rbx
0x18001672b  lea     rcx, [rax+8]
0x18001672f  call    ??0?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::vector<CCoordinate>(void)
0x180016734  mov     eax, 3F800000h
0x180016739  mov     [rdx+20h], eax
0x18001673c  mov     [rdx+24h], eax
0x18001673f  mov     dword ptr [rdx+28h], 1
0x180016746  mov     qword ptr [rdx+30h], 0
0x18001674e  mov     dword ptr [rdx+38h], 0
0x180016755  lea     rcx, [rdi+58h]
0x180016759  call    ??$?0VSolidPathCluster@@$0A@@?$shared_ptr@VSolidPathCluster@@@std@@QEAA@PEAVSolidPathCluster@@@Z; std::shared_ptr<SolidPathCluster>::shared_ptr<SolidPathCluster>(SolidPathCluster *)
0x18001675e  mov     qword ptr [rdi+50h], 0
0x180016766  call    cs:__imp_GetTickCount64
0x18001676c  mov     rbx, rax
0x18001676f  call    cs:__imp_GetCurrentThreadId
0x180016775  lea     ecx, [rbx+rax]
0x180016778  call    cs:__imp__o_srand
0x18001677e  nop
0x18001677f  mov     rax, rdi
0x180016782  mov     rbx, [rsp+28h+arg_10]
0x180016787  add     rsp, 20h
0x18001678b  pop     rdi
0x18001678c  retn
```
