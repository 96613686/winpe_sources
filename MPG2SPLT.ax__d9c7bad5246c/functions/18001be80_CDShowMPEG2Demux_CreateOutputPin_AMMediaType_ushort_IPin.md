# CDShowMPEG2Demux::CreateOutputPin(_AMMediaType *,ushort *,IPin * *)

- ea: `0x18001be80`
- end: `0x18001bf6c`
- name: `?CreateOutputPin@CDShowMPEG2Demux@@UEAAJPEAU_AMMediaType@@PEAGPEAPEAUIPin@@@Z`
- size: `236`
- prototype: `int(CDShowMPEG2Demux *__hidden this, struct _AMMediaType *, unsigned __int16 *, struct IPin **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180013f9c`
- `0x18001be80`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CDShowMPEG2Demux::CreateOutputPin(
        CMPEG2Demultiplexer **this,
        struct _AMMediaType *a2,
        struct _AMMediaType *a3,
        struct IPin **a4)
{
  unsigned __int64 v6; // rcx
  int v7; // esi
  volatile signed __int32 *v8; // rbx
  struct IPin *v9; // rcx
  struct DEMUX_PIN_RECORD *v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  if ( !LOWORD(a3->majortype.Data1) )
    return 2147942487LL;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)&a3->majortype.Data1 + v6) );
  if ( v6 >= 0x80 )
    return 2147942487LL;
  v7 = CMPEG2Demultiplexer::CreateOutputPin_(this[3], a3, a2, &v11);
  if ( v7 < 0 )
  {
    *a4 = 0;
  }
  else
  {
    v8 = (volatile signed __int32 *)v11;
    v9 = (struct IPin *)((*(_QWORD *)v11 + 24LL) & -(__int64)(*(_QWORD *)v11 != 0));
    *a4 = v9;
    ((void (__fastcall *)(struct IPin *))v9->lpVtbl->AddRef)(v9);
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( v8 )
      {
        operator delete(*((void **)v8 + 2));
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v8 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v8 + 8LL));
        operator delete((void *)v8);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001be80  push    rbx
0x18001be82  push    rbp
0x18001be83  push    rsi
0x18001be84  push    rdi
0x18001be85  sub     rsp, 28h
0x18001be89  xor     ebp, ebp
0x18001be8b  mov     rdi, r9
0x18001be8e  mov     [rsp+48h+arg_8], rbp
0x18001be93  mov     rax, r8
0x18001be96  mov     r10, rcx
0x18001be99  test    rdx, rdx
0x18001be9c  jz      loc_18001BF5E
0x18001bea2  test    r9, r9
0x18001bea5  jz      loc_18001BF5E
0x18001beab  test    rax, rax
0x18001beae  jz      loc_18001BF5E
0x18001beb4  cmp     [r8], bp
0x18001beb8  jz      loc_18001BF5E
0x18001bebe  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001bec2  inc     rcx
0x18001bec5  cmp     [r8+rcx*2], bp
0x18001beca  jnz     short loc_18001BEC2
0x18001becc  cmp     rcx, 80h
0x18001bed3  jnb     loc_18001BF5E
0x18001bed9  mov     rcx, [r10+18h]; this
0x18001bedd  lea     r9, [rsp+48h+arg_8]; struct DEMUX_PIN_RECORD **
0x18001bee2  mov     r8, rdx; struct _AMMediaType *
0x18001bee5  mov     rdx, rax; unsigned __int16 *
0x18001bee8  call    ?CreateOutputPin_@CMPEG2Demultiplexer@@AEAAJPEBGPEAU_AMMediaType@@PEAPEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::CreateOutputPin_(ushort const *,_AMMediaType *,DEMUX_PIN_RECORD * *)
0x18001beed  mov     esi, eax
0x18001beef  test    eax, eax
0x18001bef1  js      short loc_18001BF57
0x18001bef3  mov     rbx, [rsp+48h+arg_8]
0x18001bef8  mov     rcx, [rbx]
0x18001befb  lea     rdx, [rcx+18h]
0x18001beff  neg     rcx
0x18001bf02  sbb     rcx, rcx
0x18001bf05  and     rcx, rdx
0x18001bf08  mov     [rdi], rcx
0x18001bf0b  mov     rdx, [rcx]
0x18001bf0e  mov     rax, [rdx+8]
0x18001bf12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf17  or      eax, 0FFFFFFFFh
0x18001bf1a  lock xadd [rbx+8], eax
0x18001bf1f  cmp     eax, 1
0x18001bf22  jnz     short loc_18001BF5A
0x18001bf24  test    rbx, rbx
0x18001bf27  jz      short loc_18001BF5A
0x18001bf29  mov     rcx, [rbx+10h]; void *
0x18001bf2d  lea     edx, [rax+1]; unsigned __int64
0x18001bf30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bf35  mov     rax, [rbx]
0x18001bf38  mov     rcx, [rax+8]
0x18001bf3c  mov     rax, [rcx]
0x18001bf3f  mov     rax, [rax+10h]
0x18001bf43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf48  mov     edx, 18h; unsigned __int64
0x18001bf4d  mov     rcx, rbx; void *
0x18001bf50  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bf55  jmp     short loc_18001BF5A
0x18001bf57  mov     [rdi], rbp
0x18001bf5a  mov     eax, esi
0x18001bf5c  jmp     short loc_18001BF63
0x18001bf5e  mov     eax, 80070057h
0x18001bf63  add     rsp, 28h
0x18001bf67  pop     rdi
0x18001bf68  pop     rsi
0x18001bf69  pop     rbp
0x18001bf6a  pop     rbx
0x18001bf6b  retn
```
