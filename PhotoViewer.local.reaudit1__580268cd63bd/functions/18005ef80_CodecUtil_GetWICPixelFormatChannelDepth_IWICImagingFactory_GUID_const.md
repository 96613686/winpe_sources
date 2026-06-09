# CodecUtil::GetWICPixelFormatChannelDepth(IWICImagingFactory *,_GUID const &)

- ea: `0x18005ef80`
- end: `0x18005f187`
- name: `?GetWICPixelFormatChannelDepth@CodecUtil@@YAIPEAUIWICImagingFactory@@AEBU_GUID@@@Z`
- size: `519`
- prototype: `unsigned int __fastcall(CodecUtil *__hidden this, struct IWICImagingFactory *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800114ec`
- `0x18005ee98`

## callees

- `0x18000cb74`
- `0x18005ef80`
- `0x180080010`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18005f13e`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18005f13e`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18005f0af`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18005f0af`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005efdb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f01b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f046`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f099`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f0f2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f17f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005efdb`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f01b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f046`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f099`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f0f2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005f17f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CodecUtil::GetWICPixelFormatChannelDepth(
        CodecUtil *this,
        struct IWICImagingFactory *a2,
        const struct _GUID *a3)
{
  unsigned int v3; // edi
  __int64 *v4; // r15
  unsigned int v5; // esi
  unsigned __int64 v6; // rax
  int v7; // eax
  int v8; // edx
  __int64 v9; // r8
  void (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // r9
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // eax
  unsigned __int64 v15; // rdx
  bool v16; // r8
  BasePrivate *v17; // rbx
  BasePrivate *v18; // rax
  int v19; // eax
  int v20; // edx
  unsigned __int64 v21; // rdx
  BasePrivate *v22; // r8
  unsigned int i; // r9d
  unsigned int v24; // ecx
  __int64 result; // rax
  __int64 v26; // [rsp+30h] [rbp-48h] BYREF
  void (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-40h] BYREF
  BasePrivate *v28; // [rsp+40h] [rbp-38h]
  _BYTE v29[48]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v31; // [rsp+98h] [rbp+20h] BYREF

  v5 = 8;
  v6 = *(_QWORD *)&GUID_WICPixelFormatDontCare.Data1 - (unsigned __int64)a2->lpVtbl;
  if ( *(struct IWICImagingFactoryVtbl **)&GUID_WICPixelFormatDontCare.Data1 == a2->lpVtbl )
    v6 = *(_QWORD *)GUID_WICPixelFormatDontCare.Data4 - (unsigned __int64)a2[1].lpVtbl;
  try
  {
    if ( v6 )
    {
      if ( !this )
      {
        Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
        goto LABEL_18;
      }
      v27 = 0;
      v7 = (*(__int64 (__fastcall **)(CodecUtil *, struct IWICImagingFactory *, _QWORD))(*(_QWORD *)this + 48LL))(
             this,
             a2,
             &v27);
      if ( v7 < 0 )
        Base::Throw((Base *)(unsigned int)v7, v8);
      v10 = v27;
      v11 = 0;
      v26 = 0;
      if ( v27 )
      {
        (**v27)(v27, &GUID_e8eda601_3d48_431a_ab44_69059be88bbe, &v26);
        v11 = v26;
      }
      if ( !v11 )
        Base::Throw((Base *)0x80070057LL, v8);
      v31 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v11 + 112LL))(
              v11,
              &v31,
              v9,
              v10);
      if ( v12 < 0 )
        Base::Throw((Base *)(unsigned int)v12, v13);
      v3 = 0;
      v4 = `CodecUtil::GetWICPixelFormatChannelDepth'::`20'::kaBits;
      while ( v3 < v31 )
      {
        v30 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v26 + 120LL))(
                v26,
                v3,
                0,
                0,
                &v30);
        if ( v14 < 0 )
          Base::Throw((Base *)(unsigned int)v14, v15);
        v17 = 0;
        v28 = 0;
        LOBYTE(v15) = 1;
        v18 = (BasePrivate *)BasePrivate::New((BasePrivate *)v30, v15, v16);
        if ( v18 )
LABEL_18:
          v17 = v18;
        v28 = v17;
        v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BasePrivate *, unsigned int *))(*(_QWORD *)v26 + 120LL))(
                v26,
                v3,
                v30,
                v17,
                &v30);
        if ( v19 < 0 )
          Base::Throw((Base *)(unsigned int)v19, v20);
        v21 = 0;
        v22 = v17;
        for ( i = 0; i < v30; ++i )
        {
          v24 = *(unsigned __int8 *)v22;
          v22 = (BasePrivate *)((char *)v22 + 1);
          v21 = (unsigned int)(*((_DWORD *)v4 + (v24 & 0xF)) + *((_DWORD *)v4 + ((unsigned __int64)v24 >> 4)) + v21);
        }
        if ( (unsigned int)v21 <= v5 )
          v21 = v5;
        v5 = v21;
        if ( v17 )
          BasePrivate::Delete(v17, (void *)v21);
        ++v3;
      }
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v26);
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v27);
    }
    result = v5;
  }
  catch ( Base::Exception v29 )
  {
    Base::Exception::~Exception((Base::Exception *)v29);
    return 32;
  }
  return result;
}

```

## disassembly

```asm
0x18005ef80  mov     [rsp+arg_0], rbx
0x18005ef85  push    rsi
0x18005ef86  push    rdi
0x18005ef87  push    r15
0x18005ef89  sub     rsp, 60h
0x18005ef8d  mov     esi, 8
0x18005ef92  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data1
0x18005ef99  sub     rax, [rdx]
0x18005ef9c  jnz     short loc_18005EFA9
0x18005ef9e  mov     rax, qword ptr cs:GUID_WICPixelFormatDontCare.Data4
0x18005efa5  sub     rax, [rdx+8]
0x18005efa9  test    rax, rax
0x18005efac  jz      loc_18005F160
0x18005efb2  test    rcx, rcx
0x18005efb5  jz      loc_18005F17A
0x18005efbb  mov     [rsp+78h+var_40], 0
0x18005efc4  mov     rax, [rcx]
0x18005efc7  lea     r8, [rsp+78h+var_40]
0x18005efcc  mov     rax, [rax+30h]
0x18005efd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efd5  test    eax, eax
0x18005efd7  jns     short loc_18005EFE1
0x18005efd9  mov     ecx, eax
0x18005efdb  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005efe1  mov     r9, [rsp+78h+var_40]
0x18005efe6  xor     ecx, ecx
0x18005efe8  mov     [rsp+78h+var_48], rcx
0x18005efed  test    r9, r9
0x18005eff0  jz      short loc_18005F011
0x18005eff2  mov     rax, [r9]
0x18005eff5  lea     r8, [rsp+78h+var_48]
0x18005effa  lea     rdx, _GUID_e8eda601_3d48_431a_ab44_69059be88bbe
0x18005f001  mov     rcx, r9
0x18005f004  mov     rax, [rax]
0x18005f007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f00c  mov     rcx, [rsp+78h+var_48]
0x18005f011  test    rcx, rcx
0x18005f014  jnz     short loc_18005F021
0x18005f016  mov     ecx, 80070057h
0x18005f01b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005f021  mov     [rsp+78h+arg_18], 0
0x18005f02c  mov     rax, [rcx]
0x18005f02f  lea     rdx, [rsp+78h+arg_18]
0x18005f037  mov     rax, [rax+70h]
0x18005f03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f040  test    eax, eax
0x18005f042  jns     short loc_18005F04C
0x18005f044  mov     ecx, eax
0x18005f046  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005f04c  xor     edi, edi
0x18005f04e  lea     r15, ?kaBits@?BE@??GetWICPixelFormatChannelDepth@CodecUtil@@YAIPEAUIWICImagingFactory@@AEBU_GUID@@@Z@4QBIB; uint const near * const `CodecUtil::GetWICPixelFormatChannelDepth(IWICImagingFactory *,_GUID const &)'::`20'::kaBits
0x18005f055  cmp     edi, [rsp+78h+arg_18]
0x18005f05c  jnb     loc_18005F14B
0x18005f062  mov     [rsp+78h+arg_10], 0
0x18005f06d  mov     rcx, [rsp+78h+var_48]
0x18005f072  mov     rax, [rcx]
0x18005f075  lea     rdx, [rsp+78h+arg_10]
0x18005f07d  mov     [rsp+78h+var_58], rdx
0x18005f082  xor     r9d, r9d
0x18005f085  xor     r8d, r8d
0x18005f088  mov     edx, edi
0x18005f08a  mov     rax, [rax+78h]
0x18005f08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f093  test    eax, eax
0x18005f095  jns     short loc_18005F09F
0x18005f097  mov     ecx, eax
0x18005f099  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005f09f  xor     ebx, ebx
0x18005f0a1  mov     [rsp+78h+var_38], rbx
0x18005f0a6  mov     ecx, [rsp+78h+arg_10]
0x18005f0ad  mov     dl, 1
0x18005f0af  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18005f0b5  test    rax, rax
0x18005f0b8  cmovnz  rbx, rax
0x18005f0bc  mov     [rsp+78h+var_38], rbx
0x18005f0c1  mov     rcx, [rsp+78h+var_48]
0x18005f0c6  mov     rax, [rcx]
0x18005f0c9  lea     rdx, [rsp+78h+arg_10]
0x18005f0d1  mov     [rsp+78h+var_58], rdx
0x18005f0d6  mov     r9, rbx
0x18005f0d9  mov     r8d, [rsp+78h+arg_10]
0x18005f0e1  mov     edx, edi
0x18005f0e3  mov     rax, [rax+78h]
0x18005f0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f0ec  test    eax, eax
0x18005f0ee  jns     short loc_18005F0F8
0x18005f0f0  mov     ecx, eax
0x18005f0f2  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005f0f8  xor     edx, edx
0x18005f0fa  mov     r8, rbx
0x18005f0fd  xor     r9d, r9d
0x18005f100  mov     r10d, [rsp+78h+arg_10]
0x18005f108  test    r10d, r10d
0x18005f10b  jz      short loc_18005F12F
0x18005f10d  movzx   ecx, byte ptr [r8]
0x18005f111  inc     r8
0x18005f114  mov     eax, ecx
0x18005f116  shr     rax, 4
0x18005f11a  and     ecx, 0Fh
0x18005f11d  mov     eax, [r15+rax*4]
0x18005f121  add     eax, [r15+rcx*4]
0x18005f125  add     edx, eax
0x18005f127  inc     r9d
0x18005f12a  cmp     r9d, r10d
0x18005f12d  jb      short loc_18005F10D
0x18005f12f  cmp     edx, esi
0x18005f131  cmovbe  edx, esi
0x18005f134  mov     esi, edx
0x18005f136  test    rbx, rbx
0x18005f139  jz      short loc_18005F144
0x18005f13b  mov     rcx, rbx
0x18005f13e  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18005f144  inc     edi
0x18005f146  jmp     loc_18005F055
0x18005f14b  lea     rcx, [rsp+78h+var_48]
0x18005f150  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005f155  nop
0x18005f156  lea     rcx, [rsp+78h+var_40]
0x18005f15b  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005f160  mov     eax, esi
0x18005f162  jmp     short loc_18005F169
0x18005f164  mov     eax, 20h ; ' '
0x18005f169  mov     rbx, [rsp+78h+arg_0]
0x18005f171  add     rsp, 60h
0x18005f175  pop     r15
0x18005f177  pop     rdi
0x18005f178  pop     rsi
0x18005f179  retn
0x18005f17a  mov     ecx, 80004003h
0x18005f17f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
```
