# FSMCameraDeviceRegistryEntry::InternalInitialize(ushort const *,ushort const *,uchar const *,ulong)

- ea: `0x1800478ac`
- end: `0x180047d1d`
- name: `?InternalInitialize@FSMCameraDeviceRegistryEntry@@IEAAJPEBG0PEBEK@Z`
- size: `1137`
- prototype: `int(FSMCameraDeviceRegistryEntry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004761c`

## callees

- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000cadc`
- `0x18000d1e0`
- `0x180031a18`
- `0x1800478ac`
- `0x180048aec`
- `0x180048eb0`
- `0x18004bf50`

## string_xrefs

- `0x1800478e3`: `CustomCaptureSourceClsid`
- `0x18004792c`: `CustomCaptureSourceClsid`
- `0x180047a7b`: `CustomCaptureSourceClsid`
- `0x180047c2d`: `CustomCaptureSourceClsid`

## pseudocode

```c
__int64 __fastcall FSMCameraDeviceRegistryEntry::InternalInitialize(
        FSMCameraDeviceRegistryEntry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        size_t Size)
{
  unsigned __int8 Level; // al
  char v8; // r9
  size_t v9; // r14
  size_t v10; // rbp
  int v11; // ebx
  int v12; // ecx
  const GUID *v13; // r11
  __int64 v14; // rdx
  int v15; // r13d
  unsigned __int64 v16; // r12
  __int64 v17; // r14
  unsigned int v18; // eax
  const struct std::nothrow_t *unique; // rax
  __int64 v20; // r11
  int v21; // r11d
  const GUID *v22; // r8
  unsigned int v23; // eax
  int v24; // ecx
  __int64 v25; // r11
  __int64 v26; // rdx
  int v28; // [rsp+20h] [rbp-58h]
  unsigned __int64 v29; // [rsp+90h] [rbp+18h] BYREF

  v29 = 0;
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  v9 = (unsigned int)Size;
  v10 = 8;
  if ( Level >= 8u )
    WPP_SF_qSSdqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (__int64)L"CustomCaptureSourceClsid",
      (__int64)L"<nullptr>",
      *((_DWORD *)this + 19),
      v8,
      Size);
  if ( !a4 )
  {
    if ( !(_DWORD)v9 )
      goto LABEL_5;
LABEL_9:
    v11 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 36;
    goto LABEL_70;
  }
  if ( !(_DWORD)v9 )
    goto LABEL_9;
LABEL_5:
  if ( *((_DWORD *)this + 19) <= 1u )
  {
    v11 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 37;
LABEL_70:
    v28 = v12;
    goto LABEL_71;
  }
  v11 = StringCchLengthW(L"CustomCaptureSourceClsid", 0x7FFFFFFEu, &v29);
  if ( v11 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 38;
LABEL_14:
    v28 = v11;
LABEL_71:
    v22 = v13;
    goto LABEL_72;
  }
  v15 = v29 + 1;
  v16 = 2LL * (unsigned int)(v29 + 1);
  if ( v16 > 0xFFFFFFFF )
  {
    v11 = -2147024362;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 39;
    goto LABEL_70;
  }
  if ( *((_DWORD *)this + 19) == 2 )
  {
    v10 = 4;
    if ( a4 && (_DWORD)v9 != 4 )
    {
      v11 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v14 = 42;
      goto LABEL_70;
    }
  }
  else if ( *((_DWORD *)this + 19) == 3 )
  {
    if ( a4 && (_DWORD)v9 != 8 )
    {
      v11 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v14 = 43;
      goto LABEL_70;
    }
  }
  else
  {
    if ( *((_DWORD *)this + 19) == 4 )
    {
      if ( a4 )
      {
        if ( (v9 & 1) != 0 )
        {
          v11 = -2147024809;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_73;
          v14 = 44;
          goto LABEL_70;
        }
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
          WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)L"CustomCaptureSourceClsid", (__int64)a4);
        v11 = StringCchLengthW(a4, (unsigned int)v9 >> 1, &v29);
        if ( v11 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_73;
          v14 = 46;
          goto LABEL_14;
        }
      }
    }
    else if ( *((_DWORD *)this + 19) != 5 )
    {
      v11 = -2147024809;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v14 = 47;
      goto LABEL_70;
    }
    v10 = v9;
  }
  v17 = (unsigned int)(v16 + 20);
  if ( (unsigned int)v16 >= 0xFFFFFFEC )
  {
    *((_DWORD *)this + 18) = -1;
    v11 = -2147024362;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 48;
    goto LABEL_70;
  }
  v18 = v17 + v10;
  if ( (int)v17 + (int)v10 < (unsigned int)v17 )
  {
    *((_DWORD *)this + 18) = -1;
    v11 = -2147024362;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 50;
    goto LABEL_70;
  }
  *((_DWORD *)this + 18) = v18;
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v29, v18);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 8, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v29);
  v20 = *((_QWORD *)this + 8);
  if ( !v20 )
  {
    v11 = -2147024882;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = (unsigned int)(v21 + 51);
LABEL_49:
    v28 = v11;
LABEL_50:
    v22 = &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids;
LABEL_72:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v22, this, v28);
LABEL_73:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v26 = 58;
      goto LABEL_75;
    }
    return (unsigned int)v11;
  }
  v23 = *((_DWORD *)this + 18);
  if ( v23 < 0x14 )
  {
    v11 = -1072875845;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 52;
LABEL_54:
    v28 = v24;
    goto LABEL_50;
  }
  *(_DWORD *)v20 = v23;
  *(_DWORD *)(v20 + 4) = *((_DWORD *)this + 19);
  *(_DWORD *)(v20 + 8) = v15;
  *(_DWORD *)(v20 + 12) = 0;
  *(_DWORD *)(v20 + 16) = v10;
  if ( *((_DWORD *)this + 18) < (unsigned int)v17 )
  {
    v11 = -1072875845;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 53;
    goto LABEL_54;
  }
  v11 = StringCbCopyW((unsigned __int16 *)(v20 + 20), (unsigned int)v16, L"CustomCaptureSourceClsid");
  if ( v11 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_73;
    v14 = 54;
    goto LABEL_49;
  }
  if ( v10 )
  {
    if ( *((unsigned int *)this + 18) < v17 + v10 )
    {
      v11 = -1072875845;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v14 = 57;
      goto LABEL_54;
    }
    memcpy_0((void *)(v17 + v25), a4, v10);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v26 = 59;
LABEL_75:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v26, &WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids, this, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800478ac  mov     rax, rsp
0x1800478af  mov     [rax+8], rbx
0x1800478b3  mov     [rax+10h], rbp
0x1800478b7  mov     [rax+18h], r8
0x1800478bb  push    rdi
0x1800478bc  push    r12
0x1800478be  push    r13
0x1800478c0  push    r14
0x1800478c2  push    r15
0x1800478c4  sub     rsp, 50h
0x1800478c8  mov     r15, r9
0x1800478cb  mov     qword ptr [rax+18h], 0
0x1800478d3  mov     rdi, rcx
0x1800478d6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800478db  mov     r14d, dword ptr [rsp+78h+Size]
0x1800478e3  lea     rcx, aCustomcaptures; "CustomCaptureSourceClsid"
0x1800478ea  mov     ebp, 8
0x1800478ef  cmp     al, bpl
0x1800478f2  jb      short loc_180047933
0x1800478f4  mov     eax, [rdi+4Ch]
0x1800478f7  mov     dword ptr [rsp+78h+var_38], r14d; char
0x1800478fc  mov     qword ptr [rsp+78h+var_40], r9; char
0x180047901  mov     r9, rdi
0x180047904  mov     dword ptr [rsp+78h+var_48], eax; char
0x180047908  lea     rax, aNullptr; "<nullptr>"
0x18004790f  mov     [rsp+78h+var_50], rax; __int64
0x180047914  mov     [rsp+78h+var_58], rcx; __int64
0x180047919  mov     rcx, cs:WPP_GLOBAL_Control
0x180047920  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180047927  call    WPP_SF_qSSdqD
0x18004792c  lea     rcx, aCustomcaptures; "CustomCaptureSourceClsid"
0x180047933  lea     r11, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x18004793a  test    r15, r15
0x18004793d  jnz     short loc_180047968
0x18004793f  test    r14d, r14d
0x180047942  jnz     short loc_18004796D
0x180047944  cmp     dword ptr [rdi+4Ch], 1
0x180047948  ja      short loc_18004798B
0x18004794a  mov     ecx, 80070057h
0x18004794f  mov     ebx, ecx
0x180047951  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047956  cmp     al, 1
0x180047958  jb      loc_180047CD2
0x18004795e  mov     edx, 25h ; '%'
0x180047963  jmp     loc_180047CB8
0x180047968  test    r14d, r14d
0x18004796b  jnz     short loc_180047944
0x18004796d  mov     ecx, 80070057h
0x180047972  mov     ebx, ecx
0x180047974  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047979  cmp     al, 1
0x18004797b  jb      loc_180047CD2
0x180047981  mov     edx, 24h ; '$'
0x180047986  jmp     loc_180047CB8
0x18004798b  lea     r8, [rsp+78h+arg_10]; unsigned __int64 *
0x180047993  mov     edx, 7FFFFFFEh; unsigned __int64
0x180047998  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004799d  mov     ebx, eax
0x18004799f  test    eax, eax
0x1800479a1  jns     short loc_1800479BE
0x1800479a3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800479a8  cmp     al, 1
0x1800479aa  jb      loc_180047CD2
0x1800479b0  mov     edx, 26h ; '&'
0x1800479b5  mov     dword ptr [rsp+78h+var_58], ebx
0x1800479b9  jmp     loc_180047CBC
0x1800479be  mov     r13, [rsp+78h+arg_10]
0x1800479c6  mov     edx, 0FFFFFFFFh
0x1800479cb  inc     r13
0x1800479ce  mov     r12d, r13d
0x1800479d1  add     r12, r12
0x1800479d4  cmp     r12, rdx
0x1800479d7  jbe     short loc_1800479F7
0x1800479d9  mov     ecx, 80070216h
0x1800479de  mov     ebx, ecx
0x1800479e0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800479e5  cmp     al, 1
0x1800479e7  jb      loc_180047CD2
0x1800479ed  mov     edx, 27h ; '''
0x1800479f2  jmp     loc_180047CB8
0x1800479f7  mov     ecx, [rdi+4Ch]
0x1800479fa  sub     ecx, 2
0x1800479fd  jz      loc_180047B32
0x180047a03  sub     ecx, 1
0x180047a06  jz      loc_180047B0A
0x180047a0c  sub     ecx, 1
0x180047a0f  jz      short loc_180047A38
0x180047a11  cmp     ecx, 1
0x180047a14  jz      loc_180047ADB
0x180047a1a  mov     ecx, 80070057h
0x180047a1f  mov     ebx, ecx
0x180047a21  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047a26  cmp     al, 1
0x180047a28  jb      loc_180047CD2
0x180047a2e  mov     edx, 2Fh ; '/'
0x180047a33  jmp     loc_180047CB8
0x180047a38  test    r15, r15
0x180047a3b  jz      loc_180047ADB
0x180047a41  test    r14b, 1
0x180047a45  jz      short loc_180047A65
0x180047a47  mov     ecx, 80070057h
0x180047a4c  mov     ebx, ecx
0x180047a4e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047a53  cmp     al, 1
0x180047a55  jb      loc_180047CD2
0x180047a5b  mov     edx, 2Ch ; ','
0x180047a60  jmp     loc_180047CB8
0x180047a65  mov     ebx, r14d
0x180047a68  shr     ebx, 1
0x180047a6a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180047a6f  cmp     al, bpl
0x180047a72  jb      short loc_180047AA7
0x180047a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a7b  lea     rax, aCustomcaptures; "CustomCaptureSourceClsid"
0x180047a82  mov     edx, 2Dh ; '-'
0x180047a87  mov     [rsp+78h+var_50], r15; __int64
0x180047a8c  mov     r9, rdi
0x180047a8f  mov     [rsp+78h+var_58], rax; __int64
0x180047a94  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180047a9b  call    WPP_SF_qSS
0x180047aa0  lea     r11, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x180047aa7  mov     edx, ebx; unsigned __int64
0x180047aa9  lea     r8, [rsp+78h+arg_10]; unsigned __int64 *
0x180047ab1  mov     rcx, r15; unsigned __int16 *
0x180047ab4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180047ab9  mov     ebx, eax
0x180047abb  test    eax, eax
0x180047abd  jns     short loc_180047AD6
0x180047abf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047ac4  cmp     al, 1
0x180047ac6  jb      loc_180047CD2
0x180047acc  mov     edx, 2Eh ; '.'
0x180047ad1  jmp     loc_1800479B5
0x180047ad6  mov     edx, 0FFFFFFFFh
0x180047adb  mov     rbp, r14
0x180047ade  lea     r14d, [r12+14h]
0x180047ae3  cmp     r14d, 14h
0x180047ae7  jnb     short loc_180047B5D
0x180047ae9  mov     ecx, 80070216h
0x180047aee  mov     [rdi+48h], edx
0x180047af1  mov     ebx, ecx
0x180047af3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047af8  cmp     al, 1
0x180047afa  jb      loc_180047CD2
0x180047b00  mov     edx, 30h ; '0'
0x180047b05  jmp     loc_180047CB8
0x180047b0a  test    r15, r15
0x180047b0d  jz      short loc_180047ADE
0x180047b0f  cmp     r14d, ebp
0x180047b12  jz      short loc_180047ADE
0x180047b14  mov     ecx, 80070057h
0x180047b19  mov     ebx, ecx
0x180047b1b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047b20  cmp     al, 1
0x180047b22  jb      loc_180047CD2
0x180047b28  mov     edx, 2Bh ; '+'
0x180047b2d  jmp     loc_180047CB8
0x180047b32  mov     ebp, 4
0x180047b37  test    r15, r15
0x180047b3a  jz      short loc_180047ADE
0x180047b3c  cmp     r14d, ebp
0x180047b3f  jz      short loc_180047ADE
0x180047b41  mov     ecx, 80070057h
0x180047b46  mov     ebx, ecx
0x180047b48  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047b4d  cmp     al, 1
0x180047b4f  jb      loc_180047CD2
0x180047b55  lea     edx, [rbp+26h]
0x180047b58  jmp     loc_180047CB8
0x180047b5d  lea     eax, [r14+rbp]
0x180047b61  cmp     eax, r14d
0x180047b64  jb      loc_180047CA0
0x180047b6a  mov     edx, eax
0x180047b6c  lea     rcx, [rsp+78h+arg_10]
0x180047b74  mov     [rdi+48h], eax
0x180047b77  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180047b7c  mov     rdx, rax
0x180047b7f  lea     rcx, [rdi+40h]
0x180047b83  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180047b88  lea     rcx, [rsp+78h+arg_10]
0x180047b90  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180047b95  mov     r11, [rdi+40h]
0x180047b99  test    r11, r11
0x180047b9c  jnz     short loc_180047BC4
0x180047b9e  mov     ebx, 8007000Eh
0x180047ba3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047ba8  cmp     al, 1
0x180047baa  jb      loc_180047CD2
0x180047bb0  lea     edx, [r11+33h]
0x180047bb4  mov     dword ptr [rsp+78h+var_58], ebx
0x180047bb8  lea     r8, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x180047bbf  jmp     loc_180047CBF
0x180047bc4  mov     eax, [rdi+48h]
0x180047bc7  cmp     eax, 14h
0x180047bca  jnb     short loc_180047BEB
0x180047bcc  mov     ecx, 0C00D36BBh
0x180047bd1  mov     ebx, ecx
0x180047bd3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047bd8  cmp     al, 1
0x180047bda  jb      loc_180047CD2
0x180047be0  mov     edx, 34h ; '4'
0x180047be5  mov     dword ptr [rsp+78h+var_58], ecx
0x180047be9  jmp     short loc_180047BB8
0x180047beb  mov     [r11], eax
0x180047bee  mov     eax, [rdi+4Ch]
0x180047bf1  mov     [r11+4], eax
0x180047bf5  mov     [r11+8], r13d
0x180047bf9  mov     dword ptr [r11+0Ch], 0
0x180047c01  mov     [r11+10h], ebp
0x180047c05  cmp     [rdi+48h], r14d
0x180047c09  jnb     short loc_180047C26
0x180047c0b  mov     ecx, 0C00D36BBh
0x180047c10  mov     ebx, ecx
0x180047c12  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047c17  cmp     al, 1
0x180047c19  jb      loc_180047CD2
0x180047c1f  mov     edx, 35h ; '5'
0x180047c24  jmp     short loc_180047BE5
0x180047c26  mov     edx, r12d; unsigned __int64
0x180047c29  lea     rcx, [r11+14h]; unsigned __int16 *
0x180047c2d  lea     r8, aCustomcaptures; "CustomCaptureSourceClsid"
0x180047c34  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180047c39  mov     ebx, eax
0x180047c3b  test    eax, eax
0x180047c3d  jns     short loc_180047C56
0x180047c3f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047c44  cmp     al, 1
0x180047c46  jb      loc_180047CD2
0x180047c4c  mov     edx, 36h ; '6'
0x180047c51  jmp     loc_180047BB4
0x180047c56  test    rbp, rbp
0x180047c59  jz      short loc_180047C90
0x180047c5b  mov     eax, [rdi+48h]
0x180047c5e  lea     rcx, [r14+rbp]
0x180047c62  cmp     rax, rcx
0x180047c65  jnb     short loc_180047C81
0x180047c67  mov     ecx, 0C00D36BBh
0x180047c6c  mov     ebx, ecx
0x180047c6e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047c73  cmp     al, 1
0x180047c75  jb      short loc_180047CD2
0x180047c77  mov     edx, 39h ; '9'
0x180047c7c  jmp     loc_180047BE5
0x180047c81  lea     rcx, [r14+r11]; void *
0x180047c85  mov     r8, rbp; Size
0x180047c88  mov     rdx, r15; Src
0x180047c8b  call    memcpy_0
0x180047c90  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180047c95  cmp     al, 8
0x180047c97  jb      short loc_180047D01
0x180047c99  mov     edx, 3Bh ; ';'
0x180047c9e  jmp     short loc_180047CE0
0x180047ca0  mov     ecx, 80070216h
0x180047ca5  mov     [rdi+48h], edx
0x180047ca8  mov     ebx, ecx
0x180047caa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180047caf  cmp     al, 1
0x180047cb1  jb      short loc_180047CD2
0x180047cb3  mov     edx, 32h ; '2'
0x180047cb8  mov     dword ptr [rsp+78h+var_58], ecx
0x180047cbc  mov     r8, r11
0x180047cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180047cc6  mov     r9, rdi
0x180047cc9  mov     rcx, [rcx+10h]
0x180047ccd  call    WPP_SF_qD
0x180047cd2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180047cd7  cmp     al, 1
0x180047cd9  jb      short loc_180047D01
0x180047cdb  mov     edx, 3Ah ; ':'
0x180047ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ce7  lea     r8, WPP_2c63616102ab3879fc06f5609f11f22c_Traceguids
0x180047cee  mov     r9, rdi
0x180047cf1  mov     dword ptr [rsp+78h+var_58], ebx
0x180047cf5  mov     rcx, [rcx+0D8h]
0x180047cfc  call    WPP_SF_qD
0x180047d01  lea     r11, [rsp+78h+var_28]
0x180047d06  mov     eax, ebx
0x180047d08  mov     rbx, [r11+30h]
0x180047d0c  mov     rbp, [r11+38h]
0x180047d10  mov     rsp, r11
0x180047d13  pop     r15
0x180047d15  pop     r14
0x180047d17  pop     r13
0x180047d19  pop     r12
0x180047d1b  pop     rdi
0x180047d1c  retn
```
