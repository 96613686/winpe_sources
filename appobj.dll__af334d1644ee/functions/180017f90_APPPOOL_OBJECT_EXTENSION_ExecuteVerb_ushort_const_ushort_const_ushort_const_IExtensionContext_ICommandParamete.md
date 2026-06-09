# APPPOOL_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180017f90`
- end: `0x180018336`
- name: `?ExecuteVerb@APPPOOL_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(APPPOOL_OBJECT_EXTENSION *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180016e74`
- `0x180017a24`
- `0x180017f90`
- `0x18002b564`
- `0x18002bcd4`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001806f`
- `msvcrt!_wcsicmp` at `0x1800180ad`
- `msvcrt!_wcsicmp` at `0x1800181e4`
- `msvcrt!_wcsicmp` at `0x18001821e`
- `msvcrt!_wcsicmp` at `0x180018268`
- `msvcrt!_wcsicmp` at `0x18001827c`
- `msvcrt!_wcsicmp` at `0x180018290`
- `msvcrt!_wcsicmp` at `0x18001806f`
- `msvcrt!_wcsicmp` at `0x1800180ad`
- `msvcrt!_wcsicmp` at `0x1800181e4`
- `msvcrt!_wcsicmp` at `0x18001821e`
- `msvcrt!_wcsicmp` at `0x180018268`
- `msvcrt!_wcsicmp` at `0x18001827c`
- `msvcrt!_wcsicmp` at `0x180018290`

## string_xrefs

- `0x180018214`: `DELETE`

## pseudocode

```c
__int64 __fastcall APPPOOL_OBJECT_EXTENSION::ExecuteVerb(
        APPPOOL_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  APP_OBJECT_UTILS *v11; // rcx
  APPPOOL_OBJECT_EXTENSION *v12; // rcx
  int v13; // ebx
  int v14; // eax
  APP_OBJECT_UTILS *v15; // rcx
  int v16; // eax
  APP_OBJECT_UTILS *v17; // rcx
  struct ICommandParameterList *v19; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandObject *v20; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-B0h]
  APPPOOL_OBJECT_EXTENSION *v22; // [rsp+58h] [rbp-A8h]
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v25; // [rsp+90h] [rbp-70h]
  int v26; // [rsp+98h] [rbp-68h]
  __int16 v27; // [rsp+9Ch] [rbp-64h]
  int v28; // [rsp+A0h] [rbp-60h]
  __int16 v29; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[510]; // [rsp+B2h] [rbp-4Eh] BYREF

  v21 = a2;
  v22 = this;
  v20 = 0;
  v19 = 0;
  v23 = 0;
  memset_0(v30, 0, sizeof(v30));
  v26 = 512;
  v27 = 256;
  v25 = (const unsigned __int16 *)&v29;
  v28 = 0;
  v29 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 || !a7 )
  {
    v13 = -2147024809;
    goto LABEL_31;
  }
  if ( !_wcsicmp(a3, L"ADD") )
  {
    v13 = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v11, a5, a4);
    if ( v13 < 0 )
      goto LABEL_31;
    v14 = APPPOOL_OBJECT_EXTENSION::AddAppPool(v12, a5, a6, a7, a8);
    goto LABEL_12;
  }
  if ( !_wcsicmp(a3, L"LIST") )
  {
    (*(void (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a5 + 32LL))(a5);
    (*(void (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a5 + 40LL))(a5);
    v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, _DWORD))(*(_QWORD *)a5 + 56LL))(
            a5,
            a2,
            a4,
            a6,
            a7,
            0);
LABEL_12:
    v13 = v14;
    goto LABEL_31;
  }
  v13 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
          a6,
          &v19);
  if ( v13 >= 0 )
  {
    if ( *a4 )
      goto LABEL_19;
    v16 = APP_OBJECT_UTILS::PopParameter(v15, a5, v19, L"APPPOOL.NAME", (struct STRU *)v24, 0, 1);
    v13 = v16;
    if ( v16 == -2147023483 )
    {
      *((_QWORD *)&v23 + 1) = L"APPPOOL.NAME";
      *(_QWORD *)&v23 = L"APPPOOL";
      v13 = -2147024809;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a5 + 144LL))(
        a5,
        2147942487LL,
        3221226474LL,
        &v23,
        0);
      goto LABEL_31;
    }
    if ( v16 >= 0 )
    {
      a4 = v25;
LABEL_19:
      v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandObject **, _DWORD))(*(_QWORD *)a5 + 64LL))(
              a5,
              v21,
              a4,
              &v20,
              0);
      if ( v13 >= 0 )
      {
        if ( !_wcsicmp(a3, L"SET") )
        {
          v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *, _DWORD))(*(_QWORD *)a5 + 168LL))(
                  a5,
                  v20,
                  v19,
                  a7,
                  a8,
                  0);
          goto LABEL_12;
        }
        if ( _wcsicmp(a3, L"DELETE") )
        {
          if ( !_wcsicmp(a3, L"RECYCLE") || !_wcsicmp(a3, L"STOP") || !_wcsicmp(a3, L"START") )
          {
            v14 = APPPOOL_OBJECT_EXTENSION::ExecuteRscaCommand(v22, a5, a3, v20, v19, a7);
            goto LABEL_12;
          }
          v13 = -2147024846;
        }
        else
        {
          v13 = APP_OBJECT_UTILS::ValidateEmptyParameters(v17, a5, v19);
          if ( v13 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandObject *, struct ICommandObjectList *))(*(_QWORD *)a5 + 176LL))(
                    a5,
                    v20,
                    a7);
            goto LABEL_12;
          }
        }
      }
    }
  }
LABEL_31:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct ICommandObject *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v24);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180017f90  push    rbp
0x180017f92  push    rbx
0x180017f93  push    rsi
0x180017f94  push    rdi
0x180017f95  push    r12
0x180017f97  push    r13
0x180017f99  push    r14
0x180017f9b  push    r15
0x180017f9d  lea     rbp, [rsp-1C8h]
0x180017fa5  sub     rsp, 2C8h
0x180017fac  mov     rax, cs:__security_cookie
0x180017fb3  xor     rax, rsp
0x180017fb6  mov     [rbp+200h+var_50], rax
0x180017fbd  mov     rdi, [rbp+200h+arg_20]
0x180017fc4  xor     eax, eax
0x180017fc6  mov     r12, [rbp+200h+arg_28]
0x180017fcd  mov     rsi, r8
0x180017fd0  mov     r15, [rbp+200h+arg_30]
0x180017fd7  mov     rbx, rdx
0x180017fda  mov     r13, [rbp+200h+arg_38]
0x180017fe1  xorps   xmm0, xmm0
0x180017fe4  mov     [rsp+300h+var_2B0], rdx
0x180017fe9  mov     r8d, 1FEh; Size
0x180017fef  mov     [rsp+300h+var_2A8], rcx
0x180017ff4  xor     edx, edx; Val
0x180017ff6  lea     rcx, [rbp+200h+var_24E]; void *
0x180017ffa  mov     [rsp+300h+var_2B8], rax
0x180017fff  mov     [rsp+300h+var_2C0], rax
0x180018004  mov     r14, r9
0x180018007  movups  [rsp+300h+var_2A0], xmm0
0x18001800c  call    memset_0
0x180018011  xor     ecx, ecx
0x180018013  mov     [rbp+200h+var_268], 200h
0x18001801a  mov     [rbp+200h+var_264], 100h
0x180018020  lea     rax, [rbp+200h+var_250]
0x180018024  mov     [rbp+200h+var_270], rax
0x180018028  mov     [rbp+200h+var_260], ecx
0x18001802b  mov     [rbp+200h+var_250], cx
0x18001802f  test    rbx, rbx
0x180018032  jz      loc_1800182CA
0x180018038  test    rsi, rsi
0x18001803b  jz      loc_1800182CA
0x180018041  test    r14, r14
0x180018044  jz      loc_1800182CA
0x18001804a  test    rdi, rdi
0x18001804d  jz      loc_1800182CA
0x180018053  test    r12, r12
0x180018056  jz      loc_1800182CA
0x18001805c  test    r15, r15
0x18001805f  jz      loc_1800182CA
0x180018065  lea     rdx, aAdd_0; "ADD"
0x18001806c  mov     rcx, rsi; String1
0x18001806f  call    cs:__imp__wcsicmp
0x180018075  test    eax, eax
0x180018077  jnz     short loc_1800180A3
0x180018079  mov     r8, r14; unsigned __int16 *
0x18001807c  mov     rdx, rdi; struct IExtensionContext *
0x18001807f  call    ?ValidateEmptyIdentifier@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBG@Z; APP_OBJECT_UTILS::ValidateEmptyIdentifier(IExtensionContext *,ushort const *)
0x180018084  mov     ebx, eax
0x180018086  test    eax, eax
0x180018088  js      loc_1800182CF
0x18001808e  mov     r9, r15; struct ICommandObjectList *
0x180018091  mov     [rsp+300h+var_2E0], r13; struct IXMLDOMDocument *
0x180018096  mov     r8, r12; struct ICommandParameterList *
0x180018099  mov     rdx, rdi; struct IExtensionContext *
0x18001809c  call    ?AddAppPool@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z; APPPOOL_OBJECT_EXTENSION::AddAppPool(IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)
0x1800180a1  jmp     short loc_1800180FA
0x1800180a3  lea     rdx, aList; "LIST"
0x1800180aa  mov     rcx, rsi; String1
0x1800180ad  call    cs:__imp__wcsicmp
0x1800180b3  test    eax, eax
0x1800180b5  jnz     short loc_180018101
0x1800180b7  mov     rax, [rdi]
0x1800180ba  mov     rcx, rdi
0x1800180bd  mov     rax, [rax+20h]
0x1800180c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180c6  mov     rax, [rdi]
0x1800180c9  mov     rcx, rdi
0x1800180cc  mov     rax, [rax+28h]
0x1800180d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180d5  mov     rax, [rdi]
0x1800180d8  mov     r9, r12
0x1800180db  mov     dword ptr [rsp+300h+var_2D8], 0
0x1800180e3  mov     r8, r14
0x1800180e6  mov     [rsp+300h+var_2E0], r15
0x1800180eb  mov     rdx, rbx
0x1800180ee  mov     rax, [rax+38h]
0x1800180f2  mov     rcx, rdi
0x1800180f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180fa  mov     ebx, eax
0x1800180fc  jmp     loc_1800182CF
0x180018101  mov     rax, [r12]
0x180018105  lea     rdx, [rsp+300h+var_2C0]
0x18001810a  mov     rcx, r12
0x18001810d  mov     rax, [rax+50h]
0x180018111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018116  xor     r12d, r12d
0x180018119  mov     ebx, eax
0x18001811b  test    eax, eax
0x18001811d  js      loc_1800182CF
0x180018123  cmp     [r14], r12w
0x180018127  jnz     loc_1800181AF
0x18001812d  mov     r8, [rsp+300h+var_2C0]; struct ICommandParameterList *
0x180018132  lea     rax, [rsp+300h+var_290]
0x180018137  mov     [rsp+300h+var_2D0], 1; int
0x18001813f  lea     r14, aApppoolName; "APPPOOL.NAME"
0x180018146  mov     r9, r14; unsigned __int16 *
0x180018149  mov     dword ptr [rsp+300h+var_2D8], r12d; int
0x18001814e  mov     rdx, rdi; struct IExtensionContext *
0x180018151  mov     [rsp+300h+var_2E0], rax; struct STRU *
0x180018156  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001815b  mov     ebx, eax
0x18001815d  cmp     eax, 80070585h
0x180018162  jnz     short loc_1800181A3
0x180018164  lea     rax, aApppool; "APPPOOL"
0x18001816b  mov     qword ptr [rsp+300h+var_2A0+8], r14
0x180018170  mov     qword ptr [rsp+300h+var_2A0], rax
0x180018175  lea     r9, [rsp+300h+var_2A0]
0x18001817a  mov     rax, [rdi]
0x18001817d  mov     ebx, 80070057h
0x180018182  mov     r8d, 0C00003EAh
0x180018188  mov     dword ptr [rsp+300h+var_2E0], r12d
0x18001818d  mov     edx, ebx
0x18001818f  mov     rcx, rdi
0x180018192  mov     rax, [rax+90h]
0x180018199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001819e  jmp     loc_1800182CF
0x1800181a3  test    eax, eax
0x1800181a5  js      loc_1800182CF
0x1800181ab  mov     r14, [rbp+200h+var_270]
0x1800181af  mov     rax, [rdi]
0x1800181b2  lea     r9, [rsp+300h+var_2B8]
0x1800181b7  mov     rdx, [rsp+300h+var_2B0]
0x1800181bc  mov     r8, r14
0x1800181bf  mov     rcx, rdi
0x1800181c2  mov     dword ptr [rsp+300h+var_2E0], r12d
0x1800181c7  mov     rax, [rax+40h]
0x1800181cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181d0  mov     ebx, eax
0x1800181d2  test    eax, eax
0x1800181d4  js      loc_1800182CF
0x1800181da  lea     rdx, aSet_0; "SET"
0x1800181e1  mov     rcx, rsi; String1
0x1800181e4  call    cs:__imp__wcsicmp
0x1800181ea  test    eax, eax
0x1800181ec  jnz     short loc_180018214
0x1800181ee  mov     rax, [rdi]
0x1800181f1  mov     r9, r15
0x1800181f4  mov     r8, [rsp+300h+var_2C0]
0x1800181f9  mov     rdx, [rsp+300h+var_2B8]
0x1800181fe  mov     dword ptr [rsp+300h+var_2D8], r12d
0x180018203  mov     rax, [rax+0A8h]
0x18001820a  mov     [rsp+300h+var_2E0], r13
0x18001820f  jmp     loc_1800180F2
0x180018214  lea     rdx, aDelete_0; "DELETE"
0x18001821b  mov     rcx, rsi; String1
0x18001821e  call    cs:__imp__wcsicmp
0x180018224  test    eax, eax
0x180018226  jnz     short loc_18001825E
0x180018228  mov     r8, [rsp+300h+var_2C0]; struct ICommandParameterList *
0x18001822d  mov     rdx, rdi; struct IExtensionContext *
0x180018230  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180018235  mov     ebx, eax
0x180018237  test    eax, eax
0x180018239  js      loc_1800182CF
0x18001823f  mov     rax, [rdi]
0x180018242  mov     r8, r15
0x180018245  mov     rdx, [rsp+300h+var_2B8]
0x18001824a  mov     rcx, rdi
0x18001824d  mov     rax, [rax+0B0h]
0x180018254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018259  jmp     loc_1800180FA
0x18001825e  lea     rdx, aRecycle; "RECYCLE"
0x180018265  mov     rcx, rsi; String1
0x180018268  call    cs:__imp__wcsicmp
0x18001826e  test    eax, eax
0x180018270  jz      short loc_1800182A1
0x180018272  lea     rdx, aStop_0; "STOP"
0x180018279  mov     rcx, rsi; String1
0x18001827c  call    cs:__imp__wcsicmp
0x180018282  test    eax, eax
0x180018284  jz      short loc_1800182A1
0x180018286  lea     rdx, aStart; "START"
0x18001828d  mov     rcx, rsi; String1
0x180018290  call    cs:__imp__wcsicmp
0x180018296  test    eax, eax
0x180018298  jz      short loc_1800182A1
0x18001829a  mov     ebx, 80070032h
0x18001829f  jmp     short loc_1800182CF
0x1800182a1  mov     rax, [rsp+300h+var_2C0]
0x1800182a6  mov     r8, rsi; unsigned __int16 *
0x1800182a9  mov     r9, [rsp+300h+var_2B8]; struct ICommandObject *
0x1800182ae  mov     rdx, rdi; struct IExtensionContext *
0x1800182b1  mov     rcx, [rsp+300h+var_2A8]; this
0x1800182b6  mov     [rsp+300h+var_2D8], r15; struct ICommandObjectList *
0x1800182bb  mov     [rsp+300h+var_2E0], rax; struct ICommandParameterList *
0x1800182c0  call    ?ExecuteRscaCommand@APPPOOL_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandObject@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; APPPOOL_OBJECT_EXTENSION::ExecuteRscaCommand(IExtensionContext *,ushort const *,ICommandObject *,ICommandParameterList *,ICommandObjectList *)
0x1800182c5  jmp     loc_1800180FA
0x1800182ca  mov     ebx, 80070057h
0x1800182cf  mov     rcx, [rsp+300h+var_2B8]
0x1800182d4  xor     edi, edi
0x1800182d6  test    rcx, rcx
0x1800182d9  jz      short loc_1800182EC
0x1800182db  mov     rax, [rcx]
0x1800182de  mov     rax, [rax+10h]
0x1800182e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e7  mov     [rsp+300h+var_2B8], rdi
0x1800182ec  mov     rcx, [rsp+300h+var_2C0]
0x1800182f1  test    rcx, rcx
0x1800182f4  jz      short loc_180018307
0x1800182f6  mov     rax, [rcx]
0x1800182f9  mov     rax, [rax+10h]
0x1800182fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018302  mov     [rsp+300h+var_2C0], rdi
0x180018307  lea     rcx, [rsp+300h+var_290]; this
0x18001830c  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180018311  mov     eax, ebx
0x180018313  mov     rcx, [rbp+200h+var_50]
0x18001831a  xor     rcx, rsp; StackCookie
0x18001831d  call    __security_check_cookie
0x180018322  add     rsp, 2C8h
0x180018329  pop     r15
0x18001832b  pop     r14
0x18001832d  pop     r13
0x18001832f  pop     r12
0x180018331  pop     rdi
0x180018332  pop     rsi
0x180018333  pop     rbx
0x180018334  pop     rbp
0x180018335  retn
```
