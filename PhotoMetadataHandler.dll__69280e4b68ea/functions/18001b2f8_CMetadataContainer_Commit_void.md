# CMetadataContainer::Commit(void)

- ea: `0x18001b2f8`
- end: `0x18001b501`
- name: `?Commit@CMetadataContainer@@QEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(CMetadataContainer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001d310`

## callees

- `0x180002420`
- `0x1800044e0`
- `0x180004fc0`
- `0x1800053bc`
- `0x180005440`
- `0x180008b54`
- `0x18000d470`
- `0x18001b2f8`
- `0x18001c518`
- `0x18001d094`
- `0x180029010`

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
0x18001b2f8  mov     [rsp+arg_0], rcx
0x18001b2fd  push    rbx
0x18001b2fe  push    rsi
0x18001b2ff  push    r14
0x18001b301  sub     rsp, 40h
0x18001b305  mov     rbx, rcx
0x18001b308  call    ?ReadInMetadata@CMetadataContainer@@QEAAJXZ; CMetadataContainer::ReadInMetadata(void)
0x18001b30d  mov     esi, eax
0x18001b30f  test    eax, eax
0x18001b311  js      loc_18001B4F7
0x18001b317  lea     r14, [rbx+78h]
0x18001b31b  mov     [rsp+58h+var_30], r14
0x18001b320  cmp     dword ptr [rbx+70h], 0
0x18001b324  ja      short loc_18001B336
0x18001b326  mov     rcx, r14; this
0x18001b329  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001b32e  test    eax, eax
0x18001b330  jz      loc_18001B48F
0x18001b336  mov     [rsp+58h+arg_10], 0
0x18001b33f  mov     rcx, [rbx+8]
0x18001b343  mov     rax, [rcx]
0x18001b346  lea     r8, [rsp+58h+arg_10]
0x18001b34b  xor     edx, edx
0x18001b34d  mov     rax, [rax+68h]
0x18001b351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b356  mov     esi, eax
0x18001b358  test    eax, eax
0x18001b35a  js      loc_18001B485
0x18001b360  mov     [rsp+58h+arg_18], 0
0x18001b369  mov     rcx, [rbx+10h]
0x18001b36d  mov     rax, [rcx]
0x18001b370  lea     r8, [rsp+58h+arg_18]
0x18001b375  mov     rdx, [rsp+58h+arg_10]
0x18001b37a  mov     rax, [rax+0C8h]
0x18001b381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b386  mov     esi, eax
0x18001b388  test    eax, eax
0x18001b38a  js      loc_18001B47A
0x18001b390  mov     [rsp+58h+var_38], 0
0x18001b399  mov     rcx, [rsp+58h+arg_18]
0x18001b39e  mov     rax, [rcx]
0x18001b3a1  lea     rdx, [rsp+58h+var_38]
0x18001b3a6  mov     rax, [rax+20h]
0x18001b3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3af  mov     esi, eax
0x18001b3b1  test    eax, eax
0x18001b3b3  js      loc_18001B46F
0x18001b3b9  mov     rdx, [rsp+58h+var_38]; struct IWICMetadataQueryWriter *
0x18001b3be  mov     rcx, rbx; this
0x18001b3c1  call    ?_WriteOutDirtyItems@CMetadataContainer@@AEAAJPEAUIWICMetadataQueryWriter@@@Z; CMetadataContainer::_WriteOutDirtyItems(IWICMetadataQueryWriter *)
0x18001b3c6  mov     esi, eax
0x18001b3c8  test    eax, eax
0x18001b3ca  js      loc_18001B46F
0x18001b3d0  mov     r10d, 80004005h
0x18001b3d6  mov     rcx, r14; this
0x18001b3d9  call    ?GetCount@CPhotoPropertyItemList@@QEAAIXZ; CPhotoPropertyItemList::GetCount(void)
0x18001b3de  test    eax, eax
0x18001b3e0  jnz     short loc_18001B444
0x18001b3e2  lea     rcx, [rbx+50h]; struct _GUID *
0x18001b3e6  call    ?LookupContainerMask@CContainerMasks@@SAKAEBU_GUID@@@Z; CContainerMasks::LookupContainerMask(_GUID const &)
0x18001b3eb  cmp     eax, 1
0x18001b3ee  jz      short loc_18001B3FF
0x18001b3f0  cmp     eax, 2
0x18001b3f3  jnz     short loc_18001B402
0x18001b3f5  cmp     qword ptr [rbx+48h], 1E00000h
0x18001b3fd  ja      short loc_18001B402
0x18001b3ff  xor     r10d, r10d
0x18001b402  jmp     short loc_18001B413
0x18001b404  mov     rbx, [rsp+58h+arg_0]
0x18001b409  mov     r10d, [rsp+58h+arg_8]
0x18001b40e  mov     r14, [rsp+58h+var_30]
0x18001b413  test    r10d, r10d
0x18001b416  js      short loc_18001B444
0x18001b418  mov     rcx, [rsp+58h+arg_18]
0x18001b41d  mov     rax, [rcx]
0x18001b420  mov     rax, [rax+18h]
0x18001b424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b429  test    eax, eax
0x18001b42b  js      short loc_18001B444
0x18001b42d  mov     rcx, [rbx]
0x18001b430  mov     rax, [rcx]
0x18001b433  xor     edx, edx
0x18001b435  mov     rax, [rax+40h]
0x18001b439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b43e  mov     esi, eax
0x18001b440  test    eax, eax
0x18001b442  jns     short loc_18001B46F
0x18001b444  mov     r8b, 1; bool
0x18001b447  mov     rdx, [rsp+58h+arg_10]; struct IWICBitmapFrameDecode *
0x18001b44c  mov     rcx, rbx; this
0x18001b44f  call    ?_EncodeFullImage@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameDecode@@_N@Z; CMetadataContainer::_EncodeFullImage(IWICBitmapFrameDecode *,bool)
0x18001b454  mov     esi, eax
0x18001b456  cmp     eax, 88982F52h
0x18001b45b  jnz     short loc_18001B46F
0x18001b45d  xor     r8d, r8d; bool
0x18001b460  mov     rdx, [rsp+58h+arg_10]; struct IWICBitmapFrameDecode *
0x18001b465  mov     rcx, rbx; this
0x18001b468  call    ?_EncodeFullImage@CMetadataContainer@@AEAAJPEAUIWICBitmapFrameDecode@@_N@Z; CMetadataContainer::_EncodeFullImage(IWICBitmapFrameDecode *,bool)
0x18001b46d  mov     esi, eax
0x18001b46f  lea     rcx, [rsp+58h+var_38]
0x18001b474  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001b479  nop
0x18001b47a  lea     rcx, [rsp+58h+arg_18]
0x18001b47f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001b484  nop
0x18001b485  lea     rcx, [rsp+58h+arg_10]
0x18001b48a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001b48f  lea     rcx, [rbx+10h]
0x18001b493  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001b498  lea     rcx, [rbx+8]
0x18001b49c  call    ?Release@?$CComPtrBase@UIWICComponentFactory@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICComponentFactory>::Release(void)
0x18001b4a1  mov     rcx, rbx
0x18001b4a4  call    ?Release@?$CComPtrBase@UIStream@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IStream>::Release(void)
0x18001b4a9  mov     dword ptr [rbx+18h], 0
0x18001b4b0  mov     byte ptr [rbx+1Ch], 0
0x18001b4b4  mov     qword ptr [rbx+20h], 0
0x18001b4bc  mov     qword ptr [rbx+28h], 0
0x18001b4c4  mov     qword ptr [rbx+30h], 0
0x18001b4cc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001b4d3  movdqu  xmmword ptr [rbx+38h], xmm0
0x18001b4d8  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001b4df  movdqu  xmmword ptr [rbx+50h], xmm1
0x18001b4e4  lea     rcx, [rbx+60h]; this
0x18001b4e8  call    ?ClearList@CPhotoPropertyItemList@@QEAAXXZ; CPhotoPropertyItemList::ClearList(void)
0x18001b4ed  mov     rcx, r14; this
0x18001b4f0  call    ?ClearList@CPhotoPropertyItemList@@QEAAXXZ; CPhotoPropertyItemList::ClearList(void)
0x18001b4f5  mov     eax, esi
0x18001b4f7  add     rsp, 40h
0x18001b4fb  pop     r14
0x18001b4fd  pop     rsi
0x18001b4fe  pop     rbx
0x18001b4ff  retn
```
