# EnableDisableWinSATTask(bool)

- ea: `0x180024248`
- end: `0x1800244d8`
- name: `?EnableDisableWinSATTask@@YAJ_N@Z`
- size: `656`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800213a4`
- `0x1800217fc`

## callees

- `0x18000e490`
- `0x18000f0e8`
- `0x18001d358`
- `0x180024248`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180024397`
- `OLEAUT32!__imp_SysFreeString` at `0x18002448d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800244a7`
- `OLEAUT32!__imp_SysFreeString` at `0x180024397`
- `OLEAUT32!__imp_SysFreeString` at `0x18002448d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800244a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002428a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002428a`

## string_xrefs

- `0x1800242a8`: `base\winsat\common\winsatutilities.cpp`
- `0x180024387`: `base\winsat\common\winsatutilities.cpp`
- `0x18002445a`: `base\winsat\common\winsatutilities.cpp`
- `0x18002447b`: `base\winsat\common\winsatutilities.cpp`
- `0x18002429c`: `cannot disable/enable task, failed to create a TaskScheduler object`
- `0x180024334`: `cannot disable/enable task, failed to connect to the TaskScheduler `
- `0x18002437b`: `cannot disable/enable task, failed to get the root task folder`
- `0x1800243f4`: `cannot disable/enable task, failed to get the WinSAT task`
- `0x180024421`: `cannot get the enabled property for the task`
- `0x18002444e`: `cannot disable/enable task, failed to get set the enable state`
- `0x18002446f`: `%s the WinSAT Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnableDisableWinSATTask(char a1)
{
  HRESULT v1; // ebx
  __int64 v3; // rax
  OLECHAR *v4; // rbx
  int v5; // edi
  OLECHAR *v6; // rdi
  int v7; // esi
  _BYTE v8[18]; // [rsp+30h] [rbp-69h] BYREF
  int v9; // [rsp+42h] [rbp-57h]
  __int16 v10; // [rsp+46h] [rbp-53h]
  BSTR bstrString; // [rsp+50h] [rbp-49h] BYREF
  BSTR v12[3]; // [rsp+58h] [rbp-41h] BYREF
  __int128 v13; // [rsp+70h] [rbp-29h] BYREF
  __int64 v14; // [rsp+80h] [rbp-19h]
  __int128 v15; // [rsp+90h] [rbp-9h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+7h]
  __int128 v17; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+27h]
  __int16 v19; // [rsp+100h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+110h] [rbp+77h] BYREF
  __int64 v22; // [rsp+118h] [rbp+7Fh] BYREF

  LOBYTE(v19) = a1;
  v12[1] = (BSTR)-2LL;
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 0x17u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v1 < 0 )
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1389,
      "cannot disable/enable task, failed to create a TaskScheduler object");
LABEL_3:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)v1;
  }
  *(_WORD *)v8 = 1;
  *(_OWORD *)&v8[2] = 0;
  v9 = 0;
  v10 = 0;
  v3 = *(_QWORD *)ppv;
  v13 = *(_OWORD *)v8;
  v14 = 0;
  v15 = *(_OWORD *)v8;
  v16 = 0;
  v17 = *(_OWORD *)v8;
  v18 = 0;
  if ( (*(int (__fastcall **)(LPVOID, __int128 *, __int128 *, _BYTE *, __int128 *))(v3 + 80))(ppv, &v17, &v15, v8, &v13) < 0 )
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1396,
      "cannot disable/enable task, failed to connect to the TaskScheduler ");
    goto LABEL_3;
  }
  v22 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"\\Microsoft\\Windows\\Maintenance");
  v4 = bstrString;
  v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, &v22);
  if ( v5 >= 0 )
  {
    v21 = 0;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v12, L"WinSAT");
    v6 = v12[0];
    v7 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v22 + 104LL))(v22, v12[0], &v21);
    if ( v7 >= 0 )
    {
      v19 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v21 + 80LL))(v21, &v19);
      if ( v7 >= 0 )
      {
        if ( v19 && (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 88LL))(v21, 0), v7 < 0) )
        {
          Log_Text_F(
            "base\\winsat\\common\\winsatutilities.cpp",
            1439,
            "cannot disable/enable task, failed to get set the enable state");
        }
        else
        {
          Log_Text_F("base\\winsat\\common\\winsatutilities.cpp", 1443, "%s the WinSAT Task", "Diabling");
          v7 = 0;
        }
      }
      else
      {
        Log_Text_F("base\\winsat\\common\\winsatutilities.cpp", 1424, "cannot get the enabled property for the task");
      }
    }
    else
    {
      Log_Text_F(
        "base\\winsat\\common\\winsatutilities.cpp",
        1416,
        "cannot disable/enable task, failed to get the WinSAT task");
    }
    SysFreeString(v6);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    SysFreeString(v4);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)v7;
  }
  else
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1406,
      "cannot disable/enable task, failed to get the root task folder");
    SysFreeString(v4);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180024248  mov     byte ptr [rsp-8+arg_0], cl
0x18002424c  push    rbp
0x18002424d  push    rbx
0x18002424e  push    rsi
0x18002424f  push    rdi
0x180024250  push    r14
0x180024252  lea     rbp, [rsp-37h]
0x180024257  sub     rsp, 0D0h
0x18002425e  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x180024266  xor     r14d, r14d
0x180024269  mov     [rbp+57h+arg_8], r14
0x18002426d  lea     rax, [rbp+57h+arg_8]
0x180024271  mov     [rsp+0F0h+ppv], rax; ppv
0x180024276  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002427d  xor     edx, edx; pUnkOuter
0x18002427f  lea     r8d, [r14+17h]; dwClsContext
0x180024283  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002428a  call    cs:__imp_CoCreateInstance
0x180024291  nop     dword ptr [rax+rax+00h]
0x180024296  mov     ebx, eax
0x180024298  test    eax, eax
0x18002429a  jns     short loc_1800242C5
0x18002429c  lea     r8, aCannotDisableE_0; "cannot disable/enable task, failed to c"...
0x1800242a3  mov     edx, 56Dh
0x1800242a8  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x1800242af  call    Log_Text_F
0x1800242b4  nop
0x1800242b5  lea     rcx, [rbp+57h+arg_8]
0x1800242b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800242be  mov     eax, ebx
0x1800242c0  jmp     loc_1800244C9
0x1800242c5  mov     eax, 1
0x1800242ca  mov     word ptr [rbp+57h+var_C0], ax
0x1800242ce  xorps   xmm0, xmm0
0x1800242d1  xor     eax, eax
0x1800242d3  movups  xmmword ptr [rbp+57h+var_C0+2], xmm0
0x1800242d7  mov     [rbp+57h+var_AE], eax
0x1800242da  mov     [rbp+57h+var_AA], ax
0x1800242de  mov     rcx, [rbp+57h+arg_8]
0x1800242e2  mov     rax, [rcx]
0x1800242e5  movups  xmm1, xmmword ptr [rbp+57h+var_C0]
0x1800242e9  movaps  [rbp+57h+var_80], xmm1
0x1800242ed  movsd   xmm0, qword ptr [rbp-59h]
0x1800242f2  movsd   [rbp+57h+var_70], xmm0
0x1800242f7  movaps  xmmword ptr [rbp+57h+var_C0], xmm1
0x1800242fb  movsd   qword ptr [rbp-59h], xmm0
0x180024300  movaps  [rbp+57h+var_60], xmm1
0x180024304  movsd   [rbp+57h+var_50], xmm0
0x180024309  movaps  [rbp+57h+var_40], xmm1
0x18002430d  movsd   [rbp+57h+var_30], xmm0
0x180024312  lea     rdx, [rbp+57h+var_80]
0x180024316  mov     [rsp+0F0h+ppv], rdx
0x18002431b  lea     r9, [rbp+57h+var_C0]
0x18002431f  lea     r8, [rbp+57h+var_60]
0x180024323  lea     rdx, [rbp+57h+var_40]
0x180024327  mov     rax, [rax+50h]
0x18002432b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024330  test    eax, eax
0x180024332  jns     short loc_180024345
0x180024334  lea     r8, aCannotDisableE_2; "cannot disable/enable task, failed to c"...
0x18002433b  mov     edx, 574h
0x180024340  jmp     loc_1800242A8
0x180024345  mov     [rbp+57h+arg_18], r14
0x180024349  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Maintenance"
0x180024350  lea     rcx, [rbp+57h+bstrString]; this
0x180024354  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180024359  nop
0x18002435a  mov     rcx, [rbp+57h+arg_8]
0x18002435e  mov     rax, [rcx]
0x180024361  lea     r8, [rbp+57h+arg_18]
0x180024365  mov     rbx, [rbp+57h+bstrString]
0x180024369  mov     rdx, rbx
0x18002436c  mov     rax, [rax+38h]
0x180024370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024375  mov     edi, eax
0x180024377  test    eax, eax
0x180024379  jns     short loc_1800243BE
0x18002437b  lea     r8, aCannotDisableE_3; "cannot disable/enable task, failed to g"...
0x180024382  mov     edx, 57Eh
0x180024387  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x18002438e  call    Log_Text_F
0x180024393  nop
0x180024394  mov     rcx, rbx; bstrString
0x180024397  call    cs:__imp_SysFreeString
0x18002439e  nop     dword ptr [rax+rax+00h]
0x1800243a3  nop
0x1800243a4  lea     rcx, [rbp+57h+arg_18]
0x1800243a8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800243ad  nop
0x1800243ae  lea     rcx, [rbp+57h+arg_8]
0x1800243b2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800243b7  mov     eax, edi
0x1800243b9  jmp     loc_1800244C9
0x1800243be  mov     [rbp+57h+arg_10], r14
0x1800243c2  lea     rdx, aWinsat_0; "WinSAT"
0x1800243c9  lea     rcx, [rbp+57h+var_98]; this
0x1800243cd  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800243d2  nop
0x1800243d3  mov     rcx, [rbp+57h+arg_18]
0x1800243d7  mov     rax, [rcx]
0x1800243da  lea     r8, [rbp+57h+arg_10]
0x1800243de  mov     rdi, [rbp+57h+var_98]
0x1800243e2  mov     rdx, rdi
0x1800243e5  mov     rax, [rax+68h]
0x1800243e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243ee  mov     esi, eax
0x1800243f0  test    eax, eax
0x1800243f2  jns     short loc_180024402
0x1800243f4  lea     r8, aCannotDisableE_1; "cannot disable/enable task, failed to g"...
0x1800243fb  mov     edx, 588h
0x180024400  jmp     short loc_18002445A
0x180024402  mov     [rbp+57h+arg_0], r14w
0x180024407  mov     rcx, [rbp+57h+arg_10]
0x18002440b  mov     rax, [rcx]
0x18002440e  lea     rdx, [rbp+57h+arg_0]
0x180024412  mov     rax, [rax+50h]
0x180024416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002441b  mov     esi, eax
0x18002441d  test    eax, eax
0x18002441f  jns     short loc_18002442F
0x180024421  lea     r8, aCannotGetTheEn; "cannot get the enabled property for the"...
0x180024428  mov     edx, 590h
0x18002442d  jmp     short loc_18002445A
0x18002442f  cmp     [rbp+57h+arg_0], r14w
0x180024434  jz      short loc_180024468
0x180024436  mov     rcx, [rbp+57h+arg_10]
0x18002443a  mov     rax, [rcx]
0x18002443d  xor     edx, edx
0x18002443f  mov     rax, [rax+58h]
0x180024443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024448  mov     esi, eax
0x18002444a  test    eax, eax
0x18002444c  jns     short loc_180024468
0x18002444e  lea     r8, aCannotDisableE; "cannot disable/enable task, failed to g"...
0x180024455  mov     edx, 59Fh
0x18002445a  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180024461  call    Log_Text_F
0x180024466  jmp     short loc_18002448A
0x180024468  lea     r9, aDiabling; "Diabling"
0x18002446f  lea     r8, aSTheWinsatTask; "%s the WinSAT Task"
0x180024476  mov     edx, 5A3h
0x18002447b  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180024482  call    Log_Text_F
0x180024487  mov     esi, r14d
0x18002448a  mov     rcx, rdi; bstrString
0x18002448d  call    cs:__imp_SysFreeString
0x180024494  nop     dword ptr [rax+rax+00h]
0x180024499  nop
0x18002449a  lea     rcx, [rbp+57h+arg_10]
0x18002449e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800244a3  nop
0x1800244a4  mov     rcx, rbx; bstrString
0x1800244a7  call    cs:__imp_SysFreeString
0x1800244ae  nop     dword ptr [rax+rax+00h]
0x1800244b3  nop
0x1800244b4  lea     rcx, [rbp+57h+arg_18]
0x1800244b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800244bd  nop
0x1800244be  lea     rcx, [rbp+57h+arg_8]
0x1800244c2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800244c7  mov     eax, esi
0x1800244c9  add     rsp, 0D0h
0x1800244d0  pop     r14
0x1800244d2  pop     rdi
0x1800244d3  pop     rsi
0x1800244d4  pop     rbx
0x1800244d5  pop     rbp
0x1800244d6  retn
```
