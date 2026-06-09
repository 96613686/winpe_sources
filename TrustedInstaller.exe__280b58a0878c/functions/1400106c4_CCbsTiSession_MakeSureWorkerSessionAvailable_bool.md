# CCbsTiSession::MakeSureWorkerSessionAvailable(bool)

- ea: `0x1400106c4`
- end: `0x1400108c6`
- name: `?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z`
- size: `514`
- prototype: `__int64 __fastcall(CCbsTiSession *this, char)`
- caller_count: `19`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000eb34`
- `0x14000ec74`
- `0x14000eee4`
- `0x14000ef94`
- `0x14000f020`
- `0x14000f7b4`
- `0x14000f8a4`
- `0x14000fbc4`
- `0x14000fd94`
- `0x14000fe34`
- `0x14000ffb4`
- `0x1400100f4`
- `0x140010954`
- `0x140010a54`
- `0x140010c84`
- `0x140011810`
- `0x140011e34`
- `0x140012234`
- `0x140012b70`

## callees

- `0x140002070`
- `0x140006778`
- `0x14000e180`
- `0x14000e2ac`
- `0x1400106c4`
- `0x14001503c`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14001070b`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x14001070b`

## string_xrefs

- `0x140010717`: `Failed to get worker session from the stream after stack update.`
- `0x140010778`: `Failed to create worker session.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::MakeSureWorkerSessionAvailable(CCbsTiSession *this, char a2)
{
  unsigned int v4; // ebx
  __int64 **v5; // rsi
  IStream *v6; // rcx
  HRESULT InterfaceAndReleaseStream; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned __int64 i; // rbp
  __int64 v11; // r11
  CCbsTiSessionUIHandler *v12; // rax
  CCbsTiSessionUIHandler *v13; // rax
  _BYTE v15[72]; // [rsp+40h] [rbp-48h] BYREF

  v4 = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v15, (CCbsTiSession *)((char *)this + 48), 1);
  v5 = (__int64 **)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    v6 = (IStream *)*((_QWORD *)this + 22);
    if ( v6 )
    {
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                    v6,
                                    &GUID_f112757a_565b_4260_bd05_9fa34417349a,
                                    (LPVOID *)this + 5);
      v4 = InterfaceAndReleaseStream;
      if ( InterfaceAndReleaseStream < 0 )
      {
        v8 = "Failed to get worker session from the stream after stack update.";
LABEL_5:
        v9 = (unsigned int)InterfaceAndReleaseStream;
LABEL_6:
        CBSWdsLogLight(0x4000000, v9, 1, v8);
        goto LABEL_33;
      }
      *((_QWORD *)this + 22) = 0;
    }
    else
    {
      InterfaceAndReleaseStream = CCbsPublicSessionClassFactory::CreateWorkerSession(
                                    *((CCbsPublicSessionClassFactory **)this + 4),
                                    (struct ICbsSession10 **)this + 5);
      v4 = InterfaceAndReleaseStream;
      if ( InterfaceAndReleaseStream < 0 )
      {
        v8 = "Failed to create worker session.";
        goto LABEL_5;
      }
    }
  }
  if ( a2 && !*((_DWORD *)this + 29) )
  {
    if ( !*((_DWORD *)this + 30) )
    {
      v4 = -2146498559;
      v8 = "Client has not called session Initialized yet.";
LABEL_12:
      v9 = v4;
      goto LABEL_6;
    }
    if ( *((_DWORD *)this + 32) )
    {
      InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(__int64 *))(**v5 + 184))(*v5);
      v4 = InterfaceAndReleaseStream;
      if ( InterfaceAndReleaseStream < 0 )
      {
        v8 = "Failed to set enhanced options.";
        goto LABEL_5;
      }
    }
    for ( i = 0; ; ++i )
    {
      v11 = **v5;
      if ( i >= *((_QWORD *)this + 26) )
        break;
      InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v11 + 120))(
                                    *v5,
                                    *(unsigned int *)(*((_QWORD *)this + 28) + 16 * i),
                                    *(_QWORD *)(*((_QWORD *)this + 28) + 16 * i + 8));
      v4 = InterfaceAndReleaseStream;
      if ( InterfaceAndReleaseStream < 0 )
      {
        v8 = "Failed to call add source";
        goto LABEL_5;
      }
    }
    InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v11 + 152))(
                                  *v5,
                                  *((unsigned int *)this + 31),
                                  *((_QWORD *)this + 17),
                                  *((_QWORD *)this + 18),
                                  *((_QWORD *)this + 19),
                                  *((_QWORD *)this + 20));
    v4 = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream < 0 )
    {
      v8 = "Failed to initialize CBS session.";
      goto LABEL_5;
    }
    v12 = (CCbsTiSessionUIHandler *)*((_QWORD *)this + 11);
    if ( !v12 )
    {
      v13 = (CCbsTiSessionUIHandler *)operator new(0x58u);
      if ( v13 )
      {
        v12 = CCbsTiSessionUIHandler::CCbsTiSessionUIHandler(v13);
        *((_QWORD *)this + 11) = v12;
        if ( v12 )
          goto LABEL_28;
      }
      else
      {
        *((_QWORD *)this + 11) = 0;
      }
      v4 = -2147024882;
      v8 = "Failed to allocate new Ti UIHandler";
      goto LABEL_12;
    }
LABEL_28:
    *((_QWORD *)v12 + 5) = this;
    InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(__int64 *, char *))(**v5 + 88))(*v5, (char *)this + 104);
    v4 = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      *((_DWORD *)this + 29) = 1;
      goto LABEL_33;
    }
    v8 = "Failed to get session ID.";
    goto LABEL_5;
  }
LABEL_33:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v15);
  return v4;
}

```

## disassembly

```asm
0x1400106c4  push    rbx
0x1400106c6  push    rbp
0x1400106c7  push    rsi
0x1400106c8  push    rdi
0x1400106c9  push    r15
0x1400106cb  sub     rsp, 60h
0x1400106cf  mov     bpl, dl
0x1400106d2  mov     rdi, rcx
0x1400106d5  lea     rdx, [rcx+30h]; struct AutoCritSec *
0x1400106d9  xor     ebx, ebx
0x1400106db  lea     rcx, [rsp+88h+var_48]; this
0x1400106e0  lea     r15d, [rbx+1]
0x1400106e4  mov     r8b, r15b; bool
0x1400106e7  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x1400106ec  lea     rsi, [rdi+28h]
0x1400106f0  cmp     [rsi], rbx
0x1400106f3  jnz     short loc_14001073D
0x1400106f5  mov     rcx, [rdi+0B0h]; pStm
0x1400106fc  test    rcx, rcx
0x1400106ff  jz      short loc_140010766
0x140010701  mov     r8, rsi; ppv
0x140010704  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a; iid
0x14001070b  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x140010711  mov     ebx, eax
0x140010713  test    eax, eax
0x140010715  jns     short loc_140010732
0x140010717  lea     r9, aFailedToGetWor; "Failed to get worker session from the s"...
0x14001071e  mov     edx, eax
0x140010720  mov     r8d, r15d
0x140010723  mov     ecx, 4000000h
0x140010728  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14001072d  jmp     loc_1400108AF
0x140010732  mov     qword ptr [rdi+0B0h], 0
0x14001073d  test    bpl, bpl
0x140010740  jz      loc_1400108AF
0x140010746  cmp     dword ptr [rdi+74h], 0
0x14001074a  jnz     loc_1400108AF
0x140010750  cmp     dword ptr [rdi+78h], 0
0x140010754  jnz     short loc_140010781
0x140010756  mov     ebx, 800F0801h
0x14001075b  lea     r9, aClientHasNotCa; "Client has not called session Initializ"...
0x140010762  mov     edx, ebx
0x140010764  jmp     short loc_140010720
0x140010766  mov     rcx, [rdi+20h]; this
0x14001076a  mov     rdx, rsi; struct ICbsSession10 **
0x14001076d  call    ?CreateWorkerSession@CCbsPublicSessionClassFactory@@QEAAJPEAPEAUICbsSession10@@@Z; CCbsPublicSessionClassFactory::CreateWorkerSession(ICbsSession10 * *)
0x140010772  mov     ebx, eax
0x140010774  test    eax, eax
0x140010776  jns     short loc_14001073D
0x140010778  lea     r9, aFailedToCreate_18; "Failed to create worker session."
0x14001077f  jmp     short loc_14001071E
0x140010781  mov     edx, [rdi+80h]
0x140010787  test    edx, edx
0x140010789  jz      short loc_1400107AF
0x14001078b  mov     rcx, [rsi]
0x14001078e  mov     rax, [rcx]
0x140010791  mov     rax, [rax+0B8h]
0x140010798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001079d  mov     ebx, eax
0x14001079f  test    eax, eax
0x1400107a1  jns     short loc_1400107AF
0x1400107a3  lea     r9, aFailedToSetEnh; "Failed to set enhanced options."
0x1400107aa  jmp     loc_14001071E
0x1400107af  xor     ebp, ebp
0x1400107b1  mov     r10, [rsi]
0x1400107b4  mov     r11, [r10]
0x1400107b7  cmp     rbp, [rdi+0D0h]
0x1400107be  jnb     short loc_1400107F8
0x1400107c0  mov     rdx, [rdi+0E0h]
0x1400107c7  mov     rax, rbp
0x1400107ca  add     rax, rax
0x1400107cd  mov     rcx, r10
0x1400107d0  mov     r8, [rdx+rax*8+8]
0x1400107d5  mov     edx, [rdx+rax*8]
0x1400107d8  mov     rax, [r11+78h]
0x1400107dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400107e1  mov     ebx, eax
0x1400107e3  test    eax, eax
0x1400107e5  js      short loc_1400107EC
0x1400107e7  add     rbp, r15
0x1400107ea  jmp     short loc_1400107B1
0x1400107ec  lea     r9, aFailedToCallAd; "Failed to call add source"
0x1400107f3  jmp     loc_14001071E
0x1400107f8  mov     rcx, [rdi+0A0h]
0x1400107ff  mov     r9, [rdi+90h]
0x140010806  mov     r8, [rdi+88h]
0x14001080d  mov     edx, [rdi+7Ch]
0x140010810  mov     rax, [r11+98h]
0x140010817  mov     [rsp+88h+var_60], rcx
0x14001081c  mov     rcx, [rdi+98h]
0x140010823  mov     [rsp+88h+var_68], rcx
0x140010828  mov     rcx, r10
0x14001082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010830  mov     ebx, eax
0x140010832  test    eax, eax
0x140010834  jns     short loc_140010842
0x140010836  lea     r9, aFailedToInitia_3; "Failed to initialize CBS session."
0x14001083d  jmp     loc_14001071E
0x140010842  mov     rax, [rdi+58h]
0x140010846  test    rax, rax
0x140010849  jnz     short loc_140010869
0x14001084b  lea     ecx, [rax+58h]; Size
0x14001084e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010853  test    rax, rax
0x140010856  jz      short loc_140010892
0x140010858  mov     rcx, rax; this
0x14001085b  call    ??0CCbsTiSessionUIHandler@@QEAA@XZ; CCbsTiSessionUIHandler::CCbsTiSessionUIHandler(void)
0x140010860  mov     [rdi+58h], rax
0x140010864  test    rax, rax
0x140010867  jz      short loc_14001089A
0x140010869  mov     [rax+28h], rdi
0x14001086d  lea     rdx, [rdi+68h]
0x140010871  mov     rcx, [rsi]
0x140010874  mov     rax, [rcx]
0x140010877  mov     rax, [rax+58h]
0x14001087b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010880  mov     ebx, eax
0x140010882  test    eax, eax
0x140010884  jns     short loc_1400108AB
0x140010886  lea     r9, aFailedToGetSes; "Failed to get session ID."
0x14001088d  jmp     loc_14001071E
0x140010892  mov     qword ptr [rdi+58h], 0
0x14001089a  mov     ebx, 8007000Eh
0x14001089f  lea     r9, aFailedToAlloca; "Failed to allocate new Ti UIHandler"
0x1400108a6  jmp     loc_140010762
0x1400108ab  mov     [rdi+74h], r15d
0x1400108af  lea     rcx, [rsp+88h+var_48]; this
0x1400108b4  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x1400108b9  mov     eax, ebx
0x1400108bb  add     rsp, 60h
0x1400108bf  pop     r15
0x1400108c1  pop     rdi
0x1400108c2  pop     rsi
0x1400108c3  pop     rbp
0x1400108c4  pop     rbx
0x1400108c5  retn
```
