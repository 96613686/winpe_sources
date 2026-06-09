# Common::StringBuffer::SetValueFromString(ushort const *)

- ea: `0x180008db0`
- end: `0x18000902f`
- name: `?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z`
- size: `639`
- prototype: `__int64 __fastcall(Common::StringBuffer *__hidden this, const unsigned __int16 *Src)`
- caller_count: `64`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180002630`
- `0x180002c94`
- `0x180005a0c`
- `0x18000bf10`
- `0x18000d180`
- `0x18000f53c`
- `0x18000f8c4`
- `0x18001073c`
- `0x18001187c`
- `0x180013370`
- `0x1800134d0`
- `0x180013630`
- `0x180013ce4`
- `0x180014240`
- `0x180014a38`
- `0x180015be8`
- `0x180015ff0`
- `0x180016064`
- `0x1800160a0`
- `0x1800160dc`
- `0x18001b5bc`
- `0x18001f888`
- `0x180020794`
- `0x1800210c8`
- `0x180021f34`
- `0x180026214`
- `0x1800279b4`
- `0x180028528`
- `0x18002886c`
- `0x180028e94`
- `0x180029648`
- `0x18002a0f4`
- `0x18002b79c`
- `0x18002c580`
- `0x18002e6d0`
- `0x18002efe0`
- `0x1800313f8`
- `0x1800316b8`
- `0x180031984`
- `0x180031c80`
- `0x180032248`
- `0x18003254c`
- `0x180032eb4`
- `0x1800330c8`
- `0x180033dcc`
- `0x1800340d8`
- `0x180034214`
- `0x1800348b8`
- `0x1800357a0`
- `0x18003650c`

## callees

- `0x180007a10`
- `0x180008db0`
- `0x1800092c0`
- `0x1800093d0`
- `0x180017f50`
- `0x180018248`
- `0x18001ffb4`
- `0x18004c972`

## string_xrefs

- `0x180008deb`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180008f3d`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180008f4e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180008f7d`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180008f96`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180008fd6`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetValueFromString(Common::StringBuffer *this, const unsigned __int16 *Src)
{
  int v2; // r12d
  const unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  unsigned int v8; // edi
  int v9; // ecx
  unsigned int v10; // edx
  unsigned int i; // ebx
  unsigned int v12; // ebp
  __int64 v13; // rdx
  void *v14; // rcx
  int v15; // eax
  unsigned int v16; // esi
  _WORD *v17; // rdx
  unsigned int v18; // eax
  int v19; // edx
  unsigned int v20; // ecx
  __int64 v21; // r9
  __int64 v22; // rdx
  int v23; // eax
  void *v24; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v26; // [rsp+58h] [rbp+10h] BYREF

  if ( Src )
  {
    v5 = Src;
    v6 = 1073741822;
    while ( *v5 )
    {
      ++v5;
      if ( !--v6 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x249,
          (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070057LL);
        return 2147942487LL;
      }
    }
    v8 = 1073741822 - v6;
    if ( (unsigned int)(1073741822 - v6) > 0x7FFFFFFF )
    {
      v16 = -2147024362;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22F,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070216LL);
    }
    else
    {
      v9 = *((_DWORD *)this + 4);
      v10 = 0;
      if ( v9 )
        v10 = v9 - 1;
      if ( v8 <= v10 && v10 <= 0x20 )
        goto LABEL_20;
      if ( v8 <= 0x20 )
      {
        for ( i = 8; i < v8; i *= 2 )
          ;
      }
      else
      {
        i = v8;
      }
      if ( i > 0x3FFFFFFF )
      {
        v16 = -2147023613;
        v22 = 425;
        v21 = 2147943683LL;
      }
      else
      {
        if ( !i )
        {
          v24 = (void *)*((_QWORD *)this + 1);
          if ( v24 )
          {
            Common::GlobalHeap::Free(v24);
            *((_QWORD *)this + 1) = 0;
            *(_DWORD *)this = 0;
          }
          *((_DWORD *)this + 4) = 0;
          goto LABEL_20;
        }
        v12 = i + 1;
        if ( i + 1 == v9 )
        {
LABEL_20:
          v19 = *((_DWORD *)this + 4);
          v20 = 0;
          if ( v19 )
            v20 = v19 - 1;
          if ( v8 <= v20 || (v23 = Common::StringBuffer::SetCapacity(this, v8), v16 = v23, v23 >= 0) )
          {
            *(_DWORD *)this = v8;
            if ( v8 )
              *(_WORD *)(*((_QWORD *)this + 1) + 2LL * v8) = 0;
            memcpy_0(*((void **)this + 1), Src, 2 * v8);
            return 0;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x20C,
              (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)(unsigned int)v23);
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x235,
              (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
              (const char *)v16);
          }
          return v16;
        }
        v13 = *((unsigned int *)this + 4);
        v14 = (void *)*((_QWORD *)this + 1);
        v26 = 0;
        v15 = CommonHeapReAllocDefault(v14, 2 * v13, 2LL * v12, &v26);
        v16 = v15;
        if ( v15 >= 0 )
        {
          v17 = v26;
          v18 = *(_DWORD *)this;
          *((_QWORD *)this + 1) = v26;
          *((_DWORD *)this + 4) = v12;
          if ( v18 > i )
          {
            *(_DWORD *)this = i;
            v17[i] = 0;
          }
          else if ( v18 < i && !v18 )
          {
            *v17 = 0;
          }
          goto LABEL_20;
        }
        v21 = (unsigned int)v15;
        v22 = 458;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v21,
        v2);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x232,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)v16);
    }
    return v16;
  }
  Common::StringBuffer::Clear(this);
  return 0;
}

```

## disassembly

```asm
0x180008db0  push    r14
0x180008db2  push    r15
0x180008db4  sub     rsp, 38h
0x180008db8  mov     r15, rdx
0x180008dbb  mov     r14, rcx
0x180008dbe  test    rdx, rdx
0x180008dc1  jz      loc_180008FC1
0x180008dc7  mov     [rsp+48h+var_20], rdi
0x180008dcc  mov     rax, rdx
0x180008dcf  mov     edi, 3FFFFFFEh
0x180008dd4  mov     ecx, edi
0x180008dd6  cmp     word ptr [rax], 0
0x180008dda  jz      short loc_180008E0C
0x180008ddc  add     rax, 2
0x180008de0  sub     rcx, 1
0x180008de4  jnz     short loc_180008DD6
0x180008de6  mov     rcx, [rsp+48h]; this
0x180008deb  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008df2  mov     r9d, 80070057h; char *
0x180008df8  mov     edx, 249h; void *
0x180008dfd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008e02  mov     eax, 80070057h
0x180008e07  jmp     loc_180008F09
0x180008e0c  sub     edi, ecx
0x180008e0e  mov     [rsp+48h+var_18], rsi
0x180008e13  cmp     edi, 7FFFFFFFh
0x180008e19  ja      loc_180008FD1
0x180008e1f  mov     ecx, [r14+10h]
0x180008e23  mov     [rsp+48h+arg_0], rbx
0x180008e28  mov     [rsp+48h+arg_10], rbp
0x180008e2d  mov     qword ptr [rsp+48h+var_28], r12; int
0x180008e32  xor     r12d, r12d
0x180008e35  test    ecx, ecx
0x180008e37  lea     eax, [rcx-1]
0x180008e3a  mov     edx, r12d
0x180008e3d  cmovnz  edx, eax
0x180008e40  cmp     edi, edx
0x180008e42  jbe     loc_180008FF4
0x180008e48  cmp     edi, 20h ; ' '
0x180008e4b  jbe     loc_180008F17
0x180008e51  mov     ebx, edi
0x180008e53  cmp     ebx, 3FFFFFFFh
0x180008e59  ja      loc_180008FAF
0x180008e5f  test    ebx, ebx
0x180008e61  jz      loc_180009002
0x180008e67  lea     ebp, [rbx+1]
0x180008e6a  cmp     ebp, ecx
0x180008e6c  jz      short loc_180008EB9
0x180008e6e  mov     rdx, rcx
0x180008e71  mov     r8d, ebp
0x180008e74  mov     rcx, [r14+8]; Ptr
0x180008e78  lea     r9, [rsp+48h+arg_8]; void **
0x180008e7d  add     r8, r8; unsigned __int64
0x180008e80  mov     [rsp+48h+arg_8], r12
0x180008e85  add     rdx, rdx; unsigned __int64
0x180008e88  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x180008e8d  mov     esi, eax
0x180008e8f  test    eax, eax
0x180008e91  js      loc_180008F30
0x180008e97  mov     rdx, [rsp+48h+arg_8]
0x180008e9c  mov     eax, [r14]
0x180008e9f  mov     [r14+8], rdx
0x180008ea3  mov     [r14+10h], ebp
0x180008ea7  cmp     eax, ebx
0x180008ea9  ja      loc_180009020
0x180008eaf  jnb     short loc_180008EB9
0x180008eb1  test    eax, eax
0x180008eb3  jnz     short loc_180008EB9
0x180008eb5  mov     [rdx], r12w
0x180008eb9  mov     edx, [r14+10h]
0x180008ebd  mov     ecx, r12d
0x180008ec0  test    edx, edx
0x180008ec2  lea     eax, [rdx-1]
0x180008ec5  cmovnz  ecx, eax
0x180008ec8  cmp     edi, ecx
0x180008eca  ja      loc_180008F64
0x180008ed0  mov     [r14], edi
0x180008ed3  test    edi, edi
0x180008ed5  jz      short loc_180008EE0
0x180008ed7  mov     rcx, [r14+8]
0x180008edb  mov     [rcx+rdi*2], r12w
0x180008ee0  mov     rcx, [r14+8]; void *
0x180008ee4  lea     r8d, [rdi+rdi]; Size
0x180008ee8  mov     rdx, r15; Src
0x180008eeb  call    memcpy_0
0x180008ef0  mov     esi, r12d
0x180008ef3  mov     rbx, [rsp+48h+arg_0]
0x180008ef8  mov     rbp, [rsp+48h+arg_10]
0x180008efd  mov     r12, qword ptr [rsp+48h+var_28]
0x180008f02  mov     eax, esi
0x180008f04  mov     rsi, [rsp+48h+var_18]
0x180008f09  mov     rdi, [rsp+48h+var_20]
0x180008f0e  add     rsp, 38h
0x180008f12  pop     r15
0x180008f14  pop     r14
0x180008f16  retn
0x180008f17  mov     ebx, 8
0x180008f1c  cmp     edi, ebx
0x180008f1e  jbe     loc_180008E53
0x180008f24  add     ebx, ebx
0x180008f26  cmp     ebx, edi
0x180008f28  jnb     loc_180008E53
0x180008f2e  jmp     short loc_180008F24
0x180008f30  mov     r9d, eax; char *
0x180008f33  mov     edx, 1CAh; void *
0x180008f38  mov     rcx, [rsp+48h]; this
0x180008f3d  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008f44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f49  mov     rcx, [rsp+48h]; this
0x180008f4e  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008f55  mov     r9d, esi; char *
0x180008f58  mov     edx, 232h; void *
0x180008f5d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008f62  jmp     short loc_180008EF3
0x180008f64  mov     edx, edi; unsigned int
0x180008f66  mov     rcx, r14; this
0x180008f69  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180008f6e  mov     esi, eax
0x180008f70  test    eax, eax
0x180008f72  jns     loc_180008ED0
0x180008f78  mov     rcx, [rsp+48h]; this
0x180008f7d  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008f84  mov     r9d, eax; char *
0x180008f87  mov     edx, 20Ch; void *
0x180008f8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008f91  mov     rcx, [rsp+48h]; this
0x180008f96  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008f9d  mov     r9d, esi; char *
0x180008fa0  mov     edx, 235h; void *
0x180008fa5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008faa  jmp     loc_180008EF3
0x180008faf  mov     esi, 80070503h
0x180008fb4  mov     edx, 1A9h
0x180008fb9  mov     r9d, esi
0x180008fbc  jmp     loc_180008F38
0x180008fc1  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x180008fc6  xor     eax, eax
0x180008fc8  add     rsp, 38h
0x180008fcc  pop     r15
0x180008fce  pop     r14
0x180008fd0  retn
0x180008fd1  mov     rcx, [rsp+48h]; this
0x180008fd6  lea     r8, aOnecoreBaseApp_14; "onecore\\base\\appmodel\\common\\widest"...
0x180008fdd  mov     esi, 80070216h
0x180008fe2  mov     edx, 22Fh; void *
0x180008fe7  mov     r9d, esi; char *
0x180008fea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008fef  jmp     loc_180008F02
0x180008ff4  cmp     edx, 20h ; ' '
0x180008ff7  jbe     loc_180008EB9
0x180008ffd  jmp     loc_180008E48
0x180009002  mov     rcx, [r14+8]; void *
0x180009006  test    rcx, rcx
0x180009009  jz      short loc_180009017
0x18000900b  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180009010  mov     [r14+8], r12
0x180009014  mov     [r14], r12d
0x180009017  mov     [r14+10h], r12d
0x18000901b  jmp     loc_180008EB9
0x180009020  mov     ecx, ebx
0x180009022  mov     [r14], ebx
0x180009025  mov     [rdx+rcx*2], r12w
0x18000902a  jmp     loc_180008EB9
```
