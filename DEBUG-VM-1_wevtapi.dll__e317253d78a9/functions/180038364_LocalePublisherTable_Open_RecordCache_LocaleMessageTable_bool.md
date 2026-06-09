# LocalePublisherTable::Open(RecordCache *,LocaleMessageTable *,bool)

- ea: `0x180038364`
- end: `0x1800384f2`
- name: `?Open@LocalePublisherTable@@QEAAXPEAVRecordCache@@PEAVLocaleMessageTable@@_N@Z`
- size: `398`
- prototype: `void(LocalePublisherTable *__hidden this, struct RecordCache *, struct LocaleMessageTable *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180036698`

## callees

- `0x180003ed0`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a558`
- `0x180023548`
- `0x180036dc0`
- `0x1800377b8`
- `0x180038364`
- `0x180038fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LocalePublisherTable::Open(
        LocalePublisherTable *this,
        struct RecordCache *a2,
        struct LocaleMessageTable *a3,
        char a4)
{
  _BYTE v7[32]; // [rsp+20h] [rbp-58h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  int v12; // [rsp+60h] [rbp-18h]
  unsigned int v13; // [rsp+B8h] [rbp+40h] BYREF

  LOBYTE(v13) = a4;
  Buffer::Buffer((Buffer *)v7, 0, 0, 1);
  v13 = 0;
  *((_QWORD *)this + 44) = a2;
  *((_QWORD *)this + 45) = a3;
  if ( !RecordCache::GetRecord(a2, 0, (struct Buffer *)v7, &v13) )
  {
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 1168;
      v11 = -1;
      v12 = 1038;
      throw (EvtException *)&pExceptionObject;
    }
    Buffer::SetSize((Buffer *)v7, v13);
    if ( !RecordCache::GetRecord(*((RecordCache **)this + 44), 0, (struct Buffer *)v7, &v13) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = 1168;
      v11 = -1;
      v12 = 1047;
      throw (EvtException *)&pExceptionObject;
    }
  }
  Buffer::SetCurrentIndex((Buffer *)v7, 0);
  LocalePublisherTable::_PublisherRecord::Deserialize((LocalePublisherTable *)((char *)this + 160), (struct Buffer *)v7);
  Buffer::~Buffer((Buffer *)v7);
}

```

## disassembly

```asm
0x180038364  mov     byte ptr [rsp-20h+arg_18], r9b
0x180038369  push    rbp
0x18003836a  push    rbx
0x18003836b  push    rsi
0x18003836c  push    rdi
0x18003836d  mov     rbp, rsp
0x180038370  sub     rsp, 78h
0x180038374  mov     rbx, r8
0x180038377  mov     rdi, rdx
0x18003837a  mov     rsi, rcx
0x18003837d  mov     r9b, 1; bool
0x180038380  xor     r8d, r8d; unsigned int
0x180038383  xor     edx, edx; unsigned __int8 *
0x180038385  lea     rcx, [rbp+var_58]; this
0x180038389  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18003838e  nop
0x18003838f  mov     [rbp+arg_18], 0
0x180038396  mov     [rsi+160h], rdi
0x18003839d  mov     [rsi+168h], rbx
0x1800383a4  lea     r9, [rbp+arg_18]; unsigned int *
0x1800383a8  lea     r8, [rbp+var_58]; struct Buffer *
0x1800383ac  xor     edx, edx; unsigned int
0x1800383ae  mov     rcx, rdi; this
0x1800383b1  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x1800383b6  test    al, al
0x1800383b8  jnz     loc_1800384C4
0x1800383be  mov     edx, [rbp+arg_18]; unsigned int
0x1800383c1  test    edx, edx
0x1800383c3  jnz     short loc_180038433
0x1800383c5  lea     rax, WPP_GLOBAL_Control
0x1800383cc  mov     ebx, 490h
0x1800383d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383d8  cmp     rcx, rax
0x1800383db  jz      short loc_180038401
0x1800383dd  test    byte ptr [rcx+1Ch], 1
0x1800383e1  jz      short loc_180038401
0x1800383e3  cmp     byte ptr [rcx+19h], 2
0x1800383e7  jb      short loc_180038401
0x1800383e9  mov     edx, 2Fh ; '/'
0x1800383ee  mov     r9d, ebx
0x1800383f1  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x1800383f8  mov     rcx, [rcx+10h]
0x1800383fc  call    WPP_SF_D
0x180038401  xorps   xmm0, xmm0
0x180038404  movdqu  [rbp+pExceptionObject], xmm0
0x180038409  mov     [rbp+var_28], 0
0x180038411  mov     [rbp+var_20], ebx
0x180038414  mov     [rbp+var_1C], 0FFFFFFFFh
0x18003841b  mov     [rbp+var_18], 40Eh
0x180038422  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180038429  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003842d  call    _CxxThrowException_0
0x180038433  lea     rcx, [rbp+var_58]; this
0x180038437  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18003843c  lea     r9, [rbp+arg_18]; unsigned int *
0x180038440  lea     r8, [rbp+var_58]; struct Buffer *
0x180038444  xor     edx, edx; unsigned int
0x180038446  mov     rcx, [rsi+160h]; this
0x18003844d  call    ?GetRecord@RecordCache@@QEAA_NKAEAVBuffer@@AEAK@Z; RecordCache::GetRecord(ulong,Buffer &,ulong &)
0x180038452  test    al, al
0x180038454  jnz     short loc_1800384C4
0x180038456  lea     rax, WPP_GLOBAL_Control
0x18003845d  mov     ebx, 490h
0x180038462  mov     rcx, cs:WPP_GLOBAL_Control
0x180038469  cmp     rcx, rax
0x18003846c  jz      short loc_180038492
0x18003846e  test    byte ptr [rcx+1Ch], 1
0x180038472  jz      short loc_180038492
0x180038474  cmp     byte ptr [rcx+19h], 2
0x180038478  jb      short loc_180038492
0x18003847a  mov     edx, 30h ; '0'
0x18003847f  mov     r9d, ebx
0x180038482  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180038489  mov     rcx, [rcx+10h]
0x18003848d  call    WPP_SF_D
0x180038492  xorps   xmm0, xmm0
0x180038495  movdqu  [rbp+pExceptionObject], xmm0
0x18003849a  mov     [rbp+var_28], 0
0x1800384a2  mov     [rbp+var_20], ebx
0x1800384a5  mov     [rbp+var_1C], 0FFFFFFFFh
0x1800384ac  mov     [rbp+var_18], 417h
0x1800384b3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800384ba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800384be  call    _CxxThrowException_0
0x1800384c4  xor     edx, edx; unsigned int
0x1800384c6  lea     rcx, [rbp+var_58]; this
0x1800384ca  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x1800384cf  lea     rcx, [rsi+0A0h]; this
0x1800384d6  lea     rdx, [rbp+var_58]; struct Buffer *
0x1800384da  call    ?Deserialize@_PublisherRecord@LocalePublisherTable@@QEAAXAEAVBuffer@@@Z; LocalePublisherTable::_PublisherRecord::Deserialize(Buffer &)
0x1800384df  nop
0x1800384e0  lea     rcx, [rbp+var_58]; this
0x1800384e4  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x1800384e9  add     rsp, 78h
0x1800384ed  pop     rdi
0x1800384ee  pop     rsi
0x1800384ef  pop     rbx
0x1800384f0  pop     rbp
0x1800384f1  retn
```
