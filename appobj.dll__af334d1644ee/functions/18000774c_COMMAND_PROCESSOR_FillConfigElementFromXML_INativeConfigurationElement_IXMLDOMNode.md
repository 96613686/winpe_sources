# COMMAND_PROCESSOR::FillConfigElementFromXML(INativeConfigurationElement *,IXMLDOMNode *)

- ea: `0x18000774c`
- end: `0x180007f3e`
- name: `?FillConfigElementFromXML@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEAUIXMLDOMNode@@@Z`
- size: `2034`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, struct INativeConfigurationElement *, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000774c`
- `0x18000cd60`

## callees

- `0x18000774c`
- `0x18000aed4`
- `0x18002aa70`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007868`
- `OLEAUT32!__imp_SysAllocString` at `0x180007868`
- `OLEAUT32!__imp_SysFreeString` at `0x18000790e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180007eb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ece`
- `OLEAUT32!__imp_SysFreeString` at `0x18000790e`
- `OLEAUT32!__imp_SysFreeString` at `0x180007d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180007eb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ece`
- `OLEAUT32!__imp_VariantInit` at `0x1800077f2`
- `OLEAUT32!__imp_VariantInit` at `0x1800077f2`
- `OLEAUT32!__imp_VariantClear` at `0x1800078da`
- `OLEAUT32!__imp_VariantClear` at `0x180007f0c`
- `OLEAUT32!__imp_VariantClear` at `0x1800078da`
- `OLEAUT32!__imp_VariantClear` at `0x180007f0c`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::FillConfigElementFromXML(
        COMMAND_PROCESSOR *this,
        struct INativeConfigurationElement *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int v3; // r14d
  COMMAND_PROCESSOR *v4; // rsi
  OLECHAR *v5; // rdi
  struct PARAMETER_LIST *v6; // r13
  HRESULT matched; // ebx
  _QWORD *v10; // rsi
  unsigned int v11; // r15d
  int v12; // eax
  BOOL v13; // r14d
  unsigned int v14; // r15d
  COMMAND_PROCESSOR *v15; // rdi
  __int64 i; // rdx
  char *v17; // rax
  char *v18; // r9
  int v19; // ecx
  int v20; // r8d
  int v21; // eax
  int v22; // r14d
  APP_OBJECT_UTILS *v23; // rcx
  int AttributesFromXML; // eax
  unsigned int j; // edi
  COMMAND_PROCESSOR *v26; // rcx
  unsigned int v27; // r8d
  int v28; // eax
  struct INativeConfigurationElement *v31; // [rsp+38h] [rbp-C8h] BYREF
  struct IXMLDOMNode *v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh] BYREF
  struct PARAMETER_LIST *v36; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v41; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v42; // [rsp+7Ch] [rbp-84h]
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  struct INativeConfigurationElement *v46; // [rsp+98h] [rbp-68h]
  __int64 v47; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v49[192]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v4 = this;
  v45 = 0;
  v38 = 0;
  v32 = 0;
  v43 = 0;
  v44 = 0;
  v5 = 0;
  v40 = 0;
  v6 = 0;
  v39 = 0;
  v31 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v33 = 0;
  v36 = 0;
  v41 = 0;
  v34 = 0;
  v47 = 0;
  v46 = a2;
  v35 = 64;
  VariantInit(&pvarg);
  matched = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD *, unsigned int *))(*(_QWORD *)a2 + 96LL))(
              a2,
              v49,
              &v35);
  if ( matched >= 0 )
  {
    matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a3->lpVtbl->get_attributes)(a3, &v43);
    if ( matched >= 0 )
    {
      v10 = 0;
      v11 = 0;
      while ( v3 < v35 )
      {
        v10 = &v49[3 * v3];
        if ( !*(_DWORD *)v10 )
        {
          v5 = SysAllocString((const OLECHAR *)v10[1]);
          if ( !v5 )
          {
            matched = -2147024888;
            goto LABEL_73;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, struct IXMLDOMNode **))(*(_QWORD *)v43 + 56LL))(
                  v43,
                  v5,
                  &v32);
          matched = v12;
          if ( v12 )
          {
            if ( v12 < 0 )
              goto LABEL_73;
          }
          else
          {
            ((void (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v32->lpVtbl->get_nodeValue)(v32, &pvarg);
            matched = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD, LONGLONG, __int64 *))(*(_QWORD *)v46 + 160LL))(
                        v46,
                        v10[1],
                        pvarg.llVal,
                        &v45);
            if ( matched < 0 )
              goto LABEL_73;
            matched = VariantClear(&pvarg);
            if ( matched < 0 )
              goto LABEL_73;
            ++v11;
            ((void (__fastcall *)(struct IXMLDOMNode *))v32->lpVtbl->Release)(v32);
            v32 = 0;
          }
          SysFreeString(v5);
        }
        ++v3;
      }
      v5 = 0;
      matched = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 88LL))(v43, &v39);
      if ( matched < 0 )
        goto LABEL_73;
      if ( v39 > v11 )
      {
        matched = -2147024883;
        goto LABEL_73;
      }
      v13 = v11 != 0;
      matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a3->lpVtbl->get_childNodes)(a3, &v44);
      if ( matched >= 0 )
      {
        matched = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 64LL))(v44, &v40);
        if ( matched >= 0 )
        {
          v14 = 0;
          v42 = 0;
          v15 = this;
          while ( 1 )
          {
            if ( (int)v14 >= v40 )
            {
              v5 = 0;
              if ( matched >= 0 && !v13 )
                matched = 1;
              goto LABEL_73;
            }
            matched = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v44 + 56LL))(
                        v44,
                        v14,
                        &v32);
            if ( matched < 0 )
              goto LABEL_68;
            matched = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v32->lpVtbl->get_nodeName)(
                        v32,
                        &bstrString);
            if ( matched < 0 )
              goto LABEL_68;
            for ( i = 0; (unsigned int)i < v35; i = (unsigned int)(i + 1) )
            {
              v10 = &v49[3 * i];
              v17 = (char *)v10[1];
              v18 = (char *)((char *)bstrString - v17);
              do
              {
                v19 = *(unsigned __int16 *)&v18[(_QWORD)v17];
                v20 = *(unsigned __int16 *)v17 - v19;
                if ( v20 )
                  break;
                v17 += 2;
              }
              while ( v19 );
              if ( !v20 )
                break;
              v10 = 0;
            }
            if ( !v10 )
            {
LABEL_69:
              matched = -2147024883;
              goto LABEL_68;
            }
            if ( *(_DWORD *)v10 != 1 )
              break;
            matched = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, BSTR, struct INativeConfigurationElement **))(*(_QWORD *)v46 + 32LL))(
                        v46,
                        bstrString,
                        &v31);
            if ( matched < 0 )
              goto LABEL_68;
            v21 = COMMAND_PROCESSOR::FillConfigElementFromXML(v15, v31, v32);
            matched = v21;
            if ( v21 < 0 )
              goto LABEL_68;
            if ( v21 != 1 )
              v13 = 1;
            (*(void (**)(void))(*(_QWORD *)v31 + 16LL))();
            v31 = 0;
LABEL_66:
            ((void (__fastcall *)(struct IXMLDOMNode *))v32->lpVtbl->Release)(v32);
            v32 = 0;
            SysFreeString(bstrString);
            ++v14;
            bstrString = 0;
          }
          if ( (unsigned int)(*(_DWORD *)v10 - 2) > 2 )
            goto LABEL_69;
          v22 = 0;
          matched = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v46 + 40LL))(
                      v46,
                      &v33);
          if ( matched < 0 )
            goto LABEL_68;
          matched = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, &v41);
          if ( matched < 0 )
            goto LABEL_68;
          AttributesFromXML = APP_OBJECT_UTILS::GetAttributesFromXML(v23, v32, &v36);
          v6 = v36;
          matched = AttributesFromXML;
          if ( AttributesFromXML < 0 )
            goto LABEL_68;
          for ( j = 0; j < v41; ++j )
          {
            LODWORD(v36) = 0;
            matched = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v33 + 32LL))(
                        v33,
                        j,
                        &v31);
            if ( matched < 0 )
              goto LABEL_68;
            matched = COMMAND_PROCESSOR::MatchCollectionElement(v26, v31, v27, v6, (int *)&v36);
            if ( matched < 0 )
              goto LABEL_68;
            v22 = (int)v36;
            if ( (_DWORD)v36 )
            {
              v42 = j;
              goto LABEL_49;
            }
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
            v31 = 0;
          }
          j = v42;
LABEL_49:
          switch ( *(_DWORD *)v10 )
          {
            case 2:
              if ( !v22 )
              {
                matched = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v33 + 48LL))(
                            v33,
                            v10[1],
                            &v31);
                if ( matched < 0 )
                  goto LABEL_68;
              }
              matched = COMMAND_PROCESSOR::FillConfigElementFromXML(this, v31, v32);
              if ( matched < 0 )
                goto LABEL_68;
              if ( v22 )
                goto LABEL_65;
              break;
            case 3:
              matched = COMMAND_PROCESSOR::FillConfigElementFromXML(this, v31, v32);
              if ( matched < 0 )
                goto LABEL_68;
              if ( !v22 )
              {
                matched = -2147023728;
LABEL_68:
                v5 = 0;
                goto LABEL_73;
              }
              v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 64LL))(v33, j, &v38);
              goto LABEL_64;
            case 4:
              matched = COMMAND_PROCESSOR::FillConfigElementFromXML(this, v31, v32);
              if ( matched < 0 )
                goto LABEL_68;
              matched = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v33 + 48LL))(
                          v33,
                          L"clear",
                          &v31);
              if ( matched < 0 )
                goto LABEL_68;
              break;
            default:
              goto LABEL_69;
          }
          matched = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 40LL))(v33, &v34);
          if ( matched < 0 )
            goto LABEL_68;
          v28 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, _QWORD, __int64 *))(*(_QWORD *)v33 + 56LL))(
                  v33,
                  v31,
                  (unsigned int)-(v34 != 0),
                  &v38);
LABEL_64:
          matched = v28;
          if ( v28 < 0 )
            goto LABEL_68;
LABEL_65:
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          v33 = 0;
          (*(void (__fastcall **)(struct PARAMETER_LIST *))(*(_QWORD *)v6 + 16LL))(v6);
          v15 = this;
          v6 = 0;
          v36 = 0;
          v13 = 1;
          goto LABEL_66;
        }
      }
LABEL_73:
      v4 = this;
    }
  }
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *))(*((_QWORD *)v4 + 1) + 120LL))(
      (__int64)v4 + 8,
      (unsigned int)matched,
      &Str);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 24LL))(v38, &v47);
    (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*((_QWORD *)v4 + 1) + 128LL))(
      (__int64)v4 + 8,
      (unsigned int)matched,
      v47,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v32 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v32->lpVtbl->Release)(v32);
    v32 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v5 )
    SysFreeString(v5);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(struct PARAMETER_LIST *))(*(_QWORD *)v6 + 16LL))(v6);
  VariantClear(&pvarg);
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x18000774c  mov     [rsp-8+arg_18], rbx
0x180007751  push    rbp
0x180007752  push    rsi
0x180007753  push    rdi
0x180007754  push    r12
0x180007756  push    r13
0x180007758  push    r14
0x18000775a  push    r15
0x18000775c  lea     rbp, [rsp-5D0h]
0x180007764  sub     rsp, 6D0h
0x18000776b  mov     rax, cs:__security_cookie
0x180007772  xor     rax, rsp
0x180007775  mov     [rbp+600h+var_40], rax
0x18000777c  xor     r14d, r14d
0x18000777f  mov     [rsp+700h+var_6D0], rcx
0x180007784  mov     rsi, rcx
0x180007787  mov     [rbp+600h+var_670], r14
0x18000778b  xorps   xmm0, xmm0
0x18000778e  mov     [rsp+700h+var_698], r14
0x180007793  xor     eax, eax
0x180007795  mov     [rsp+700h+var_6C0], r14
0x18000779a  lea     rcx, [rbp+600h+pvarg]; pvarg
0x18000779e  mov     [rbp+600h+var_680], r14
0x1800077a2  mov     [rbp+600h+var_678], r14
0x1800077a6  mov     edi, r14d
0x1800077a9  mov     [rsp+700h+var_68C], r14d
0x1800077ae  mov     r13d, r14d
0x1800077b1  mov     [rsp+700h+var_690], r14d
0x1800077b6  mov     r12, r8
0x1800077b9  mov     [rsp+700h+var_6C8], r14
0x1800077be  mov     rbx, rdx
0x1800077c1  mov     [rsp+700h+bstrString], r14
0x1800077c6  movups  xmmword ptr [rbp+600h+pvarg], xmm0
0x1800077ca  mov     qword ptr [rbp+600h+pvarg+10h], rax
0x1800077ce  mov     [rsp+700h+var_6B8], r14
0x1800077d3  mov     [rsp+700h+var_6A8], r14
0x1800077d8  mov     [rsp+700h+var_688], r14d
0x1800077dd  mov     [rsp+700h+var_6B0], r14d
0x1800077e2  mov     [rbp+600h+var_660], r14
0x1800077e6  mov     [rbp+600h+var_668], rdx
0x1800077ea  mov     [rsp+700h+var_6AC], 40h ; '@'
0x1800077f2  call    cs:__imp_VariantInit
0x1800077f8  mov     rax, [rbx]
0x1800077fb  lea     r8, [rsp+700h+var_6AC]
0x180007800  lea     rdx, [rbp+600h+var_640]
0x180007804  mov     rcx, rbx
0x180007807  mov     rax, [rax+60h]
0x18000780b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007810  mov     ebx, eax
0x180007812  test    eax, eax
0x180007814  js      loc_180007DA3
0x18000781a  mov     rax, [r12]
0x18000781e  lea     rdx, [rbp+600h+var_680]
0x180007822  mov     rcx, r12
0x180007825  mov     rax, [rax+88h]
0x18000782c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007831  mov     ebx, eax
0x180007833  test    eax, eax
0x180007835  js      loc_180007DA3
0x18000783b  mov     esi, r14d
0x18000783e  mov     r15d, r14d
0x180007841  cmp     r14d, [rsp+700h+var_6AC]
0x180007846  jnb     loc_180007926
0x18000784c  mov     eax, r14d
0x18000784f  lea     rsi, [rbp+600h+var_640]
0x180007853  lea     rcx, [rax+rax*2]
0x180007857  lea     rsi, [rsi+rcx*8]
0x18000785b  cmp     [rsi], r13d
0x18000785e  jnz     loc_180007914
0x180007864  mov     rcx, [rsi+8]; psz
0x180007868  call    cs:__imp_SysAllocString
0x18000786e  mov     rdi, rax
0x180007871  test    rax, rax
0x180007874  jz      loc_18000791C
0x18000787a  mov     rcx, [rbp+600h+var_680]
0x18000787e  lea     r8, [rsp+700h+var_6C0]
0x180007883  mov     rdx, [rcx]
0x180007886  mov     rax, [rdx+38h]
0x18000788a  mov     rdx, rdi
0x18000788d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007892  mov     ebx, eax
0x180007894  test    eax, eax
0x180007896  jnz     short loc_180007905
0x180007898  mov     rcx, [rsp+700h+var_6C0]
0x18000789d  lea     rdx, [rbp+600h+pvarg]
0x1800078a1  mov     rax, [rcx]
0x1800078a4  mov     rax, [rax+40h]
0x1800078a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078ad  mov     rcx, [rbp+600h+var_668]
0x1800078b1  lea     r9, [rbp+600h+var_670]
0x1800078b5  mov     r8, qword ptr [rbp+600h+pvarg+8]
0x1800078b9  mov     rdx, [rsi+8]
0x1800078bd  mov     rax, [rcx]
0x1800078c0  mov     rax, [rax+0A0h]
0x1800078c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078cc  mov     ebx, eax
0x1800078ce  test    eax, eax
0x1800078d0  js      loc_180007D9E
0x1800078d6  lea     rcx, [rbp+600h+pvarg]; pvarg
0x1800078da  call    cs:__imp_VariantClear
0x1800078e0  mov     ebx, eax
0x1800078e2  test    eax, eax
0x1800078e4  js      loc_180007D9E
0x1800078ea  mov     rcx, [rsp+700h+var_6C0]
0x1800078ef  inc     r15d
0x1800078f2  mov     rax, [rcx]
0x1800078f5  mov     rax, [rax+10h]
0x1800078f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fe  mov     [rsp+700h+var_6C0], r13
0x180007903  jmp     short loc_18000790B
0x180007905  js      loc_180007D9E
0x18000790b  mov     rcx, rdi; bstrString
0x18000790e  call    cs:__imp_SysFreeString
0x180007914  inc     r14d
0x180007917  jmp     loc_180007841
0x18000791c  mov     ebx, 80070008h
0x180007921  jmp     loc_180007D9E
0x180007926  mov     rcx, [rbp+600h+var_680]
0x18000792a  lea     rdx, [rsp+700h+var_690]
0x18000792f  mov     rax, [rcx]
0x180007932  mov     rax, [rax+58h]
0x180007936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000793b  xor     edi, edi
0x18000793d  mov     ebx, eax
0x18000793f  test    eax, eax
0x180007941  js      loc_180007D9E
0x180007947  cmp     [rsp+700h+var_690], r15d
0x18000794c  jbe     short loc_180007958
0x18000794e  mov     ebx, 8007000Dh
0x180007953  jmp     loc_180007D9E
0x180007958  mov     rax, [r12]
0x18000795c  lea     rdx, [rbp+600h+var_678]
0x180007960  xor     r14d, r14d
0x180007963  mov     rcx, r12
0x180007966  test    r15d, r15d
0x180007969  mov     rax, [rax+60h]
0x18000796d  setnz   r14b
0x180007971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007976  mov     ebx, eax
0x180007978  test    eax, eax
0x18000797a  js      loc_180007D9E
0x180007980  mov     rcx, [rbp+600h+var_678]
0x180007984  lea     rdx, [rsp+700h+var_68C]
0x180007989  mov     rax, [rcx]
0x18000798c  mov     rax, [rax+40h]
0x180007990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007995  mov     ebx, eax
0x180007997  test    eax, eax
0x180007999  js      loc_180007D9E
0x18000799f  xor     r15d, r15d
0x1800079a2  mov     [rsp+700h+var_684], edi
0x1800079a6  mov     rdi, [rsp+700h+var_6D0]
0x1800079ab  lea     r12d, [r15+1]
0x1800079af  cmp     r15d, [rsp+700h+var_68C]
0x1800079b4  jge     loc_180007D90
0x1800079ba  mov     rcx, [rbp+600h+var_678]
0x1800079be  lea     r8, [rsp+700h+var_6C0]
0x1800079c3  mov     edx, r15d
0x1800079c6  mov     rax, [rcx]
0x1800079c9  mov     rax, [rax+38h]
0x1800079cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d2  mov     ebx, eax
0x1800079d4  test    eax, eax
0x1800079d6  js      loc_180007D85
0x1800079dc  mov     rcx, [rsp+700h+var_6C0]
0x1800079e1  lea     rdx, [rsp+700h+bstrString]
0x1800079e6  mov     rax, [rcx]
0x1800079e9  mov     rax, [rax+38h]
0x1800079ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f2  mov     ebx, eax
0x1800079f4  test    eax, eax
0x1800079f6  js      loc_180007D85
0x1800079fc  mov     r10d, [rsp+700h+var_6AC]
0x180007a01  xor     edx, edx
0x180007a03  test    r10d, r10d
0x180007a06  jz      short loc_180007A45
0x180007a08  mov     r9, [rsp+700h+bstrString]
0x180007a0d  lea     rcx, [rdx+rdx*2]
0x180007a11  lea     rsi, [rbp+600h+var_640]
0x180007a15  lea     rsi, [rsi+rcx*8]
0x180007a19  mov     rax, [rsi+8]
0x180007a1d  sub     r9, rax
0x180007a20  movzx   r8d, word ptr [rax]
0x180007a24  movzx   ecx, word ptr [rax+r9]
0x180007a29  sub     r8d, ecx
0x180007a2c  jnz     short loc_180007A36
0x180007a2e  add     rax, 2
0x180007a32  test    ecx, ecx
0x180007a34  jnz     short loc_180007A20
0x180007a36  test    r8d, r8d
0x180007a39  jz      short loc_180007A45
0x180007a3b  xor     esi, esi
0x180007a3d  add     edx, r12d
0x180007a40  cmp     edx, r10d
0x180007a43  jb      short loc_180007A08
0x180007a45  test    rsi, rsi
0x180007a48  jz      loc_180007D89
0x180007a4e  mov     eax, [rsi]
0x180007a50  cmp     eax, r12d
0x180007a53  jnz     short loc_180007AC5
0x180007a55  mov     r12, [rbp+600h+var_668]
0x180007a59  lea     r8, [rsp+700h+var_6C8]
0x180007a5e  mov     rdx, [rsp+700h+bstrString]
0x180007a63  mov     rcx, r12
0x180007a66  mov     rax, [r12]
0x180007a6a  mov     rax, [rax+20h]
0x180007a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a73  mov     ebx, eax
0x180007a75  test    eax, eax
0x180007a77  js      loc_180007D85
0x180007a7d  mov     r8, [rsp+700h+var_6C0]; struct IXMLDOMNode *
0x180007a82  mov     rcx, rdi; this
0x180007a85  mov     rdx, [rsp+700h+var_6C8]; struct INativeConfigurationElement *
0x180007a8a  call    ?FillConfigElementFromXML@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEAUIXMLDOMNode@@@Z; COMMAND_PROCESSOR::FillConfigElementFromXML(INativeConfigurationElement *,IXMLDOMNode *)
0x180007a8f  mov     ebx, eax
0x180007a91  test    eax, eax
0x180007a93  js      loc_180007D85
0x180007a99  mov     rcx, [rsp+700h+var_6C8]
0x180007a9e  mov     r12d, 1
0x180007aa4  cmp     eax, r12d
0x180007aa7  cmovnz  r14d, r12d
0x180007aab  mov     rax, [rcx]
0x180007aae  mov     rax, [rax+10h]
0x180007ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab7  mov     [rsp+700h+var_6C8], 0
0x180007ac0  jmp     loc_180007D4A
0x180007ac5  add     eax, 0FFFFFFFEh
0x180007ac8  cmp     eax, 2
0x180007acb  ja      loc_180007D89
0x180007ad1  mov     rcx, [rbp+600h+var_668]
0x180007ad5  lea     rdx, [rsp+700h+var_6B8]
0x180007ada  xor     r14d, r14d
0x180007add  mov     rax, [rcx]
0x180007ae0  mov     rax, [rax+28h]
0x180007ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae9  mov     ebx, eax
0x180007aeb  test    eax, eax
0x180007aed  js      loc_180007D85
0x180007af3  mov     rcx, [rsp+700h+var_6B8]
0x180007af8  lea     rdx, [rsp+700h+var_688]
0x180007afd  mov     rax, [rcx]
0x180007b00  mov     rax, [rax+18h]
0x180007b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b09  mov     ebx, eax
0x180007b0b  test    eax, eax
0x180007b0d  js      loc_180007D85
0x180007b13  mov     rdx, [rsp+700h+var_6C0]; struct IXMLDOMNode *
0x180007b18  lea     r8, [rsp+700h+var_6A8]; struct ICommandParameterList **
0x180007b1d  call    ?GetAttributesFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEAPEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::GetAttributesFromXML(IXMLDOMNode *,ICommandParameterList * *)
0x180007b22  mov     r13, [rsp+700h+var_6A8]
0x180007b27  mov     ebx, eax
0x180007b29  test    eax, eax
0x180007b2b  js      loc_180007D85
0x180007b31  xor     edi, edi
0x180007b33  cmp     edi, [rsp+700h+var_688]
0x180007b37  jnb     short loc_180007BB3
0x180007b39  mov     rcx, [rsp+700h+var_6B8]
0x180007b3e  lea     r8, [rsp+700h+var_6C8]
0x180007b43  mov     edx, edi
0x180007b45  mov     dword ptr [rsp+700h+var_6A8], 0
0x180007b4d  mov     rax, [rcx]
0x180007b50  mov     rax, [rax+20h]
0x180007b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b59  mov     ebx, eax
0x180007b5b  test    eax, eax
0x180007b5d  js      loc_180007D85
0x180007b63  mov     rdx, [rsp+700h+var_6C8]; struct INativeConfigurationElement *
0x180007b68  lea     rax, [rsp+700h+var_6A8]
0x180007b6d  mov     r9, r13; struct PARAMETER_LIST *
0x180007b70  mov     [rsp+700h+var_6E0], rax; int *
0x180007b75  call    ?MatchCollectionElement@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@KPEAVPARAMETER_LIST@@PEAH@Z; COMMAND_PROCESSOR::MatchCollectionElement(INativeConfigurationElement *,ulong,PARAMETER_LIST *,int *)
0x180007b7a  mov     ebx, eax
0x180007b7c  test    eax, eax
0x180007b7e  js      loc_180007D85
0x180007b84  mov     r14d, dword ptr [rsp+700h+var_6A8]
0x180007b89  test    r14d, r14d
0x180007b8c  jnz     short loc_180007BAD
0x180007b8e  mov     rcx, [rsp+700h+var_6C8]
0x180007b93  mov     rax, [rcx]
0x180007b96  mov     rax, [rax+10h]
0x180007b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9f  add     edi, r12d
0x180007ba2  mov     [rsp+700h+var_6C8], 0
0x180007bab  jmp     short loc_180007B33
0x180007bad  mov     [rsp+700h+var_684], edi
0x180007bb1  jmp     short loc_180007BB7
0x180007bb3  mov     edi, [rsp+700h+var_684]
0x180007bb7  cmp     dword ptr [rsi], 2
0x180007bba  jnz     short loc_180007C11
0x180007bbc  test    r14d, r14d
0x180007bbf  jnz     short loc_180007BE5
0x180007bc1  mov     rcx, [rsp+700h+var_6B8]
0x180007bc6  lea     r8, [rsp+700h+var_6C8]
0x180007bcb  mov     rdx, [rsi+8]
0x180007bcf  mov     rax, [rcx]
0x180007bd2  mov     rax, [rax+30h]
0x180007bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdb  mov     ebx, eax
0x180007bdd  test    eax, eax
0x180007bdf  js      loc_180007D85
  ... truncated ...
```
