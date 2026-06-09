# CCbsTiSession::FinalizeEx(uint,_CbsRequiredAction *)

- ea: `0x14000fbc4`
- end: `0x14000fd76`
- name: `?FinalizeEx@CCbsTiSession@@UEAAJIPEAW4_CbsRequiredAction@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(CCbsTiSession *__hidden this, unsigned int, enum _CbsRequiredAction *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x14000fbb0`

## callees

- `0x140006778`
- `0x14000a880`
- `0x14000dca8`
- `0x14000e2ac`
- `0x14000fbc4`
- `0x1400106c4`
- `0x140011ad0`
- `0x140011bc8`
- `0x140011e34`
- `0x140017658`
- `0x14002b010`

## string_xrefs

- `0x14000fd39`: `Failed to resume the session after servicing stack update.`

## pseudocode

```c
__int64 __fastcall CCbsTiSession::FinalizeEx(CCbsTiSession *this, unsigned int a2, enum _CbsRequiredAction *a3)
{
  CCbsTiSession *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // r9
  size_t v9; // rdx
  int v10; // ecx
  int v11; // ebp
  int v12; // eax
  bool v13; // zf
  int SureWorkerSessionAvailable; // eax
  int v15; // ecx
  _BYTE v17[32]; // [rsp+20h] [rbp-48h] BYREF
  bool v18; // [rsp+70h] [rbp+8h] BYREF

  v3 = (CCbsTiSession *)((char *)this - 256);
  CritSecLocker::CritSecLocker((CritSecLocker *)v17, (CCbsTiSession *)((char *)this - 208), 1);
  if ( a3 )
  {
    if ( *((_DWORD *)this - 22) && (a2 & 0x80000) == 0 )
    {
      v7 = -2146498494;
      v8 = "Cannot finalize a session that has been finalized.";
      goto LABEL_3;
    }
    *((_DWORD *)this - 33) |= a2;
    v10 = *((_DWORD *)this - 33);
    v11 = v10 & 0x200;
    *((_DWORD *)this - 22) = 1;
    v13 = *((_QWORD *)this - 27) == 0;
    *((_DWORD *)this - 36) = v11 != 0;
    if ( v13 && !v10 && !*((_DWORD *)this - 32) )
    {
      v7 = 0;
      v12 = 0;
      v13 = vbRequireReboot == 0;
LABEL_24:
      LOBYTE(v12) = !v13;
      *(_DWORD *)a3 = v12;
      goto LABEL_25;
    }
    SureWorkerSessionAvailable = CCbsTiSession::MakeSureWorkerSessionAvailable(v3, 1);
    v7 = SureWorkerSessionAvailable;
    if ( SureWorkerSessionAvailable >= 0 )
    {
      CCbsTiSession::RegisterTiUIHandler(v3);
      CritSecLocker::Unlock((CritSecLocker *)v17);
      SureWorkerSessionAvailable = (*(__int64 (__fastcall **)(_QWORD, _QWORD, enum _CbsRequiredAction *))(**((_QWORD **)this - 27) + 112LL))(
                                     *((_QWORD *)this - 27),
                                     a2,
                                     a3);
      v7 = SureWorkerSessionAvailable;
      if ( SureWorkerSessionAvailable >= 0 )
      {
        if ( v11 )
          goto LABEL_25;
        v15 = *(_DWORD *)(*((_QWORD *)this - 21) + 48LL);
        if ( v15 == 985091 )
        {
          CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(v3);
          WaitForTiWorkerToShutdown();
          v7 = 0;
          goto LABEL_25;
        }
        if ( v15 != 985139 )
          goto LABEL_25;
        CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(v3);
        WaitForTiWorkerToShutdown();
        v18 = 0;
        SureWorkerSessionAvailable = CCbsTiSession::ResumeSession(v3, 0, &v18);
        v7 = SureWorkerSessionAvailable;
        if ( SureWorkerSessionAvailable >= 0 )
        {
          v12 = 0;
          v13 = !v18;
          goto LABEL_24;
        }
        v8 = "Failed to resume the session after servicing stack update.";
      }
      else
      {
        v8 = "Failed to FinalizeEx using worker session";
      }
    }
    else
    {
      v8 = "Failed to get worker session.";
    }
    v9 = (unsigned int)SureWorkerSessionAvailable;
    goto LABEL_4;
  }
  v7 = -2147467261;
  v8 = "Invalid argument: pRequiredAction.";
LABEL_3:
  v9 = v7;
LABEL_4:
  CBSWdsLogLight(0x4000000u, v9, (size_t *)1, v8);
LABEL_25:
  CritSecLocker::~CritSecLocker((CritSecLocker *)v17);
  return v7;
}

```

## disassembly

```asm
0x14000fbc4  mov     [rsp+arg_8], rbx
0x14000fbc9  mov     [rsp+arg_10], rbp
0x14000fbce  push    rsi
0x14000fbcf  push    rdi
0x14000fbd0  push    r13
0x14000fbd2  push    r14
0x14000fbd4  push    r15
0x14000fbd6  sub     rsp, 40h
0x14000fbda  lea     rsi, [rcx-100h]
0x14000fbe1  mov     r14, r8
0x14000fbe4  mov     r15d, edx
0x14000fbe7  mov     rdi, rcx
0x14000fbea  mov     r13d, 1
0x14000fbf0  lea     rdx, [rsi+30h]; struct AutoCritSec *
0x14000fbf4  mov     r8b, r13b; bool
0x14000fbf7  lea     rcx, [rsp+68h+var_48]; this
0x14000fbfc  call    ??0CritSecLocker@@QEAA@AEAVAutoCritSec@@_N@Z; CritSecLocker::CritSecLocker(AutoCritSec &,bool)
0x14000fc01  test    r14, r14
0x14000fc04  jnz     short loc_14000FC26
0x14000fc06  mov     ebx, 80004003h
0x14000fc0b  lea     r9, aInvalidArgumen_17; "Invalid argument: pRequiredAction."
0x14000fc12  mov     edx, ebx
0x14000fc14  mov     r8d, r13d
0x14000fc17  mov     ecx, 4000000h
0x14000fc1c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000fc21  jmp     loc_14000FD51
0x14000fc26  cmp     dword ptr [rdi-58h], 0
0x14000fc2a  jz      short loc_14000FC41
0x14000fc2c  bt      r15d, 13h
0x14000fc31  jb      short loc_14000FC41
0x14000fc33  mov     ebx, 800F0842h
0x14000fc38  lea     r9, aCannotFinalize; "Cannot finalize a session that has been"...
0x14000fc3f  jmp     short loc_14000FC12
0x14000fc41  or      [rdi-84h], r15d
0x14000fc48  mov     eax, 0
0x14000fc4d  mov     ecx, [rdi-84h]
0x14000fc53  mov     ebp, ecx
0x14000fc55  and     ebp, 200h
0x14000fc5b  mov     [rdi-58h], r13d
0x14000fc5f  setnz   al
0x14000fc62  cmp     qword ptr [rdi-0D8h], 0
0x14000fc6a  mov     [rdi-90h], eax
0x14000fc70  jnz     short loc_14000FC8A
0x14000fc72  test    ecx, ecx
0x14000fc74  jnz     short loc_14000FC8A
0x14000fc76  cmp     [rdi-80h], ecx
0x14000fc79  jnz     short loc_14000FC8A
0x14000fc7b  xor     ebx, ebx
0x14000fc7d  xor     eax, eax
0x14000fc7f  cmp     cs:?vbRequireReboot@@3HA, eax; int vbRequireReboot
0x14000fc85  jmp     loc_14000FD4B
0x14000fc8a  mov     dl, r13b; bool
0x14000fc8d  mov     rcx, rsi; this
0x14000fc90  call    ?MakeSureWorkerSessionAvailable@CCbsTiSession@@QEAAJ_N@Z; CCbsTiSession::MakeSureWorkerSessionAvailable(bool)
0x14000fc95  mov     ebx, eax
0x14000fc97  test    eax, eax
0x14000fc99  jns     short loc_14000FCA9
0x14000fc9b  lea     r9, aFailedToGetWor_1; "Failed to get worker session."
0x14000fca2  mov     edx, eax
0x14000fca4  jmp     loc_14000FC14
0x14000fca9  mov     rcx, rsi; this
0x14000fcac  call    ?RegisterTiUIHandler@CCbsTiSession@@QEAAXXZ; CCbsTiSession::RegisterTiUIHandler(void)
0x14000fcb1  lea     rcx, [rsp+68h+var_48]; this
0x14000fcb6  call    ?Unlock@CritSecLocker@@UEAAXXZ; CritSecLocker::Unlock(void)
0x14000fcbb  mov     rcx, [rdi-0D8h]
0x14000fcc2  mov     r8, r14
0x14000fcc5  mov     edx, r15d
0x14000fcc8  mov     rax, [rcx]
0x14000fccb  mov     rax, [rax+70h]
0x14000fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fcd4  mov     ebx, eax
0x14000fcd6  test    eax, eax
0x14000fcd8  jns     short loc_14000FCE3
0x14000fcda  lea     r9, aFailedToFinali; "Failed to FinalizeEx using worker sessi"...
0x14000fce1  jmp     short loc_14000FCA2
0x14000fce3  test    ebp, ebp
0x14000fce5  jnz     short loc_14000FD51
0x14000fce7  mov     rax, [rdi-0A8h]
0x14000fcee  mov     ecx, [rax+30h]
0x14000fcf1  cmp     ecx, 0F0803h
0x14000fcf7  jnz     short loc_14000FD0A
0x14000fcf9  mov     rcx, rsi; this
0x14000fcfc  call    ?ReleaseWorkerSessionAfterServicingStackUpdate@CCbsTiSession@@QEAAXXZ; CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(void)
0x14000fd01  call    WaitForTiWorkerToShutdown
0x14000fd06  xor     ebx, ebx
0x14000fd08  jmp     short loc_14000FD51
0x14000fd0a  cmp     ecx, 0F0833h
0x14000fd10  jnz     short loc_14000FD51
0x14000fd12  mov     rcx, rsi; this
0x14000fd15  call    ?ReleaseWorkerSessionAfterServicingStackUpdate@CCbsTiSession@@QEAAXXZ; CCbsTiSession::ReleaseWorkerSessionAfterServicingStackUpdate(void)
0x14000fd1a  call    WaitForTiWorkerToShutdown
0x14000fd1f  lea     r8, [rsp+68h+arg_0]; bool *
0x14000fd24  mov     [rsp+68h+arg_0], 0
0x14000fd29  xor     edx, edx; bool
0x14000fd2b  mov     rcx, rsi; this
0x14000fd2e  call    ?ResumeSession@CCbsTiSession@@QEAAJ_NPEA_N@Z; CCbsTiSession::ResumeSession(bool,bool *)
0x14000fd33  mov     ebx, eax
0x14000fd35  test    eax, eax
0x14000fd37  jns     short loc_14000FD45
0x14000fd39  lea     r9, aFailedToResume; "Failed to resume the session after serv"...
0x14000fd40  jmp     loc_14000FCA2
0x14000fd45  xor     eax, eax
0x14000fd47  cmp     [rsp+68h+arg_0], al
0x14000fd4b  setnz   al
0x14000fd4e  mov     [r14], eax
0x14000fd51  lea     rcx, [rsp+68h+var_48]; this
0x14000fd56  call    ??1CritSecLocker@@UEAA@XZ; CritSecLocker::~CritSecLocker(void)
0x14000fd5b  lea     r11, [rsp+68h+var_28]
0x14000fd60  mov     eax, ebx
0x14000fd62  mov     rbx, [r11+38h]
0x14000fd66  mov     rbp, [r11+40h]
0x14000fd6a  mov     rsp, r11
0x14000fd6d  pop     r15
0x14000fd6f  pop     r14
0x14000fd71  pop     r13
0x14000fd73  pop     rdi
0x14000fd74  pop     rsi
0x14000fd75  retn
```
