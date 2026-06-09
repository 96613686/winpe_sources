# CMPEG2Demultiplexer::CreateInstance_NoClock(IUnknown *,long *)

- ea: `0x180013f20`
- end: `0x180013f93`
- name: `?CreateInstance_NoClock@CMPEG2Demultiplexer@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `115`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001008`
- `0x180012acc`
- `0x180013f20`
- `0x180034010`

## pseudocode

```c
struct CUnknown *__fastcall CMPEG2Demultiplexer::CreateInstance_NoClock(struct IUnknown *a1, int *a2)
{
  CMPEG2Demultiplexer *v4; // rax
  const unsigned __int16 *v5; // rdx
  CMPEG2Demultiplexer *v6; // rcx

  v4 = (CMPEG2Demultiplexer *)operator new(0x5E8u);
  if ( !v4 )
  {
    v6 = 0;
    goto LABEL_5;
  }
  v6 = CMPEG2Demultiplexer::CMPEG2Demultiplexer(v4, v5, a1, &CLSID_MPEG2Demultiplexer_NoClock, a2);
  if ( !v6 )
LABEL_5:
    *a2 = -2147024882;
  if ( *a2 < 0 )
  {
    if ( v6 )
      (*(void (__fastcall **)(CMPEG2Demultiplexer *, __int64))(*(_QWORD *)v6 + 24LL))(v6, 1);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180013f20  mov     [rsp+arg_0], rbx
0x180013f25  push    rdi
0x180013f26  sub     rsp, 30h
0x180013f2a  mov     rdi, rcx
0x180013f2d  mov     rbx, rdx
0x180013f30  mov     ecx, 5E8h; Size
0x180013f35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013f3a  test    rax, rax
0x180013f3d  jz      short loc_180013F60
0x180013f3f  lea     r9, CLSID_MPEG2Demultiplexer_NoClock; struct _GUID *
0x180013f46  mov     [rsp+38h+var_18], rbx; int *
0x180013f4b  mov     r8, rdi; struct IUnknown *
0x180013f4e  mov     rcx, rax; this
0x180013f51  call    ??0CMPEG2Demultiplexer@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z; CMPEG2Demultiplexer::CMPEG2Demultiplexer(ushort const *,IUnknown *,_GUID const &,long *)
0x180013f56  mov     rcx, rax
0x180013f59  test    rax, rax
0x180013f5c  jz      short loc_180013F62
0x180013f5e  jmp     short loc_180013F68
0x180013f60  xor     ecx, ecx
0x180013f62  mov     dword ptr [rbx], 8007000Eh
0x180013f68  cmp     dword ptr [rbx], 0
0x180013f6b  jge     short loc_180013F85
0x180013f6d  test    rcx, rcx
0x180013f70  jz      short loc_180013F83
0x180013f72  mov     rax, [rcx]
0x180013f75  mov     edx, 1
0x180013f7a  mov     rax, [rax+18h]
0x180013f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f83  xor     ecx, ecx
0x180013f85  mov     rbx, [rsp+38h+arg_0]
0x180013f8a  mov     rax, rcx
0x180013f8d  add     rsp, 30h
0x180013f91  pop     rdi
0x180013f92  retn
```
