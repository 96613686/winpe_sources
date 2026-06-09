# BACKUP_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180023740`
- end: `0x180023ba0`
- name: `?CreateObjects@BACKUP_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1120`
- prototype: `int(BACKUP_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001ed0`
- `0x180001fb0`
- `0x180005440`
- `0x180023110`
- `0x180023740`
- `0x180024528`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800239bd`
- `msvcrt!_wcsicmp` at `0x1800239bd`

## string_xrefs

- `0x1800238e5`: `system.applicationHost/configHistory`

## pseudocode

```c
__int64 __fastcall BACKUP_OBJECT_EXTENSION::CreateObjects(
        BACKUP_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  __int64 v9; // rcx
  int BackupObjectPaths; // ebx
  int v11; // eax
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // r14
  const unsigned __int16 *v14; // rsi
  COMMAND_OBJECT *v15; // rax
  BACKUP_OBJECT *v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandParameterList *v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[32]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp-68h]
  int v30; // [rsp+A0h] [rbp-60h]
  __int16 v31; // [rsp+A4h] [rbp-5Ch]
  int v32; // [rsp+A8h] [rbp-58h]
  _BYTE v33[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v34; // [rsp+D0h] [rbp-30h]
  _BYTE v35[32]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v36; // [rsp+108h] [rbp+8h]
  __int16 v37; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v38[510]; // [rsp+122h] [rbp+22h] BYREF

  MULTISZ::MULTISZ((MULTISZ *)v35);
  MULTISZ::MULTISZ((MULTISZ *)v33);
  v21 = 0;
  v22 = 0;
  memset_0(v38, 0, sizeof(v38));
  v30 = 512;
  String2 = (wchar_t *)&v37;
  v31 = 256;
  v32 = 0;
  v37 = 0;
  v23 = 0;
  v27 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  if ( a2 && a3 && a4 && a5 && a6 )
  {
    BackupObjectPaths = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
                          a5,
                          &v22);
    if ( BackupObjectPaths >= 0 )
    {
      if ( !*a3 )
      {
        v11 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v9, a4, v22, L"BACKUP.NAME", (struct STRU *)v28, 0, 1);
        v9 = 0x80000000LL;
        BackupObjectPaths = v11;
        if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147023483 )
          goto LABEL_38;
        a3 = String2;
        if ( !*String2 )
          goto LABEL_12;
      }
      BackupObjectPaths = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v9, a4, v22);
      if ( BackupObjectPaths >= 0 )
      {
LABEL_12:
        BackupObjectPaths = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a4 + 80LL))(
                              a4,
                              &Str,
                              &v23);
        if ( BackupObjectPaths < 0 )
          goto LABEL_48;
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v23 + 24LL))(
               v23,
               L"system.applicationHost/configHistory",
               L"MACHINE/WEBROOT/APPHOST",
               &v24,
               &v27,
               0) < 0 )
        {
          v12 = L"%systemdrive%\\inetpub\\history";
          v26 = L"%systemdrive%\\inetpub\\history";
        }
        else
        {
          BackupObjectPaths = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 **, __int64 *, _QWORD))(*(_QWORD *)v24 + 64LL))(
                                v24,
                                L"path",
                                &v26,
                                &v25,
                                0);
          if ( BackupObjectPaths < 0 )
          {
            if ( v25 )
              (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a4 + 120LL))(
                a4,
                (unsigned int)BackupObjectPaths,
                &Str,
                v25,
                0);
            goto LABEL_38;
          }
          v12 = v26;
        }
        BackupObjectPaths = BACKUP_FILE_SYSTEM_HELPER::GetBackupObjectPaths(
                              v12,
                              (struct MULTISZ *)v35,
                              (struct MULTISZ *)v33);
        if ( BackupObjectPaths >= 0 )
        {
          v13 = (const unsigned __int16 *)(v36 & -(__int64)(*(_WORD *)v36 != 0));
          v14 = (const unsigned __int16 *)(v34 & -(__int64)(*(_WORD *)v34 != 0));
          while ( v13 )
          {
            if ( !*a3 || !_wcsicmp(v14, a3) )
            {
              v15 = (COMMAND_OBJECT *)operator new(0xD8u);
              v16 = v15;
              if ( !v15 )
              {
                BackupObjectPaths = -2147024888;
                break;
              }
              COMMAND_OBJECT::COMMAND_OBJECT(v15);
              *(_QWORD *)v16 = &BACKUP_OBJECT::`vftable';
              BackupObjectPaths = BACKUP_OBJECT::Create(v16, v14, v13);
              if ( BackupObjectPaths < 0
                || (v17 = *(_QWORD *)a4,
                    v21 = 0,
                    BackupObjectPaths = (*(__int64 (__fastcall **)(struct IExtensionContext *, BACKUP_OBJECT *, struct ICommandParameterList *, int *))(v17 + 152))(
                                          a4,
                                          v16,
                                          v22,
                                          &v21),
                    BackupObjectPaths < 0)
                || v21
                && (BackupObjectPaths = (*(__int64 (__fastcall **)(struct ICommandObjectList *, BACKUP_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                                          a6,
                                          v16),
                    BackupObjectPaths < 0) )
              {
                (*(void (__fastcall **)(BACKUP_OBJECT *))(*(_QWORD *)v16 + 16LL))(v16);
                break;
              }
              (*(void (__fastcall **)(BACKUP_OBJECT *))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v18 = -1;
            do
              ++v18;
            while ( v13[v18] );
            v13 = (const unsigned __int16 *)((unsigned __int64)&v13[v18 + 1] & -(__int64)(v13[v18 + 1] != 0));
            v19 = -1;
            do
              ++v19;
            while ( v14[v19] );
            v14 = (const unsigned __int16 *)((unsigned __int64)&v14[v19 + 1] & -(__int64)(v14[v19 + 1] != 0));
          }
        }
      }
    }
  }
  else
  {
    BackupObjectPaths = -2147024809;
  }
LABEL_38:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
LABEL_48:
  BUFFER::~BUFFER((BUFFER *)v28);
  BUFFER::~BUFFER((BUFFER *)v33);
  BUFFER::~BUFFER((BUFFER *)v35);
  return (unsigned int)BackupObjectPaths;
}

```

## disassembly

```asm
0x180023740  mov     [rsp-8+arg_0], rbx
0x180023745  push    rbp
0x180023746  push    rsi
0x180023747  push    rdi
0x180023748  push    r12
0x18002374a  push    r13
0x18002374c  push    r14
0x18002374e  push    r15
0x180023750  lea     rbp, [rsp-230h]
0x180023758  sub     rsp, 330h
0x18002375f  mov     rax, cs:__security_cookie
0x180023766  xor     rax, rsp
0x180023769  mov     [rbp+260h+var_40], rax
0x180023770  mov     rdi, [rbp+260h+arg_20]
0x180023777  lea     rcx, [rbp+260h+var_278]; this
0x18002377b  mov     r13, [rbp+260h+arg_28]
0x180023782  mov     r12, r9
0x180023785  mov     r15, r8
0x180023788  mov     rbx, rdx
0x18002378b  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180023790  lea     rcx, [rbp+260h+var_2B0]; this
0x180023794  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180023799  xor     esi, esi
0x18002379b  lea     rcx, [rbp+260h+var_23E]; void *
0x18002379f  xor     edx, edx; Val
0x1800237a1  mov     [rsp+360h+var_320], esi
0x1800237a5  mov     r8d, 1FEh; Size
0x1800237ab  mov     [rsp+360h+var_318], rsi
0x1800237b0  call    memset_0
0x1800237b5  mov     [rbp+260h+var_2C0], 200h
0x1800237bc  lea     rax, [rbp+260h+var_240]
0x1800237c0  mov     [rbp+260h+String2], rax
0x1800237c4  mov     [rbp+260h+var_2BC], 100h
0x1800237ca  mov     [rbp+260h+var_2B8], esi
0x1800237cd  mov     [rbp+260h+var_240], si
0x1800237d1  mov     [rsp+360h+var_310], rsi
0x1800237d6  mov     [rsp+360h+var_2F0], rsi
0x1800237db  mov     [rsp+360h+var_308], rsi
0x1800237e0  mov     [rsp+360h+var_2F8], rsi
0x1800237e5  mov     [rsp+360h+var_300], rsi
0x1800237ea  test    rbx, rbx
0x1800237ed  jz      loc_180023ACA
0x1800237f3  test    r15, r15
0x1800237f6  jz      loc_180023ACA
0x1800237fc  test    r12, r12
0x1800237ff  jz      loc_180023ACA
0x180023805  test    rdi, rdi
0x180023808  jz      loc_180023ACA
0x18002380e  test    r13, r13
0x180023811  jz      loc_180023ACA
0x180023817  mov     rax, [rdi]
0x18002381a  lea     rdx, [rsp+360h+var_318]
0x18002381f  mov     rcx, rdi
0x180023822  mov     rax, [rax+50h]
0x180023826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002382b  mov     ebx, eax
0x18002382d  test    eax, eax
0x18002382f  js      loc_180023ACF
0x180023835  cmp     [r15], si
0x180023839  jnz     short loc_180023888
0x18002383b  mov     r8, [rsp+360h+var_318]; struct ICommandParameterList *
0x180023840  lea     rax, [rsp+360h+var_2E8]
0x180023845  mov     [rsp+360h+var_330], 1; int
0x18002384d  lea     r9, aBackupName; "BACKUP.NAME"
0x180023854  mov     [rsp+360h+var_338], esi; int
0x180023858  mov     rdx, r12; struct IExtensionContext *
0x18002385b  mov     [rsp+360h+var_340], rax; struct STRU *
0x180023860  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180023865  mov     ecx, 80000000h; this
0x18002386a  mov     ebx, eax
0x18002386c  add     eax, ecx
0x18002386e  test    ecx, eax
0x180023870  jnz     short loc_18002387E
0x180023872  cmp     ebx, 80070585h
0x180023878  jnz     loc_180023ACF
0x18002387e  mov     r15, [rbp+260h+String2]
0x180023882  cmp     [r15], si
0x180023886  jz      short loc_18002389F
0x180023888  mov     r8, [rsp+360h+var_318]; struct ICommandParameterList *
0x18002388d  mov     rdx, r12; struct IExtensionContext *
0x180023890  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180023895  mov     ebx, eax
0x180023897  test    eax, eax
0x180023899  js      loc_180023ACF
0x18002389f  mov     rax, [r12]
0x1800238a3  lea     r8, [rsp+360h+var_310]
0x1800238a8  lea     rdx, Str
0x1800238af  mov     rcx, r12
0x1800238b2  mov     rax, [rax+50h]
0x1800238b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238bb  mov     ebx, eax
0x1800238bd  test    eax, eax
0x1800238bf  js      loc_180023B58
0x1800238c5  mov     rcx, [rsp+360h+var_310]
0x1800238ca  lea     rdx, [rsp+360h+var_2F0]
0x1800238cf  mov     qword ptr [rsp+360h+var_338], rsi
0x1800238d4  lea     r9, [rsp+360h+var_308]
0x1800238d9  mov     [rsp+360h+var_340], rdx
0x1800238de  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800238e5  lea     rdx, aSystemApplicat_0; "system.applicationHost/configHistory"
0x1800238ec  mov     rax, [rcx]
0x1800238ef  mov     rax, [rax+18h]
0x1800238f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238f8  test    eax, eax
0x1800238fa  js      short loc_180023963
0x1800238fc  mov     rcx, [rsp+360h+var_308]
0x180023901  lea     r9, [rsp+360h+var_300]
0x180023906  lea     r8, [rsp+360h+var_2F8]
0x18002390b  mov     [rsp+360h+var_340], rsi
0x180023910  lea     rdx, aPath_1; "path"
0x180023917  mov     rax, [rcx]
0x18002391a  mov     rax, [rax+40h]
0x18002391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023923  mov     ebx, eax
0x180023925  test    eax, eax
0x180023927  jns     short loc_18002395C
0x180023929  mov     rcx, [rsp+360h+var_300]
0x18002392e  test    rcx, rcx
0x180023931  jz      loc_180023ACF
0x180023937  mov     rax, [r12]
0x18002393b  lea     r8, Str
0x180023942  mov     r9, rcx
0x180023945  mov     dword ptr [rsp+360h+var_340], esi
0x180023949  mov     edx, ebx
0x18002394b  mov     rcx, r12
0x18002394e  mov     rax, [rax+78h]
0x180023952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023957  jmp     loc_180023ACF
0x18002395c  mov     rcx, [rsp+360h+var_2F8]
0x180023961  jmp     short loc_18002396F
0x180023963  lea     rcx, aSystemdriveIne; "%systemdrive%\\inetpub\\history"
0x18002396a  mov     [rsp+360h+var_2F8], rcx
0x18002396f  lea     r8, [rbp+260h+var_2B0]; struct MULTISZ *
0x180023973  lea     rdx, [rbp+260h+var_278]; struct MULTISZ *
0x180023977  call    ?GetBackupObjectPaths@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBGPEAVMULTISZ@@1@Z; BACKUP_FILE_SYSTEM_HELPER::GetBackupObjectPaths(ushort const *,MULTISZ *,MULTISZ *)
0x18002397c  mov     ebx, eax
0x18002397e  test    eax, eax
0x180023980  js      loc_180023ACF
0x180023986  mov     rcx, [rbp+260h+var_258]
0x18002398a  movzx   eax, word ptr [rcx]
0x18002398d  neg     ax
0x180023990  sbb     r14, r14
0x180023993  and     r14, rcx
0x180023996  mov     rcx, [rbp+260h+var_290]
0x18002399a  movzx   eax, word ptr [rcx]
0x18002399d  neg     ax
0x1800239a0  sbb     rsi, rsi
0x1800239a3  and     rsi, rcx
0x1800239a6  xor     edi, edi
0x1800239a8  test    r14, r14
0x1800239ab  jz      loc_180023ACF
0x1800239b1  cmp     [r15], di
0x1800239b5  jz      short loc_1800239CB
0x1800239b7  mov     rdx, r15; String2
0x1800239ba  mov     rcx, rsi; String1
0x1800239bd  call    cs:__imp__wcsicmp
0x1800239c3  test    eax, eax
0x1800239c5  jnz     loc_180023A6A
0x1800239cb  mov     ecx, 0D8h; Size
0x1800239d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800239d5  mov     rdi, rax
0x1800239d8  test    rax, rax
0x1800239db  jz      loc_180023AC3
0x1800239e1  mov     rcx, rax; this
0x1800239e4  call    ??0COMMAND_OBJECT@@QEAA@XZ; COMMAND_OBJECT::COMMAND_OBJECT(void)
0x1800239e9  lea     rcx, ??_7BACKUP_OBJECT@@6B@; const BACKUP_OBJECT::`vftable'
0x1800239f0  mov     r8, r14; unsigned __int16 *
0x1800239f3  mov     [rdi], rcx
0x1800239f6  mov     rdx, rsi; unsigned __int16 *
0x1800239f9  mov     rcx, rdi; this
0x1800239fc  call    ?Create@BACKUP_OBJECT@@QEAAJPEBG0@Z; BACKUP_OBJECT::Create(ushort const *,ushort const *)
0x180023a01  mov     ebx, eax
0x180023a03  test    eax, eax
0x180023a05  js      loc_180023AB2
0x180023a0b  mov     rax, [r12]
0x180023a0f  lea     r9, [rsp+360h+var_320]
0x180023a14  mov     r8, [rsp+360h+var_318]
0x180023a19  mov     rdx, rdi
0x180023a1c  mov     rcx, r12
0x180023a1f  mov     [rsp+360h+var_320], 0
0x180023a27  mov     rax, [rax+98h]
0x180023a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a33  mov     ebx, eax
0x180023a35  test    eax, eax
0x180023a37  js      short loc_180023AB2
0x180023a39  cmp     [rsp+360h+var_320], 0
0x180023a3e  jz      short loc_180023A59
0x180023a40  mov     rax, [r13+0]
0x180023a44  mov     rdx, rdi
0x180023a47  mov     rcx, r13
0x180023a4a  mov     rax, [rax+18h]
0x180023a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a53  mov     ebx, eax
0x180023a55  test    eax, eax
0x180023a57  js      short loc_180023AB2
0x180023a59  mov     rax, [rdi]
0x180023a5c  mov     rcx, rdi
0x180023a5f  mov     rax, [rax+10h]
0x180023a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a68  xor     edi, edi
0x180023a6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023a6e  inc     rax
0x180023a71  cmp     [r14+rax*2], di
0x180023a76  jnz     short loc_180023A6E
0x180023a78  lea     rcx, [r14+2]
0x180023a7c  lea     rcx, [rcx+rax*2]
0x180023a80  movzx   eax, word ptr [rcx]
0x180023a83  neg     ax
0x180023a86  sbb     r14, r14
0x180023a89  and     r14, rcx
0x180023a8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023a90  inc     rax
0x180023a93  cmp     [rsi+rax*2], di
0x180023a97  jnz     short loc_180023A90
0x180023a99  lea     rcx, [rsi+2]
0x180023a9d  lea     rcx, [rcx+rax*2]
0x180023aa1  movzx   eax, word ptr [rcx]
0x180023aa4  neg     ax
0x180023aa7  sbb     rsi, rsi
0x180023aaa  and     rsi, rcx
0x180023aad  jmp     loc_1800239A8
0x180023ab2  mov     rax, [rdi]
0x180023ab5  mov     rcx, rdi
0x180023ab8  mov     rax, [rax+10h]
0x180023abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ac1  jmp     short loc_180023ACF
0x180023ac3  mov     ebx, 80070008h
0x180023ac8  jmp     short loc_180023ACF
0x180023aca  mov     ebx, 80070057h
0x180023acf  mov     rcx, [rsp+360h+var_318]
0x180023ad4  xor     edi, edi
0x180023ad6  test    rcx, rcx
0x180023ad9  jz      short loc_180023AEC
0x180023adb  mov     rax, [rcx]
0x180023ade  mov     rax, [rax+10h]
0x180023ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ae7  mov     [rsp+360h+var_318], rdi
0x180023aec  mov     rcx, [rsp+360h+var_310]
0x180023af1  test    rcx, rcx
0x180023af4  jz      short loc_180023B07
0x180023af6  mov     rax, [rcx]
0x180023af9  mov     rax, [rax+10h]
0x180023afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b02  mov     [rsp+360h+var_310], rdi
0x180023b07  mov     rcx, [rsp+360h+var_308]
0x180023b0c  test    rcx, rcx
0x180023b0f  jz      short loc_180023B22
0x180023b11  mov     rax, [rcx]
0x180023b14  mov     rax, [rax+10h]
0x180023b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b1d  mov     [rsp+360h+var_308], rdi
0x180023b22  mov     rcx, [rsp+360h+var_2F0]
0x180023b27  test    rcx, rcx
0x180023b2a  jz      short loc_180023B3D
0x180023b2c  mov     rax, [rcx]
0x180023b2f  mov     rax, [rax+10h]
0x180023b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b38  mov     [rsp+360h+var_2F0], rdi
0x180023b3d  mov     rcx, [rsp+360h+var_300]
0x180023b42  test    rcx, rcx
0x180023b45  jz      short loc_180023B58
0x180023b47  mov     rax, [rcx]
0x180023b4a  mov     rax, [rax+10h]
0x180023b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b53  mov     [rsp+360h+var_300], rdi
0x180023b58  lea     rcx, [rsp+360h+var_2E8]; this
0x180023b5d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023b62  lea     rcx, [rbp+260h+var_2B0]; this
0x180023b66  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023b6b  lea     rcx, [rbp+260h+var_278]; this
0x180023b6f  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023b74  mov     eax, ebx
0x180023b76  mov     rcx, [rbp+260h+var_40]
0x180023b7d  xor     rcx, rsp; StackCookie
0x180023b80  call    __security_check_cookie
0x180023b85  mov     rbx, [rsp+360h+arg_0]
0x180023b8d  add     rsp, 330h
0x180023b94  pop     r15
0x180023b96  pop     r14
0x180023b98  pop     r13
0x180023b9a  pop     r12
0x180023b9c  pop     rdi
0x180023b9d  pop     rsi
0x180023b9e  pop     rbp
0x180023b9f  retn
```
