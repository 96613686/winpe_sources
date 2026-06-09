# CHeap::CreateSharedHandleInternal(_SECURITY_ATTRIBUTES const *,ulong,ushort const *,void * *)

- ea: `0x18005098c`
- end: `0x180050b8b`
- name: `?CreateSharedHandleInternal@CHeap@@QEAAJPEBU_SECURITY_ATTRIBUTES@@KPEBGPEAPEAX@Z`
- size: `511`
- prototype: `__int64 __fastcall(CHeap *__hidden this, const struct _SECURITY_ATTRIBUTES *, unsigned int, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180050820`
- `0x1800f1070`

## callees

- `0x180007df0`
- `0x18000b010`
- `0x18005098c`
- `0x180050b94`
- `0x180050c08`
- `0x1800a09c0`
- `0x1800a44b0`
- `0x1800a8e84`
- `0x1800bb480`
- `0x180145150`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTShareObjects` at `0x180050a84`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateBundleObject` at `0x180234c19`

## string_xrefs

- `0x180050b58`: `Access parameter must be GENERIC_ALL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHeap::CreateSharedHandleInternal(
        CHeap *this,
        const struct _SECURITY_ATTRIBUTES *a2,
        int a3,
        const unsigned __int16 *a4,
        void **a5)
{
  __int64 v9; // rbx
  _DWORD *v10; // rcx
  int v11; // esi
  int v12; // edx
  int v13; // r8d
  __int64 v14; // r14
  __int64 v15; // rbx
  unsigned int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // ebx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // [rsp+40h] [rbp-1A8h] BYREF
  const unsigned __int16 *v24; // [rsp+48h] [rbp-1A0h]
  _DWORD v25[2]; // [rsp+50h] [rbp-198h] BYREF
  int *v26; // [rsp+58h] [rbp-190h]
  __int128 *v27; // [rsp+60h] [rbp-188h]
  _DWORD *v28; // [rsp+68h] [rbp-180h]
  __int64 v29; // [rsp+70h] [rbp-178h]
  int v30; // [rsp+78h] [rbp-170h]
  int v31; // [rsp+7Ch] [rbp-16Ch]
  __int128 v32; // [rsp+80h] [rbp-168h]
  __int128 v33; // [rsp+90h] [rbp-158h]
  _BYTE v34[88]; // [rsp+B0h] [rbp-138h] BYREF
  __int64 v35; // [rsp+108h] [rbp-E0h]
  _BYTE v36[88]; // [rsp+110h] [rbp-D8h] BYREF
  __int64 v37; // [rsp+168h] [rbp-80h]
  int v38; // [rsp+170h] [rbp-78h] BYREF
  __int64 v39; // [rsp+174h] [rbp-74h]
  _DWORD v40[4]; // [rsp+180h] [rbp-68h] BYREF
  __int128 v41; // [rsp+190h] [rbp-58h] BYREF
  __int64 v42; // [rsp+1A0h] [rbp-48h]
  _QWORD v43[8]; // [rsp+1A8h] [rbp-40h] BYREF

  v24 = a4;
  if ( !a5 || (*((_BYTE *)this + 224) & 2) == 0 )
    return 2147942487LL;
  v9 = *(_QWORD *)(*((_QWORD *)this + 32) + 192LL);
  v38 = *(_DWORD *)(*((_QWORD *)this + 29) + 4LL);
  v39 = 0;
  v10 = (_DWORD *)*((_QWORD *)this + 46);
  if ( v10 )
  {
    if ( !v9 )
    {
      LODWORD(v39) = *v10;
      HIDWORD(v39) = v10[18];
LABEL_14:
      v11 = 3;
      goto LABEL_5;
    }
    return 2147942487LL;
  }
  v11 = 1;
  if ( v9 )
  {
    LODWORD(v39) = *(_DWORD *)(v9 + 208);
    HIDWORD(v39) = *(_DWORD *)(*(_QWORD *)(v9 + 200) + 208LL);
    goto LABEL_14;
  }
LABEL_5:
  if ( a3 != 0x10000000 )
  {
    CDevice::ReportRetailValidationErrorF(
      (CDevice *)(*((_QWORD *)this + 19) + 288LL),
      D3D12_MESSAGE_ID_DEVICE_CREATE_SHARED_HANDLE_INVALIDARG,
      "Access parameter must be GENERIC_ALL.");
    ThrowFailure(-2147024809);
  }
  InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>(
    v34,
    a4,
    a2);
  v14 = v35;
  *(_DWORD *)(v35 + 24) &= ~0x80u;
  if ( v9 )
  {
    InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&public: static long NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>(
      v36,
      0,
      a2);
    v41 = 0;
    v42 = 0;
    v23 = v37;
    std::fill<_OBJECT_ATTRIBUTES * *,_OBJECT_ATTRIBUTES *>(&v41, v43, &v23);
    v40[0] = a3;
    v40[1] = a3;
    v40[2] = a3;
    v25[1] = 0;
    v33 = 0;
    v25[0] = v11;
    v26 = &v38;
    v27 = &v41;
    v29 = v14;
    v30 = a3;
    v31 = 1;
    v32 = D3D_NT_HANDLE_BUNDLE_PROTECTED_RESOURCE;
    v28 = v40;
    v22 = CallAndLogImpl<long (*)(_D3DKMT_CREATEBUNDLEOBJECT *),_D3DKMT_CREATEBUNDLEOBJECT *>(
            D3DKMTCreateBundleObject,
            v21,
            CLayeredObject<CCommandAllocator>::AddRef,
            v25);
    v19 = NDXGI::CDevice::NTStatusToHResult(*(_QWORD *)(*((_QWORD *)this + 19) + 760LL), v22, 0);
    if ( v19 == -2147024890 )
      v19 = -2005270484;
    ThrowFailure(v19);
    *a5 = (void *)*((_QWORD *)&v33 + 1);
  }
  else
  {
    v15 = *(_QWORD *)(*((_QWORD *)this + 19) + 760LL);
    v16 = CallAndLogImpl<long (*)(unsigned int,unsigned int const *,_OBJECT_ATTRIBUTES *,unsigned long,void * *),unsigned int,unsigned int const *,_OBJECT_ATTRIBUTES *,unsigned long,void * *>(
            D3DKMTShareObjects,
            v12,
            v13,
            v11,
            (__int64)&v38,
            v14,
            a3,
            (__int64)a5);
    v19 = NDXGI::CDevice::NTStatusToHResult(v15, v16, 1);
    if ( v19 == -2147024890 )
      v19 = -2005270484;
  }
  if ( v19 >= 0 && (byte_180333481 & 1) != 0 )
    McTemplateU0qpz_EtwEventWriteTransfer(
      v18,
      v17,
      *(_DWORD *)(*((_QWORD *)this + 29) + 4LL),
      (unsigned int)*a5,
      (__int64)v24);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18005098c  mov     r11, rsp
0x18005098f  push    rbx
0x180050990  push    rsi
0x180050991  push    rdi
0x180050992  push    r12
0x180050994  push    r13
0x180050996  push    r14
0x180050998  push    r15
0x18005099a  sub     rsp, 1B0h
0x1800509a1  mov     rax, cs:__security_cookie
0x1800509a8  xor     rax, rsp
0x1800509ab  mov     [rsp+1E8h+var_40], rax
0x1800509b3  mov     r14, r9
0x1800509b6  mov     [rsp+1E8h+var_1A0], r9
0x1800509bb  mov     r12d, r8d
0x1800509be  mov     r13, rdx
0x1800509c1  mov     rdi, rcx
0x1800509c4  mov     r15, [rsp+1E8h+arg_20]
0x1800509cc  test    r15, r15
0x1800509cf  jz      loc_180050B81
0x1800509d5  test    byte ptr [rcx+0E0h], 2
0x1800509dc  jz      loc_180050B81
0x1800509e2  mov     rax, [rcx+100h]
0x1800509e9  mov     rbx, [rax+0C0h]
0x1800509f0  mov     rax, [rcx+0E8h]
0x1800509f7  mov     ecx, [rax+4]
0x1800509fa  mov     [r11-78h], ecx
0x1800509fe  xor     eax, eax
0x180050a00  mov     [r11-74h], rax
0x180050a04  mov     rcx, [rdi+170h]
0x180050a0b  test    rcx, rcx
0x180050a0e  jnz     loc_180050AD9
0x180050a14  lea     esi, [rax+1]
0x180050a17  test    rbx, rbx
0x180050a1a  jnz     loc_180050B27
0x180050a20  cmp     r12d, 10000000h
0x180050a27  jnz     loc_180050B4A
0x180050a2d  mov     r8, r13
0x180050a30  mov     rdx, r14
0x180050a33  lea     rcx, [rsp+1E8h+var_138]
0x180050a3b  call    ??0?$InitObjectAttributesHelper@$1?NTStatusToHResult_TranslateToAPIError@CUMDAdapter@NDXGI@@SAJJ@Z@@QEAA@PEBGPEBU_SECURITY_ATTRIBUTES@@@Z; InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>(ushort const *,_SECURITY_ATTRIBUTES const *)
0x180050a40  mov     r14, [rsp+1E8h+var_E0]
0x180050a48  btr     dword ptr [r14+18h], 7
0x180050a4e  test    rbx, rbx
0x180050a51  jnz     loc_180234B46
0x180050a57  mov     rax, [rdi+98h]
0x180050a5e  mov     rbx, [rax+2F8h]
0x180050a65  mov     [rsp+1E8h+var_1B0], r15
0x180050a6a  mov     [rsp+1E8h+var_1B8], r12d
0x180050a6f  mov     [rsp+1E8h+var_1C0], r14
0x180050a74  lea     rax, [rsp+1E8h+var_78]
0x180050a7c  mov     [rsp+1E8h+var_1C8], rax
0x180050a81  mov     r9d, esi
0x180050a84  mov     rcx, cs:__imp_D3DKMTShareObjects
0x180050a8b  call    ??$CallAndLogImpl@P6AJIPEBIPEAU_OBJECT_ATTRIBUTES@@KPEAPEAX@ZIPEBIPEAU1@KPEAPEAX@@YAJP6AJIPEBIPEAU_OBJECT_ATTRIBUTES@@KPEAPEAX@ZPEBDP6A?AW4RecordStatusFilterResult@@J@ZI01K2@Z; CallAndLogImpl<long (*)(uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *),uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *>(long (*)(uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *),char const *,RecordStatusFilterResult (*)(long),uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *)
0x180050a90  mov     r8d, 1
0x180050a96  mov     edx, eax
0x180050a98  mov     rcx, rbx
0x180050a9b  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180050aa0  mov     ebx, eax
0x180050aa2  mov     eax, 887A002Ch
0x180050aa7  cmp     ebx, 80070006h
0x180050aad  cmovz   ebx, eax
0x180050ab0  test    ebx, ebx
0x180050ab2  jns     short loc_180050AFF
0x180050ab4  mov     eax, ebx
0x180050ab6  mov     rcx, [rsp+1E8h+var_40]
0x180050abe  xor     rcx, rsp; StackCookie
0x180050ac1  call    __security_check_cookie
0x180050ac6  add     rsp, 1B0h
0x180050acd  pop     r15
0x180050acf  pop     r14
0x180050ad1  pop     r13
0x180050ad3  pop     r12
0x180050ad5  pop     rdi
0x180050ad6  pop     rsi
0x180050ad7  pop     rbx
0x180050ad8  retn
0x180050ad9  test    rbx, rbx
0x180050adc  jnz     loc_180050B81
0x180050ae2  mov     eax, [rcx]
0x180050ae4  mov     [rsp+1E8h+var_74], eax
0x180050aeb  mov     eax, [rcx+48h]
0x180050aee  mov     [rsp+1E8h+var_70], eax
0x180050af5  mov     esi, 3
0x180050afa  jmp     loc_180050A20
0x180050aff  test    cs:byte_180333481, 1
0x180050b06  jz      short loc_180050AB4
0x180050b08  mov     r8, [rdi+0E8h]
0x180050b0f  mov     rax, [rsp+1E8h+var_1A0]
0x180050b14  mov     [rsp+1E8h+var_1C8], rax
0x180050b19  mov     r9, [r15]
0x180050b1c  mov     r8d, [r8+4]
0x180050b20  call    McTemplateU0qpz_EtwEventWriteTransfer
0x180050b25  jmp     short loc_180050AB4
0x180050b27  mov     eax, [rbx+0D0h]
0x180050b2d  mov     [rsp+1E8h+var_74], eax
0x180050b34  mov     rax, [rbx+0C8h]
0x180050b3b  mov     ecx, [rax+0D0h]
0x180050b41  mov     [rsp+1E8h+var_70], ecx
0x180050b48  jmp     short loc_180050AF5
0x180050b4a  mov     rcx, [rdi+98h]
0x180050b51  add     rcx, 120h; this
0x180050b58  lea     r8, aAccessParamete; "Access parameter must be GENERIC_ALL."
0x180050b5f  mov     edx, 411h; enum D3D12_MESSAGE_ID
0x180050b64  call    ?ReportRetailValidationErrorF@CDevice@@UEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; CDevice::ReportRetailValidationErrorF(D3D12_MESSAGE_ID,char const *,...)
0x180050b69  mov     ecx, 80070057h; int
0x180050b6e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180050b73  jmp     loc_180050A2D
0x180050b78  mov     eax, dword ptr [rsp+1E8h+var_1A8]
0x180050b7c  jmp     loc_180050AB6
0x180050b81  mov     eax, 80070057h
0x180050b86  jmp     loc_180050AB6
0x180234b46  mov     r8, r13
0x180234b49  xor     edx, edx
0x180234b4b  lea     rcx, [rsp+1E8h+var_D8]
0x180234b53  call    ??0?$InitObjectAttributesHelper@$1?NTStatusToHResult_TranslateToAPIError@CUMDAdapter@NDXGI@@SAJJ@Z@@QEAA@PEBGPEBU_SECURITY_ATTRIBUTES@@@Z; InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>::InitObjectAttributesHelper<&NDXGI::CUMDAdapter::NTStatusToHResult_TranslateToAPIError(long)>(ushort const *,_SECURITY_ATTRIBUTES const *)
0x180234b58  xorps   xmm0, xmm0
0x180234b5b  xor     eax, eax
0x180234b5d  movups  [rsp+1E8h+var_58], xmm0
0x180234b65  mov     [rsp+1E8h+var_48], rax
0x180234b6d  mov     rax, [rsp+1E8h+var_80]
0x180234b75  mov     [rsp+1E8h+var_1A8], rax
0x180234b7a  lea     r8, [rsp+1E8h+var_1A8]
0x180234b7f  lea     rdx, [rsp+1E8h+var_40]
0x180234b87  lea     rcx, [rsp+1E8h+var_58]
0x180234b8f  call    ??$fill@PEAPEAU_OBJECT_ATTRIBUTES@@PEAU1@@std@@YAXQEAPEAU_OBJECT_ATTRIBUTES@@0AEBQEAU1@@Z; std::fill<_OBJECT_ATTRIBUTES * *,_OBJECT_ATTRIBUTES *>(_OBJECT_ATTRIBUTES * * const,_OBJECT_ATTRIBUTES * * const,_OBJECT_ATTRIBUTES * const &)
0x180234b94  mov     [rsp+1E8h+var_68], r12d
0x180234b9c  mov     [rsp+1E8h+var_64], r12d
0x180234ba4  mov     [rsp+1E8h+var_60], r12d
0x180234bac  mov     [rsp+1E8h+var_194], 0
0x180234bb4  xorps   xmm0, xmm0
0x180234bb7  movdqa  [rsp+1E8h+var_158], xmm0
0x180234bc0  mov     [rsp+1E8h+var_198], esi
0x180234bc4  lea     rax, [rsp+1E8h+var_78]
0x180234bcc  mov     [rsp+1E8h+var_190], rax
0x180234bd1  lea     rax, [rsp+1E8h+var_58]
0x180234bd9  mov     [rsp+1E8h+var_188], rax
0x180234bde  mov     [rsp+1E8h+var_178], r14
0x180234be3  mov     [rsp+1E8h+var_170], r12d
0x180234be8  mov     [rsp+1E8h+var_16C], 1
0x180234bf0  movups  xmm0, cs:D3D_NT_HANDLE_BUNDLE_PROTECTED_RESOURCE
0x180234bf7  movdqu  [rsp+1E8h+var_168], xmm0
0x180234c00  lea     rax, [rsp+1E8h+var_68]
0x180234c08  mov     [rsp+1E8h+var_180], rax
0x180234c0d  lea     r9, [rsp+1E8h+var_198]
0x180234c12  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x180234c19  mov     rcx, cs:__imp_D3DKMTCreateBundleObject
0x180234c20  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATEBUNDLEOBJECT@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATEBUNDLEOBJECT@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATEBUNDLEOBJECT *),_D3DKMT_CREATEBUNDLEOBJECT *>(long (*)(_D3DKMT_CREATEBUNDLEOBJECT *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_CREATEBUNDLEOBJECT *)
0x180234c25  mov     rcx, [rdi+98h]
0x180234c2c  xor     r8d, r8d
0x180234c2f  mov     edx, eax
0x180234c31  mov     rcx, [rcx+2F8h]
0x180234c38  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180234c3d  mov     ebx, eax
0x180234c3f  mov     eax, 887A002Ch
0x180234c44  cmp     ebx, 80070006h
0x180234c4a  cmovz   ebx, eax
0x180234c4d  mov     ecx, ebx; int
0x180234c4f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180234c54  mov     rax, qword ptr [rsp+1E8h+var_158+8]
0x180234c5c  mov     [r15], rax
0x180234c5f  jmp     loc_180050AB0
```
