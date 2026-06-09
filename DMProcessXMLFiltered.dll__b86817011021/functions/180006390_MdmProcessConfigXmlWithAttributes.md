# MdmProcessConfigXmlWithAttributes

- ea: `0x180006390`
- end: `0x18000698e`
- name: `MdmProcessConfigXmlWithAttributes`
- size: `1534`
- prototype: `__int64 __fastcall(__int64, unsigned int, OLECHAR *, BSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003ab8`
- `0x180006260`

## callees

- `0x180005224`
- `0x180006390`
- `0x180008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006429`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006444`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006464`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006429`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006444`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180006464`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000655d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800065e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800066a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006710`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000679a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000681d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800068e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000694c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006964`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000655d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800065e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800066a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006710`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000679a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000681d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800068e2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000694c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006964`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006487`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006487`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006513`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000674f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006513`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000674f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000666a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000667a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006910`
- `OLEAUT32!__imp_SysFreeString` at `0x180006920`
- `OLEAUT32!__imp_SysFreeString` at `0x18000666a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000667a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066e4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800068b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006910`
- `OLEAUT32!__imp_SysFreeString` at `0x180006920`

## string_xrefs

- `0x1800063d4`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x18000649f`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x18000652b`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x1800065ad`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x180006653`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x180006767`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x1800067ea`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x18000688f`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`

## pseudocode

```c
__int64 __fastcall MdmProcessConfigXmlWithAttributes(__int64 a1, unsigned int a2, OLECHAR *a3, BSTR *a4)
{
  BSTR *v4; // r12
  int v8; // r13d
  unsigned int v9; // r15d
  __int64 v10; // r12
  HRESULT v11; // eax
  unsigned int v12; // r15d
  HRESULT v13; // eax
  unsigned int v14; // r15d
  int v15; // eax
  unsigned int v16; // edi
  int v17; // eax
  unsigned int v18; // edi
  OLECHAR *v19; // rcx
  unsigned int v20; // edi
  HRESULT v21; // eax
  unsigned int v22; // r15d
  int v23; // eax
  unsigned int v24; // edi
  __int64 v25; // r8
  int v26; // eax
  unsigned int v27; // edi
  OLECHAR *v28; // rcx
  unsigned int v29; // edi
  int ppv; // [rsp+20h] [rbp-A8h]
  int ppva; // [rsp+20h] [rbp-A8h]
  int ppvb; // [rsp+20h] [rbp-A8h]
  int v33; // [rsp+30h] [rbp-98h] BYREF
  LPVOID v34; // [rsp+38h] [rbp-90h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-88h] BYREF
  BSTR v36; // [rsp+50h] [rbp-78h]
  int *v37; // [rsp+58h] [rbp-70h]
  char v38; // [rsp+60h] [rbp-68h]
  BSTR v39[2]; // [rsp+68h] [rbp-60h] BYREF
  BSTR v40[2]; // [rsp+78h] [rbp-50h]
  __int128 v41; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a4;
  v33 = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
  if ( !a2 && a3 || !a3 && a2 )
    return 2147942487LL;
  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    v10 = 0;
    do
    {
      v34 = (LPVOID)(16 * v10);
      if ( !(unsigned int)_o__wcsicmp(L"OMADM::DpuRunningMode", *(_QWORD *)&a3[8 * v10]) )
      {
        if ( (unsigned int)_o__wcsicmp(*(_QWORD *)((char *)a3 + (_QWORD)v34 + 8), L"INPROC") )
        {
          if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)((char *)a3 + (_QWORD)v34 + 8), L"OUTPROC") )
            v8 = 1;
        }
        else
        {
          v8 = 0;
        }
      }
      ++v9;
      ++v10;
    }
    while ( v9 < a2 );
    v4 = a4;
  }
  v11 = CoInitializeEx(0, 0);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v33 = 1;
    v37 = &v33;
    v38 = 1;
    v34 = 0;
    if ( v8 )
    {
      v41 = 0;
      *(_OWORD *)v39 = 0;
      v40[0] = 0;
      v21 = CoCreateInstance(
              &GUID_417976b7_917d_4f1e_8f14_c18fccb0b3a8,
              0,
              0x10004u,
              &GUID_b0fdb0eb_eff0_4205_8a17_4911b5745780,
              &v34);
      v22 = v21;
      if ( v21 >= 0 )
      {
        if ( a2 && a3 )
        {
          *((_QWORD *)&v41 + 1) = a3;
          LODWORD(v41) = a2;
        }
        v23 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v34 + 24LL))(v34, &v41);
        v24 = v23;
        if ( v23 >= 0 )
        {
          v25 = -1;
          do
            ++v25;
          while ( *(_WORD *)(a1 + 2 * v25) );
          (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v34 + 32LL))(
            v34,
            a1,
            (unsigned int)(2 * v25 + 2));
          bstrString[0] = (BSTR)v39;
          LOBYTE(bstrString[1]) = 1;
          v26 = (*(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)v34 + 40LL))(v34, v39);
          v27 = v26;
          if ( v26 >= 0 )
          {
            if ( v4 )
            {
              *v4 = v39[0];
              v28 = 0;
              v39[0] = 0;
            }
            else
            {
              v28 = v39[0];
            }
            v29 = (unsigned int)v39[1];
            SysFreeString(v28);
            v39[0] = 0;
            SysFreeString(v40[0]);
            v40[0] = 0;
            if ( v34 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
            v38 = 0;
            if ( v33 )
              CoUninitialize();
            return v29;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x93,
              (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
              (const char *)(unsigned int)v26,
              ppvb);
            SysFreeString(v39[0]);
            v39[0] = 0;
            SysFreeString(v40[0]);
            v40[0] = 0;
            if ( v34 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
            v38 = 0;
            if ( v33 )
              CoUninitialize();
            return v27;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8A,
            (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
            (const char *)(unsigned int)v23,
            ppvb);
          if ( v34 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
          v38 = 0;
          if ( v33 )
            CoUninitialize();
          return v24;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
          (const char *)(unsigned int)v21,
          ppvb);
        if ( v34 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
        v38 = 0;
        if ( v33 )
          CoUninitialize();
        return v22;
      }
    }
    else
    {
      *(_OWORD *)v39 = 0;
      *(_OWORD *)v40 = 0;
      *(_OWORD *)bstrString = 0;
      v36 = 0;
      v13 = CoCreateInstance(
              &GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401,
              0,
              1u,
              &GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd,
              &v34);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( a2 && a3 )
        {
          v40[1] = a3;
          LODWORD(v40[0]) = a2;
        }
        v15 = (*(__int64 (__fastcall **)(LPVOID, BSTR *, __int64))(*(_QWORD *)v34 + 24LL))(v34, v39, 32);
        v16 = v15;
        if ( v15 >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 32LL))(v34, a1, 0, 0);
          *(_QWORD *)&v41 = bstrString;
          BYTE8(v41) = 1;
          v17 = (*(__int64 (__fastcall **)(LPVOID, BSTR *, __int64))(*(_QWORD *)v34 + 40LL))(v34, bstrString, 24);
          v18 = v17;
          if ( v17 >= 0 )
          {
            if ( v4 )
            {
              *v4 = bstrString[0];
              v19 = 0;
              bstrString[0] = 0;
            }
            else
            {
              v19 = bstrString[0];
            }
            v20 = (unsigned int)bstrString[1];
            SysFreeString(v19);
            bstrString[0] = 0;
            SysFreeString(v36);
            v36 = 0;
            if ( v34 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
            v38 = 0;
            if ( v33 )
              CoUninitialize();
            return v20;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6A,
              (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
              (const char *)(unsigned int)v17,
              0);
            SysFreeString(bstrString[0]);
            bstrString[0] = 0;
            SysFreeString(v36);
            v36 = 0;
            if ( v34 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
            v38 = 0;
            if ( v33 )
              CoUninitialize();
            return v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5C,
            (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
            (const char *)(unsigned int)v15,
            ppva);
          if ( v34 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
          v38 = 0;
          if ( v33 )
            CoUninitialize();
          return v16;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
          (const char *)(unsigned int)v13,
          ppva);
        if ( v34 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
        v38 = 0;
        if ( v33 )
          CoUninitialize();
        return v14;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      (const char *)(unsigned int)v11,
      ppv);
    return v12;
  }
}

```

## disassembly

```asm
0x180006390  mov     rax, rsp
0x180006393  mov     [rax+10h], rbx
0x180006397  mov     [rax+18h], rsi
0x18000639b  mov     [rax+20h], r9
0x18000639f  mov     [rax+8], rcx
0x1800063a3  push    rdi
0x1800063a4  push    r12
0x1800063a6  push    r13
0x1800063a8  push    r14
0x1800063aa  push    r15
0x1800063ac  sub     rsp, 0A0h
0x1800063b3  mov     r12, r9
0x1800063b6  mov     rsi, r8
0x1800063b9  mov     edi, edx
0x1800063bb  xor     ebx, ebx
0x1800063bd  mov     [rsp+0C8h+var_98], ebx
0x1800063c1  test    rcx, rcx
0x1800063c4  jnz     short loc_1800063ED
0x1800063c6  mov     rcx, [rsp+0C8h]; this
0x1800063ce  mov     r9d, 80070057h; char *
0x1800063d4  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800063db  lea     edx, [rbx+1Eh]; void *
0x1800063de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063e3  mov     eax, 80070057h
0x1800063e8  jmp     loc_180006971
0x1800063ed  test    edi, edi
0x1800063ef  jnz     short loc_1800063F6
0x1800063f1  test    rsi, rsi
0x1800063f4  jnz     short loc_1800063E3
0x1800063f6  test    rsi, rsi
0x1800063f9  jnz     short loc_1800063FF
0x1800063fb  test    edi, edi
0x1800063fd  jnz     short loc_1800063E3
0x1800063ff  mov     r13d, ebx
0x180006402  mov     r15d, ebx
0x180006405  mov     r14d, 1
0x18000640b  test    edi, edi
0x18000640d  jz      short loc_180006483
0x18000640f  mov     r12, rbx
0x180006412  mov     rax, r12
0x180006415  shl     rax, 4
0x180006419  mov     [rsp+0C8h+var_90], rax
0x18000641e  mov     rdx, [rax+rsi]
0x180006422  lea     rcx, aOmadmDpurunnin; "OMADM::DpuRunningMode"
0x180006429  call    cs:__imp__o__wcsicmp
0x18000642f  test    eax, eax
0x180006431  jnz     short loc_180006470
0x180006433  lea     rdx, aInproc; "INPROC"
0x18000643a  mov     rcx, [rsp+0C8h+var_90]
0x18000643f  mov     rcx, [rcx+rsi+8]
0x180006444  call    cs:__imp__o__wcsicmp
0x18000644a  test    eax, eax
0x18000644c  jnz     short loc_180006453
0x18000644e  mov     r13d, ebx
0x180006451  jmp     short loc_180006470
0x180006453  lea     rdx, aOutproc; "OUTPROC"
0x18000645a  mov     rax, [rsp+0C8h+var_90]
0x18000645f  mov     rcx, [rax+rsi+8]
0x180006464  call    cs:__imp__o__wcsicmp
0x18000646a  test    eax, eax
0x18000646c  cmovz   r13d, r14d
0x180006470  add     r15d, r14d
0x180006473  add     r12, r14
0x180006476  cmp     r15d, edi
0x180006479  jb      short loc_180006412
0x18000647b  mov     r12, [rsp+0C8h+arg_18]
0x180006483  xor     edx, edx; dwCoInit
0x180006485  xor     ecx, ecx; pvReserved
0x180006487  call    cs:__imp_CoInitializeEx
0x18000648d  mov     r15d, eax
0x180006490  test    eax, eax
0x180006492  jns     short loc_1800064B8
0x180006494  mov     rcx, [rsp+0C8h]; this
0x18000649c  mov     r9d, eax; char *
0x18000649f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800064a6  mov     edx, 39h ; '9'; void *
0x1800064ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064b0  mov     eax, r15d
0x1800064b3  jmp     loc_180006971
0x1800064b8  mov     [rsp+0C8h+var_98], r14d
0x1800064bd  lea     rax, [rsp+0C8h+var_98]
0x1800064c2  mov     [rsp+0C8h+var_70], rax
0x1800064c7  mov     [rsp+0C8h+var_68], r14b
0x1800064cc  xorps   xmm0, xmm0
0x1800064cf  xorps   xmm1, xmm1
0x1800064d2  xor     eax, eax
0x1800064d4  mov     [rsp+0C8h+var_90], rbx
0x1800064d9  test    r13d, r13d
0x1800064dc  jnz     loc_18000671D
0x1800064e2  movups  xmmword ptr [rsp+0C8h+var_60], xmm0
0x1800064e7  movups  xmmword ptr [rsp+0C8h+var_50], xmm0
0x1800064ec  movups  xmmword ptr [rsp+0C8h+bstrString], xmm1
0x1800064f1  mov     [rsp+0C8h+var_78], rax
0x1800064f6  lea     rax, [rsp+0C8h+var_90]
0x1800064fb  mov     qword ptr [rsp+0C8h+ppv], rax; int
0x180006500  lea     r9, _GUID_ed3799a5_8188_4414_b9ab_bd37f064ddcd; riid
0x180006507  mov     r8d, r14d; dwClsContext
0x18000650a  xor     edx, edx; pUnkOuter
0x18000650c  lea     rcx, _GUID_f4477ad6_6b3a_411b_9ecc_7ce89b665401; rclsid
0x180006513  call    cs:__imp_CoCreateInstance
0x180006519  mov     r15d, eax
0x18000651c  test    eax, eax
0x18000651e  jns     short loc_18000656B
0x180006520  mov     rcx, [rsp+0C8h]; this
0x180006528  mov     r9d, eax; char *
0x18000652b  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x180006532  lea     edx, [r13+50h]; void *
0x180006536  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000653b  nop
0x18000653c  mov     rcx, [rsp+0C8h+var_90]
0x180006541  test    rcx, rcx
0x180006544  jz      short loc_180006553
0x180006546  mov     rax, [rcx]
0x180006549  mov     rax, [rax+10h]
0x18000654d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006552  nop
0x180006553  mov     [rsp+0C8h+var_68], bl
0x180006557  cmp     [rsp+0C8h+var_98], ebx
0x18000655b  jz      short loc_180006563
0x18000655d  call    cs:__imp_CoUninitialize
0x180006563  mov     eax, r15d
0x180006566  jmp     loc_180006971
0x18000656b  test    edi, edi
0x18000656d  jz      short loc_180006580
0x18000656f  test    rsi, rsi
0x180006572  jz      short loc_180006580
0x180006574  mov     [rsp+0C8h+var_50+8], rsi
0x18000657c  mov     dword ptr [rsp+0C8h+var_50], edi
0x180006580  mov     rcx, [rsp+0C8h+var_90]
0x180006585  mov     rax, [rcx]
0x180006588  mov     r8d, 20h ; ' '
0x18000658e  lea     rdx, [rsp+0C8h+var_60]
0x180006593  mov     rax, [rax+18h]
0x180006597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000659c  mov     edi, eax
0x18000659e  test    eax, eax
0x1800065a0  jns     short loc_1800065ED
0x1800065a2  mov     rcx, [rsp+0C8h]; this
0x1800065aa  mov     r9d, eax; char *
0x1800065ad  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800065b4  mov     edx, 5Ch ; '\'; void *
0x1800065b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065be  nop
0x1800065bf  mov     rcx, [rsp+0C8h+var_90]
0x1800065c4  test    rcx, rcx
0x1800065c7  jz      short loc_1800065D6
0x1800065c9  mov     rax, [rcx]
0x1800065cc  mov     rax, [rax+10h]
0x1800065d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d5  nop
0x1800065d6  mov     [rsp+0C8h+var_68], bl
0x1800065da  cmp     [rsp+0C8h+var_98], ebx
0x1800065de  jz      short loc_1800065E6
0x1800065e0  call    cs:__imp_CoUninitialize
0x1800065e6  mov     eax, edi
0x1800065e8  jmp     loc_180006971
0x1800065ed  mov     rcx, [rsp+0C8h+var_90]
0x1800065f2  mov     rax, [rcx]
0x1800065f5  mov     qword ptr [rsp+0C8h+ppv], rbx; int
0x1800065fa  xor     r9d, r9d
0x1800065fd  xor     r8d, r8d
0x180006600  mov     rdx, [rsp+0C8h+arg_0]
0x180006608  mov     rax, [rax+20h]
0x18000660c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006611  lea     rax, [rsp+0C8h+bstrString]
0x180006616  mov     qword ptr [rsp+0C8h+var_40], rax
0x18000661e  mov     byte ptr [rsp+0C8h+var_40+8], r14b
0x180006626  mov     rcx, [rsp+0C8h+var_90]
0x18000662b  mov     rax, [rcx]
0x18000662e  mov     r8d, 18h
0x180006634  lea     rdx, [rsp+0C8h+bstrString]
0x180006639  mov     rax, [rax+28h]
0x18000663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006642  mov     edi, eax
0x180006644  test    eax, eax
0x180006646  jns     short loc_1800066B3
0x180006648  mov     rcx, [rsp+0C8h]; this
0x180006650  mov     r9d, eax; char *
0x180006653  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x18000665a  mov     edx, 6Ah ; 'j'; void *
0x18000665f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006664  nop
0x180006665  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x18000666a  call    cs:__imp_SysFreeString
0x180006670  mov     [rsp+0C8h+bstrString], rbx
0x180006675  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x18000667a  call    cs:__imp_SysFreeString
0x180006680  mov     [rsp+0C8h+var_78], rbx
0x180006685  mov     rcx, [rsp+0C8h+var_90]
0x18000668a  test    rcx, rcx
0x18000668d  jz      short loc_18000669C
0x18000668f  mov     rax, [rcx]
0x180006692  mov     rax, [rax+10h]
0x180006696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000669b  nop
0x18000669c  mov     [rsp+0C8h+var_68], bl
0x1800066a0  cmp     [rsp+0C8h+var_98], ebx
0x1800066a4  jz      short loc_1800066AC
0x1800066a6  call    cs:__imp_CoUninitialize
0x1800066ac  mov     eax, edi
0x1800066ae  jmp     loc_180006971
0x1800066b3  test    r12, r12
0x1800066b6  jz      short loc_1800066CB
0x1800066b8  mov     rax, [rsp+0C8h+bstrString]
0x1800066bd  mov     [r12], rax
0x1800066c1  mov     rcx, rbx
0x1800066c4  mov     [rsp+0C8h+bstrString], rbx
0x1800066c9  jmp     short loc_1800066D0
0x1800066cb  mov     rcx, [rsp+0C8h+bstrString]; bstrString
0x1800066d0  mov     edi, dword ptr [rsp+0C8h+bstrString+8]
0x1800066d4  call    cs:__imp_SysFreeString
0x1800066da  mov     [rsp+0C8h+bstrString], rbx
0x1800066df  mov     rcx, [rsp+0C8h+var_78]; bstrString
0x1800066e4  call    cs:__imp_SysFreeString
0x1800066ea  mov     [rsp+0C8h+var_78], rbx
0x1800066ef  mov     rcx, [rsp+0C8h+var_90]
0x1800066f4  test    rcx, rcx
0x1800066f7  jz      short loc_180006706
0x1800066f9  mov     rax, [rcx]
0x1800066fc  mov     rax, [rax+10h]
0x180006700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006705  nop
0x180006706  mov     [rsp+0C8h+var_68], bl
0x18000670a  cmp     [rsp+0C8h+var_98], ebx
0x18000670e  jz      short loc_180006716
0x180006710  call    cs:__imp_CoUninitialize
0x180006716  mov     eax, edi
0x180006718  jmp     loc_180006971
0x18000671d  movups  [rsp+0C8h+var_40], xmm0
0x180006725  movups  xmmword ptr [rsp+0C8h+var_60], xmm1
0x18000672a  mov     [rsp+0C8h+var_50], rax
0x18000672f  lea     rax, [rsp+0C8h+var_90]
0x180006734  mov     qword ptr [rsp+0C8h+ppv], rax; int
0x180006739  lea     r9, _GUID_b0fdb0eb_eff0_4205_8a17_4911b5745780; riid
0x180006740  xor     edx, edx; pUnkOuter
0x180006742  mov     r8d, 10004h; dwClsContext
0x180006748  lea     rcx, _GUID_417976b7_917d_4f1e_8f14_c18fccb0b3a8; rclsid
0x18000674f  call    cs:__imp_CoCreateInstance
0x180006755  mov     r15d, eax
0x180006758  test    eax, eax
0x18000675a  jns     short loc_1800067A8
0x18000675c  mov     rcx, [rsp+0C8h]; this
0x180006764  mov     r9d, eax; char *
0x180006767  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x18000676e  mov     edx, 80h; void *
0x180006773  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006778  nop
0x180006779  mov     rcx, [rsp+0C8h+var_90]
0x18000677e  test    rcx, rcx
0x180006781  jz      short loc_180006790
0x180006783  mov     rax, [rcx]
0x180006786  mov     rax, [rax+10h]
0x18000678a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000678f  nop
0x180006790  mov     [rsp+0C8h+var_68], bl
0x180006794  cmp     [rsp+0C8h+var_98], ebx
0x180006798  jz      short loc_1800067A0
0x18000679a  call    cs:__imp_CoUninitialize
0x1800067a0  mov     eax, r15d
0x1800067a3  jmp     loc_180006971
0x1800067a8  test    edi, edi
0x1800067aa  jz      short loc_1800067C0
0x1800067ac  test    rsi, rsi
0x1800067af  jz      short loc_1800067C0
0x1800067b1  mov     qword ptr [rsp+0C8h+var_40+8], rsi
0x1800067b9  mov     dword ptr [rsp+0C8h+var_40], edi
0x1800067c0  mov     rcx, [rsp+0C8h+var_90]
0x1800067c5  mov     rax, [rcx]
0x1800067c8  lea     rdx, [rsp+0C8h+var_40]
0x1800067d0  mov     rax, [rax+18h]
0x1800067d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d9  mov     edi, eax
0x1800067db  test    eax, eax
0x1800067dd  jns     short loc_18000682A
0x1800067df  mov     rcx, [rsp+0C8h]; this
0x1800067e7  mov     r9d, eax; char *
0x1800067ea  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800067f1  mov     edx, 8Ah; void *
0x1800067f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067fb  nop
0x1800067fc  mov     rcx, [rsp+0C8h+var_90]
0x180006801  test    rcx, rcx
0x180006804  jz      short loc_180006813
0x180006806  mov     rax, [rcx]
0x180006809  mov     rax, [rax+10h]
0x18000680d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006812  nop
0x180006813  mov     [rsp+0C8h+var_68], bl
0x180006817  cmp     [rsp+0C8h+var_98], ebx
0x18000681b  jz      short loc_180006823
0x18000681d  call    cs:__imp_CoUninitialize
0x180006823  mov     eax, edi
0x180006825  jmp     loc_180006971
0x18000682a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000682e  mov     rdx, [rsp+0C8h+arg_0]
0x180006836  inc     r8
0x180006839  cmp     [rdx+r8*2], bx
0x18000683e  jnz     short loc_180006836
0x180006840  mov     rcx, [rsp+0C8h+var_90]
0x180006845  mov     rax, [rcx]
  ... truncated ...
```
