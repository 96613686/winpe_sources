# sub_1800EFB7C

- ea: `0x1800efb7c`
- end: `0x1800f0081`
- name: `sub_1800EFB7C`
- size: `1285`
- prototype: `__int64 __fastcall(__int64, __int64, LPVOID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800f0284`

## callees

- `0x1800048f0`
- `0x18001916c`
- `0x18001abf0`
- `0x18001d0f4`
- `0x180020dcc`
- `0x180025a94`
- `0x180028810`
- `0x18002b4a4`
- `0x180038800`
- `0x180038b44`
- `0x1800efb7c`
- `0x1800f176c`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800efeb5`
- `ole32!CoCreateInstance` at `0x1800efeb5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800efd1c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800efd1c`

## string_xrefs

- `0x1800efc3b`: `CustomActionsManager::CreateDispatchInstance::GetRegInfo failed for custom action name: %1%. Error: E_FAIL`
- `0x1800efd65`: `CustomActionsManager: CLSIDFromProgID failed for ProgId: %1%. Error: %2%`
- `0x1800efeff`: `CustomActionsManager: Unable to create instance of %1% (%2%).  Error: %3%`

## pseudocode

```c
__int64 __fastcall sub_1800EFB7C(__int64 a1, __int64 a2, LPVOID *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  const OLECHAR *v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rbx
  unsigned int v25; // ebx
  __int128 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h]
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h]
  _BYTE v33[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[272]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v35[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  HRESULT v36; // [rsp+2D0h] [rbp+1D0h] BYREF
  LPCOLESTR lpszProgID[2]; // [rsp+2D8h] [rbp+1D8h] BYREF
  __m128i si128; // [rsp+2E8h] [rbp+1E8h]
  CLSID clsid; // [rsp+2F8h] [rbp+1F8h] BYREF

  v36 = 0;
  *(_OWORD *)lpszProgID = 0;
  si128 = _mm_load_si128((const __m128i *)&xmmword_1801685F0);
  LOWORD(lpszProgID[0]) = 0;
  if ( !(unsigned __int8)sub_1800F176C(a1 + 24, a2, lpszProgID) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
    {
      v5 = sub_180025A94();
      sub_180025A94();
      v29 = 0;
      v30 = 0;
      sub_18001916C(
        &v29,
        L"CustomActionsManager::CreateDispatchInstance::GetRegInfo failed for custom action name: %1%. Error: E_FAIL",
        106);
      v7 = sub_180038B44(v6, v34, &v29);
      *(_QWORD *)&v27 = a2;
      *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
      *(_QWORD *)&v28 = sub_180018450;
      v8 = sub_18001ABF0(v7, &v27);
      v27 = 0;
      v28 = 0;
      sub_18001916C(&v27, L"CaCore", 6);
      sub_180038800(v5, 1, &v27, v8);
      sub_180028810(&v27);
      sub_180020DCC(v34);
      sub_180028810(&v29);
    }
    v36 = -2147467259;
  }
  clsid = 0;
  if ( v36 >= 0 )
  {
    v9 = (const OLECHAR *)lpszProgID;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = lpszProgID[0];
    v36 = CLSIDFromProgID(v9, &clsid);
    if ( v36 < 0 && (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
    {
      v10 = sub_180025A94();
      sub_180025A94();
      v31 = 0;
      v32 = 0;
      sub_18001916C(&v31, L"CustomActionsManager: CLSIDFromProgID failed for ProgId: %1%. Error: %2%", 72);
      v12 = sub_180038B44(v11, v35, &v31);
      *(_QWORD *)&v27 = a2;
      *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
      *(_QWORD *)&v28 = sub_180018450;
      v13 = sub_18001ABF0(v12, &v27);
      v14 = sub_18001D0F4(v34, L"0x%02x");
      *(_QWORD *)&v27 = &v36;
      *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
      *(_QWORD *)&v28 = sub_18001AB60;
      v15 = sub_18001ABF0(v14, &v27);
      *(_QWORD *)&v27 = sub_18002B4A4(v15, v33);
      *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
      *(_QWORD *)&v28 = sub_180018450;
      v16 = sub_18001ABF0(v13, &v27);
      v29 = 0;
      v30 = 0;
      sub_18001916C(&v29, L"CaCore", 6);
      sub_180038800(v10, 1, &v29, v16);
      sub_180028810(&v29);
      sub_180028810(v33);
      sub_180020DCC(v34);
      sub_180020DCC(v35);
      sub_180028810(&v31);
    }
    if ( v36 >= 0 )
    {
      v36 = CoCreateInstance(&clsid, 0, 1u, &stru_180160C78, a3);
      if ( v36 < 0 && (*(_BYTE *)(*(_QWORD *)sub_180025A94() + 32LL) & 1) != 0 )
      {
        v17 = sub_180025A94();
        sub_180025A94();
        v29 = 0;
        v30 = 0;
        sub_18001916C(&v29, L"CustomActionsManager: Unable to create instance of %1% (%2%).  Error: %3%", 73);
        v19 = sub_180038B44(v18, v34, &v29);
        *(_QWORD *)&v27 = a2;
        *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
        *(_QWORD *)&v28 = sub_180018450;
        v20 = sub_18001ABF0(v19, &v27);
        *(_QWORD *)&v27 = lpszProgID;
        *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
        *(_QWORD *)&v28 = sub_180018450;
        v21 = sub_18001ABF0(v20, &v27);
        v22 = sub_18001D0F4(v35, L"0x%02x");
        *(_QWORD *)&v27 = &v36;
        *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
        *(_QWORD *)&v28 = sub_18001AB60;
        v23 = sub_18001ABF0(v22, &v27);
        *(_QWORD *)&v27 = sub_18002B4A4(v23, v33);
        *((_QWORD *)&v27 + 1) = guard_check_icall_nop;
        *(_QWORD *)&v28 = sub_180018450;
        v24 = sub_18001ABF0(v21, &v27);
        v31 = 0;
        v32 = 0;
        sub_18001916C(&v31, L"CaCore", 6);
        sub_180038800(v17, 1, &v31, v24);
        sub_180028810(&v31);
        sub_180028810(v33);
        sub_180020DCC(v35);
        sub_180020DCC(v34);
        sub_180028810(&v29);
      }
    }
  }
  v25 = v36;
  sub_180028810(lpszProgID);
  return v25;
}

```

## disassembly

```asm
0x1800efb7c  push    rbp
0x1800efb7e  push    rbx
0x1800efb7f  push    rsi
0x1800efb80  push    rdi
0x1800efb81  push    r12
0x1800efb83  push    r13
0x1800efb85  push    r14
0x1800efb87  lea     rbp, [rsp-210h]
0x1800efb8f  sub     rsp, 310h
0x1800efb96  mov     rax, cs:__security_cookie
0x1800efb9d  xor     rax, rsp
0x1800efba0  mov     [rbp+240h+var_38], rax
0x1800efba7  mov     r14, r8
0x1800efbaa  mov     rsi, rdx
0x1800efbad  mov     [rbp+240h+var_70], 0
0x1800efbb7  xorps   xmm0, xmm0
0x1800efbba  movups  xmmword ptr [rbp+240h+lpszProgID], xmm0
0x1800efbc1  movdqa  xmm1, cs:xmmword_1801685F0
0x1800efbc9  movdqu  [rbp+240h+var_58], xmm1
0x1800efbd1  xor     eax, eax
0x1800efbd3  mov     word ptr [rbp+240h+lpszProgID], ax
0x1800efbda  add     rcx, 18h
0x1800efbde  lea     r8, [rbp+240h+lpszProgID]
0x1800efbe5  call    sub_1800F176C
0x1800efbea  mov     r12d, 1
0x1800efbf0  lea     r13, _guard_check_icall_nop
0x1800efbf7  lea     rbx, sub_180018450
0x1800efbfe  test    al, al
0x1800efc00  jnz     loc_1800EFCE7
0x1800efc06  call    sub_180025A94
0x1800efc0b  mov     rax, [rax]
0x1800efc0e  test    [rax+20h], r12b
0x1800efc12  jbe     loc_1800EFCDD
0x1800efc18  call    sub_180025A94
0x1800efc1d  mov     rdi, rax
0x1800efc20  call    sub_180025A94
0x1800efc25  xorps   xmm0, xmm0
0x1800efc28  movups  [rsp+340h+var_2F0], xmm0
0x1800efc2d  xorps   xmm1, xmm1
0x1800efc30  movdqu  [rsp+340h+var_2E0], xmm1
0x1800efc36  lea     r8d, [r12+69h]
0x1800efc3b  lea     rdx, aCustomactionsm; "CustomActionsManager::CreateDispatchIns"...
0x1800efc42  lea     rcx, [rsp+340h+var_2F0]
0x1800efc47  call    sub_18001916C
0x1800efc4c  nop
0x1800efc4d  lea     r8, [rsp+340h+var_2F0]
0x1800efc52  lea     rdx, [rbp+240h+var_290]
0x1800efc56  call    sub_180038B44
0x1800efc5b  nop
0x1800efc5c  mov     qword ptr [rsp+340h+var_310], rsi
0x1800efc61  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800efc66  mov     qword ptr [rsp+340h+var_300], rbx
0x1800efc6b  lea     rdx, [rsp+340h+var_310]
0x1800efc70  mov     rcx, rax
0x1800efc73  call    sub_18001ABF0
0x1800efc78  mov     rbx, rax
0x1800efc7b  xorps   xmm0, xmm0
0x1800efc7e  movups  [rsp+340h+var_310], xmm0
0x1800efc83  xorps   xmm1, xmm1
0x1800efc86  movdqu  [rsp+340h+var_300], xmm1
0x1800efc8c  lea     r8d, [r12+5]
0x1800efc91  lea     rdx, aCacore; "CaCore"
0x1800efc98  lea     rcx, [rsp+340h+var_310]
0x1800efc9d  call    sub_18001916C
0x1800efca2  nop
0x1800efca3  mov     r9, rbx
0x1800efca6  lea     r8, [rsp+340h+var_310]
0x1800efcab  mov     edx, r12d
0x1800efcae  mov     rcx, rdi
0x1800efcb1  call    sub_180038800
0x1800efcb6  nop
0x1800efcb7  lea     rcx, [rsp+340h+var_310]
0x1800efcbc  call    sub_180028810
0x1800efcc1  nop
0x1800efcc2  lea     rcx, [rbp+240h+var_290]
0x1800efcc6  call    sub_180020DCC
0x1800efccb  nop
0x1800efccc  lea     rcx, [rsp+340h+var_2F0]
0x1800efcd1  call    sub_180028810
0x1800efcd6  lea     rbx, sub_180018450
0x1800efcdd  mov     [rbp+240h+var_70], 80004005h
0x1800efce7  xorps   xmm0, xmm0
0x1800efcea  movups  [rbp+240h+clsid], xmm0
0x1800efcf1  cmp     [rbp+240h+var_70], 0
0x1800efcf8  jl      loc_1800F004C
0x1800efcfe  lea     rcx, [rbp+240h+lpszProgID]
0x1800efd05  cmp     qword ptr [rbp+240h+var_58+8], 7
0x1800efd0d  cmova   rcx, [rbp+240h+lpszProgID]; lpszProgID
0x1800efd15  lea     rdx, [rbp+240h+clsid]; lpclsid
0x1800efd1c  call    cs:CLSIDFromProgID
0x1800efd22  mov     [rbp+240h+var_70], eax
0x1800efd28  test    eax, eax
0x1800efd2a  jns     loc_1800EFE90
0x1800efd30  call    sub_180025A94
0x1800efd35  mov     rax, [rax]
0x1800efd38  test    [rax+20h], r12b
0x1800efd3c  jbe     loc_1800EFE90
0x1800efd42  call    sub_180025A94
0x1800efd47  mov     rdi, rax
0x1800efd4a  call    sub_180025A94
0x1800efd4f  xorps   xmm0, xmm0
0x1800efd52  movups  [rsp+340h+var_2D0], xmm0
0x1800efd57  xorps   xmm1, xmm1
0x1800efd5a  movdqu  [rbp+240h+var_2C0], xmm1
0x1800efd5f  mov     r8d, 48h ; 'H'
0x1800efd65  lea     rdx, aCustomactionsm_0; "CustomActionsManager: CLSIDFromProgID f"...
0x1800efd6c  lea     rcx, [rsp+340h+var_2D0]
0x1800efd71  call    sub_18001916C
0x1800efd76  nop
0x1800efd77  lea     r8, [rsp+340h+var_2D0]
0x1800efd7c  lea     rdx, [rbp+240h+var_180]
0x1800efd83  call    sub_180038B44
0x1800efd88  nop
0x1800efd89  mov     qword ptr [rsp+340h+var_310], rsi
0x1800efd8e  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800efd93  mov     qword ptr [rsp+340h+var_300], rbx
0x1800efd98  lea     rdx, [rsp+340h+var_310]
0x1800efd9d  mov     rcx, rax
0x1800efda0  call    sub_18001ABF0
0x1800efda5  mov     rbx, rax
0x1800efda8  lea     rdx, a0x02x; "0x%02x"
0x1800efdaf  lea     rcx, [rbp+240h+var_290]
0x1800efdb3  call    sub_18001D0F4
0x1800efdb8  nop
0x1800efdb9  lea     rcx, [rbp+240h+var_70]
0x1800efdc0  mov     qword ptr [rsp+340h+var_310], rcx
0x1800efdc5  lea     rcx, _guard_check_icall_nop
0x1800efdcc  mov     qword ptr [rsp+340h+var_310+8], rcx
0x1800efdd1  lea     rcx, sub_18001AB60
0x1800efdd8  mov     qword ptr [rsp+340h+var_300], rcx
0x1800efddd  lea     rdx, [rsp+340h+var_310]
0x1800efde2  mov     rcx, rax
0x1800efde5  call    sub_18001ABF0
0x1800efdea  lea     rdx, [rbp+240h+var_2B0]
0x1800efdee  mov     rcx, rax
0x1800efdf1  call    sub_18002B4A4
0x1800efdf6  nop
0x1800efdf7  mov     qword ptr [rsp+340h+var_310], rax
0x1800efdfc  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800efe01  lea     rax, sub_180018450
0x1800efe08  mov     qword ptr [rsp+340h+var_300], rax
0x1800efe0d  lea     rdx, [rsp+340h+var_310]
0x1800efe12  mov     rcx, rbx
0x1800efe15  call    sub_18001ABF0
0x1800efe1a  mov     rbx, rax
0x1800efe1d  xorps   xmm0, xmm0
0x1800efe20  movups  [rsp+340h+var_2F0], xmm0
0x1800efe25  xorps   xmm1, xmm1
0x1800efe28  movdqu  [rsp+340h+var_2E0], xmm1
0x1800efe2e  mov     r8d, 6
0x1800efe34  lea     rdx, aCacore; "CaCore"
0x1800efe3b  lea     rcx, [rsp+340h+var_2F0]
0x1800efe40  call    sub_18001916C
0x1800efe45  nop
0x1800efe46  mov     r9, rbx
0x1800efe49  lea     r8, [rsp+340h+var_2F0]
0x1800efe4e  mov     edx, r12d
0x1800efe51  mov     rcx, rdi
0x1800efe54  call    sub_180038800
0x1800efe59  nop
0x1800efe5a  lea     rcx, [rsp+340h+var_2F0]
0x1800efe5f  call    sub_180028810
0x1800efe64  nop
0x1800efe65  lea     rcx, [rbp+240h+var_2B0]
0x1800efe69  call    sub_180028810
0x1800efe6e  nop
0x1800efe6f  lea     rcx, [rbp+240h+var_290]
0x1800efe73  call    sub_180020DCC
0x1800efe78  nop
0x1800efe79  lea     rcx, [rbp+240h+var_180]
0x1800efe80  call    sub_180020DCC
0x1800efe85  nop
0x1800efe86  lea     rcx, [rsp+340h+var_2D0]
0x1800efe8b  call    sub_180028810
0x1800efe90  cmp     [rbp+240h+var_70], 0
0x1800efe97  jl      loc_1800F004C
0x1800efe9d  mov     [rsp+340h+ppv], r14; ppv
0x1800efea2  lea     r9, stru_180160C78; riid
0x1800efea9  mov     r8d, r12d; dwClsContext
0x1800efeac  xor     edx, edx; pUnkOuter
0x1800efeae  lea     rcx, [rbp+240h+clsid]; rclsid
0x1800efeb5  call    cs:CoCreateInstance
0x1800efebb  mov     [rbp+240h+var_70], eax
0x1800efec1  test    eax, eax
0x1800efec3  jns     loc_1800F004C
0x1800efec9  call    sub_180025A94
0x1800efece  mov     rax, [rax]
0x1800efed1  test    [rax+20h], r12b
0x1800efed5  jbe     loc_1800F004C
0x1800efedb  call    sub_180025A94
0x1800efee0  mov     rdi, rax
0x1800efee3  call    sub_180025A94
0x1800efee8  xorps   xmm0, xmm0
0x1800efeeb  movups  [rsp+340h+var_2F0], xmm0
0x1800efef0  xorps   xmm1, xmm1
0x1800efef3  movdqu  [rsp+340h+var_2E0], xmm1
0x1800efef9  mov     r8d, 49h ; 'I'
0x1800efeff  lea     rdx, aCustomactionsm_1; "CustomActionsManager: Unable to create "...
0x1800eff06  lea     rcx, [rsp+340h+var_2F0]
0x1800eff0b  call    sub_18001916C
0x1800eff10  nop
0x1800eff11  lea     r8, [rsp+340h+var_2F0]
0x1800eff16  lea     rdx, [rbp+240h+var_290]
0x1800eff1a  call    sub_180038B44
0x1800eff1f  nop
0x1800eff20  mov     qword ptr [rsp+340h+var_310], rsi
0x1800eff25  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800eff2a  lea     rsi, sub_180018450
0x1800eff31  mov     qword ptr [rsp+340h+var_300], rsi
0x1800eff36  lea     rdx, [rsp+340h+var_310]
0x1800eff3b  mov     rcx, rax
0x1800eff3e  call    sub_18001ABF0
0x1800eff43  lea     rcx, [rbp+240h+lpszProgID]
0x1800eff4a  mov     qword ptr [rsp+340h+var_310], rcx
0x1800eff4f  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800eff54  mov     qword ptr [rsp+340h+var_300], rsi
0x1800eff59  lea     rdx, [rsp+340h+var_310]
0x1800eff5e  mov     rcx, rax
0x1800eff61  call    sub_18001ABF0
0x1800eff66  mov     rbx, rax
0x1800eff69  lea     rdx, a0x02x; "0x%02x"
0x1800eff70  lea     rcx, [rbp+240h+var_180]
0x1800eff77  call    sub_18001D0F4
0x1800eff7c  nop
0x1800eff7d  lea     rcx, [rbp+240h+var_70]
0x1800eff84  mov     qword ptr [rsp+340h+var_310], rcx
0x1800eff89  lea     rcx, _guard_check_icall_nop
0x1800eff90  mov     qword ptr [rsp+340h+var_310+8], rcx
0x1800eff95  lea     rcx, sub_18001AB60
0x1800eff9c  mov     qword ptr [rsp+340h+var_300], rcx
0x1800effa1  lea     rdx, [rsp+340h+var_310]
0x1800effa6  mov     rcx, rax
0x1800effa9  call    sub_18001ABF0
0x1800effae  lea     rdx, [rbp+240h+var_2B0]
0x1800effb2  mov     rcx, rax
0x1800effb5  call    sub_18002B4A4
0x1800effba  nop
0x1800effbb  mov     qword ptr [rsp+340h+var_310], rax
0x1800effc0  mov     qword ptr [rsp+340h+var_310+8], r13
0x1800effc5  mov     qword ptr [rsp+340h+var_300], rsi
0x1800effca  lea     rdx, [rsp+340h+var_310]
0x1800effcf  mov     rcx, rbx
0x1800effd2  call    sub_18001ABF0
0x1800effd7  mov     rbx, rax
0x1800effda  xorps   xmm0, xmm0
0x1800effdd  movups  [rsp+340h+var_2D0], xmm0
0x1800effe2  xorps   xmm1, xmm1
0x1800effe5  movdqu  [rbp+240h+var_2C0], xmm1
0x1800effea  mov     r8d, 6
0x1800efff0  lea     rdx, aCacore; "CaCore"
0x1800efff7  lea     rcx, [rsp+340h+var_2D0]
0x1800efffc  call    sub_18001916C
0x1800f0001  nop
0x1800f0002  mov     r9, rbx
0x1800f0005  lea     r8, [rsp+340h+var_2D0]
0x1800f000a  mov     edx, r12d
0x1800f000d  mov     rcx, rdi
0x1800f0010  call    sub_180038800
0x1800f0015  nop
0x1800f0016  lea     rcx, [rsp+340h+var_2D0]
0x1800f001b  call    sub_180028810
0x1800f0020  nop
0x1800f0021  lea     rcx, [rbp+240h+var_2B0]
0x1800f0025  call    sub_180028810
0x1800f002a  nop
0x1800f002b  lea     rcx, [rbp+240h+var_180]
0x1800f0032  call    sub_180020DCC
0x1800f0037  nop
0x1800f0038  lea     rcx, [rbp+240h+var_290]
0x1800f003c  call    sub_180020DCC
0x1800f0041  nop
0x1800f0042  lea     rcx, [rsp+340h+var_2F0]
0x1800f0047  call    sub_180028810
0x1800f004c  mov     ebx, [rbp+240h+var_70]
0x1800f0052  lea     rcx, [rbp+240h+lpszProgID]
0x1800f0059  call    sub_180028810
0x1800f005e  mov     eax, ebx
0x1800f0060  mov     rcx, [rbp+240h+var_38]
0x1800f0067  xor     rcx, rsp; StackCookie
0x1800f006a  call    __security_check_cookie
0x1800f006f  add     rsp, 310h
0x1800f0076  pop     r14
0x1800f0078  pop     r13
0x1800f007a  pop     r12
0x1800f007c  pop     rdi
0x1800f007d  pop     rsi
0x1800f007e  pop     rbx
0x1800f007f  pop     rbp
0x1800f0080  retn
```
