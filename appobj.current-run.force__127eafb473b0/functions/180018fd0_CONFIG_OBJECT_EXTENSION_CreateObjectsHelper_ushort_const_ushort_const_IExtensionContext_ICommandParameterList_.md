# CONFIG_OBJECT_EXTENSION::CreateObjectsHelper(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,int,int,ICommandObjectList *)

- ea: `0x180018fd0`
- end: `0x1800194dc`
- name: `?CreateObjectsHelper@CONFIG_OBJECT_EXTENSION@@AEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@HHPEAVICommandObjectList@@@Z`
- size: `1292`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, int, int, struct ICommandObjectList *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018fa0`
- `0x18001a850`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180004a70`
- `0x180005440`
- `0x180012ad4`
- `0x180018b78`
- `0x180018fd0`
- `0x18001d714`
- `0x18002b860`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180034d90`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::CreateObjectsHelper(
        CONFIG_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        int a6,
        int a7,
        struct ICommandObjectList *a8)
{
  COMMAND_OBJECT *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // r8
  CONFIG_OBJECT_EXTENSION *v14; // rcx
  int v15; // ebx
  APP_OBJECT_UTILS *v16; // rcx
  unsigned __int16 *v17; // r13
  int v18; // eax
  int v19; // r12d
  int v20; // eax
  unsigned int i; // r15d
  int v22; // eax
  COMMAND_OBJECT *v23; // rax
  struct INativeConfigurationElement *v24; // r9
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  struct ICommandParameterList *v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-98h] BYREF
  struct ICommandObjectList *v32; // [rsp+70h] [rbp-90h]
  _BYTE v33[32]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+A0h] [rbp-60h]
  __int16 v36; // [rsp+A4h] [rbp-5Ch]
  int v37; // [rsp+A8h] [rbp-58h]
  _BYTE v38[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 *v39; // [rsp+D0h] [rbp-30h]
  int v40; // [rsp+D8h] [rbp-28h]
  __int16 v41; // [rsp+DCh] [rbp-24h]
  int v42; // [rsp+E0h] [rbp-20h]
  _BYTE v43[32]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v44; // [rsp+108h] [rbp+8h]
  int v45; // [rsp+110h] [rbp+10h]
  __int16 v46; // [rsp+114h] [rbp+14h]
  int v47; // [rsp+118h] [rbp+18h]
  _QWORD v48[1024]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v49; // [rsp+2120h] [rbp+2020h] BYREF
  _BYTE v50[510]; // [rsp+2122h] [rbp+2022h] BYREF
  __int16 v51; // [rsp+2320h] [rbp+2220h] BYREF
  _BYTE v52[510]; // [rsp+2322h] [rbp+2222h] BYREF
  __int16 v53; // [rsp+2520h] [rbp+2420h] BYREF
  _BYTE v54[510]; // [rsp+2522h] [rbp+2422h] BYREF

  v32 = a8;
  v31 = 0;
  memset_0(v52, 0, sizeof(v52));
  v46 = 256;
  v44 = (unsigned __int16 *)&v51;
  v45 = 512;
  v47 = 0;
  v51 = 0;
  memset_0(v50, 0, sizeof(v50));
  v35 = 512;
  v37 = 0;
  v49 = 0;
  v29 = 0;
  v11 = 0;
  v26 = 0;
  v28 = 0;
  v30 = 0;
  v34 = (unsigned __int16 *)&v49;
  v36 = 256;
  memset_0(v54, 0, sizeof(v54));
  v40 = 512;
  v39 = &v53;
  v42 = 0;
  v53 = 0;
  v41 = 256;
  memset_0(v48, 0, sizeof(v48));
  v27 = 1024;
  if ( a2 && a3 && a4 && a5 && a8 )
  {
    v15 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
            a5,
            &v30);
    if ( v15 >= 0 )
    {
      v15 = CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(v14, a4, v30, (const unsigned __int16 **)&v31, 0);
      if ( (int)(v15 + 0x80000000) < 0 || v15 == -2147023483 )
      {
        v15 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)0x80000000LL, a4, v30);
        if ( v15 >= 0 )
        {
          v15 = APP_OBJECT_UTILS::ResolveConfigPath(v16, a4, a3, (struct STRU *)v43, 0, 0);
          if ( v15 >= 0 )
          {
            v17 = v44;
            v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int16 *, __int64))(*(_QWORD *)a4 + 72LL))(
                    a4,
                    v44,
                    &v49,
                    256);
            if ( v15 >= 0 )
            {
              STRU::SyncWithBuffer((STRU *)v33);
              v18 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64 *))(*(_QWORD *)a4 + 80LL))(
                      a4,
                      v34,
                      &v29);
              v13 = 0;
              v15 = v18;
              if ( v18 >= 0 )
              {
                if ( v31 && *v31 )
                {
                  v19 = 0;
                  v48[0] = v31;
                  v27 = 1;
                }
                else
                {
                  v19 = 1;
                  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *))(*(_QWORD *)v29 + 80LL))(
                          v29,
                          v48,
                          &v27);
                  v13 = 0;
                  v15 = v20;
                  if ( v20 < 0 )
                    goto LABEL_37;
                }
                for ( i = 0; ; ++i )
                {
                  v11 = 0;
                  if ( i >= v27 )
                    break;
                  v31 = (unsigned __int16 *)v48[i];
                  v22 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, __int64 *, __int64 *, _QWORD, int))(*(_QWORD *)v29 + 112LL))(
                          v29,
                          v31,
                          v17,
                          &v28,
                          &v26,
                          0,
                          a6 != 0 ? 26 : 10);
                  v13 = 0;
                  v15 = v22;
                  if ( v22 >= 0 )
                  {
                    v23 = (COMMAND_OBJECT *)operator new(0xD8u);
                    v11 = v23;
                    if ( !v23 )
                    {
                      v15 = -2147024888;
                      v11 = 0;
                      break;
                    }
                    COMMAND_OBJECT::COMMAND_OBJECT(v23);
                    *(_QWORD *)v11 = &CONFIG_OBJECT::`vftable';
                    COMMAND_OBJECT::SetConfigElement(v11, v24);
                    v15 = CONFIG_OBJECT::Create(v11, v31, v34, v17);
                    if ( v15 < 0 )
                      break;
                    v15 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, COMMAND_OBJECT *))(*(_QWORD *)v32 + 24LL))(
                            v32,
                            v11);
                    if ( v15 < 0 )
                      break;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                    v28 = 0;
                    if ( v26 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                      v26 = 0;
                    }
                    (*(void (__fastcall **)(COMMAND_OBJECT *))(*(_QWORD *)v11 + 16LL))(v11);
                    v13 = 0;
                  }
                  else
                  {
                    if ( !v19 || v22 != -2147023728 && v22 != -2147024846 )
                    {
                      if ( v26 )
                      {
                        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a4 + 112LL))(
                          a4,
                          (unsigned int)v22,
                          &Str,
                          v26,
                          0);
                        v13 = 0;
                      }
                      v11 = 0;
                      break;
                    }
                    if ( v26 )
                    {
                      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v26 + 16LL))(v26, v12, 0);
                      v13 = 0;
                      v26 = 0;
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
    v15 = -2147024809;
  }
LABEL_37:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v29 + 16LL))(v29, v12, v13);
    v29 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, v12, v13);
    v26 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(COMMAND_OBJECT *, __int64, __int64))(*(_QWORD *)v11 + 16LL))(v11, v12, v13);
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v28 + 16LL))(v28, v12, v13);
    v28 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *, __int64, __int64))(*(_QWORD *)v30 + 16LL))(v30, v12, v13);
    v30 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v38);
  BUFFER::~BUFFER((BUFFER *)v33);
  BUFFER::~BUFFER((BUFFER *)v43);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180018fd0  mov     [rsp-8+arg_0], rbx
0x180018fd5  push    rbp
0x180018fd6  push    rsi
0x180018fd7  push    rdi
0x180018fd8  push    r12
0x180018fda  push    r13
0x180018fdc  push    r14
0x180018fde  push    r15
0x180018fe0  lea     rbp, [rsp-2630h]
0x180018fe8  mov     eax, 2730h
0x180018fed  call    _alloca_probe
0x180018ff2  sub     rsp, rax
0x180018ff5  mov     rax, cs:__security_cookie
0x180018ffc  xor     rax, rsp
0x180018fff  mov     [rbp+2660h+var_40], rax
0x180019006  mov     r12, [rbp+2660h+arg_38]
0x18001900d  lea     rcx, [rbp+2660h+var_43E]; void *
0x180019014  mov     r14, [rbp+2660h+arg_20]
0x18001901b  mov     r15, r8
0x18001901e  mov     rbx, rdx
0x180019021  mov     [rsp+2760h+var_26F0], r12
0x180019026  mov     edi, 1FEh
0x18001902b  mov     [rsp+2760h+var_26F8], 0
0x180019034  mov     r8d, edi; Size
0x180019037  xor     edx, edx; Val
0x180019039  mov     rsi, r9
0x18001903c  call    memset_0
0x180019041  lea     rax, [rbp+2660h+var_440]
0x180019048  mov     [rbp+2660h+var_264C], 100h
0x18001904e  mov     [rbp+2660h+var_2658], rax
0x180019052  lea     r13d, [rdi+2]
0x180019056  xor     eax, eax
0x180019058  mov     [rbp+2660h+var_2650], r13d
0x18001905c  mov     r8d, edi; Size
0x18001905f  mov     [rbp+2660h+var_2648], eax
0x180019062  xor     edx, edx; Val
0x180019064  mov     [rbp+2660h+var_440], ax
0x18001906b  lea     rcx, [rbp+2660h+var_63E]; void *
0x180019072  call    memset_0
0x180019077  xor     ecx, ecx
0x180019079  mov     [rbp+2660h+var_26C0], r13d
0x18001907d  mov     [rbp+2660h+var_26B8], ecx
0x180019080  lea     rax, [rbp+2660h+var_640]
0x180019087  mov     [rbp+2660h+var_640], cx
0x18001908e  lea     r8d, [r13-2]; Size
0x180019092  mov     [rsp+2760h+var_2708], rcx
0x180019097  mov     edi, ecx
0x180019099  mov     [rsp+2760h+var_2720], rcx
0x18001909e  xor     edx, edx; Val
0x1800190a0  mov     [rsp+2760h+var_2710], rcx
0x1800190a5  mov     [rsp+2760h+var_2700], rcx
0x1800190aa  lea     rcx, [rbp+2660h+var_23E]; void *
0x1800190b1  mov     [rbp+2660h+var_26C8], rax
0x1800190b5  mov     [rbp+2660h+var_26BC], 100h
0x1800190bb  call    memset_0
0x1800190c0  lea     rax, [rbp+2660h+var_240]
0x1800190c7  mov     [rbp+2660h+var_2688], r13d
0x1800190cb  xor     r13d, r13d
0x1800190ce  mov     [rbp+2660h+var_2690], rax
0x1800190d2  xor     edx, edx; Val
0x1800190d4  mov     [rbp+2660h+var_2680], r13d
0x1800190d8  mov     r8d, 2000h; Size
0x1800190de  mov     [rbp+2660h+var_240], r13w
0x1800190e6  lea     rcx, [rbp+2660h+var_2640]; void *
0x1800190ea  mov     [rbp+2660h+var_2684], 100h
0x1800190f0  call    memset_0
0x1800190f5  mov     [rsp+2760h+var_2718], 400h
0x1800190fd  test    rbx, rbx
0x180019100  jz      loc_180019405
0x180019106  test    r15, r15
0x180019109  jz      loc_180019405
0x18001910f  test    rsi, rsi
0x180019112  jz      loc_180019405
0x180019118  test    r14, r14
0x18001911b  jz      loc_180019405
0x180019121  test    r12, r12
0x180019124  jz      loc_180019405
0x18001912a  mov     rax, [r14]
0x18001912d  lea     rdx, [rsp+2760h+var_2700]
0x180019132  mov     rcx, r14
0x180019135  mov     rax, [rax+50h]
0x180019139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001913e  mov     ebx, eax
0x180019140  test    eax, eax
0x180019142  js      loc_18001940A
0x180019148  mov     r8, [rsp+2760h+var_2700]; struct ICommandParameterList *
0x18001914d  lea     r9, [rsp+2760h+var_26F8]; unsigned __int16 **
0x180019152  mov     rdx, rsi; struct IExtensionContext *
0x180019155  mov     dword ptr [rsp+2760h+var_2740], r13d; int
0x18001915a  call    ?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z; CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)
0x18001915f  mov     ecx, 80000000h; this
0x180019164  mov     ebx, eax
0x180019166  add     eax, ecx
0x180019168  test    ecx, eax
0x18001916a  jnz     short loc_180019178
0x18001916c  cmp     ebx, 80070585h
0x180019172  jnz     loc_18001940A
0x180019178  mov     r8, [rsp+2760h+var_2700]; struct ICommandParameterList *
0x18001917d  mov     rdx, rsi; struct IExtensionContext *
0x180019180  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180019185  mov     ebx, eax
0x180019187  test    eax, eax
0x180019189  js      loc_18001940A
0x18001918f  mov     [rsp+2760h+var_2738], r13; struct SITE_OBJECT **
0x180019194  lea     r9, [rbp+2660h+var_2678]; struct STRU *
0x180019198  mov     r8, r15; unsigned __int16 *
0x18001919b  mov     [rsp+2760h+var_2740], r13; unsigned __int16 **
0x1800191a0  mov     rdx, rsi; struct IExtensionContext *
0x1800191a3  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)
0x1800191a8  mov     ebx, eax
0x1800191aa  test    eax, eax
0x1800191ac  js      loc_18001940A
0x1800191b2  mov     rax, [rsi]
0x1800191b5  lea     r8, [rbp+2660h+var_640]
0x1800191bc  mov     r13, [rbp+2660h+var_2658]
0x1800191c0  mov     r9d, 100h
0x1800191c6  mov     rdx, r13
0x1800191c9  mov     rcx, rsi
0x1800191cc  mov     rax, [rax+48h]
0x1800191d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191d5  mov     ebx, eax
0x1800191d7  test    eax, eax
0x1800191d9  js      loc_18001940A
0x1800191df  lea     rcx, [rsp+2760h+var_26E8]; this
0x1800191e4  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800191e9  mov     rax, [rsi]
0x1800191ec  lea     r8, [rsp+2760h+var_2708]
0x1800191f1  mov     rdx, [rbp+2660h+var_26C8]
0x1800191f5  mov     rcx, rsi
0x1800191f8  mov     rax, [rax+50h]
0x1800191fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019201  xor     r8d, r8d
0x180019204  mov     ebx, eax
0x180019206  test    eax, eax
0x180019208  js      loc_18001940A
0x18001920e  neg     [rbp+2660h+arg_28]
0x180019214  mov     rax, [rsp+2760h+var_26F8]
0x180019219  sbb     r14d, r14d
0x18001921c  and     r14d, 10h
0x180019220  add     r14d, 0Ah
0x180019224  test    rax, rax
0x180019227  jz      short loc_180019240
0x180019229  cmp     [rax], r8w
0x18001922d  jz      short loc_180019240
0x18001922f  mov     r12d, r8d
0x180019232  mov     [rbp+2660h+var_2640], rax
0x180019236  mov     [rsp+2760h+var_2718], 1
0x18001923e  jmp     short loc_18001926D
0x180019240  mov     rcx, [rsp+2760h+var_2708]
0x180019245  lea     r8, [rsp+2760h+var_2718]
0x18001924a  lea     rdx, [rbp+2660h+var_2640]
0x18001924e  mov     r12d, 1
0x180019254  mov     rax, [rcx]
0x180019257  mov     rax, [rax+50h]
0x18001925b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019260  xor     r8d, r8d
0x180019263  mov     ebx, eax
0x180019265  test    eax, eax
0x180019267  js      loc_18001940A
0x18001926d  mov     r15d, r8d
0x180019270  mov     rdi, r8
0x180019273  cmp     r15d, [rsp+2760h+var_2718]
0x180019278  jnb     loc_18001940A
0x18001927e  mov     rcx, [rsp+2760h+var_2708]
0x180019283  lea     r9, [rsp+2760h+var_2710]
0x180019288  mov     eax, r15d
0x18001928b  mov     [rsp+2760h+var_2730], r14d
0x180019290  mov     [rsp+2760h+var_2738], r8
0x180019295  lea     r8, [rsp+2760h+var_2720]
0x18001929a  mov     [rsp+2760h+var_2740], r8
0x18001929f  mov     r8, r13
0x1800192a2  mov     rdx, [rbp+rax*8+2660h+var_2640]
0x1800192a7  mov     [rsp+2760h+var_26F8], rdx
0x1800192ac  mov     rax, [rcx]
0x1800192af  mov     rax, [rax+70h]
0x1800192b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192b8  xor     r8d, r8d
0x1800192bb  mov     ebx, eax
0x1800192bd  test    eax, eax
0x1800192bf  jns     short loc_180019303
0x1800192c1  test    r12d, r12d
0x1800192c4  jz      loc_1800193CA
0x1800192ca  cmp     eax, 80070490h
0x1800192cf  jz      short loc_1800192DC
0x1800192d1  cmp     eax, 80070032h
0x1800192d6  jnz     loc_1800193CA
0x1800192dc  mov     rcx, [rsp+2760h+var_2720]
0x1800192e1  test    rcx, rcx
0x1800192e4  jz      loc_1800193C2
0x1800192ea  mov     rax, [rcx]
0x1800192ed  mov     rax, [rax+10h]
0x1800192f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f6  xor     r8d, r8d
0x1800192f9  mov     [rsp+2760h+var_2720], r8
0x1800192fe  jmp     loc_1800193C2
0x180019303  mov     ecx, 0D8h; Size
0x180019308  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001930d  mov     rdi, rax
0x180019310  test    rax, rax
0x180019313  jz      loc_1800193FC
0x180019319  mov     r9, [rsp+2760h+var_2710]
0x18001931e  mov     rcx, rax; this
0x180019321  call    ??0COMMAND_OBJECT@@QEAA@XZ; COMMAND_OBJECT::COMMAND_OBJECT(void)
0x180019326  lea     rcx, ??_7CONFIG_OBJECT@@6B@; const CONFIG_OBJECT::`vftable'
0x18001932d  mov     rdx, r9; struct INativeConfigurationElement *
0x180019330  mov     [rdi], rcx
0x180019333  mov     rcx, rdi; this
0x180019336  call    ?SetConfigElement@COMMAND_OBJECT@@QEAAXPEAVINativeConfigurationElement@@@Z; COMMAND_OBJECT::SetConfigElement(INativeConfigurationElement *)
0x18001933b  mov     r8, [rbp+2660h+var_26C8]; unsigned __int16 *
0x18001933f  mov     r9, r13; unsigned __int16 *
0x180019342  mov     rdx, [rsp+2760h+var_26F8]; unsigned __int16 *
0x180019347  mov     rcx, rdi; this
0x18001934a  call    ?Create@CONFIG_OBJECT@@QEAAJPEBG00@Z; CONFIG_OBJECT::Create(ushort const *,ushort const *,ushort const *)
0x18001934f  mov     ebx, eax
0x180019351  test    eax, eax
0x180019353  js      loc_18001940A
0x180019359  mov     rcx, [rsp+2760h+var_26F0]
0x18001935e  mov     rdx, rdi
0x180019361  mov     rax, [rcx]
0x180019364  mov     rax, [rax+18h]
0x180019368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001936d  mov     ebx, eax
0x18001936f  test    eax, eax
0x180019371  js      loc_18001940A
0x180019377  mov     rcx, [rsp+2760h+var_2710]
0x18001937c  mov     rax, [rcx]
0x18001937f  mov     rax, [rax+10h]
0x180019383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019388  mov     rcx, [rsp+2760h+var_2720]
0x18001938d  mov     [rsp+2760h+var_2710], 0
0x180019396  test    rcx, rcx
0x180019399  jz      short loc_1800193B0
0x18001939b  mov     rax, [rcx]
0x18001939e  mov     rax, [rax+10h]
0x1800193a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193a7  mov     [rsp+2760h+var_2720], 0
0x1800193b0  mov     rax, [rdi]
0x1800193b3  mov     rcx, rdi
0x1800193b6  mov     rax, [rax+10h]
0x1800193ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193bf  xor     r8d, r8d
0x1800193c2  inc     r15d
0x1800193c5  jmp     loc_180019270
0x1800193ca  mov     rcx, [rsp+2760h+var_2720]
0x1800193cf  test    rcx, rcx
0x1800193d2  jz      short loc_1800193F7
0x1800193d4  mov     rax, [rsi]
0x1800193d7  mov     r9, rcx
0x1800193da  mov     dword ptr [rsp+2760h+var_2740], r8d
0x1800193df  mov     edx, ebx
0x1800193e1  lea     r8, Str
0x1800193e8  mov     rcx, rsi
0x1800193eb  mov     rax, [rax+70h]
0x1800193ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193f4  xor     r8d, r8d
0x1800193f7  mov     rdi, r8
0x1800193fa  jmp     short loc_18001940A
0x1800193fc  mov     ebx, 80070008h
0x180019401  xor     edi, edi
0x180019403  jmp     short loc_18001940A
0x180019405  mov     ebx, 80070057h
0x18001940a  mov     rcx, [rsp+2760h+var_2708]
0x18001940f  test    rcx, rcx
0x180019412  jz      short loc_180019429
0x180019414  mov     rax, [rcx]
0x180019417  mov     rax, [rax+10h]
0x18001941b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019420  mov     [rsp+2760h+var_2708], 0
0x180019429  mov     rcx, [rsp+2760h+var_2720]
0x18001942e  test    rcx, rcx
0x180019431  jz      short loc_180019448
0x180019433  mov     rax, [rcx]
0x180019436  mov     rax, [rax+10h]
0x18001943a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001943f  mov     [rsp+2760h+var_2720], 0
0x180019448  test    rdi, rdi
0x18001944b  jz      short loc_18001945C
0x18001944d  mov     rax, [rdi]
0x180019450  mov     rcx, rdi
0x180019453  mov     rax, [rax+10h]
0x180019457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001945c  mov     rcx, [rsp+2760h+var_2710]
0x180019461  xor     edi, edi
0x180019463  test    rcx, rcx
0x180019466  jz      short loc_180019479
0x180019468  mov     rax, [rcx]
0x18001946b  mov     rax, [rax+10h]
0x18001946f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019474  mov     [rsp+2760h+var_2710], rdi
0x180019479  mov     rcx, [rsp+2760h+var_2700]
0x18001947e  test    rcx, rcx
0x180019481  jz      short loc_180019494
0x180019483  mov     rax, [rcx]
0x180019486  mov     rax, [rax+10h]
0x18001948a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001948f  mov     [rsp+2760h+var_2700], rdi
0x180019494  lea     rcx, [rbp+2660h+var_26B0]; this
0x180019498  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001949d  lea     rcx, [rsp+2760h+var_26E8]; this
0x1800194a2  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
  ... truncated ...
```
