# CHangReport::WerCallback(_WER_CALLBACK_INPUT * const)

- ea: `0x14001ff40`
- end: `0x14002025f`
- name: `?WerCallback@CHangReport@@AEAAHQEAU_WER_CALLBACK_INPUT@@@Z`
- size: `799`
- prototype: `__int64 __fastcall(CHangReport *__hidden this, struct _WER_CALLBACK_INPUT *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001fae0`

## callees

- `0x14001f200`
- `0x14001ff40`
- `0x14002152c`
- `0x140046708`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400201f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002024e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400201f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002024e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ff7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400201e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001ff7e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400201e1`

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
0x14001ff40  push    rbx
0x14001ff42  push    rbp
0x14001ff43  push    rsi
0x14001ff44  push    rdi
0x14001ff45  sub     rsp, 58h
0x14001ff49  mov     rdi, rdx
0x14001ff4c  mov     rbx, rcx
0x14001ff4f  mov     ebp, 1
0x14001ff54  xor     esi, esi
0x14001ff56  lea     r8, aChangreportWer; "CHangReport::WerCallback"
0x14001ff5d  lea     rdx, [rsp+78h+lpCriticalSection]
0x14001ff62  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001ff67  nop
0x14001ff68  cmp     [rbx+3Ch], esi
0x14001ff6b  jnz     short loc_14001FF84
0x14001ff6d  mov     rsi, [rdi+10h]
0x14001ff71  xor     r8d, r8d; pftTimeout
0x14001ff74  mov     rdx, rsi; h
0x14001ff77  mov     rcx, [rbx+60A0h]; pwa
0x14001ff7e  call    cs:__imp_SetThreadpoolWait
0x14001ff84  mov     ecx, [rdi+8]
0x14001ff87  cmp     ecx, 0Bh
0x14001ff8a  jg      loc_1400200B3
0x14001ff90  jz      loc_140020098
0x14001ff96  sub     ecx, 1
0x14001ff99  jz      loc_140020078
0x14001ff9f  sub     ecx, 1
0x14001ffa2  jz      loc_14002004F
0x14001ffa8  sub     ecx, 3
0x14001ffab  jz      loc_14002003D
0x14001ffb1  sub     ecx, 1
0x14001ffb4  jz      short loc_14002001E
0x14001ffb6  sub     ecx, 1
0x14001ffb9  jz      short loc_14002000A
0x14001ffbb  sub     ecx, 1
0x14001ffbe  jz      short loc_14001FFF2
0x14001ffc0  sub     ecx, 1
0x14001ffc3  jz      short loc_14001FFE6
0x14001ffc5  cmp     ecx, 1
0x14001ffc8  jnz     loc_1400200E6
0x14001ffce  mov     rax, [rbx]
0x14001ffd1  mov     rdx, [rdi+18h]
0x14001ffd5  mov     rax, [rax+50h]
0x14001ffd9  mov     rcx, rbx
0x14001ffdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ffe1  jmp     loc_1400201CC
0x14001ffe6  mov     rax, [rbx]
0x14001ffe9  mov     rax, [rax+78h]
0x14001ffed  jmp     loc_1400201BD
0x14001fff2  mov     rdx, rsi; void *
0x14001fff5  mov     rcx, rbx; this
0x14001fff8  call    ?_CheckIfCanceled@CHangReport@@IEAAHPEAX@Z; CHangReport::_CheckIfCanceled(void *)
0x14001fffd  xor     esi, esi
0x14001ffff  test    eax, eax
0x140020001  setz    sil
0x140020005  jmp     loc_1400201CE
0x14002000a  mov     rax, [rbx]
0x14002000d  mov     rcx, rbx
0x140020010  mov     rax, [rax+48h]
0x140020014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020019  jmp     loc_1400201CC
0x14002001e  mov     rax, [rbx]
0x140020021  lea     rdx, [rdi+1Ch]
0x140020025  mov     r9, rsi
0x140020028  mov     r8d, [rdi+18h]
0x14002002c  mov     rcx, rbx
0x14002002f  mov     rax, [rax+70h]
0x140020033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020038  jmp     loc_1400201CC
0x14002003d  xor     ebp, ebp
0x14002003f  mov     rax, [rbx]
0x140020042  lea     rdx, [rdi+1Ch]
0x140020046  mov     rax, [rax+90h]
0x14002004d  jmp     short loc_14001FFD9
0x14002004f  mov     rax, [rbx]
0x140020052  mov     rcx, [rdi+20h]
0x140020056  mov     [rsp+78h+var_58], rcx
0x14002005b  mov     r9, [rdi+18h]
0x14002005f  mov     r8, rsi
0x140020062  lea     rdx, [rsp+78h+lpCriticalSection]
0x140020067  mov     rcx, rbx
0x14002006a  mov     rax, [rax+68h]
0x14002006e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020073  jmp     loc_1400201CC
0x140020078  mov     rax, [rbx]
0x14002007b  mov     r9, [rdi+28h]
0x14002007f  mov     r8, [rdi+20h]
0x140020083  mov     rdx, [rdi+18h]
0x140020087  mov     rax, [rax+60h]
0x14002008b  mov     rcx, rbx
0x14002008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020093  jmp     loc_1400201CC
0x140020098  mov     rax, [rbx]
0x14002009b  mov     r8d, [rdi+1Ch]
0x14002009f  mov     edx, [rdi+18h]
0x1400200a2  mov     rcx, rbx
0x1400200a5  mov     rax, [rax+58h]
0x1400200a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200ae  jmp     loc_1400201CC
0x1400200b3  sub     ecx, 0Ch
0x1400200b6  jz      loc_1400201B3
0x1400200bc  sub     ecx, 4
0x1400200bf  jz      loc_14002019F
0x1400200c5  sub     ecx, 2
0x1400200c8  jz      loc_140020183
0x1400200ce  sub     ecx, 1
0x1400200d1  jz      loc_140020166
0x1400200d7  sub     ecx, 1
0x1400200da  jz      short loc_140020145
0x1400200dc  sub     ecx, 1
0x1400200df  jz      short loc_14002010E
0x1400200e1  cmp     ecx, 1
0x1400200e4  jz      short loc_1400200ED
0x1400200e6  xor     esi, esi
0x1400200e8  jmp     loc_1400201CE
0x1400200ed  xor     ebp, ebp
0x1400200ef  mov     rax, [rbx]
0x1400200f2  lea     rdx, [rdi+1Ch]
0x1400200f6  mov     r8d, [rdi+18h]
0x1400200fa  mov     rcx, rbx
0x1400200fd  mov     rax, [rax+0B0h]
0x140020104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020109  jmp     loc_1400201CC
0x14002010e  xor     ebp, ebp
0x140020110  mov     rax, [rbx]
0x140020113  lea     rdx, [rdi+48h]
0x140020117  mov     rcx, [rdi+40h]
0x14002011b  mov     [rsp+78h+var_50], rcx
0x140020120  mov     rcx, [rdi+38h]
0x140020124  mov     [rsp+78h+var_58], rcx
0x140020129  mov     r9, [rdi+30h]
0x14002012d  mov     r8, [rdi+28h]
0x140020131  mov     rcx, rbx
0x140020134  mov     rax, [rax+0A8h]
0x14002013b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020140  jmp     loc_1400201CC
0x140020145  xor     ebp, ebp
0x140020147  mov     rax, [rbx]
0x14002014a  mov     r9, [rdi+38h]
0x14002014e  mov     r8, [rdi+30h]
0x140020152  mov     edx, [rdi+28h]
0x140020155  mov     rcx, rbx
0x140020158  mov     rax, [rax+0A0h]
0x14002015f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020164  jmp     short loc_1400201CC
0x140020166  xor     ebp, ebp
0x140020168  lea     rdx, [rdi+18h]
0x14002016c  mov     rax, [rbx]
0x14002016f  mov     r9, [rdx+48h]
0x140020173  mov     r8, [rdi+58h]
0x140020177  mov     rax, [rax+98h]
0x14002017e  jmp     loc_14002008B
0x140020183  mov     rax, [rbx]
0x140020186  mov     r9d, [rdi+20h]
0x14002018a  mov     r8d, [rdi+1Ch]
0x14002018e  mov     edx, [rdi+18h]
0x140020191  mov     rcx, rbx
0x140020194  mov     rax, [rax+40h]
0x140020198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002019d  jmp     short loc_1400201CC
0x14002019f  lea     rdx, [rdi+18h]
0x1400201a3  mov     rax, [rbx]
0x1400201a6  lea     r8, [rdx+8]
0x1400201aa  mov     rax, [rax+88h]
0x1400201b1  jmp     short loc_1400201C4
0x1400201b3  mov     rax, [rbx]
0x1400201b6  mov     rax, [rax+80h]
0x1400201bd  mov     r8, rsi
0x1400201c0  lea     rdx, [rdi+18h]
0x1400201c4  mov     rcx, rbx
0x1400201c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400201cc  mov     esi, eax
0x1400201ce  mov     [rsp+78h+arg_0], esi
0x1400201d5  xor     r8d, r8d; pftTimeout
0x1400201d8  xor     edx, edx; h
0x1400201da  mov     rcx, [rbx+60A0h]; pwa
0x1400201e1  call    cs:__imp_SetThreadpoolWait
0x1400201e7  cmp     [rsp+78h+var_30], 0
0x1400201ec  jnz     short loc_1400201F0
0x1400201ee  int     2Ch; Windows NT - assertion failure
0x1400201f0  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1400201f5  call    cs:__imp_LeaveCriticalSection
0x1400201fb  xor     al, al
0x1400201fd  mov     [rsp+78h+var_30], al
0x140020201  cmp     qword ptr [rbx+48h], 0
0x140020206  jz      short loc_140020245
0x140020208  test    ebp, ebp
0x14002020a  jz      short loc_140020245
0x14002020c  mov     rax, [rbx]
0x14002020f  mov     rcx, rbx
0x140020212  mov     rax, [rax+8]
0x140020216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002021b  lea     r9, [rsp+78h+arg_0]
0x140020223  xor     ecx, ecx
0x140020225  test    esi, esi
0x140020227  cmovnz  r9, rcx; int *
0x14002022b  mov     r8, rdi; struct _WER_CALLBACK_INPUT *
0x14002022e  mov     rdx, rax; wchar_t *
0x140020231  mov     rcx, [rbx+48h]; void *
0x140020235  call    ?WerPluginsInvokeCallback@@YAJPEAXPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z; WerPluginsInvokeCallback(void *,wchar_t const *,_WER_CALLBACK_INPUT *,int *)
0x14002023a  mov     esi, [rsp+78h+arg_0]
0x140020241  mov     al, [rsp+78h+var_30]
0x140020245  test    al, al
0x140020247  jz      short loc_140020254
0x140020249  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x14002024e  call    cs:__imp_LeaveCriticalSection
0x140020254  mov     eax, esi
0x140020256  add     rsp, 58h
0x14002025a  pop     rdi
0x14002025b  pop     rsi
0x14002025c  pop     rbp
0x14002025d  pop     rbx
0x14002025e  retn
```
