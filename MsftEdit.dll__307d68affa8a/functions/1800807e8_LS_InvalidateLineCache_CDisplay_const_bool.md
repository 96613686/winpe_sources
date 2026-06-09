# LS::InvalidateLineCache(CDisplay const *,bool)

- ea: `0x1800807e8`
- end: `0x18008095f`
- name: `?InvalidateLineCache@LS@@YAXPEBVCDisplay@@_N@Z`
- size: `375`
- prototype: `void __fastcall(LS *__hidden this, const struct CDisplay *, bool)`
- caller_count: `17`
- callee_count: `7`
- tags: ``

## callers

- `0x180018af0`
- `0x18003c4e0`
- `0x180050dc4`
- `0x18006793c`
- `0x18006b8f0`
- `0x1800700a4`
- `0x180074ed4`
- `0x18007574c`
- `0x180091b90`
- `0x1800b61b0`
- `0x1800c154c`
- `0x1800db540`
- `0x1800de1b0`
- `0x1801002a0`
- `0x180117b20`
- `0x18011a5d0`
- `0x18014c5b0`

## callees

- `0x18002af88`
- `0x1800807e8`
- `0x180081004`
- `0x1800810b8`
- `0x1800824a8`
- `0x1800825c0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080904`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180080904`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008080e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008090a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008080e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008090a`

## pseudocode

```c
void __fastcall LS::InvalidateLineCache(LS *this, const struct CDisplay *a2)
{
  int v2; // ebx
  _DWORD *LockTelemetry; // rax
  int v5; // ecx
  __int64 v6; // rbx
  Ptls6::ols *v7; // rbx
  __int16 v8; // ax
  Ptls6::CLsLine *v9; // rcx
  _DWORD *v10; // rax
  __int16 v11; // dx
  RTL_SRWLOCK *Lock; // rax
  __int64 v13; // rax
  int v14; // [rsp+30h] [rbp+8h] BYREF
  char v15; // [rsp+34h] [rbp+Ch]

  v2 = (int)CLockSharedData::LockOwner;
  v14 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v2 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v13 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v13 + 4);
  }
  v5 = CLSLock::_cOLSBusy + 1;
  v15 = 1;
  ++CLSLock::_cOLSBusy;
  if ( this )
  {
    v6 = *((_QWORD *)this + 2);
    if ( v6 )
    {
      v7 = (*(_DWORD *)(v6 + 184) & 0x40000000) != 0 ? *(Ptls6::ols **)(v6 + 616) : CLSLock::_pols;
      if ( v7 )
      {
        v8 = *((_WORD *)v7 + 526);
        if ( v5 > 1 )
        {
          *((_WORD *)v7 + 526) = v8 | 0x10;
        }
        else
        {
          *((_WORD *)v7 + 526) = v8 & 0xFFEF;
          if ( this == *((LS **)v7 + 4) )
          {
            v9 = (Ptls6::CLsLine *)*((_QWORD *)v7 + 6);
            if ( v9 )
            {
              v10 = (_DWORD *)*((_QWORD *)v7 + 5);
              if ( v10 && *v10 == 977490764 && *((_DWORD **)v9 + 1) == v10 )
                Ptls6::CLsLine::Destroy(v9);
              *((_QWORD *)v7 + 6) = 0;
            }
            v11 = *((_WORD *)v7 + 406);
            *((_WORD *)v7 + 92) = -1;
            if ( v11 >= 0 )
            {
              if ( qword_1802DF5C8 )
                (*(void (__fastcall **)(CCharFormatArray *))(*(_QWORD *)qword_1802DF5C8 + 8LL))(qword_1802DF5C8);
              *((_WORD *)v7 + 406) = -1;
            }
            if ( (*((_BYTE *)v7 + 1052) & 0x20) == 0 )
              Ptls6::ols::ClearRunCache(v7);
          }
        }
      }
    }
  }
  CLSLock::~CLSLock((CLSLock *)&v14);
}

```

## disassembly

```asm
0x1800807e8  mov     [rsp+arg_8], rbx
0x1800807ed  mov     [rsp+arg_10], rsi
0x1800807f2  push    rdi
0x1800807f3  sub     rsp, 20h
0x1800807f7  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800807fd  xor     esi, esi
0x1800807ff  mov     [rsp+28h+arg_0], esi
0x180080803  mov     rdi, rcx
0x180080806  test    ebx, ebx
0x180080808  jz      loc_1800808FA
0x18008080e  call    cs:__imp_GetCurrentThreadId
0x180080814  cmp     ebx, eax
0x180080816  jnz     loc_1800808FA
0x18008081c  xor     ecx, ecx
0x18008081e  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180080823  inc     dword ptr [rax]
0x180080825  mov     ecx, cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x18008082b  inc     ecx
0x18008082d  mov     [rsp+28h+arg_4], 1
0x180080832  mov     cs:?_cOLSBusy@CLSLock@@1HA, ecx; int CLSLock::_cOLSBusy
0x180080838  test    rdi, rdi
0x18008083b  jz      loc_1800808E0
0x180080841  mov     rbx, [rdi+10h]
0x180080845  test    rbx, rbx
0x180080848  jz      loc_1800808E0
0x18008084e  mov     eax, [rbx+0B8h]
0x180080854  shr     eax, 1Eh
0x180080857  test    al, 1
0x180080859  jnz     loc_180080946
0x18008085f  mov     rbx, cs:?_pols@CLSLock@@1PEAUols@Ptls6@@EA; Ptls6::ols * CLSLock::_pols
0x180080866  test    rbx, rbx
0x180080869  jz      short loc_1800808E0
0x18008086b  movzx   eax, word ptr [rbx+41Ch]
0x180080872  cmp     ecx, 1
0x180080875  jg      loc_180080952
0x18008087b  mov     ecx, 0FFEFh
0x180080880  and     ax, cx
0x180080883  mov     [rbx+41Ch], ax
0x18008088a  cmp     rdi, [rbx+20h]
0x18008088e  jnz     short loc_1800808E0
0x180080890  mov     rcx, [rbx+30h]; this
0x180080894  test    rcx, rcx
0x180080897  jz      short loc_1800808B9
0x180080899  mov     rax, [rbx+28h]
0x18008089d  test    rax, rax
0x1800808a0  jz      short loc_1800808B5
0x1800808a2  cmp     dword ptr [rax], 3A43534Ch
0x1800808a8  jnz     short loc_1800808B5
0x1800808aa  cmp     [rcx+8], rax
0x1800808ae  jnz     short loc_1800808B5
0x1800808b0  call    ?Destroy@CLsLine@Ptls6@@UEAAXXZ; Ptls6::CLsLine::Destroy(void)
0x1800808b5  mov     [rbx+30h], rsi
0x1800808b9  movzx   edx, word ptr [rbx+32Ch]
0x1800808c0  or      edi, 0FFFFFFFFh
0x1800808c3  mov     [rbx+0B8h], di
0x1800808ca  test    dx, dx
0x1800808cd  jns     short loc_180080925
0x1800808cf  test    byte ptr [rbx+41Ch], 20h
0x1800808d6  jnz     short loc_1800808E0
0x1800808d8  mov     rcx, rbx; this
0x1800808db  call    ?ClearRunCache@ols@Ptls6@@QEAAXXZ; Ptls6::ols::ClearRunCache(void)
0x1800808e0  lea     rcx, [rsp+28h+arg_0]; this
0x1800808e5  call    ??1CLSLock@@QEAA@XZ; CLSLock::~CLSLock(void)
0x1800808ea  mov     rbx, [rsp+28h+arg_8]
0x1800808ef  mov     rsi, [rsp+28h+arg_10]
0x1800808f4  add     rsp, 20h
0x1800808f8  pop     rdi
0x1800808f9  retn
0x1800808fa  xor     ecx, ecx
0x1800808fc  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180080901  mov     rcx, rax; SRWLock
0x180080904  call    cs:__imp_AcquireSRWLockExclusive
0x18008090a  call    cs:__imp_GetCurrentThreadId
0x180080910  xor     ecx, ecx
0x180080912  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180080918  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18008091d  inc     dword ptr [rax+4]
0x180080920  jmp     loc_180080825
0x180080925  mov     rcx, cs:qword_1802DF5C8
0x18008092c  test    rcx, rcx
0x18008092f  jz      short loc_18008093D
0x180080931  mov     rax, [rcx]
0x180080934  mov     rax, [rax+8]
0x180080938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008093d  mov     [rbx+32Ch], di
0x180080944  jmp     short loc_1800808CF
0x180080946  mov     rbx, [rbx+268h]
0x18008094d  jmp     loc_180080866
0x180080952  or      ax, 10h
0x180080956  mov     [rbx+41Ch], ax
0x18008095d  jmp     short loc_1800808E0
```
