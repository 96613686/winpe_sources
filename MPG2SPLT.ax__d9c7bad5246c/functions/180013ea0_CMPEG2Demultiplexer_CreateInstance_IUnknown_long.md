# CMPEG2Demultiplexer::CreateInstance(IUnknown *,long *)

- ea: `0x180013ea0`
- end: `0x180013f13`
- name: `?CreateInstance@CMPEG2Demultiplexer@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `115`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001008`
- `0x180012acc`
- `0x180013ea0`
- `0x180034010`

## pseudocode

```c
struct CUnknown *__fastcall CMPEG2Demultiplexer::CreateInstance(struct IUnknown *a1, int *a2)
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
  v6 = CMPEG2Demultiplexer::CMPEG2Demultiplexer(v4, v5, a1, &CLSID_MPEG2Demultiplexer, a2);
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
0x180013ea0  mov     [rsp+arg_0], rbx
0x180013ea5  push    rdi
0x180013ea6  sub     rsp, 30h
0x180013eaa  mov     rdi, rcx
0x180013ead  mov     rbx, rdx
0x180013eb0  mov     ecx, 5E8h; Size
0x180013eb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013eba  test    rax, rax
0x180013ebd  jz      short loc_180013EE0
0x180013ebf  lea     r9, CLSID_MPEG2Demultiplexer; struct _GUID *
0x180013ec6  mov     [rsp+38h+var_18], rbx; int *
0x180013ecb  mov     r8, rdi; struct IUnknown *
0x180013ece  mov     rcx, rax; this
0x180013ed1  call    ??0CMPEG2Demultiplexer@@QEAA@PEBGPEAUIUnknown@@AEBU_GUID@@PEAJ@Z; CMPEG2Demultiplexer::CMPEG2Demultiplexer(ushort const *,IUnknown *,_GUID const &,long *)
0x180013ed6  mov     rcx, rax
0x180013ed9  test    rax, rax
0x180013edc  jz      short loc_180013EE2
0x180013ede  jmp     short loc_180013EE8
0x180013ee0  xor     ecx, ecx
0x180013ee2  mov     dword ptr [rbx], 8007000Eh
0x180013ee8  cmp     dword ptr [rbx], 0
0x180013eeb  jge     short loc_180013F05
0x180013eed  test    rcx, rcx
0x180013ef0  jz      short loc_180013F03
0x180013ef2  mov     rax, [rcx]
0x180013ef5  mov     edx, 1
0x180013efa  mov     rax, [rax+18h]
0x180013efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f03  xor     ecx, ecx
0x180013f05  mov     rbx, [rsp+38h+arg_0]
0x180013f0a  mov     rax, rcx
0x180013f0d  add     rsp, 30h
0x180013f11  pop     rdi
0x180013f12  retn
```
