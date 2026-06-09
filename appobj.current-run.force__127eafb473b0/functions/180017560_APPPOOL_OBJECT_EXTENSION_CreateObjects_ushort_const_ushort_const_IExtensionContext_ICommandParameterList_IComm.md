# APPPOOL_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180017560`
- end: `0x180017a1c`
- name: `?CreateObjects@APPPOOL_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1212`
- prototype: `int(APPPOOL_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180016e28`
- `0x1800172ec`
- `0x180017560`
- `0x18001833c`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017892`
- `msvcrt!_wcsicmp` at `0x180017892`

## pseudocode

```c
__int64 __fastcall APPPOOL_OBJECT_EXTENSION::CreateObjects(
        APPPOOL_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  unsigned int v6; // r15d
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // eax
  const wchar_t *v13; // r13
  APPPOOL_OBJECT *v14; // rax
  APPPOOL_OBJECT *v15; // rdi
  __int64 v16; // rax
  unsigned int v17; // ebx
  BOOL v18; // ecx
  BOOL v20; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v21; // [rsp+48h] [rbp-B8h] BYREF
  struct ICommandParameterList *v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp-80h] BYREF
  APPPOOL_OBJECT_EXTENSION *v30; // [rsp+88h] [rbp-78h]
  _BYTE v31[32]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String2; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B8h] [rbp-48h]
  __int16 v34; // [rsp+BCh] [rbp-44h]
  int v35; // [rsp+C0h] [rbp-40h]
  __int16 v36; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v37[510]; // [rsp+D2h] [rbp-2Eh] BYREF

  v6 = 0;
  v30 = this;
  v26 = 0;
  v21 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v23 = 0;
  v20 = 0;
  String1 = 0;
  memset_0(v37, 0, sizeof(v37));
  v33 = 512;
  String2 = (wchar_t *)&v36;
  v34 = 256;
  v35 = 0;
  v36 = 0;
  v22 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v11 = -2147024809;
    goto LABEL_39;
  }
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v22);
  if ( v11 < 0 )
    goto LABEL_39;
  if ( *a3 )
    goto LABEL_11;
  v12 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v10, a4, v22, L"APPPOOL.NAME", (struct STRU *)v31, 0, 1);
  v10 = 0x80000000LL;
  v11 = v12;
  if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147023483 )
    goto LABEL_39;
  a3 = String2;
  if ( *String2 )
  {
LABEL_11:
    v11 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v10, a4, v22);
    if ( v11 < 0 )
      goto LABEL_39;
  }
  v13 = &Str;
  if ( ((*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a4 + 32LL))(a4) & 8) == 0 )
    v13 = L"MACHINE/WEBROOT/APPHOST";
  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a4 + 80LL))(
          a4,
          v13,
          &v27);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *, _QWORD))(*(_QWORD *)v27 + 24LL))(
            v27,
            L"system.applicationHost/applicationPools",
            L"MACHINE/WEBROOT/APPHOST",
            &v26,
            &v28,
            0);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v26 + 40LL))(
              v26,
              &v25);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 24LL))(v25, &v23);
        if ( v11 >= 0 )
        {
          while ( v6 < v23 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v25 + 32LL))(
                    v25,
                    v6,
                    &v21);
            if ( v11 < 0 )
              break;
            v14 = (APPPOOL_OBJECT *)operator new(0xD8u);
            if ( !v14 || (v15 = APPPOOL_OBJECT::APPPOOL_OBJECT(v14, v21, v26)) == 0 )
            {
              v11 = -2147024888;
              break;
            }
            v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                    v21,
                    L"name",
                    &String1,
                    0,
                    0);
            if ( v11 < 0 )
              goto LABEL_36;
            v16 = *(_QWORD *)a4;
            v17 = 4;
            v24 = 4;
            if ( ((*(__int64 (__fastcall **)(struct IExtensionContext *))(v16 + 32))(a4) & 4) == 0 )
            {
              APPPOOL_OBJECT_EXTENSION::GetApppoolState(
                v30,
                String1,
                (enum __MIDL___MIDL_itf_rscaps_0000_0003_0001 *)&v24);
              v17 = v24;
            }
            v11 = APPPOOL_OBJECT::Create(v15, v13, v17);
            if ( v11 < 0 )
              goto LABEL_36;
            if ( *a3 )
            {
              v18 = _wcsicmp(String1, a3) == 0;
              v20 = v18;
            }
            else
            {
              v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, APPPOOL_OBJECT *, struct ICommandParameterList *, BOOL *))(*(_QWORD *)a4 + 152LL))(
                      a4,
                      v15,
                      v22,
                      &v20);
              if ( v11 < 0 )
                goto LABEL_36;
              v18 = v20;
            }
            if ( v18 )
            {
              v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, APPPOOL_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                      a6,
                      v15);
              if ( v11 < 0 || *a3 )
              {
LABEL_36:
                (*(void (__fastcall **)(APPPOOL_OBJECT *))(*(_QWORD *)v15 + 16LL))(v15);
                break;
              }
            }
            (*(void (__fastcall **)(APPPOOL_OBJECT *))(*(_QWORD *)v15 + 16LL))(v15);
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
            ++v6;
            v21 = 0;
          }
        }
      }
    }
    else if ( v28 )
    {
      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a4 + 112LL))(
        a4,
        (unsigned int)v11,
        &Str,
        v28,
        0);
    }
  }
LABEL_39:
  if ( v21 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v31);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017560  mov     [rsp-8+arg_8], rbx
0x180017565  push    rbp
0x180017566  push    rsi
0x180017567  push    rdi
0x180017568  push    r12
0x18001756a  push    r13
0x18001756c  push    r14
0x18001756e  push    r15
0x180017570  lea     rbp, [rsp-1E0h]
0x180017578  sub     rsp, 2E0h
0x18001757f  mov     rax, cs:__security_cookie
0x180017586  xor     rax, rsp
0x180017589  mov     [rbp+210h+var_40], rax
0x180017590  mov     rdi, [rbp+210h+arg_20]
0x180017597  xor     r15d, r15d
0x18001759a  mov     r12, [rbp+210h+arg_28]
0x1800175a1  mov     r14, r8
0x1800175a4  mov     rbx, rdx
0x1800175a7  mov     [rbp+210h+var_288], rcx
0x1800175ab  xor     edx, edx; Val
0x1800175ad  mov     [rsp+310h+var_2A8], r15
0x1800175b2  mov     r8d, 1FEh; Size
0x1800175b8  mov     [rsp+310h+var_2C8], r15
0x1800175bd  lea     rcx, [rbp+210h+var_23E]; void *
0x1800175c1  mov     [rsp+310h+var_2B0], r15
0x1800175c6  mov     [rsp+310h+var_2A0], r15
0x1800175cb  mov     rsi, r9
0x1800175ce  mov     [rsp+310h+var_298], r15
0x1800175d3  mov     [rsp+310h+var_2B8], r15d
0x1800175d8  mov     [rsp+310h+var_2D0], r15d
0x1800175dd  mov     [rbp+210h+String1], r15
0x1800175e1  call    memset_0
0x1800175e6  mov     [rbp+210h+var_258], 200h
0x1800175ed  lea     rax, [rbp+210h+var_240]
0x1800175f1  mov     [rbp+210h+String2], rax
0x1800175f5  mov     [rbp+210h+var_254], 100h
0x1800175fb  mov     [rbp+210h+var_250], r15d
0x1800175ff  mov     [rbp+210h+var_240], r15w
0x180017604  mov     [rsp+310h+var_2C0], r15
0x180017609  test    rbx, rbx
0x18001760c  jz      loc_18001793E
0x180017612  test    r14, r14
0x180017615  jz      loc_18001793E
0x18001761b  test    rsi, rsi
0x18001761e  jz      loc_18001793E
0x180017624  test    rdi, rdi
0x180017627  jz      loc_18001793E
0x18001762d  test    r12, r12
0x180017630  jz      loc_18001793E
0x180017636  mov     rax, [rdi]
0x180017639  lea     rdx, [rsp+310h+var_2C0]
0x18001763e  mov     rcx, rdi
0x180017641  mov     rax, [rax+50h]
0x180017645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001764a  mov     ebx, eax
0x18001764c  test    eax, eax
0x18001764e  js      loc_180017943
0x180017654  cmp     [r14], r15w
0x180017658  jnz     short loc_1800176A7
0x18001765a  mov     r8, [rsp+310h+var_2C0]; struct ICommandParameterList *
0x18001765f  lea     rax, [rbp+210h+var_280]
0x180017663  mov     [rsp+310h+var_2E0], 1; int
0x18001766b  lea     r9, aApppoolName; "APPPOOL.NAME"
0x180017672  mov     [rsp+310h+var_2E8], r15d; int
0x180017677  mov     rdx, rsi; struct IExtensionContext *
0x18001767a  mov     [rsp+310h+var_2F0], rax; struct STRU *
0x18001767f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180017684  mov     ecx, 80000000h; this
0x180017689  mov     ebx, eax
0x18001768b  add     eax, ecx
0x18001768d  test    ecx, eax
0x18001768f  jnz     short loc_18001769D
0x180017691  cmp     ebx, 80070585h
0x180017697  jnz     loc_180017943
0x18001769d  mov     r14, [rbp+210h+String2]
0x1800176a1  cmp     [r14], r15w
0x1800176a5  jz      short loc_1800176BE
0x1800176a7  mov     r8, [rsp+310h+var_2C0]; struct ICommandParameterList *
0x1800176ac  mov     rdx, rsi; struct IExtensionContext *
0x1800176af  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x1800176b4  mov     ebx, eax
0x1800176b6  test    eax, eax
0x1800176b8  js      loc_180017943
0x1800176be  mov     rax, [rsi]
0x1800176c1  mov     rcx, rsi
0x1800176c4  mov     rax, [rax+20h]
0x1800176c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176cd  test    al, 8
0x1800176cf  lea     rdi, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800176d6  mov     rax, [rsi]
0x1800176d9  lea     r13, Str
0x1800176e0  cmovz   r13, rdi
0x1800176e4  lea     r8, [rsp+310h+var_2A0]
0x1800176e9  mov     rdx, r13
0x1800176ec  mov     rcx, rsi
0x1800176ef  mov     rax, [rax+50h]
0x1800176f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176f8  mov     ebx, eax
0x1800176fa  test    eax, eax
0x1800176fc  js      loc_180017943
0x180017702  mov     rcx, [rsp+310h+var_2A0]
0x180017707  lea     rdx, [rsp+310h+var_298]
0x18001770c  mov     qword ptr [rsp+310h+var_2E8], r15
0x180017711  lea     r9, [rsp+310h+var_2A8]
0x180017716  mov     [rsp+310h+var_2F0], rdx
0x18001771b  mov     r8, rdi
0x18001771e  lea     rdx, aSystemApplicat_3; "system.applicationHost/applicationPools"
0x180017725  mov     rax, [rcx]
0x180017728  mov     rax, [rax+18h]
0x18001772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017731  mov     ebx, eax
0x180017733  test    eax, eax
0x180017735  jns     short loc_18001776A
0x180017737  mov     rcx, [rsp+310h+var_298]
0x18001773c  test    rcx, rcx
0x18001773f  jz      loc_180017943
0x180017745  mov     rax, [rsi]
0x180017748  lea     r8, Str
0x18001774f  mov     r9, rcx
0x180017752  mov     dword ptr [rsp+310h+var_2F0], r15d
0x180017757  mov     edx, ebx
0x180017759  mov     rcx, rsi
0x18001775c  mov     rax, [rax+70h]
0x180017760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017765  jmp     loc_180017943
0x18001776a  mov     rcx, [rsp+310h+var_2A8]
0x18001776f  lea     rdx, [rsp+310h+var_2B0]
0x180017774  mov     rax, [rcx]
0x180017777  mov     rax, [rax+28h]
0x18001777b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017780  mov     ebx, eax
0x180017782  test    eax, eax
0x180017784  js      loc_180017943
0x18001778a  mov     rcx, [rsp+310h+var_2B0]
0x18001778f  lea     rdx, [rsp+310h+var_2B8]
0x180017794  mov     rax, [rcx]
0x180017797  mov     rax, [rax+18h]
0x18001779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177a0  mov     ebx, eax
0x1800177a2  test    eax, eax
0x1800177a4  js      loc_180017943
0x1800177aa  cmp     r15d, [rsp+310h+var_2B8]
0x1800177af  jnb     loc_180017943
0x1800177b5  mov     rcx, [rsp+310h+var_2B0]
0x1800177ba  lea     r8, [rsp+310h+var_2C8]
0x1800177bf  mov     edx, r15d
0x1800177c2  mov     rax, [rcx]
0x1800177c5  mov     rax, [rax+20h]
0x1800177c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177ce  mov     ebx, eax
0x1800177d0  test    eax, eax
0x1800177d2  js      loc_180017943
0x1800177d8  mov     ecx, 0D8h; Size
0x1800177dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800177e2  xor     ebx, ebx
0x1800177e4  test    rax, rax
0x1800177e7  jz      loc_180017937
0x1800177ed  mov     r8, [rsp+310h+var_2A8]; struct INativeConfigurationElement *
0x1800177f2  mov     rcx, rax; this
0x1800177f5  mov     rdx, [rsp+310h+var_2C8]; struct INativeConfigurationElement *
0x1800177fa  call    ??0APPPOOL_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; APPPOOL_OBJECT::APPPOOL_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x1800177ff  mov     rdi, rax
0x180017802  test    rax, rax
0x180017805  jz      loc_180017937
0x18001780b  mov     rcx, [rsp+310h+var_2C8]
0x180017810  lea     r8, [rbp+210h+String1]
0x180017814  xor     r9d, r9d
0x180017817  mov     [rsp+310h+var_2F0], rbx
0x18001781c  lea     rdx, aName_0; "name"
0x180017823  mov     rax, [rcx]
0x180017826  mov     rax, [rax+40h]
0x18001782a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001782f  mov     ebx, eax
0x180017831  test    eax, eax
0x180017833  js      loc_180017926
0x180017839  mov     rax, [rsi]
0x18001783c  mov     ebx, 4
0x180017841  mov     rcx, rsi
0x180017844  mov     [rsp+310h+var_2B4], ebx
0x180017848  mov     rax, [rax+20h]
0x18001784c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017851  test    bl, al
0x180017853  jnz     short loc_18001786B
0x180017855  mov     rdx, [rbp+210h+String1]; unsigned __int16 *
0x180017859  lea     r8, [rsp+310h+var_2B4]; enum __MIDL___MIDL_itf_rscaps_0000_0003_0001 *
0x18001785e  mov     rcx, [rbp+210h+var_288]; this
0x180017862  call    ?GetApppoolState@APPPOOL_OBJECT_EXTENSION@@AEAAJPEBGPEAW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z; APPPOOL_OBJECT_EXTENSION::GetApppoolState(ushort const *,__MIDL___MIDL_itf_rscaps_0000_0003_0001 *)
0x180017867  mov     ebx, [rsp+310h+var_2B4]
0x18001786b  mov     r8d, ebx
0x18001786e  mov     rdx, r13
0x180017871  mov     rcx, rdi
0x180017874  call    ?Create@APPPOOL_OBJECT@@QEAAJPEBGW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z; APPPOOL_OBJECT::Create(ushort const *,__MIDL___MIDL_itf_rscaps_0000_0003_0001)
0x180017879  mov     ebx, eax
0x18001787b  xor     eax, eax
0x18001787d  test    ebx, ebx
0x18001787f  js      loc_180017926
0x180017885  cmp     [r14], ax
0x180017889  jz      short loc_1800178A7
0x18001788b  mov     rcx, [rbp+210h+String1]; String1
0x18001788f  mov     rdx, r14; String2
0x180017892  call    cs:__imp__wcsicmp
0x180017898  xor     edx, edx
0x18001789a  mov     ecx, edx
0x18001789c  test    eax, eax
0x18001789e  setz    cl
0x1800178a1  mov     [rsp+310h+var_2D0], ecx
0x1800178a5  jmp     short loc_1800178D0
0x1800178a7  mov     rax, [rsi]
0x1800178aa  lea     r9, [rsp+310h+var_2D0]
0x1800178af  mov     r8, [rsp+310h+var_2C0]
0x1800178b4  mov     rdx, rdi
0x1800178b7  mov     rcx, rsi
0x1800178ba  mov     rax, [rax+98h]
0x1800178c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178c6  mov     ebx, eax
0x1800178c8  test    eax, eax
0x1800178ca  js      short loc_180017926
0x1800178cc  mov     ecx, [rsp+310h+var_2D0]
0x1800178d0  test    ecx, ecx
0x1800178d2  jz      short loc_1800178F5
0x1800178d4  mov     rax, [r12]
0x1800178d8  mov     rdx, rdi
0x1800178db  mov     rcx, r12
0x1800178de  mov     rax, [rax+18h]
0x1800178e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178e7  mov     ebx, eax
0x1800178e9  xor     eax, eax
0x1800178eb  test    ebx, ebx
0x1800178ed  js      short loc_180017926
0x1800178ef  cmp     [r14], ax
0x1800178f3  jnz     short loc_180017926
0x1800178f5  mov     rax, [rdi]
0x1800178f8  mov     rcx, rdi
0x1800178fb  mov     rax, [rax+10h]
0x1800178ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017904  mov     rcx, [rsp+310h+var_2C8]
0x180017909  mov     rax, [rcx]
0x18001790c  mov     rax, [rax+10h]
0x180017910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017915  inc     r15d
0x180017918  mov     [rsp+310h+var_2C8], 0
0x180017921  jmp     loc_1800177AA
0x180017926  mov     rax, [rdi]
0x180017929  mov     rcx, rdi
0x18001792c  mov     rax, [rax+10h]
0x180017930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017935  jmp     short loc_180017943
0x180017937  mov     ebx, 80070008h
0x18001793c  jmp     short loc_180017943
0x18001793e  mov     ebx, 80070057h
0x180017943  mov     rcx, [rsp+310h+var_2C8]
0x180017948  xor     edi, edi
0x18001794a  test    rcx, rcx
0x18001794d  jz      short loc_180017960
0x18001794f  mov     rax, [rcx]
0x180017952  mov     rax, [rax+10h]
0x180017956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001795b  mov     [rsp+310h+var_2C8], rdi
0x180017960  mov     rcx, [rsp+310h+var_2B0]
0x180017965  test    rcx, rcx
0x180017968  jz      short loc_18001797B
0x18001796a  mov     rax, [rcx]
0x18001796d  mov     rax, [rax+10h]
0x180017971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017976  mov     [rsp+310h+var_2B0], rdi
0x18001797b  mov     rcx, [rsp+310h+var_2A8]
0x180017980  test    rcx, rcx
0x180017983  jz      short loc_180017996
0x180017985  mov     rax, [rcx]
0x180017988  mov     rax, [rax+10h]
0x18001798c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017991  mov     [rsp+310h+var_2A8], rdi
0x180017996  mov     rcx, [rsp+310h+var_2A0]
0x18001799b  test    rcx, rcx
0x18001799e  jz      short loc_1800179B1
0x1800179a0  mov     rax, [rcx]
0x1800179a3  mov     rax, [rax+10h]
0x1800179a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ac  mov     [rsp+310h+var_2A0], rdi
0x1800179b1  mov     rcx, [rsp+310h+var_298]
0x1800179b6  test    rcx, rcx
0x1800179b9  jz      short loc_1800179CC
0x1800179bb  mov     rax, [rcx]
0x1800179be  mov     rax, [rax+10h]
0x1800179c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179c7  mov     [rsp+310h+var_298], rdi
0x1800179cc  mov     rcx, [rsp+310h+var_2C0]
0x1800179d1  test    rcx, rcx
0x1800179d4  jz      short loc_1800179E7
0x1800179d6  mov     rax, [rcx]
0x1800179d9  mov     rax, [rax+10h]
0x1800179dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179e2  mov     [rsp+310h+var_2C0], rdi
0x1800179e7  lea     rcx, [rbp+210h+var_280]; this
0x1800179eb  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800179f0  mov     eax, ebx
0x1800179f2  mov     rcx, [rbp+210h+var_40]
0x1800179f9  xor     rcx, rsp; StackCookie
0x1800179fc  call    __security_check_cookie
0x180017a01  mov     rbx, [rsp+310h+arg_8]
  ... truncated ...
```
