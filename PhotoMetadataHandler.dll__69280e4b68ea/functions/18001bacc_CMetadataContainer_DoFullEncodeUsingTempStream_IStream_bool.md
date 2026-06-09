# CMetadataContainer::_DoFullEncodeUsingTempStream(IStream *,bool)

- ea: `0x18001bacc`
- end: `0x18001bcc1`
- name: `?_DoFullEncodeUsingTempStream@CMetadataContainer@@AEAAJPEAUIStream@@_N@Z`
- size: `501`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this, struct IStream *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c560`
- `0x18001c63c`

## callees

- `0x180008b54`
- `0x18001bacc`
- `0x18001c990`
- `0x18001cc90`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)v12);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v10);
            }
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001bacc  mov     [rsp-28h+arg_8], rbx
0x18001bad1  push    rbp
0x18001bad2  push    rsi
0x18001bad3  push    rdi
0x18001bad4  push    r14
0x18001bad6  push    r15
0x18001bad8  mov     rbp, rsp
0x18001badb  sub     rsp, 50h
0x18001badf  mov     r15b, r8b
0x18001bae2  mov     r14, rdx
0x18001bae5  mov     rsi, rcx
0x18001bae8  mov     [rbp+arg_18], 0
0x18001baf0  mov     rcx, [rcx+10h]
0x18001baf4  mov     rax, [rcx]
0x18001baf7  lea     rdx, [rsi+50h]
0x18001bafb  lea     r9, [rbp+arg_18]
0x18001baff  lea     r8, GUID_VendorMicrosoft
0x18001bb06  mov     rax, [rax+40h]
0x18001bb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb0f  mov     ebx, eax
0x18001bb11  test    eax, eax
0x18001bb13  js      loc_18001BCA1
0x18001bb19  mov     rcx, [rbp+arg_18]
0x18001bb1d  mov     rax, [rcx]
0x18001bb20  mov     r8d, 2
0x18001bb26  mov     rdx, r14
0x18001bb29  mov     rax, [rax+18h]
0x18001bb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb32  mov     ebx, eax
0x18001bb34  test    eax, eax
0x18001bb36  js      loc_18001BCA1
0x18001bb3c  mov     r8, [rsi+8]; struct IWICBitmapDecoder *
0x18001bb40  mov     rdx, [rbp+arg_18]; struct IWICBitmapEncoder *
0x18001bb44  mov     rcx, rsi; this
0x18001bb47  call    ?_SetUpContainerEncoder@CMetadataContainer@@AEAAJPEAUIWICBitmapEncoder@@PEAUIWICBitmapDecoder@@@Z; CMetadataContainer::_SetUpContainerEncoder(IWICBitmapEncoder *,IWICBitmapDecoder *)
0x18001bb4c  mov     ebx, eax
0x18001bb4e  test    eax, eax
0x18001bb50  js      loc_18001BCA1
0x18001bb56  mov     [rbp+arg_0], 0
0x18001bb5d  mov     rcx, [rsi+8]
0x18001bb61  mov     rax, [rcx]
0x18001bb64  lea     rdx, [rbp+arg_0]
0x18001bb68  mov     rax, [rax+60h]
0x18001bb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb71  mov     ebx, eax
0x18001bb73  xor     edi, edi
0x18001bb75  cmp     [rbp+arg_0], edi
0x18001bb78  jbe     loc_18001BC56
0x18001bb7e  test    ebx, ebx
0x18001bb80  js      loc_18001BCA1
0x18001bb86  mov     [rbp+var_18], 0
0x18001bb8e  mov     rcx, [rsi+8]
0x18001bb92  mov     rax, [rcx]
0x18001bb95  lea     r8, [rbp+var_18]
0x18001bb99  mov     edx, edi
0x18001bb9b  mov     rax, [rax+68h]
0x18001bb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bba4  mov     ebx, eax
0x18001bba6  test    eax, eax
0x18001bba8  js      loc_18001BC42
0x18001bbae  mov     [rbp+var_20], 0
0x18001bbb6  mov     [rbp+var_10], 0
0x18001bbbe  mov     rcx, [rbp+arg_18]
0x18001bbc2  mov     rax, [rcx]
0x18001bbc5  lea     r8, [rbp+var_10]
0x18001bbc9  lea     rdx, [rbp+var_20]
0x18001bbcd  mov     rax, [rax+50h]
0x18001bbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd6  mov     ebx, eax
0x18001bbd8  test    eax, eax
0x18001bbda  js      short loc_18001BC2E
0x18001bbdc  mov     [rsp+50h+var_28], r15b; bool
0x18001bbe1  mov     [rsp+50h+var_30], edi; unsigned int
0x18001bbe5  mov     r9, [rbp+var_10]; struct IPropertyBag2 *
0x18001bbe9  mov     r8, [rbp+var_18]; struct IWICBitmapFrameDecode *
0x18001bbed  mov     rdx, [rbp+var_20]; struct IWICBitmapFrameEncode *
0x18001bbf1  mov     rcx, rsi; this
0x18001bbf4  call    ?_SetUpFrameEncoder@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameEncode@@PEAUIWICBitmapFrameDecode@@PEAUIPropertyBag2@@I_N@Z; CMetadataContainer::_SetUpFrameEncoder(IWICBitmapFrameEncode *,IWICBitmapFrameDecode *,IPropertyBag2 *,uint,bool)
0x18001bbf9  mov     ebx, eax
0x18001bbfb  test    eax, eax
0x18001bbfd  js      short loc_18001BC2E
0x18001bbff  mov     rcx, [rbp+var_20]
0x18001bc03  mov     rax, [rcx]
0x18001bc06  xor     r8d, r8d
0x18001bc09  mov     rdx, [rbp+var_18]
0x18001bc0d  mov     rax, [rax+58h]
0x18001bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc16  mov     ebx, eax
0x18001bc18  test    eax, eax
0x18001bc1a  js      short loc_18001BC2E
0x18001bc1c  mov     rcx, [rbp+var_20]
0x18001bc20  mov     rax, [rcx]
0x18001bc23  mov     rax, [rax+60h]
0x18001bc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc2c  mov     ebx, eax
0x18001bc2e  lea     rcx, [rbp+var_10]
0x18001bc32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bc37  nop
0x18001bc38  lea     rcx, [rbp+var_20]
0x18001bc3c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bc41  nop
0x18001bc42  lea     rcx, [rbp+var_18]
0x18001bc46  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bc4b  inc     edi
0x18001bc4d  cmp     edi, [rbp+arg_0]
0x18001bc50  jb      loc_18001BB7E
0x18001bc56  test    ebx, ebx
0x18001bc58  js      short loc_18001BCA1
0x18001bc5a  mov     rcx, [rbp+arg_18]
0x18001bc5e  mov     rax, [rcx]
0x18001bc61  mov     rax, [rax+58h]
0x18001bc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc6a  mov     ebx, eax
0x18001bc6c  test    eax, eax
0x18001bc6e  js      short loc_18001BCA1
0x18001bc70  mov     rcx, [rbp+arg_18]
0x18001bc74  test    rcx, rcx
0x18001bc77  jz      short loc_18001BC8E
0x18001bc79  mov     [rbp+arg_18], 0
0x18001bc81  mov     rax, [rcx]
0x18001bc84  mov     rax, [rax+10h]
0x18001bc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc8d  nop
0x18001bc8e  mov     rax, [r14]
0x18001bc91  xor     edx, edx
0x18001bc93  mov     rcx, r14
0x18001bc96  mov     rax, [rax+40h]
0x18001bc9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc9f  mov     ebx, eax
0x18001bca1  lea     rcx, [rbp+arg_18]
0x18001bca5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bcaa  mov     eax, ebx
0x18001bcac  mov     rbx, [rsp+50h+arg_8]
0x18001bcb4  add     rsp, 50h
0x18001bcb8  pop     r15
0x18001bcba  pop     r14
0x18001bcbc  pop     rdi
0x18001bcbd  pop     rsi
0x18001bcbe  pop     rbp
0x18001bcbf  retn
```
