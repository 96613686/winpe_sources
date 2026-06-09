# GetDisplayDriverCapabilities(unsigned __int64,ulong,_ACGLockDownState *)

- ea: `0x1800026f4`
- end: `0x180002d66`
- name: `?GetDisplayDriverCapabilities@@YAJ_KKPEAW4_ACGLockDownState@@@Z`
- size: `1650`
- prototype: `__int64 __fastcall(void *, HRESULT, enum _ACGLockDownState *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003060`

## callees

- `0x1800026f4`
- `0x180003278`
- `0x18000342c`
- `0x180003484`
- `0x180006956`
- `0x180006980`
- `0x180007010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180002741`
- `dxgi!CreateDXGIFactory1` at `0x180002741`

## pseudocode

```c
__int64 __fastcall GetDisplayDriverCapabilities(void *a1, HRESULT a2, enum _ACGLockDownState *a3)
{
  unsigned int v5; // r13d
  HRESULT v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  void *v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  void *v21; // rbx
  void *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // rcx
  void *v24; // rbx
  void *v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  int v27; // ecx
  void *v28; // rcx
  void *v30; // rcx
  void *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v33)(_QWORD, GUID *, _QWORD *); // rcx
  HRESULT v34; // [rsp+40h] [rbp-C0h] BYREF
  void *ppFactory; // [rsp+48h] [rbp-B8h] BYREF
  void *v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, void **); // [rsp+58h] [rbp-A8h] BYREF
  void *v38; // [rsp+60h] [rbp-A0h] BYREF
  void *v39; // [rsp+68h] [rbp-98h] BYREF
  void *v40; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[256]; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+180h] [rbp+80h]
  int v43; // [rsp+184h] [rbp+84h]
  void *v44; // [rsp+1A8h] [rbp+A8h]
  char v45; // [rsp+1B0h] [rbp+B0h]
  _BYTE v46[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  void **v47; // [rsp+1D0h] [rbp+D0h]
  __int64 v48; // [rsp+1D8h] [rbp+D8h]
  void **v49; // [rsp+1E0h] [rbp+E0h]
  __int64 v50; // [rsp+1E8h] [rbp+E8h]
  HRESULT *v51; // [rsp+1F0h] [rbp+F0h]
  __int64 v52; // [rsp+1F8h] [rbp+F8h]

  v5 = 0;
  *(_DWORD *)a3 = 0;
  ppFactory = 0;
  v7 = CreateDXGIFactory1(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &ppFactory);
  v10 = v7;
  if ( v7 >= 0 )
  {
    memset_0(v41, 0, 0x140u);
    while ( 1 )
    {
      v37 = 0;
      v12 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppFactory + 96LL))(ppFactory, v5, &v37);
      v10 = v12;
      if ( v12 < 0 )
        break;
      v36 = 0;
      v15 = (**v37)(v37, &GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e, &v36);
      v10 = v15;
      if ( v15 < 0 )
      {
        if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
        {
          v48 = 8;
          v47 = &v38;
          LODWORD(v39) = v15;
          v49 = (void **)&v34;
          v34 = a2;
          v51 = (HRESULT *)&v39;
          v38 = a1;
          v50 = 4;
          v52 = 4;
          McGenEventWrite_EventWriteTransfer(v16, DXGIAdapter2QueryFailed, v17, 4, v46);
        }
        v31 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v32 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v37;
        if ( v37 )
        {
          v37 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v32)[2])(v32);
        }
        v11 = ppFactory;
        if ( ppFactory )
        {
          ppFactory = 0;
          goto LABEL_66;
        }
        return v10;
      }
      v18 = (*(__int64 (__fastcall **)(void *, _BYTE *))(*(_QWORD *)v36 + 144LL))(v36, v41);
      v10 = v18;
      if ( v18 < 0 )
      {
        if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
        {
          LODWORD(v39) = v18;
          v47 = &v38;
          v34 = a2;
          v49 = (void **)&v34;
          v38 = a1;
          v51 = (HRESULT *)&v39;
          v48 = 8;
          v50 = 4;
          v52 = 4;
          McGenEventWrite_EventWriteTransfer(v19, DXGIAdapterDescFailed, v20, 4, v46);
        }
        v30 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
        }
        goto LABEL_62;
      }
      v39 = v44;
      v21 = v44;
      if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
      {
        v34 = a2;
        v47 = &v40;
        v38 = v44;
        v49 = &v38;
        v40 = a1;
        v51 = &v34;
        v48 = 8;
        v50 = 8;
        v52 = 4;
        McGenEventWrite_EventWriteTransfer(v19, DXGIEnumeratedAdapter, v20, 4, v46);
      }
      if ( !a1 || v21 == a1 )
      {
        v24 = 0;
        if ( v36 )
        {
          v24 = v36;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 8LL))(v36);
          v25 = v36;
          if ( v36 )
          {
            v36 = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
        v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v37;
        if ( v37 )
        {
          v37 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v26)[2])(v26);
        }
        if ( v42 == 5140 && v43 == 140 )
        {
          if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
          {
            v34 = a2;
            v47 = &v38;
            v38 = a1;
            v49 = (void **)&v34;
            v48 = 8;
            v50 = 4;
            McGenEventWrite_EventWriteTransfer(v26, SoftwareRenderingMode, v20, 3, v46);
          }
          *(_DWORD *)a3 = 1;
        }
        else if ( v5 )
        {
          if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
            McTemplateU0zqqxq_EventWriteTransfer(
              (_DWORD)v26,
              (unsigned int)UnexpectedAdapterId,
              (unsigned int)v41,
              v42,
              v43,
              (char)a1,
              a2);
          *(_DWORD *)a3 = 5;
        }
        else
        {
          v38 = ppFactory;
          if ( ppFactory )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 8LL))(ppFactory);
          if ( (unsigned __int8)ShouldForceAdapterToACG(v24, v41, &v38) )
          {
            if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
              McTemplateU0zqqxq_EventWriteTransfer(
                v27,
                (unsigned int)AdapterForcedToACG,
                (unsigned int)v41,
                v42,
                v43,
                (char)a1,
                a2);
            *(_DWORD *)a3 = 3;
          }
          else if ( (v45 & 4) == 0 )
          {
            if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
              McTemplateU0zqqxq_EventWriteTransfer(
                v27,
                (unsigned int)AdapterDoesNotSupportACG,
                (unsigned int)v41,
                v42,
                v43,
                (char)a1,
                a2);
            *(_DWORD *)a3 = 2;
          }
        }
        if ( v24 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
        v28 = ppFactory;
        if ( ppFactory )
        {
          ppFactory = 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
        }
        return 0;
      }
      v22 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v37;
      if ( v37 )
      {
        v37 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
      }
      ++v5;
    }
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
    {
      LODWORD(v39) = v12;
      v47 = &v38;
      v34 = a2;
      v49 = (void **)&v34;
      v38 = a1;
      v51 = (HRESULT *)&v39;
      v48 = 8;
      v50 = 4;
      v52 = 4;
      McGenEventWrite_EventWriteTransfer(v13, DXGIAdapterEnumFailed, v14, 4, v46);
    }
LABEL_62:
    v33 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v37;
    if ( v37 )
    {
      v37 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v33)[2])(v33);
    }
    v11 = ppFactory;
    if ( ppFactory )
    {
      ppFactory = 0;
      goto LABEL_66;
    }
  }
  else
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 8) != 0 )
    {
      v34 = v7;
      LODWORD(v39) = a2;
      v47 = &v36;
      v36 = a1;
      v49 = &v39;
      v48 = 8;
      v51 = &v34;
      v50 = 4;
      v52 = 4;
      McGenEventWrite_EventWriteTransfer(v8, DXGIFactoryCreationFailed, v9, 4, v46);
    }
    v11 = ppFactory;
    if ( ppFactory )
    {
      ppFactory = 0;
LABEL_66:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800026f4  push    rbp
0x1800026f6  push    rbx
0x1800026f7  push    rsi
0x1800026f8  push    rdi
0x1800026f9  push    r12
0x1800026fb  push    r13
0x1800026fd  push    r14
0x1800026ff  push    r15
0x180002701  lea     rbp, [rsp-118h]
0x180002709  sub     rsp, 218h
0x180002710  mov     rax, cs:__security_cookie
0x180002717  xor     rax, rsp
0x18000271a  mov     [rbp+150h+var_50], rax
0x180002721  mov     r15d, edx
0x180002724  mov     r14, rcx
0x180002727  xor     r13d, r13d
0x18000272a  lea     rdx, [rsp+250h+ppFactory]; ppFactory
0x18000272f  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387; riid
0x180002736  mov     [r8], r13d
0x180002739  mov     [rsp+250h+ppFactory], r13
0x18000273e  mov     r12, r8
0x180002741  call    cs:__imp_CreateDXGIFactory1
0x180002747  mov     ebx, eax
0x180002749  test    eax, eax
0x18000274b  jns     loc_1800027DB
0x180002751  lea     esi, [r13+8]
0x180002755  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, sil
0x18000275c  jz      short loc_1800027C3
0x18000275e  mov     [rsp+250h+var_210], eax
0x180002762  lea     edi, [rsi-4]
0x180002765  lea     rax, [rsp+250h+var_200]
0x18000276a  mov     dword ptr [rsp+250h+var_1E8], r15d
0x18000276f  mov     [rbp+150h+var_80], rax
0x180002776  lea     rdx, DXGIFactoryCreationFailed
0x18000277d  lea     rax, [rsp+250h+var_1E8]
0x180002782  mov     [rsp+250h+var_200], r14
0x180002787  mov     [rbp+150h+var_70], rax
0x18000278e  mov     r9d, edi
0x180002791  lea     rax, [rsp+250h+var_210]
0x180002796  mov     [rbp+150h+var_78], rsi
0x18000279d  mov     [rbp+150h+var_60], rax
0x1800027a4  lea     rax, [rbp+150h+var_90]
0x1800027ab  mov     [rsp+250h+var_230], rax
0x1800027b0  mov     [rbp+150h+var_68], rdi
0x1800027b7  mov     [rbp+150h+var_58], rdi
0x1800027be  call    McGenEventWrite_EventWriteTransfer
0x1800027c3  mov     rcx, [rsp+250h+ppFactory]
0x1800027c8  test    rcx, rcx
0x1800027cb  jz      loc_180002D41
0x1800027d1  mov     [rsp+250h+ppFactory], r13
0x1800027d6  jmp     loc_180002D35
0x1800027db  xor     edx, edx; Val
0x1800027dd  lea     rcx, [rbp+150h+var_1D0]; void *
0x1800027e1  mov     r8d, 140h; Size
0x1800027e7  call    memset_0
0x1800027ec  mov     esi, 8
0x1800027f1  lea     edi, [rsi-4]
0x1800027f4  mov     rcx, [rsp+250h+ppFactory]
0x1800027f9  lea     r8, [rsp+250h+var_1F8]
0x1800027fe  mov     [rsp+250h+var_1F8], 0
0x180002807  mov     edx, r13d
0x18000280a  mov     rax, [rcx]
0x18000280d  mov     rax, [rax+60h]
0x180002811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002816  mov     ebx, eax
0x180002818  test    eax, eax
0x18000281a  js      loc_180002C98
0x180002820  mov     rcx, [rsp+250h+var_1F8]
0x180002825  lea     r8, [rsp+250h+var_200]
0x18000282a  mov     [rsp+250h+var_200], 0
0x180002833  lea     rdx, _GUID_3c8d99d1_4fbf_4181_a82c_af66bf7bd24e
0x18000283a  mov     rax, [rcx]
0x18000283d  mov     rax, [rax]
0x180002840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002845  mov     ebx, eax
0x180002847  test    eax, eax
0x180002849  js      loc_180002BD9
0x18000284f  mov     rcx, [rsp+250h+var_200]
0x180002854  lea     rdx, [rbp+150h+var_1D0]
0x180002858  mov     rax, [rcx]
0x18000285b  mov     rax, [rax+90h]
0x180002862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002867  mov     ebx, eax
0x180002869  test    eax, eax
0x18000286b  js      loc_180002B46
0x180002871  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, dil
0x180002878  mov     eax, dword ptr [rbp+150h+var_A8]
0x18000287e  mov     dword ptr [rsp+250h+var_1E8], eax
0x180002882  mov     eax, dword ptr [rbp+150h+var_A8+4]
0x180002888  mov     dword ptr [rsp+250h+var_1E8+4], eax
0x18000288c  mov     rbx, [rsp+250h+var_1E8]
0x180002891  jz      short loc_1800028F6
0x180002893  lea     rax, [rsp+250h+var_1E0]
0x180002898  mov     [rsp+250h+var_210], r15d
0x18000289d  mov     [rbp+150h+var_80], rax
0x1800028a4  lea     rdx, DXGIEnumeratedAdapter
0x1800028ab  lea     rax, [rsp+250h+var_1F0]
0x1800028b0  mov     [rsp+250h+var_1F0], rbx
0x1800028b5  mov     [rbp+150h+var_70], rax
0x1800028bc  mov     r9d, edi
0x1800028bf  lea     rax, [rsp+250h+var_210]
0x1800028c4  mov     [rsp+250h+var_1E0], r14
0x1800028c9  mov     [rbp+150h+var_60], rax
0x1800028d0  lea     rax, [rbp+150h+var_90]
0x1800028d7  mov     [rsp+250h+var_230], rax
0x1800028dc  mov     [rbp+150h+var_78], rsi
0x1800028e3  mov     [rbp+150h+var_68], rsi
0x1800028ea  mov     [rbp+150h+var_58], rdi
0x1800028f1  call    McGenEventWrite_EventWriteTransfer
0x1800028f6  test    r14, r14
0x1800028f9  jz      short loc_180002946
0x1800028fb  cmp     rbx, r14
0x1800028fe  jz      short loc_180002946
0x180002900  mov     rcx, [rsp+250h+var_200]
0x180002905  test    rcx, rcx
0x180002908  jz      short loc_18000291F
0x18000290a  mov     [rsp+250h+var_200], 0
0x180002913  mov     rax, [rcx]
0x180002916  mov     rax, [rax+10h]
0x18000291a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291f  mov     rcx, [rsp+250h+var_1F8]
0x180002924  test    rcx, rcx
0x180002927  jz      short loc_18000293E
0x180002929  mov     [rsp+250h+var_1F8], 0
0x180002932  mov     rax, [rcx]
0x180002935  mov     rax, [rax+10h]
0x180002939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293e  inc     r13d
0x180002941  jmp     loc_1800027F4
0x180002946  mov     rcx, [rsp+250h+var_200]
0x18000294b  xor     ebx, ebx
0x18000294d  test    rcx, rcx
0x180002950  jz      short loc_180002980
0x180002952  mov     rax, [rcx]
0x180002955  mov     rbx, rcx
0x180002958  mov     rax, [rax+8]
0x18000295c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002961  mov     rcx, [rsp+250h+var_200]
0x180002966  test    rcx, rcx
0x180002969  jz      short loc_180002980
0x18000296b  mov     [rsp+250h+var_200], 0
0x180002974  mov     rax, [rcx]
0x180002977  mov     rax, [rax+10h]
0x18000297b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002980  mov     rcx, [rsp+250h+var_1F8]
0x180002985  test    rcx, rcx
0x180002988  jz      short loc_18000299F
0x18000298a  mov     [rsp+250h+var_1F8], 0
0x180002993  mov     rax, [rcx]
0x180002996  mov     rax, [rax+10h]
0x18000299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000299f  mov     r9d, [rbp+150h+var_D0]
0x1800029a6  mov     eax, [rbp+150h+var_CC]
0x1800029ac  cmp     r9d, 1414h
0x1800029b3  jnz     short loc_180002A20
0x1800029b5  cmp     eax, 8Ch
0x1800029ba  jnz     short loc_180002A20
0x1800029bc  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, dil
0x1800029c3  jz      short loc_180002A13
0x1800029c5  lea     rax, [rsp+250h+var_1F0]
0x1800029ca  mov     [rsp+250h+var_210], r15d
0x1800029cf  mov     [rbp+150h+var_80], rax
0x1800029d6  lea     rdx, SoftwareRenderingMode
0x1800029dd  lea     rax, [rsp+250h+var_210]
0x1800029e2  mov     [rsp+250h+var_1F0], r14
0x1800029e7  mov     [rbp+150h+var_70], rax
0x1800029ee  mov     r9d, 3
0x1800029f4  lea     rax, [rbp+150h+var_90]
0x1800029fb  mov     [rbp+150h+var_78], rsi
0x180002a02  mov     [rsp+250h+var_230], rax
0x180002a07  mov     [rbp+150h+var_68], rdi
0x180002a0e  call    McGenEventWrite_EventWriteTransfer
0x180002a13  mov     dword ptr [r12], 1
0x180002a1b  jmp     loc_180002B0C
0x180002a20  test    r13d, r13d
0x180002a23  jz      short loc_180002A59
0x180002a25  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, dil
0x180002a2c  jz      short loc_180002A4C
0x180002a2e  mov     [rsp+250h+var_220], r15d
0x180002a33  lea     r8, [rbp+150h+var_1D0]
0x180002a37  mov     [rsp+250h+var_228], r14
0x180002a3c  lea     rdx, UnexpectedAdapterId
0x180002a43  mov     dword ptr [rsp+250h+var_230], eax
0x180002a47  call    McTemplateU0zqqxq_EventWriteTransfer
0x180002a4c  mov     dword ptr [r12], 5
0x180002a54  jmp     loc_180002B0C
0x180002a59  mov     rcx, [rsp+250h+ppFactory]
0x180002a5e  mov     [rsp+250h+var_1F0], rcx
0x180002a63  test    rcx, rcx
0x180002a66  jz      short loc_180002A74
0x180002a68  mov     rax, [rcx]
0x180002a6b  mov     rax, [rax+8]
0x180002a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a74  lea     r8, [rsp+250h+var_1F0]
0x180002a79  mov     rcx, rbx
0x180002a7c  lea     rdx, [rbp+150h+var_1D0]
0x180002a80  call    ?ShouldForceAdapterToACG@@YA_NPEAUIDXGIAdapter4@@PEAUDXGI_ADAPTER_DESC3@@V?$ComPtr@UIDXGIFactory1@@@WRL@Microsoft@@@Z; ShouldForceAdapterToACG(IDXGIAdapter4 *,DXGI_ADAPTER_DESC3 *,Microsoft::WRL::ComPtr<IDXGIFactory1>)
0x180002a85  test    al, al
0x180002a87  jz      short loc_180002AC7
0x180002a89  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, dil
0x180002a90  jz      short loc_180002ABD
0x180002a92  mov     eax, [rbp+150h+var_CC]
0x180002a98  lea     r8, [rbp+150h+var_1D0]
0x180002a9c  mov     r9d, [rbp+150h+var_D0]
0x180002aa3  lea     rdx, AdapterForcedToACG
0x180002aaa  mov     [rsp+250h+var_220], r15d
0x180002aaf  mov     [rsp+250h+var_228], r14
0x180002ab4  mov     dword ptr [rsp+250h+var_230], eax
0x180002ab8  call    McTemplateU0zqqxq_EventWriteTransfer
0x180002abd  mov     dword ptr [r12], 3
0x180002ac5  jmp     short loc_180002B0C
0x180002ac7  test    [rbp+150h+var_A0], dil
0x180002ace  jnz     short loc_180002B0C
0x180002ad0  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, dil
0x180002ad7  jz      short loc_180002B04
0x180002ad9  mov     eax, [rbp+150h+var_CC]
0x180002adf  lea     r8, [rbp+150h+var_1D0]
0x180002ae3  mov     r9d, [rbp+150h+var_D0]
0x180002aea  lea     rdx, AdapterDoesNotSupportACG
0x180002af1  mov     [rsp+250h+var_220], r15d
0x180002af6  mov     [rsp+250h+var_228], r14
0x180002afb  mov     dword ptr [rsp+250h+var_230], eax
0x180002aff  call    McTemplateU0zqqxq_EventWriteTransfer
0x180002b04  mov     dword ptr [r12], 2
0x180002b0c  test    rbx, rbx
0x180002b0f  jz      short loc_180002B20
0x180002b11  mov     rax, [rbx]
0x180002b14  mov     rcx, rbx
0x180002b17  mov     rax, [rax+10h]
0x180002b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b20  mov     rcx, [rsp+250h+ppFactory]
0x180002b25  test    rcx, rcx
0x180002b28  jz      short loc_180002B3F
0x180002b2a  mov     [rsp+250h+ppFactory], 0
0x180002b33  mov     rax, [rcx]
0x180002b36  mov     rax, [rax+10h]
0x180002b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3f  xor     eax, eax
0x180002b41  jmp     loc_180002D43
0x180002b46  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, sil
0x180002b4d  jz      short loc_180002BB1
0x180002b4f  lea     rax, [rsp+250h+var_1F0]
0x180002b54  mov     dword ptr [rsp+250h+var_1E8], ebx
0x180002b58  mov     [rbp+150h+var_80], rax
0x180002b5f  lea     rdx, DXGIAdapterDescFailed
0x180002b66  lea     rax, [rsp+250h+var_210]
0x180002b6b  mov     [rsp+250h+var_210], r15d
0x180002b70  mov     [rbp+150h+var_70], rax
0x180002b77  mov     r9d, edi
0x180002b7a  lea     rax, [rsp+250h+var_1E8]
0x180002b7f  mov     [rsp+250h+var_1F0], r14
0x180002b84  mov     [rbp+150h+var_60], rax
0x180002b8b  lea     rax, [rbp+150h+var_90]
0x180002b92  mov     [rsp+250h+var_230], rax
0x180002b97  mov     [rbp+150h+var_78], rsi
0x180002b9e  mov     [rbp+150h+var_68], rdi
0x180002ba5  mov     [rbp+150h+var_58], rdi
0x180002bac  call    McGenEventWrite_EventWriteTransfer
0x180002bb1  mov     rcx, [rsp+250h+var_200]
0x180002bb6  test    rcx, rcx
0x180002bb9  jz      loc_180002D03
0x180002bbf  mov     [rsp+250h+var_200], 0
0x180002bc8  mov     rax, [rcx]
0x180002bcb  mov     rax, [rax+10h]
0x180002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd4  jmp     loc_180002D03
0x180002bd9  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, sil
0x180002be0  jz      short loc_180002C48
0x180002be2  lea     rax, [rsp+250h+var_1F0]
0x180002be7  mov     [rbp+150h+var_78], rsi
0x180002bee  mov     [rbp+150h+var_80], rax
0x180002bf5  lea     rdx, DXGIAdapter2QueryFailed
0x180002bfc  lea     rax, [rsp+250h+var_210]
0x180002c01  mov     dword ptr [rsp+250h+var_1E8], ebx
0x180002c05  mov     [rbp+150h+var_70], rax
0x180002c0c  xor     esi, esi
0x180002c0e  lea     rax, [rsp+250h+var_1E8]
0x180002c13  mov     [rsp+250h+var_210], r15d
0x180002c18  mov     [rbp+150h+var_60], rax
0x180002c1f  mov     r9d, edi
0x180002c22  lea     rax, [rbp+150h+var_90]
0x180002c29  mov     [rsp+250h+var_1F0], r14
0x180002c2e  mov     [rsp+250h+var_230], rax
0x180002c33  mov     [rbp+150h+var_68], rdi
0x180002c3a  mov     [rbp+150h+var_58], rdi
0x180002c41  call    McGenEventWrite_EventWriteTransfer
0x180002c46  jmp     short loc_180002C4A
0x180002c48  xor     esi, esi
0x180002c4a  mov     rcx, [rsp+250h+var_200]
0x180002c4f  test    rcx, rcx
0x180002c52  jz      short loc_180002C65
0x180002c54  mov     [rsp+250h+var_200], rsi
0x180002c59  mov     rax, [rcx]
0x180002c5c  mov     rax, [rax+10h]
0x180002c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c65  mov     rcx, [rsp+250h+var_1F8]
0x180002c6a  test    rcx, rcx
0x180002c6d  jz      short loc_180002C80
0x180002c6f  mov     [rsp+250h+var_1F8], rsi
0x180002c74  mov     rax, [rcx]
  ... truncated ...
```
