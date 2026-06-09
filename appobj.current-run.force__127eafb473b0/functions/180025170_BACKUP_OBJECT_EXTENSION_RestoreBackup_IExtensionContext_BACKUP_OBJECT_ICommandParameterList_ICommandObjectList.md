# BACKUP_OBJECT_EXTENSION::RestoreBackup(IExtensionContext *,BACKUP_OBJECT *,ICommandParameterList *,ICommandObjectList *,void * *)

- ea: `0x180025170`
- end: `0x1800253f5`
- name: `?RestoreBackup@BACKUP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVBACKUP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAPEAX@Z`
- size: `645`
- prototype: `int(BACKUP_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct BACKUP_OBJECT *, struct ICommandParameterList *, struct ICommandObjectList *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180024090`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000557c`
- `0x180006b6c`
- `0x180025170`
- `0x1800253fc`
- `0x18002b0cc`
- `0x18002bd3c`
- `0x18002cdd8`
- `0x18002cfb8`
- `0x18002da9c`
- `0x18002dc60`
- `0x18002e468`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall BACKUP_OBJECT_EXTENSION::RestoreBackup(
        BACKUP_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct BACKUP_OBJECT *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        void **a6)
{
  int started; // ebx
  APP_OBJECT_UTILS *v10; // rcx
  unsigned int v11; // edi
  STATUS_OBJECT *v12; // rax
  const unsigned __int16 **v13; // rdi
  int v15; // [rsp+28h] [rbp-B1h]
  unsigned int v16; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int16 *v17; // [rsp+48h] [rbp-91h] BYREF
  va_list v18; // [rsp+50h] [rbp-89h] BYREF
  int v19; // [rsp+60h] [rbp-79h] BYREF
  __int64 v20; // [rsp+68h] [rbp-71h]
  _QWORD v21[5]; // [rsp+70h] [rbp-69h] BYREF
  int v22; // [rsp+98h] [rbp-41h]
  __int16 v23; // [rsp+9Ch] [rbp-3Dh]
  _QWORD v24[5]; // [rsp+A0h] [rbp-39h] BYREF
  int v25; // [rsp+C8h] [rbp-11h]
  __int16 v26; // [rsp+CCh] [rbp-Dh]
  int v27; // [rsp+D0h] [rbp-9h]
  va_list Arguments[2]; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+Fh]

  v29 = 0;
  v18 = 0;
  v17 = 0;
  v24[0] = 0;
  v24[4] = v24;
  v21[4] = v21;
  v25 = 32;
  v26 = 256;
  v27 = 0;
  v16 = 1;
  v19 = 0;
  v21[0] = 0;
  v22 = 32;
  v23 = 256;
  v20 = 0;
  *(_OWORD *)Arguments = 0;
  if ( a2 && a3 && a4 && a5 && a6 )
  {
    started = APP_OBJECT_UTILS::PopBooleanParameter((APP_OBJECT_UTILS *)0x20, a2, a4, L"stop", (int *)&v16, v15, 1);
    v10 = (APP_OBJECT_UTILS *)(started + 0x80000000);
    if ( (int)v10 < 0 || started == -2147023483 )
    {
      started = APP_OBJECT_UTILS::ValidateEmptyParameters(v10, a2, a4);
      if ( started >= 0 )
      {
        started = (*(__int64 (__fastcall **)(struct BACKUP_OBJECT *, const unsigned __int16 *, va_list *))(*(_QWORD *)a3 + 80LL))(
                    a3,
                    L"BACKUP.NAME",
                    &v18);
        if ( started >= 0 )
        {
          started = (*(__int64 (__fastcall **)(struct BACKUP_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)a3 + 80LL))(
                      a3,
                      L"path",
                      &v17);
          if ( started >= 0 )
          {
            v11 = v16;
            if ( !v16
              || (started = ResolveServices((struct SERVICES_MANAGER *)&v19), started >= 0)
              && ((v16 = 60000, (int)SERVICES_MANAGER::StopAll((SERVICES_MANAGER *)&v19, &v16) >= 0)
               || (started = SERVICES_MANAGER::Kill((SERVICES_MANAGER *)&v19), started >= 0)) )
            {
              started = BACKUP_FILE_SYSTEM_HELPER::RestoreBackupInPath(v17);
              if ( started >= 0 )
              {
                if ( !v11
                  || (v16 = 30000, started = SERVICES_MANAGER::StartAll((SERVICES_MANAGER *)&v19, &v16), started >= 0) )
                {
                  v12 = (STATUS_OBJECT *)operator new(0x110u);
                  if ( v12 && (v13 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v12)) != 0 )
                  {
                    Arguments[0] = v18;
                    started = STATUS_OBJECT::Create(v13, 0x40Fu, Arguments);
                    if ( started >= 0 )
                      started = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a5 + 24LL))(
                                  a5,
                                  v13);
                    (*((void (__fastcall **)(const unsigned __int16 **))*v13 + 2))(v13);
                  }
                  else
                  {
                    started = -2147024888;
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
    started = -2147024809;
  }
  SERVICES_MANAGER::~SERVICES_MANAGER((SERVICES_MANAGER *)&v19);
  BUFFER::~BUFFER((BUFFER *)v24);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180025170  mov     [rsp-8+arg_0], rbx
0x180025175  push    rbp
0x180025176  push    rsi
0x180025177  push    rdi
0x180025178  push    r14
0x18002517a  push    r15
0x18002517c  lea     rbp, [rsp-27h]
0x180025181  sub     rsp, 100h
0x180025188  mov     rax, cs:__security_cookie
0x18002518f  xor     rax, rsp
0x180025192  mov     [rbp+47h+var_30], rax
0x180025196  mov     r15, [rbp+47h+arg_20]
0x18002519a  xor     eax, eax
0x18002519c  mov     ecx, 20h ; ' '; this
0x1800251a1  mov     [rbp+47h+var_38], rax
0x1800251a5  mov     [rsp+120h+var_D0], rax
0x1800251aa  mov     r14, rdx
0x1800251ad  mov     [rsp+120h+var_D8], rax
0x1800251b2  xorps   xmm0, xmm0
0x1800251b5  mov     [rbp+47h+var_80], rax
0x1800251b9  lea     rax, [rbp+47h+var_80]
0x1800251bd  mov     [rbp+47h+var_60], rax
0x1800251c1  lea     rax, [rbp+47h+var_B0]
0x1800251c5  mov     [rbp+47h+var_90], rax
0x1800251c9  lea     edx, [rcx-1Fh]
0x1800251cc  mov     [rbp+47h+var_58], ecx
0x1800251cf  mov     rsi, r9
0x1800251d2  mov     [rbp+47h+var_54], 100h
0x1800251d8  mov     rdi, r8
0x1800251db  mov     [rbp+47h+var_50], 0
0x1800251e2  mov     [rsp+120h+var_E0], edx
0x1800251e6  mov     [rbp+47h+var_C0], 0
0x1800251ed  mov     [rbp+47h+var_B0], 0
0x1800251f5  mov     [rbp+47h+var_88], ecx
0x1800251f8  mov     [rbp+47h+var_84], 100h
0x1800251fe  mov     [rbp+47h+var_B8], 0
0x180025206  movups  xmmword ptr [rbp+47h+Arguments], xmm0
0x18002520a  test    r14, r14
0x18002520d  jz      loc_1800253B9
0x180025213  test    r8, r8
0x180025216  jz      loc_1800253B9
0x18002521c  test    r9, r9
0x18002521f  jz      loc_1800253B9
0x180025225  test    r15, r15
0x180025228  jz      loc_1800253B9
0x18002522e  cmp     [rbp+47h+arg_28], 0
0x180025233  jz      loc_1800253B9
0x180025239  mov     [rsp+120h+var_F0], edx; int
0x18002523d  lea     rax, [rsp+120h+var_E0]
0x180025242  mov     rdx, r14; struct IExtensionContext *
0x180025245  mov     [rsp+120h+var_100], rax; int *
0x18002524a  lea     r9, aStop; "stop"
0x180025251  mov     r8, rsi; struct ICommandParameterList *
0x180025254  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x180025259  mov     ebx, eax
0x18002525b  mov     eax, 80000000h
0x180025260  lea     ecx, [rbx+rax]; this
0x180025263  test    eax, ecx
0x180025265  jnz     short loc_180025273
0x180025267  cmp     ebx, 80070585h
0x18002526d  jnz     loc_1800253BE
0x180025273  mov     r8, rsi; struct ICommandParameterList *
0x180025276  mov     rdx, r14; struct IExtensionContext *
0x180025279  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18002527e  mov     ebx, eax
0x180025280  test    eax, eax
0x180025282  js      loc_1800253BE
0x180025288  mov     rax, [rdi]
0x18002528b  lea     r8, [rsp+120h+var_D0]
0x180025290  lea     rdx, aBackupName; "BACKUP.NAME"
0x180025297  mov     rcx, rdi
0x18002529a  mov     rax, [rax+50h]
0x18002529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252a3  mov     ebx, eax
0x1800252a5  test    eax, eax
0x1800252a7  js      loc_1800253BE
0x1800252ad  mov     rax, [rdi]
0x1800252b0  lea     r8, [rsp+120h+var_D8]
0x1800252b5  lea     rdx, aPath_1; "path"
0x1800252bc  mov     rcx, rdi
0x1800252bf  mov     rax, [rax+50h]
0x1800252c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252c8  mov     ebx, eax
0x1800252ca  test    eax, eax
0x1800252cc  js      loc_1800253BE
0x1800252d2  mov     edi, [rsp+120h+var_E0]
0x1800252d6  test    edi, edi
0x1800252d8  jz      short loc_18002531A
0x1800252da  lea     rcx, [rbp+47h+var_C0]; this
0x1800252de  call    ?ResolveServices@@YAJPEAVSERVICES_MANAGER@@@Z; ResolveServices(SERVICES_MANAGER *)
0x1800252e3  mov     ebx, eax
0x1800252e5  test    eax, eax
0x1800252e7  js      loc_1800253BE
0x1800252ed  lea     rdx, [rsp+120h+var_E0]; unsigned int *
0x1800252f2  mov     [rsp+120h+var_E0], 0EA60h
0x1800252fa  lea     rcx, [rbp+47h+var_C0]; this
0x1800252fe  call    ?StopAll@SERVICES_MANAGER@@QEAAJPEAK@Z; SERVICES_MANAGER::StopAll(ulong *)
0x180025303  test    eax, eax
0x180025305  jns     short loc_18002531A
0x180025307  lea     rcx, [rbp+47h+var_C0]; this
0x18002530b  call    ?Kill@SERVICES_MANAGER@@QEAAJXZ; SERVICES_MANAGER::Kill(void)
0x180025310  mov     ebx, eax
0x180025312  test    eax, eax
0x180025314  js      loc_1800253BE
0x18002531a  mov     rcx, [rsp+120h+var_D8]; unsigned __int16 *
0x18002531f  call    ?RestoreBackupInPath@BACKUP_FILE_SYSTEM_HELPER@@SAJPEBG@Z; BACKUP_FILE_SYSTEM_HELPER::RestoreBackupInPath(ushort const *)
0x180025324  mov     ebx, eax
0x180025326  test    eax, eax
0x180025328  js      loc_1800253BE
0x18002532e  test    edi, edi
0x180025330  jz      short loc_18002534E
0x180025332  lea     rdx, [rsp+120h+var_E0]; unsigned int *
0x180025337  mov     [rsp+120h+var_E0], 7530h
0x18002533f  lea     rcx, [rbp+47h+var_C0]; this
0x180025343  call    ?StartAll@SERVICES_MANAGER@@QEAAJPEAK@Z; SERVICES_MANAGER::StartAll(ulong *)
0x180025348  mov     ebx, eax
0x18002534a  test    eax, eax
0x18002534c  js      short loc_1800253BE
0x18002534e  mov     ecx, 110h; Size
0x180025353  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025358  test    rax, rax
0x18002535b  jz      short loc_1800253B2
0x18002535d  mov     rcx, rax; this
0x180025360  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180025365  mov     rdi, rax
0x180025368  test    rax, rax
0x18002536b  jz      short loc_1800253B2
0x18002536d  mov     rax, [rsp+120h+var_D0]
0x180025372  lea     r8, [rbp+47h+Arguments]; Arguments
0x180025376  mov     edx, 40Fh; dwMessageId
0x18002537b  mov     [rbp+47h+Arguments], rax
0x18002537f  mov     rcx, rdi; this
0x180025382  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180025387  mov     ebx, eax
0x180025389  test    eax, eax
0x18002538b  js      short loc_1800253A1
0x18002538d  mov     rax, [r15]
0x180025390  mov     rdx, rdi
0x180025393  mov     rcx, r15
0x180025396  mov     rax, [rax+18h]
0x18002539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002539f  mov     ebx, eax
0x1800253a1  mov     rax, [rdi]
0x1800253a4  mov     rcx, rdi
0x1800253a7  mov     rax, [rax+10h]
0x1800253ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b0  jmp     short loc_1800253BE
0x1800253b2  mov     ebx, 80070008h
0x1800253b7  jmp     short loc_1800253BE
0x1800253b9  mov     ebx, 80070057h
0x1800253be  lea     rcx, [rbp+47h+var_C0]; this
0x1800253c2  call    ??1SERVICES_MANAGER@@QEAA@XZ; SERVICES_MANAGER::~SERVICES_MANAGER(void)
0x1800253c7  lea     rcx, [rbp+47h+var_80]; this
0x1800253cb  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800253d0  mov     eax, ebx
0x1800253d2  mov     rcx, [rbp+47h+var_30]
0x1800253d6  xor     rcx, rsp; StackCookie
0x1800253d9  call    __security_check_cookie
0x1800253de  mov     rbx, [rsp+120h+arg_0]
0x1800253e6  add     rsp, 100h
0x1800253ed  pop     r15
0x1800253ef  pop     r14
0x1800253f1  pop     rdi
0x1800253f2  pop     rsi
0x1800253f3  pop     rbp
0x1800253f4  retn
```
