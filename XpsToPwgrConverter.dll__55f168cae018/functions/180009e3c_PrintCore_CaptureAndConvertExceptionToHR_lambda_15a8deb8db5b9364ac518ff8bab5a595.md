# PrintCore::CaptureAndConvertExceptionToHR__lambda_15a8deb8db5b9364ac518ff8bab5a595___

- ea: `0x180009e3c`
- end: `0x18000a03d`
- name: `PrintCore::CaptureAndConvertExceptionToHR__lambda_15a8deb8db5b9364ac518ff8bab5a595___`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a420`

## callees

- `0x18000200c`
- `0x1800021a0`
- `0x180009e3c`
- `0x18000a0ac`
- `0x18000a130`
- `0x18000c514`
- `0x18000cddc`
- `0x180011010`

## string_xrefs

- `0x18000a010`: `onecoreuap\printscan\print\drivers\renderlibrary\pwgraster\pwgrcore\pwgrstreamwriter.cpp`
- `0x18000a017`: `Failed to write bytes to output stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PrintCore::CaptureAndConvertExceptionToHR__lambda_15a8deb8db5b9364ac518ff8bab5a595___(__int64 a1)
{
  __int64 v2; // rsi
  _OWORD *v3; // r14
  char *v4; // rbx
  __int128 v5; // xmm1
  __int128 v6; // xmm2
  __int128 v7; // xmm3
  __int128 v8; // xmm4
  __int128 v9; // xmm5
  __int128 v10; // xmm6
  __int64 v11; // xmm7_8
  int v12; // eax
  PWGRCore::CPWGRBitmapEncoder *v13; // rsi
  __int64 v14; // rdi
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rdx
  void (__fastcall *v19)(_QWORD, __int64, __int64, __int64); // rax
  PrintCore::WindowsError *v20[3]; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+48h] [rbp-90h] BYREF
  __int64 v22; // [rsp+58h] [rbp-80h]
  _BYTE pExceptionObject[96]; // [rsp+60h] [rbp-78h] BYREF
  unsigned int v24; // [rsp+E0h] [rbp+8h]
  int v25; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v26; // [rsp+F0h] [rbp+18h]

  v24 = 0;
  v2 = *(_QWORD *)(a1 + 8);
  v3 = *(_OWORD **)a1;
  try
  {
    v4 = (char *)operator new(0x88u);
    *((_DWORD *)v4 + 2) = 1;
    *((_DWORD *)v4 + 3) = 1;
    *(_QWORD *)v4 = &std::_Ref_count_obj2<PWGRCore::CPWGRVendorDataHandler>::`vftable';
    v5 = v3[1];
    v6 = v3[2];
    v7 = v3[3];
    v8 = v3[4];
    v9 = v3[5];
    v10 = *(_OWORD *)(v2 + 28);
    v11 = *(_QWORD *)(v2 + 44);
    *((_OWORD *)v4 + 1) = *v3;
    *((_OWORD *)v4 + 2) = v5;
    *((_OWORD *)v4 + 3) = v6;
    *((_OWORD *)v4 + 4) = v7;
    *((_OWORD *)v4 + 5) = v8;
    *((_OWORD *)v4 + 6) = v9;
    *((_OWORD *)v4 + 7) = v10;
    *((_QWORD *)v4 + 16) = v11;
    v20[1] = (PrintCore::WindowsError *)(v4 + 16);
    v20[2] = (PrintCore::WindowsError *)v4;
    v21 = 0;
    v22 = 0;
    PWGRCore::CPWGRPageHeader::GetBitmapHeader(v4 + 16, &v21);
    v25 = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(**(_QWORD **)(*(_QWORD *)(a1 + 8) + 16LL) + 32LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL),
            v21,
            (unsigned int)(DWORD2(v21) - v21),
            &v25);
    if ( v12 < 0 )
    {
      PrintCore::WindowsError::WindowsError(
        (PrintCore::WindowsError *)pExceptionObject,
        v12,
        "Failed to write bytes to output stream",
        "onecoreuap\\printscan\\print\\drivers\\renderlibrary\\pwgraster\\pwgrcore\\pwgrstreamwriter.cpp",
        0x45u);
      throw (PrintCore::WindowsError *)pExceptionObject;
    }
    v13 = *(PWGRCore::CPWGRBitmapEncoder **)(*(_QWORD *)(a1 + 8) + 56LL);
    v14 = **(_QWORD **)(a1 + 16);
    v26 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
    PWGRCore::CPWGRBitmapEncoder::EncodeBitmapToStream(v13);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    std::vector<unsigned char>::~vector<unsigned char>(&v21);
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v4)(v4);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( std::out_of_range )
  {
    return (unsigned int)-2147023728;
  }
  catch ( std::invalid_argument )
  {
    return (unsigned int)-2147024809;
  }
  catch ( std::range_error )
  {
    return (unsigned int)-2147483637;
  }
  catch ( PrintCore::WindowsError *v20 )
  {
    v24 = *((_DWORD *)v20[0] + 6);
    v16 = *((unsigned int *)v20[0] + 12);
    v17 = *((_QWORD *)v20[0] + 5);
    v18 = *((_QWORD *)v20[0] + 4);
    v19 = (void (__fastcall *)(_QWORD, __int64, __int64, __int64))_InterlockedCompareExchange64(
                                                                    (volatile signed __int64 *)&PrintCore::WindowsErrorLogger::s_pCallback,
                                                                    0,
                                                                    0);
    if ( v19 )
      v19(v24, v18, v17, v16);
    return v24;
  }
  catch ( ... )
  {
    return (unsigned int)-2147418113;
  }
  return v24;
}

```

## disassembly

```asm
0x180009e3c  mov     rax, rsp
0x180009e3f  mov     [rax+20h], rbx
0x180009e43  push    rsi
0x180009e44  push    rdi
0x180009e45  push    r14
0x180009e47  sub     rsp, 0C0h
0x180009e4e  movaps  xmmword ptr [rax-28h], xmm6
0x180009e52  movaps  xmmword ptr [rax-38h], xmm7
0x180009e56  mov     rdi, rcx
0x180009e59  mov     [rsp+0D8h+arg_0], 0
0x180009e64  mov     rsi, [rcx+8]
0x180009e68  mov     r14, [rcx]
0x180009e6b  mov     ecx, 88h; Size
0x180009e70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e75  mov     rbx, rax
0x180009e78  mov     eax, 1
0x180009e7d  mov     [rbx+8], eax
0x180009e80  mov     [rbx+0Ch], eax
0x180009e83  lea     rax, ??_7?$_Ref_count_obj2@VCPWGRVendorDataHandler@PWGRCore@@@std@@6B@; const std::_Ref_count_obj2<PWGRCore::CPWGRVendorDataHandler>::`vftable'
0x180009e8a  mov     [rbx], rax
0x180009e8d  lea     rcx, [rbx+10h]
0x180009e91  movups  xmm0, xmmword ptr [r14]
0x180009e95  movups  xmm1, xmmword ptr [r14+10h]
0x180009e9a  movups  xmm2, xmmword ptr [r14+20h]
0x180009e9f  movups  xmm3, xmmword ptr [r14+30h]
0x180009ea4  movups  xmm4, xmmword ptr [r14+40h]
0x180009ea9  movups  xmm5, xmmword ptr [r14+50h]
0x180009eae  movups  xmm6, xmmword ptr [rsi+1Ch]
0x180009eb2  movsd   xmm7, qword ptr [rsi+2Ch]
0x180009eb7  movups  xmmword ptr [rcx], xmm0
0x180009eba  movups  xmmword ptr [rcx+10h], xmm1
0x180009ebe  movups  xmmword ptr [rcx+20h], xmm2
0x180009ec2  movups  xmmword ptr [rcx+30h], xmm3
0x180009ec6  movups  xmmword ptr [rcx+40h], xmm4
0x180009eca  movups  xmmword ptr [rcx+50h], xmm5
0x180009ece  movups  xmmword ptr [rcx+60h], xmm6
0x180009ed2  movsd   qword ptr [rcx+70h], xmm7
0x180009ed7  mov     [rsp+0D8h+var_A0], rcx
0x180009edc  mov     [rsp+0D8h+var_98], rbx
0x180009ee1  xorps   xmm0, xmm0
0x180009ee4  movdqu  [rsp+0D8h+var_90], xmm0
0x180009eea  mov     [rsp+0D8h+var_80], 0
0x180009ef3  lea     rdx, [rsp+0D8h+var_90]
0x180009ef8  call    ?GetBitmapHeader@CPWGRPageHeader@PWGRCore@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; PWGRCore::CPWGRPageHeader::GetBitmapHeader(std::vector<uchar> &)
0x180009efd  mov     [rsp+0D8h+arg_8], 0
0x180009f08  mov     rax, [rdi+8]
0x180009f0c  mov     rcx, [rax+10h]
0x180009f10  mov     rdx, qword ptr [rsp+0D8h+var_90]
0x180009f15  mov     rax, [rcx]
0x180009f18  mov     r8d, dword ptr [rsp+0D8h+var_90+8]
0x180009f1d  sub     r8d, edx
0x180009f20  lea     r9, [rsp+0D8h+arg_8]
0x180009f28  mov     rax, [rax+20h]
0x180009f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f31  test    eax, eax
0x180009f33  js      loc_18000A008
0x180009f39  mov     rax, [rdi+8]
0x180009f3d  mov     rsi, [rax+38h]
0x180009f41  lea     r14, [rax+10h]
0x180009f45  mov     rax, [rdi+10h]
0x180009f49  mov     rdi, [rax]
0x180009f4c  mov     [rsp+0D8h+arg_10], rdi
0x180009f54  test    rdi, rdi
0x180009f57  jz      short loc_180009F69
0x180009f59  mov     rax, [rdi]
0x180009f5c  mov     rcx, rdi
0x180009f5f  mov     rax, [rax+8]
0x180009f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f68  nop
0x180009f69  mov     r8, r14
0x180009f6c  lea     rdx, [rsp+0D8h+arg_10]
0x180009f74  mov     rcx, rsi; this
0x180009f77  call    ?EncodeBitmapToStream@CPWGRBitmapEncoder@PWGRCore@@QEAAXAEBV?$ComPtr@UIPageBitmapProvider@@@WRL@Microsoft@@AEBV?$ComPtr@UIStream@@@45@@Z; PWGRCore::CPWGRBitmapEncoder::EncodeBitmapToStream(Microsoft::WRL::ComPtr<IPageBitmapProvider> const &,Microsoft::WRL::ComPtr<IStream> const &)
0x180009f7c  nop
0x180009f7d  test    rdi, rdi
0x180009f80  jz      short loc_180009F92
0x180009f82  mov     rax, [rdi]
0x180009f85  mov     rcx, rdi
0x180009f88  mov     rax, [rax+10h]
0x180009f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f91  nop
0x180009f92  lea     rcx, [rsp+0D8h+var_90]
0x180009f97  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180009f9c  nop
0x180009f9d  test    rbx, rbx
0x180009fa0  jz      short loc_180009FD9
0x180009fa2  or      edi, 0FFFFFFFFh
0x180009fa5  mov     eax, edi
0x180009fa7  lock xadd [rbx+8], eax
0x180009fac  add     eax, edi
0x180009fae  jnz     short loc_180009FD9
0x180009fb0  mov     rax, [rbx]
0x180009fb3  mov     rcx, rbx
0x180009fb6  mov     rax, [rax]
0x180009fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fbe  mov     eax, edi
0x180009fc0  lock xadd [rbx+0Ch], eax
0x180009fc5  add     eax, edi
0x180009fc7  jnz     short loc_180009FD9
0x180009fc9  mov     rax, [rbx]
0x180009fcc  mov     rcx, rbx
0x180009fcf  mov     rax, [rax+8]
0x180009fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd8  nop
0x180009fd9  mov     eax, [rsp+0D8h+arg_0]
0x180009fe0  lea     r11, [rsp+0D8h+var_18]
0x180009fe8  mov     rbx, [r11+38h]
0x180009fec  movaps  xmm6, xmmword ptr [r11-10h]
0x180009ff1  movaps  xmm7, xmmword ptr [r11-20h]
0x180009ff6  mov     rsp, r11
0x180009ff9  pop     r14
0x180009ffb  pop     rdi
0x180009ffc  pop     rsi
0x180009ffd  retn
0x180009ffe  jmp     short loc_180009FD9
0x18000a000  jmp     short loc_180009FD9
0x18000a002  jmp     short loc_180009FD9
0x18000a004  jmp     short loc_180009FD9
0x18000a006  jmp     short loc_180009FD9
0x18000a008  mov     [rsp+0D8h+var_B8], 45h ; 'E'; unsigned int
0x18000a010  lea     r9, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\drivers\\"...
0x18000a017  lea     r8, aFailedToWriteB; "Failed to write bytes to output stream"
0x18000a01e  mov     edx, eax; int
0x18000a020  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x18000a025  call    ??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z; PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)
0x18000a02a  lea     rdx, _TI2?AVWindowsError@PrintCore@@; pThrowInfo
0x18000a031  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000a036  call    _CxxThrowException_0
```
