# PimIMService::UpdateMetadata(SyncPartnerData const &,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &)

- ea: `0x18000adf0`
- end: `0x18000affe`
- name: `?UpdateMetadata@PimIMService@@UEAAJAEBUSyncPartnerData@@AEBU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@Z`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x1800086a0`
- `0x18000adf0`
- `0x18000c88c`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000aeb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af18`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aeb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af18`

## string_xrefs

- `0x18000aea0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000aefd`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000af39`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000af9a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::UpdateMetadata(__int64 a1, __int64 a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __int64 v4; // rcx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // edi
  OLECHAR *v11; // rcx
  OLECHAR *v12; // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // r9
  __int64 v17; // [rsp+40h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-41h] BYREF
  int v19; // [rsp+50h] [rbp-39h] BYREF
  __int128 v20; // [rsp+54h] [rbp-35h]
  _BYTE v21[28]; // [rsp+64h] [rbp-25h] BYREF
  __int64 v22; // [rsp+80h] [rbp-9h] BYREF
  int v23; // [rsp+88h] [rbp-1h]
  __int128 v24; // [rsp+90h] [rbp+7h]
  __int128 v25; // [rsp+A0h] [rbp+17h]
  __int128 v26; // [rsp+B0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+37h]

  v3 = *a3;
  v4 = *((_QWORD *)a3 + 7);
  v17 = v4;
  v6 = a3[1];
  v24 = v3;
  v7 = a3[2];
  v25 = v6;
  v27 = *((_QWORD *)a3 + 6);
  v26 = v7;
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    v8 = v17;
    goto LABEL_10;
  }
  if ( (_DWORD)v24 == 4 )
    goto LABEL_18;
  v22 = *(_QWORD *)((char *)&v24 + 4);
  bstrString = 0;
  v23 = HIDWORD(v24);
  v9 = OLITEMIDToString(&v22, &bstrString);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = bstrString;
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *, BSTR, __int64 *))(**(_QWORD **)(a2 + 8) + 136LL))(
            *(_QWORD *)(a2 + 8),
            0,
            12,
            &v22,
            bstrString,
            &v17);
    v10 = v13;
    if ( v13 >= 0 )
    {
      SysFreeString(v12);
      v8 = v17;
LABEL_10:
      if ( (_DWORD)v24 == 4 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 128LL))(v8);
        v10 = v14;
        if ( v14 < 0 )
        {
          v15 = 2587;
          goto LABEL_15;
        }
      }
      else
      {
        if ( WORD3(v25) )
        {
          Log_AssertionEvent(
            v8,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            2567);
          v8 = v17;
        }
        v19 = *(_DWORD *)(a2 + 16);
        memset(v21, 0, sizeof(v21));
        *(_DWORD *)&v21[12] = 16;
        v20 = 0;
        DWORD1(v20) = DWORD2(v25);
        *(_DWORD *)&v21[4] = *(_DWORD *)(a2 + 20);
        *(_QWORD *)&v21[20] = (char *)&v26 + 8;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v8 + 40LL))(v8, 2, &v19);
        v10 = v14;
        if ( v14 < 0 )
        {
          v15 = 2579;
LABEL_15:
          Log_HREvent(
            (unsigned int)v14,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            v15);
          goto LABEL_19;
        }
      }
LABEL_18:
      v10 = 0;
      goto LABEL_19;
    }
    Log_HREvent(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2561);
    v11 = v12;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      2553);
    v11 = bstrString;
  }
  SysFreeString(v11);
LABEL_19:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return v10;
}

```

## disassembly

```asm
0x18000adf0  mov     [rsp-8+arg_0], rbx
0x18000adf5  mov     [rsp-8+arg_18], rsi
0x18000adfa  push    rbp
0x18000adfb  push    rdi
0x18000adfc  push    r14
0x18000adfe  lea     rbp, [rsp-47h]
0x18000ae03  sub     rsp, 0D0h
0x18000ae0a  mov     rax, cs:__security_cookie
0x18000ae11  xor     rax, rsp
0x18000ae14  mov     [rbp+57h+var_18], rax
0x18000ae18  movups  xmm0, xmmword ptr [r8]
0x18000ae1c  mov     rcx, [r8+38h]
0x18000ae20  xor     r14d, r14d
0x18000ae23  mov     [rbp+57h+var_A0], rcx
0x18000ae27  mov     rsi, rdx
0x18000ae2a  movups  xmm1, xmmword ptr [r8+10h]
0x18000ae2f  movups  [rbp+57h+var_50], xmm0
0x18000ae33  movups  xmm0, xmmword ptr [r8+20h]
0x18000ae38  movups  [rbp+57h+var_40], xmm1
0x18000ae3c  movsd   xmm1, qword ptr [r8+30h]
0x18000ae42  movsd   [rbp+57h+var_20], xmm1
0x18000ae47  movups  [rbp+57h+var_30], xmm0
0x18000ae4b  test    rcx, rcx
0x18000ae4e  jz      short loc_18000AE69
0x18000ae50  mov     rax, [rcx]
0x18000ae53  mov     rax, [rax+8]
0x18000ae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5c  mov     rcx, [rbp+57h+var_A0]
0x18000ae60  test    rcx, rcx
0x18000ae63  jnz     loc_18000AF22
0x18000ae69  cmp     dword ptr [rbp+57h+var_50], 4
0x18000ae6d  jz      loc_18000AFCC
0x18000ae73  movsd   xmm0, qword ptr [rbp+57h+var_50+4]
0x18000ae78  lea     rdx, [rbp+57h+bstrString]
0x18000ae7c  mov     eax, dword ptr [rbp+57h+var_50+0Ch]
0x18000ae7f  lea     rcx, [rbp+57h+var_60]
0x18000ae83  movsd   [rbp+57h+var_60], xmm0
0x18000ae88  mov     [rbp+57h+bstrString], r14
0x18000ae8c  mov     [rbp+57h+var_58], eax
0x18000ae8f  call    OLITEMIDToString
0x18000ae94  mov     edi, eax
0x18000ae96  test    eax, eax
0x18000ae98  jns     short loc_18000AEC2
0x18000ae9a  mov     r9d, 9F9h
0x18000aea0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000aea7  mov     edx, 1
0x18000aeac  mov     ecx, eax
0x18000aeae  call    Log_HREvent
0x18000aeb3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000aeb7  call    cs:__imp_SysFreeString
0x18000aebd  jmp     loc_18000AFCF
0x18000aec2  mov     rcx, [rsi+8]
0x18000aec6  lea     rdx, [rbp+57h+var_A0]
0x18000aeca  mov     rbx, [rbp+57h+bstrString]
0x18000aece  lea     r9, [rbp+57h+var_60]
0x18000aed2  mov     [rsp+0E0h+var_B8], rdx
0x18000aed7  xor     edx, edx
0x18000aed9  mov     [rsp+0E0h+var_C0], rbx
0x18000aede  mov     rax, [rcx]
0x18000aee1  lea     r8d, [rdx+0Ch]
0x18000aee5  mov     rax, [rax+88h]
0x18000aeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef1  mov     edi, eax
0x18000aef3  test    eax, eax
0x18000aef5  jns     short loc_18000AF15
0x18000aef7  mov     r9d, 0A01h
0x18000aefd  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000af04  mov     edx, 1
0x18000af09  mov     ecx, eax
0x18000af0b  call    Log_HREvent
0x18000af10  mov     rcx, rbx
0x18000af13  jmp     short loc_18000AEB7
0x18000af15  mov     rcx, rbx; bstrString
0x18000af18  call    cs:__imp_SysFreeString
0x18000af1e  mov     rcx, [rbp+57h+var_A0]
0x18000af22  cmp     dword ptr [rbp+57h+var_50], 4
0x18000af26  jz      loc_18000AFAF
0x18000af2c  cmp     word ptr [rbp+57h+var_40+6], r14w
0x18000af31  jz      short loc_18000AF49
0x18000af33  mov     r8d, 0A07h
0x18000af39  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000af40  call    Log_AssertionEvent
0x18000af45  mov     rcx, [rbp+57h+var_A0]
0x18000af49  mov     eax, [rsi+10h]
0x18000af4c  lea     r8, [rbp+57h+var_90]
0x18000af50  mov     [rbp+57h+var_90], eax
0x18000af53  xorps   xmm0, xmm0
0x18000af56  mov     eax, dword ptr [rbp+57h+var_40+8]
0x18000af59  mov     edx, 2
0x18000af5e  movups  [rbp+57h+var_7C], xmm0
0x18000af62  movups  [rbp+57h+var_7C+0Ch], xmm0
0x18000af66  mov     dword ptr [rbp+57h+var_7C+0Ch], 10h
0x18000af6d  movups  [rbp+57h+var_8C], xmm0
0x18000af71  mov     dword ptr [rbp+57h+var_8C+4], eax
0x18000af74  mov     eax, [rsi+14h]
0x18000af77  mov     dword ptr [rbp+57h+var_7C+4], eax
0x18000af7a  lea     rax, [rbp+57h+var_30+8]
0x18000af7e  mov     [rbp+57h+var_68], rax
0x18000af82  mov     rax, [rcx]
0x18000af85  mov     rax, [rax+28h]
0x18000af89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8e  mov     edi, eax
0x18000af90  test    eax, eax
0x18000af92  jns     short loc_18000AFCC
0x18000af94  mov     r9d, 0A13h
0x18000af9a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000afa1  mov     edx, 1
0x18000afa6  mov     ecx, eax
0x18000afa8  call    Log_HREvent
0x18000afad  jmp     short loc_18000AFCF
0x18000afaf  mov     rax, [rcx]
0x18000afb2  mov     rax, [rax+80h]
0x18000afb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbe  mov     edi, eax
0x18000afc0  test    eax, eax
0x18000afc2  jns     short loc_18000AFCC
0x18000afc4  mov     r9d, 0A1Bh
0x18000afca  jmp     short loc_18000AF9A
0x18000afcc  mov     edi, r14d
0x18000afcf  lea     rcx, [rbp+57h+var_A0]
0x18000afd3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000afd8  mov     eax, edi
0x18000afda  mov     rcx, [rbp+57h+var_18]
0x18000afde  xor     rcx, rsp; StackCookie
0x18000afe1  call    __security_check_cookie
0x18000afe6  lea     r11, [rsp+0E0h+var_10]
0x18000afee  mov     rbx, [r11+20h]
0x18000aff2  mov     rsi, [r11+38h]
0x18000aff6  mov     rsp, r11
0x18000aff9  pop     r14
0x18000affb  pop     rdi
0x18000affc  pop     rbp
0x18000affd  retn
```
