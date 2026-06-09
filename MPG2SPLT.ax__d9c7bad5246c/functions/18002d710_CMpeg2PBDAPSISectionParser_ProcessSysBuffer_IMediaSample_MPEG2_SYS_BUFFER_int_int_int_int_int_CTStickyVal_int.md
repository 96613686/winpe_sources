# CMpeg2PBDAPSISectionParser::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x18002d710`
- end: `0x18002d8d1`
- name: `?ProcessSysBuffer@CMpeg2PBDAPSISectionParser@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `449`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180017cf8`
- `0x180017f0c`
- `0x18001818c`
- `0x180019a60`
- `0x18002a7e0`
- `0x18002ae14`
- `0x18002ce98`
- `0x18002d710`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2PBDAPSISectionParser::ProcessSysBuffer(
        CCopyFrameParser *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        unsigned int a7,
        int a8,
        __int64 a9)
{
  int v9; // ebp
  __int64 v10; // rdx
  char *v12; // rcx
  int v14; // ebx
  __int64 v15; // rbp
  __int64 v16; // r15
  unsigned __int16 v17; // si
  CPbdaTagTableHandler *v18; // r12
  struct _PBDA_TAG_ATTRIBUTE *TagAttribPtr; // r13
  unsigned int v20; // r9d
  __int64 v21; // rcx
  struct _GUID v23; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v24[280]; // [rsp+60h] [rbp-118h] BYREF
  int v25; // [rsp+180h] [rbp+8h]

  v9 = a7;
  v10 = a3;
  v12 = (char *)this - 2536;
  if ( *(_DWORD *)(a3 + 32) != 71 )
    v10 = 0;
  if ( (**(unsigned int (__fastcall ***)(char *, __int64, _QWORD, _QWORD, int *))v12)(v12, v10, a4, a7, &a5) )
  {
    v14 = CMpeg2PSIParse::ProcessSysBuffer(this, a5, a6, v9, a8, a9);
  }
  else
  {
    if ( *((_DWORD *)this + 95) )
      *(_DWORD *)(a3 + 28) |= 0x2000u;
    v14 = -2147467259;
  }
  v15 = 0;
  v25 = *((_DWORD *)this - 6);
  if ( v25 > 0 )
  {
    do
    {
      v16 = *((unsigned __int8 *)this + v15 - 280);
      v17 = 0;
      v18 = (CPbdaTagTableHandler *)*((_QWORD *)this + v16 - 291);
      do
      {
        TagAttribPtr = CPbdaTagTableHandler::GetTagAttribPtr(v18, v17);
        if ( TagAttribPtr )
        {
          Mpeg2DemuxAttributes::CAttributeList::CAttributeList((Mpeg2DemuxAttributes::CAttributeList *)v24);
          Mpeg2DemuxAttributes::CAttributeList::Reset((Mpeg2DemuxAttributes::CAttributeList *)v24);
          (**((void (__fastcall ***)(char *, _BYTE *))this + 6))((char *)this + 48, v24);
          v20 = TagAttribPtr->TableDataSize + 27;
          v23 = DSATTRIB_PBDATAG_ATTRIBUTE;
          Mpeg2DemuxAttributes::CAttributeList::AddAttribute(
            (Mpeg2DemuxAttributes::CAttributeList *)v24,
            &v23,
            TagAttribPtr,
            v20);
          v14 = CBufferSourceManager::WrapAndCompleteEmptySample(
                  (CCopyFrameParser *)((char *)this + 48),
                  (struct Mpeg2DemuxAttributes::CAttributeList *)v24);
          if ( v14 >= 0 )
          {
            v21 = *((_QWORD *)this + v16 - 291);
            if ( v21 )
              *(_DWORD *)(((unsigned __int64)(unsigned __int8)v17 << 6) + v21 + 56) = 0;
          }
          Mpeg2DemuxAttributes::CAttributeList::~CAttributeList((Mpeg2DemuxAttributes::CAttributeList *)v24);
        }
        ++v17;
      }
      while ( v17 < 5u );
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (int)v15 < v25 );
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002d710  mov     r11, rsp
0x18002d713  push    rbx
0x18002d714  push    rbp
0x18002d715  push    rsi
0x18002d716  push    rdi
0x18002d717  push    r12
0x18002d719  push    r13
0x18002d71b  push    r14
0x18002d71d  push    r15
0x18002d71f  sub     rsp, 138h
0x18002d726  mov     ebp, [rsp+178h+arg_30]
0x18002d72d  xor     eax, eax
0x18002d72f  mov     r14, rdx
0x18002d732  mov     esi, r9d
0x18002d735  mov     rdx, r8
0x18002d738  mov     rdi, rcx
0x18002d73b  add     rcx, 0FFFFFFFFFFFFF618h
0x18002d742  mov     rbx, r8
0x18002d745  cmp     dword ptr [r8+20h], 47h ; 'G'
0x18002d74a  mov     r9d, ebp
0x18002d74d  mov     r8d, esi
0x18002d750  cmovnz  rdx, rax
0x18002d754  lea     rax, [r11+28h]
0x18002d758  mov     r10, [rcx]
0x18002d75b  mov     qword ptr [rsp+178h+var_158], rax
0x18002d760  mov     rax, [r10]
0x18002d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d768  test    eax, eax
0x18002d76a  jz      short loc_18002D7B3
0x18002d76c  mov     rax, [rsp+178h+arg_40]
0x18002d774  mov     r9d, esi
0x18002d777  mov     [rsp+178h+var_138], rax; __int64
0x18002d77c  mov     r8, rbx
0x18002d77f  mov     eax, [rsp+178h+arg_38]
0x18002d786  mov     rdx, r14
0x18002d789  mov     [rsp+178h+var_140], eax; int
0x18002d78d  mov     rcx, rdi; this
0x18002d790  mov     eax, [rsp+178h+arg_28]
0x18002d797  mov     [rsp+178h+var_148], ebp; int
0x18002d79b  mov     [rsp+178h+var_150], eax; int
0x18002d79f  mov     eax, [rsp+178h+arg_20]
0x18002d7a6  mov     [rsp+178h+var_158], eax; int
0x18002d7aa  call    ?ProcessSysBuffer@CMpeg2PSIParse@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z; CMpeg2PSIParse::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)
0x18002d7af  mov     ebx, eax
0x18002d7b1  jmp     short loc_18002D7C6
0x18002d7b3  cmp     dword ptr [rdi+17Ch], 0
0x18002d7ba  jz      short loc_18002D7C1
0x18002d7bc  bts     dword ptr [rbx+1Ch], 0Dh
0x18002d7c1  mov     ebx, 80004005h
0x18002d7c6  mov     r14d, [rdi-18h]
0x18002d7ca  xor     ebp, ebp
0x18002d7cc  mov     [rsp+178h+arg_0], r14d
0x18002d7d4  test    r14d, r14d
0x18002d7d7  jle     loc_18002D8BB
0x18002d7dd  movzx   r15d, byte ptr [rbp+rdi-118h]
0x18002d7e6  xor     esi, esi
0x18002d7e8  mov     r12, [rdi+r15*8-918h]
0x18002d7f0  lea     r14d, [rsi+1]
0x18002d7f4  mov     dl, sil; unsigned __int8
0x18002d7f7  mov     rcx, r12; this
0x18002d7fa  call    ?GetTagAttribPtr@CPbdaTagTableHandler@@QEAAPEAU_PBDA_TAG_ATTRIBUTE@@E@Z; CPbdaTagTableHandler::GetTagAttribPtr(uchar)
0x18002d7ff  mov     r13, rax
0x18002d802  test    rax, rax
0x18002d805  jz      loc_18002D89D
0x18002d80b  lea     rcx, [rsp+178h+var_118]; this
0x18002d810  call    ??0CAttributeList@Mpeg2DemuxAttributes@@QEAA@XZ; Mpeg2DemuxAttributes::CAttributeList::CAttributeList(void)
0x18002d815  lea     rcx, [rsp+178h+var_118]; this
0x18002d81a  call    ?Reset@CAttributeList@Mpeg2DemuxAttributes@@QEAAXXZ; Mpeg2DemuxAttributes::CAttributeList::Reset(void)
0x18002d81f  lea     rbx, [rdi+30h]
0x18002d823  mov     rcx, [rbx]
0x18002d826  lea     rdx, [rsp+178h+var_118]
0x18002d82b  mov     rax, [rcx]
0x18002d82e  mov     rcx, rbx
0x18002d831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d836  movups  xmm0, xmmword ptr cs:DSATTRIB_PBDATAG_ATTRIBUTE.Data1
0x18002d83d  mov     r9d, [r13+14h]
0x18002d841  lea     rdx, [rsp+178h+var_128]; struct _GUID
0x18002d846  add     r9d, 1Bh; unsigned int
0x18002d84a  lea     rcx, [rsp+178h+var_118]; this
0x18002d84f  mov     r8, r13; void *
0x18002d852  movdqu  xmmword ptr [rsp+178h+var_128.Data1], xmm0
0x18002d858  call    ?AddAttribute@CAttributeList@Mpeg2DemuxAttributes@@QEAAJU_GUID@@PEAXK@Z; Mpeg2DemuxAttributes::CAttributeList::AddAttribute(_GUID,void *,ulong)
0x18002d85d  lea     rdx, [rsp+178h+var_118]; struct Mpeg2DemuxAttributes::CAttributeList *
0x18002d862  mov     rcx, rbx; this
0x18002d865  call    ?WrapAndCompleteEmptySample@CBufferSourceManager@@IEAAJPEAVCAttributeList@Mpeg2DemuxAttributes@@@Z; CBufferSourceManager::WrapAndCompleteEmptySample(Mpeg2DemuxAttributes::CAttributeList *)
0x18002d86a  mov     ebx, eax
0x18002d86c  test    eax, eax
0x18002d86e  js      short loc_18002D893
0x18002d870  cmp     sil, 5
0x18002d874  jnb     short loc_18002D893
0x18002d876  mov     rcx, [rdi+r15*8-918h]
0x18002d87e  test    rcx, rcx
0x18002d881  jz      short loc_18002D893
0x18002d883  movzx   eax, sil
0x18002d887  shl     rax, 6
0x18002d88b  mov     dword ptr [rax+rcx+38h], 0
0x18002d893  lea     rcx, [rsp+178h+var_118]; this
0x18002d898  call    ??1CAttributeList@Mpeg2DemuxAttributes@@UEAA@XZ; Mpeg2DemuxAttributes::CAttributeList::~CAttributeList(void)
0x18002d89d  add     si, r14w
0x18002d8a1  cmp     si, 5
0x18002d8a5  jb      loc_18002D7F4
0x18002d8ab  add     ebp, r14d
0x18002d8ae  cmp     ebp, [rsp+178h+arg_0]
0x18002d8b5  jl      loc_18002D7DD
0x18002d8bb  mov     eax, ebx
0x18002d8bd  add     rsp, 138h
0x18002d8c4  pop     r15
0x18002d8c6  pop     r14
0x18002d8c8  pop     r13
0x18002d8ca  pop     r12
0x18002d8cc  pop     rdi
0x18002d8cd  pop     rsi
0x18002d8ce  pop     rbp
0x18002d8cf  pop     rbx
0x18002d8d0  retn
```
