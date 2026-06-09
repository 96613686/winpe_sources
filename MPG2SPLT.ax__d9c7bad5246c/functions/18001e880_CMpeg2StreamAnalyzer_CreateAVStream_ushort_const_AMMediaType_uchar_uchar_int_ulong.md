# CMpeg2StreamAnalyzer::CreateAVStream_(ushort const *,_AMMediaType *,uchar,uchar,int,ulong)

- ea: `0x18001e880`
- end: `0x18001e93d`
- name: `?CreateAVStream_@CMpeg2StreamAnalyzer@@IEAAJPEBGPEAU_AMMediaType@@EEHK@Z`
- size: `189`
- prototype: `int(CMpeg2StreamAnalyzer *__hidden this, const unsigned __int16 *, struct _AMMediaType *, unsigned __int8, unsigned __int8, int, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fe90`
- `0x18001fff4`
- `0x180020208`
- `0x180020318`
- `0x1800203fc`

## callees

- `0x180013f9c`
- `0x180014370`
- `0x180014608`
- `0x18001e880`

## pseudocode

```c
__int64 __fastcall CMpeg2StreamAnalyzer::CreateAVStream_(
        CMPEG2Demultiplexer **this,
        const unsigned __int16 *a2,
        struct _AMMediaType *a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        int a6,
        unsigned int a7)
{
  unsigned int v7; // ebp
  int OutputPin; // ebx
  int v12; // [rsp+80h] [rbp+8h] BYREF
  int v13; // [rsp+84h] [rbp+Ch]

  v7 = a4;
  OutputPin = CMPEG2Demultiplexer::CreateOutputPin_(this[1], a2, a3, 0);
  if ( OutputPin >= 0 )
  {
    a7 = v7;
    if ( a6 <= 0 )
      v12 = 0x10000000;
    else
      v12 = a5;
    v13 = a6;
    OutputPin = CMPEG2Demultiplexer::CreateStreamMap_(this[1], 1u, &a7, a2, 0, 0xFFFFFFFF, &v12, 1, 0);
    if ( OutputPin < 0 )
      CMPEG2Demultiplexer::DeletePin_(this[1], a2);
  }
  return (unsigned int)OutputPin;
}

```

## disassembly

```asm
0x18001e880  push    rbx
0x18001e882  push    rbp
0x18001e883  push    rsi
0x18001e884  push    rdi
0x18001e885  sub     rsp, 58h
0x18001e889  movzx   ebp, r9b
0x18001e88d  mov     rsi, rcx
0x18001e890  mov     rcx, [rcx+8]; this
0x18001e894  xor     r9d, r9d; struct DEMUX_PIN_RECORD **
0x18001e897  mov     rdi, rdx
0x18001e89a  call    ?CreateOutputPin_@CMPEG2Demultiplexer@@AEAAJPEBGPEAU_AMMediaType@@PEAPEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::CreateOutputPin_(ushort const *,_AMMediaType *,DEMUX_PIN_RECORD * *)
0x18001e89f  mov     ebx, eax
0x18001e8a1  test    eax, eax
0x18001e8a3  js      loc_18001E932
0x18001e8a9  mov     ecx, [rsp+78h+arg_28]
0x18001e8b0  mov     [rsp+78h+arg_30], ebp
0x18001e8b7  test    ecx, ecx
0x18001e8b9  jle     short loc_18001E8CC
0x18001e8bb  movzx   eax, [rsp+78h+arg_20]
0x18001e8c3  mov     [rsp+78h+arg_0], eax
0x18001e8ca  jmp     short loc_18001E8D7
0x18001e8cc  mov     [rsp+78h+arg_0], 10000000h
0x18001e8d7  mov     [rsp+78h+var_38], 0; int
0x18001e8df  lea     rax, [rsp+78h+arg_0]
0x18001e8e7  mov     edx, 1; unsigned int
0x18001e8ec  mov     [rsp+78h+arg_4], ecx
0x18001e8f3  mov     rcx, [rsi+8]; this
0x18001e8f7  lea     r8, [rsp+78h+arg_30]; unsigned int *
0x18001e8ff  mov     [rsp+78h+var_40], edx; int
0x18001e903  mov     r9, rdi; unsigned __int16 *
0x18001e906  mov     [rsp+78h+var_48], rax; void *
0x18001e90b  mov     [rsp+78h+var_50], 0FFFFFFFFh; unsigned int
0x18001e913  mov     [rsp+78h+var_58], 0; unsigned int
0x18001e91b  call    ?CreateStreamMap_@CMPEG2Demultiplexer@@AEAAJKPEAKPEBGKKPEAXHH@Z; CMPEG2Demultiplexer::CreateStreamMap_(ulong,ulong *,ushort const *,ulong,ulong,void *,int,int)
0x18001e920  mov     ebx, eax
0x18001e922  test    eax, eax
0x18001e924  jns     short loc_18001E932
0x18001e926  mov     rcx, [rsi+8]; this
0x18001e92a  mov     rdx, rdi; unsigned __int16 *
0x18001e92d  call    ?DeletePin_@CMPEG2Demultiplexer@@AEAAJPEBG@Z; CMPEG2Demultiplexer::DeletePin_(ushort const *)
0x18001e932  mov     eax, ebx
0x18001e934  add     rsp, 58h
0x18001e938  pop     rdi
0x18001e939  pop     rsi
0x18001e93a  pop     rbp
0x18001e93b  pop     rbx
0x18001e93c  retn
```
