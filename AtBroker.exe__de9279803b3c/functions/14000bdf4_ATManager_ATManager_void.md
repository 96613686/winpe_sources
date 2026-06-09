# ATManager::~ATManager(void)

- ea: `0x14000bdf4`
- end: `0x14000be4c`
- name: `??1ATManager@@QEAA@XZ`
- size: `88`
- prototype: `void __fastcall(ATManager *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400048b8`
- `0x14000b250`
- `0x14000c8b4`
- `0x14000e1dc`
- `0x140010244`
- `0x140015cf4`
- `0x140015ec8`

## callees

- `0x140001e44`
- `0x14000bdf4`
- `0x14000c108`
- `0x14000cdf4`
- `0x1400113b0`

## pseudocode

```c
void __fastcall ATManager::~ATManager(ATManager *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  Accommodation *v4; // rsi

  v2 = (_QWORD *)((char *)this + 304);
  if ( *((_QWORD *)this + 40) )
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = (Accommodation *)v3[2];
      v3 = (_QWORD *)*v3;
      if ( v4 )
      {
        Accommodation::~Accommodation(v4);
        operator delete(v4);
      }
    }
  }
  ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(v2);
  StartList::~StartList(this);
}

```

## disassembly

```asm
0x14000bdf4  push    rbx
0x14000bdf6  push    rbp
0x14000bdf7  push    rsi
0x14000bdf8  push    rdi
0x14000bdf9  sub     rsp, 28h
0x14000bdfd  mov     rbp, rcx
0x14000be00  lea     rdi, [rcx+130h]
0x14000be07  cmp     qword ptr [rdi+10h], 0
0x14000be0c  jz      short loc_14000BE34
0x14000be0e  mov     rbx, [rdi]
0x14000be11  jmp     short loc_14000BE2F
0x14000be13  mov     rsi, [rbx+10h]
0x14000be17  mov     rbx, [rbx]
0x14000be1a  test    rsi, rsi
0x14000be1d  jz      short loc_14000BE2F
0x14000be1f  mov     rcx, rsi; this
0x14000be22  call    ??1Accommodation@@QEAA@XZ; Accommodation::~Accommodation(void)
0x14000be27  mov     rcx, rsi; Block
0x14000be2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000be2f  test    rbx, rbx
0x14000be32  jnz     short loc_14000BE13
0x14000be34  mov     rcx, rdi
0x14000be37  call    ?RemoveAll@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::RemoveAll(void)
0x14000be3c  mov     rcx, rbp; this
0x14000be3f  add     rsp, 28h
0x14000be43  pop     rdi
0x14000be44  pop     rsi
0x14000be45  pop     rbp
0x14000be46  pop     rbx
0x14000be47  jmp     ??1StartList@@QEAA@XZ; StartList::~StartList(void)
```
