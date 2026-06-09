# TRACE_OBJECT_EXTENSION::RemoveTraceRule(IExtensionContext *,ICommandObject *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180028f50`
- end: `0x1800293f8`
- name: `?RemoveTraceRule@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandObject@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1192`
- prototype: `int(TRACE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025fe4`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000557c`
- `0x180006b6c`
- `0x180028f50`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180029182`
- `msvcrt!_wcsicmp` at `0x180029182`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::RemoveTraceRule(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandObject *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  const unsigned __int16 **v8; // rdi
  int v9; // ebx
  APP_OBJECT_UTILS *v10; // rcx
  unsigned int v11; // esi
  APP_OBJECT_UTILS *v12; // rcx
  unsigned int v13; // esi
  unsigned int i; // r12d
  __int64 v15; // rax
  STATUS_OBJECT *v16; // rax
  __int64 *v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  va_list v26; // [rsp+80h] [rbp-80h] BYREF
  va_list v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  va_list Arguments[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v30[32]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *String2; // [rsp+C8h] [rbp-38h]
  int v32; // [rsp+D0h] [rbp-30h]
  __int16 v33; // [rsp+D4h] [rbp-2Ch]
  int v34; // [rsp+D8h] [rbp-28h]
  __int16 v35; // [rsp+E0h] [rbp-20h] BYREF
  char v36[510]; // [rsp+E2h] [rbp-1Eh] BYREF

  v23 = 0;
  v25 = 0;
  v18 = 0;
  v19 = 0;
  *(_OWORD *)Arguments = 0;
  v22 = 0;
  v21 = 0;
  v28 = 0;
  String1 = 0;
  memset_0(v36, 0, sizeof(v36));
  v32 = 512;
  String2 = (wchar_t *)&v35;
  v8 = 0;
  v33 = 256;
  v34 = 0;
  v35 = 0;
  v20 = 0;
  v26 = 0;
  v27 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v9 = -2147024809;
    goto LABEL_38;
  }
  v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v23);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v25);
    if ( v9 >= 0 )
    {
      v11 = APP_OBJECT_UTILS::PopParameter(v10, a2, a4, L"path", (struct STRU *)v30, 0, 1);
      v12 = (APP_OBJECT_UTILS *)(v11 + 0x80000000);
      if ( (int)v12 >= 0 && v11 != -2147023483 )
      {
        v9 = v11;
        goto LABEL_38;
      }
      v9 = APP_OBJECT_UTILS::ValidateEmptyParameters(v12, a2, a4);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v23 + 40LL))(v23, &v18);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v18 + 24))(v18, &v20);
          if ( v9 >= 0 )
          {
            v13 = v11 >> 31;
            for ( i = 0; i < v20; ++i )
            {
              v15 = *v18;
              if ( v13 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 64))(v18, 0, &v21);
                if ( v9 < 0 )
                  goto LABEL_38;
              }
              else
              {
                v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v18, i, &v19);
                if ( v9 < 0 )
                  goto LABEL_38;
                v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **, __int64 *, _QWORD))(*(_QWORD *)v19 + 64LL))(
                       v19,
                       L"path",
                       &String1,
                       &v22,
                       0);
                if ( v9 < 0 )
                  goto LABEL_38;
                if ( !_wcsicmp(String1, String2) )
                  break;
                String1 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                v19 = 0;
              }
            }
            if ( v19 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v18 + 64))(v18, i, &v21);
              if ( v9 < 0 )
                goto LABEL_38;
            }
            else if ( !v13 )
            {
              v9 = -2147023483;
              (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
                a2,
                2147943813LL,
                3221226507LL,
                Arguments,
                0);
              goto LABEL_38;
            }
            v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, _QWORD))(*(_QWORD *)a2 + 208LL))(
                   a2,
                   v25,
                   0);
            if ( v9 >= 0 )
            {
              v16 = (STATUS_OBJECT *)operator new(0x110u);
              if ( v16 )
              {
                v8 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v16);
                if ( v8 )
                {
                  v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a3 + 24LL))(a3, &v26);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a3 + 32LL))(
                           a3,
                           &v27);
                    if ( v9 >= 0 )
                    {
                      Arguments[0] = v26;
                      Arguments[1] = v27;
                      v9 = STATUS_OBJECT::Create(v8, 0x3EEu, Arguments);
                      if ( v9 >= 0 )
                        v9 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a5 + 24LL))(
                               a5,
                               v8);
                    }
                  }
                  goto LABEL_38;
                }
              }
              else
              {
                v8 = 0;
              }
              v9 = -2147024888;
            }
          }
        }
      }
    }
  }
LABEL_38:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *))(*(_QWORD *)a2 + 120LL))(
      a2,
      (unsigned int)v9,
      &Str);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL))(v21, &v28);
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 128LL))(
      a2,
      (unsigned int)v9,
      v28,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    v18 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v8 )
    (*((void (__fastcall **)(const unsigned __int16 **))*v8 + 2))(v8);
  BUFFER::~BUFFER((BUFFER *)v30);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180028f50  mov     [rsp-8+arg_0], rbx
0x180028f55  push    rbp
0x180028f56  push    rsi
0x180028f57  push    rdi
0x180028f58  push    r12
0x180028f5a  push    r13
0x180028f5c  push    r14
0x180028f5e  push    r15
0x180028f60  lea     rbp, [rsp-1F0h]
0x180028f68  sub     rsp, 2F0h
0x180028f6f  mov     rax, cs:__security_cookie
0x180028f76  xor     rax, rsp
0x180028f79  mov     [rbp+220h+var_40], rax
0x180028f80  mov     r13, [rbp+220h+arg_20]
0x180028f87  lea     rcx, [rbp+220h+var_23E]; void *
0x180028f8b  xor     esi, esi
0x180028f8d  mov     r14, r8
0x180028f90  mov     r15, rdx
0x180028f93  mov     [rsp+320h+var_2B8], rsi
0x180028f98  xorps   xmm0, xmm0
0x180028f9b  mov     [rsp+320h+var_2A8], rsi
0x180028fa0  xor     edx, edx; Val
0x180028fa2  mov     [rsp+320h+var_2E0], rsi
0x180028fa7  mov     r8d, 1FEh; Size
0x180028fad  mov     [rsp+320h+var_2D8], rsi
0x180028fb2  movups  xmmword ptr [rbp+220h+Arguments], xmm0
0x180028fb6  mov     [rsp+320h+var_2C0], rsi
0x180028fbb  mov     r12, r9
0x180028fbe  mov     [rsp+320h+var_2C8], rsi
0x180028fc3  mov     [rbp+220h+var_290], rsi
0x180028fc7  mov     [rsp+320h+String1], rsi
0x180028fcc  call    memset_0
0x180028fd1  mov     [rbp+220h+var_250], 200h
0x180028fd8  lea     rax, [rbp+220h+var_240]
0x180028fdc  mov     [rbp+220h+String2], rax
0x180028fe0  mov     edi, esi
0x180028fe2  mov     [rbp+220h+var_24C], 100h
0x180028fe8  mov     [rbp+220h+var_248], esi
0x180028feb  mov     [rbp+220h+var_240], si
0x180028fef  mov     [rsp+320h+var_2D0], esi
0x180028ff3  mov     [rbp+220h+var_2A0], rsi
0x180028ff7  mov     [rbp+220h+var_298], rsi
0x180028ffb  test    r15, r15
0x180028ffe  jz      loc_1800292D0
0x180029004  test    r14, r14
0x180029007  jz      loc_1800292D0
0x18002900d  test    r12, r12
0x180029010  jz      loc_1800292D0
0x180029016  test    r13, r13
0x180029019  jz      loc_1800292D0
0x18002901f  mov     rax, [r14]
0x180029022  lea     rdx, [rsp+320h+var_2B8]
0x180029027  mov     rcx, r14
0x18002902a  mov     rax, [rax+30h]
0x18002902e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029033  mov     ebx, eax
0x180029035  test    eax, eax
0x180029037  js      loc_1800292D5
0x18002903d  mov     rax, [r14]
0x180029040  lea     rdx, [rsp+320h+var_2A8]
0x180029045  mov     rcx, r14
0x180029048  mov     rax, [rax+28h]
0x18002904c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029051  mov     ebx, eax
0x180029053  test    eax, eax
0x180029055  js      loc_1800292D5
0x18002905b  mov     [rsp+320h+var_2F0], 1; int
0x180029063  lea     rax, [rbp+220h+var_278]
0x180029067  mov     [rsp+320h+var_2F8], esi; int
0x18002906b  lea     r9, aPath_1; "path"
0x180029072  mov     r8, r12; struct ICommandParameterList *
0x180029075  mov     [rsp+320h+var_300], rax; struct STRU *
0x18002907a  mov     rdx, r15; struct IExtensionContext *
0x18002907d  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180029082  mov     esi, eax
0x180029084  mov     eax, 80000000h
0x180029089  lea     ecx, [rsi+rax]; this
0x18002908c  test    eax, ecx
0x18002908e  jnz     short loc_18002909F
0x180029090  cmp     esi, 80070585h
0x180029096  jz      short loc_18002909F
0x180029098  mov     ebx, esi
0x18002909a  jmp     loc_1800292D5
0x18002909f  mov     r8, r12; struct ICommandParameterList *
0x1800290a2  mov     rdx, r15; struct IExtensionContext *
0x1800290a5  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x1800290aa  mov     ebx, eax
0x1800290ac  test    eax, eax
0x1800290ae  js      loc_1800292D5
0x1800290b4  mov     rcx, [rsp+320h+var_2B8]
0x1800290b9  lea     rdx, [rsp+320h+var_2E0]
0x1800290be  mov     rax, [rcx]
0x1800290c1  mov     rax, [rax+28h]
0x1800290c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ca  mov     ebx, eax
0x1800290cc  test    eax, eax
0x1800290ce  js      loc_1800292D5
0x1800290d4  mov     rcx, [rsp+320h+var_2E0]
0x1800290d9  lea     rdx, [rsp+320h+var_2D0]
0x1800290de  mov     rax, [rcx]
0x1800290e1  mov     rax, [rax+18h]
0x1800290e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290ea  mov     ebx, eax
0x1800290ec  test    eax, eax
0x1800290ee  js      loc_1800292D5
0x1800290f4  shr     esi, 1Fh
0x1800290f7  xor     r12d, r12d
0x1800290fa  cmp     r12d, [rsp+320h+var_2D0]
0x1800290ff  jnb     loc_1800291AF
0x180029105  mov     rcx, [rsp+320h+var_2E0]
0x18002910a  mov     rax, [rcx]
0x18002910d  test    esi, esi
0x18002910f  jz      short loc_18002912D
0x180029111  mov     rax, [rax+40h]
0x180029115  lea     r8, [rsp+320h+var_2C8]
0x18002911a  xor     edx, edx
0x18002911c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029121  mov     ebx, eax
0x180029123  test    eax, eax
0x180029125  js      loc_1800292D5
0x18002912b  jmp     short loc_1800291A7
0x18002912d  mov     rax, [rax+20h]
0x180029131  lea     r8, [rsp+320h+var_2D8]
0x180029136  mov     edx, r12d
0x180029139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002913e  mov     ebx, eax
0x180029140  test    eax, eax
0x180029142  js      loc_1800292D5
0x180029148  mov     rcx, [rsp+320h+var_2D8]
0x18002914d  lea     r9, [rsp+320h+var_2C0]
0x180029152  lea     r8, [rsp+320h+String1]
0x180029157  mov     [rsp+320h+var_300], rdi
0x18002915c  lea     rdx, aPath_1; "path"
0x180029163  mov     rax, [rcx]
0x180029166  mov     rax, [rax+40h]
0x18002916a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002916f  mov     ebx, eax
0x180029171  test    eax, eax
0x180029173  js      loc_1800292D5
0x180029179  mov     rdx, [rbp+220h+String2]; String2
0x18002917d  mov     rcx, [rsp+320h+String1]; String1
0x180029182  call    cs:__imp__wcsicmp
0x180029188  test    eax, eax
0x18002918a  jz      short loc_1800291AF
0x18002918c  mov     rcx, [rsp+320h+var_2D8]
0x180029191  mov     [rsp+320h+String1], rdi
0x180029196  mov     rax, [rcx]
0x180029199  mov     rax, [rax+10h]
0x18002919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291a2  mov     [rsp+320h+var_2D8], rdi
0x1800291a7  inc     r12d
0x1800291aa  jmp     loc_1800290FA
0x1800291af  cmp     [rsp+320h+var_2D8], rdi
0x1800291b4  jz      short loc_1800291DD
0x1800291b6  mov     rcx, [rsp+320h+var_2E0]
0x1800291bb  lea     r8, [rsp+320h+var_2C8]
0x1800291c0  mov     edx, r12d
0x1800291c3  mov     rax, [rcx]
0x1800291c6  mov     rax, [rax+40h]
0x1800291ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291cf  xor     esi, esi
0x1800291d1  mov     ebx, eax
0x1800291d3  test    eax, eax
0x1800291d5  js      loc_1800292D5
0x1800291db  jmp     short loc_18002920F
0x1800291dd  test    esi, esi
0x1800291df  jnz     short loc_18002920D
0x1800291e1  mov     rax, [r15]
0x1800291e4  lea     r9, [rbp+220h+Arguments]
0x1800291e8  mov     edx, 80070585h
0x1800291ed  mov     dword ptr [rsp+320h+var_300], edi
0x1800291f1  mov     r8d, 0C000040Bh
0x1800291f7  mov     rcx, r15
0x1800291fa  mov     ebx, edx
0x1800291fc  mov     rax, [rax+90h]
0x180029203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029208  jmp     loc_1800292D5
0x18002920d  xor     esi, esi
0x18002920f  mov     rax, [r15]
0x180029212  xor     r8d, r8d
0x180029215  mov     rdx, [rsp+320h+var_2A8]
0x18002921a  mov     rcx, r15
0x18002921d  mov     rax, [rax+0D0h]
0x180029224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029229  mov     ebx, eax
0x18002922b  test    eax, eax
0x18002922d  js      loc_1800292D5
0x180029233  mov     ecx, 110h; Size
0x180029238  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002923d  test    rax, rax
0x180029240  jz      loc_1800292C6
0x180029246  mov     rcx, rax; this
0x180029249  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x18002924e  mov     rdi, rax
0x180029251  test    rax, rax
0x180029254  jz      short loc_1800292C9
0x180029256  mov     rax, [r14]
0x180029259  lea     rdx, [rbp+220h+var_2A0]
0x18002925d  mov     rcx, r14
0x180029260  mov     rax, [rax+18h]
0x180029264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029269  mov     ebx, eax
0x18002926b  test    eax, eax
0x18002926d  js      short loc_1800292D5
0x18002926f  mov     rax, [r14]
0x180029272  lea     rdx, [rbp+220h+var_298]
0x180029276  mov     rcx, r14
0x180029279  mov     rax, [rax+20h]
0x18002927d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029282  mov     ebx, eax
0x180029284  test    eax, eax
0x180029286  js      short loc_1800292D5
0x180029288  mov     rax, [rbp+220h+var_2A0]
0x18002928c  lea     r8, [rbp+220h+Arguments]; Arguments
0x180029290  mov     [rbp+220h+Arguments], rax
0x180029294  mov     edx, 3EEh; dwMessageId
0x180029299  mov     rax, [rbp+220h+var_298]
0x18002929d  mov     rcx, rdi; this
0x1800292a0  mov     [rbp+220h+Arguments+8], rax
0x1800292a4  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x1800292a9  mov     ebx, eax
0x1800292ab  test    eax, eax
0x1800292ad  js      short loc_1800292D5
0x1800292af  mov     rax, [r13+0]
0x1800292b3  mov     rdx, rdi
0x1800292b6  mov     rcx, r13
0x1800292b9  mov     rax, [rax+18h]
0x1800292bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c2  mov     ebx, eax
0x1800292c4  jmp     short loc_1800292D5
0x1800292c6  mov     rdi, rsi
0x1800292c9  mov     ebx, 80070008h
0x1800292ce  jmp     short loc_1800292D5
0x1800292d0  mov     ebx, 80070057h
0x1800292d5  mov     r9, [rsp+320h+var_2C0]
0x1800292da  xor     esi, esi
0x1800292dc  test    r9, r9
0x1800292df  jz      short loc_180029313
0x1800292e1  mov     rax, [r15]
0x1800292e4  lea     r8, Str
0x1800292eb  mov     edx, ebx
0x1800292ed  mov     dword ptr [rsp+320h+var_300], esi
0x1800292f1  mov     rcx, r15
0x1800292f4  mov     rax, [rax+78h]
0x1800292f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292fd  mov     rcx, [rsp+320h+var_2C0]
0x180029302  mov     rax, [rcx]
0x180029305  mov     rax, [rax+10h]
0x180029309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002930e  mov     [rsp+320h+var_2C0], rsi
0x180029313  mov     rcx, [rsp+320h+var_2C8]
0x180029318  test    rcx, rcx
0x18002931b  jz      short loc_18002935E
0x18002931d  mov     rax, [rcx]
0x180029320  lea     rdx, [rbp+220h+var_290]
0x180029324  mov     rax, [rax+18h]
0x180029328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002932d  mov     rax, [r15]
0x180029330  xor     r9d, r9d
0x180029333  mov     r8, [rbp+220h+var_290]
0x180029337  mov     edx, ebx
0x180029339  mov     rcx, r15
0x18002933c  mov     rax, [rax+80h]
0x180029343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029348  mov     rcx, [rsp+320h+var_2C8]
0x18002934d  mov     rax, [rcx]
0x180029350  mov     rax, [rax+10h]
0x180029354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029359  mov     [rsp+320h+var_2C8], rsi
0x18002935e  mov     rcx, [rsp+320h+var_2B8]
0x180029363  test    rcx, rcx
0x180029366  jz      short loc_180029379
0x180029368  mov     rax, [rcx]
0x18002936b  mov     rax, [rax+10h]
0x18002936f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029374  mov     [rsp+320h+var_2B8], rsi
0x180029379  mov     rcx, [rsp+320h+var_2E0]
0x18002937e  test    rcx, rcx
0x180029381  jz      short loc_180029394
0x180029383  mov     rax, [rcx]
0x180029386  mov     rax, [rax+10h]
0x18002938a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002938f  mov     [rsp+320h+var_2E0], rsi
0x180029394  mov     rcx, [rsp+320h+var_2D8]
0x180029399  test    rcx, rcx
0x18002939c  jz      short loc_1800293AF
0x18002939e  mov     rax, [rcx]
0x1800293a1  mov     rax, [rax+10h]
0x1800293a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293aa  mov     [rsp+320h+var_2D8], rsi
0x1800293af  test    rdi, rdi
0x1800293b2  jz      short loc_1800293C3
0x1800293b4  mov     rax, [rdi]
0x1800293b7  mov     rcx, rdi
0x1800293ba  mov     rax, [rax+10h]
0x1800293be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293c3  lea     rcx, [rbp+220h+var_278]; this
0x1800293c7  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800293cc  mov     eax, ebx
0x1800293ce  mov     rcx, [rbp+220h+var_40]
  ... truncated ...
```
