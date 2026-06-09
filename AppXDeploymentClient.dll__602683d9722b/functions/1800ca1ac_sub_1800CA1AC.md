# sub_1800CA1AC

- ea: `0x1800ca1ac`
- end: `0x1800ca4d4`
- name: `sub_1800CA1AC`
- size: `808`
- prototype: `__int64 __fastcall(__int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007db54`
- `0x1800904b0`

## callees

- `0x180008a1c`
- `0x18003c1b0`
- `0x18004d4f0`
- `0x180086c48`
- `0x180089374`
- `0x1800ca1ac`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ca2cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ca2cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca243`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca28c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca3be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca448`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca452`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca4a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca4af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca243`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca28c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca3be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca3c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca448`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca452`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca4a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ca4af`

## string_xrefs

- `0x1800ca1ef`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`
- `0x1800ca22c`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`
- `0x1800ca275`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`
- `0x1800ca2de`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`
- `0x1800ca393`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`
- `0x1800ca413`: `onecore\admin\appmodel\common\scheduledtaskhelper.cpp`

## pseudocode

```c
__int64 __fastcall sub_1800CA1AC(__int64 a1, unsigned __int8 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  HRESULT v7; // eax
  __int64 v8; // rdx
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, BSTR, __int64 *); // rdi
  OLECHAR *v11; // rbx
  int v12; // eax
  int v13; // edi
  __int64 v14; // r14
  __int64 (__fastcall *v15)(__int64, BSTR, _QWORD *); // rsi
  OLECHAR *v16; // rdi
  int v17; // esi
  __int64 v18; // rdx
  BSTR bstrString; // [rsp+30h] [rbp-89h] BYREF
  BSTR v21; // [rsp+38h] [rbp-81h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v23; // [rsp+50h] [rbp-69h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h]
  __int64 v25; // [rsp+70h] [rbp-49h]
  __int128 v26; // [rsp+80h] [rbp-39h] BYREF
  __int64 v27; // [rsp+90h] [rbp-29h]
  __int128 v28; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-9h]
  __int128 v30; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v31; // [rsp+D0h] [rbp+17h]
  void *retaddr; // [rsp+118h] [rbp+5Fh]
  int v33; // [rsp+120h] [rbp+67h] BYREF
  int v34; // [rsp+124h] [rbp+6Bh]
  LPVOID ppv; // [rsp+130h] [rbp+77h] BYREF
  __int64 v36; // [rsp+138h] [rbp+7Fh] BYREF

  v34 = HIDWORD(a1);
  v25 = -2;
  v33 = -2147221008;
  v3 = sub_180089374(&v33);
  v4 = v3;
  if ( v3 < 0 )
  {
    sub_180008A1C(retaddr, 24, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v3);
    goto LABEL_22;
  }
  bstrString = 0;
  v5 = sub_18004D4F0(&bstrString, L"\\Microsoft\\Windows\\AppxDeploymentClient");
  v4 = v5;
  if ( v5 < 0 )
  {
    sub_180008A1C(retaddr, 28, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v5);
LABEL_5:
    SysFreeString(bstrString);
    goto LABEL_22;
  }
  v21 = 0;
  v6 = sub_18004D4F0(&v21, L"Pre-staged app cleanup");
  v4 = v6;
  if ( v6 < 0 )
  {
    sub_180008A1C(retaddr, 31, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v6);
LABEL_8:
    SysFreeString(v21);
    goto LABEL_5;
  }
  v23 = 0;
  LOWORD(v23) = 1;
  ppv = 0;
  sub_18003C1B0(&ppv);
  v7 = CoCreateInstance(&stru_1801384A8, 0, 1u, &stru_180138498, &ppv);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 42;
LABEL_11:
    sub_180008A1C(retaddr, v8, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v7);
    sub_18003C1B0(&ppv);
    goto LABEL_8;
  }
  v24 = 0;
  v26 = v23;
  v27 = 0;
  v28 = v23;
  v29 = 0;
  v30 = v23;
  v31 = 0;
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v30,
         &v28,
         &v26,
         &v23);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 43;
    goto LABEL_11;
  }
  v36 = 0;
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL);
  sub_18003C1B0(&v36);
  v11 = bstrString;
  v12 = v10(v9, bstrString, &v36);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v22[0] = 0;
    v14 = v36;
    v15 = *(__int64 (__fastcall **)(__int64, BSTR, _QWORD *))(*(_QWORD *)v36 + 104LL);
    sub_18003C1B0(v22);
    v16 = v21;
    v17 = v15(v14, v21, v22);
    if ( v17 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v22[0] + 88LL))(
              v22[0],
              (unsigned __int16)((a2 ^ 1) - 1));
      if ( v17 >= 0 )
      {
        sub_18003C1B0(v22);
        sub_18003C1B0(&v36);
        sub_18003C1B0(&ppv);
        SysFreeString(v16);
        SysFreeString(v11);
        v4 = 0;
        goto LABEL_22;
      }
      v18 = 50;
    }
    else
    {
      v18 = 49;
    }
    sub_180008A1C(retaddr, v18, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v17);
    sub_18003C1B0(v22);
    sub_18003C1B0(&v36);
    sub_18003C1B0(&ppv);
    SysFreeString(v16);
    SysFreeString(v11);
    v4 = v17;
  }
  else
  {
    sub_180008A1C(retaddr, 46, "onecore\\admin\\appmodel\\common\\scheduledtaskhelper.cpp", (unsigned int)v12);
    sub_18003C1B0(&v36);
    sub_18003C1B0(&ppv);
    SysFreeString(v21);
    SysFreeString(v11);
    v4 = v13;
  }
LABEL_22:
  sub_180086C48(&v33);
  return v4;
}

```

## disassembly

```asm
0x1800ca1ac  mov     [rsp-8+arg_0], rcx
0x1800ca1b1  push    rbp
0x1800ca1b2  push    rbx
0x1800ca1b3  push    rsi
0x1800ca1b4  push    rdi
0x1800ca1b5  push    r13
0x1800ca1b7  push    r14
0x1800ca1b9  push    r15
0x1800ca1bb  lea     rbp, [rsp-27h]
0x1800ca1c0  sub     rsp, 0E0h
0x1800ca1c7  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1800ca1cf  mov     r15b, dl
0x1800ca1d2  mov     dword ptr [rbp+57h+arg_0], 800401F0h
0x1800ca1d9  lea     rcx, [rbp+57h+arg_0]
0x1800ca1dd  call    sub_180089374
0x1800ca1e2  mov     ebx, eax
0x1800ca1e4  test    eax, eax
0x1800ca1e6  jns     short loc_1800CA205
0x1800ca1e8  mov     rcx, [rbp+5Fh]
0x1800ca1ec  mov     r9d, eax
0x1800ca1ef  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca1f6  mov     edx, 18h
0x1800ca1fb  call    sub_180008A1C
0x1800ca200  jmp     loc_1800CA4B7
0x1800ca205  mov     [rsp+110h+bstrString], 0
0x1800ca20e  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\AppxDeploymentCli"...
0x1800ca215  lea     rcx, [rsp+110h+bstrString]
0x1800ca21a  call    sub_18004D4F0
0x1800ca21f  mov     ebx, eax
0x1800ca221  test    eax, eax
0x1800ca223  jns     short loc_1800CA24E
0x1800ca225  mov     rcx, [rbp+5Fh]
0x1800ca229  mov     r9d, eax
0x1800ca22c  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca233  mov     edx, 1Ch
0x1800ca238  call    sub_180008A1C
0x1800ca23d  nop
0x1800ca23e  mov     rcx, [rsp+110h+bstrString]; bstrString
0x1800ca243  call    cs:__imp_SysFreeString
0x1800ca249  jmp     loc_1800CA4B7
0x1800ca24e  mov     [rsp+110h+var_D8], 0
0x1800ca257  lea     rdx, aPreStagedAppCl; "Pre-staged app cleanup"
0x1800ca25e  lea     rcx, [rsp+110h+var_D8]
0x1800ca263  call    sub_18004D4F0
0x1800ca268  mov     ebx, eax
0x1800ca26a  test    eax, eax
0x1800ca26c  jns     short loc_1800CA294
0x1800ca26e  mov     rcx, [rbp+5Fh]
0x1800ca272  mov     r9d, eax
0x1800ca275  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca27c  mov     edx, 1Fh
0x1800ca281  call    sub_180008A1C
0x1800ca286  nop
0x1800ca287  mov     rcx, [rsp+110h+var_D8]; bstrString
0x1800ca28c  call    cs:__imp_SysFreeString
0x1800ca292  jmp     short loc_1800CA23E
0x1800ca294  xorps   xmm0, xmm0
0x1800ca297  xor     edi, edi
0x1800ca299  movups  [rbp+57h+var_C0], xmm0
0x1800ca29d  lea     r13d, [rdi+1]
0x1800ca2a1  mov     word ptr [rbp+57h+var_C0], r13w
0x1800ca2a6  mov     [rbp+57h+arg_10], rdi
0x1800ca2aa  lea     rcx, [rbp+57h+arg_10]
0x1800ca2ae  call    sub_18003C1B0
0x1800ca2b3  lea     rax, [rbp+57h+arg_10]
0x1800ca2b7  mov     [rsp+110h+ppv], rax; ppv
0x1800ca2bc  lea     r9, stru_180138498; riid
0x1800ca2c3  mov     r8d, r13d; dwClsContext
0x1800ca2c6  xor     edx, edx; pUnkOuter
0x1800ca2c8  lea     rcx, stru_1801384A8; rclsid
0x1800ca2cf  call    cs:CoCreateInstance
0x1800ca2d5  mov     ebx, eax
0x1800ca2d7  test    eax, eax
0x1800ca2d9  jns     short loc_1800CA2FD
0x1800ca2db  lea     edx, [rdi+2Ah]
0x1800ca2de  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca2e5  mov     r9d, eax
0x1800ca2e8  mov     rcx, [rbp+5Fh]
0x1800ca2ec  call    sub_180008A1C
0x1800ca2f1  nop
0x1800ca2f2  lea     rcx, [rbp+57h+arg_10]
0x1800ca2f6  call    sub_18003C1B0
0x1800ca2fb  jmp     short loc_1800CA287
0x1800ca2fd  mov     rcx, [rbp+57h+arg_10]
0x1800ca301  movups  xmm1, [rbp+57h+var_C0]
0x1800ca305  movaps  [rbp+57h+var_C0], xmm1
0x1800ca309  mov     [rbp+57h+var_B0], rdi
0x1800ca30d  movaps  [rbp+57h+var_90], xmm1
0x1800ca311  mov     [rbp+57h+var_80], rdi
0x1800ca315  movaps  [rbp+57h+var_70], xmm1
0x1800ca319  mov     [rbp+57h+var_60], rdi
0x1800ca31d  movaps  [rbp+57h+var_50], xmm1
0x1800ca321  mov     [rbp+57h+var_40], rdi
0x1800ca325  mov     rax, [rcx]
0x1800ca328  lea     rdx, [rbp+57h+var_C0]
0x1800ca32c  mov     [rsp+110h+ppv], rdx
0x1800ca331  lea     r9, [rbp+57h+var_90]
0x1800ca335  lea     r8, [rbp+57h+var_70]
0x1800ca339  lea     rdx, [rbp+57h+var_50]
0x1800ca33d  mov     rax, [rax+50h]
0x1800ca341  call    j__guard_dispatch_icall
0x1800ca346  mov     ebx, eax
0x1800ca348  test    eax, eax
0x1800ca34a  jns     short loc_1800CA353
0x1800ca34c  mov     edx, 2Bh ; '+'
0x1800ca351  jmp     short loc_1800CA2DE
0x1800ca353  mov     [rbp+57h+arg_18], 0
0x1800ca35b  mov     rsi, [rbp+57h+arg_10]
0x1800ca35f  mov     rax, [rsi]
0x1800ca362  mov     rdi, [rax+38h]
0x1800ca366  lea     rcx, [rbp+57h+arg_18]
0x1800ca36a  call    sub_18003C1B0
0x1800ca36f  lea     r8, [rbp+57h+arg_18]
0x1800ca373  mov     rbx, [rsp+110h+bstrString]
0x1800ca378  mov     rdx, rbx
0x1800ca37b  mov     rcx, rsi
0x1800ca37e  mov     rax, rdi
0x1800ca381  call    j__guard_dispatch_icall
0x1800ca386  mov     edi, eax
0x1800ca388  test    eax, eax
0x1800ca38a  jns     short loc_1800CA3D5
0x1800ca38c  mov     rcx, [rbp+5Fh]
0x1800ca390  mov     r9d, eax
0x1800ca393  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca39a  mov     edx, 2Eh ; '.'
0x1800ca39f  call    sub_180008A1C
0x1800ca3a4  nop
0x1800ca3a5  lea     rcx, [rbp+57h+arg_18]
0x1800ca3a9  call    sub_18003C1B0
0x1800ca3ae  nop
0x1800ca3af  lea     rcx, [rbp+57h+arg_10]
0x1800ca3b3  call    sub_18003C1B0
0x1800ca3b8  nop
0x1800ca3b9  mov     rcx, [rsp+110h+var_D8]; bstrString
0x1800ca3be  call    cs:__imp_SysFreeString
0x1800ca3c4  nop
0x1800ca3c5  mov     rcx, rbx; bstrString
0x1800ca3c8  call    cs:__imp_SysFreeString
0x1800ca3ce  mov     ebx, edi
0x1800ca3d0  jmp     loc_1800CA4B7
0x1800ca3d5  mov     [rbp+57h+var_D0], 0
0x1800ca3dd  mov     r14, [rbp+57h+arg_18]
0x1800ca3e1  mov     rax, [r14]
0x1800ca3e4  mov     rsi, [rax+68h]
0x1800ca3e8  lea     rcx, [rbp+57h+var_D0]
0x1800ca3ec  call    sub_18003C1B0
0x1800ca3f1  lea     r8, [rbp+57h+var_D0]
0x1800ca3f5  mov     rdi, [rsp+110h+var_D8]
0x1800ca3fa  mov     rdx, rdi
0x1800ca3fd  mov     rcx, r14
0x1800ca400  mov     rax, rsi
0x1800ca403  call    j__guard_dispatch_icall
0x1800ca408  mov     esi, eax
0x1800ca40a  test    eax, eax
0x1800ca40c  jns     short loc_1800CA45C
0x1800ca40e  mov     edx, 31h ; '1'
0x1800ca413  lea     r8, aOnecoreAdminAp_66; "onecore\\admin\\appmodel\\common\\sched"...
0x1800ca41a  mov     r9d, esi
0x1800ca41d  mov     rcx, [rbp+5Fh]
0x1800ca421  call    sub_180008A1C
0x1800ca426  nop
0x1800ca427  lea     rcx, [rbp+57h+var_D0]
0x1800ca42b  call    sub_18003C1B0
0x1800ca430  nop
0x1800ca431  lea     rcx, [rbp+57h+arg_18]
0x1800ca435  call    sub_18003C1B0
0x1800ca43a  nop
0x1800ca43b  lea     rcx, [rbp+57h+arg_10]
0x1800ca43f  call    sub_18003C1B0
0x1800ca444  nop
0x1800ca445  mov     rcx, rdi; bstrString
0x1800ca448  call    cs:__imp_SysFreeString
0x1800ca44e  nop
0x1800ca44f  mov     rcx, rbx; bstrString
0x1800ca452  call    cs:__imp_SysFreeString
0x1800ca458  mov     ebx, esi
0x1800ca45a  jmp     short loc_1800CA4B7
0x1800ca45c  mov     rcx, [rbp+57h+var_D0]
0x1800ca460  mov     rax, [rcx]
0x1800ca463  xor     r15b, r13b
0x1800ca466  movzx   edx, r15b
0x1800ca46a  sub     dx, r13w
0x1800ca46e  mov     rax, [rax+58h]
0x1800ca472  call    j__guard_dispatch_icall
0x1800ca477  mov     esi, eax
0x1800ca479  test    eax, eax
0x1800ca47b  jns     short loc_1800CA484
0x1800ca47d  mov     edx, 32h ; '2'
0x1800ca482  jmp     short loc_1800CA413
0x1800ca484  lea     rcx, [rbp+57h+var_D0]
0x1800ca488  call    sub_18003C1B0
0x1800ca48d  nop
0x1800ca48e  lea     rcx, [rbp+57h+arg_18]
0x1800ca492  call    sub_18003C1B0
0x1800ca497  nop
0x1800ca498  lea     rcx, [rbp+57h+arg_10]
0x1800ca49c  call    sub_18003C1B0
0x1800ca4a1  nop
0x1800ca4a2  mov     rcx, rdi; bstrString
0x1800ca4a5  call    cs:__imp_SysFreeString
0x1800ca4ab  nop
0x1800ca4ac  mov     rcx, rbx; bstrString
0x1800ca4af  call    cs:__imp_SysFreeString
0x1800ca4b5  xor     ebx, ebx
0x1800ca4b7  lea     rcx, [rbp+57h+arg_0]
0x1800ca4bb  call    sub_180086C48
0x1800ca4c0  mov     eax, ebx
0x1800ca4c2  add     rsp, 0E0h
0x1800ca4c9  pop     r15
0x1800ca4cb  pop     r14
0x1800ca4cd  pop     r13
0x1800ca4cf  pop     rdi
0x1800ca4d0  pop     rsi
0x1800ca4d1  pop     rbx
0x1800ca4d2  pop     rbp
0x1800ca4d3  retn
```
