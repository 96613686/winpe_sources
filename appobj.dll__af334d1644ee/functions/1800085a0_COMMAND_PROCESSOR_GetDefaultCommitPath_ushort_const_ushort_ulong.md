# COMMAND_PROCESSOR::GetDefaultCommitPath(ushort const *,ushort *,ulong)

- ea: `0x1800085a0`
- end: `0x18000893e`
- name: `?GetDefaultCommitPath@COMMAND_PROCESSOR@@UEAAJPEBGPEAGK@Z`
- size: `926`
- prototype: `int(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fb0`
- `0x180004a70`
- `0x1800085a0`
- `0x18000d5e0`
- `0x18002b670`
- `0x18002b860`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800086b7`
- `msvcrt!_wcsnicmp` at `0x1800086b7`
- `msvcrt!wcsrchr` at `0x1800088b6`
- `msvcrt!wcsrchr` at `0x1800088b6`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::GetDefaultCommitPath(
        unsigned __int64 this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  unsigned int v7; // r14d
  int v8; // r12d
  int v9; // ebx
  APP_OBJECT_UTILS *v10; // rcx
  APP_OBJECT_UTILS *v11; // rcx
  int v12; // ecx
  int v13; // ecx
  unsigned __int16 *v14; // r15
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rdx
  APP_OBJECT_UTILS *v20; // rcx
  int v21; // eax
  wchar_t *v23; // rax
  unsigned __int16 **v24; // [rsp+20h] [rbp-E0h]
  struct SITE_OBJECT **v25; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-B8h]
  __int128 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[32]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+88h] [rbp-78h]
  __int16 v34; // [rsp+8Ch] [rbp-74h]
  int v35; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+A0h] [rbp-60h] BYREF
  char v37[510]; // [rsp+A2h] [rbp-5Eh] BYREF

  LODWORD(v29) = a4;
  v7 = 0;
  v26 = 0;
  memset_0(v37, 0, sizeof(v37));
  v33 = 512;
  Str = (wchar_t *)&v36;
  v34 = 256;
  v8 = 1;
  v35 = 0;
  v36 = 0;
  v28 = 0;
  v27 = 0;
  v30 = 0;
  if ( !a3 )
    goto LABEL_2;
  v10 = (APP_OBJECT_UTILS *)*(unsigned int *)(this + 184);
  if ( !(_DWORD)v10 )
  {
    if ( a2 )
    {
      v21 = APP_OBJECT_UTILS::ResolveConfigPath(
              v10,
              (struct IExtensionContext *)(this & ((unsigned __int128)-(__int128)(this - 8) >> 64)),
              a2,
              (struct STRU *)v31,
              0,
              0);
LABEL_32:
      v9 = v21;
      if ( v21 >= 0 )
      {
        v26 = Str;
        goto LABEL_34;
      }
LABEL_36:
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        v28 = 0;
      }
      goto LABEL_38;
    }
    goto LABEL_2;
  }
  v11 = (APP_OBJECT_UTILS *)(unsigned int)((_DWORD)v10 - 1);
  if ( !(_DWORD)v11 )
  {
    if ( a2 )
    {
      v9 = APP_OBJECT_UTILS::ResolveConfigPath(
             v11,
             (struct IExtensionContext *)(this & ((unsigned __int128)-(__int128)(this - 8) >> 64)),
             a2,
             (struct STRU *)v31,
             0,
             0);
      if ( v9 < 0 )
        goto LABEL_36;
      v26 = Str;
      v23 = wcsrchr(Str, 0x2Fu);
      if ( v23 )
      {
        *v23 = 0;
        STRU::SyncWithBuffer((STRU *)v31);
        goto LABEL_34;
      }
      *(_QWORD *)&v30 = v26;
      (*(void (__fastcall **)(unsigned __int64, _QWORD, __int64, __int128 *, _DWORD))(*(_QWORD *)this + 144LL))(
        this,
        (unsigned int)v9,
        3221226544LL,
        &v30,
        0);
      goto LABEL_45;
    }
    goto LABEL_2;
  }
  v12 = (_DWORD)v11 - 1;
  if ( !v12 )
  {
    if ( a2 )
    {
      LODWORD(v24) = 4;
      v9 = (*(__int64 (__fastcall **)(unsigned __int64, const unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)this + 64LL))(
             this,
             L"APP",
             a2,
             &v27);
      if ( v9 < 0 )
        goto LABEL_36;
      if ( !v27 )
        goto LABEL_45;
      v18 = v27;
      v19 = L"APP.NAME";
      goto LABEL_30;
    }
LABEL_2:
    v9 = -2147024809;
    goto LABEL_40;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
    {
      v9 = -2147418113;
      goto LABEL_40;
    }
    v14 = *(unsigned __int16 **)(this + 48);
    v26 = v14;
    if ( !a2 )
      goto LABEL_34;
    if ( v14 )
    {
      v15 = -1;
      v16 = -1;
      do
        ++v16;
      while ( v14[v16] );
      do
        ++v15;
      while ( a2[v15] );
      if ( (unsigned int)v16 > (unsigned int)v15 )
        goto LABEL_20;
      while ( v7 < (unsigned int)v16 )
      {
        if ( _wcsnicmp(v14, a2, 1u) )
        {
          v8 = 0;
          break;
        }
        ++v7;
      }
      if ( !v8 )
      {
LABEL_20:
        *(_QWORD *)&v30 = *(_QWORD *)(this + 48);
        v9 = -2147024809;
        v17 = *(_QWORD *)this;
        *((_QWORD *)&v30 + 1) = a2;
        (*(void (__fastcall **)(unsigned __int64, __int64, __int64, __int128 *, _DWORD))(v17 + 144))(
          this,
          2147942487LL,
          3221226524LL,
          &v30,
          0);
        goto LABEL_36;
      }
LABEL_34:
      v9 = StringCchCopyW(a3, (unsigned int)v29, v26);
      if ( v9 >= 0 )
        v9 = 0;
      goto LABEL_36;
    }
LABEL_45:
    v9 = -2147024809;
    goto LABEL_36;
  }
  if ( !a2 )
    goto LABEL_2;
  LODWORD(v24) = 4;
  v9 = (*(__int64 (__fastcall **)(unsigned __int64, const unsigned __int16 *, unsigned __int16 *, __int64 *))(*(_QWORD *)this + 64LL))(
         this,
         L"SITE",
         a2,
         &v28);
  if ( v9 < 0 )
    goto LABEL_36;
  v18 = v28;
  if ( v28 )
  {
    v19 = L"SITE.NAME";
LABEL_30:
    v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v18 + 80LL))(
           v18,
           v19,
           &v26);
    if ( v9 < 0 )
      goto LABEL_36;
    v21 = APP_OBJECT_UTILS::ResolveConfigPath(
            v20,
            *(_DWORD *)(this + 188),
            v26,
            (struct STRU *)v31,
            (const unsigned __int16 **)v24,
            (struct STRU *)v25);
    goto LABEL_32;
  }
  v9 = -2147024809;
LABEL_38:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
LABEL_40:
  BUFFER::~BUFFER((BUFFER *)v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800085a0  push    rbp
0x1800085a2  push    rbx
0x1800085a3  push    rsi
0x1800085a4  push    rdi
0x1800085a5  push    r12
0x1800085a7  push    r13
0x1800085a9  push    r14
0x1800085ab  push    r15
0x1800085ad  lea     rbp, [rsp-1B8h]
0x1800085b5  sub     rsp, 2B8h
0x1800085bc  mov     rax, cs:__security_cookie
0x1800085c3  xor     rax, rsp
0x1800085c6  mov     [rbp+1F0h+var_50], rax
0x1800085cd  mov     r13, r8
0x1800085d0  mov     dword ptr [rsp+2F0h+var_2A8], r9d
0x1800085d5  mov     rsi, rdx
0x1800085d8  mov     rdi, rcx
0x1800085db  xor     r14d, r14d
0x1800085de  lea     rcx, [rbp+1F0h+var_24E]; void *
0x1800085e2  xor     edx, edx; Val
0x1800085e4  mov     [rsp+2F0h+var_2C0], r14
0x1800085e9  mov     r8d, 1FEh; Size
0x1800085ef  call    memset_0
0x1800085f4  mov     [rbp+1F0h+var_268], 200h
0x1800085fb  lea     rax, [rbp+1F0h+var_250]
0x1800085ff  mov     [rbp+1F0h+Str], rax
0x180008603  xorps   xmm0, xmm0
0x180008606  mov     [rbp+1F0h+var_264], 100h
0x18000860c  lea     r12d, [r14+1]
0x180008610  mov     [rbp+1F0h+var_260], r14d
0x180008614  mov     [rbp+1F0h+var_250], r14w
0x180008619  mov     [rsp+2F0h+var_2B0], r14
0x18000861e  mov     [rsp+2F0h+var_2B8], r14
0x180008623  movups  [rsp+2F0h+var_2A0], xmm0
0x180008628  test    r13, r13
0x18000862b  jnz     short loc_180008637
0x18000862d  mov     ebx, 80070057h
0x180008632  jmp     loc_180008842
0x180008637  mov     ecx, [rdi+0B8h]; this
0x18000863d  test    ecx, ecx
0x18000863f  jz      loc_18000890C
0x180008645  sub     ecx, r12d; this
0x180008648  jz      loc_180008871
0x18000864e  sub     ecx, r12d
0x180008651  jz      loc_18000876C
0x180008657  sub     ecx, r12d
0x18000865a  jz      loc_180008716
0x180008660  cmp     ecx, r12d
0x180008663  jz      short loc_18000866F
0x180008665  mov     ebx, 8000FFFFh
0x18000866a  jmp     loc_180008842
0x18000866f  mov     r15, [rdi+30h]
0x180008673  mov     [rsp+2F0h+var_2C0], r15
0x180008678  test    rsi, rsi
0x18000867b  jz      loc_1800087F3
0x180008681  test    r15, r15
0x180008684  jz      loc_1800088EF
0x18000868a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000868e  mov     rbx, rax
0x180008691  inc     rbx
0x180008694  cmp     [r15+rbx*2], r14w
0x180008699  jnz     short loc_180008691
0x18000869b  inc     rax
0x18000869e  cmp     [rsi+rax*2], r14w
0x1800086a3  jnz     short loc_18000869B
0x1800086a5  cmp     ebx, eax
0x1800086a7  ja      short loc_1800086DA
0x1800086a9  cmp     r14d, ebx
0x1800086ac  jnb     short loc_1800086CE
0x1800086ae  mov     r8, r12; MaxCount
0x1800086b1  mov     rdx, rsi; String2
0x1800086b4  mov     rcx, r15; String1
0x1800086b7  call    cs:__imp__wcsnicmp
0x1800086bd  test    eax, eax
0x1800086bf  jnz     short loc_1800086C6
0x1800086c1  add     r14d, r12d
0x1800086c4  jmp     short loc_1800086A9
0x1800086c6  xor     r14d, r14d
0x1800086c9  mov     r12d, r14d
0x1800086cc  jmp     short loc_1800086D1
0x1800086ce  xor     r14d, r14d
0x1800086d1  test    r12d, r12d
0x1800086d4  jnz     loc_1800087F3
0x1800086da  mov     rax, [rdi+30h]
0x1800086de  lea     r9, [rsp+2F0h+var_2A0]
0x1800086e3  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x1800086e8  mov     ebx, 80070057h
0x1800086ed  mov     rax, [rdi]
0x1800086f0  mov     r8d, 0C000041Ch
0x1800086f6  mov     edx, ebx
0x1800086f8  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x1800086fd  mov     rcx, rdi
0x180008700  mov     dword ptr [rsp+2F0h+var_2D0], r14d
0x180008705  mov     rax, [rax+90h]
0x18000870c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008711  jmp     loc_18000880C
0x180008716  test    rsi, rsi
0x180008719  jz      loc_18000862D
0x18000871f  mov     rax, [rdi]
0x180008722  lea     r9, [rsp+2F0h+var_2B0]
0x180008727  mov     r8, rsi
0x18000872a  mov     dword ptr [rsp+2F0h+var_2D0], 4
0x180008732  lea     rdx, aSite_0; "SITE"
0x180008739  mov     rcx, rdi
0x18000873c  mov     rax, [rax+40h]
0x180008740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008745  mov     ebx, eax
0x180008747  test    eax, eax
0x180008749  js      loc_18000880C
0x18000874f  mov     rcx, [rsp+2F0h+var_2B0]
0x180008754  test    rcx, rcx
0x180008757  jnz     short loc_180008763
0x180008759  mov     ebx, 80070057h
0x18000875e  jmp     loc_180008827
0x180008763  lea     rdx, aSiteName; "SITE.NAME"
0x18000876a  jmp     short loc_1800087B8
0x18000876c  test    rsi, rsi
0x18000876f  jz      loc_18000862D
0x180008775  mov     rax, [rdi]
0x180008778  lea     r9, [rsp+2F0h+var_2B8]
0x18000877d  mov     r8, rsi
0x180008780  mov     dword ptr [rsp+2F0h+var_2D0], 4; unsigned __int16 **
0x180008788  lea     rdx, aApp_0; "APP"
0x18000878f  mov     rcx, rdi
0x180008792  mov     rax, [rax+40h]
0x180008796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000879b  mov     ebx, eax
0x18000879d  test    eax, eax
0x18000879f  js      short loc_18000880C
0x1800087a1  cmp     [rsp+2F0h+var_2B8], r14
0x1800087a6  jz      loc_1800088EF
0x1800087ac  mov     rcx, [rsp+2F0h+var_2B8]
0x1800087b1  lea     rdx, aAppName_0; "APP.NAME"
0x1800087b8  mov     rax, [rcx]
0x1800087bb  lea     r8, [rsp+2F0h+var_2C0]
0x1800087c0  mov     rax, [rax+50h]
0x1800087c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c9  mov     ebx, eax
0x1800087cb  test    eax, eax
0x1800087cd  js      short loc_18000880C
0x1800087cf  mov     r8, [rsp+2F0h+var_2C0]; unsigned __int16 *
0x1800087d4  lea     r9, [rsp+2F0h+var_290]; struct STRU *
0x1800087d9  mov     edx, [rdi+0BCh]; int
0x1800087df  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJHPEBGPEAVSTRU@@PEAPEBG1@Z; APP_OBJECT_UTILS::ResolveConfigPath(int,ushort const *,STRU *,ushort const * *,STRU *)
0x1800087e4  mov     ebx, eax
0x1800087e6  test    eax, eax
0x1800087e8  js      short loc_18000880C
0x1800087ea  mov     rax, [rbp+1F0h+Str]
0x1800087ee  mov     [rsp+2F0h+var_2C0], rax
0x1800087f3  mov     edx, dword ptr [rsp+2F0h+var_2A8]; unsigned __int64
0x1800087f7  mov     rcx, r13; unsigned __int16 *
0x1800087fa  mov     r8, [rsp+2F0h+var_2C0]; unsigned __int16 *
0x1800087ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008804  test    eax, eax
0x180008806  mov     ebx, eax
0x180008808  cmovns  ebx, r14d
0x18000880c  mov     rcx, [rsp+2F0h+var_2B0]
0x180008811  test    rcx, rcx
0x180008814  jz      short loc_180008827
0x180008816  mov     rax, [rcx]
0x180008819  mov     rax, [rax+10h]
0x18000881d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008822  mov     [rsp+2F0h+var_2B0], r14
0x180008827  mov     rcx, [rsp+2F0h+var_2B8]
0x18000882c  test    rcx, rcx
0x18000882f  jz      short loc_180008842
0x180008831  mov     rax, [rcx]
0x180008834  mov     rax, [rax+10h]
0x180008838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000883d  mov     [rsp+2F0h+var_2B8], r14
0x180008842  lea     rcx, [rsp+2F0h+var_290]; this
0x180008847  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000884c  mov     eax, ebx
0x18000884e  mov     rcx, [rbp+1F0h+var_50]
0x180008855  xor     rcx, rsp; StackCookie
0x180008858  call    __security_check_cookie
0x18000885d  add     rsp, 2B8h
0x180008864  pop     r15
0x180008866  pop     r14
0x180008868  pop     r13
0x18000886a  pop     r12
0x18000886c  pop     rdi
0x18000886d  pop     rsi
0x18000886e  pop     rbx
0x18000886f  pop     rbp
0x180008870  retn
0x180008871  test    rsi, rsi
0x180008874  jz      loc_18000862D
0x18000887a  lea     rax, [rdi-8]
0x18000887e  mov     [rsp+2F0h+var_2C8], r14; struct SITE_OBJECT **
0x180008883  neg     rax
0x180008886  mov     [rsp+2F0h+var_2D0], r14; unsigned __int16 **
0x18000888b  lea     r9, [rsp+2F0h+var_290]; struct STRU *
0x180008890  mov     r8, rsi; unsigned __int16 *
0x180008893  sbb     rdx, rdx
0x180008896  and     rdx, rdi; struct IExtensionContext *
0x180008899  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)
0x18000889e  mov     ebx, eax
0x1800088a0  test    eax, eax
0x1800088a2  js      loc_18000880C
0x1800088a8  mov     rcx, [rbp+1F0h+Str]; Str
0x1800088ac  mov     edx, 2Fh ; '/'; Ch
0x1800088b1  mov     [rsp+2F0h+var_2C0], rcx
0x1800088b6  call    cs:__imp_wcsrchr
0x1800088bc  test    rax, rax
0x1800088bf  jnz     short loc_1800088F9
0x1800088c1  mov     rax, [rsp+2F0h+var_2C0]
0x1800088c6  lea     r9, [rsp+2F0h+var_2A0]
0x1800088cb  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x1800088d0  mov     r8d, 0C0000430h
0x1800088d6  mov     rax, [rdi]
0x1800088d9  mov     edx, ebx
0x1800088db  mov     rcx, rdi
0x1800088de  mov     dword ptr [rsp+2F0h+var_2D0], r14d
0x1800088e3  mov     rax, [rax+90h]
0x1800088ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088ef  mov     ebx, 80070057h
0x1800088f4  jmp     loc_18000880C
0x1800088f9  lea     rcx, [rsp+2F0h+var_290]; this
0x1800088fe  mov     [rax], r14w
0x180008902  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180008907  jmp     loc_1800087F3
0x18000890c  test    rsi, rsi
0x18000890f  jz      loc_18000862D
0x180008915  lea     rax, [rdi-8]
0x180008919  mov     [rsp+2F0h+var_2C8], r14; struct SITE_OBJECT **
0x18000891e  neg     rax
0x180008921  mov     [rsp+2F0h+var_2D0], r14; unsigned __int16 **
0x180008926  lea     r9, [rsp+2F0h+var_290]; struct STRU *
0x18000892b  mov     r8, rsi; unsigned __int16 *
0x18000892e  sbb     rdx, rdx
0x180008931  and     rdx, rdi; struct IExtensionContext *
0x180008934  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)
0x180008939  jmp     loc_1800087E4
```
