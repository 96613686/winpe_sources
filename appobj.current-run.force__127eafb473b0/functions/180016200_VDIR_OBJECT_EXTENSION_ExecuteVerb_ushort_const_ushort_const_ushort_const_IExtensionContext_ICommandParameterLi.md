# VDIR_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180016200`
- end: `0x1800165d1`
- name: `?ExecuteVerb@VDIR_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `977`
- prototype: `int(VDIR_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180015138`
- `0x180015398`
- `0x180016200`
- `0x18002b564`
- `0x18002bb20`
- `0x18002bcd4`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800162ea`
- `msvcrt!_wcsicmp` at `0x180016332`
- `msvcrt!_wcsicmp` at `0x1800164ae`
- `msvcrt!_wcsicmp` at `0x1800164d7`
- `msvcrt!_wcsicmp` at `0x180016516`
- `msvcrt!_wcsicmp` at `0x1800162ea`
- `msvcrt!_wcsicmp` at `0x180016332`
- `msvcrt!_wcsicmp` at `0x1800164ae`
- `msvcrt!_wcsicmp` at `0x1800164d7`
- `msvcrt!_wcsicmp` at `0x180016516`

## string_xrefs

- `0x18001650c`: `DELETE`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT_EXTENSION::ExecuteVerb(
        VDIR_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  APP_OBJECT_UTILS *v11; // rcx
  VDIR_OBJECT_EXTENSION *v12; // rcx
  int v13; // ebx
  int v14; // eax
  APP_OBJECT_UTILS *v15; // rcx
  int v16; // eax
  __int64 v17; // r8
  APP_OBJECT_UTILS *v18; // rcx
  APP_OBJECT_UTILS *v19; // rcx
  APP_OBJECT_EXTENSION *v20; // rcx
  APP_OBJECT_UTILS *v21; // rcx
  struct APP_OBJECT *v23; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandParameterList *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String2; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-90h] BYREF
  struct IXMLDOMDocument *v29; // [rsp+78h] [rbp-88h]
  _BYTE v30[32]; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v31; // [rsp+A0h] [rbp-60h]
  int v32; // [rsp+A8h] [rbp-58h]
  __int16 v33; // [rsp+ACh] [rbp-54h]
  int v34; // [rsp+B0h] [rbp-50h]
  __int16 v35; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[510]; // [rsp+C2h] [rbp-3Eh] BYREF

  v29 = a8;
  v23 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  memset_0(v36, 0, sizeof(v36));
  v32 = 512;
  v31 = (const unsigned __int16 *)&v35;
  v33 = 256;
  v34 = 0;
  v35 = 0;
  String1 = 0;
  String2 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
  {
    v13 = -2147024809;
    goto LABEL_33;
  }
  if ( !_wcsicmp(a3, L"ADD") )
  {
    v13 = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v11, a5, a4);
    if ( v13 < 0 )
      goto LABEL_33;
    v14 = VDIR_OBJECT_EXTENSION::AddDir(v12, a5, a4, a6, a7, v29);
    goto LABEL_12;
  }
  if ( !_wcsicmp(a3, L"LIST") )
  {
    v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)a5 + 56LL))(
            a5,
            a2,
            a4,
            a6,
            a7,
            0);
LABEL_12:
    v13 = v14;
    goto LABEL_33;
  }
  v13 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
          a6,
          &v24);
  if ( v13 >= 0 )
  {
    if ( *a4 )
    {
LABEL_20:
      v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct APP_OBJECT **, _DWORD))(*(_QWORD *)a5 + 64LL))(
              a5,
              a2,
              a4,
              &v23,
              0);
      if ( v13 >= 0 )
      {
        v13 = APP_OBJECT_UTILS::ResolveUrl(v18, a4, 0, (const unsigned __int16 **)&String1, 0);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(struct APP_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v23 + 80LL))(
                  v23,
                  L"VDIR.NAME",
                  &v26);
          if ( v13 >= 0 )
          {
            v13 = APP_OBJECT_UTILS::ResolveUrl(v19, v26, 0, (const unsigned __int16 **)&String2, 0);
            if ( v13 >= 0 )
            {
              if ( _wcsicmp(String1, String2) )
              {
                *(_QWORD *)&v25 = a2;
                v17 = 3221226508LL;
                *((_QWORD *)&v25 + 1) = a3;
                goto LABEL_17;
              }
              if ( !_wcsicmp(a3, L"SET") )
              {
                v14 = APP_OBJECT_EXTENSION::SetApp(v20, a5, v23, v24, a7, v29, 0);
                goto LABEL_12;
              }
              if ( _wcsicmp(a3, L"DELETE") )
              {
                v13 = -2147024846;
              }
              else
              {
                v13 = APP_OBJECT_UTILS::ValidateEmptyParameters(v21, a5, v24);
                if ( v13 >= 0 )
                {
                  v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct APP_OBJECT *, struct ICommandObjectList *))(*(_QWORD *)a5 + 176LL))(
                          a5,
                          v23,
                          a7);
                  goto LABEL_12;
                }
              }
            }
          }
        }
      }
      goto LABEL_33;
    }
    v16 = APP_OBJECT_UTILS::PopParameter(v15, a5, v24, L"VDIR.NAME", (struct STRU *)v30, 0, 1);
    v13 = v16;
    if ( v16 == -2147023483 )
    {
      v17 = 3221226474LL;
      *(_QWORD *)&v25 = L"VDIR";
      *((_QWORD *)&v25 + 1) = L"VDIR.NAME";
LABEL_17:
      v13 = -2147024846;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a5 + 144LL))(
        a5,
        2147942450LL,
        v17,
        &v25,
        0);
      goto LABEL_33;
    }
    if ( v16 >= 0 )
    {
      a4 = v31;
      goto LABEL_20;
    }
  }
LABEL_33:
  if ( v23 )
  {
    (*(void (__fastcall **)(struct APP_OBJECT *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v30);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016200  mov     [rsp-8+arg_0], rbx
0x180016205  push    rbp
0x180016206  push    rsi
0x180016207  push    rdi
0x180016208  push    r12
0x18001620a  push    r13
0x18001620c  push    r14
0x18001620e  push    r15
0x180016210  lea     rbp, [rsp-1D0h]
0x180016218  sub     rsp, 2D0h
0x18001621f  mov     rax, cs:__security_cookie
0x180016226  xor     rax, rsp
0x180016229  mov     [rbp+200h+var_40], rax
0x180016230  mov     rax, [rbp+200h+arg_38]
0x180016237  lea     rcx, [rbp+200h+var_23E]; void *
0x18001623b  mov     rdi, [rbp+200h+arg_20]
0x180016242  xor     ebx, ebx
0x180016244  mov     r15, [rbp+200h+arg_28]
0x18001624b  mov     r14, r8
0x18001624e  mov     r12, [rbp+200h+arg_30]
0x180016255  mov     r13, rdx
0x180016258  xorps   xmm0, xmm0
0x18001625b  mov     [rsp+300h+var_288], rax
0x180016260  xor     edx, edx; Val
0x180016262  mov     [rsp+300h+var_2C0], rbx
0x180016267  mov     r8d, 1FEh; Size
0x18001626d  mov     [rsp+300h+var_2A0], rbx
0x180016272  movups  [rsp+300h+var_2B0], xmm0
0x180016277  mov     [rsp+300h+var_2B8], rbx
0x18001627c  mov     rsi, r9
0x18001627f  call    memset_0
0x180016284  mov     [rbp+200h+var_258], 200h
0x18001628b  lea     rax, [rbp+200h+var_240]
0x18001628f  mov     [rbp+200h+var_260], rax
0x180016293  mov     [rbp+200h+var_254], 100h
0x180016299  mov     [rbp+200h+var_250], ebx
0x18001629c  mov     [rbp+200h+var_240], bx
0x1800162a0  mov     [rsp+300h+String1], rbx
0x1800162a5  mov     [rsp+300h+String2], rbx
0x1800162aa  test    r13, r13
0x1800162ad  jz      loc_180016559
0x1800162b3  test    r14, r14
0x1800162b6  jz      loc_180016559
0x1800162bc  test    rsi, rsi
0x1800162bf  jz      loc_180016559
0x1800162c5  test    rdi, rdi
0x1800162c8  jz      loc_180016559
0x1800162ce  test    r15, r15
0x1800162d1  jz      loc_180016559
0x1800162d7  test    r12, r12
0x1800162da  jz      loc_180016559
0x1800162e0  lea     rdx, aAdd_0; "ADD"
0x1800162e7  mov     rcx, r14; String1
0x1800162ea  call    cs:__imp__wcsicmp
0x1800162f0  test    eax, eax
0x1800162f2  jnz     short loc_180016328
0x1800162f4  mov     r8, rsi; unsigned __int16 *
0x1800162f7  mov     rdx, rdi; struct IExtensionContext *
0x1800162fa  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x1800162ff  mov     ebx, eax
0x180016301  test    eax, eax
0x180016303  js      loc_18001655E
0x180016309  mov     rax, [rsp+300h+var_288]
0x18001630e  mov     r9, r15; struct ICommandParameterList *
0x180016311  mov     [rsp+300h+var_2D8], rax; struct IXMLDOMDocument *
0x180016316  mov     r8, rsi; unsigned __int16 *
0x180016319  mov     rdx, rdi; struct IExtensionContext *
0x18001631c  mov     [rsp+300h+var_2E0], r12; struct ICommandObjectList *
0x180016321  call    ?AddDir@VDIR_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; VDIR_OBJECT_EXTENSION::AddDir(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x180016326  jmp     short loc_18001635D
0x180016328  lea     rdx, aList; "LIST"
0x18001632f  mov     rcx, r14; String1
0x180016332  call    cs:__imp__wcsicmp
0x180016338  test    eax, eax
0x18001633a  jnz     short loc_180016364
0x18001633c  mov     rax, [rdi]
0x18001633f  mov     r9, r15
0x180016342  mov     dword ptr [rsp+300h+var_2D8], ebx
0x180016346  mov     r8, rsi
0x180016349  mov     rdx, r13
0x18001634c  mov     [rsp+300h+var_2E0], r12
0x180016351  mov     rcx, rdi
0x180016354  mov     rax, [rax+38h]
0x180016358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001635d  mov     ebx, eax
0x18001635f  jmp     loc_18001655E
0x180016364  mov     rax, [r15]
0x180016367  lea     rdx, [rsp+300h+var_2B8]
0x18001636c  mov     rcx, r15
0x18001636f  mov     rax, [rax+50h]
0x180016373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016378  xor     r15d, r15d
0x18001637b  mov     ebx, eax
0x18001637d  test    eax, eax
0x18001637f  js      loc_18001655E
0x180016385  cmp     [rsi], r15w
0x180016389  jnz     loc_180016414
0x18001638f  mov     r8, [rsp+300h+var_2B8]; struct ICommandParameterList *
0x180016394  lea     rax, [rbp+200h+var_280]
0x180016398  mov     [rsp+300h+var_2D0], 1; int
0x1800163a0  lea     r9, aVdirName; "VDIR.NAME"
0x1800163a7  mov     dword ptr [rsp+300h+var_2D8], r15d; int
0x1800163ac  mov     rdx, rdi; struct IExtensionContext *
0x1800163af  mov     [rsp+300h+var_2E0], rax; struct STRU *
0x1800163b4  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800163b9  mov     ebx, eax
0x1800163bb  cmp     eax, 80070585h
0x1800163c0  jnz     short loc_180016408
0x1800163c2  lea     rax, aVdir; "VDIR"
0x1800163c9  mov     r8d, 0C00003EAh
0x1800163cf  lea     rdx, aVdirName; "VDIR.NAME"
0x1800163d6  mov     qword ptr [rsp+300h+var_2B0], rax
0x1800163db  mov     qword ptr [rsp+300h+var_2B0+8], rdx
0x1800163e0  mov     rax, [rdi]
0x1800163e3  lea     r9, [rsp+300h+var_2B0]
0x1800163e8  mov     ebx, 80070032h
0x1800163ed  mov     dword ptr [rsp+300h+var_2E0], r15d
0x1800163f2  mov     edx, ebx
0x1800163f4  mov     rcx, rdi
0x1800163f7  mov     rax, [rax+90h]
0x1800163fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016403  jmp     loc_18001655E
0x180016408  test    eax, eax
0x18001640a  js      loc_18001655E
0x180016410  mov     rsi, [rbp+200h+var_260]
0x180016414  mov     rax, [rdi]
0x180016417  lea     r9, [rsp+300h+var_2C0]
0x18001641c  mov     r8, rsi
0x18001641f  mov     dword ptr [rsp+300h+var_2E0], r15d
0x180016424  mov     rdx, r13
0x180016427  mov     rcx, rdi
0x18001642a  mov     rax, [rax+40h]
0x18001642e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016433  mov     ebx, eax
0x180016435  test    eax, eax
0x180016437  js      loc_18001655E
0x18001643d  lea     r9, [rsp+300h+String1]; unsigned __int16 **
0x180016442  mov     [rsp+300h+var_2E0], r15; int *
0x180016447  xor     r8d, r8d; struct STRU *
0x18001644a  mov     rdx, rsi; unsigned __int16 *
0x18001644d  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x180016452  mov     ebx, eax
0x180016454  test    eax, eax
0x180016456  js      loc_18001655E
0x18001645c  mov     rcx, [rsp+300h+var_2C0]
0x180016461  lea     r8, [rsp+300h+var_2A0]
0x180016466  lea     rdx, aVdirName; "VDIR.NAME"
0x18001646d  mov     rax, [rcx]
0x180016470  mov     rax, [rax+50h]
0x180016474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016479  mov     ebx, eax
0x18001647b  test    eax, eax
0x18001647d  js      loc_18001655E
0x180016483  mov     rdx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180016488  lea     r9, [rsp+300h+String2]; unsigned __int16 **
0x18001648d  xor     r8d, r8d; struct STRU *
0x180016490  mov     [rsp+300h+var_2E0], r15; int *
0x180016495  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x18001649a  mov     ebx, eax
0x18001649c  test    eax, eax
0x18001649e  js      loc_18001655E
0x1800164a4  mov     rdx, [rsp+300h+String2]; String2
0x1800164a9  mov     rcx, [rsp+300h+String1]; String1
0x1800164ae  call    cs:__imp__wcsicmp
0x1800164b4  test    eax, eax
0x1800164b6  jz      short loc_1800164CD
0x1800164b8  mov     qword ptr [rsp+300h+var_2B0], r13
0x1800164bd  mov     r8d, 0C000040Ch
0x1800164c3  mov     qword ptr [rsp+300h+var_2B0+8], r14
0x1800164c8  jmp     loc_1800163E0
0x1800164cd  lea     rdx, aSet_0; "SET"
0x1800164d4  mov     rcx, r14; String1
0x1800164d7  call    cs:__imp__wcsicmp
0x1800164dd  test    eax, eax
0x1800164df  jnz     short loc_18001650C
0x1800164e1  mov     rax, [rsp+300h+var_288]
0x1800164e6  mov     rdx, rdi; struct IExtensionContext *
0x1800164e9  mov     r9, [rsp+300h+var_2B8]; struct ICommandParameterList *
0x1800164ee  mov     r8, [rsp+300h+var_2C0]; struct APP_OBJECT *
0x1800164f3  mov     [rsp+300h+var_2D0], r15d; int
0x1800164f8  mov     [rsp+300h+var_2D8], rax; struct IXMLDOMDocument *
0x1800164fd  mov     [rsp+300h+var_2E0], r12; struct ICommandObjectList *
0x180016502  call    ?SetApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVAPP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z; APP_OBJECT_EXTENSION::SetApp(IExtensionContext *,APP_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)
0x180016507  jmp     loc_18001635D
0x18001650c  lea     rdx, aDelete_0; "DELETE"
0x180016513  mov     rcx, r14; String1
0x180016516  call    cs:__imp__wcsicmp
0x18001651c  test    eax, eax
0x18001651e  jnz     short loc_180016552
0x180016520  mov     r8, [rsp+300h+var_2B8]; struct ICommandParameterList *
0x180016525  mov     rdx, rdi; struct IExtensionContext *
0x180016528  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001652d  mov     ebx, eax
0x18001652f  test    eax, eax
0x180016531  js      short loc_18001655E
0x180016533  mov     rax, [rdi]
0x180016536  mov     r8, r12
0x180016539  mov     rdx, [rsp+300h+var_2C0]
0x18001653e  mov     rcx, rdi
0x180016541  mov     rax, [rax+0B0h]
0x180016548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654d  jmp     loc_18001635D
0x180016552  mov     ebx, 80070032h
0x180016557  jmp     short loc_18001655E
0x180016559  mov     ebx, 80070057h
0x18001655e  mov     rcx, [rsp+300h+var_2C0]
0x180016563  test    rcx, rcx
0x180016566  jz      short loc_18001657D
0x180016568  mov     rax, [rcx]
0x18001656b  mov     rax, [rax+10h]
0x18001656f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016574  mov     [rsp+300h+var_2C0], 0
0x18001657d  mov     rcx, [rsp+300h+var_2B8]
0x180016582  test    rcx, rcx
0x180016585  jz      short loc_18001659C
0x180016587  mov     rax, [rcx]
0x18001658a  mov     rax, [rax+10h]
0x18001658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016593  mov     [rsp+300h+var_2B8], 0
0x18001659c  lea     rcx, [rbp+200h+var_280]; this
0x1800165a0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800165a5  mov     eax, ebx
0x1800165a7  mov     rcx, [rbp+200h+var_40]
0x1800165ae  xor     rcx, rsp; StackCookie
0x1800165b1  call    __security_check_cookie
0x1800165b6  mov     rbx, [rsp+300h+arg_0]
0x1800165be  add     rsp, 2D0h
0x1800165c5  pop     r15
0x1800165c7  pop     r14
0x1800165c9  pop     r13
0x1800165cb  pop     r12
0x1800165cd  pop     rdi
0x1800165ce  pop     rsi
0x1800165cf  pop     rbp
0x1800165d0  retn
```
