# FSConstructSensorTransformUri

- ea: `0x18002f2e4`
- end: `0x18002f68f`
- name: `FSConstructSensorTransformUri`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ed6c`

## callees

- `0x180004f78`
- `0x1800060f8`
- `0x180006a98`
- `0x18000cadc`
- `0x18002f2e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f4bc`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f4e7`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f4bc`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002f4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f672`

## pseudocode

```c
__int64 __fastcall FSConstructSensorTransformUri(const IID *a1, unsigned __int16 *a2, __int64 a3, int *a4)
{
  HRESULT v7; // ebx
  int v8; // ecx
  __int64 v9; // rdx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // r11
  unsigned int v13; // r11d
  int v14; // r8d
  unsigned __int64 v15; // r11
  unsigned __int64 v16; // r11
  unsigned int v17; // r11d
  int v18; // ecx
  unsigned __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  LPOLESTR v22; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp-8h] BYREF
  LPOLESTR lpsz; // [rsp+80h] [rbp+20h] BYREF

  lpsz = 0;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)v7;
    v9 = 14;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)v7;
    v10 = 15;
    goto LABEL_54;
  }
  if ( !a1->Data1 )
  {
    v7 = StringFromIID(a1 + 1, &lpsz);
    if ( v7 >= 0 )
    {
      v7 = StringFromIID(a1 + 2, &v22);
      if ( v7 >= 0 )
      {
        v7 = StringCchLengthW(lpsz, 0x7FFFFFFFu, &v23);
        if ( v7 >= 0 )
        {
          v7 = StringCchLengthW(v22, v15, &v20);
          if ( v7 >= 0 )
          {
            v7 = StringCchLengthW(L"sensortransform://", v16, &v21);
            if ( v7 >= 0 )
            {
              v18 = v20 + v23 + v21 + 2;
              if ( v18 >= v17 )
              {
                v7 = -2147024809;
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_55;
                v9 = 21;
                goto LABEL_4;
              }
              *a4 = v18;
              if ( v18 >= 260 )
              {
                v7 = -1072860816;
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_55;
                v9 = 22;
                goto LABEL_4;
              }
              v7 = StringCchPrintfW(a2, 0x104u, L"%s%s%c%s", L"sensortransform://", lpsz, 58, v22);
              if ( v7 >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_55;
              v10 = 23;
            }
            else
            {
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_55;
              v10 = 20;
            }
          }
          else
          {
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_55;
            v10 = 19;
          }
        }
        else
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_55;
          v10 = 18;
        }
      }
      else
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_55;
        v10 = 17;
      }
    }
    else
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_55;
      v10 = 16;
    }
LABEL_54:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v7);
    goto LABEL_55;
  }
  if ( a1->Data1 != 2 )
  {
    v7 = -2147024846;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)v7;
    v10 = 30;
    goto LABEL_54;
  }
  v11 = *(const unsigned __int16 **)&a1[2].Data1;
  if ( v11 )
  {
    v7 = StringCchLengthW(v11, 0x7FFFFFFFu, &v20);
    if ( v7 >= 0 )
    {
      v7 = StringCchLengthW(L"sensortransformmodule://", v12, &v21);
      if ( v7 >= 0 )
      {
        v14 = v20 + v21 + 1;
        if ( v14 >= v13 )
        {
          v7 = -2147024809;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_55;
          v9 = 27;
          goto LABEL_4;
        }
        *a4 = v14;
        if ( v14 >= 260 )
        {
          v7 = -1072860816;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_55;
          v9 = 28;
          goto LABEL_4;
        }
        v7 = StringCchPrintfW(a2, 0x104u, L"%s%s", L"sensortransformmodule://", *(_QWORD *)&a1[2].Data1);
        if ( v7 >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_55;
        v10 = 29;
      }
      else
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_55;
        v10 = 26;
      }
    }
    else
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_55;
      v10 = 25;
    }
    goto LABEL_54;
  }
  v7 = -2147024809;
  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    return (unsigned int)v7;
  v9 = 24;
LABEL_4:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v8);
LABEL_55:
  if ( lpsz )
  {
    CoTaskMemFree(lpsz);
    lpsz = 0;
  }
  if ( v22 )
    CoTaskMemFree(v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002f2e4  mov     [rsp-18h+arg_8], rbx
0x18002f2e9  mov     [rsp-18h+arg_10], rsi
0x18002f2ee  push    rbp
0x18002f2ef  push    rdi
0x18002f2f0  push    r14
0x18002f2f2  mov     rbp, rsp
0x18002f2f5  sub     rsp, 60h
0x18002f2f9  mov     [rbp+lpsz], 0
0x18002f301  mov     rsi, r9
0x18002f304  mov     [rbp+var_10], 0
0x18002f30c  mov     r14, rdx
0x18002f30f  mov     [rbp+var_8], 0
0x18002f317  mov     rdi, rcx
0x18002f31a  mov     [rbp+var_20], 0
0x18002f322  mov     [rbp+var_18], 0
0x18002f32a  test    rcx, rcx
0x18002f32d  jnz     short loc_18002F34F
0x18002f32f  mov     ecx, 80070057h
0x18002f334  mov     ebx, ecx
0x18002f336  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f33b  cmp     al, 1
0x18002f33d  jb      loc_18002F678
0x18002f343  lea     edx, [rdi+0Eh]
0x18002f346  mov     dword ptr [rsp+60h+var_40], ecx
0x18002f34a  jmp     loc_18002F638
0x18002f34f  test    rsi, rsi
0x18002f352  jnz     short loc_18002F36E
0x18002f354  mov     ebx, 80004003h
0x18002f359  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f35e  cmp     al, 1
0x18002f360  jb      loc_18002F678
0x18002f366  lea     edx, [rsi+0Fh]
0x18002f369  jmp     loc_18002F634
0x18002f36e  cmp     dword ptr [rcx], 0
0x18002f371  jz      loc_18002F4B4
0x18002f377  cmp     dword ptr [rcx], 2
0x18002f37a  jz      short loc_18002F398
0x18002f37c  mov     ebx, 80070032h
0x18002f381  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f386  cmp     al, 1
0x18002f388  jb      loc_18002F678
0x18002f38e  mov     edx, 1Eh
0x18002f393  jmp     loc_18002F634
0x18002f398  mov     rcx, [rcx+20h]; unsigned __int16 *
0x18002f39c  test    rcx, rcx
0x18002f39f  jnz     short loc_18002F3BC
0x18002f3a1  mov     ecx, 80070057h
0x18002f3a6  mov     ebx, ecx
0x18002f3a8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f3ad  cmp     al, 1
0x18002f3af  jb      loc_18002F678
0x18002f3b5  mov     edx, 18h
0x18002f3ba  jmp     short loc_18002F346
0x18002f3bc  mov     r11d, 7FFFFFFFh
0x18002f3c2  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18002f3c6  mov     edx, r11d; unsigned __int64
0x18002f3c9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f3ce  mov     ebx, eax
0x18002f3d0  test    eax, eax
0x18002f3d2  jns     short loc_18002F3EB
0x18002f3d4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f3d9  cmp     al, 1
0x18002f3db  jb      loc_18002F652
0x18002f3e1  mov     edx, 19h
0x18002f3e6  jmp     loc_18002F634
0x18002f3eb  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18002f3ef  mov     rdx, r11; unsigned __int64
0x18002f3f2  lea     rcx, aSensortransfor_0; "sensortransformmodule://"
0x18002f3f9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f3fe  mov     ebx, eax
0x18002f400  test    eax, eax
0x18002f402  jns     short loc_18002F41B
0x18002f404  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f409  cmp     al, 1
0x18002f40b  jb      loc_18002F652
0x18002f411  mov     edx, 1Ah
0x18002f416  jmp     loc_18002F634
0x18002f41b  mov     r8d, dword ptr [rbp+var_18]
0x18002f41f  inc     r8d
0x18002f422  add     r8d, dword ptr [rbp+var_20]
0x18002f426  cmp     r8d, r11d
0x18002f429  jb      short loc_18002F449
0x18002f42b  mov     ecx, 80070057h
0x18002f430  mov     ebx, ecx
0x18002f432  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f437  cmp     al, 1
0x18002f439  jb      loc_18002F652
0x18002f43f  mov     edx, 1Bh
0x18002f444  jmp     loc_18002F346
0x18002f449  mov     edx, 104h; unsigned __int64
0x18002f44e  mov     [rsi], r8d
0x18002f451  cmp     r8d, edx
0x18002f454  jl      short loc_18002F474
0x18002f456  mov     ecx, 0C00D7170h
0x18002f45b  mov     ebx, ecx
0x18002f45d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f462  cmp     al, 1
0x18002f464  jb      loc_18002F652
0x18002f46a  mov     edx, 1Ch
0x18002f46f  jmp     loc_18002F346
0x18002f474  mov     rax, [rdi+20h]
0x18002f478  lea     r9, aSensortransfor_0; "sensortransformmodule://"
0x18002f47f  lea     r8, aSS; "%s%s"
0x18002f486  mov     [rsp+60h+var_40], rax
0x18002f48b  mov     rcx, r14; unsigned __int16 *
0x18002f48e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f493  mov     ebx, eax
0x18002f495  test    eax, eax
0x18002f497  jns     loc_18002F652
0x18002f49d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f4a2  cmp     al, 1
0x18002f4a4  jb      loc_18002F652
0x18002f4aa  mov     edx, 1Dh
0x18002f4af  jmp     loc_18002F634
0x18002f4b4  add     rcx, 10h; rclsid
0x18002f4b8  lea     rdx, [rbp+lpsz]; lplpsz
0x18002f4bc  call    cs:__imp_StringFromIID
0x18002f4c2  mov     ebx, eax
0x18002f4c4  test    eax, eax
0x18002f4c6  jns     short loc_18002F4DF
0x18002f4c8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f4cd  cmp     al, 1
0x18002f4cf  jb      loc_18002F652
0x18002f4d5  mov     edx, 10h
0x18002f4da  jmp     loc_18002F634
0x18002f4df  lea     rcx, [rdi+20h]; rclsid
0x18002f4e3  lea     rdx, [rbp+var_10]; lplpsz
0x18002f4e7  call    cs:__imp_StringFromIID
0x18002f4ed  mov     ebx, eax
0x18002f4ef  test    eax, eax
0x18002f4f1  jns     short loc_18002F50A
0x18002f4f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f4f8  cmp     al, 1
0x18002f4fa  jb      loc_18002F652
0x18002f500  mov     edx, 11h
0x18002f505  jmp     loc_18002F634
0x18002f50a  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18002f50e  lea     r8, [rbp+var_8]; unsigned __int64 *
0x18002f512  mov     r11d, 7FFFFFFFh
0x18002f518  mov     edx, r11d; unsigned __int64
0x18002f51b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f520  mov     ebx, eax
0x18002f522  test    eax, eax
0x18002f524  jns     short loc_18002F53D
0x18002f526  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f52b  cmp     al, 1
0x18002f52d  jb      loc_18002F652
0x18002f533  mov     edx, 12h
0x18002f538  jmp     loc_18002F634
0x18002f53d  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x18002f541  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18002f545  mov     rdx, r11; unsigned __int64
0x18002f548  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f54d  mov     ebx, eax
0x18002f54f  test    eax, eax
0x18002f551  jns     short loc_18002F56A
0x18002f553  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f558  cmp     al, 1
0x18002f55a  jb      loc_18002F652
0x18002f560  mov     edx, 13h
0x18002f565  jmp     loc_18002F634
0x18002f56a  lea     r8, [rbp+var_18]; unsigned __int64 *
0x18002f56e  mov     rdx, r11; unsigned __int64
0x18002f571  lea     rcx, aSensortransfor; "sensortransform://"
0x18002f578  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f57d  mov     ebx, eax
0x18002f57f  test    eax, eax
0x18002f581  jns     short loc_18002F59A
0x18002f583  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f588  cmp     al, 1
0x18002f58a  jb      loc_18002F652
0x18002f590  mov     edx, 14h
0x18002f595  jmp     loc_18002F634
0x18002f59a  mov     edx, dword ptr [rbp+var_8]
0x18002f59d  add     edx, dword ptr [rbp+var_20]
0x18002f5a0  mov     ecx, dword ptr [rbp+var_18]
0x18002f5a3  add     ecx, 2
0x18002f5a6  add     ecx, edx
0x18002f5a8  cmp     ecx, r11d
0x18002f5ab  jb      short loc_18002F5CB
0x18002f5ad  mov     ecx, 80070057h
0x18002f5b2  mov     ebx, ecx
0x18002f5b4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f5b9  cmp     al, 1
0x18002f5bb  jb      loc_18002F652
0x18002f5c1  mov     edx, 15h
0x18002f5c6  jmp     loc_18002F346
0x18002f5cb  mov     edx, 104h; unsigned __int64
0x18002f5d0  mov     [rsi], ecx
0x18002f5d2  cmp     ecx, edx
0x18002f5d4  jl      short loc_18002F5F0
0x18002f5d6  mov     ecx, 0C00D7170h
0x18002f5db  mov     ebx, ecx
0x18002f5dd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f5e2  cmp     al, 1
0x18002f5e4  jb      short loc_18002F652
0x18002f5e6  mov     edx, 16h
0x18002f5eb  jmp     loc_18002F346
0x18002f5f0  mov     rax, [rbp+var_10]
0x18002f5f4  lea     r9, aSensortransfor; "sensortransform://"
0x18002f5fb  mov     [rsp+60h+var_30], rax
0x18002f600  lea     r8, aSSCS; "%s%s%c%s"
0x18002f607  mov     rax, [rbp+lpsz]
0x18002f60b  mov     rcx, r14; unsigned __int16 *
0x18002f60e  mov     [rsp+60h+var_38], 3Ah ; ':'
0x18002f616  mov     [rsp+60h+var_40], rax
0x18002f61b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f620  mov     ebx, eax
0x18002f622  test    eax, eax
0x18002f624  jns     short loc_18002F652
0x18002f626  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f62b  cmp     al, 1
0x18002f62d  jb      short loc_18002F652
0x18002f62f  mov     edx, 17h
0x18002f634  mov     dword ptr [rsp+60h+var_40], ebx
0x18002f638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f63f  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002f646  xor     r9d, r9d
0x18002f649  mov     rcx, [rcx+10h]
0x18002f64d  call    WPP_SF_qD
0x18002f652  mov     rcx, [rbp+lpsz]; pv
0x18002f656  test    rcx, rcx
0x18002f659  jz      short loc_18002F669
0x18002f65b  call    cs:__imp_CoTaskMemFree
0x18002f661  mov     [rbp+lpsz], 0
0x18002f669  mov     rcx, [rbp+var_10]; pv
0x18002f66d  test    rcx, rcx
0x18002f670  jz      short loc_18002F678
0x18002f672  call    cs:__imp_CoTaskMemFree
0x18002f678  lea     r11, [rsp+60h+var_s0]
0x18002f67d  mov     eax, ebx
0x18002f67f  mov     rbx, [r11+28h]
0x18002f683  mov     rsi, [r11+30h]
0x18002f687  mov     rsp, r11
0x18002f68a  pop     r14
0x18002f68c  pop     rdi
0x18002f68d  pop     rbp
0x18002f68e  retn
```
