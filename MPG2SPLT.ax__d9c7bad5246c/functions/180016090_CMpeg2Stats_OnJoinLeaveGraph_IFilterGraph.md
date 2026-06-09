# CMpeg2Stats::OnJoinLeaveGraph(IFilterGraph *)

- ea: `0x180016090`
- end: `0x180016174`
- name: `?OnJoinLeaveGraph@CMpeg2Stats@@QEAAXPEAUIFilterGraph@@@Z`
- size: `228`
- prototype: `void __fastcall(CMpeg2Stats *__hidden this, struct IFilterGraph *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015650`

## callees

- `0x180011ef4`
- `0x180016090`
- `0x180034010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800160f5`
- `ole32!CoCreateInstance` at `0x1800160f5`

## pseudocode

```c
void __fastcall CMpeg2Stats::OnJoinLeaveGraph(CMpeg2Stats *this, struct IFilterGraph *a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  void (__fastcall *v7)(__int64, __int128 *, struct IFilterGraph *); // rax
  __int64 v8; // rdi
  __int128 v9; // [rsp+30h] [rbp-18h] BYREF

  Mpeg2DemuxTrace::CeHomeETWProvider::Initialize((CMpeg2Stats *)((char *)this + 8256), a2);
  v4 = (__int64 *)((char *)this + 9512);
  v5 = *((_QWORD *)this + 1189);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *v4 = 0;
  }
  if ( a2 )
  {
    CoCreateInstance(
      &GUID_ed233797_f47d_475e_9fca_3d549e4ddaa4,
      0,
      0x17u,
      &GUID_607aef69_87f1_49a9_8fdb_48ee72bbe477,
      (LPVOID *)this + 1189);
    v6 = *v4;
    if ( *v4 )
    {
      v7 = *(void (__fastcall **)(__int64, __int128 *, struct IFilterGraph *))(*(_QWORD *)v6 + 24LL);
      v9 = xmmword_18003A380;
      v7(v6, &v9, a2);
      v8 = *v4;
      if ( v8 )
      {
        if ( *(_QWORD *)this )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
        *(_QWORD *)this = 0;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v8 + 32LL))(v8, 0, 127);
      }
    }
  }
}

```

## disassembly

```asm
0x180016090  mov     [rsp+arg_0], rbx
0x180016095  mov     [rsp+arg_8], rsi
0x18001609a  push    rdi
0x18001609b  sub     rsp, 40h
0x18001609f  mov     rbx, rcx
0x1800160a2  mov     rsi, rdx
0x1800160a5  add     rcx, 2040h; this
0x1800160ac  call    ?Initialize@CeHomeETWProvider@Mpeg2DemuxTrace@@QEAAXPEAUIFilterGraph@@@Z; Mpeg2DemuxTrace::CeHomeETWProvider::Initialize(IFilterGraph *)
0x1800160b1  lea     rdi, [rbx+2528h]
0x1800160b8  mov     rcx, [rdi]
0x1800160bb  test    rcx, rcx
0x1800160be  jz      short loc_1800160D3
0x1800160c0  mov     rax, [rcx]
0x1800160c3  mov     rax, [rax+10h]
0x1800160c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160cc  mov     qword ptr [rdi], 0
0x1800160d3  test    rsi, rsi
0x1800160d6  jz      loc_180016164
0x1800160dc  xor     edx, edx; pUnkOuter
0x1800160de  mov     [rsp+48h+ppv], rdi; ppv
0x1800160e3  lea     r9, _GUID_607aef69_87f1_49a9_8fdb_48ee72bbe477; riid
0x1800160ea  lea     rcx, _GUID_ed233797_f47d_475e_9fca_3d549e4ddaa4; rclsid
0x1800160f1  lea     r8d, [rdx+17h]; dwClsContext
0x1800160f5  call    cs:__imp_CoCreateInstance
0x1800160fb  mov     rcx, [rdi]
0x1800160fe  test    rcx, rcx
0x180016101  jz      short loc_180016164
0x180016103  mov     rax, [rcx]
0x180016106  lea     rdx, [rsp+48h+var_18]
0x18001610b  movups  xmm0, cs:xmmword_18003A380
0x180016112  mov     r8, rsi
0x180016115  mov     rax, [rax+18h]
0x180016119  movdqu  [rsp+48h+var_18], xmm0
0x18001611f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016124  mov     rdi, [rdi]
0x180016127  test    rdi, rdi
0x18001612a  jz      short loc_180016164
0x18001612c  mov     rcx, [rbx]
0x18001612f  test    rcx, rcx
0x180016132  jz      short loc_180016140
0x180016134  mov     rax, [rcx]
0x180016137  mov     rax, [rax+10h]
0x18001613b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016140  mov     qword ptr [rbx], 0
0x180016147  xor     r9d, r9d
0x18001614a  mov     rax, [rdi]
0x18001614d  xor     edx, edx
0x18001614f  mov     rcx, rdi
0x180016152  mov     [rsp+48h+ppv], rbx
0x180016157  lea     r8d, [r9+7Fh]
0x18001615b  mov     rax, [rax+20h]
0x18001615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016164  mov     rbx, [rsp+48h+arg_0]
0x180016169  mov     rsi, [rsp+48h+arg_8]
0x18001616e  add     rsp, 40h
0x180016172  pop     rdi
0x180016173  retn
```
