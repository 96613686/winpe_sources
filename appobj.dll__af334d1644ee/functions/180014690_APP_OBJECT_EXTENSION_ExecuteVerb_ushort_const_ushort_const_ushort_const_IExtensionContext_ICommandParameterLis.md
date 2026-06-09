# APP_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180014690`
- end: `0x180014a37`
- name: `?ExecuteVerb@APP_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(APP_OBJECT_EXTENSION *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180013504`
- `0x180014690`
- `0x180015138`
- `0x18002b564`
- `0x18002bb20`
- `0x18002bcd4`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014777`
- `msvcrt!_wcsicmp` at `0x1800147c4`
- `msvcrt!_wcsicmp` at `0x18001491b`
- `msvcrt!_wcsicmp` at `0x180014944`
- `msvcrt!_wcsicmp` at `0x180014983`
- `msvcrt!_wcsicmp` at `0x180014777`
- `msvcrt!_wcsicmp` at `0x1800147c4`
- `msvcrt!_wcsicmp` at `0x18001491b`
- `msvcrt!_wcsicmp` at `0x180014944`
- `msvcrt!_wcsicmp` at `0x180014983`

## string_xrefs

- `0x180014979`: `DELETE`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_EXTENSION::ExecuteVerb(
        APP_OBJECT_EXTENSION *this,
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
  APP_OBJECT_UTILS *v14; // rcx
  int v15; // eax
  __int64 v16; // r8
  APP_OBJECT_UTILS *v17; // rcx
  APP_OBJECT_EXTENSION *v18; // rcx
  APP_OBJECT_UTILS *v19; // rcx
  struct APP_OBJECT *v21; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandParameterList *v22; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String2; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMDocument *v26; // [rsp+70h] [rbp-90h]
  APP_OBJECT_EXTENSION *v27; // [rsp+78h] [rbp-88h]
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v29; // [rsp+A0h] [rbp-60h]
  int v30; // [rsp+A8h] [rbp-58h]
  __int16 v31; // [rsp+ACh] [rbp-54h]
  int v32; // [rsp+B0h] [rbp-50h]
  __int16 v33; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v34[510]; // [rsp+C2h] [rbp-3Eh] BYREF

  v27 = this;
  v26 = a8;
  v21 = 0;
  v23 = 0;
  String1 = 0;
  v22 = 0;
  memset_0(v34, 0, sizeof(v34));
  v30 = 512;
  v29 = (const unsigned __int16 *)&v33;
  v31 = 256;
  v32 = 0;
  v33 = 0;
  String2 = 0;
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
    v13 = APP_OBJECT_EXTENSION::AddApp(v27, a5, a4, a6, a7, v26);
    goto LABEL_12;
  }
  if ( !_wcsicmp(a3, L"LIST") )
  {
    v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)a5 + 56LL))(
            a5,
            a2,
            a4,
            a6,
            a7,
            0);
LABEL_12:
    v12 = v13;
    goto LABEL_32;
  }
  v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
          a6,
          &v22);
  if ( v12 >= 0 )
  {
    if ( *a4 )
    {
LABEL_20:
      v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct APP_OBJECT **, _DWORD))(*(_QWORD *)a5 + 64LL))(
              a5,
              a2,
              a4,
              &v21,
              0);
      if ( v12 >= 0 )
      {
        v12 = APP_OBJECT_UTILS::ResolveUrl(v17, a4, 0, (const unsigned __int16 **)&String2, 0);
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(struct APP_OBJECT *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v21 + 80LL))(
                  v21,
                  L"path",
                  &String1);
          if ( v12 >= 0 )
          {
            if ( _wcsicmp(String1, String2) )
            {
              *(_QWORD *)&v23 = a2;
              v16 = 3221226508LL;
              *((_QWORD *)&v23 + 1) = a3;
              goto LABEL_17;
            }
            if ( !_wcsicmp(a3, L"SET") )
            {
              v13 = APP_OBJECT_EXTENSION::SetApp(v18, a5, v21, v22, a7, v26, 0);
              goto LABEL_12;
            }
            if ( _wcsicmp(a3, L"DELETE") )
            {
              v12 = -2147024846;
            }
            else
            {
              v12 = APP_OBJECT_UTILS::ValidateEmptyParameters(v19, a5, v22);
              if ( v12 >= 0 )
              {
                v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct APP_OBJECT *, struct ICommandObjectList *))(*(_QWORD *)a5 + 176LL))(
                        a5,
                        v21,
                        a7);
                goto LABEL_12;
              }
            }
          }
        }
      }
      goto LABEL_32;
    }
    v15 = APP_OBJECT_UTILS::PopParameter(v14, a5, v22, L"APP.NAME", (struct STRU *)v28, 0, 1);
    v12 = v15;
    if ( v15 == -2147023483 )
    {
      *((_QWORD *)&v23 + 1) = L"APP.NAME";
      *(_QWORD *)&v23 = L"APP";
      v16 = 3221226474LL;
LABEL_17:
      v12 = -2147024846;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a5 + 144LL))(
        a5,
        2147942450LL,
        v16,
        &v23,
        0);
      goto LABEL_32;
    }
    if ( v15 >= 0 )
    {
      a4 = v29;
      goto LABEL_20;
    }
  }
LABEL_32:
  if ( v21 )
  {
    (*(void (__fastcall **)(struct APP_OBJECT *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v28);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014690  push    rbp
0x180014692  push    rbx
0x180014693  push    rsi
0x180014694  push    rdi
0x180014695  push    r12
0x180014697  push    r13
0x180014699  push    r14
0x18001469b  push    r15
0x18001469d  lea     rbp, [rsp-1D8h]
0x1800146a5  sub     rsp, 2D8h
0x1800146ac  mov     rax, cs:__security_cookie
0x1800146b3  xor     rax, rsp
0x1800146b6  mov     [rbp+210h+var_50], rax
0x1800146bd  mov     rax, [rbp+210h+arg_38]
0x1800146c4  xor     ebx, ebx
0x1800146c6  mov     rdi, [rbp+210h+arg_20]
0x1800146cd  mov     r14, r8
0x1800146d0  mov     r15, [rbp+210h+arg_28]
0x1800146d7  mov     r13, rdx
0x1800146da  mov     r12, [rbp+210h+arg_30]
0x1800146e1  xorps   xmm0, xmm0
0x1800146e4  mov     [rsp+310h+var_298], rcx
0x1800146e9  xor     edx, edx; Val
0x1800146eb  mov     r8d, 1FEh; Size
0x1800146f1  mov     [rsp+310h+var_2A0], rax
0x1800146f6  lea     rcx, [rbp+210h+var_24E]; void *
0x1800146fa  mov     [rsp+310h+var_2D0], rbx
0x1800146ff  movups  [rsp+310h+var_2C0], xmm0
0x180014704  mov     [rsp+310h+String1], rbx
0x180014709  mov     rsi, r9
0x18001470c  mov     [rsp+310h+var_2C8], rbx
0x180014711  call    memset_0
0x180014716  mov     [rbp+210h+var_268], 200h
0x18001471d  lea     rax, [rbp+210h+var_250]
0x180014721  mov     [rbp+210h+var_270], rax
0x180014725  mov     [rbp+210h+var_264], 100h
0x18001472b  mov     [rbp+210h+var_260], ebx
0x18001472e  mov     [rbp+210h+var_250], bx
0x180014732  mov     [rsp+310h+String2], rbx
0x180014737  test    r13, r13
0x18001473a  jz      loc_1800149C6
0x180014740  test    r14, r14
0x180014743  jz      loc_1800149C6
0x180014749  test    rsi, rsi
0x18001474c  jz      loc_1800149C6
0x180014752  test    rdi, rdi
0x180014755  jz      loc_1800149C6
0x18001475b  test    r15, r15
0x18001475e  jz      loc_1800149C6
0x180014764  test    r12, r12
0x180014767  jz      loc_1800149C6
0x18001476d  lea     rdx, aAdd_0; "ADD"
0x180014774  mov     rcx, r14; String1
0x180014777  call    cs:__imp__wcsicmp
0x18001477d  test    eax, eax
0x18001477f  jnz     short loc_1800147BA
0x180014781  mov     r8, rsi; unsigned __int16 *
0x180014784  mov     rdx, rdi; struct IExtensionContext *
0x180014787  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x18001478c  mov     ebx, eax
0x18001478e  test    eax, eax
0x180014790  js      loc_1800149CB
0x180014796  mov     rax, [rsp+310h+var_2A0]
0x18001479b  mov     r9, r15; struct ICommandParameterList *
0x18001479e  mov     rcx, [rsp+310h+var_298]; this
0x1800147a3  mov     r8, rsi; unsigned __int16 *
0x1800147a6  mov     [rsp+310h+var_2E8], rax; struct IXMLDOMDocument *
0x1800147ab  mov     rdx, rdi; struct IExtensionContext *
0x1800147ae  mov     [rsp+310h+var_2F0], r12; struct ICommandObjectList *
0x1800147b3  call    ?AddApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; APP_OBJECT_EXTENSION::AddApp(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x1800147b8  jmp     short loc_1800147EF
0x1800147ba  lea     rdx, aList; "LIST"
0x1800147c1  mov     rcx, r14; String1
0x1800147c4  call    cs:__imp__wcsicmp
0x1800147ca  test    eax, eax
0x1800147cc  jnz     short loc_1800147F6
0x1800147ce  mov     rax, [rdi]
0x1800147d1  mov     r9, r15
0x1800147d4  mov     dword ptr [rsp+310h+var_2E8], ebx
0x1800147d8  mov     r8, rsi
0x1800147db  mov     rdx, r13
0x1800147de  mov     [rsp+310h+var_2F0], r12
0x1800147e3  mov     rcx, rdi
0x1800147e6  mov     rax, [rax+38h]
0x1800147ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ef  mov     ebx, eax
0x1800147f1  jmp     loc_1800149CB
0x1800147f6  mov     rax, [r15]
0x1800147f9  lea     rdx, [rsp+310h+var_2C8]
0x1800147fe  mov     rcx, r15
0x180014801  mov     rax, [rax+50h]
0x180014805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001480a  xor     r15d, r15d
0x18001480d  mov     ebx, eax
0x18001480f  test    eax, eax
0x180014811  js      loc_1800149CB
0x180014817  cmp     [rsi], r15w
0x18001481b  jnz     loc_1800148A2
0x180014821  mov     r8, [rsp+310h+var_2C8]; struct ICommandParameterList *
0x180014826  lea     rax, [rbp+210h+var_290]
0x18001482a  mov     [rsp+310h+var_2E0], 1; int
0x180014832  lea     rsi, aAppName_0; "APP.NAME"
0x180014839  mov     r9, rsi; unsigned __int16 *
0x18001483c  mov     dword ptr [rsp+310h+var_2E8], r15d; int
0x180014841  mov     rdx, rdi; struct IExtensionContext *
0x180014844  mov     [rsp+310h+var_2F0], rax; struct STRU *
0x180014849  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001484e  mov     ebx, eax
0x180014850  cmp     eax, 80070585h
0x180014855  jnz     short loc_180014896
0x180014857  lea     rax, aApp_0; "APP"
0x18001485e  mov     qword ptr [rsp+310h+var_2C0+8], rsi
0x180014863  mov     qword ptr [rsp+310h+var_2C0], rax
0x180014868  mov     r8d, 0C00003EAh
0x18001486e  mov     rax, [rdi]
0x180014871  lea     r9, [rsp+310h+var_2C0]
0x180014876  mov     ebx, 80070032h
0x18001487b  mov     dword ptr [rsp+310h+var_2F0], r15d
0x180014880  mov     edx, ebx
0x180014882  mov     rcx, rdi
0x180014885  mov     rax, [rax+90h]
0x18001488c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014891  jmp     loc_1800149CB
0x180014896  test    eax, eax
0x180014898  js      loc_1800149CB
0x18001489e  mov     rsi, [rbp+210h+var_270]
0x1800148a2  mov     rax, [rdi]
0x1800148a5  lea     r9, [rsp+310h+var_2D0]
0x1800148aa  mov     r8, rsi
0x1800148ad  mov     dword ptr [rsp+310h+var_2F0], r15d
0x1800148b2  mov     rdx, r13
0x1800148b5  mov     rcx, rdi
0x1800148b8  mov     rax, [rax+40h]
0x1800148bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c1  mov     ebx, eax
0x1800148c3  test    eax, eax
0x1800148c5  js      loc_1800149CB
0x1800148cb  lea     r9, [rsp+310h+String2]; unsigned __int16 **
0x1800148d0  mov     [rsp+310h+var_2F0], r15; int *
0x1800148d5  xor     r8d, r8d; struct STRU *
0x1800148d8  mov     rdx, rsi; unsigned __int16 *
0x1800148db  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x1800148e0  mov     ebx, eax
0x1800148e2  test    eax, eax
0x1800148e4  js      loc_1800149CB
0x1800148ea  mov     rcx, [rsp+310h+var_2D0]
0x1800148ef  lea     r8, [rsp+310h+String1]
0x1800148f4  lea     rdx, aPath_1; "path"
0x1800148fb  mov     rax, [rcx]
0x1800148fe  mov     rax, [rax+50h]
0x180014902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014907  mov     ebx, eax
0x180014909  test    eax, eax
0x18001490b  js      loc_1800149CB
0x180014911  mov     rdx, [rsp+310h+String2]; String2
0x180014916  mov     rcx, [rsp+310h+String1]; String1
0x18001491b  call    cs:__imp__wcsicmp
0x180014921  test    eax, eax
0x180014923  jz      short loc_18001493A
0x180014925  mov     qword ptr [rsp+310h+var_2C0], r13
0x18001492a  mov     r8d, 0C000040Ch
0x180014930  mov     qword ptr [rsp+310h+var_2C0+8], r14
0x180014935  jmp     loc_18001486E
0x18001493a  lea     rdx, aSet_0; "SET"
0x180014941  mov     rcx, r14; String1
0x180014944  call    cs:__imp__wcsicmp
0x18001494a  test    eax, eax
0x18001494c  jnz     short loc_180014979
0x18001494e  mov     rax, [rsp+310h+var_2A0]
0x180014953  mov     rdx, rdi; struct IExtensionContext *
0x180014956  mov     r9, [rsp+310h+var_2C8]; struct ICommandParameterList *
0x18001495b  mov     r8, [rsp+310h+var_2D0]; struct APP_OBJECT *
0x180014960  mov     [rsp+310h+var_2E0], r15d; int
0x180014965  mov     [rsp+310h+var_2E8], rax; struct IXMLDOMDocument *
0x18001496a  mov     [rsp+310h+var_2F0], r12; struct ICommandObjectList *
0x18001496f  call    ?SetApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVAPP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z; APP_OBJECT_EXTENSION::SetApp(IExtensionContext *,APP_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)
0x180014974  jmp     loc_1800147EF
0x180014979  lea     rdx, aDelete_0; "DELETE"
0x180014980  mov     rcx, r14; String1
0x180014983  call    cs:__imp__wcsicmp
0x180014989  test    eax, eax
0x18001498b  jnz     short loc_1800149BF
0x18001498d  mov     r8, [rsp+310h+var_2C8]; struct ICommandParameterList *
0x180014992  mov     rdx, rdi; struct IExtensionContext *
0x180014995  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001499a  mov     ebx, eax
0x18001499c  test    eax, eax
0x18001499e  js      short loc_1800149CB
0x1800149a0  mov     rax, [rdi]
0x1800149a3  mov     r8, r12
0x1800149a6  mov     rdx, [rsp+310h+var_2D0]
0x1800149ab  mov     rcx, rdi
0x1800149ae  mov     rax, [rax+0B0h]
0x1800149b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ba  jmp     loc_1800147EF
0x1800149bf  mov     ebx, 80070032h
0x1800149c4  jmp     short loc_1800149CB
0x1800149c6  mov     ebx, 80070057h
0x1800149cb  mov     rcx, [rsp+310h+var_2D0]
0x1800149d0  test    rcx, rcx
0x1800149d3  jz      short loc_1800149EA
0x1800149d5  mov     rax, [rcx]
0x1800149d8  mov     rax, [rax+10h]
0x1800149dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e1  mov     [rsp+310h+var_2D0], 0
0x1800149ea  mov     rcx, [rsp+310h+var_2C8]
0x1800149ef  test    rcx, rcx
0x1800149f2  jz      short loc_180014A09
0x1800149f4  mov     rax, [rcx]
0x1800149f7  mov     rax, [rax+10h]
0x1800149fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a00  mov     [rsp+310h+var_2C8], 0
0x180014a09  lea     rcx, [rbp+210h+var_290]; this
0x180014a0d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180014a12  mov     eax, ebx
0x180014a14  mov     rcx, [rbp+210h+var_50]
0x180014a1b  xor     rcx, rsp; StackCookie
0x180014a1e  call    __security_check_cookie
0x180014a23  add     rsp, 2D8h
0x180014a2a  pop     r15
0x180014a2c  pop     r14
0x180014a2e  pop     r13
0x180014a30  pop     r12
0x180014a32  pop     rdi
0x180014a33  pop     rsi
0x180014a34  pop     rbx
0x180014a35  pop     rbp
0x180014a36  retn
```
