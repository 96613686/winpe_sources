# CMetadataContainer::Commit(void)

- ea: `0x18001a658`
- end: `0x18001a860`
- name: `?Commit@CMetadataContainer@@QEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001c5d0`

## callees

- `0x180002360`
- `0x180004490`
- `0x180004d50`
- `0x1800052a8`
- `0x180005328`
- `0x180007804`
- `0x18000db50`
- `0x18001a658`
- `0x18001b83c`
- `0x18001c380`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMetadataContainer::Commit(CMetadataContainer *this)
{
  CMetadataContainer *v1; // rbx
  __int64 result; // rax
  int v3; // esi
  CPhotoPropertyItemList *v4; // r14
  unsigned int v5; // eax
  int v6; // r10d
  struct IWICMetadataQueryWriter *v7; // [rsp+20h] [rbp-38h] BYREF
  CPhotoPropertyItemList *v8; // [rsp+28h] [rbp-30h]
  const ATL::CAtlException *v9; // [rsp+30h] [rbp-28h] BYREF
  struct IWICBitmapFrameDecode *v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v1 = this;
  result = CMetadataContainer::ReadInMetadata(this);
  v3 = result;
  if ( (int)result >= 0 )
  {
    v4 = (CMetadataContainer *)((char *)v1 + 120);
    v8 = (CMetadataContainer *)((char *)v1 + 120);
    if ( *((_DWORD *)v1 + 28) || CPhotoPropertyItemList::GetCount((CMetadataContainer *)((char *)v1 + 120)) )
    {
      v11 = 0;
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWICBitmapFrameDecode **))(**((_QWORD **)v1 + 1) + 104LL))(
             *((_QWORD *)v1 + 1),
             0,
             &v11);
      if ( v3 >= 0 )
      {
        v12 = 0;
        v3 = (*(__int64 (__fastcall **)(_QWORD, struct IWICBitmapFrameDecode *, __int64 *))(**((_QWORD **)v1 + 2) + 200LL))(
               *((_QWORD *)v1 + 2),
               v11,
               &v12);
        if ( v3 >= 0 )
        {
          v7 = 0;
          v3 = (*(__int64 (__fastcall **)(__int64, struct IWICMetadataQueryWriter **))(*(_QWORD *)v12 + 32LL))(v12, &v7);
          if ( v3 >= 0 )
          {
            v3 = CMetadataContainer::_WriteOutDirtyItems(v1, v7);
            if ( v3 >= 0 )
            {
              if ( CPhotoPropertyItemList::GetCount((CMetadataContainer *)((char *)v1 + 120)) )
                goto LABEL_18;
              try
              {
                v5 = CContainerMasks::LookupContainerMask((const struct _GUID *)v1 + 5);
                if ( v5 == 1 || v5 == 2 && *((_QWORD *)v1 + 9) <= 0x1E00000u )
                  v6 = 0;
              }
              catch ( const ATL::CAtlException *v9 )
              {
                v1 = this;
                v6 = *(_DWORD *)v9;
                v4 = v8;
              }
              if ( v6 < 0
                || (*(int (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12) < 0
                || (v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v1 + 64LL))(*(_QWORD *)v1, 0), v3 < 0) )
              {
LABEL_18:
                v3 = CMetadataContainer::_EncodeFullImage(v1, v11, 1);
                if ( v3 == -2003292334 )
                  v3 = CMetadataContainer::_EncodeFullImage(v1, v11, 0);
              }
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v7);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
    }
    ATL::CComPtrBase<IWICComponentFactory>::Release((char *)v1 + 16);
    ATL::CComPtrBase<IWICComponentFactory>::Release((char *)v1 + 8);
    ATL::CComPtrBase<IStream>::Release(v1);
    *((_DWORD *)v1 + 6) = 0;
    *((_BYTE *)v1 + 28) = 0;
    *((_QWORD *)v1 + 4) = 0;
    *((_QWORD *)v1 + 5) = 0;
    *((_QWORD *)v1 + 6) = 0;
    *(GUID *)((char *)v1 + 56) = GUID_NULL;
    *((GUID *)v1 + 5) = GUID_NULL;
    CPhotoPropertyItemList::ClearList((CMetadataContainer *)((char *)v1 + 96));
    CPhotoPropertyItemList::ClearList(v4);
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x18001a658  mov     [rsp+arg_0], rcx
0x18001a65d  push    rbx
0x18001a65e  push    rsi
0x18001a65f  push    r14
0x18001a661  sub     rsp, 40h
0x18001a665  mov     rbx, rcx
0x18001a668  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001a66d  mov     esi, eax
0x18001a66f  test    eax, eax
0x18001a671  js      loc_18001A857
0x18001a677  lea     r14, [rbx+78h]
0x18001a67b  mov     [rsp+58h+var_30], r14
0x18001a680  cmp     dword ptr [rbx+70h], 0
0x18001a684  ja      short loc_18001A696
0x18001a686  mov     rcx, r14; this
0x18001a689  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001a68e  test    eax, eax
0x18001a690  jz      loc_18001A7EF
0x18001a696  mov     [rsp+58h+arg_10], 0
0x18001a69f  mov     rcx, [rbx+8]
0x18001a6a3  mov     rax, [rcx]
0x18001a6a6  lea     r8, [rsp+58h+arg_10]
0x18001a6ab  xor     edx, edx
0x18001a6ad  mov     rax, [rax+68h]
0x18001a6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6b6  mov     esi, eax
0x18001a6b8  test    eax, eax
0x18001a6ba  js      loc_18001A7E5
0x18001a6c0  mov     [rsp+58h+arg_18], 0
0x18001a6c9  mov     rcx, [rbx+10h]
0x18001a6cd  mov     rax, [rcx]
0x18001a6d0  lea     r8, [rsp+58h+arg_18]
0x18001a6d5  mov     rdx, [rsp+58h+arg_10]
0x18001a6da  mov     rax, [rax+0C8h]
0x18001a6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6e6  mov     esi, eax
0x18001a6e8  test    eax, eax
0x18001a6ea  js      loc_18001A7DA
0x18001a6f0  mov     [rsp+58h+var_38], 0
0x18001a6f9  mov     rcx, [rsp+58h+arg_18]
0x18001a6fe  mov     rax, [rcx]
0x18001a701  lea     rdx, [rsp+58h+var_38]
0x18001a706  mov     rax, [rax+20h]
0x18001a70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a70f  mov     esi, eax
0x18001a711  test    eax, eax
0x18001a713  js      loc_18001A7CF
0x18001a719  mov     rdx, [rsp+58h+var_38]; struct IWICMetadataQueryWriter *
0x18001a71e  mov     rcx, rbx; this
0x18001a721  call    ?_WriteOutDirtyItems@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z; CMetadataContainer::_WriteOutDirtyItems(IWICMetadataQueryWriter *)
0x18001a726  mov     esi, eax
0x18001a728  test    eax, eax
0x18001a72a  js      loc_18001A7CF
0x18001a730  mov     r10d, 80004005h
0x18001a736  mov     rcx, r14; this
0x18001a739  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001a73e  test    eax, eax
0x18001a740  jnz     short loc_18001A7A4
0x18001a742  lea     rcx, [rbx+50h]; struct _GUID *
0x18001a746  call    ?LookupContainerMask@CContainerMasks@@SAKAEBU_GUID@@@Z; CContainerMasks::LookupContainerMask(_GUID const &)
0x18001a74b  cmp     eax, 1
0x18001a74e  jz      short loc_18001A75F
0x18001a750  cmp     eax, 2
0x18001a753  jnz     short loc_18001A762
0x18001a755  cmp     qword ptr [rbx+48h], 1E00000h
0x18001a75d  ja      short loc_18001A762
0x18001a75f  xor     r10d, r10d
0x18001a762  jmp     short loc_18001A773
0x18001a764  mov     rbx, [rsp+58h+arg_0]
0x18001a769  mov     r10d, [rsp+58h+arg_8]
0x18001a76e  mov     r14, [rsp+58h+var_30]
0x18001a773  test    r10d, r10d
0x18001a776  js      short loc_18001A7A4
0x18001a778  mov     rcx, [rsp+58h+arg_18]
0x18001a77d  mov     rax, [rcx]
0x18001a780  mov     rax, [rax+18h]
0x18001a784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a789  test    eax, eax
0x18001a78b  js      short loc_18001A7A4
0x18001a78d  mov     rcx, [rbx]
0x18001a790  mov     rax, [rcx]
0x18001a793  xor     edx, edx
0x18001a795  mov     rax, [rax+40h]
0x18001a799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a79e  mov     esi, eax
0x18001a7a0  test    eax, eax
0x18001a7a2  jns     short loc_18001A7CF
0x18001a7a4  mov     r8b, 1; bool
0x18001a7a7  mov     rdx, [rsp+58h+arg_10]; struct IWICBitmapFrameDecode *
0x18001a7ac  mov     rcx, rbx; this
0x18001a7af  call    ?_EncodeFullImage@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameDecode@@_N@Z; CMetadataContainer::_EncodeFullImage(IWICBitmapFrameDecode *,bool)
0x18001a7b4  mov     esi, eax
0x18001a7b6  cmp     eax, 88982F52h
0x18001a7bb  jnz     short loc_18001A7CF
0x18001a7bd  xor     r8d, r8d; bool
0x18001a7c0  mov     rdx, [rsp+58h+arg_10]; struct IWICBitmapFrameDecode *
0x18001a7c5  mov     rcx, rbx; this
0x18001a7c8  call    ?_EncodeFullImage@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameDecode@@_N@Z; CMetadataContainer::_EncodeFullImage(IWICBitmapFrameDecode *,bool)
0x18001a7cd  mov     esi, eax
0x18001a7cf  lea     rcx, [rsp+58h+var_38]
0x18001a7d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a7d9  nop
0x18001a7da  lea     rcx, [rsp+58h+arg_18]
0x18001a7df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a7e4  nop
0x18001a7e5  lea     rcx, [rsp+58h+arg_10]
0x18001a7ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a7ef  lea     rcx, [rbx+10h]
0x18001a7f3  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001a7f8  lea     rcx, [rbx+8]
0x18001a7fc  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001a801  mov     rcx, rbx
0x18001a804  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001a809  mov     dword ptr [rbx+18h], 0
0x18001a810  mov     byte ptr [rbx+1Ch], 0
0x18001a814  mov     qword ptr [rbx+20h], 0
0x18001a81c  mov     qword ptr [rbx+28h], 0
0x18001a824  mov     qword ptr [rbx+30h], 0
0x18001a82c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001a833  movdqu  xmmword ptr [rbx+38h], xmm0
0x18001a838  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001a83f  movdqu  xmmword ptr [rbx+50h], xmm1
0x18001a844  lea     rcx, [rbx+60h]; this
0x18001a848  call    ?ClearList@CPhotoPropertyItemList@@QEAAXXZ; CPhotoPropertyItemList::ClearList(void)
0x18001a84d  mov     rcx, r14; this
0x18001a850  call    ?ClearList@CPhotoPropertyItemList@@QEAAXXZ; CPhotoPropertyItemList::ClearList(void)
0x18001a855  mov     eax, esi
0x18001a857  add     rsp, 40h
0x18001a85b  pop     r14
0x18001a85d  pop     rsi
0x18001a85e  pop     rbx
0x18001a85f  retn
```
