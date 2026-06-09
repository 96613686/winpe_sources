# SITE_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180011690`
- end: `0x1800119f0`
- name: `?ExecuteVerb@SITE_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `864`
- prototype: `__int64 __fastcall(SITE_OBJECT_EXTENSION *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x18000f234`
- `0x1800113c8`
- `0x180011690`
- `0x180012d34`
- `0x18002b564`
- `0x18002bcd4`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011767`
- `msvcrt!_wcsicmp` at `0x1800117aa`
- `msvcrt!_wcsicmp` at `0x1800118ae`
- `msvcrt!_wcsicmp` at `0x1800118e3`
- `msvcrt!_wcsicmp` at `0x18001192d`
- `msvcrt!_wcsicmp` at `0x180011941`
- `msvcrt!_wcsicmp` at `0x180011767`
- `msvcrt!_wcsicmp` at `0x1800117aa`
- `msvcrt!_wcsicmp` at `0x1800118ae`
- `msvcrt!_wcsicmp` at `0x1800118e3`
- `msvcrt!_wcsicmp` at `0x18001192d`
- `msvcrt!_wcsicmp` at `0x180011941`

## string_xrefs

- `0x1800118d9`: `DELETE`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::ExecuteVerb(
        SITE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  APP_OBJECT_UTILS *v11; // rcx
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  int v15; // eax
  int v16; // ecx
  APP_OBJECT_UTILS *v17; // rcx
  SITE_OBJECT_EXTENSION *v18; // rcx
  APP_OBJECT_UTILS *v19; // rcx
  APP_OBJECT_UTILS *v20; // rcx
  struct ICommandParameterList *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct SITE_OBJECT *v23; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v24; // [rsp+50h] [rbp-B0h]
  SITE_OBJECT_EXTENSION *v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  __int16 v29; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+90h] [rbp-70h]
  __int16 v31; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v32[510]; // [rsp+A2h] [rbp-5Eh] BYREF

  v24 = a2;
  v25 = this;
  v23 = 0;
  v22 = 0;
  memset_0(v32, 0, sizeof(v32));
  v28 = 512;
  v29 = 256;
  v27 = (const unsigned __int16 *)&v31;
  v30 = 0;
  v31 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
  {
    v12 = -2147024809;
    goto LABEL_32;
  }
  if ( !_wcsicmp(a3, L"ADD") )
  {
    v12 = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v11, a5, a4);
    if ( v12 < 0 )
      goto LABEL_32;
    v13 = SITE_OBJECT_EXTENSION::AddSite(v25, a5, a6, a7, a8);
    goto LABEL_14;
  }
  if ( !_wcsicmp(a3, L"LIST") )
  {
    v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a5 + 32LL))(a5);
    v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a5 + 40LL))(a5);
    v16 = v14 | 8;
    if ( v15 != 1 )
      v16 = v14;
    v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, int))(*(_QWORD *)a5 + 56LL))(
            a5,
            v24,
            a4,
            a6,
            a7,
            v16);
    goto LABEL_14;
  }
  v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
          a6,
          &v22);
  if ( v12 >= 0 )
  {
    if ( !*a4 )
    {
      v12 = APP_OBJECT_UTILS::PopParameter(v17, a5, v22, L"SITE.NAME", (struct STRU *)v26, 0, 1);
      if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147023483 )
        goto LABEL_32;
      a4 = v27;
    }
    v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct SITE_OBJECT **, _DWORD))(*(_QWORD *)a5 + 64LL))(
            a5,
            v24,
            a4,
            &v23,
            0);
    if ( v12 >= 0 )
    {
      if ( !_wcsicmp(a3, L"SET") )
      {
        v13 = SITE_OBJECT_EXTENSION::SetSite(v18, a5, v23, v22, a7, a8);
LABEL_14:
        v12 = v13;
        goto LABEL_32;
      }
      if ( _wcsicmp(a3, L"DELETE") )
      {
        if ( _wcsicmp(a3, L"START") && _wcsicmp(a3, L"STOP") )
        {
          v12 = -2147024846;
        }
        else
        {
          v12 = APP_OBJECT_UTILS::ValidateEmptyParameters(v20, a5, v22);
          if ( v12 >= 0 )
          {
            v13 = SITE_OBJECT_EXTENSION::ExecuteRscaCommand(v25, a5, a3, v23, a7);
            goto LABEL_14;
          }
        }
      }
      else
      {
        v12 = APP_OBJECT_UTILS::ValidateEmptyParameters(v19, a5, v22);
        if ( v12 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct SITE_OBJECT *, struct ICommandObjectList *))(*(_QWORD *)a5 + 176LL))(
                  a5,
                  v23,
                  a7);
          goto LABEL_14;
        }
      }
    }
  }
LABEL_32:
  if ( v23 )
  {
    (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180011690  push    rbp
0x180011692  push    rbx
0x180011693  push    rsi
0x180011694  push    rdi
0x180011695  push    r12
0x180011697  push    r13
0x180011699  push    r14
0x18001169b  push    r15
0x18001169d  lea     rbp, [rsp-1B8h]
0x1800116a5  sub     rsp, 2B8h
0x1800116ac  mov     rax, cs:__security_cookie
0x1800116b3  xor     rax, rsp
0x1800116b6  mov     [rbp+1F0h+var_50], rax
0x1800116bd  mov     rdi, [rbp+1F0h+arg_20]
0x1800116c4  xor     eax, eax
0x1800116c6  mov     r12, [rbp+1F0h+arg_28]
0x1800116cd  mov     rsi, r8
0x1800116d0  mov     r15, [rbp+1F0h+arg_30]
0x1800116d7  mov     rbx, rdx
0x1800116da  mov     r13, [rbp+1F0h+arg_38]
0x1800116e1  mov     r8d, 1FEh; Size
0x1800116e7  mov     [rsp+2F0h+var_2A0], rdx
0x1800116ec  mov     r14, r9
0x1800116ef  mov     [rsp+2F0h+var_298], rcx
0x1800116f4  xor     edx, edx; Val
0x1800116f6  lea     rcx, [rbp+1F0h+var_24E]; void *
0x1800116fa  mov     [rsp+2F0h+var_2A8], rax
0x1800116ff  mov     [rsp+2F0h+var_2B0], rax
0x180011704  call    memset_0
0x180011709  xor     ecx, ecx
0x18001170b  mov     [rbp+1F0h+var_268], 200h
0x180011712  mov     [rbp+1F0h+var_264], 100h
0x180011718  lea     rax, [rbp+1F0h+var_250]
0x18001171c  mov     [rbp+1F0h+var_270], rax
0x180011720  mov     [rbp+1F0h+var_260], ecx
0x180011723  mov     [rbp+1F0h+var_250], cx
0x180011727  test    rbx, rbx
0x18001172a  jz      loc_180011984
0x180011730  test    rsi, rsi
0x180011733  jz      loc_180011984
0x180011739  test    r14, r14
0x18001173c  jz      loc_180011984
0x180011742  test    rdi, rdi
0x180011745  jz      loc_180011984
0x18001174b  test    r12, r12
0x18001174e  jz      loc_180011984
0x180011754  test    r15, r15
0x180011757  jz      loc_180011984
0x18001175d  lea     rdx, aAdd_0; "ADD"
0x180011764  mov     rcx, rsi; String1
0x180011767  call    cs:__imp__wcsicmp
0x18001176d  test    eax, eax
0x18001176f  jnz     short loc_1800117A0
0x180011771  mov     r8, r14; unsigned __int16 *
0x180011774  mov     rdx, rdi; struct IExtensionContext *
0x180011777  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x18001177c  mov     ebx, eax
0x18001177e  test    eax, eax
0x180011780  js      loc_180011989
0x180011786  mov     rcx, [rsp+2F0h+var_298]; this
0x18001178b  mov     r9, r15; struct ICommandObjectList *
0x18001178e  mov     r8, r12; struct ICommandParameterList *
0x180011791  mov     [rsp+2F0h+var_2D0], r13; struct IXMLDOMDocument *
0x180011796  mov     rdx, rdi; struct IExtensionContext *
0x180011799  call    ?AddSite@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; SITE_OBJECT_EXTENSION::AddSite(IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x18001179e  jmp     short loc_180011802
0x1800117a0  lea     rdx, aList; "LIST"
0x1800117a7  mov     rcx, rsi; String1
0x1800117aa  call    cs:__imp__wcsicmp
0x1800117b0  test    eax, eax
0x1800117b2  jnz     short loc_180011809
0x1800117b4  mov     rax, [rdi]
0x1800117b7  mov     rcx, rdi
0x1800117ba  mov     rax, [rax+20h]
0x1800117be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117c3  mov     rcx, [rdi]
0x1800117c6  mov     ebx, eax
0x1800117c8  mov     rax, [rcx+28h]
0x1800117cc  mov     rcx, rdi
0x1800117cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117d4  mov     rdx, [rsp+2F0h+var_2A0]
0x1800117d9  mov     ecx, ebx
0x1800117db  or      ecx, 8
0x1800117de  mov     r9, r12
0x1800117e1  cmp     eax, 1
0x1800117e4  mov     r8, r14
0x1800117e7  mov     rax, [rdi]
0x1800117ea  cmovnz  ecx, ebx
0x1800117ed  mov     dword ptr [rsp+2F0h+var_2C8], ecx
0x1800117f1  mov     rcx, rdi
0x1800117f4  mov     [rsp+2F0h+var_2D0], r15
0x1800117f9  mov     rax, [rax+38h]
0x1800117fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011802  mov     ebx, eax
0x180011804  jmp     loc_180011989
0x180011809  mov     rax, [r12]
0x18001180d  lea     rdx, [rsp+2F0h+var_2B0]
0x180011812  mov     rcx, r12
0x180011815  mov     rax, [rax+50h]
0x180011819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001181e  xor     r12d, r12d
0x180011821  mov     ebx, eax
0x180011823  test    eax, eax
0x180011825  js      loc_180011989
0x18001182b  cmp     [r14], r12w
0x18001182f  jnz     short loc_180011879
0x180011831  mov     r8, [rsp+2F0h+var_2B0]; struct ICommandParameterList *
0x180011836  lea     rax, [rsp+2F0h+var_290]
0x18001183b  mov     [rsp+2F0h+var_2C0], 1; int
0x180011843  lea     r9, aSiteName; "SITE.NAME"
0x18001184a  mov     dword ptr [rsp+2F0h+var_2C8], r12d; int
0x18001184f  mov     rdx, rdi; struct IExtensionContext *
0x180011852  mov     [rsp+2F0h+var_2D0], rax; struct STRU *
0x180011857  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001185c  mov     ecx, 80000000h
0x180011861  mov     ebx, eax
0x180011863  add     eax, ecx
0x180011865  test    ecx, eax
0x180011867  jnz     short loc_180011875
0x180011869  cmp     ebx, 80070585h
0x18001186f  jnz     loc_180011989
0x180011875  mov     r14, [rbp+1F0h+var_270]
0x180011879  mov     rax, [rdi]
0x18001187c  lea     r9, [rsp+2F0h+var_2A8]
0x180011881  mov     rdx, [rsp+2F0h+var_2A0]
0x180011886  mov     r8, r14
0x180011889  mov     rcx, rdi
0x18001188c  mov     dword ptr [rsp+2F0h+var_2D0], r12d
0x180011891  mov     rax, [rax+40h]
0x180011895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001189a  mov     ebx, eax
0x18001189c  test    eax, eax
0x18001189e  js      loc_180011989
0x1800118a4  lea     rdx, aSet_0; "SET"
0x1800118ab  mov     rcx, rsi; String1
0x1800118ae  call    cs:__imp__wcsicmp
0x1800118b4  test    eax, eax
0x1800118b6  jnz     short loc_1800118D9
0x1800118b8  mov     r9, [rsp+2F0h+var_2B0]; struct ICommandParameterList *
0x1800118bd  mov     rdx, rdi; struct IExtensionContext *
0x1800118c0  mov     r8, [rsp+2F0h+var_2A8]; struct SITE_OBJECT *
0x1800118c5  mov     [rsp+2F0h+var_2C8], r13; struct IXMLDOMDocument *
0x1800118ca  mov     [rsp+2F0h+var_2D0], r15; struct ICommandObjectList *
0x1800118cf  call    ?SetSite@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVSITE_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; SITE_OBJECT_EXTENSION::SetSite(IExtensionContext *,SITE_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x1800118d4  jmp     loc_180011802
0x1800118d9  lea     rdx, aDelete_0; "DELETE"
0x1800118e0  mov     rcx, rsi; String1
0x1800118e3  call    cs:__imp__wcsicmp
0x1800118e9  test    eax, eax
0x1800118eb  jnz     short loc_180011923
0x1800118ed  mov     r8, [rsp+2F0h+var_2B0]; struct ICommandParameterList *
0x1800118f2  mov     rdx, rdi; struct IExtensionContext *
0x1800118f5  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x1800118fa  mov     ebx, eax
0x1800118fc  test    eax, eax
0x1800118fe  js      loc_180011989
0x180011904  mov     rax, [rdi]
0x180011907  mov     r8, r15
0x18001190a  mov     rdx, [rsp+2F0h+var_2A8]
0x18001190f  mov     rcx, rdi
0x180011912  mov     rax, [rax+0B0h]
0x180011919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001191e  jmp     loc_180011802
0x180011923  lea     rdx, aStart; "START"
0x18001192a  mov     rcx, rsi; String1
0x18001192d  call    cs:__imp__wcsicmp
0x180011933  test    eax, eax
0x180011935  jz      short loc_180011952
0x180011937  lea     rdx, aStop_0; "STOP"
0x18001193e  mov     rcx, rsi; String1
0x180011941  call    cs:__imp__wcsicmp
0x180011947  test    eax, eax
0x180011949  jz      short loc_180011952
0x18001194b  mov     ebx, 80070032h
0x180011950  jmp     short loc_180011989
0x180011952  mov     r8, [rsp+2F0h+var_2B0]; struct ICommandParameterList *
0x180011957  mov     rdx, rdi; struct IExtensionContext *
0x18001195a  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001195f  mov     ebx, eax
0x180011961  test    eax, eax
0x180011963  js      short loc_180011989
0x180011965  mov     r9, [rsp+2F0h+var_2A8]; struct ICommandObject *
0x18001196a  mov     r8, rsi; unsigned __int16 *
0x18001196d  mov     rcx, [rsp+2F0h+var_298]; this
0x180011972  mov     rdx, rdi; struct IExtensionContext *
0x180011975  mov     [rsp+2F0h+var_2D0], r15; struct ICommandObjectList *
0x18001197a  call    ?ExecuteRscaCommand@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandObject@@PEAVICommandObjectList@@@Z; SITE_OBJECT_EXTENSION::ExecuteRscaCommand(IExtensionContext *,ushort const *,ICommandObject *,ICommandObjectList *)
0x18001197f  jmp     loc_180011802
0x180011984  mov     ebx, 80070057h
0x180011989  mov     rcx, [rsp+2F0h+var_2A8]
0x18001198e  xor     edi, edi
0x180011990  test    rcx, rcx
0x180011993  jz      short loc_1800119A6
0x180011995  mov     rax, [rcx]
0x180011998  mov     rax, [rax+10h]
0x18001199c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a1  mov     [rsp+2F0h+var_2A8], rdi
0x1800119a6  mov     rcx, [rsp+2F0h+var_2B0]
0x1800119ab  test    rcx, rcx
0x1800119ae  jz      short loc_1800119C1
0x1800119b0  mov     rax, [rcx]
0x1800119b3  mov     rax, [rax+10h]
0x1800119b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119bc  mov     [rsp+2F0h+var_2B0], rdi
0x1800119c1  lea     rcx, [rsp+2F0h+var_290]; this
0x1800119c6  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800119cb  mov     eax, ebx
0x1800119cd  mov     rcx, [rbp+1F0h+var_50]
0x1800119d4  xor     rcx, rsp; StackCookie
0x1800119d7  call    __security_check_cookie
0x1800119dc  add     rsp, 2B8h
0x1800119e3  pop     r15
0x1800119e5  pop     r14
0x1800119e7  pop     r13
0x1800119e9  pop     r12
0x1800119eb  pop     rdi
0x1800119ec  pop     rsi
0x1800119ed  pop     rbx
0x1800119ee  pop     rbp
0x1800119ef  retn
```
