# EventRendering::RenderEventToXml(Event const &,ulong,void *,ulong *)

- ea: `0x180001568`
- end: `0x180001714`
- name: `?RenderEventToXml@EventRendering@@YAKAEBVEvent@@KPEAXPEAK@Z`
- size: `428`
- prototype: `unsigned int __fastcall(EventRendering *__hidden this, const struct Event *, unsigned int, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180005f20`
- `0x180007fb8`

## callees

- `0x180001568`
- `0x180001720`
- `0x180001730`
- `0x180003158`
- `0x180003dc0`
- `0x18000a100`
- `0x18000b95c`
- `0x180023548`
- `0x180038fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EventRendering::RenderEventToXml(EventRendering *this, const struct Event *a2, void *a3, _DWORD *a4)
{
  int v6; // ebx
  unsigned int Size; // ebx
  void **v9; // [rsp+30h] [rbp-D0h] BYREF
  void *v10; // [rsp+38h] [rbp-C8h]
  int v11; // [rsp+40h] [rbp-C0h]
  int v12; // [rsp+44h] [rbp-BCh]
  char v13; // [rsp+48h] [rbp-B8h]
  void ***v14; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int8 *BufferPtr; // [rsp+58h] [rbp-A8h]
  __int64 v16; // [rsp+60h] [rbp-A0h]
  __int128 pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+84h] [rbp-7Ch]
  int v21; // [rsp+88h] [rbp-78h]
  _QWORD v22[3]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-58h]
  _BYTE v24[224]; // [rsp+C0h] [rbp-40h] BYREF

  v6 = (int)a2;
  if ( !a4 || (_DWORD)a2 && !a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 87);
    }
    pExceptionObject = 0;
    v18 = 0;
    v19 = 87;
    v20 = -1;
    v21 = 146;
    throw (EvtException *)&pExceptionObject;
  }
  v22[0] = 0;
  v23 = 0;
  v22[1] = *((_QWORD *)this + 7);
  v22[2] = *((unsigned int *)this + 17);
  BinXmlReader::BinXmlReader(
    (BinXmlReader *)v24,
    (struct BinXmlReaderData *)v22,
    (unsigned int)a3,
    0,
    0,
    *((struct BinXmlTemplateTable **)this + 5));
  v9 = &Buffer::`vftable';
  v11 = 0;
  v13 = 0;
  v10 = a3;
  v12 = v6;
  v14 = &v9;
  BufferPtr = 0;
  v16 = 0;
  Size = Buffer::GetSize((Buffer *)&v9);
  BufferPtr = Buffer::GetBufferPtr((Buffer *)&v9);
  HIDWORD(v16) = Size;
  BinXmlReader::GetXmlText((BinXmlReader *)v24, (struct WriteBuffer *)&v14);
  *a4 = v16;
  v9 = &Buffer::`vftable';
  if ( v10 == a3 )
  {
    if ( v13 )
      operator delete(v10);
    BinXmlReader::~BinXmlReader((BinXmlReader *)v24);
    return 0;
  }
  else
  {
    if ( v13 )
      operator delete(v10);
    BinXmlReader::~BinXmlReader((BinXmlReader *)v24);
    return 122;
  }
}

```

## disassembly

```asm
0x180001568  push    rbp
0x18000156a  push    rbx
0x18000156b  push    rsi
0x18000156c  push    rdi
0x18000156d  push    r15
0x18000156f  lea     rbp, [rsp-80h]
0x180001574  sub     rsp, 180h
0x18000157b  mov     rsi, r9
0x18000157e  mov     rdi, r8
0x180001581  mov     ebx, edx
0x180001583  test    r9, r9
0x180001586  jz      loc_1800016A2
0x18000158c  test    edx, edx
0x18000158e  jnz     loc_180001699
0x180001594  mov     [rbp+0A0h+var_110], 0
0x18000159c  xorps   xmm0, xmm0
0x18000159f  movdqu  [rbp+0A0h+var_F8], xmm0
0x1800015a4  mov     rax, [rcx+38h]
0x1800015a8  mov     [rbp+0A0h+var_108], rax
0x1800015ac  mov     eax, [rcx+44h]
0x1800015af  mov     [rbp+0A0h+var_100], rax
0x1800015b3  mov     rax, [rcx+28h]
0x1800015b7  mov     [rsp+1A0h+var_178], rax; struct BinXmlTemplateTable *
0x1800015bc  mov     [rsp+1A0h+var_180], 0; struct BinXmlStringTable *
0x1800015c5  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x1800015c8  lea     rdx, [rbp+0A0h+var_110]; struct BinXmlReaderData *
0x1800015cc  lea     rcx, [rbp+0A0h+var_E0]; this
0x1800015d0  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x1800015d5  nop
0x1800015d6  lea     r15, ??_7Buffer@@6B@; const Buffer::`vftable'
0x1800015dd  mov     [rsp+1A0h+var_170], r15
0x1800015e2  mov     [rsp+1A0h+var_160], 0
0x1800015ea  mov     [rsp+1A0h+var_158], 0
0x1800015ef  mov     [rsp+1A0h+var_168], rdi
0x1800015f4  mov     [rsp+1A0h+var_15C], ebx
0x1800015f8  lea     rax, [rsp+1A0h+var_170]
0x1800015fd  mov     [rsp+1A0h+var_150], rax
0x180001602  mov     [rsp+1A0h+var_148], 0
0x18000160b  mov     [rsp+1A0h+var_140], 0
0x180001614  lea     rcx, [rsp+1A0h+var_170]; this
0x180001619  call    ?GetSize@Buffer@@UEBAKXZ; Buffer::GetSize(void)
0x18000161e  mov     ebx, eax
0x180001620  lea     rcx, [rsp+1A0h+var_170]; this
0x180001625  call    ?GetBufferPtr@Buffer@@UEBAPEBEXZ; Buffer::GetBufferPtr(void)
0x18000162a  mov     [rsp+1A0h+var_148], rax
0x18000162f  mov     dword ptr [rsp+1A0h+var_140+4], ebx
0x180001633  lea     rdx, [rsp+1A0h+var_150]; struct WriteBuffer *
0x180001638  lea     rcx, [rbp+0A0h+var_E0]; this
0x18000163c  call    ?GetXmlText@BinXmlReader@@QEAAXAEAVWriteBuffer@@@Z; BinXmlReader::GetXmlText(WriteBuffer &)
0x180001641  mov     eax, dword ptr [rsp+1A0h+var_140]
0x180001645  mov     [rsi], eax
0x180001647  mov     rcx, [rsp+1A0h+var_168]; void *
0x18000164c  mov     [rsp+1A0h+var_170], r15
0x180001651  cmp     rcx, rdi
0x180001654  jz      short loc_18000167F
0x180001656  cmp     [rsp+1A0h+var_158], 0
0x18000165b  jz      short loc_180001663
0x18000165d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001662  nop
0x180001663  lea     rcx, [rbp+0A0h+var_E0]; this
0x180001667  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x18000166c  mov     eax, 7Ah ; 'z'
0x180001671  add     rsp, 180h
0x180001678  pop     r15
0x18000167a  pop     rdi
0x18000167b  pop     rsi
0x18000167c  pop     rbx
0x18000167d  pop     rbp
0x18000167e  retn
0x18000167f  cmp     [rsp+1A0h+var_158], 0
0x180001684  jz      short loc_18000168C
0x180001686  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000168b  nop
0x18000168c  lea     rcx, [rbp+0A0h+var_E0]; this
0x180001690  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x180001695  xor     eax, eax
0x180001697  jmp     short loc_180001671
0x180001699  test    rdi, rdi
0x18000169c  jnz     loc_180001594
0x1800016a2  lea     rax, WPP_GLOBAL_Control
0x1800016a9  mov     ebx, 57h ; 'W'
0x1800016ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016b5  cmp     rcx, rax
0x1800016b8  jz      short loc_1800016DF
0x1800016ba  test    dword ptr [rcx+1Ch], 40000h
0x1800016c1  jz      short loc_1800016DF
0x1800016c3  cmp     byte ptr [rcx+19h], 2
0x1800016c7  jb      short loc_1800016DF
0x1800016c9  lea     edx, [rbx-4Bh]
0x1800016cc  mov     r9d, ebx
0x1800016cf  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x1800016d6  mov     rcx, [rcx+10h]
0x1800016da  call    WPP_SF_D
0x1800016df  xorps   xmm0, xmm0
0x1800016e2  movdqu  [rsp+1A0h+pExceptionObject], xmm0
0x1800016e8  mov     [rsp+1A0h+var_128], 0
0x1800016f1  mov     [rbp+0A0h+var_120], ebx
0x1800016f4  mov     [rbp+0A0h+var_11C], 0FFFFFFFFh
0x1800016fb  mov     [rbp+0A0h+var_118], 92h
0x180001702  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180001709  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18000170e  call    _CxxThrowException_0
```
