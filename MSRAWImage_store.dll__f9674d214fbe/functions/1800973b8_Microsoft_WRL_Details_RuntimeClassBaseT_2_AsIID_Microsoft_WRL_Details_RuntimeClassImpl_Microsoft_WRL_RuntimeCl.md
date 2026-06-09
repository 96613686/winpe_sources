# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWICRawMetadataBlockReaderBase,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWICRawMetadataBlockReaderBase,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x1800973b8`
- end: `0x18009748c`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCWICRawMetadataBlockReaderBase@@UIWICMetadataBlockReader@@U?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCWICRawMetadataBlockReaderBase@@UIWICMetadataBlockReader@@U?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009d090`

## callees

- `0x180096010`
- `0x1800970ec`
- `0x1800973b8`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWICRawMetadataBlockReaderBase,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  void **v8; // r8
  void *v9; // r9
  int CanCastTo; // ebx
  __int64 v11; // rcx
  void *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r9
  const struct _GUID *v15; // r10

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1) )
    {
      *v8 = v9;
      CanCastTo = 0;
      goto LABEL_13;
    }
    if ( (unsigned int)InlineIsEqualGUID(v7, v6) )
    {
      *v8 = v12;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(v11, &GUID_3b16811b_6a43_4ec9_a813_3d930c13b940)
        && !(unsigned int)InlineIsEqualGUID(v13, &GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94) )
      {
        CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v14 + 8), v15, v8);
        if ( CanCastTo == -2147467262 )
          CanCastTo = -2147467262;
LABEL_12:
        if ( CanCastTo < 0 )
          return (unsigned int)CanCastTo;
LABEL_13:
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v8 + 8LL))(*v8, *(_QWORD *)*v8);
        return (unsigned int)CanCastTo;
      }
      *v8 = (void *)v14;
    }
    CanCastTo = 0;
    goto LABEL_12;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1800973b8  push    rbx
0x1800973ba  sub     rsp, 30h
0x1800973be  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800973c7  mov     r10, rdx
0x1800973ca  mov     r9, rcx
0x1800973cd  mov     qword ptr [r8], 0
0x1800973d4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800973db  mov     rcx, r10
0x1800973de  call    InlineIsEqualGUID
0x1800973e3  test    eax, eax
0x1800973e5  jnz     loc_180097471
0x1800973eb  lea     rdx, _GUID_feaa2a8d_b3f3_43e4_b25c_d1de990a1ae1
0x1800973f2  call    InlineIsEqualGUID
0x1800973f7  test    eax, eax
0x1800973f9  jz      short loc_180097402
0x1800973fb  mov     [r8], r9
0x1800973fe  xor     ebx, ebx
0x180097400  jmp     short loc_18009745E
0x180097402  add     r9, 68h ; 'h'
0x180097406  call    InlineIsEqualGUID
0x18009740b  test    eax, eax
0x18009740d  jz      short loc_180097416
0x18009740f  mov     [r8], r9
0x180097412  xor     ebx, ebx
0x180097414  jmp     short loc_18009745A
0x180097416  add     r9, 8
0x18009741a  lea     rdx, _GUID_3b16811b_6a43_4ec9_a813_3d930c13b940
0x180097421  call    InlineIsEqualGUID
0x180097426  test    eax, eax
0x180097428  jnz     short loc_18009743A
0x18009742a  lea     rdx, _GUID_00000120_a8f2_4877_ba0a_fd2b6645fb94
0x180097431  call    InlineIsEqualGUID
0x180097436  test    eax, eax
0x180097438  jz      short loc_180097442
0x18009743a  mov     rax, r8
0x18009743d  mov     [rax], r9
0x180097440  jmp     short loc_180097412
0x180097442  lea     rcx, [r9+8]; this
0x180097446  mov     rdx, r10; struct _GUID *
0x180097449  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x18009744e  mov     ebx, eax
0x180097450  mov     eax, 80004002h
0x180097455  cmp     ebx, eax
0x180097457  cmovz   ebx, eax
0x18009745a  test    ebx, ebx
0x18009745c  js      short loc_18009746D
0x18009745e  mov     rcx, [r8]
0x180097461  mov     rdx, [rcx]
0x180097464  mov     rax, [rdx+8]
0x180097468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009746d  mov     eax, ebx
0x18009746f  jmp     short loc_180097485
0x180097471  mov     [r8], r9
0x180097474  mov     rax, [r9]
0x180097477  mov     rcx, r9
0x18009747a  mov     rax, [rax+8]
0x18009747e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097483  xor     eax, eax
0x180097485  add     rsp, 30h
0x180097489  pop     rbx
0x18009748a  retn
```
