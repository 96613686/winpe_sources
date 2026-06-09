# CHangReport::WerCallback(_WER_CALLBACK_INPUT * const)

- ea: `0x1400214f0`
- end: `0x140021828`
- name: `?WerCallback@CHangReport@@AEAAHQEAU_WER_CALLBACK_INPUT@@@Z`
- size: `824`
- prototype: `__int64 __fastcall(CHangReport *__hidden this, struct _WER_CALLBACK_INPUT *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140021070`

## callees

- `0x1400207c4`
- `0x1400214f0`
- `0x140022b58`
- `0x140049944`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400217b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400217b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021810`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14002152e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140021797`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14002152e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140021797`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CHangReport::WerCallback(CHangReport *this, struct _WER_CALLBACK_INPUT *const a2)
{
  int v4; // ebp
  void *v5; // rsi
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  __int64 (__fastcall *v15)(CHangReport *, char *, void *); // rax
  BOOL v16; // esi
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  char v23; // al
  const wchar_t *v24; // rax
  int *v25; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-38h] BYREF
  char v28; // [rsp+48h] [rbp-30h]
  BOOL v29; // [rsp+80h] [rbp+8h] BYREF

  v4 = 1;
  v5 = 0;
  CHangReport::Lock(this, &lpCriticalSection, L"CHangReport::WerCallback");
  if ( !*((_DWORD *)this + 15) )
  {
    v5 = (void *)*((_QWORD *)a2 + 2);
    SetThreadpoolWait(*((PTP_WAIT *)this + 3092), v5, 0);
  }
  v6 = *((_DWORD *)a2 + 2);
  if ( v6 > 11 )
  {
    v17 = v6 - 12;
    if ( !v17 )
    {
      v15 = *(__int64 (__fastcall **)(CHangReport *, char *, void *))(*(_QWORD *)this + 128LL);
LABEL_39:
      v14 = v15(this, (char *)a2 + 24, v5);
      goto LABEL_40;
    }
    v18 = v17 - 4;
    if ( v18 )
    {
      v19 = v18 - 2;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              if ( v22 != 1 )
                goto LABEL_31;
              v4 = 0;
              v14 = (*(__int64 (__fastcall **)(CHangReport *, char *, _QWORD))(*(_QWORD *)this + 176LL))(
                      this,
                      (char *)a2 + 28,
                      *((unsigned int *)a2 + 6));
            }
            else
            {
              v4 = 0;
              v14 = (*(__int64 (__fastcall **)(CHangReport *, char *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 168LL))(
                      this,
                      (char *)a2 + 72,
                      *((_QWORD *)a2 + 5),
                      *((_QWORD *)a2 + 6),
                      *((_QWORD *)a2 + 7),
                      *((_QWORD *)a2 + 8));
            }
          }
          else
          {
            v4 = 0;
            v14 = (*(__int64 (__fastcall **)(CHangReport *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 160LL))(
                    this,
                    *((unsigned int *)a2 + 10),
                    *((_QWORD *)a2 + 6),
                    *((_QWORD *)a2 + 7));
          }
        }
        else
        {
          v4 = 0;
          v14 = (*(__int64 (__fastcall **)(CHangReport *, char *, _QWORD, _QWORD))(*(_QWORD *)this + 152LL))(
                  this,
                  (char *)a2 + 24,
                  *((_QWORD *)a2 + 11),
                  *((_QWORD *)a2 + 12));
        }
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(CHangReport *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 64LL))(
                this,
                *((unsigned int *)a2 + 6),
                *((unsigned int *)a2 + 7),
                *((unsigned int *)a2 + 8));
      }
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(CHangReport *, char *, char *))(*(_QWORD *)this + 136LL))(
              this,
              (char *)a2 + 24,
              (char *)a2 + 32);
    }
  }
  else if ( v6 == 11 )
  {
    v14 = (*(__int64 (__fastcall **)(CHangReport *, _QWORD, _QWORD))(*(_QWORD *)this + 88LL))(
            this,
            *((unsigned int *)a2 + 6),
            *((unsigned int *)a2 + 7));
  }
  else
  {
    v7 = v6 - 1;
    if ( !v7 )
    {
      v14 = (*(__int64 (__fastcall **)(CHangReport *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 96LL))(
              this,
              *((_QWORD *)a2 + 3),
              *((_QWORD *)a2 + 4),
              *((_QWORD *)a2 + 5));
      goto LABEL_40;
    }
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 3;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( !v12 )
            {
              v16 = CHangReport::_CheckIfCanceled(this, v5) == 0;
              goto LABEL_41;
            }
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 == 1 )
              {
                v14 = (*(__int64 (__fastcall **)(CHangReport *, _QWORD))(*(_QWORD *)this + 80LL))(
                        this,
                        *((_QWORD *)a2 + 3));
                goto LABEL_40;
              }
LABEL_31:
              v16 = 0;
              goto LABEL_41;
            }
            v15 = *(__int64 (__fastcall **)(CHangReport *, char *, void *))(*(_QWORD *)this + 120LL);
            goto LABEL_39;
          }
          v14 = (*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 72LL))(this);
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(CHangReport *, char *, _QWORD, void *))(*(_QWORD *)this + 112LL))(
                  this,
                  (char *)a2 + 28,
                  *((unsigned int *)a2 + 6),
                  v5);
        }
      }
      else
      {
        v4 = 0;
        v14 = (*(__int64 (__fastcall **)(CHangReport *, char *))(*(_QWORD *)this + 144LL))(this, (char *)a2 + 28);
      }
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(CHangReport *, LPCRITICAL_SECTION *, void *, _QWORD, _QWORD))(*(_QWORD *)this + 104LL))(
              this,
              &lpCriticalSection,
              v5,
              *((_QWORD *)a2 + 3),
              *((_QWORD *)a2 + 4));
    }
  }
LABEL_40:
  v16 = v14;
LABEL_41:
  v29 = v16;
  SetThreadpoolWait(*((PTP_WAIT *)this + 3092), 0, 0);
  if ( !v28 )
    __int2c();
  LeaveCriticalSection(lpCriticalSection);
  v23 = 0;
  v28 = 0;
  if ( *((_QWORD *)this + 9) && v4 )
  {
    v24 = (const wchar_t *)(*(__int64 (__fastcall **)(CHangReport *))(*(_QWORD *)this + 8LL))(this);
    v25 = &v29;
    if ( v16 )
      v25 = 0;
    WerPluginsInvokeCallback(*((void **)this + 9), v24, a2, v25);
    v16 = v29;
    v23 = v28;
  }
  if ( v23 )
    LeaveCriticalSection(lpCriticalSection);
  return v16;
}

```

## disassembly

```asm
0x1400214f0  push    rbx
0x1400214f2  push    rbp
0x1400214f3  push    rsi
0x1400214f4  push    rdi
0x1400214f5  sub     rsp, 58h
0x1400214f9  mov     rdi, rdx
0x1400214fc  mov     rbx, rcx
0x1400214ff  mov     ebp, 1
0x140021504  xor     esi, esi
0x140021506  lea     r8, aChangreportWer; "CHangReport::WerCallback"
0x14002150d  lea     rdx, [rsp+78h+lpCriticalSection]
0x140021512  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x140021517  nop
0x140021518  cmp     [rbx+3Ch], esi
0x14002151b  jnz     short loc_14002153A
0x14002151d  mov     rsi, [rdi+10h]
0x140021521  xor     r8d, r8d; pftTimeout
0x140021524  mov     rdx, rsi; h
0x140021527  mov     rcx, [rbx+60A0h]; pwa
0x14002152e  call    cs:__imp_SetThreadpoolWait
0x140021535  nop     dword ptr [rax+rax+00h]
0x14002153a  mov     ecx, [rdi+8]
0x14002153d  cmp     ecx, 0Bh
0x140021540  jg      loc_140021669
0x140021546  jz      loc_14002164E
0x14002154c  sub     ecx, 1
0x14002154f  jz      loc_14002162E
0x140021555  sub     ecx, 1
0x140021558  jz      loc_140021605
0x14002155e  sub     ecx, 3
0x140021561  jz      loc_1400215F3
0x140021567  sub     ecx, 1
0x14002156a  jz      short loc_1400215D4
0x14002156c  sub     ecx, 1
0x14002156f  jz      short loc_1400215C0
0x140021571  sub     ecx, 1
0x140021574  jz      short loc_1400215A8
0x140021576  sub     ecx, 1
0x140021579  jz      short loc_14002159C
0x14002157b  cmp     ecx, 1
0x14002157e  jnz     loc_14002169C
0x140021584  mov     rax, [rbx]
0x140021587  mov     rdx, [rdi+18h]
0x14002158b  mov     rax, [rax+50h]
0x14002158f  mov     rcx, rbx
0x140021592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021597  jmp     loc_140021782
0x14002159c  mov     rax, [rbx]
0x14002159f  mov     rax, [rax+78h]
0x1400215a3  jmp     loc_140021773
0x1400215a8  mov     rdx, rsi; void *
0x1400215ab  mov     rcx, rbx; this
0x1400215ae  call    ?_CheckIfCanceled@CHangReport@@IEAAHPEAX@Z; CHangReport::_CheckIfCanceled(void *)
0x1400215b3  xor     esi, esi
0x1400215b5  test    eax, eax
0x1400215b7  setz    sil
0x1400215bb  jmp     loc_140021784
0x1400215c0  mov     rax, [rbx]
0x1400215c3  mov     rcx, rbx
0x1400215c6  mov     rax, [rax+48h]
0x1400215ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400215cf  jmp     loc_140021782
0x1400215d4  mov     rax, [rbx]
0x1400215d7  lea     rdx, [rdi+1Ch]
0x1400215db  mov     r9, rsi
0x1400215de  mov     r8d, [rdi+18h]
0x1400215e2  mov     rcx, rbx
0x1400215e5  mov     rax, [rax+70h]
0x1400215e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400215ee  jmp     loc_140021782
0x1400215f3  xor     ebp, ebp
0x1400215f5  mov     rax, [rbx]
0x1400215f8  lea     rdx, [rdi+1Ch]
0x1400215fc  mov     rax, [rax+90h]
0x140021603  jmp     short loc_14002158F
0x140021605  mov     rax, [rbx]
0x140021608  mov     rcx, [rdi+20h]
0x14002160c  mov     [rsp+78h+var_58], rcx
0x140021611  mov     r9, [rdi+18h]
0x140021615  mov     r8, rsi
0x140021618  lea     rdx, [rsp+78h+lpCriticalSection]
0x14002161d  mov     rcx, rbx
0x140021620  mov     rax, [rax+68h]
0x140021624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021629  jmp     loc_140021782
0x14002162e  mov     rax, [rbx]
0x140021631  mov     r9, [rdi+28h]
0x140021635  mov     r8, [rdi+20h]
0x140021639  mov     rdx, [rdi+18h]
0x14002163d  mov     rax, [rax+60h]
0x140021641  mov     rcx, rbx
0x140021644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021649  jmp     loc_140021782
0x14002164e  mov     rax, [rbx]
0x140021651  mov     r8d, [rdi+1Ch]
0x140021655  mov     edx, [rdi+18h]
0x140021658  mov     rcx, rbx
0x14002165b  mov     rax, [rax+58h]
0x14002165f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021664  jmp     loc_140021782
0x140021669  sub     ecx, 0Ch
0x14002166c  jz      loc_140021769
0x140021672  sub     ecx, 4
0x140021675  jz      loc_140021755
0x14002167b  sub     ecx, 2
0x14002167e  jz      loc_140021739
0x140021684  sub     ecx, 1
0x140021687  jz      loc_14002171C
0x14002168d  sub     ecx, 1
0x140021690  jz      short loc_1400216FB
0x140021692  sub     ecx, 1
0x140021695  jz      short loc_1400216C4
0x140021697  cmp     ecx, 1
0x14002169a  jz      short loc_1400216A3
0x14002169c  xor     esi, esi
0x14002169e  jmp     loc_140021784
0x1400216a3  xor     ebp, ebp
0x1400216a5  mov     rax, [rbx]
0x1400216a8  lea     rdx, [rdi+1Ch]
0x1400216ac  mov     r8d, [rdi+18h]
0x1400216b0  mov     rcx, rbx
0x1400216b3  mov     rax, [rax+0B0h]
0x1400216ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400216bf  jmp     loc_140021782
0x1400216c4  xor     ebp, ebp
0x1400216c6  mov     rax, [rbx]
0x1400216c9  lea     rdx, [rdi+48h]
0x1400216cd  mov     rcx, [rdi+40h]
0x1400216d1  mov     [rsp+78h+var_50], rcx
0x1400216d6  mov     rcx, [rdi+38h]
0x1400216da  mov     [rsp+78h+var_58], rcx
0x1400216df  mov     r9, [rdi+30h]
0x1400216e3  mov     r8, [rdi+28h]
0x1400216e7  mov     rcx, rbx
0x1400216ea  mov     rax, [rax+0A8h]
0x1400216f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400216f6  jmp     loc_140021782
0x1400216fb  xor     ebp, ebp
0x1400216fd  mov     rax, [rbx]
0x140021700  mov     r9, [rdi+38h]
0x140021704  mov     r8, [rdi+30h]
0x140021708  mov     edx, [rdi+28h]
0x14002170b  mov     rcx, rbx
0x14002170e  mov     rax, [rax+0A0h]
0x140021715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002171a  jmp     short loc_140021782
0x14002171c  xor     ebp, ebp
0x14002171e  lea     rdx, [rdi+18h]
0x140021722  mov     rax, [rbx]
0x140021725  mov     r9, [rdx+48h]
0x140021729  mov     r8, [rdi+58h]
0x14002172d  mov     rax, [rax+98h]
0x140021734  jmp     loc_140021641
0x140021739  mov     rax, [rbx]
0x14002173c  mov     r9d, [rdi+20h]
0x140021740  mov     r8d, [rdi+1Ch]
0x140021744  mov     edx, [rdi+18h]
0x140021747  mov     rcx, rbx
0x14002174a  mov     rax, [rax+40h]
0x14002174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021753  jmp     short loc_140021782
0x140021755  lea     rdx, [rdi+18h]
0x140021759  mov     rax, [rbx]
0x14002175c  lea     r8, [rdx+8]
0x140021760  mov     rax, [rax+88h]
0x140021767  jmp     short loc_14002177A
0x140021769  mov     rax, [rbx]
0x14002176c  mov     rax, [rax+80h]
0x140021773  mov     r8, rsi
0x140021776  lea     rdx, [rdi+18h]
0x14002177a  mov     rcx, rbx
0x14002177d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021782  mov     esi, eax
0x140021784  mov     [rsp+78h+arg_0], esi
0x14002178b  xor     r8d, r8d; pftTimeout
0x14002178e  xor     edx, edx; h
0x140021790  mov     rcx, [rbx+60A0h]; pwa
0x140021797  call    cs:__imp_SetThreadpoolWait
0x14002179e  nop     dword ptr [rax+rax+00h]
0x1400217a3  cmp     [rsp+78h+var_30], 0
0x1400217a8  jnz     short loc_1400217AC
0x1400217aa  int     2Ch; Windows NT - assertion failure
0x1400217ac  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1400217b1  call    cs:__imp_LeaveCriticalSection
0x1400217b8  nop     dword ptr [rax+rax+00h]
0x1400217bd  xor     al, al
0x1400217bf  mov     [rsp+78h+var_30], al
0x1400217c3  cmp     qword ptr [rbx+48h], 0
0x1400217c8  jz      short loc_140021807
0x1400217ca  test    ebp, ebp
0x1400217cc  jz      short loc_140021807
0x1400217ce  mov     rax, [rbx]
0x1400217d1  mov     rcx, rbx
0x1400217d4  mov     rax, [rax+8]
0x1400217d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400217dd  lea     r9, [rsp+78h+arg_0]
0x1400217e5  xor     ecx, ecx
0x1400217e7  test    esi, esi
0x1400217e9  cmovnz  r9, rcx; int *
0x1400217ed  mov     r8, rdi; struct _WER_CALLBACK_INPUT *
0x1400217f0  mov     rdx, rax; wchar_t *
0x1400217f3  mov     rcx, [rbx+48h]; void *
0x1400217f7  call    ?WerPluginsInvokeCallback@@YAJPEAXPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z; WerPluginsInvokeCallback(void *,wchar_t const *,_WER_CALLBACK_INPUT *,int *)
0x1400217fc  mov     esi, [rsp+78h+arg_0]
0x140021803  mov     al, [rsp+78h+var_30]
0x140021807  test    al, al
0x140021809  jz      short loc_14002181C
0x14002180b  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x140021810  call    cs:__imp_LeaveCriticalSection
0x140021817  nop     dword ptr [rax+rax+00h]
0x14002181c  mov     eax, esi
0x14002181e  add     rsp, 58h
0x140021822  pop     rdi
0x140021823  pop     rsi
0x140021824  pop     rbp
0x140021825  pop     rbx
0x140021826  retn
```
