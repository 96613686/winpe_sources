# GetEmf(IStream *,int,uint)

- ea: `0x1800ed770`
- end: `0x1800ed85f`
- name: `?GetEmf@@YAPEAUHENHMETAFILE__@@PEAUIStream@@HI@Z`
- size: `239`
- prototype: `HENHMETAFILE __fastcall(struct IStream *, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009ba10`
- `0x18011ad50`

## callees

- `0x1800ed770`
- `0x1800f14b0`
- `0x18011c9c0`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ed7d1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ed7d1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800ed7a9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800ed7a9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ed849`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800ed849`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ed801`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800ed801`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ed82a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800ed82a`
- `GDI32!SetMetaFileBitsEx` at `0x1800ed816`
- `GDI32!SetMetaFileBitsEx` at `0x1800ed816`
- `GDI32!SetEnhMetaFileBits` at `0x1800ed81e`
- `GDI32!SetEnhMetaFileBits` at `0x1800ed81e`

## pseudocode

```c
HENHMETAFILE __fastcall GetEmf(struct IStream *a1, int a2, unsigned int a3)
{
  SIZE_T v3; // rdi
  void *v7; // rsi
  HGLOBAL v8; // rax
  void *v9; // rbx
  const BYTE *v10; // rax
  void *v11; // rax
  __int64 v12[9]; // [rsp+20h] [rbp-48h] BYREF
  LPSTREAM ppstm; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::GetImpl'::`2'::impl)
    && !(_DWORD)v3 )
  {
    return 0;
  }
  v7 = 0;
  v8 = GlobalAlloc(0x22u, v3);
  v9 = v8;
  if ( v8 )
  {
    ppstm = 0;
    if ( CreateStreamOnHGlobal(v8, 1, &ppstm) >= 0 && ppstm )
    {
      v12[0] = v3;
      if ( (unsigned int)CopyStream(a1, ppstm, v12) )
      {
        v10 = (const BYTE *)GlobalLock(v9);
        if ( v10 )
        {
          if ( a2 )
            v11 = SetMetaFileBitsEx(v3, v10);
          else
            v11 = SetEnhMetaFileBits(v3, v10);
          v7 = v11;
        }
        GlobalUnlock(v9);
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
    else
    {
      GlobalFree(v9);
    }
  }
  return (HENHMETAFILE)v7;
}

```

## disassembly

```asm
0x1800ed770  push    rbx
0x1800ed772  push    rbp
0x1800ed773  push    rsi
0x1800ed774  push    rdi
0x1800ed775  push    r14
0x1800ed777  push    r15
0x1800ed779  sub     rsp, 38h
0x1800ed77d  mov     edi, r8d
0x1800ed780  mov     r14d, edx
0x1800ed783  mov     r15, rcx
0x1800ed786  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::GetImpl(void)'::`2'::impl
0x1800ed78d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HandleZeroSizedEmf>::__private_IsEnabled(void)
0x1800ed792  test    al, al
0x1800ed794  jz      short loc_1800ED7A1
0x1800ed796  test    edi, edi
0x1800ed798  jnz     short loc_1800ED7A1
0x1800ed79a  xor     eax, eax
0x1800ed79c  jmp     loc_1800ED852
0x1800ed7a1  xor     esi, esi
0x1800ed7a3  mov     rdx, rdi; dwBytes
0x1800ed7a6  lea     ecx, [rsi+22h]; uFlags
0x1800ed7a9  call    cs:__imp_GlobalAlloc
0x1800ed7af  mov     rbx, rax
0x1800ed7b2  test    rax, rax
0x1800ed7b5  jz      loc_1800ED84F
0x1800ed7bb  lea     r8, [rsp+68h+ppstm]; ppstm
0x1800ed7c3  mov     [rsp+68h+ppstm], rsi
0x1800ed7cb  lea     edx, [rsi+1]; fDeleteOnRelease
0x1800ed7ce  mov     rcx, rax; hGlobal
0x1800ed7d1  call    cs:__imp_CreateStreamOnHGlobal
0x1800ed7d7  test    eax, eax
0x1800ed7d9  js      short loc_1800ED846
0x1800ed7db  mov     rdx, [rsp+68h+ppstm]; struct IStream *
0x1800ed7e3  test    rdx, rdx
0x1800ed7e6  jz      short loc_1800ED846
0x1800ed7e8  lea     r8, [rsp+68h+var_48]; __int64 *
0x1800ed7ed  mov     [rsp+68h+var_48], rdi
0x1800ed7f2  mov     rcx, r15; struct IStream *
0x1800ed7f5  call    ?CopyStream@@YAHPEAUIStream@@0AEB_J@Z; CopyStream(IStream *,IStream *,__int64 const &)
0x1800ed7fa  test    eax, eax
0x1800ed7fc  jz      short loc_1800ED830
0x1800ed7fe  mov     rcx, rbx; hMem
0x1800ed801  call    cs:__imp_GlobalLock
0x1800ed807  test    rax, rax
0x1800ed80a  jz      short loc_1800ED827
0x1800ed80c  mov     rdx, rax; pb
0x1800ed80f  mov     ecx, edi; nSize
0x1800ed811  test    r14d, r14d
0x1800ed814  jz      short loc_1800ED81E
0x1800ed816  call    cs:__imp_SetMetaFileBitsEx
0x1800ed81c  jmp     short loc_1800ED824
0x1800ed81e  call    cs:__imp_SetEnhMetaFileBits
0x1800ed824  mov     rsi, rax
0x1800ed827  mov     rcx, rbx; hMem
0x1800ed82a  call    cs:__imp_GlobalUnlock
0x1800ed830  mov     rcx, [rsp+68h+ppstm]
0x1800ed838  mov     rax, [rcx]
0x1800ed83b  mov     rax, [rax+10h]
0x1800ed83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed844  jmp     short loc_1800ED84F
0x1800ed846  mov     rcx, rbx; hMem
0x1800ed849  call    cs:__imp_GlobalFree
0x1800ed84f  mov     rax, rsi
0x1800ed852  add     rsp, 38h
0x1800ed856  pop     r15
0x1800ed858  pop     r14
0x1800ed85a  pop     rdi
0x1800ed85b  pop     rsi
0x1800ed85c  pop     rbp
0x1800ed85d  pop     rbx
0x1800ed85e  retn
```
