# CreateBinXMLFromCustomXML(ulong,wchar_t const *,ulong,ulong const *,ulong,int,uchar *,ulong *,_GUID *)

- ea: `0x18002e034`
- end: `0x18002e22d`
- name: `?CreateBinXMLFromCustomXML@@YAKKPEB_WKPEBKKHPEAEPEAKPEAU_GUID@@@Z`
- size: `505`
- prototype: `unsigned int(unsigned int, const wchar_t *, unsigned int, const unsigned int *, unsigned int, int, unsigned __int8 *, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180026860`

## callees

- `0x180003ed0`
- `0x180007180`
- `0x180009d80`
- `0x18000a2d0`
- `0x18000a4b4`
- `0x18000a558`
- `0x18000bb4c`
- `0x1800196a0`
- `0x18002e034`
- `0x18002e234`
- `0x18002eb48`
- `0x180030c24`
- `0x180038fcc`
- `0x18003c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateBinXMLFromCustomXML(
        unsigned int a1,
        const wchar_t *a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int a5,
        int a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        struct _GUID *a9)
{
  __int64 v10; // r15
  __int64 v12; // r14
  unsigned __int8 *v13; // rsi
  unsigned int *v14; // rdi
  char v15; // r8
  size_t v16; // rax
  __int64 result; // rax
  size_t v18; // rdi
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // rbx
  _BYTE v21[8]; // [rsp+40h] [rbp-F8h] BYREF
  void *Src; // [rsp+48h] [rbp-F0h]
  size_t Size; // [rsp+50h] [rbp-E8h]
  __int128 v24; // [rsp+60h] [rbp-D8h] BYREF
  _QWORD v25[2]; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+80h] [rbp-B8h]
  EvtException *v27; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v28[48]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v29[120]; // [rsp+C0h] [rbp-78h] BYREF

  try
  {
    v10 = a3;
    v12 = a1;
    v13 = a7;
    if ( a7 )
    {
      if ( a5 )
      {
LABEL_4:
        v14 = a8;
        *a8 = 0;
        Buffer::Buffer((Buffer *)v21, 0, 0, 1);
        Buffer::SetSize((Buffer *)v21, 0x2800u);
        Buffer::SetCurrentIndex((Buffer *)v21, 0);
        WriteBuffer::WriteBuffer((WriteBuffer *)v25, (struct BufferStream *)v21);
        BinXmlWriter::BinXmlWriter((BinXmlWriter *)v28, 1, (struct WriteBuffer *)v25, 0, 0, a4, v10);
        *(_QWORD *)&v24 = a2;
        *((_QWORD *)&v24 + 1) = v12;
        BinXmlWriter::Parse((BinXmlWriter *)v28, &v24, v15);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v25[0] + 32LL))(v25[0], v26);
        v16 = (unsigned int)Size;
        *v14 = Size;
        if ( (unsigned int)v16 <= a5 )
        {
          memcpy_0(v13, Src, v16);
          v18 = 2 * v12;
          v19 = (unsigned __int8 *)MIDL_user_allocate(4 * v10 + 2 * v12);
          v20 = v19;
          a7 = v19;
          if ( v19 )
          {
            memcpy_0(v19, a2, v18);
            memcpy_0(&v20[v18], a4, 4 * v10);
            Sha256HashToGuid(v20, 4 * v10 + v18, a9);
            tlx::_FreeFixedLocal::~_FreeFixedLocal((tlx::_FreeFixedLocal *)&a7);
            utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
            Buffer::~Buffer((Buffer *)v21);
            return 0;
          }
          else
          {
            tlx::_FreeFixedLocal::~_FreeFixedLocal((tlx::_FreeFixedLocal *)&a7);
            utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
            Buffer::~Buffer((Buffer *)v21);
            return 14;
          }
        }
        else
        {
          utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v29);
          Buffer::~Buffer((Buffer *)v21);
          return 122;
        }
      }
    }
    else if ( !a5 )
    {
      goto LABEL_4;
    }
    result = 87;
  }
  catch ( EvtException *v27 )
  {
    return *((unsigned int *)v27 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x18002e034  push    rbx
0x18002e036  push    rsi
0x18002e037  push    rdi
0x18002e038  push    r12
0x18002e03a  push    r13
0x18002e03c  push    r14
0x18002e03e  push    r15
0x18002e040  sub     rsp, 100h
0x18002e047  mov     r12, r9
0x18002e04a  mov     r15d, r8d
0x18002e04d  mov     r13, rdx
0x18002e050  mov     r14d, ecx
0x18002e053  mov     rsi, [rsp+138h+arg_30]
0x18002e05b  mov     ebx, [rsp+138h+arg_20]
0x18002e062  test    rsi, rsi
0x18002e065  jnz     loc_18002E204
0x18002e06b  test    ebx, ebx
0x18002e06d  jnz     loc_18002E20C
0x18002e073  mov     rdi, [rsp+138h+arg_38]
0x18002e07b  mov     dword ptr [rdi], 0
0x18002e081  mov     r9b, 1; bool
0x18002e084  xor     r8d, r8d; unsigned int
0x18002e087  xor     edx, edx; unsigned __int8 *
0x18002e089  lea     rcx, [rsp+138h+var_F8]; this
0x18002e08e  call    ??0Buffer@@QEAA@PEBEK_N@Z; Buffer::Buffer(uchar const *,ulong,bool)
0x18002e093  nop
0x18002e094  mov     edx, 2800h; unsigned int
0x18002e099  lea     rcx, [rsp+138h+var_F8]; this
0x18002e09e  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18002e0a3  xor     edx, edx; unsigned int
0x18002e0a5  lea     rcx, [rsp+138h+var_F8]; this
0x18002e0aa  call    ?SetCurrentIndex@Buffer@@UEAAXK@Z; Buffer::SetCurrentIndex(ulong)
0x18002e0af  lea     rdx, [rsp+138h+var_F8]; struct BufferStream *
0x18002e0b4  lea     rcx, [rsp+138h+var_C8]; this
0x18002e0b9  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x18002e0be  mov     [rsp+138h+var_108], r15d; unsigned int
0x18002e0c3  mov     [rsp+138h+var_110], r12; unsigned int *
0x18002e0c8  mov     [rsp+138h+var_118], 0; struct BinXmlTemplateTable *
0x18002e0d1  xor     r9d, r9d; struct BinXmlStringTable *
0x18002e0d4  lea     r8, [rsp+138h+var_C8]; struct WriteBuffer *
0x18002e0d9  mov     dl, 1; bool
0x18002e0db  lea     rcx, [rsp+138h+var_A8]; this
0x18002e0e3  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x18002e0e8  nop
0x18002e0e9  mov     [rsp+138h+var_D8], r13
0x18002e0ee  mov     [rsp+138h+var_D0], r14
0x18002e0f3  lea     rdx, [rsp+138h+var_D8]
0x18002e0f8  lea     rcx, [rsp+138h+var_A8]; this
0x18002e100  call    ?Parse@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N1@Z; BinXmlWriter::Parse(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,bool)
0x18002e105  mov     rcx, [rsp+138h+var_C8]
0x18002e10a  mov     rax, [rcx]
0x18002e10d  mov     edx, [rsp+138h+var_B8]
0x18002e114  mov     rax, [rax+20h]
0x18002e118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e11d  mov     eax, dword ptr [rsp+138h+Size]
0x18002e121  mov     [rdi], eax
0x18002e123  cmp     eax, ebx
0x18002e125  jbe     short loc_18002E149
0x18002e127  lea     rcx, [rsp+138h+var_78]
0x18002e12f  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e134  nop
0x18002e135  lea     rcx, [rsp+138h+var_F8]; this
0x18002e13a  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e13f  mov     eax, 7Ah ; 'z'
0x18002e144  jmp     loc_18002E21A
0x18002e149  mov     r8, rax; Size
0x18002e14c  mov     rdx, [rsp+138h+Src]; Src
0x18002e151  mov     rcx, rsi; void *
0x18002e154  call    memcpy_0
0x18002e159  lea     rdi, [r14+r14]
0x18002e15d  lea     rsi, ds:0[r15*4]
0x18002e165  lea     rcx, [rsi+rdi]; size
0x18002e169  call    MIDL_user_allocate
0x18002e16e  mov     rbx, rax
0x18002e171  mov     [rsp+138h+arg_30], rax
0x18002e179  test    rax, rax
0x18002e17c  jnz     short loc_18002E1A9
0x18002e17e  lea     rcx, [rsp+138h+arg_30]; this
0x18002e186  call    ??1_FreeFixedLocal@tlx@@QEAA@XZ; tlx::_FreeFixedLocal::~_FreeFixedLocal(void)
0x18002e18b  nop
0x18002e18c  lea     rcx, [rsp+138h+var_78]
0x18002e194  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e199  nop
0x18002e19a  lea     rcx, [rsp+138h+var_F8]; this
0x18002e19f  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e1a4  lea     eax, [rbx+0Eh]
0x18002e1a7  jmp     short loc_18002E21A
0x18002e1a9  mov     r8, rdi; Size
0x18002e1ac  mov     rdx, r13; Src
0x18002e1af  mov     rcx, rbx; void *
0x18002e1b2  call    memcpy_0
0x18002e1b7  lea     rcx, [rdi+rbx]; void *
0x18002e1bb  mov     r8, rsi; Size
0x18002e1be  mov     rdx, r12; Src
0x18002e1c1  call    memcpy_0
0x18002e1c6  lea     edx, [rsi+rdi]; unsigned int
0x18002e1c9  mov     r8, [rsp+138h+arg_40]; struct _GUID *
0x18002e1d1  mov     rcx, rbx; unsigned __int8 *
0x18002e1d4  call    ?Sha256HashToGuid@@YAJPEAEKPEAU_GUID@@@Z; Sha256HashToGuid(uchar *,ulong,_GUID *)
0x18002e1d9  lea     rcx, [rsp+138h+arg_30]; this
0x18002e1e1  call    ??1_FreeFixedLocal@tlx@@QEAA@XZ; tlx::_FreeFixedLocal::~_FreeFixedLocal(void)
0x18002e1e6  nop
0x18002e1e7  lea     rcx, [rsp+138h+var_78]
0x18002e1ef  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18002e1f4  nop
0x18002e1f5  lea     rcx, [rsp+138h+var_F8]; this
0x18002e1fa  call    ??1Buffer@@UEAA@XZ; Buffer::~Buffer(void)
0x18002e1ff  nop
0x18002e200  xor     eax, eax
0x18002e202  jmp     short loc_18002E21A
0x18002e204  test    ebx, ebx
0x18002e206  jnz     loc_18002E073
0x18002e20c  mov     eax, 57h ; 'W'
0x18002e211  jmp     short loc_18002E21A
0x18002e213  mov     eax, [rsp+138h+arg_28]
0x18002e21a  add     rsp, 100h
0x18002e221  pop     r15
0x18002e223  pop     r14
0x18002e225  pop     r13
0x18002e227  pop     r12
0x18002e229  pop     rdi
0x18002e22a  pop     rsi
0x18002e22b  pop     rbx
0x18002e22c  retn
```
