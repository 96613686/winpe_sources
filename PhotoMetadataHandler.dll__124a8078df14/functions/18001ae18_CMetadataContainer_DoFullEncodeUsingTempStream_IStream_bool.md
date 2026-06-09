# CMetadataContainer::_DoFullEncodeUsingTempStream(IStream *,bool)

- ea: `0x18001ae18`
- end: `0x18001b00c`
- name: `?_DoFullEncodeUsingTempStream@CMetadataContainer@@AEAAJPEAUIStream@@_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IStream *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b884`
- `0x18001b95c`

## callees

- `0x180007804`
- `0x18001ae18`
- `0x18001bc9c`
- `0x18001bf8c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall CMetadataContainer::_DoFullEncodeUsingTempStream(
        CMetadataContainer *this,
        struct IStream *a2,
        bool a3)
{
  int v6; // ebx
  unsigned int v7; // edi
  struct IWICBitmapEncoder *v8; // rcx
  struct IWICBitmapFrameEncode *v10; // [rsp+30h] [rbp-20h] BYREF
  struct IWICBitmapFrameDecode *v11; // [rsp+38h] [rbp-18h] BYREF
  struct IPropertyBag2 *v12[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+80h] [rbp+30h] BYREF
  struct IWICBitmapEncoder *v14; // [rsp+98h] [rbp+48h] BYREF

  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, char *, GUID *, struct IWICBitmapEncoder **))(**((_QWORD **)this + 2) + 64LL))(
         *((_QWORD *)this + 2),
         (char *)this + 80,
         &GUID_VendorMicrosoft,
         &v14);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *, struct IStream *, __int64))v14->lpVtbl->Initialize)(
           v14,
           a2,
           2);
    if ( v6 >= 0 )
    {
      v6 = CMetadataContainer::_SetUpContainerEncoder(this, v14, *((struct IWICBitmapDecoder **)this + 1));
      if ( v6 >= 0 )
      {
        v13 = 0;
        v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 1) + 96LL))(
               *((_QWORD *)this + 1),
               &v13);
        v7 = 0;
        if ( v13 )
        {
          while ( v6 >= 0 )
          {
            v11 = 0;
            v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWICBitmapFrameDecode **))(**((_QWORD **)this + 1)
                                                                                            + 104LL))(
                   *((_QWORD *)this + 1),
                   v7,
                   &v11);
            if ( v6 >= 0 )
            {
              v10 = 0;
              v12[0] = 0;
              v6 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *, struct IWICBitmapFrameEncode **, struct IPropertyBag2 **))v14->lpVtbl->CreateNewFrame)(
                     v14,
                     &v10,
                     v12);
              if ( v6 >= 0 )
              {
                v6 = CMetadataContainer::_SetUpFrameEncoder(this, v10, v11, v12[0], v7, a3);
                if ( v6 >= 0 )
                {
                  v6 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *, struct IWICBitmapFrameDecode *, _QWORD))v10->lpVtbl->WriteSource)(
                         v10,
                         v11,
                         0);
                  if ( v6 >= 0 )
                    v6 = ((__int64 (__fastcall *)(struct IWICBitmapFrameEncode *))v10->lpVtbl->Commit)(v10);
                }
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v12);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
            if ( ++v7 >= v13 )
              goto LABEL_13;
          }
        }
        else
        {
LABEL_13:
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(struct IWICBitmapEncoder *))v14->lpVtbl->Commit)(v14);
            if ( v6 >= 0 )
            {
              v8 = v14;
              if ( v14 )
              {
                v14 = 0;
                ((void (__fastcall *)(struct IWICBitmapEncoder *))v8->lpVtbl->Release)(v8);
              }
              v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD))a2->lpVtbl->Commit)(a2, 0);
            }
          }
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ae18  mov     [rsp-28h+arg_8], rbx
0x18001ae1d  push    rbp
0x18001ae1e  push    rsi
0x18001ae1f  push    rdi
0x18001ae20  push    r14
0x18001ae22  push    r15
0x18001ae24  mov     rbp, rsp
0x18001ae27  sub     rsp, 50h
0x18001ae2b  mov     r15b, r8b
0x18001ae2e  mov     r14, rdx
0x18001ae31  mov     rsi, rcx
0x18001ae34  mov     [rbp+arg_18], 0
0x18001ae3c  mov     rcx, [rcx+10h]
0x18001ae40  mov     rax, [rcx]
0x18001ae43  lea     rdx, [rsi+50h]
0x18001ae47  lea     r9, [rbp+arg_18]
0x18001ae4b  lea     r8, GUID_VendorMicrosoft
0x18001ae52  mov     rax, [rax+40h]
0x18001ae56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae5b  mov     ebx, eax
0x18001ae5d  test    eax, eax
0x18001ae5f  js      loc_18001AFED
0x18001ae65  mov     rcx, [rbp+arg_18]
0x18001ae69  mov     rax, [rcx]
0x18001ae6c  mov     r8d, 2
0x18001ae72  mov     rdx, r14
0x18001ae75  mov     rax, [rax+18h]
0x18001ae79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae7e  mov     ebx, eax
0x18001ae80  test    eax, eax
0x18001ae82  js      loc_18001AFED
0x18001ae88  mov     r8, [rsi+8]; struct IWICBitmapDecoder *
0x18001ae8c  mov     rdx, [rbp+arg_18]; struct IWICBitmapEncoder *
0x18001ae90  mov     rcx, rsi; this
0x18001ae93  call    ?_SetUpContainerEncoder@CMetadataContainer@@AEAAJPEAUIWICBitmapEncoder@@PEAUIWICBitmapDecoder@@@Z; CMetadataContainer::_SetUpContainerEncoder(IWICBitmapEncoder *,IWICBitmapDecoder *)
0x18001ae98  mov     ebx, eax
0x18001ae9a  test    eax, eax
0x18001ae9c  js      loc_18001AFED
0x18001aea2  mov     [rbp+arg_0], 0
0x18001aea9  mov     rcx, [rsi+8]
0x18001aead  mov     rax, [rcx]
0x18001aeb0  lea     rdx, [rbp+arg_0]
0x18001aeb4  mov     rax, [rax+60h]
0x18001aeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aebd  mov     ebx, eax
0x18001aebf  xor     edi, edi
0x18001aec1  cmp     [rbp+arg_0], edi
0x18001aec4  jbe     loc_18001AFA2
0x18001aeca  test    ebx, ebx
0x18001aecc  js      loc_18001AFED
0x18001aed2  mov     [rbp+var_18], 0
0x18001aeda  mov     rcx, [rsi+8]
0x18001aede  mov     rax, [rcx]
0x18001aee1  lea     r8, [rbp+var_18]
0x18001aee5  mov     edx, edi
0x18001aee7  mov     rax, [rax+68h]
0x18001aeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef0  mov     ebx, eax
0x18001aef2  test    eax, eax
0x18001aef4  js      loc_18001AF8E
0x18001aefa  mov     [rbp+var_20], 0
0x18001af02  mov     [rbp+var_10], 0
0x18001af0a  mov     rcx, [rbp+arg_18]
0x18001af0e  mov     rax, [rcx]
0x18001af11  lea     r8, [rbp+var_10]
0x18001af15  lea     rdx, [rbp+var_20]
0x18001af19  mov     rax, [rax+50h]
0x18001af1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af22  mov     ebx, eax
0x18001af24  test    eax, eax
0x18001af26  js      short loc_18001AF7A
0x18001af28  mov     [rsp+50h+var_28], r15b; bool
0x18001af2d  mov     [rsp+50h+var_30], edi; unsigned int
0x18001af31  mov     r9, [rbp+var_10]; struct IPropertyBag2 *
0x18001af35  mov     r8, [rbp+var_18]; struct IWICBitmapFrameDecode *
0x18001af39  mov     rdx, [rbp+var_20]; struct IWICBitmapFrameEncode *
0x18001af3d  mov     rcx, rsi; this
0x18001af40  call    ?_SetUpFrameEncoder@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameEncode@@PEAUIWICBitmapFrameDecode@@PEAUIPropertyBag2@@I_N@Z; CMetadataContainer::_SetUpFrameEncoder(IWICBitmapFrameEncode *,IWICBitmapFrameDecode *,IPropertyBag2 *,uint,bool)
0x18001af45  mov     ebx, eax
0x18001af47  test    eax, eax
0x18001af49  js      short loc_18001AF7A
0x18001af4b  mov     rcx, [rbp+var_20]
0x18001af4f  mov     rax, [rcx]
0x18001af52  xor     r8d, r8d
0x18001af55  mov     rdx, [rbp+var_18]
0x18001af59  mov     rax, [rax+58h]
0x18001af5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af62  mov     ebx, eax
0x18001af64  test    eax, eax
0x18001af66  js      short loc_18001AF7A
0x18001af68  mov     rcx, [rbp+var_20]
0x18001af6c  mov     rax, [rcx]
0x18001af6f  mov     rax, [rax+60h]
0x18001af73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af78  mov     ebx, eax
0x18001af7a  lea     rcx, [rbp+var_10]
0x18001af7e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001af83  nop
0x18001af84  lea     rcx, [rbp+var_20]
0x18001af88  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001af8d  nop
0x18001af8e  lea     rcx, [rbp+var_18]
0x18001af92  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001af97  inc     edi
0x18001af99  cmp     edi, [rbp+arg_0]
0x18001af9c  jb      loc_18001AECA
0x18001afa2  test    ebx, ebx
0x18001afa4  js      short loc_18001AFED
0x18001afa6  mov     rcx, [rbp+arg_18]
0x18001afaa  mov     rax, [rcx]
0x18001afad  mov     rax, [rax+58h]
0x18001afb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afb6  mov     ebx, eax
0x18001afb8  test    eax, eax
0x18001afba  js      short loc_18001AFED
0x18001afbc  mov     rcx, [rbp+arg_18]
0x18001afc0  test    rcx, rcx
0x18001afc3  jz      short loc_18001AFDA
0x18001afc5  mov     [rbp+arg_18], 0
0x18001afcd  mov     rax, [rcx]
0x18001afd0  mov     rax, [rax+10h]
0x18001afd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afd9  nop
0x18001afda  mov     rax, [r14]
0x18001afdd  xor     edx, edx
0x18001afdf  mov     rcx, r14
0x18001afe2  mov     rax, [rax+40h]
0x18001afe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afeb  mov     ebx, eax
0x18001afed  lea     rcx, [rbp+arg_18]
0x18001aff1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001aff6  mov     eax, ebx
0x18001aff8  mov     rbx, [rsp+50h+arg_8]
0x18001b000  add     rsp, 50h
0x18001b004  pop     r15
0x18001b006  pop     r14
0x18001b008  pop     rdi
0x18001b009  pop     rsi
0x18001b00a  pop     rbp
0x18001b00b  retn
```
