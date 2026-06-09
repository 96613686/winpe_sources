# APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)

- ea: `0x18002ac98`
- end: `0x18002b0c3`
- name: `?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z`
- size: `1067`
- prototype: `__int64 __fastcall(APP_OBJECT_UTILS *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, struct STRU *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800267d4`
- `0x18002ac98`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180002ed0`
- `0x18002ac98`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18002aeb6`
- `msvcrt!wcsstr` at `0x18002aeb6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b009`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b01e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b009`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b01e`
- `OLEAUT32!__imp_VariantInit` at `0x18002ad4a`
- `OLEAUT32!__imp_VariantInit` at `0x18002ad4a`
- `OLEAUT32!__imp_VariantClear` at `0x18002aff9`
- `OLEAUT32!__imp_VariantClear` at `0x18002aff9`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
        APP_OBJECT_UTILS *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct STRU *a5)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  signed int v10; // ebx
  const unsigned __int8 *pbVal; // rdx
  unsigned int j; // edi
  const unsigned __int16 *v13; // rax
  int v14; // r8d
  int v15; // edx
  __int64 v16; // rax
  signed int NodeOrAttributeValueFromXML; // eax
  wchar_t *v18; // rax
  wchar_t *v19; // rdi
  const unsigned __int16 *v20; // rdi
  unsigned int i; // esi
  unsigned __int16 *v22; // rax
  int v23; // r8d
  int v24; // ecx
  struct IXMLDOMNode *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v33; // [rsp+60h] [rbp-A0h] BYREF
  LONGLONG llVal; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[32]; // [rsp+88h] [rbp-78h] BYREF
  char *v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+B0h] [rbp-50h]
  __int16 v39; // [rsp+B4h] [rbp-4Ch]
  int v40; // [rsp+B8h] [rbp-48h]
  __int16 v41; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[510]; // [rsp+C2h] [rbp-3Eh] BYREF

  v28 = 0;
  bstrString = 0;
  v33 = 0;
  llVal = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(v42, 0, sizeof(v42));
  v38 = 512;
  v37 = (char *)&v41;
  v39 = 256;
  v40 = 0;
  v41 = 0;
  v26 = 0;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  v29 = 0;
  VariantInit(&pvarg);
  if ( !a2 || !a3 || !a5 )
  {
    v10 = -2147024809;
    goto LABEL_43;
  }
  if ( *a3 )
  {
    v18 = wcsstr(a3, L"\\");
    v19 = v18;
    if ( v18 )
    {
      v10 = STRU::Copy((STRU *)v36, (const unsigned __int8 *)a3, v18 - a3);
      if ( v10 < 0 )
        goto LABEL_43;
      v20 = v19 + 1;
    }
    else
    {
      v10 = STRU::Copy((STRU *)v36, (const unsigned __int8 *)a3);
      if ( v10 < 0 )
        goto LABEL_43;
      v20 = &Str;
    }
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a2->lpVtbl->get_childNodes)(a2, &v31);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 64LL))(v31, &v29);
      if ( v10 >= 0 )
      {
        for ( i = 0; (int)i < v29; ++i )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v31 + 56LL))(
                  v31,
                  i,
                  &v26);
          if ( v10 < 0 )
            goto LABEL_43;
          v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v26->lpVtbl->get_nodeName)(v26, &bstrString);
          if ( v10 < 0 )
            goto LABEL_43;
          v22 = (unsigned __int16 *)v37;
          do
          {
            v23 = *(unsigned __int16 *)((char *)v22 + (char *)bstrString - v37);
            v24 = *v22 - v23;
            if ( v24 )
              break;
            ++v22;
          }
          while ( v23 );
          if ( !v24 )
          {
            NodeOrAttributeValueFromXML = APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(this, v26, v20, a4, a5);
            goto LABEL_22;
          }
          ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
          v26 = 0;
        }
        v10 = -2147023728;
      }
    }
  }
  else
  {
    lpVtbl = a2->lpVtbl;
    if ( a4 )
    {
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))lpVtbl->get_attributes)(a2, &v30);
      if ( v10 < 0 )
        goto LABEL_43;
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 88LL))(v30, &v28);
      if ( v10 < 0 )
        goto LABEL_43;
      for ( j = 0; ; ++j )
      {
        if ( (int)j >= v28 )
        {
          v10 = -2147023483;
          goto LABEL_43;
        }
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v30 + 80LL))(v30, j, &v27);
        if ( v10 < 0 )
          goto LABEL_43;
        v10 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v27 + 56))(v27, &v33);
        if ( v10 < 0 )
          goto LABEL_43;
        v13 = a4;
        do
        {
          v14 = *(const unsigned __int16 *)((char *)v13 + (char *)v33 - (char *)a4);
          v15 = *v13 - v14;
          if ( v15 )
            break;
          ++v13;
        }
        while ( v14 );
        v16 = *v27;
        if ( !v15 )
          break;
        (*(void (**)(void))(v16 + 16))();
        v27 = 0;
      }
      v10 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(v16 + 64))(v27, &pvarg);
      if ( v10 < 0 )
        goto LABEL_43;
      pbVal = pvarg.pbVal;
      llVal = pvarg.llVal;
    }
    else
    {
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LONGLONG *))lpVtbl->get_text)(a2, &llVal);
      if ( v10 < 0 )
        goto LABEL_43;
      pbVal = (const unsigned __int8 *)llVal;
    }
    NodeOrAttributeValueFromXML = STRU::Copy(a5, pbVal);
LABEL_22:
    v10 = NodeOrAttributeValueFromXML;
  }
LABEL_43:
  VariantClear(&pvarg);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v33 )
  {
    SysFreeString(v33);
    v33 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    v27 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002ac98  push    rbp
0x18002ac9a  push    rbx
0x18002ac9b  push    rsi
0x18002ac9c  push    rdi
0x18002ac9d  push    r12
0x18002ac9f  push    r13
0x18002aca1  push    r14
0x18002aca3  push    r15
0x18002aca5  lea     rbp, [rsp-1D8h]
0x18002acad  sub     rsp, 2D8h
0x18002acb4  mov     rax, cs:__security_cookie
0x18002acbb  xor     rax, rsp
0x18002acbe  mov     [rbp+210h+var_50], rax
0x18002acc5  mov     r15, [rbp+210h+arg_20]
0x18002accc  xor     r13d, r13d
0x18002accf  mov     rbx, r8
0x18002acd2  mov     [rsp+310h+var_2D0], r13d
0x18002acd7  mov     rsi, rdx
0x18002acda  mov     [rsp+310h+bstrString], r13
0x18002acdf  mov     r12, rcx
0x18002ace2  mov     [rsp+310h+var_2B0], r13
0x18002ace7  xorps   xmm0, xmm0
0x18002acea  mov     [rsp+310h+var_2A8], r13
0x18002acef  xor     eax, eax
0x18002acf1  lea     rcx, [rbp+210h+var_24E]; void *
0x18002acf5  xor     edx, edx; Val
0x18002acf7  mov     qword ptr [rbp+210h+pvarg+10h], rax
0x18002acfb  mov     r8d, 1FEh; Size
0x18002ad01  mov     r14, r9
0x18002ad04  movups  xmmword ptr [rsp+310h+pvarg], xmm0
0x18002ad09  call    memset_0
0x18002ad0e  lea     rax, [rbp+210h+var_250]
0x18002ad12  mov     [rbp+210h+var_260], 200h
0x18002ad19  lea     rcx, [rsp+310h+pvarg]; pvarg
0x18002ad1e  mov     [rbp+210h+var_268], rax
0x18002ad22  mov     [rbp+210h+var_25C], 100h
0x18002ad28  mov     [rbp+210h+var_258], r13d
0x18002ad2c  mov     [rbp+210h+var_250], r13w
0x18002ad31  mov     [rsp+310h+var_2E0], r13
0x18002ad36  mov     [rsp+310h+var_2D8], r13
0x18002ad3b  mov     [rsp+310h+var_2C8], r13
0x18002ad40  mov     [rsp+310h+var_2C0], r13
0x18002ad45  mov     [rsp+310h+var_2CC], r13d
0x18002ad4a  call    cs:__imp_VariantInit
0x18002ad50  test    rsi, rsi
0x18002ad53  jz      loc_18002AFEF
0x18002ad59  test    rbx, rbx
0x18002ad5c  jz      loc_18002AFEF
0x18002ad62  test    r15, r15
0x18002ad65  jz      loc_18002AFEF
0x18002ad6b  cmp     [rbx], r13w
0x18002ad6f  jnz     loc_18002AEAC
0x18002ad75  mov     rax, [rsi]
0x18002ad78  mov     rcx, rsi
0x18002ad7b  test    r14, r14
0x18002ad7e  jnz     short loc_18002ADA5
0x18002ad80  mov     rax, [rax+0D0h]
0x18002ad87  lea     rdx, [rsp+310h+var_2A8]
0x18002ad8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad91  mov     ebx, eax
0x18002ad93  test    eax, eax
0x18002ad95  js      loc_18002AFF4
0x18002ad9b  mov     rdx, [rsp+310h+var_2A8]
0x18002ada0  jmp     loc_18002AE93
0x18002ada5  mov     rax, [rax+88h]
0x18002adac  lea     rdx, [rsp+310h+var_2C8]
0x18002adb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adb6  mov     ebx, eax
0x18002adb8  test    eax, eax
0x18002adba  js      loc_18002AFF4
0x18002adc0  mov     rcx, [rsp+310h+var_2C8]
0x18002adc5  lea     rdx, [rsp+310h+var_2D0]
0x18002adca  mov     rax, [rcx]
0x18002adcd  mov     rax, [rax+58h]
0x18002add1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002add6  mov     ebx, eax
0x18002add8  test    eax, eax
0x18002adda  js      loc_18002AFF4
0x18002ade0  mov     edi, r13d
0x18002ade3  cmp     edi, [rsp+310h+var_2D0]
0x18002ade7  jge     loc_18002AEA2
0x18002aded  mov     rcx, [rsp+310h+var_2C8]
0x18002adf2  lea     r8, [rsp+310h+var_2D8]
0x18002adf7  mov     edx, edi
0x18002adf9  mov     rax, [rcx]
0x18002adfc  mov     rax, [rax+50h]
0x18002ae00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae05  mov     ebx, eax
0x18002ae07  test    eax, eax
0x18002ae09  js      loc_18002AFF4
0x18002ae0f  mov     rcx, [rsp+310h+var_2D8]
0x18002ae14  lea     rdx, [rsp+310h+var_2B0]
0x18002ae19  mov     rax, [rcx]
0x18002ae1c  mov     rax, [rax+38h]
0x18002ae20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae25  mov     ebx, eax
0x18002ae27  test    eax, eax
0x18002ae29  js      loc_18002AFF4
0x18002ae2f  mov     rcx, [rsp+310h+var_2B0]
0x18002ae34  mov     rax, r14
0x18002ae37  sub     rcx, r14
0x18002ae3a  movzx   edx, word ptr [rax]
0x18002ae3d  movzx   r8d, word ptr [rax+rcx]
0x18002ae42  sub     edx, r8d
0x18002ae45  jnz     short loc_18002AE50
0x18002ae47  add     rax, 2
0x18002ae4b  test    r8d, r8d
0x18002ae4e  jnz     short loc_18002AE3A
0x18002ae50  mov     rcx, [rsp+310h+var_2D8]
0x18002ae55  mov     rax, [rcx]
0x18002ae58  test    edx, edx
0x18002ae5a  jz      short loc_18002AE71
0x18002ae5c  mov     rax, [rax+10h]
0x18002ae60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae65  inc     edi
0x18002ae67  mov     [rsp+310h+var_2D8], r13
0x18002ae6c  jmp     loc_18002ADE3
0x18002ae71  mov     rax, [rax+40h]
0x18002ae75  lea     rdx, [rsp+310h+pvarg]
0x18002ae7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae7f  mov     ebx, eax
0x18002ae81  test    eax, eax
0x18002ae83  js      loc_18002AFF4
0x18002ae89  mov     rdx, qword ptr [rsp+310h+pvarg+8]; unsigned __int16 *
0x18002ae8e  mov     [rsp+310h+var_2A8], rdx
0x18002ae93  mov     rcx, r15; this
0x18002ae96  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002ae9b  mov     ebx, eax
0x18002ae9d  jmp     loc_18002AFF4
0x18002aea2  mov     ebx, 80070585h
0x18002aea7  jmp     loc_18002AFF4
0x18002aeac  lea     rdx, asc_180039420; "\\"
0x18002aeb3  mov     rcx, rbx; Str
0x18002aeb6  call    cs:__imp_wcsstr
0x18002aebc  mov     rdx, rbx; unsigned __int16 *
0x18002aebf  lea     rcx, [rbp+210h+var_288]; this
0x18002aec3  mov     rdi, rax
0x18002aec6  test    rax, rax
0x18002aec9  jnz     short loc_18002AEE3
0x18002aecb  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002aed0  mov     ebx, eax
0x18002aed2  test    eax, eax
0x18002aed4  js      loc_18002AFF4
0x18002aeda  lea     rdi, Str
0x18002aee1  jmp     short loc_18002AEFF
0x18002aee3  mov     r8, rdi
0x18002aee6  sub     r8, rbx
0x18002aee9  sar     r8, 1; unsigned int
0x18002aeec  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002aef1  mov     ebx, eax
0x18002aef3  test    eax, eax
0x18002aef5  js      loc_18002AFF4
0x18002aefb  add     rdi, 2
0x18002aeff  mov     rax, [rsi]
0x18002af02  lea     rdx, [rsp+310h+var_2C0]
0x18002af07  mov     rcx, rsi
0x18002af0a  mov     rax, [rax+60h]
0x18002af0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af13  mov     ebx, eax
0x18002af15  test    eax, eax
0x18002af17  js      loc_18002AFF4
0x18002af1d  mov     rcx, [rsp+310h+var_2C0]
0x18002af22  lea     rdx, [rsp+310h+var_2CC]
0x18002af27  mov     rax, [rcx]
0x18002af2a  mov     rax, [rax+40h]
0x18002af2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af33  mov     ebx, eax
0x18002af35  test    eax, eax
0x18002af37  js      loc_18002AFF4
0x18002af3d  mov     esi, r13d
0x18002af40  cmp     esi, [rsp+310h+var_2CC]
0x18002af44  jge     loc_18002AFE8
0x18002af4a  mov     rcx, [rsp+310h+var_2C0]
0x18002af4f  lea     r8, [rsp+310h+var_2E0]
0x18002af54  mov     edx, esi
0x18002af56  mov     rax, [rcx]
0x18002af59  mov     rax, [rax+38h]
0x18002af5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af62  mov     ebx, eax
0x18002af64  test    eax, eax
0x18002af66  js      loc_18002AFF4
0x18002af6c  mov     rcx, [rsp+310h+var_2E0]
0x18002af71  lea     rdx, [rsp+310h+bstrString]
0x18002af76  mov     rax, [rcx]
0x18002af79  mov     rax, [rax+38h]
0x18002af7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af82  mov     ebx, eax
0x18002af84  test    eax, eax
0x18002af86  js      short loc_18002AFF4
0x18002af88  mov     rax, [rbp+210h+var_268]
0x18002af8c  mov     rdx, [rsp+310h+bstrString]
0x18002af91  sub     rdx, rax
0x18002af94  movzx   ecx, word ptr [rax]
0x18002af97  movzx   r8d, word ptr [rax+rdx]
0x18002af9c  sub     ecx, r8d
0x18002af9f  jnz     short loc_18002AFAA
0x18002afa1  add     rax, 2
0x18002afa5  test    r8d, r8d
0x18002afa8  jnz     short loc_18002AF94
0x18002afaa  test    ecx, ecx
0x18002afac  jz      short loc_18002AFCB
0x18002afae  mov     rcx, [rsp+310h+var_2E0]
0x18002afb3  mov     rax, [rcx]
0x18002afb6  mov     rax, [rax+10h]
0x18002afba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002afbf  inc     esi
0x18002afc1  mov     [rsp+310h+var_2E0], r13
0x18002afc6  jmp     loc_18002AF40
0x18002afcb  mov     rdx, [rsp+310h+var_2E0]; struct IXMLDOMNode *
0x18002afd0  mov     r9, r14; unsigned __int16 *
0x18002afd3  mov     r8, rdi; unsigned __int16 *
0x18002afd6  mov     [rsp+310h+var_2F0], r15; struct STRU *
0x18002afdb  mov     rcx, r12; this
0x18002afde  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x18002afe3  jmp     loc_18002AE9B
0x18002afe8  mov     ebx, 80070490h
0x18002afed  jmp     short loc_18002AFF4
0x18002afef  mov     ebx, 80070057h
0x18002aff4  lea     rcx, [rsp+310h+pvarg]; pvarg
0x18002aff9  call    cs:__imp_VariantClear
0x18002afff  mov     rcx, [rsp+310h+bstrString]; bstrString
0x18002b004  test    rcx, rcx
0x18002b007  jz      short loc_18002B014
0x18002b009  call    cs:__imp_SysFreeString
0x18002b00f  mov     [rsp+310h+bstrString], r13
0x18002b014  mov     rcx, [rsp+310h+var_2B0]; bstrString
0x18002b019  test    rcx, rcx
0x18002b01c  jz      short loc_18002B029
0x18002b01e  call    cs:__imp_SysFreeString
0x18002b024  mov     [rsp+310h+var_2B0], r13
0x18002b029  mov     rcx, [rsp+310h+var_2E0]
0x18002b02e  test    rcx, rcx
0x18002b031  jz      short loc_18002B044
0x18002b033  mov     rax, [rcx]
0x18002b036  mov     rax, [rax+10h]
0x18002b03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b03f  mov     [rsp+310h+var_2E0], r13
0x18002b044  mov     rcx, [rsp+310h+var_2D8]
0x18002b049  test    rcx, rcx
0x18002b04c  jz      short loc_18002B05F
0x18002b04e  mov     rax, [rcx]
0x18002b051  mov     rax, [rax+10h]
0x18002b055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b05a  mov     [rsp+310h+var_2D8], r13
0x18002b05f  mov     rcx, [rsp+310h+var_2C8]
0x18002b064  test    rcx, rcx
0x18002b067  jz      short loc_18002B07A
0x18002b069  mov     rax, [rcx]
0x18002b06c  mov     rax, [rax+10h]
0x18002b070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b075  mov     [rsp+310h+var_2C8], r13
0x18002b07a  mov     rcx, [rsp+310h+var_2C0]
0x18002b07f  test    rcx, rcx
0x18002b082  jz      short loc_18002B095
0x18002b084  mov     rax, [rcx]
0x18002b087  mov     rax, [rax+10h]
0x18002b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b090  mov     [rsp+310h+var_2C0], r13
0x18002b095  lea     rcx, [rbp+210h+var_288]; this
0x18002b099  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002b09e  mov     eax, ebx
0x18002b0a0  mov     rcx, [rbp+210h+var_50]
0x18002b0a7  xor     rcx, rsp; StackCookie
0x18002b0aa  call    __security_check_cookie
0x18002b0af  add     rsp, 2D8h
0x18002b0b6  pop     r15
0x18002b0b8  pop     r14
0x18002b0ba  pop     r13
0x18002b0bc  pop     r12
0x18002b0be  pop     rdi
0x18002b0bf  pop     rsi
0x18002b0c0  pop     rbx
0x18002b0c1  pop     rbp
0x18002b0c2  retn
```
