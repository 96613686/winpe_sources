# TRACE_OBJECT::Create(IExtensionContext *,ushort const *,ushort const *,IXMLDOMDocument *)

- ea: `0x180026aec`
- end: `0x180026f70`
- name: `?Create@TRACE_OBJECT@@QEAAJPEAVIExtensionContext@@PEBG1PEAUIXMLDOMDocument@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(TRACE_OBJECT *__hidden this, struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026f78`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180005ba8`
- `0x180026aec`
- `0x18002a7e4`
- `0x18002aa70`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180026dd8`: `processId`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT::Create(
        TRACE_OBJECT *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IXMLDOMDocument *a5)
{
  struct ICommandParameterList *v9; // rdi
  struct SITE_OBJECT *v10; // r15
  int v11; // ebx
  APP_OBJECT_UTILS *v12; // rcx
  int AttributesFromXML; // eax
  APP_OBJECT_UTILS *v14; // rcx
  APP_OBJECT_UTILS *v15; // rcx
  APP_OBJECT_UTILS *v16; // rcx
  APP_OBJECT_UTILS *v17; // rcx
  int SiteById; // eax
  unsigned __int16 *v19; // r8
  APP_OBJECT_UTILS *v20; // rcx
  APP_OBJECT_UTILS *v21; // rcx
  unsigned int i; // r14d
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMNode *v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v26; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v27; // [rsp+58h] [rbp-A8h] BYREF
  struct SITE_OBJECT *v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v30; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[32]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h]
  __int16 v34; // [rsp+A4h] [rbp-5Ch]
  int v35; // [rsp+A8h] [rbp-58h]
  _BYTE v36[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v37; // [rsp+D0h] [rbp-30h]
  int v38; // [rsp+D8h] [rbp-28h]
  __int16 v39; // [rsp+DCh] [rbp-24h]
  int v40; // [rsp+E0h] [rbp-20h]
  __int16 v41; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v42[510]; // [rsp+F2h] [rbp-Eh] BYREF
  __int16 v43; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v44[510]; // [rsp+2F2h] [rbp+1F2h] BYREF

  memset_0(v42, 0, sizeof(v42));
  v39 = 256;
  v40 = 0;
  v41 = 0;
  v9 = 0;
  v27 = 0;
  v24 = 0;
  v37 = (unsigned __int16 *)&v41;
  v38 = 512;
  memset_0(v44, 0, sizeof(v44));
  v33 = 512;
  v32 = (unsigned __int16 *)&v43;
  v10 = 0;
  v34 = 256;
  v35 = 0;
  v43 = 0;
  v30 = 0;
  v29 = 0;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  if ( a5 && a3 && a4 && a2 )
  {
    *((_QWORD *)this + 28) = a5;
    ((void (__fastcall *)(struct IXMLDOMDocument *))a5->lpVtbl->AddRef)(a5);
    v11 = COMMAND_OBJECT::AddAttribute(this, L"TRACE.NAME", a4);
    if ( v11 >= 0 )
    {
      v11 = COMMAND_OBJECT::AddAttribute(this, L"PATH", a3);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMNode **))(**((_QWORD **)this + 28) + 360LL))(
                *((_QWORD *)this + 28),
                &v25);
        if ( v11 >= 0 )
        {
          AttributesFromXML = APP_OBJECT_UTILS::GetAttributesFromXML(v12, v25, &v27);
          v9 = v27;
          v11 = AttributesFromXML;
          if ( AttributesFromXML >= 0 )
          {
            v11 = APP_OBJECT_UTILS::PopParameter(v14, a2, v27, L"URL", (struct STRU *)v31, 0, 1);
            if ( v11 >= 0 )
            {
              v11 = COMMAND_OBJECT::AddAttribute(this, L"URL", v32);
              if ( v11 >= 0 )
              {
                v11 = APP_OBJECT_UTILS::PopParameter(v15, a2, v9, L"STATUSCODE", (struct STRU *)v31, 0, 1);
                if ( v11 >= 0 )
                {
                  v11 = COMMAND_OBJECT::AddAttribute(this, L"STATUSCODE", v32);
                  if ( v11 >= 0 )
                  {
                    v11 = APP_OBJECT_UTILS::PopParameter(v16, a2, v9, L"siteid", (struct STRU *)v31, 0, 1);
                    if ( v11 >= 0 )
                    {
                      v11 = COMMAND_OBJECT::AddAttribute(this, L"SITE.ID", v32);
                      if ( v11 >= 0 )
                      {
                        SiteById = APP_OBJECT_UTILS::FindSiteById(v17, a2, v32, &v28);
                        v10 = v28;
                        if ( SiteById >= 0 )
                        {
                          v11 = (*(__int64 (__fastcall **)(struct SITE_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v28 + 80LL))(
                                  v28,
                                  L"SITE.NAME",
                                  &v26);
                          if ( v11 < 0 )
                            goto LABEL_33;
                          v19 = v26;
                        }
                        else
                        {
                          v19 = L"<Unknown>";
                          v26 = L"<Unknown>";
                        }
                        v11 = COMMAND_OBJECT::AddAttribute(this, L"SITE.NAME", v19);
                        if ( v11 >= 0 )
                        {
                          v11 = APP_OBJECT_UTILS::PopParameter(v20, a2, v9, L"processId", (struct STRU *)v31, 0, 1);
                          if ( v11 >= 0 )
                          {
                            v11 = COMMAND_OBJECT::AddAttribute(this, L"WP.NAME", v32);
                            if ( v11 >= 0 )
                            {
                              v11 = APP_OBJECT_UTILS::PopParameter(v21, a2, v9, L"appPoolId", (struct STRU *)v31, 0, 1);
                              if ( v11 >= 0 )
                              {
                                v11 = COMMAND_OBJECT::AddAttribute(this, L"APPPOOL.NAME", v32);
                                if ( v11 >= 0 )
                                {
                                  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)v9 + 24LL))(
                                          v9,
                                          &v24);
                                  if ( v11 >= 0 )
                                  {
                                    for ( i = 0; i < v24; ++i )
                                    {
                                      v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v9 + 32LL))(
                                              v9,
                                              i,
                                              &v30,
                                              &v29);
                                      if ( v11 < 0 )
                                        goto LABEL_33;
                                      v11 = COMMAND_OBJECT::AddAttribute(this, v30, v29);
                                      if ( v11 < 0 )
                                        goto LABEL_33;
                                    }
                                    v11 = STRU::Copy((STRU *)v36, (const unsigned __int8 *)a4);
                                    if ( v11 >= 0 )
                                      v11 = STRU::Copy(
                                              (TRACE_OBJECT *)((char *)this + 16),
                                              (const unsigned __int8 *)v37);
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_33:
  if ( v25 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v10 )
    (*(void (__fastcall **)(struct SITE_OBJECT *))(*(_QWORD *)v10 + 16LL))(v10);
  BUFFER::~BUFFER((BUFFER *)v31);
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180026aec  push    rbp
0x180026aee  push    rbx
0x180026aef  push    rsi
0x180026af0  push    rdi
0x180026af1  push    r12
0x180026af3  push    r13
0x180026af5  push    r14
0x180026af7  push    r15
0x180026af9  lea     rbp, [rsp-408h]
0x180026b01  sub     rsp, 508h
0x180026b08  mov     rax, cs:__security_cookie
0x180026b0f  xor     rax, rsp
0x180026b12  mov     [rbp+440h+var_50], rax
0x180026b19  mov     r12, r8
0x180026b1c  mov     r14, rdx
0x180026b1f  mov     rsi, rcx
0x180026b22  mov     r15d, 1FEh
0x180026b28  mov     r8d, r15d; Size
0x180026b2b  lea     rcx, [rbp+440h+var_44E]; void *
0x180026b2f  xor     edx, edx; Val
0x180026b31  mov     r13, r9
0x180026b34  call    memset_0
0x180026b39  xor     ecx, ecx
0x180026b3b  mov     [rbp+440h+var_464], 100h
0x180026b41  mov     [rbp+440h+var_460], ecx
0x180026b44  lea     rax, [rbp+440h+var_450]
0x180026b48  mov     [rbp+440h+var_450], cx
0x180026b4c  lea     ebx, [r15+2]
0x180026b50  mov     edi, ecx
0x180026b52  mov     [rsp+540h+var_4E8], rcx
0x180026b57  mov     [rsp+540h+var_500], ecx
0x180026b5b  mov     r8d, r15d; Size
0x180026b5e  lea     rcx, [rbp+440h+var_24E]; void *
0x180026b65  mov     [rbp+440h+var_470], rax
0x180026b69  xor     edx, edx; Val
0x180026b6b  mov     [rbp+440h+var_468], ebx
0x180026b6e  call    memset_0
0x180026b73  mov     rcx, [rbp+440h+arg_20]
0x180026b7a  lea     rax, [rbp+440h+var_250]
0x180026b81  mov     [rbp+440h+var_4A0], ebx
0x180026b84  xor     ebx, ebx
0x180026b86  mov     [rbp+440h+var_4A8], rax
0x180026b8a  mov     r15d, ebx
0x180026b8d  mov     [rbp+440h+var_49C], 100h
0x180026b93  mov     [rbp+440h+var_498], ebx
0x180026b96  mov     [rbp+440h+var_250], bx
0x180026b9d  mov     [rsp+540h+var_4D0], rbx
0x180026ba2  mov     [rsp+540h+var_4D8], rbx
0x180026ba7  mov     [rsp+540h+var_4F8], rbx
0x180026bac  mov     [rsp+540h+var_4F0], rbx
0x180026bb1  mov     [rsp+540h+var_4E0], rbx
0x180026bb6  test    rcx, rcx
0x180026bb9  jz      loc_180026EEC
0x180026bbf  test    r12, r12
0x180026bc2  jz      loc_180026EEC
0x180026bc8  test    r13, r13
0x180026bcb  jz      loc_180026EEC
0x180026bd1  test    r14, r14
0x180026bd4  jz      loc_180026EEC
0x180026bda  mov     [rsi+0E0h], rcx
0x180026be1  mov     rax, [rcx]
0x180026be4  mov     rax, [rax+8]
0x180026be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bed  mov     r8, r13; unsigned __int16 *
0x180026bf0  lea     rdx, aTraceName; "TRACE.NAME"
0x180026bf7  mov     rcx, rsi; this
0x180026bfa  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026bff  mov     ebx, eax
0x180026c01  test    eax, eax
0x180026c03  js      loc_180026EF1
0x180026c09  mov     r8, r12; unsigned __int16 *
0x180026c0c  lea     rdx, aPath; "PATH"
0x180026c13  mov     rcx, rsi; this
0x180026c16  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026c1b  xor     r12d, r12d
0x180026c1e  mov     ebx, eax
0x180026c20  test    eax, eax
0x180026c22  js      loc_180026EF1
0x180026c28  mov     rcx, [rsi+0E0h]
0x180026c2f  lea     rdx, [rsp+540h+var_4F8]
0x180026c34  mov     rax, [rcx]
0x180026c37  mov     rax, [rax+168h]
0x180026c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c43  mov     ebx, eax
0x180026c45  test    eax, eax
0x180026c47  js      loc_180026EF1
0x180026c4d  mov     rdx, [rsp+540h+var_4F8]; struct IXMLDOMNode *
0x180026c52  lea     r8, [rsp+540h+var_4E8]; struct ICommandParameterList **
0x180026c57  call    ?GetAttributesFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEAPEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::GetAttributesFromXML(IXMLDOMNode *,ICommandParameterList * *)
0x180026c5c  mov     rdi, [rsp+540h+var_4E8]
0x180026c61  mov     ebx, eax
0x180026c63  test    eax, eax
0x180026c65  js      loc_180026EF1
0x180026c6b  mov     [rsp+540h+var_510], 1; int
0x180026c73  lea     rax, [rsp+540h+var_4C8]
0x180026c78  mov     [rsp+540h+var_518], r12d; int
0x180026c7d  lea     r9, aUrl; "URL"
0x180026c84  mov     r8, rdi; struct ICommandParameterList *
0x180026c87  mov     [rsp+540h+var_520], rax; struct STRU *
0x180026c8c  mov     rdx, r14; struct IExtensionContext *
0x180026c8f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180026c94  mov     ebx, eax
0x180026c96  test    eax, eax
0x180026c98  js      loc_180026EF1
0x180026c9e  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026ca2  lea     rdx, aUrl; "URL"
0x180026ca9  mov     rcx, rsi; this
0x180026cac  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026cb1  mov     ebx, eax
0x180026cb3  test    eax, eax
0x180026cb5  js      loc_180026EF1
0x180026cbb  mov     [rsp+540h+var_510], 1; int
0x180026cc3  lea     rax, [rsp+540h+var_4C8]
0x180026cc8  mov     [rsp+540h+var_518], r12d; int
0x180026ccd  lea     r9, aStatuscode; "STATUSCODE"
0x180026cd4  mov     r8, rdi; struct ICommandParameterList *
0x180026cd7  mov     [rsp+540h+var_520], rax; struct STRU *
0x180026cdc  mov     rdx, r14; struct IExtensionContext *
0x180026cdf  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180026ce4  mov     ebx, eax
0x180026ce6  test    eax, eax
0x180026ce8  js      loc_180026EF1
0x180026cee  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026cf2  lea     rdx, aStatuscode; "STATUSCODE"
0x180026cf9  mov     rcx, rsi; this
0x180026cfc  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026d01  mov     ebx, eax
0x180026d03  test    eax, eax
0x180026d05  js      loc_180026EF1
0x180026d0b  mov     [rsp+540h+var_510], 1; int
0x180026d13  lea     rax, [rsp+540h+var_4C8]
0x180026d18  mov     [rsp+540h+var_518], r12d; int
0x180026d1d  lea     r9, aSiteid; "siteid"
0x180026d24  mov     r8, rdi; struct ICommandParameterList *
0x180026d27  mov     [rsp+540h+var_520], rax; struct STRU *
0x180026d2c  mov     rdx, r14; struct IExtensionContext *
0x180026d2f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180026d34  mov     ebx, eax
0x180026d36  test    eax, eax
0x180026d38  js      loc_180026EF1
0x180026d3e  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026d42  lea     rdx, aSiteId; "SITE.ID"
0x180026d49  mov     rcx, rsi; this
0x180026d4c  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026d51  mov     ebx, eax
0x180026d53  test    eax, eax
0x180026d55  js      loc_180026EF1
0x180026d5b  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026d5f  lea     r9, [rsp+540h+var_4E0]; struct SITE_OBJECT **
0x180026d64  mov     rdx, r14; struct IExtensionContext *
0x180026d67  call    ?FindSiteById@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::FindSiteById(IExtensionContext *,ushort const *,SITE_OBJECT * *)
0x180026d6c  mov     r15, [rsp+540h+var_4E0]
0x180026d71  test    eax, eax
0x180026d73  jns     short loc_180026D83
0x180026d75  lea     r8, aUnknown_1; "<Unknown>"
0x180026d7c  mov     [rsp+540h+var_4F0], r8
0x180026d81  jmp     short loc_180026DAD
0x180026d83  mov     rax, [r15]
0x180026d86  lea     r8, [rsp+540h+var_4F0]
0x180026d8b  lea     rdx, aSiteName; "SITE.NAME"
0x180026d92  mov     rcx, r15
0x180026d95  mov     rax, [rax+50h]
0x180026d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d9e  mov     ebx, eax
0x180026da0  test    eax, eax
0x180026da2  js      loc_180026EF1
0x180026da8  mov     r8, [rsp+540h+var_4F0]; unsigned __int16 *
0x180026dad  lea     rdx, aSiteName; "SITE.NAME"
0x180026db4  mov     rcx, rsi; this
0x180026db7  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026dbc  mov     ebx, eax
0x180026dbe  test    eax, eax
0x180026dc0  js      loc_180026EF1
0x180026dc6  mov     [rsp+540h+var_510], 1; int
0x180026dce  lea     rax, [rsp+540h+var_4C8]
0x180026dd3  mov     [rsp+540h+var_518], r12d; int
0x180026dd8  lea     r9, aProcessid; "processId"
0x180026ddf  mov     r8, rdi; struct ICommandParameterList *
0x180026de2  mov     [rsp+540h+var_520], rax; struct STRU *
0x180026de7  mov     rdx, r14; struct IExtensionContext *
0x180026dea  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180026def  mov     ebx, eax
0x180026df1  test    eax, eax
0x180026df3  js      loc_180026EF1
0x180026df9  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026dfd  lea     rdx, aWpName_0; "WP.NAME"
0x180026e04  mov     rcx, rsi; this
0x180026e07  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026e0c  mov     ebx, eax
0x180026e0e  test    eax, eax
0x180026e10  js      loc_180026EF1
0x180026e16  mov     [rsp+540h+var_510], 1; int
0x180026e1e  lea     rax, [rsp+540h+var_4C8]
0x180026e23  mov     [rsp+540h+var_518], r12d; int
0x180026e28  lea     r9, aApppoolid; "appPoolId"
0x180026e2f  mov     r8, rdi; struct ICommandParameterList *
0x180026e32  mov     [rsp+540h+var_520], rax; struct STRU *
0x180026e37  mov     rdx, r14; struct IExtensionContext *
0x180026e3a  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180026e3f  mov     ebx, eax
0x180026e41  test    eax, eax
0x180026e43  js      loc_180026EF1
0x180026e49  mov     r8, [rbp+440h+var_4A8]; unsigned __int16 *
0x180026e4d  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x180026e54  mov     rcx, rsi; this
0x180026e57  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026e5c  mov     ebx, eax
0x180026e5e  test    eax, eax
0x180026e60  js      loc_180026EF1
0x180026e66  mov     rax, [rdi]
0x180026e69  lea     rdx, [rsp+540h+var_500]
0x180026e6e  mov     rcx, rdi
0x180026e71  mov     rax, [rax+18h]
0x180026e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e7a  mov     ebx, eax
0x180026e7c  test    eax, eax
0x180026e7e  js      short loc_180026EF1
0x180026e80  mov     r14d, r12d
0x180026e83  cmp     r14d, [rsp+540h+var_500]
0x180026e88  jnb     short loc_180026EC9
0x180026e8a  mov     rax, [rdi]
0x180026e8d  lea     r9, [rsp+540h+var_4D8]
0x180026e92  lea     r8, [rsp+540h+var_4D0]
0x180026e97  mov     edx, r14d
0x180026e9a  mov     rcx, rdi
0x180026e9d  mov     rax, [rax+20h]
0x180026ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea6  mov     ebx, eax
0x180026ea8  test    eax, eax
0x180026eaa  js      short loc_180026EF1
0x180026eac  mov     r8, [rsp+540h+var_4D8]; unsigned __int16 *
0x180026eb1  mov     rcx, rsi; this
0x180026eb4  mov     rdx, [rsp+540h+var_4D0]; unsigned __int16 *
0x180026eb9  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026ebe  mov     ebx, eax
0x180026ec0  test    eax, eax
0x180026ec2  js      short loc_180026EF1
0x180026ec4  inc     r14d
0x180026ec7  jmp     short loc_180026E83
0x180026ec9  mov     rdx, r13; unsigned __int16 *
0x180026ecc  lea     rcx, [rbp+440h+var_490]; this
0x180026ed0  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026ed5  mov     ebx, eax
0x180026ed7  test    eax, eax
0x180026ed9  js      short loc_180026EF1
0x180026edb  mov     rdx, [rbp+440h+var_470]; unsigned __int16 *
0x180026edf  lea     rcx, [rsi+10h]; this
0x180026ee3  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026ee8  mov     ebx, eax
0x180026eea  jmp     short loc_180026EF1
0x180026eec  mov     ebx, 80070057h
0x180026ef1  mov     rcx, [rsp+540h+var_4F8]
0x180026ef6  test    rcx, rcx
0x180026ef9  jz      short loc_180026F10
0x180026efb  mov     rax, [rcx]
0x180026efe  mov     rax, [rax+10h]
0x180026f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f07  mov     [rsp+540h+var_4F8], 0
0x180026f10  test    rdi, rdi
0x180026f13  jz      short loc_180026F24
0x180026f15  mov     rax, [rdi]
0x180026f18  mov     rcx, rdi
0x180026f1b  mov     rax, [rax+10h]
0x180026f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f24  test    r15, r15
0x180026f27  jz      short loc_180026F38
0x180026f29  mov     rax, [r15]
0x180026f2c  mov     rcx, r15
0x180026f2f  mov     rax, [rax+10h]
0x180026f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f38  lea     rcx, [rsp+540h+var_4C8]; this
0x180026f3d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026f42  lea     rcx, [rbp+440h+var_490]; this
0x180026f46  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026f4b  mov     eax, ebx
0x180026f4d  mov     rcx, [rbp+440h+var_50]
0x180026f54  xor     rcx, rsp; StackCookie
0x180026f57  call    __security_check_cookie
0x180026f5c  add     rsp, 508h
0x180026f63  pop     r15
0x180026f65  pop     r14
0x180026f67  pop     r13
0x180026f69  pop     r12
0x180026f6b  pop     rdi
0x180026f6c  pop     rsi
0x180026f6d  pop     rbx
0x180026f6e  pop     rbp
0x180026f6f  retn
```
