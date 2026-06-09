# WaasMedic::TasksHelper::CompareSettings(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)

- ea: `0x18005e614`
- end: `0x18005ec4e`
- name: `?CompareSettings@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z`
- size: `1594`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005fc80`

## callees

- `0x18002543c`
- `0x18005e614`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e887`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e9ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e887`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e9ec`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e767`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e799`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e8c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e8fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea58`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb37`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb45`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb53`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb61`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e767`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e799`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e8c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e8fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea3c`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ea58`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb37`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb45`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb53`
- `OLEAUT32!__imp_SysFreeString` at `0x18005eb61`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e7c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e866`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e926`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e9cb`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e7c4`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e866`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e926`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e9cb`

## string_xrefs

- `0x18005ea18`: `Error encountered when comparing current task settings with expected task settings. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall WaasMedic::TasksHelper::CompareSettings(_QWORD *a1, _QWORD *a2, int a3, _BYTE *a4)
{
  int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, BSTR *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, BSTR *); // rbx
  const WCHAR *v12; // rdi
  const wchar_t *v13; // r8
  UINT v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, BSTR *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, BSTR *); // rbx
  const WCHAR *v19; // rdi
  const wchar_t *v20; // r8
  UINT v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  _WORD v33[2]; // [rsp+38h] [rbp-39h] BYREF
  __int16 v34; // [rsp+3Ch] [rbp-35h] BYREF
  __int16 v35; // [rsp+40h] [rbp-31h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-21h] BYREF
  BSTR v38; // [rsp+58h] [rbp-19h] BYREF
  __int64 v39; // [rsp+60h] [rbp-11h] BYREF
  __int64 v40; // [rsp+68h] [rbp-9h] BYREF
  BSTR v41; // [rsp+70h] [rbp-1h] BYREF
  __int64 v42; // [rsp+78h] [rbp+7h] BYREF
  __int64 v43; // [rsp+80h] [rbp+Fh] BYREF
  __int64 v44; // [rsp+88h] [rbp+17h] BYREF
  _QWORD v45[7]; // [rsp+90h] [rbp+1Fh] BYREF
  int v46; // [rsp+E8h] [rbp+77h] BYREF

  v46 = a3;
  v40 = 0;
  v39 = 0;
  v45[0] = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  bstrString = 0;
  v38 = 0;
  pbstr = 0;
  v41 = 0;
  if ( *a1 && *a2 && a4 )
  {
    *a4 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 88LL))(*a2, &v40);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 88LL))(*a1, &v39);
      if ( v7 >= 0 )
      {
        v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v39)(v39, &IID_ITaskSettings3, &v44);
        if ( v7 >= 0 )
        {
          v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v40)(v40, &IID_ITaskSettings3, v45);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 408LL))(v44, &v42);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v45[0] + 408LL))(v45[0], &v43);
              if ( v7 >= 0 )
              {
                if ( !v42 )
                  goto LABEL_16;
                v8 = v43;
                v9 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v43 + 64LL);
                SysFreeString(bstrString);
                bstrString = 0;
                v7 = v9(v8, &bstrString);
                if ( v7 >= 0 )
                {
                  v10 = v42;
                  v11 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v42 + 64LL);
                  SysFreeString(v38);
                  v38 = 0;
                  v7 = v11(v10, &v38);
                  if ( v7 >= 0 )
                  {
                    v12 = v38;
                    if ( SysStringLen(bstrString) )
                    {
                      v14 = SysStringLen(bstrString);
                      if ( CompareStringW(0x400u, 0, v12, -1, bstrString, v14) == 2 )
                        goto LABEL_16;
                    }
                    else if ( !v12 || !*v12 )
                    {
LABEL_16:
                      LOWORD(v46) = 0;
                      v33[0] = 0;
                      v7 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v39 + 232LL))(v39, v33);
                      if ( v7 < 0 )
                        goto LABEL_38;
                      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 232LL))(v40, &v46);
                      if ( v7 < 0 )
                        goto LABEL_38;
                      if ( (_WORD)v46 != v33[0] )
                      {
                        v13 = L"true";
                        if ( !v33[0] )
                          v13 = L"false";
                        LogLevelW(3u, L"Settings enabled states did not match! Expected: %s; Actual: %s", v13);
                        goto LABEL_39;
                      }
                      v15 = v39;
                      v16 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v39 + 216LL);
                      SysFreeString(v41);
                      v41 = 0;
                      v7 = v16(v15, &v41);
                      if ( v7 < 0 )
                        goto LABEL_38;
                      v17 = v40;
                      v18 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v40 + 216LL);
                      SysFreeString(pbstr);
                      pbstr = 0;
                      v7 = v18(v17, &pbstr);
                      if ( v7 < 0 )
                        goto LABEL_38;
                      v19 = v41;
                      if ( SysStringLen(pbstr) )
                      {
                        v21 = SysStringLen(pbstr);
                        if ( CompareStringW(0x400u, 0, v19, -1, pbstr, v21) == 2 )
                          goto LABEL_29;
                      }
                      else if ( !v19 || !*v19 )
                      {
LABEL_29:
                        v34 = 0;
                        v35 = 0;
                        v7 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v39 + 168LL))(v39, &v35);
                        if ( v7 >= 0 )
                        {
                          v7 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v40 + 168LL))(v40, &v34);
                          if ( v7 >= 0 )
                          {
                            if ( v34 == v35 )
                            {
                              *a4 = 1;
                            }
                            else
                            {
                              v20 = L"true";
                              if ( !v35 )
                                v20 = L"false";
                              LogLevelW(
                                3u,
                                L"Settings start when available did not match! Expected: %s; Actual: %s",
                                v20);
                            }
                            goto LABEL_39;
                          }
                        }
                        goto LABEL_38;
                      }
                      LogLevelW(3u, L"Settings execution time limits did not match! Expected: %s; Actual: %s", v41);
LABEL_39:
                      SysFreeString(v41);
                      v41 = 0;
                      SysFreeString(pbstr);
                      pbstr = 0;
                      SysFreeString(v38);
                      v38 = 0;
                      SysFreeString(bstrString);
                      bstrString = 0;
                      v22 = v42;
                      if ( v42 )
                      {
                        v42 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                      }
                      v23 = v43;
                      if ( v43 )
                      {
                        v43 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                      }
                      v24 = v44;
                      if ( v44 )
                      {
                        v44 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                      }
                      v25 = v45[0];
                      if ( v45[0] )
                      {
                        v45[0] = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                      }
                      v26 = v39;
                      if ( v39 )
                      {
                        v39 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                      }
                      v27 = v40;
                      if ( v40 )
                      {
                        v40 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                      }
                      v28 = *a1;
                      if ( *a1 )
                      {
                        *a1 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                      }
                      v29 = *a2;
                      if ( *a2 )
                      {
                        *a2 = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                      }
                      return (unsigned int)v7;
                    }
                    LogLevelW(3u, L"Settings periods did not match! Expected: %s; Actual: %s", v38);
                    goto LABEL_39;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_38:
    LogLevelW(
      2u,
      L"Error encountered when comparing current task settings with expected task settings. hr=0x%08x",
      (unsigned int)v7);
    goto LABEL_39;
  }
  SysFreeString(0);
  v41 = 0;
  SysFreeString(pbstr);
  pbstr = 0;
  SysFreeString(v38);
  v38 = 0;
  SysFreeString(bstrString);
  bstrString = 0;
  v31 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v32 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18005e614  mov     rax, rsp
0x18005e617  mov     [rax+18h], r8d
0x18005e61b  mov     [rax+10h], rdx
0x18005e61f  mov     [rax+8], rcx
0x18005e623  push    rbp
0x18005e624  push    rbx
0x18005e625  push    rsi
0x18005e626  push    rdi
0x18005e627  push    r12
0x18005e629  push    r14
0x18005e62b  push    r15
0x18005e62d  lea     rbp, [rax-5Fh]
0x18005e631  sub     rsp, 90h
0x18005e638  mov     r15, r9
0x18005e63b  mov     rsi, rdx
0x18005e63e  mov     r14, rcx
0x18005e641  xor     r12d, r12d
0x18005e644  mov     [rbp+57h+var_60], r12
0x18005e648  mov     [rbp+57h+var_68], r12
0x18005e64c  mov     [rbp+57h+var_38], r12
0x18005e650  mov     [rbp+57h+var_40], r12
0x18005e654  mov     [rbp+57h+var_48], r12
0x18005e658  mov     [rbp+57h+var_50], r12
0x18005e65c  mov     [rbp+57h+bstrString], r12
0x18005e660  mov     [rbp+57h+var_70], r12
0x18005e664  mov     [rbp+57h+pbstr], r12
0x18005e668  mov     [rbp+57h+var_58], r12
0x18005e66c  cmp     [rcx], r12
0x18005e66f  jz      loc_18005EB35
0x18005e675  cmp     [rdx], r12
0x18005e678  jz      loc_18005EB35
0x18005e67e  test    r9, r9
0x18005e681  jz      loc_18005EB35
0x18005e687  mov     [r9], r12b
0x18005e68a  mov     rcx, [rdx]
0x18005e68d  mov     rax, [rcx]
0x18005e690  lea     rdx, [rbp+57h+var_60]
0x18005e694  mov     rax, [rax+58h]
0x18005e698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e69d  mov     ebx, eax
0x18005e69f  test    eax, eax
0x18005e6a1  js      loc_18005EA15
0x18005e6a7  mov     rcx, [r14]
0x18005e6aa  mov     rax, [rcx]
0x18005e6ad  lea     rdx, [rbp+57h+var_68]
0x18005e6b1  mov     rax, [rax+58h]
0x18005e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6ba  mov     ebx, eax
0x18005e6bc  test    eax, eax
0x18005e6be  js      loc_18005EA15
0x18005e6c4  mov     rcx, [rbp+57h+var_68]
0x18005e6c8  mov     rax, [rcx]
0x18005e6cb  lea     r8, [rbp+57h+var_40]
0x18005e6cf  lea     rdx, IID_ITaskSettings3
0x18005e6d6  mov     rax, [rax]
0x18005e6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6de  mov     ebx, eax
0x18005e6e0  test    eax, eax
0x18005e6e2  js      loc_18005EA15
0x18005e6e8  mov     rcx, [rbp+57h+var_60]
0x18005e6ec  mov     rax, [rcx]
0x18005e6ef  lea     r8, [rbp+57h+var_38]
0x18005e6f3  lea     rdx, IID_ITaskSettings3
0x18005e6fa  mov     rax, [rax]
0x18005e6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e702  mov     ebx, eax
0x18005e704  test    eax, eax
0x18005e706  js      loc_18005EA15
0x18005e70c  mov     rcx, [rbp+57h+var_40]
0x18005e710  mov     rax, [rcx]
0x18005e713  lea     rdx, [rbp+57h+var_50]
0x18005e717  mov     rax, [rax+198h]
0x18005e71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e723  mov     ebx, eax
0x18005e725  test    eax, eax
0x18005e727  js      loc_18005EA15
0x18005e72d  mov     rcx, [rbp+57h+var_38]
0x18005e731  mov     rax, [rcx]
0x18005e734  lea     rdx, [rbp+57h+var_48]
0x18005e738  mov     rax, [rax+198h]
0x18005e73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e744  mov     ebx, eax
0x18005e746  test    eax, eax
0x18005e748  js      loc_18005EA15
0x18005e74e  cmp     [rbp+57h+var_50], r12
0x18005e752  jz      loc_18005E7E1
0x18005e758  mov     rdi, [rbp+57h+var_48]
0x18005e75c  mov     rax, [rdi]
0x18005e75f  mov     rbx, [rax+40h]
0x18005e763  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005e767  call    cs:__imp_SysFreeString
0x18005e76d  mov     [rbp+57h+bstrString], r12
0x18005e771  lea     rdx, [rbp+57h+bstrString]
0x18005e775  mov     rcx, rdi
0x18005e778  mov     rax, rbx
0x18005e77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e780  mov     ebx, eax
0x18005e782  test    eax, eax
0x18005e784  js      loc_18005EA15
0x18005e78a  mov     rdi, [rbp+57h+var_50]
0x18005e78e  mov     rax, [rdi]
0x18005e791  mov     rbx, [rax+40h]
0x18005e795  mov     rcx, [rbp+57h+var_70]; bstrString
0x18005e799  call    cs:__imp_SysFreeString
0x18005e79f  mov     [rbp+57h+var_70], r12
0x18005e7a3  lea     rdx, [rbp+57h+var_70]
0x18005e7a7  mov     rcx, rdi
0x18005e7aa  mov     rax, rbx
0x18005e7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7b2  mov     ebx, eax
0x18005e7b4  test    eax, eax
0x18005e7b6  js      loc_18005EA15
0x18005e7bc  mov     rdi, [rbp+57h+var_70]
0x18005e7c0  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18005e7c4  call    cs:__imp_SysStringLen
0x18005e7ca  test    eax, eax
0x18005e7cc  jnz     loc_18005E862
0x18005e7d2  test    rdi, rdi
0x18005e7d5  jz      short loc_18005E7E1
0x18005e7d7  cmp     [rdi], r12w
0x18005e7db  jnz     loc_18005E896
0x18005e7e1  mov     word ptr [rbp+57h+arg_10], r12w
0x18005e7e6  mov     [rbp+57h+var_90], r12w
0x18005e7eb  mov     rcx, [rbp+57h+var_68]
0x18005e7ef  mov     rax, [rcx]
0x18005e7f2  lea     rdx, [rbp+57h+var_90]
0x18005e7f6  mov     rax, [rax+0E8h]
0x18005e7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e802  mov     ebx, eax
0x18005e804  test    eax, eax
0x18005e806  js      loc_18005EA15
0x18005e80c  mov     rcx, [rbp+57h+var_60]
0x18005e810  mov     rax, [rcx]
0x18005e813  lea     rdx, [rbp+57h+arg_10]
0x18005e817  mov     rax, [rax+0E8h]
0x18005e81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e823  mov     ebx, eax
0x18005e825  test    eax, eax
0x18005e827  js      loc_18005EA15
0x18005e82d  movzx   eax, word ptr [rbp+57h+arg_10]
0x18005e831  movzx   ecx, [rbp+57h+var_90]
0x18005e835  cmp     ax, cx
0x18005e838  jz      short loc_18005E8B4
0x18005e83a  lea     r9, aTrue; "true"
0x18005e841  mov     r8, r9
0x18005e844  lea     rdx, aFalse_0; "false"
0x18005e84b  test    cx, cx
0x18005e84e  cmovz   r8, rdx
0x18005e852  test    ax, ax
0x18005e855  cmovz   r9, rdx
0x18005e859  lea     rdx, aSettingsEnable; "Settings enabled states did not match! "...
0x18005e860  jmp     short loc_18005E8A5
0x18005e862  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18005e866  call    cs:__imp_SysStringLen
0x18005e86c  mov     rcx, [rbp+57h+bstrString]
0x18005e870  mov     [rsp+28h], eax; cchCount2
0x18005e874  mov     [rsp+0C0h+lpString2], rcx; lpString2
0x18005e879  or      r9d, 0FFFFFFFFh; cchCount1
0x18005e87d  mov     r8, rdi; lpString1
0x18005e880  xor     edx, edx; dwCmpFlags
0x18005e882  mov     ecx, 400h; Locale
0x18005e887  call    cs:__imp_CompareStringW
0x18005e88d  cmp     eax, 2
0x18005e890  jz      loc_18005E7E1
0x18005e896  mov     r9, [rbp+57h+bstrString]
0x18005e89a  mov     r8, [rbp+57h+var_70]
0x18005e89e  lea     rdx, aSettingsPeriod; "Settings periods did not match! Expecte"...
0x18005e8a5  mov     ecx, 3; unsigned __int8
0x18005e8aa  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005e8af  jmp     loc_18005EA2A
0x18005e8b4  mov     rdi, [rbp+57h+var_68]
0x18005e8b8  mov     rax, [rdi]
0x18005e8bb  mov     rbx, [rax+0D8h]
0x18005e8c2  mov     rcx, [rbp+57h+var_58]; bstrString
0x18005e8c6  call    cs:__imp_SysFreeString
0x18005e8cc  mov     [rbp+57h+var_58], r12
0x18005e8d0  lea     rdx, [rbp+57h+var_58]
0x18005e8d4  mov     rcx, rdi
0x18005e8d7  mov     rax, rbx
0x18005e8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8df  mov     ebx, eax
0x18005e8e1  test    eax, eax
0x18005e8e3  js      loc_18005EA15
0x18005e8e9  mov     rdi, [rbp+57h+var_60]
0x18005e8ed  mov     rax, [rdi]
0x18005e8f0  mov     rbx, [rax+0D8h]
0x18005e8f7  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18005e8fb  call    cs:__imp_SysFreeString
0x18005e901  mov     [rbp+57h+pbstr], r12
0x18005e905  lea     rdx, [rbp+57h+pbstr]
0x18005e909  mov     rcx, rdi
0x18005e90c  mov     rax, rbx
0x18005e90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e914  mov     ebx, eax
0x18005e916  test    eax, eax
0x18005e918  js      loc_18005EA15
0x18005e91e  mov     rdi, [rbp+57h+var_58]
0x18005e922  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18005e926  call    cs:__imp_SysStringLen
0x18005e92c  test    eax, eax
0x18005e92e  jnz     loc_18005E9C7
0x18005e934  test    rdi, rdi
0x18005e937  jz      short loc_18005E943
0x18005e939  cmp     [rdi], r12w
0x18005e93d  jnz     loc_18005E9FB
0x18005e943  mov     [rbp+57h+var_8C], r12w
0x18005e948  mov     [rbp+57h+var_88], r12w
0x18005e94d  mov     rcx, [rbp+57h+var_68]
0x18005e951  mov     rax, [rcx]
0x18005e954  lea     rdx, [rbp+57h+var_88]
0x18005e958  mov     rax, [rax+0A8h]
0x18005e95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e964  mov     ebx, eax
0x18005e966  test    eax, eax
0x18005e968  js      loc_18005EA15
0x18005e96e  mov     rcx, [rbp+57h+var_60]
0x18005e972  mov     rax, [rcx]
0x18005e975  lea     rdx, [rbp+57h+var_8C]
0x18005e979  mov     rax, [rax+0A8h]
0x18005e980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e985  mov     ebx, eax
0x18005e987  test    eax, eax
0x18005e989  js      loc_18005EA15
0x18005e98f  movzx   eax, [rbp+57h+var_8C]
0x18005e993  movzx   ecx, [rbp+57h+var_88]
0x18005e997  cmp     ax, cx
0x18005e99a  jz      short loc_18005EA0F
0x18005e99c  lea     r9, aTrue; "true"
0x18005e9a3  mov     r8, r9
0x18005e9a6  lea     rdx, aFalse_0; "false"
0x18005e9ad  test    cx, cx
0x18005e9b0  cmovz   r8, rdx
0x18005e9b4  test    ax, ax
0x18005e9b7  cmovz   r9, rdx
0x18005e9bb  lea     rdx, aSettingsStartW; "Settings start when available did not m"...
0x18005e9c2  jmp     loc_18005E8A5
0x18005e9c7  mov     rcx, [rbp+57h+pbstr]; pbstr
0x18005e9cb  call    cs:__imp_SysStringLen
0x18005e9d1  mov     rdx, [rbp+57h+pbstr]
0x18005e9d5  mov     [rsp+28h], eax; cchCount2
0x18005e9d9  mov     [rsp+0C0h+lpString2], rdx; lpString2
0x18005e9de  or      r9d, 0FFFFFFFFh; cchCount1
0x18005e9e2  mov     r8, rdi; lpString1
0x18005e9e5  xor     edx, edx; dwCmpFlags
0x18005e9e7  mov     ecx, 400h; Locale
0x18005e9ec  call    cs:__imp_CompareStringW
0x18005e9f2  cmp     eax, 2
0x18005e9f5  jz      loc_18005E943
0x18005e9fb  mov     r9, [rbp+57h+pbstr]
0x18005e9ff  mov     r8, [rbp+57h+var_58]
0x18005ea03  lea     rdx, aSettingsExecut; "Settings execution time limits did not "...
0x18005ea0a  jmp     loc_18005E8A5
0x18005ea0f  mov     byte ptr [r15], 1
0x18005ea13  jmp     short loc_18005EA2A
0x18005ea15  mov     r8d, ebx
0x18005ea18  lea     rdx, aErrorEncounter_0; "Error encountered when comparing curren"...
0x18005ea1f  mov     ecx, 2; unsigned __int8
0x18005ea24  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005ea29  nop
0x18005ea2a  mov     rcx, [rbp+57h+var_58]; bstrString
0x18005ea2e  call    cs:__imp_SysFreeString
0x18005ea34  mov     [rbp+57h+var_58], r12
0x18005ea38  mov     rcx, [rbp+57h+pbstr]; bstrString
0x18005ea3c  call    cs:__imp_SysFreeString
0x18005ea42  mov     [rbp+57h+pbstr], r12
0x18005ea46  mov     rcx, [rbp+57h+var_70]; bstrString
0x18005ea4a  call    cs:__imp_SysFreeString
0x18005ea50  mov     [rbp+57h+var_70], r12
0x18005ea54  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005ea58  call    cs:__imp_SysFreeString
0x18005ea5e  mov     [rbp+57h+bstrString], r12
0x18005ea62  mov     rcx, [rbp+57h+var_50]
0x18005ea66  test    rcx, rcx
0x18005ea69  jz      short loc_18005EA7C
0x18005ea6b  mov     [rbp+57h+var_50], r12
0x18005ea6f  mov     rax, [rcx]
0x18005ea72  mov     rax, [rax+10h]
0x18005ea76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea7b  nop
0x18005ea7c  mov     rcx, [rbp+57h+var_48]
0x18005ea80  test    rcx, rcx
0x18005ea83  jz      short loc_18005EA96
0x18005ea85  mov     [rbp+57h+var_48], r12
0x18005ea89  mov     rax, [rcx]
0x18005ea8c  mov     rax, [rax+10h]
0x18005ea90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea95  nop
0x18005ea96  mov     rcx, [rbp+57h+var_40]
0x18005ea9a  test    rcx, rcx
0x18005ea9d  jz      short loc_18005EAB0
0x18005ea9f  mov     [rbp+57h+var_40], r12
0x18005eaa3  mov     rax, [rcx]
0x18005eaa6  mov     rax, [rax+10h]
0x18005eaaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eaaf  nop
0x18005eab0  mov     rcx, [rbp+57h+var_38]
0x18005eab4  test    rcx, rcx
0x18005eab7  jz      short loc_18005EACA
0x18005eab9  mov     [rbp+57h+var_38], r12
0x18005eabd  mov     rax, [rcx]
  ... truncated ...
```
