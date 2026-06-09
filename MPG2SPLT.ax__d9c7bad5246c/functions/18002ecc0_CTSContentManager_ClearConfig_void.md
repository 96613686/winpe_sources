# CTSContentManager::ClearConfig_(void)

- ea: `0x18002ecc0`
- end: `0x18002ed94`
- name: `?ClearConfig_@CTSContentManager@@MEAAXXZ`
- size: `212`
- prototype: `void __fastcall(CTSContentManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18002e264`

## callees

- `0x180001048`
- `0x180021df8`
- `0x18002e424`
- `0x18002ec18`
- `0x18002ecc0`
- `0x180030668`
- `0x180030c68`
- `0x180030f74`

## pseudocode

```c
void __fastcall CTSContentManager::ClearConfig_(CTSContentManager *this)
{
  struct CDemuxBaseParser *v1; // r8
  CMPEG2PSISectionBufferSource *v3; // rcx
  _QWORD *v4; // rdx
  __int64 v5; // rax
  char *v6; // rsi
  _QWORD *v7; // rdi
  CTSProgram *v8; // rbx
  CTSProgram *v9; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct CDemuxBaseParser *)*((_QWORD *)this + 8);
  v9 = 0;
  *((_DWORD *)this + 394) = 0;
  if ( v1 )
  {
    CMPEG2Controller::UnmapStreamInternal(*((CMPEG2Controller **)this + 3), 0, v1);
    v3 = (CMPEG2PSISectionBufferSource *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 8) = 0;
    CMPEG2PSISectionBufferSource::Clear(v3);
    CTSContentManager::UnregisterKnownStream(this, *((struct SINGULAR_STREAM **)this + 12));
    v4 = (_QWORD *)*((_QWORD *)this + 12);
    v5 = *((_QWORD *)this + 9);
    v6 = (char *)this + 224;
    v7 = (_QWORD *)((char *)this + 592);
    *v4 = v5;
    v4[1] = (char *)this + 72;
    *(_QWORD *)(v5 + 8) = v4;
    *((_QWORD *)this + 9) = v4;
    *((_QWORD *)this + 12) = 0;
    while ( (_QWORD *)*v7 != v7 )
    {
      TGenericMap<unsigned __int64,unsigned long,0,5,19>::RemoveFirst(v6, &v9);
      v8 = v9;
      CTSProgram::Shutdown(v9);
      if ( v8 )
      {
        CTSProgram::~CTSProgram(v8);
        operator delete(v8);
      }
    }
  }
}

```

## disassembly

```asm
0x18002ecc0  mov     [rsp+arg_8], rbx
0x18002ecc5  mov     [rsp+arg_10], rsi
0x18002ecca  push    rdi
0x18002eccb  sub     rsp, 20h
0x18002eccf  mov     r8, [rcx+40h]; struct CDemuxBaseParser *
0x18002ecd3  mov     rbx, rcx
0x18002ecd6  mov     [rsp+28h+arg_0], 0
0x18002ecdf  mov     dword ptr [rcx+628h], 0
0x18002ece9  test    r8, r8
0x18002ecec  jz      loc_18002ED84
0x18002ecf2  mov     rcx, [rcx+18h]; this
0x18002ecf6  xor     edx, edx; unsigned int
0x18002ecf8  call    ?UnmapStreamInternal@CMPEG2Controller@@QEAAJK_K@Z; CMPEG2Controller::UnmapStreamInternal(ulong,unsigned __int64)
0x18002ecfd  mov     rcx, [rbx+38h]; this
0x18002ed01  mov     qword ptr [rbx+40h], 0
0x18002ed09  call    ?Clear@CMPEG2PSISectionBufferSource@@QEAAXXZ; CMPEG2PSISectionBufferSource::Clear(void)
0x18002ed0e  mov     rdx, [rbx+60h]; struct SINGULAR_STREAM *
0x18002ed12  mov     rcx, rbx; this
0x18002ed15  call    ?UnregisterKnownStream@CTSContentManager@@QEAAJPEAUSINGULAR_STREAM@@@Z; CTSContentManager::UnregisterKnownStream(SINGULAR_STREAM *)
0x18002ed1a  mov     rdx, [rbx+60h]
0x18002ed1e  lea     rcx, [rbx+48h]
0x18002ed22  mov     rax, [rcx]
0x18002ed25  lea     rsi, [rbx+0E0h]
0x18002ed2c  lea     rdi, [rsi+170h]
0x18002ed33  mov     [rdx], rax
0x18002ed36  mov     [rdx+8], rcx
0x18002ed3a  mov     [rax+8], rdx
0x18002ed3e  mov     [rcx], rdx
0x18002ed41  mov     qword ptr [rbx+60h], 0
0x18002ed49  cmp     [rdi], rdi
0x18002ed4c  jz      short loc_18002ED84
0x18002ed4e  lea     rdx, [rsp+28h+arg_0]
0x18002ed53  mov     rcx, rsi
0x18002ed56  call    ?RemoveFirst@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::RemoveFirst(unsigned __int64 *)
0x18002ed5b  mov     rbx, [rsp+28h+arg_0]
0x18002ed60  mov     rcx, rbx; this
0x18002ed63  call    ?Shutdown@CTSProgram@@QEAAJXZ; CTSProgram::Shutdown(void)
0x18002ed68  test    rbx, rbx
0x18002ed6b  jz      short loc_18002ED49
0x18002ed6d  mov     rcx, rbx; this
0x18002ed70  call    ??1CTSProgram@@QEAA@XZ; CTSProgram::~CTSProgram(void)
0x18002ed75  mov     edx, 3B8h; unsigned __int64
0x18002ed7a  mov     rcx, rbx; void *
0x18002ed7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ed82  jmp     short loc_18002ED49
0x18002ed84  mov     rbx, [rsp+28h+arg_8]
0x18002ed89  mov     rsi, [rsp+28h+arg_10]
0x18002ed8e  add     rsp, 20h
0x18002ed92  pop     rdi
0x18002ed93  retn
```
