# MODULE_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x1800200b0`
- end: `0x18002066d`
- name: `?CreateObjects@MODULE_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1469`
- prototype: `int(MODULE_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18001fe08`
- `0x18001fe54`
- `0x1800200b0`
- `0x180022394`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800204b3`
- `msvcrt!_wcsicmp` at `0x1800204b3`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::CreateObjects(
        MODULE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  struct INativeConfigurationSystem *v8; // rdi
  struct INativeSectionException *v9; // r12
  unsigned int v11; // r13d
  APP_OBJECT_UTILS *v12; // rcx
  int v13; // ebx
  MODULE_OBJECT_EXTENSION *v14; // rcx
  int v15; // r9d
  unsigned __int16 *v16; // rdi
  int ModulesConfigurationForApp; // eax
  struct INativeConfigurationElement *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rdx
  struct INativeConfigurationElement *v21; // rcx
  MODULE_OBJECT *v22; // rdi
  MODULE_OBJECT *v23; // rax
  MODULE_OBJECT *v24; // rax
  MODULE_OBJECT *v25; // rcx
  int v26; // eax
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v29; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+68h] [rbp-98h] BYREF
  struct INativeSectionException *v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  struct INativeConfigurationElement *v34; // [rsp+80h] [rbp-80h] BYREF
  struct INativeConfigurationSystem *v35; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-60h] BYREF
  struct ICommandObjectList *v38; // [rsp+A8h] [rbp-58h]
  _BYTE v39[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v40; // [rsp+D0h] [rbp-30h]
  int v41; // [rsp+D8h] [rbp-28h]
  __int16 v42; // [rsp+DCh] [rbp-24h]
  int v43; // [rsp+E0h] [rbp-20h]
  _BYTE v44[32]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v45; // [rsp+108h] [rbp+8h]
  int v46; // [rsp+110h] [rbp+10h]
  __int16 v47; // [rsp+114h] [rbp+14h]
  int v48; // [rsp+118h] [rbp+18h]
  _BYTE v49[32]; // [rsp+120h] [rbp+20h] BYREF
  const unsigned __int16 *v50; // [rsp+140h] [rbp+40h]
  int v51; // [rsp+148h] [rbp+48h]
  __int16 v52; // [rsp+14Ch] [rbp+4Ch]
  int v53; // [rsp+150h] [rbp+50h]
  __int16 v54; // [rsp+160h] [rbp+60h] BYREF
  char v55[510]; // [rsp+162h] [rbp+62h] BYREF
  __int16 v56; // [rsp+360h] [rbp+260h] BYREF
  char v57[510]; // [rsp+362h] [rbp+262h] BYREF
  __int16 v58; // [rsp+560h] [rbp+460h] BYREF
  char v59[510]; // [rsp+562h] [rbp+462h] BYREF

  v38 = a6;
  v35 = 0;
  v34 = 0;
  v30 = 0;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v33 = 0;
  v31 = 0;
  String1 = 0;
  v28 = 0;
  memset_0(v55, 0, sizeof(v55));
  v51 = 512;
  v50 = (const unsigned __int16 *)&v54;
  v52 = 256;
  v53 = 0;
  v54 = 0;
  memset_0(v57, 0, sizeof(v57));
  v41 = 512;
  v40 = (unsigned __int16 *)&v56;
  v42 = 256;
  v43 = 0;
  v56 = 0;
  memset_0(v59, 0, sizeof(v59));
  v46 = 512;
  v47 = 256;
  v45 = (unsigned __int16 *)&v58;
  v48 = 0;
  v58 = 0;
  v29 = 0;
  v36 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v13 = -2147024809;
    goto LABEL_57;
  }
  v11 = 0;
  v13 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v29);
  if ( v13 >= 0 )
  {
    if ( *a3 )
      goto LABEL_11;
    v13 = APP_OBJECT_UTILS::PopParameter(v12, a4, v29, L"MODULE.NAME", (struct STRU *)v49, 0, 1);
    if ( ((v13 + 0x80000000) & 0x80000000) != 0 || v13 == -2147023483 )
    {
      a3 = v50;
LABEL_11:
      v13 = APP_OBJECT_UTILS::PopParameter(v12, a4, v29, L"APP.NAME", (struct STRU *)v39, 0, 1);
      if ( ((v13 + 0x80000000) & 0x80000000) != 0 || v13 == -2147023483 )
      {
        if ( !*a3 || (v13 = APP_OBJECT_UTILS::ValidateEmptyParameters(v14, a4, v29), v13 >= 0) )
        {
          v16 = v40;
          ModulesConfigurationForApp = MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(
                                         v14,
                                         v40,
                                         a4,
                                         v15,
                                         &v35,
                                         (struct STRU *)v44,
                                         &v34,
                                         (struct STRU *)v39,
                                         &v32);
          v9 = v32;
          v13 = ModulesConfigurationForApp;
          v18 = v34;
          if ( ModulesConfigurationForApp < 0 )
          {
            if ( v32 )
            {
              (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, struct INativeSectionException *, _DWORD))(*(_QWORD *)a4 + 112LL))(
                a4,
                (unsigned int)ModulesConfigurationForApp,
                L"MODULE",
                v32,
                0);
              goto LABEL_41;
            }
            if ( ModulesConfigurationForApp == -2147024828 )
            {
              v13 = -2147467259;
              *(_QWORD *)&v36 = L"APP";
              v19 = 3221226475LL;
              v20 = 2147500037LL;
              *((_QWORD *)&v36 + 1) = L"LIST";
            }
            else
            {
              v20 = 2147942402LL;
              if ( ModulesConfigurationForApp != -2147024894 )
                goto LABEL_41;
              *((_QWORD *)&v36 + 1) = v16;
              *(_QWORD *)&v36 = L"APP";
              v19 = 3221226521LL;
            }
            (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a4 + 144LL))(
              a4,
              v20,
              v19,
              &v36,
              0);
            goto LABEL_41;
          }
          v21 = v34;
          v34 = (struct INativeConfigurationElement *)((unsigned __int64)v40 & -(__int64)(v43 != 0));
          v13 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v18 + 40LL))(
                  v21,
                  &v33);
          if ( v13 >= 0 )
          {
            LODWORD(v32) = 0;
            (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 24LL))(v33, &v31);
            while ( 1 )
            {
              v22 = 0;
              if ( v11 >= v31 )
              {
LABEL_54:
                v25 = v22;
                v13 = 0;
                if ( !v22 )
                  goto LABEL_41;
LABEL_55:
                (*(void (__fastcall **)(MODULE_OBJECT *))(*(_QWORD *)v25 + 16LL))(v25);
                goto LABEL_41;
              }
              v28 = 0;
              v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v33 + 32LL))(
                      v33,
                      v11,
                      &v30);
              if ( v13 < 0 )
                goto LABEL_41;
              v23 = (MODULE_OBJECT *)operator new(0xD8u);
              if ( !v23 || (v24 = MODULE_OBJECT::MODULE_OBJECT(v23, v30, v18), (v22 = v24) == 0) )
              {
                v13 = -2147024888;
                goto LABEL_41;
              }
              v13 = MODULE_OBJECT::Create(v24, (const unsigned __int16 *)v34, v45);
              v25 = v22;
              if ( v13 < 0 )
                goto LABEL_55;
              if ( !*a3 )
                break;
              v13 = (*(__int64 (__fastcall **)(MODULE_OBJECT *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v22 + 80LL))(
                      v22,
                      L"MODULE.NAME",
                      &String1);
              v25 = v22;
              if ( v13 < 0 )
                goto LABEL_55;
              if ( _wcsicmp(String1, a3) )
                goto LABEL_35;
              v26 = 1;
              v28 = 1;
              LODWORD(v32) = 1;
LABEL_36:
              if ( v26 )
              {
                v13 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, MODULE_OBJECT *))(*(_QWORD *)v38 + 24LL))(
                        v38,
                        v22);
                v25 = v22;
                if ( v13 < 0 )
                  goto LABEL_55;
                if ( (_DWORD)v32 )
                  goto LABEL_54;
              }
              (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
              v30 = 0;
              (*(void (__fastcall **)(MODULE_OBJECT *))(*(_QWORD *)v22 + 16LL))(v22);
              ++v11;
            }
            v13 = (*(__int64 (__fastcall **)(struct IExtensionContext *, MODULE_OBJECT *, struct ICommandParameterList *, int *))(*(_QWORD *)a4 + 152LL))(
                    a4,
                    v22,
                    v29,
                    &v28);
            v25 = v22;
            if ( v13 < 0 )
              goto LABEL_55;
LABEL_35:
            v26 = v28;
            goto LABEL_36;
          }
LABEL_41:
          if ( v18 )
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v18 + 16LL))(v18);
          v8 = v35;
        }
      }
    }
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v29 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
LABEL_57:
  BUFFER::~BUFFER((BUFFER *)v44);
  BUFFER::~BUFFER((BUFFER *)v39);
  BUFFER::~BUFFER((BUFFER *)v49);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800200b0  mov     [rsp-8+arg_0], rbx
0x1800200b5  push    rbp
0x1800200b6  push    rsi
0x1800200b7  push    rdi
0x1800200b8  push    r12
0x1800200ba  push    r13
0x1800200bc  push    r14
0x1800200be  push    r15
0x1800200c0  lea     rbp, [rsp-670h]
0x1800200c8  sub     rsp, 770h
0x1800200cf  mov     rax, cs:__security_cookie
0x1800200d6  xor     rax, rsp
0x1800200d9  mov     [rbp+6A0h+var_40], rax
0x1800200e0  mov     r13, [rbp+6A0h+arg_28]
0x1800200e7  lea     rcx, [rbp+6A0h+var_63E]; void *
0x1800200eb  mov     r14, [rbp+6A0h+arg_20]
0x1800200f2  xor     eax, eax
0x1800200f4  mov     r15, r8
0x1800200f7  mov     [rbp+6A0h+var_6F8], r13
0x1800200fb  mov     rbx, rdx
0x1800200fe  mov     [rbp+6A0h+var_718], rax
0x180020102  xor     edx, edx; Val
0x180020104  mov     [rbp+6A0h+var_720], rax
0x180020108  mov     r8d, 1FEh; Size
0x18002010e  mov     [rsp+7A0h+var_740], rax
0x180020113  mov     edi, eax
0x180020115  mov     [rsp+7A0h+var_730], rax
0x18002011a  mov     r12d, eax
0x18002011d  mov     [rsp+7A0h+var_728], rax
0x180020122  mov     [rsp+7A0h+var_738], eax
0x180020126  mov     rsi, r9
0x180020129  mov     [rbp+6A0h+String1], rax
0x18002012d  mov     [rsp+7A0h+var_750], eax
0x180020131  call    memset_0
0x180020136  lea     rax, [rbp+6A0h+var_640]
0x18002013a  mov     [rbp+6A0h+var_658], 200h
0x180020141  mov     [rbp+6A0h+var_660], rax
0x180020145  lea     rcx, [rbp+6A0h+var_43E]; void *
0x18002014c  xor     eax, eax
0x18002014e  mov     [rbp+6A0h+var_654], 100h
0x180020154  xor     edx, edx; Val
0x180020156  mov     [rbp+6A0h+var_650], eax
0x180020159  mov     r8d, 1FEh; Size
0x18002015f  mov     [rbp+6A0h+var_640], ax
0x180020163  call    memset_0
0x180020168  lea     rax, [rbp+6A0h+var_440]
0x18002016f  mov     [rbp+6A0h+var_6C8], 200h
0x180020176  mov     [rbp+6A0h+var_6D0], rax
0x18002017a  lea     rcx, [rbp+6A0h+var_23E]; void *
0x180020181  xor     eax, eax
0x180020183  mov     [rbp+6A0h+var_6C4], 100h
0x180020189  xor     edx, edx; Val
0x18002018b  mov     [rbp+6A0h+var_6C0], eax
0x18002018e  mov     r8d, 1FEh; Size
0x180020194  mov     [rbp+6A0h+var_440], ax
0x18002019b  call    memset_0
0x1800201a0  xor     ecx, ecx
0x1800201a2  mov     [rbp+6A0h+var_690], 200h
0x1800201a9  mov     [rbp+6A0h+var_68C], 100h
0x1800201af  lea     rax, [rbp+6A0h+var_240]
0x1800201b6  mov     [rbp+6A0h+var_698], rax
0x1800201ba  xorps   xmm0, xmm0
0x1800201bd  mov     [rbp+6A0h+var_688], ecx
0x1800201c0  mov     [rbp+6A0h+var_240], cx
0x1800201c7  mov     [rsp+7A0h+var_748], rcx
0x1800201cc  movups  [rbp+6A0h+var_710], xmm0
0x1800201d0  test    rbx, rbx
0x1800201d3  jz      loc_180020621
0x1800201d9  test    r15, r15
0x1800201dc  jz      loc_180020621
0x1800201e2  test    rsi, rsi
0x1800201e5  jz      loc_180020621
0x1800201eb  test    r14, r14
0x1800201ee  jz      loc_180020621
0x1800201f4  test    r13, r13
0x1800201f7  jz      loc_180020621
0x1800201fd  mov     rax, [r14]
0x180020200  lea     rdx, [rsp+7A0h+var_748]
0x180020205  mov     rcx, r14
0x180020208  mov     rax, [rax+50h]
0x18002020c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020211  xor     r13d, r13d
0x180020214  mov     ebx, eax
0x180020216  test    eax, eax
0x180020218  js      loc_18002057D
0x18002021e  mov     r14d, 80000000h
0x180020224  cmp     [r15], r13w
0x180020228  jnz     short loc_18002026E
0x18002022a  mov     r8, [rsp+7A0h+var_748]; struct ICommandParameterList *
0x18002022f  lea     rax, [rbp+6A0h+var_680]
0x180020233  mov     dword ptr [rsp+7A0h+var_770], 1; int
0x18002023b  lea     r9, aModuleName_0; "MODULE.NAME"
0x180020242  mov     dword ptr [rsp+7A0h+var_778], r13d; int
0x180020247  mov     rdx, rsi; struct IExtensionContext *
0x18002024a  mov     [rsp+7A0h+var_780], rax; struct STRU *
0x18002024f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180020254  mov     ebx, eax
0x180020256  add     eax, r14d
0x180020259  test    r14d, eax
0x18002025c  jnz     short loc_18002026A
0x18002025e  cmp     ebx, 80070585h
0x180020264  jnz     loc_18002057D
0x18002026a  mov     r15, [rbp+6A0h+var_660]
0x18002026e  mov     r8, [rsp+7A0h+var_748]; struct ICommandParameterList *
0x180020273  lea     rax, [rbp+6A0h+var_6F0]
0x180020277  mov     dword ptr [rsp+7A0h+var_770], 1; int
0x18002027f  lea     r9, aAppName_0; "APP.NAME"
0x180020286  mov     dword ptr [rsp+7A0h+var_778], r13d; int
0x18002028b  mov     rdx, rsi; struct IExtensionContext *
0x18002028e  mov     [rsp+7A0h+var_780], rax; struct STRU *
0x180020293  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180020298  mov     ebx, eax
0x18002029a  add     eax, r14d
0x18002029d  test    r14d, eax
0x1800202a0  jnz     short loc_1800202AE
0x1800202a2  cmp     ebx, 80070585h
0x1800202a8  jnz     loc_18002057D
0x1800202ae  cmp     [r15], r13w
0x1800202b2  jz      short loc_1800202CB
0x1800202b4  mov     r8, [rsp+7A0h+var_748]; struct ICommandParameterList *
0x1800202b9  mov     rdx, rsi; struct IExtensionContext *
0x1800202bc  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x1800202c1  mov     ebx, eax
0x1800202c3  test    eax, eax
0x1800202c5  js      loc_18002057D
0x1800202cb  mov     rdi, [rbp+6A0h+var_6D0]
0x1800202cf  lea     rax, [rsp+7A0h+var_730]
0x1800202d4  mov     [rsp+7A0h+var_760], rax; struct INativeSectionException **
0x1800202d9  mov     r8, rsi; struct IExtensionContext *
0x1800202dc  lea     rax, [rbp+6A0h+var_6F0]
0x1800202e0  mov     rdx, rdi; unsigned __int16 *
0x1800202e3  mov     [rsp+7A0h+var_768], rax; struct STRU *
0x1800202e8  lea     rax, [rbp+6A0h+var_720]
0x1800202ec  mov     [rsp+7A0h+var_770], rax; struct INativeConfigurationElement **
0x1800202f1  lea     rax, [rbp+6A0h+var_6B8]
0x1800202f5  mov     [rsp+7A0h+var_778], rax; struct STRU *
0x1800202fa  lea     rax, [rbp+6A0h+var_718]
0x1800202fe  mov     [rsp+7A0h+var_780], rax; struct INativeConfigurationSystem **
0x180020303  call    ?GetModulesConfigurationForApp@MODULE_OBJECT_EXTENSION@@AEAAJPEBGPEAVIExtensionContext@@HPEAPEAVINativeConfigurationSystem@@PEAVSTRU@@PEAPEAVINativeConfigurationElement@@3PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(ushort const *,IExtensionContext *,int,INativeConfigurationSystem * *,STRU *,INativeConfigurationElement * *,STRU *,INativeSectionException * *)
0x180020308  mov     r12, [rsp+7A0h+var_730]
0x18002030d  mov     ebx, eax
0x18002030f  mov     r14, [rbp+6A0h+var_720]
0x180020313  test    eax, eax
0x180020315  jns     loc_1800203B4
0x18002031b  test    r12, r12
0x18002031e  jz      short loc_180020345
0x180020320  mov     rax, [rsi]
0x180020323  lea     r8, aModule_0; "MODULE"
0x18002032a  mov     r9, r12
0x18002032d  mov     dword ptr [rsp+7A0h+var_780], r13d
0x180020332  mov     edx, ebx
0x180020334  mov     rcx, rsi
0x180020337  mov     rax, [rax+70h]
0x18002033b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020340  jmp     loc_180020565
0x180020345  cmp     ebx, 80070044h
0x18002034b  jnz     short loc_180020390
0x18002034d  lea     rax, aApp_0; "APP"
0x180020354  mov     ebx, 80004005h
0x180020359  mov     qword ptr [rbp+6A0h+var_710], rax
0x18002035d  mov     r8d, 0C00003EBh
0x180020363  lea     rax, aList; "LIST"
0x18002036a  mov     edx, ebx
0x18002036c  mov     qword ptr [rbp+6A0h+var_710+8], rax
0x180020370  mov     rax, [rsi]
0x180020373  lea     r9, [rbp+6A0h+var_710]
0x180020377  mov     rcx, rsi
0x18002037a  mov     dword ptr [rsp+7A0h+var_780], r13d
0x18002037f  mov     rax, [rax+90h]
0x180020386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002038b  jmp     loc_180020565
0x180020390  mov     edx, 80070002h
0x180020395  cmp     ebx, edx
0x180020397  jnz     loc_180020565
0x18002039d  lea     rax, aApp_0; "APP"
0x1800203a4  mov     qword ptr [rbp+6A0h+var_710+8], rdi
0x1800203a8  mov     qword ptr [rbp+6A0h+var_710], rax
0x1800203ac  mov     r8d, 0C0000419h
0x1800203b2  jmp     short loc_180020370
0x1800203b4  mov     eax, [rbp+6A0h+var_6C0]
0x1800203b7  lea     rdx, [rsp+7A0h+var_728]
0x1800203bc  neg     eax
0x1800203be  mov     rcx, r14
0x1800203c1  sbb     rax, rax
0x1800203c4  and     rax, [rbp+6A0h+var_6D0]
0x1800203c8  mov     [rbp+6A0h+var_720], rax
0x1800203cc  mov     rax, [r14]
0x1800203cf  mov     rax, [rax+28h]
0x1800203d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203d8  mov     ebx, eax
0x1800203da  test    eax, eax
0x1800203dc  js      loc_180020565
0x1800203e2  mov     rcx, [rsp+7A0h+var_728]
0x1800203e7  lea     rdx, [rsp+7A0h+var_738]
0x1800203ec  mov     dword ptr [rsp+7A0h+var_730], r13d
0x1800203f1  mov     rax, [rcx]
0x1800203f4  mov     rax, [rax+18h]
0x1800203f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203fd  xor     ebx, ebx
0x1800203ff  mov     rdi, rbx
0x180020402  cmp     r13d, [rsp+7A0h+var_738]
0x180020407  jnb     loc_1800205F9
0x18002040d  mov     rcx, [rsp+7A0h+var_728]
0x180020412  lea     r8, [rsp+7A0h+var_740]
0x180020417  mov     [rsp+7A0h+var_750], ebx
0x18002041b  mov     edx, r13d
0x18002041e  mov     rax, [rcx]
0x180020421  mov     rax, [rax+20h]
0x180020425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002042a  mov     ebx, eax
0x18002042c  test    eax, eax
0x18002042e  js      loc_180020562
0x180020434  mov     ecx, 0D8h; Size
0x180020439  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002043e  test    rax, rax
0x180020441  jz      loc_18002055D
0x180020447  mov     rdx, [rsp+7A0h+var_740]; struct INativeConfigurationElement *
0x18002044c  mov     r8, r14; struct INativeConfigurationElement *
0x18002044f  mov     rcx, rax; this
0x180020452  call    ??0MODULE_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; MODULE_OBJECT::MODULE_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180020457  mov     rdi, rax
0x18002045a  test    rax, rax
0x18002045d  jz      loc_18002055D
0x180020463  mov     r8, [rbp+6A0h+var_698]; unsigned __int16 *
0x180020467  mov     rcx, rax; this
0x18002046a  mov     rdx, [rbp+6A0h+var_720]; unsigned __int16 *
0x18002046e  call    ?Create@MODULE_OBJECT@@QEAAJPEBG0@Z; MODULE_OBJECT::Create(ushort const *,ushort const *)
0x180020473  mov     ebx, eax
0x180020475  mov     rcx, rdi
0x180020478  xor     eax, eax
0x18002047a  test    ebx, ebx
0x18002047c  js      loc_18002060D
0x180020482  cmp     [r15], ax
0x180020486  jz      short loc_1800204CE
0x180020488  mov     rax, [rdi]
0x18002048b  lea     r8, [rbp+6A0h+String1]
0x18002048f  lea     rdx, aModuleName_0; "MODULE.NAME"
0x180020496  mov     rax, [rax+50h]
0x18002049a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002049f  mov     ebx, eax
0x1800204a1  mov     rcx, rdi
0x1800204a4  test    eax, eax
0x1800204a6  js      loc_18002060D
0x1800204ac  mov     rcx, [rbp+6A0h+String1]; String1
0x1800204b0  mov     rdx, r15; String2
0x1800204b3  call    cs:__imp__wcsicmp
0x1800204b9  xor     ebx, ebx
0x1800204bb  test    eax, eax
0x1800204bd  jnz     short loc_1800204FC
0x1800204bf  lea     ecx, [rbx+1]
0x1800204c2  mov     eax, ecx
0x1800204c4  mov     [rsp+7A0h+var_750], ecx
0x1800204c8  mov     dword ptr [rsp+7A0h+var_730], ecx
0x1800204cc  jmp     short loc_180020500
0x1800204ce  mov     rax, [rsi]
0x1800204d1  lea     r9, [rsp+7A0h+var_750]
0x1800204d6  mov     r8, [rsp+7A0h+var_748]
0x1800204db  mov     rdx, rdi
0x1800204de  mov     rcx, rsi
0x1800204e1  mov     rax, [rax+98h]
0x1800204e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204ed  mov     ebx, eax
0x1800204ef  mov     rcx, rdi
0x1800204f2  test    eax, eax
0x1800204f4  js      loc_18002060D
0x1800204fa  xor     ebx, ebx
0x1800204fc  mov     eax, [rsp+7A0h+var_750]
0x180020500  test    eax, eax
0x180020502  jz      short loc_180020530
0x180020504  mov     rcx, [rbp+6A0h+var_6F8]
0x180020508  mov     rdx, rdi
0x18002050b  mov     rax, [rcx]
0x18002050e  mov     rax, [rax+18h]
0x180020512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020517  mov     ebx, eax
0x180020519  mov     rcx, rdi
0x18002051c  test    eax, eax
0x18002051e  js      loc_18002060D
0x180020524  xor     ebx, ebx
0x180020526  cmp     dword ptr [rsp+7A0h+var_730], ebx
0x18002052a  jnz     loc_1800205F9
0x180020530  mov     rcx, [rsp+7A0h+var_740]
0x180020535  mov     rax, [rcx]
0x180020538  mov     rax, [rax+10h]
0x18002053c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020541  mov     [rsp+7A0h+var_740], rbx
0x180020546  mov     rcx, rdi
0x180020549  mov     rax, [rdi]
0x18002054c  mov     rax, [rax+10h]
0x180020550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020555  inc     r13d
0x180020558  jmp     loc_1800203FF
0x18002055d  mov     ebx, 80070008h
0x180020562  xor     r13d, r13d
0x180020565  test    r14, r14
0x180020568  jz      short loc_180020579
0x18002056a  mov     rax, [r14]
0x18002056d  mov     rcx, r14
0x180020570  mov     rax, [rax+10h]
0x180020574  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
