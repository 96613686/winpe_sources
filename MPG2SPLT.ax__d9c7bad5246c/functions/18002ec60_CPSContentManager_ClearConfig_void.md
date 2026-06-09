# CPSContentManager::ClearConfig_(void)

- ea: `0x18002ec60`
- end: `0x18002ecb1`
- name: `?ClearConfig_@CPSContentManager@@MEAAXXZ`
- size: `81`
- prototype: `void __fastcall(CPSContentManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002e22c`

## callees

- `0x180021df8`
- `0x18002ec60`
- `0x1800303e8`
- `0x180034010`

## pseudocode

```c
void __fastcall CPSContentManager::ClearConfig_(CPSContentManager *this)
{
  struct CDemuxBaseParser *v1; // r8

  v1 = (struct CDemuxBaseParser *)*((_QWORD *)this + 6);
  if ( v1 )
  {
    CMPEG2Controller::UnmapStreamInternal(*((CMPEG2Controller **)this + 3), 0xBAu, v1);
    CPCRRecordBufferSource::RegisterIPCRValueNotify(*((CPCRRecordBufferSource **)this + 5), 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x18002ec60  push    rbx
0x18002ec62  sub     rsp, 20h
0x18002ec66  mov     r8, [rcx+30h]; struct CDemuxBaseParser *
0x18002ec6a  mov     rbx, rcx
0x18002ec6d  test    r8, r8
0x18002ec70  jz      short loc_18002ECAB
0x18002ec72  mov     rcx, [rcx+18h]; this
0x18002ec76  mov     edx, 0BAh; unsigned int
0x18002ec7b  call    ?UnmapStreamInternal@CMPEG2Controller@@QEAAJK_K@Z; CMPEG2Controller::UnmapStreamInternal(ulong,unsigned __int64)
0x18002ec80  mov     rcx, [rbx+28h]; this
0x18002ec84  xor     edx, edx; struct CIPCRValueNotify *
0x18002ec86  call    ?RegisterIPCRValueNotify@CPCRRecordBufferSource@@QEAAXPEAVCIPCRValueNotify@@@Z; CPCRRecordBufferSource::RegisterIPCRValueNotify(CIPCRValueNotify *)
0x18002ec8b  mov     rcx, [rbx+28h]
0x18002ec8f  mov     rax, [rcx]
0x18002ec92  mov     rax, [rax+10h]
0x18002ec96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec9b  mov     qword ptr [rbx+28h], 0
0x18002eca3  mov     qword ptr [rbx+30h], 0
0x18002ecab  add     rsp, 20h
0x18002ecaf  pop     rbx
0x18002ecb0  retn
```
