# SensorDevice::CreateSensorStreamFromBlob(__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *,uchar const *,long,IMFSensorStreamInternal * *)

- ea: `0x18001abe4`
- end: `0x18001ad82`
- name: `?CreateSensorStreamFromBlob@SensorDevice@@IEAAJPEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005@@PEBEJPEAPEAUIMFSensorStreamInternal@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(SensorDevice *this, struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *, const unsigned __int8 *, unsigned int, struct IMFSensorStreamInternal **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a100`

## callees

- `0x180005fa0`
- `0x18001abe4`
- `0x18001af34`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18001ac4c`
- `MFPlat!MFCreateAttributes` at `0x18001ac4c`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001ac68`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001ac68`

## pseudocode

```c
__int64 __fastcall SensorDevice::CreateSensorStreamFromBlob(
        SensorDevice *this,
        struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        struct IMFSensorStreamInternal **a5)
{
  struct IMFSensorStreamInternal **v8; // rsi
  HRESULT SensorStream; // eax
  unsigned int v10; // ebx
  __int64 v12; // rdx
  IMFAttributes *pAttributes; // [rsp+58h] [rbp+10h] BYREF

  pAttributes = 0;
  if ( !a2 )
  {
    SensorStream = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      return v10;
    v12 = 287;
    goto LABEL_16;
  }
  v8 = a5;
  if ( !a5 )
  {
    v10 = -2147467261;
    if ( !g_wppLevels )
      return v10;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      288,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      this,
      -2147467261);
    goto LABEL_9;
  }
  *a5 = 0;
  if ( !a3 )
  {
    SensorStream = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      return v10;
    v12 = 289;
    goto LABEL_16;
  }
  if ( a4 < 0x10 || (signed int)a4 < *((_DWORD *)a2 + 2) )
  {
    SensorStream = -2147024809;
    v10 = -2147024809;
    if ( !g_wppLevels )
      return v10;
    v12 = 290;
    goto LABEL_16;
  }
  SensorStream = MFCreateAttributes(&pAttributes, 1u);
  v10 = SensorStream;
  if ( SensorStream < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_9;
    v12 = 291;
    goto LABEL_16;
  }
  SensorStream = MFInitAttributesFromBlob(pAttributes, a3, *((_DWORD *)a2 + 2));
  v10 = SensorStream;
  if ( SensorStream < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_9;
    v12 = 292;
    goto LABEL_16;
  }
  SensorStream = SensorStream::CreateSensorStream(*((_DWORD *)a2 + 1), *((_DWORD *)this + 52), pAttributes, v8);
  v10 = SensorStream;
  if ( SensorStream < 0 && g_wppLevels )
  {
    v12 = 293;
LABEL_16:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      this,
      SensorStream);
  }
LABEL_9:
  if ( pAttributes )
    ((void (__fastcall *)(IMFAttributes *))pAttributes->lpVtbl->Release)(pAttributes);
  return v10;
}

```

## disassembly

```asm
0x18001abe4  mov     rax, rsp
0x18001abe7  mov     [rax+8], rbx
0x18001abeb  mov     [rax+18h], rbp
0x18001abef  push    rsi
0x18001abf0  push    rdi
0x18001abf1  push    r14
0x18001abf3  sub     rsp, 30h
0x18001abf7  mov     qword ptr [rax+10h], 0
0x18001abff  mov     r14, r8
0x18001ac02  mov     rbp, rdx
0x18001ac05  mov     rdi, rcx
0x18001ac08  test    rdx, rdx
0x18001ac0b  jz      loc_18001ACC3
0x18001ac11  mov     rsi, [rsp+48h+arg_20]
0x18001ac16  test    rsi, rsi
0x18001ac19  jz      loc_18001AD0F
0x18001ac1f  mov     qword ptr [rsi], 0
0x18001ac26  test    r8, r8
0x18001ac29  jz      loc_18001AD28
0x18001ac2f  cmp     r9d, 10h
0x18001ac33  jb      loc_18001ACDA
0x18001ac39  cmp     r9d, [rdx+8]
0x18001ac3d  jl      loc_18001ACDA
0x18001ac43  mov     edx, 1; cInitialSize
0x18001ac48  lea     rcx, [rax+10h]; ppMFAttributes
0x18001ac4c  call    cs:__imp_MFCreateAttributes
0x18001ac52  mov     ebx, eax
0x18001ac54  test    eax, eax
0x18001ac56  js      loc_18001AD43
0x18001ac5c  mov     r8d, [rbp+8]; cbBufSize
0x18001ac60  mov     rdx, r14; pBuf
0x18001ac63  mov     rcx, [rsp+48h+pAttributes]; pAttributes
0x18001ac68  call    cs:__imp_MFInitAttributesFromBlob
0x18001ac6e  mov     ebx, eax
0x18001ac70  test    eax, eax
0x18001ac72  js      loc_18001AD57
0x18001ac78  mov     r8, [rsp+48h+pAttributes]; struct IMFAttributes *
0x18001ac7d  mov     r9, rsi; struct IMFSensorStreamInternal **
0x18001ac80  mov     edx, [rdi+0D0h]; int
0x18001ac86  mov     ecx, [rbp+4]; unsigned int
0x18001ac89  call    ?CreateSensorStream@SensorStream@@SAJKJPEAUIMFAttributes@@PEAPEAUIMFSensorStreamInternal@@@Z; SensorStream::CreateSensorStream(ulong,long,IMFAttributes *,IMFSensorStreamInternal * *)
0x18001ac8e  mov     ebx, eax
0x18001ac90  test    eax, eax
0x18001ac92  js      loc_18001AD6B
0x18001ac98  mov     rcx, [rsp+48h+pAttributes]
0x18001ac9d  test    rcx, rcx
0x18001aca0  jz      short loc_18001ACAE
0x18001aca2  mov     rax, [rcx]
0x18001aca5  mov     rax, [rax+10h]
0x18001aca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acae  mov     rbp, [rsp+48h+arg_10]
0x18001acb3  mov     eax, ebx
0x18001acb5  mov     rbx, [rsp+48h+arg_0]
0x18001acba  add     rsp, 30h
0x18001acbe  pop     r14
0x18001acc0  pop     rdi
0x18001acc1  pop     rsi
0x18001acc2  retn
0x18001acc3  mov     eax, 80070057h
0x18001acc8  mov     ebx, eax
0x18001acca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001acd1  jb      short loc_18001ACAE
0x18001acd3  mov     edx, 11Fh
0x18001acd8  jmp     short loc_18001ACEF
0x18001acda  mov     eax, 80070057h
0x18001acdf  mov     ebx, eax
0x18001ace1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ace8  jb      short loc_18001ACAE
0x18001acea  mov     edx, 122h
0x18001acef  mov     [rsp+48h+var_28], eax
0x18001acf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acfa  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001ad01  mov     r9, rdi
0x18001ad04  mov     rcx, [rcx+10h]
0x18001ad08  call    WPP_SF_qD
0x18001ad0d  jmp     short loc_18001AC98
0x18001ad0f  mov     ebx, 80004003h
0x18001ad14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad1b  jb      short loc_18001ACAE
0x18001ad1d  mov     edx, 120h
0x18001ad22  mov     [rsp+48h+var_28], ebx
0x18001ad26  jmp     short loc_18001ACF3
0x18001ad28  mov     eax, 80070057h
0x18001ad2d  mov     ebx, eax
0x18001ad2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad36  jb      loc_18001ACAE
0x18001ad3c  mov     edx, 121h
0x18001ad41  jmp     short loc_18001ACEF
0x18001ad43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad4a  jb      loc_18001AC98
0x18001ad50  mov     edx, 123h
0x18001ad55  jmp     short loc_18001ACEF
0x18001ad57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad5e  jb      loc_18001AC98
0x18001ad64  mov     edx, 124h
0x18001ad69  jmp     short loc_18001ACEF
0x18001ad6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad72  jb      loc_18001AC98
0x18001ad78  mov     edx, 125h
0x18001ad7d  jmp     loc_18001ACEF
```
