# CCbsTiSession::ResumeSession(bool,bool *)

- ea: `0x140011e34`
- end: `0x1400120a0`
- name: `?ResumeSession@CCbsTiSession@@QEAAJ_NPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, bool, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fbc4`
- `0x140010d00`
- `0x1400120b0`

## callees

- `0x140006778`
- `0x14000e2ac`
- `0x1400106c4`
- `0x140011e34`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140011fcd`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x140011fcd`

## string_xrefs

- `0x140011ee2`: `Failed to open existing session: %S`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::ResumeSession(CCbsTiSession *this, char a2, bool *a3)
{
  IUnknown *v3; // rsi
  int v7; // ebx
  const char *v8; // r9
  __int64 v9; // rcx
  int SureWorkerSessionAvailable; // eax
  size_t v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  _QWORD *v16; // r14
  __int64 v17; // rcx
  HRESULT v18; // eax
  int v19; // eax
  int v20; // eax
  _BYTE v22[32]; // [rsp+30h] [rbp-48h] BYREF

  v3 = 0;
  CritSecLocker::CritSecLocker((CritSecLocker *)v22, (CCbsTiSession *)((char *)this + 48), 1);
  if ( !a3 )
  {
    v7 = -2147467261;
    v8 = "Invalid argument: pbRestartRequired.";
LABEL_31:
    v11 = (unsigned int)v7;
    goto LABEL_32;
  }
  v9 = *((_QWORD *)this + 5);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 5) = 0;
  }
  SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(this, 0);
  v7 = SureWorkerSessionAvailable;
  if ( SureWorkerSessionAvailable < 0 )
  {
    v8 = "Failed to get worker session.";
LABEL_7:
    v11 = (unsigned int)SureWorkerSessionAvailable;
LABEL_32:
    CBSWdsLogLight(0x4000000u, v11, (size_t *)1, v8);
    goto LABEL_33;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
         *((_QWORD *)this + 5),
         128,
         *((_QWORD *)this + 13),
         0,
         0);
  if ( v7 < 0 )
  {
    CBSWdsLogLight(
      0x4000000u,
      (unsigned int)v7,
      (size_t *)1,
      "Failed to open existing session: %S",
      *((const wchar_t **)this + 13));
    goto LABEL_33;
  }
  if ( *((_DWORD *)this + 32) )
  {
    SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5));
    v7 = SureWorkerSessionAvailable;
    if ( SureWorkerSessionAvailable < 0 )
    {
      v8 = "Failed to set enhanced options.";
      goto LABEL_7;
    }
  }
  v12 = *((_QWORD *)this + 11);
  *((_DWORD *)this + 29) = 1;
  *(_DWORD *)(v12 + 48) = 0;
  v13 = *((_QWORD *)this + 11);
  if ( v13 )
    v14 = v13 + *(int *)(*(_QWORD *)(v13 + 8) + 4LL) + 8LL;
  else
    v14 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 128LL))(*((_QWORD *)this + 5), v14);
  if ( v15 < 0 )
    CBSWdsLogLight(0x4000000u, (unsigned int)v15, (size_t *)1, "Not able to set CbsHandler");
  v3 = (IUnknown *)*((_QWORD *)this + 5);
  if ( !a2 )
    goto LABEL_27;
  v16 = (_QWORD *)((char *)this + 176);
  v17 = *((_QWORD *)this + 22);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *v16 = 0;
  }
  v18 = CoMarshalInterThreadInterfaceInStream(&GUID_f568c899_af4f_4eaa_b12a_b8e5f1b219de, v3, (LPSTREAM *)this + 22);
  v7 = v18;
  if ( v18 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v16 + 40LL))(*v16, 0, 0, 0);
    v7 = v19;
    if ( v19 < 0 )
    {
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)v19,
        (size_t *)1,
        "Failed to reset position in the worker session stream.");
      goto LABEL_34;
    }
    *((_QWORD *)this + 5) = 0;
LABEL_27:
    v20 = ((__int64 (__fastcall *)(IUnknown *, _QWORD))v3->lpVtbl[3].AddRef)(v3, 0);
    v7 = 0;
    if ( v20 != -2147021886 )
      v7 = v20;
    *a3 = v20 == -2147021886;
    if ( v7 >= 0 )
    {
LABEL_33:
      if ( !a2 )
        goto LABEL_36;
      goto LABEL_34;
    }
    v8 = "Failed to resume the session after SSU";
    goto LABEL_31;
  }
  CBSWdsLogLight(0x4000000u, (unsigned int)v18, (size_t *)1, "Failed to marshal the new TiSession.");
LABEL_34:
  if ( v3 )
    ((void (__fastcall *)(IUnknown *))v3->lpVtbl->Release)(v3);
LABEL_36:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140011e34  mov     [rsp+arg_8], rbx
0x140011e39  mov     [rsp+arg_10], rbp
0x140011e3e  push    rsi
0x140011e3f  push    rdi
0x140011e40  push    r13
0x140011e42  push    r14
0x140011e44  push    r15
0x140011e46  sub     rsp, 50h
0x140011e4a  xor     esi, esi
0x140011e4c  mov     bpl, dl
0x140011e4f  mov     r15, r8
0x140011e52  lea     rdx, [rcx+30h]; struct AutoCritSec *
0x140011e56  mov     rdi, rcx
0x140011e59  lea     rcx, [rsp+78h+var_48]; this
0x140011e5e  lea     r13d, [rsi+1]
0x140011e62  mov     r8b, r13b; bool
0x140011e65  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x140011e6a  test    r15, r15
0x140011e6d  jnz     short loc_140011E80
0x140011e6f  mov     ebx, 80004003h
0x140011e74  lea     r9, aInvalidArgumen_30; "Invalid argument: pbRestartRequired."
0x140011e7b  jmp     loc_140012053
0x140011e80  mov     rcx, [rdi+28h]
0x140011e84  test    rcx, rcx
0x140011e87  jz      short loc_140011E99
0x140011e89  mov     rax, [rcx]
0x140011e8c  mov     rax, [rax+10h]
0x140011e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e95  mov     [rdi+28h], rsi
0x140011e99  xor     edx, edx; bool
0x140011e9b  mov     rcx, rdi; this
0x140011e9e  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x140011ea3  mov     ebx, eax
0x140011ea5  test    eax, eax
0x140011ea7  jns     short loc_140011EB7
0x140011ea9  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x140011eb0  mov     edx, eax
0x140011eb2  jmp     loc_140012055
0x140011eb7  mov     rcx, [rdi+28h]
0x140011ebb  xor     r9d, r9d
0x140011ebe  mov     r8, [rdi+68h]
0x140011ec2  mov     edx, 80h
0x140011ec7  mov     [rsp+78h+var_58], rsi
0x140011ecc  mov     rax, [rcx]
0x140011ecf  mov     rax, [rax+18h]
0x140011ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011ed8  mov     ebx, eax
0x140011eda  test    eax, eax
0x140011edc  jns     short loc_140011F02
0x140011ede  mov     rax, [rdi+68h]
0x140011ee2  lea     r9, aFailedToOpenEx; "Failed to open existing session: %S"
0x140011ee9  mov     r8d, r13d
0x140011eec  mov     [rsp+78h+var_58], rax
0x140011ef1  mov     edx, ebx
0x140011ef3  mov     ecx, 4000000h
0x140011ef8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140011efd  jmp     loc_140012062
0x140011f02  mov     edx, [rdi+80h]
0x140011f08  test    edx, edx
0x140011f0a  jz      short loc_140011F2E
0x140011f0c  mov     rcx, [rdi+28h]
0x140011f10  mov     rax, [rcx]
0x140011f13  mov     rax, [rax+0B8h]
0x140011f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f1f  mov     ebx, eax
0x140011f21  test    eax, eax
0x140011f23  jns     short loc_140011F2E
0x140011f25  lea     r9, aFailedToSetEnh; "Failed to set enhanced options."
0x140011f2c  jmp     short loc_140011EB0
0x140011f2e  mov     rax, [rdi+58h]
0x140011f32  mov     [rdi+74h], r13d
0x140011f36  mov     [rax+30h], esi
0x140011f39  mov     rcx, [rdi+28h]
0x140011f3d  mov     rax, [rcx]
0x140011f40  mov     r9, [rax+80h]
0x140011f47  mov     rax, [rdi+58h]
0x140011f4b  test    rax, rax
0x140011f4e  jnz     short loc_140011F54
0x140011f50  xor     edx, edx
0x140011f52  jmp     short loc_140011F63
0x140011f54  mov     rdx, [rax+8]
0x140011f58  movsxd  rdx, dword ptr [rdx+4]
0x140011f5c  add     rdx, 8
0x140011f60  add     rdx, rax
0x140011f63  mov     rax, r9
0x140011f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f6b  test    eax, eax
0x140011f6d  jns     short loc_140011F85
0x140011f6f  lea     r9, aNotAbleToSetCb; "Not able to set CbsHandler"
0x140011f76  mov     r8d, r13d
0x140011f79  mov     edx, eax
0x140011f7b  mov     ecx, 4000000h
0x140011f80  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140011f85  mov     rsi, [rdi+28h]
0x140011f89  test    bpl, bpl
0x140011f8c  jz      loc_140012025
0x140011f92  lea     r14, [rdi+0B0h]
0x140011f99  mov     [rsp+78h+arg_0], 0
0x140011fa5  mov     rcx, [r14]
0x140011fa8  test    rcx, rcx
0x140011fab  jz      short loc_140011FC0
0x140011fad  mov     rax, [rcx]
0x140011fb0  mov     rax, [rax+10h]
0x140011fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fb9  mov     qword ptr [r14], 0
0x140011fc0  mov     r8, r14; ppStm
0x140011fc3  lea     rcx, _GUID_f568c899_af4f_4eaa_b12a_b8e5f1b219de; riid
0x140011fca  mov     rdx, rsi; pUnk
0x140011fcd  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x140011fd3  mov     ebx, eax
0x140011fd5  test    eax, eax
0x140011fd7  jns     short loc_140011FF1
0x140011fd9  lea     r9, aFailedToMarsha_0; "Failed to marshal the new TiSession."
0x140011fe0  mov     r8d, r13d
0x140011fe3  mov     edx, eax
0x140011fe5  mov     ecx, 4000000h
0x140011fea  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140011fef  jmp     short loc_140012067
0x140011ff1  mov     rcx, [r14]
0x140011ff4  xor     r9d, r9d
0x140011ff7  mov     rdx, [rsp+78h+arg_0]
0x140011fff  xor     r8d, r8d
0x140012002  mov     rax, [rcx]
0x140012005  mov     rax, [rax+28h]
0x140012009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001200e  mov     ebx, eax
0x140012010  test    eax, eax
0x140012012  jns     short loc_14001201D
0x140012014  lea     r9, aFailedToResetP; "Failed to reset position in the worker "...
0x14001201b  jmp     short loc_140011FE0
0x14001201d  mov     qword ptr [rdi+28h], 0
0x140012025  mov     rax, [rsi]
0x140012028  xor     edx, edx
0x14001202a  mov     rcx, rsi
0x14001202d  mov     rax, [rax+50h]
0x140012031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012036  xor     ebx, ebx
0x140012038  mov     ecx, 80070BC2h
0x14001203d  cmp     eax, ecx
0x14001203f  cmovnz  ebx, eax
0x140012042  setz    al
0x140012045  mov     [r15], al
0x140012048  test    ebx, ebx
0x14001204a  jns     short loc_140012062
0x14001204c  lea     r9, aFailedToResume_0; "Failed to resume the session after SSU"
0x140012053  mov     edx, ebx
0x140012055  mov     r8d, r13d
0x140012058  mov     ecx, 4000000h
0x14001205d  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140012062  test    bpl, bpl
0x140012065  jz      short loc_14001207B
0x140012067  test    rsi, rsi
0x14001206a  jz      short loc_14001207B
0x14001206c  mov     rax, [rsi]
0x14001206f  mov     rcx, rsi
0x140012072  mov     rax, [rax+10h]
0x140012076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001207b  lea     rcx, [rsp+78h+var_48]; this
0x140012080  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x140012085  lea     r11, [rsp+78h+var_28]
0x14001208a  mov     eax, ebx
0x14001208c  mov     rbx, [r11+38h]
0x140012090  mov     rbp, [r11+40h]
0x140012094  mov     rsp, r11
0x140012097  pop     r15
0x140012099  pop     r14
0x14001209b  pop     r13
0x14001209d  pop     rdi
0x14001209e  pop     rsi
0x14001209f  retn
```
