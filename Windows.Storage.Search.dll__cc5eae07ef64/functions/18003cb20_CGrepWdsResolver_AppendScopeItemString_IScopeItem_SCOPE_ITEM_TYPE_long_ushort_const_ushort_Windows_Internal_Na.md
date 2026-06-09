# CGrepWdsResolver::_AppendScopeItemString(IScopeItem *,SCOPE_ITEM_TYPE,long (*)(ushort const *,ushort * *),Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> *)

- ea: `0x18003cb20`
- end: `0x18003ccfe`
- name: `?_AppendScopeItemString@CGrepWdsResolver@@AEAAJPEAUIScopeItem@@W4SCOPE_ITEM_TYPE@@P6AJPEBGPEAPEAG@ZPEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c96c`

## callees

- `0x18003c364`
- `0x18003cb20`
- `0x18003d55c`
- `0x18003ed00`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccad`

## string_xrefs

- `0x18003cc63`: `Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGrepWdsResolver::_AppendScopeItemString(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 (__fastcall *a4)(LPVOID, LPVOID *),
        __int64 a5)
{
  int appended; // edi
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, LPVOID *); // rbx
  WCHAR *v11; // rsi
  void *v12; // rbx
  const wchar_t *v13; // r9
  const wchar_t *v14; // r8
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v18[4]; // [rsp+40h] [rbp-20h] BYREF
  int v19; // [rsp+80h] [rbp+20h] BYREF
  int v20; // [rsp+84h] [rbp+24h]
  LPVOID v21; // [rsp+88h] [rbp+28h] BYREF

  v20 = HIDWORD(a1);
  v19 = 0;
  appended = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 48LL))(a2, &v19);
  if ( appended >= 0 )
  {
    v17 = 0;
    appended = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)a2 + 120LL))(
                 a2,
                 &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                 &v17);
    if ( appended >= 0 )
    {
      v21 = 0;
      v9 = v17;
      v10 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v17 + 40LL);
      CoTaskMemFree(0);
      appended = v10(v9, 2147647488LL, &v21);
      if ( appended >= 0 )
      {
        memset(v18, 0, 24);
        if ( a4 )
        {
          pv = 0;
          CoTaskMemFree(0);
          appended = a4(v21, &pv);
          v11 = (WCHAR *)pv;
          pv = 0;
          CoTaskMemFree(0);
        }
        else
        {
          appended = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                       v18,
                       v21,
                       -1);
          v11 = (WCHAR *)v18[0];
        }
        if ( appended >= 0 )
        {
          pv = 0;
          CoTaskMemFree(0);
          appended = ScopeStrEscapeValue(v11, (unsigned __int16 **)&pv);
          v12 = pv;
          if ( appended >= 0 )
          {
            v13 = L"=";
            if ( a3 != 1 )
              v13 = L"<>";
            v14 = L"Directory";
            if ( v19 != 1 )
              v14 = L"Scope";
            appended = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::AppendFormat(
                         a5,
                         L"%s %s '%s'",
                         v14,
                         v13,
                         pv);
          }
          CoTaskMemFree(v12);
        }
        if ( v11 )
          CoTaskMemFree(v11);
      }
      CoTaskMemFree(v21);
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003cb20  mov     [rsp-18h+arg_10], rbx
0x18003cb25  mov     [rsp-18h+arg_18], rsi
0x18003cb2a  mov     [rsp-18h+arg_0], rcx
0x18003cb2f  push    rbp
0x18003cb30  push    rdi
0x18003cb31  push    r14
0x18003cb33  mov     rbp, rsp
0x18003cb36  sub     rsp, 60h
0x18003cb3a  mov     rsi, r9
0x18003cb3d  mov     r14d, r8d
0x18003cb40  mov     rbx, rdx
0x18003cb43  mov     dword ptr [rbp+arg_0], 0
0x18003cb4a  mov     rax, [rdx]
0x18003cb4d  lea     rdx, [rbp+arg_0]
0x18003cb51  mov     rcx, rbx
0x18003cb54  mov     rax, [rax+30h]
0x18003cb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb5d  mov     edi, eax
0x18003cb5f  test    eax, eax
0x18003cb61  js      loc_18003CCCA
0x18003cb67  mov     [rbp+var_28], 0
0x18003cb6f  mov     rax, [rbx]
0x18003cb72  lea     r8, [rbp+var_28]
0x18003cb76  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18003cb7d  mov     rcx, rbx
0x18003cb80  mov     rax, [rax+78h]
0x18003cb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb89  mov     edi, eax
0x18003cb8b  test    eax, eax
0x18003cb8d  js      loc_18003CCB4
0x18003cb93  mov     [rbp+arg_8], 0
0x18003cb9b  mov     rdi, [rbp+var_28]
0x18003cb9f  mov     rax, [rdi]
0x18003cba2  mov     rbx, [rax+28h]
0x18003cba6  xor     ecx, ecx; pv
0x18003cba8  call    cs:__imp_CoTaskMemFree
0x18003cbae  lea     r8, [rbp+arg_8]
0x18003cbb2  mov     edx, 80028000h
0x18003cbb7  mov     rcx, rdi
0x18003cbba  mov     rax, rbx
0x18003cbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbc2  mov     edi, eax
0x18003cbc4  test    eax, eax
0x18003cbc6  js      loc_18003CCA9
0x18003cbcc  mov     [rbp+var_20], 0
0x18003cbd4  mov     [rbp+var_18], 0
0x18003cbdc  mov     [rbp+var_10], 0
0x18003cbe4  test    rsi, rsi
0x18003cbe7  jz      loc_18003CCE1
0x18003cbed  mov     [rbp+pv], 0
0x18003cbf5  xor     ecx, ecx; pv
0x18003cbf7  call    cs:__imp_CoTaskMemFree
0x18003cbfd  lea     rdx, [rbp+pv]
0x18003cc01  mov     rcx, [rbp+arg_8]
0x18003cc05  mov     rax, rsi
0x18003cc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc0d  mov     edi, eax
0x18003cc0f  mov     rsi, [rbp+pv]
0x18003cc13  mov     [rbp+pv], 0
0x18003cc1b  xor     ecx, ecx; pv
0x18003cc1d  call    cs:__imp_CoTaskMemFree
0x18003cc23  test    edi, edi
0x18003cc25  js      short loc_18003CC9A
0x18003cc27  mov     [rbp+pv], 0
0x18003cc2f  xor     ecx, ecx; pv
0x18003cc31  call    cs:__imp_CoTaskMemFree
0x18003cc37  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18003cc3b  mov     rcx, rsi; pszStr
0x18003cc3e  call    ?ScopeStrEscapeValue@@YAJPEBGPEAPEAG@Z; ScopeStrEscapeValue(ushort const *,ushort * *)
0x18003cc43  mov     edi, eax
0x18003cc45  mov     rbx, [rbp+pv]
0x18003cc49  test    eax, eax
0x18003cc4b  js      short loc_18003CC90
0x18003cc4d  lea     rax, asc_1800F8A9C; "<>"
0x18003cc54  lea     r9, asc_1800F8AA4; "="
0x18003cc5b  cmp     r14d, 1
0x18003cc5f  cmovnz  r9, rax
0x18003cc63  lea     r8, aDirectory; "Directory"
0x18003cc6a  lea     rax, aScope_0; "Scope"
0x18003cc71  cmp     dword ptr [rbp+arg_0], 1
0x18003cc75  cmovnz  r8, rax
0x18003cc79  mov     [rsp+60h+var_40], rbx
0x18003cc7e  lea     rdx, aSSS_0; "%s %s '%s'"
0x18003cc85  mov     rcx, [rbp+arg_20]
0x18003cc89  call    ?AppendFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::AppendFormat(ushort const *,...)
0x18003cc8e  mov     edi, eax
0x18003cc90  mov     rcx, rbx; pv
0x18003cc93  call    cs:__imp_CoTaskMemFree
0x18003cc99  nop
0x18003cc9a  test    rsi, rsi
0x18003cc9d  jz      short loc_18003CCA9
0x18003cc9f  mov     rcx, rsi; pv
0x18003cca2  call    cs:__imp_CoTaskMemFree
0x18003cca8  nop
0x18003cca9  mov     rcx, [rbp+arg_8]; pv
0x18003ccad  call    cs:__imp_CoTaskMemFree
0x18003ccb3  nop
0x18003ccb4  mov     rcx, [rbp+var_28]
0x18003ccb8  test    rcx, rcx
0x18003ccbb  jz      short loc_18003CCCA
0x18003ccbd  mov     rax, [rcx]
0x18003ccc0  mov     rax, [rax+10h]
0x18003ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccc9  nop
0x18003ccca  mov     eax, edi
0x18003cccc  lea     r11, [rsp+60h+var_s0]
0x18003ccd1  mov     rbx, [r11+30h]
0x18003ccd5  mov     rsi, [r11+38h]
0x18003ccd9  mov     rsp, r11
0x18003ccdc  pop     r14
0x18003ccde  pop     rdi
0x18003ccdf  pop     rbp
0x18003cce0  retn
0x18003cce1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003cce5  mov     rdx, [rbp+arg_8]
0x18003cce9  lea     rcx, [rbp+var_20]
0x18003cced  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003ccf2  mov     edi, eax
0x18003ccf4  mov     rsi, [rbp+var_20]
0x18003ccf8  jmp     loc_18003CC23
```
