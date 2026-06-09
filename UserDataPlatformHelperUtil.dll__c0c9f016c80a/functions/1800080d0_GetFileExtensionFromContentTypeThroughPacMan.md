# GetFileExtensionFromContentTypeThroughPacMan

- ea: `0x1800080d0`
- end: `0x1800083aa`
- name: `GetFileExtensionFromContentTypeThroughPacMan`
- size: `730`
- prototype: `__int64 __fastcall(const OLECHAR *, OLECHAR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800083e0`

## callees

- `0x180003ec0`
- `0x180007c90`
- `0x1800080d0`
- `0x18000b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180008131`
- `OLEAUT32!__imp_SysAllocString` at `0x180008131`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000827d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180008331`
- `OLEAUT32!__imp_SysFreeString` at `0x180008384`
- `OLEAUT32!__imp_SysFreeString` at `0x18000838c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000827d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1800082d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180008331`
- `OLEAUT32!__imp_SysFreeString` at `0x180008384`
- `OLEAUT32!__imp_SysFreeString` at `0x18000838c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800081e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180008252`
- `OLEAUT32!__imp_SysStringLen` at `0x1800081e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180008252`
- `OLEAUT32!__imp_VarBstrCat` at `0x18000826e`
- `OLEAUT32!__imp_VarBstrCat` at `0x18000826e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000810f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000810f`

## pseudocode

```c
__int64 __fastcall GetFileExtensionFromContentTypeThroughPacMan(const OLECHAR *a1, OLECHAR **a2)
{
  OLECHAR *v2; // rbx
  OLECHAR *v4; // rdi
  HRESULT Instance; // esi
  __int64 v6; // rax
  OLECHAR *v7; // rcx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  OLECHAR *v11; // rsi
  __int64 v12; // rcx
  BSTR pbstr; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  BSTR v15; // [rsp+40h] [rbp-30h] BYREF
  BSTR pbstrResult; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v18; // [rsp+60h] [rbp-10h]
  __int64 v19; // [rsp+A0h] [rbp+30h] BYREF
  OLECHAR *psz; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  v15 = 0;
  if ( a1 )
  {
    v4 = SysAllocString(a1);
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v4 = 0;
  }
  psz = 0;
  Instance = CoCreateInstance(
               &GUID_b9e511fc_e364_497a_a121_b7b3612cedce,
               0,
               0x17u,
               &GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a,
               (LPVOID *)&psz);
  if ( Instance < 0 )
  {
    if ( psz )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 16LL))(psz);
    goto LABEL_13;
  }
  v17[0] = 20;
  v17[1] = v4;
  v21 = 0;
  v6 = *(_QWORD *)psz;
  v18 = 0;
  Instance = (*(__int64 (__fastcall **)(OLECHAR *, __int64 *, _QWORD *))(v6 + 48))(psz, &v21, v17);
  if ( Instance < 0 )
  {
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( psz )
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 16LL))(psz);
LABEL_13:
    SysFreeString(v4);
    v7 = 0;
LABEL_14:
    SysFreeString(v7);
    return (unsigned int)Instance;
  }
  v19 = 0;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL))(v21, &v19) )
  {
    if ( SysStringLen(v2) )
    {
      ATL::CComBSTR::Append(&v15, v9);
      v2 = v15;
    }
    v10 = 0;
    v14 = 0;
    if ( v19 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &GUID_6b87cb6c_0b88_4989_a4ec_033714f710d4, &v14);
      v10 = v14;
    }
    pbstr = 0;
    Instance = (*(__int64 (__fastcall **)(__int64, OLECHAR *, BSTR *))(*(_QWORD *)v10 + 56LL))(v10, v4, &pbstr);
    if ( Instance < 0 )
    {
LABEL_29:
      SysFreeString(pbstr);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( psz )
        (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 16LL))(psz);
      SysFreeString(v4);
      v7 = v2;
      goto LABEL_14;
    }
    v11 = pbstr;
    if ( SysStringLen(pbstr) )
    {
      pbstrResult = 0;
      Instance = VarBstrCat(v2, v11, &pbstrResult);
      if ( Instance < 0 )
        goto LABEL_29;
      SysFreeString(v2);
      v2 = pbstrResult;
      v15 = pbstrResult;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    SysFreeString(pbstr);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v12 = v19;
  *a2 = v2;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( psz )
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 16LL))(psz);
  SysFreeString(v4);
  SysFreeString(0);
  return 0;
}

```

## disassembly

```asm
0x1800080d0  push    rbp
0x1800080d2  push    rbx
0x1800080d3  push    rsi
0x1800080d4  push    rdi
0x1800080d5  push    r14
0x1800080d7  mov     rbp, rsp
0x1800080da  sub     rsp, 70h
0x1800080de  xor     ebx, ebx
0x1800080e0  mov     r14, rdx
0x1800080e3  mov     [rbp+var_30], rbx
0x1800080e7  test    rcx, rcx
0x1800080ea  jnz     short loc_180008131
0x1800080ec  xor     edi, edi
0x1800080ee  xor     edx, edx; pUnkOuter
0x1800080f0  mov     [rbp+psz], rbx
0x1800080f4  lea     rax, [rbp+psz]
0x1800080f8  lea     r9, _GUID_698d57c2_292d_4cf3_b73c_d95a6922ed9a; riid
0x1800080ff  mov     [rsp+70h+ppv], rax; ppv
0x180008104  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x18000810b  lea     r8d, [rdx+17h]; dwClsContext
0x18000810f  call    cs:__imp_CoCreateInstance
0x180008115  mov     rcx, [rbp+psz]; psz
0x180008119  mov     esi, eax
0x18000811b  test    eax, eax
0x18000811d  jns     short loc_180008145
0x18000811f  test    rcx, rcx
0x180008122  jz      loc_1800081A8
0x180008128  mov     rdx, [rcx]
0x18000812b  mov     rax, [rdx+10h]
0x18000812f  jmp     short loc_1800081A3
0x180008131  call    cs:__imp_SysAllocString
0x180008137  mov     rdi, rax
0x18000813a  test    rax, rax
0x18000813d  jz      loc_18000839F
0x180008143  jmp     short loc_1800080EE
0x180008145  mov     qword ptr [rbp+var_20], 14h
0x18000814d  lea     r8, [rbp+var_20]
0x180008151  mov     qword ptr [rbp+var_20+8], rdi
0x180008155  lea     rdx, [rbp+arg_18]
0x180008159  movups  xmm0, [rbp+var_20]
0x18000815d  mov     [rbp+arg_18], rbx
0x180008161  mov     rax, [rcx]
0x180008164  xorps   xmm1, xmm1
0x180008167  movaps  [rbp+var_20], xmm0
0x18000816b  movaps  [rbp+var_10], xmm1
0x18000816f  mov     rax, [rax+30h]
0x180008173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008178  mov     esi, eax
0x18000817a  test    eax, eax
0x18000817c  jns     short loc_1800081C0
0x18000817e  mov     rcx, [rbp+arg_18]
0x180008182  test    rcx, rcx
0x180008185  jz      short loc_180008193
0x180008187  mov     rdx, [rcx]
0x18000818a  mov     rax, [rdx+10h]
0x18000818e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008193  mov     rcx, [rbp+psz]
0x180008197  test    rcx, rcx
0x18000819a  jz      short loc_1800081A8
0x18000819c  mov     rax, [rcx]
0x18000819f  mov     rax, [rax+10h]
0x1800081a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081a8  mov     rcx, rdi; bstrString
0x1800081ab  call    cs:__imp_SysFreeString
0x1800081b1  xor     ecx, ecx; bstrString
0x1800081b3  call    cs:__imp_SysFreeString
0x1800081b9  mov     eax, esi
0x1800081bb  jmp     loc_180008394
0x1800081c0  mov     [rbp+arg_0], rbx
0x1800081c4  mov     rcx, [rbp+arg_18]
0x1800081c8  lea     rdx, [rbp+arg_0]
0x1800081cc  mov     rax, [rcx]
0x1800081cf  mov     rax, [rax+18h]
0x1800081d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d8  test    eax, eax
0x1800081da  jnz     loc_18000833F
0x1800081e0  mov     rcx, rbx; pbstr
0x1800081e3  call    cs:__imp_SysStringLen
0x1800081e9  test    eax, eax
0x1800081eb  jz      short loc_1800081FA
0x1800081ed  lea     rcx, [rbp+var_30]; this
0x1800081f1  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800081f6  mov     rbx, [rbp+var_30]
0x1800081fa  mov     r9, [rbp+arg_0]
0x1800081fe  xor     ecx, ecx
0x180008200  mov     [rbp+var_38], rcx
0x180008204  test    r9, r9
0x180008207  jz      short loc_180008226
0x180008209  mov     rax, [r9]
0x18000820c  lea     r8, [rbp+var_38]
0x180008210  lea     rdx, _GUID_6b87cb6c_0b88_4989_a4ec_033714f710d4
0x180008217  mov     rcx, r9
0x18000821a  mov     rax, [rax]
0x18000821d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008222  mov     rcx, [rbp+var_38]
0x180008226  mov     [rbp+pbstr], 0
0x18000822e  lea     r8, [rbp+pbstr]
0x180008232  mov     rax, [rcx]
0x180008235  mov     rdx, rdi
0x180008238  mov     rax, [rax+38h]
0x18000823c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008241  mov     esi, eax
0x180008243  test    eax, eax
0x180008245  js      loc_1800082D0
0x18000824b  mov     rsi, [rbp+pbstr]
0x18000824f  mov     rcx, rsi; pbstr
0x180008252  call    cs:__imp_SysStringLen
0x180008258  test    eax, eax
0x18000825a  jz      short loc_18000828B
0x18000825c  lea     r8, [rbp+pbstrResult]; pbstrResult
0x180008260  mov     [rbp+pbstrResult], 0
0x180008268  mov     rdx, rsi; bstrRight
0x18000826b  mov     rcx, rbx; bstrLeft
0x18000826e  call    cs:__imp_VarBstrCat
0x180008274  mov     esi, eax
0x180008276  test    eax, eax
0x180008278  js      short loc_1800082D0
0x18000827a  mov     rcx, rbx; bstrString
0x18000827d  call    cs:__imp_SysFreeString
0x180008283  mov     rbx, [rbp+pbstrResult]
0x180008287  mov     [rbp+var_30], rbx
0x18000828b  mov     rcx, [rbp+arg_0]
0x18000828f  test    rcx, rcx
0x180008292  jz      short loc_1800082A8
0x180008294  mov     rax, [rcx]
0x180008297  mov     rax, [rax+10h]
0x18000829b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082a0  mov     [rbp+arg_0], 0
0x1800082a8  mov     rcx, [rbp+pbstr]; bstrString
0x1800082ac  call    cs:__imp_SysFreeString
0x1800082b2  mov     rcx, [rbp+var_38]
0x1800082b6  test    rcx, rcx
0x1800082b9  jz      loc_1800081C4
0x1800082bf  mov     rax, [rcx]
0x1800082c2  mov     rax, [rax+10h]
0x1800082c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082cb  jmp     loc_1800081C4
0x1800082d0  mov     rcx, [rbp+pbstr]; bstrString
0x1800082d4  call    cs:__imp_SysFreeString
0x1800082da  mov     rcx, [rbp+var_38]
0x1800082de  test    rcx, rcx
0x1800082e1  jz      short loc_1800082EF
0x1800082e3  mov     rax, [rcx]
0x1800082e6  mov     rax, [rax+10h]
0x1800082ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ef  mov     rcx, [rbp+arg_0]
0x1800082f3  test    rcx, rcx
0x1800082f6  jz      short loc_180008304
0x1800082f8  mov     rax, [rcx]
0x1800082fb  mov     rax, [rax+10h]
0x1800082ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008304  mov     rcx, [rbp+arg_18]
0x180008308  test    rcx, rcx
0x18000830b  jz      short loc_180008319
0x18000830d  mov     rax, [rcx]
0x180008310  mov     rax, [rax+10h]
0x180008314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008319  mov     rcx, [rbp+psz]
0x18000831d  test    rcx, rcx
0x180008320  jz      short loc_18000832E
0x180008322  mov     rax, [rcx]
0x180008325  mov     rax, [rax+10h]
0x180008329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832e  mov     rcx, rdi; bstrString
0x180008331  call    cs:__imp_SysFreeString
0x180008337  mov     rcx, rbx
0x18000833a  jmp     loc_1800081B3
0x18000833f  mov     rcx, [rbp+arg_0]
0x180008343  mov     [r14], rbx
0x180008346  test    rcx, rcx
0x180008349  jz      short loc_180008357
0x18000834b  mov     rax, [rcx]
0x18000834e  mov     rax, [rax+10h]
0x180008352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008357  mov     rcx, [rbp+arg_18]
0x18000835b  test    rcx, rcx
0x18000835e  jz      short loc_18000836C
0x180008360  mov     rax, [rcx]
0x180008363  mov     rax, [rax+10h]
0x180008367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836c  mov     rcx, [rbp+psz]
0x180008370  test    rcx, rcx
0x180008373  jz      short loc_180008381
0x180008375  mov     rax, [rcx]
0x180008378  mov     rax, [rax+10h]
0x18000837c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008381  mov     rcx, rdi; bstrString
0x180008384  call    cs:__imp_SysFreeString
0x18000838a  xor     ecx, ecx; bstrString
0x18000838c  call    cs:__imp_SysFreeString
0x180008392  xor     eax, eax
0x180008394  add     rsp, 70h
0x180008398  pop     r14
0x18000839a  pop     rdi
0x18000839b  pop     rsi
0x18000839c  pop     rbx
0x18000839d  pop     rbp
0x18000839e  retn
0x18000839f  mov     ecx, 8007000Eh; int
0x1800083a4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
