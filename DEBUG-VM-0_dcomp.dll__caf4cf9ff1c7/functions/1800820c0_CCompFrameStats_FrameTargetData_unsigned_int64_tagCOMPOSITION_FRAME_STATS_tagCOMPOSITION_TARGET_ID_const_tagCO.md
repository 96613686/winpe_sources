# CCompFrameStats::FrameTargetData(unsigned __int64,tagCOMPOSITION_FRAME_STATS *,tagCOMPOSITION_TARGET_ID const *,tagCOMPOSITION_TARGET_STATS *)

- ea: `0x1800820c0`
- end: `0x18008223a`
- name: `?FrameTargetData@CCompFrameStats@@UEBA_N_KPEAUtagCOMPOSITION_FRAME_STATS@@PEBUtagCOMPOSITION_TARGET_ID@@PEAUtagCOMPOSITION_TARGET_STATS@@@Z`
- size: `378`
- prototype: `bool __fastcall(CCompFrameStats *__hidden this, unsigned __int64, struct tagCOMPOSITION_FRAME_STATS *, const struct tagCOMPOSITION_TARGET_ID *, struct tagCOMPOSITION_TARGET_STATS *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180081f30`
- `0x1800dc770`
- `0x1801768c0`
- `0x180176970`
- `0x180176e90`

## callees

- `0x1800820c0`
- `0x180082240`
- `0x180082500`
- `0x1800827d0`
- `0x1800f6f10`
- `0x1800f7a80`

## import_xrefs

- `win32u!NtDCompositionGetStatistics` at `0x18008221d`
- `win32u!NtDCompositionGetStatistics` at `0x18008221d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082158`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082158`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082123`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082123`

## pseudocode

```c
char __fastcall CCompFrameStats::FrameTargetData(
        CCompFrameStats *this,
        struct tagCOMPOSITION_FRAME_STATS *a2,
        struct tagCOMPOSITION_FRAME_STATS *a3,
        const struct tagCOMPOSITION_TARGET_ID *a4,
        struct tagCOMPOSITION_TARGET_STATS *a5)
{
  bool v6; // bl
  char v9; // r14
  char v10; // r12
  __int64 v11; // r8
  __int64 v12; // r9
  struct tagCOMPOSITION_FRAME_STATS *v13; // r10
  int Statistics; // eax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  struct tagCOMPOSITION_FRAME_STATS *v19; // [rsp+30h] [rbp-B8h] BYREF
  _OWORD v20[4]; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+80h] [rbp-68h]

  v6 = a4 == 0;
  v19 = a3;
  v9 = 1;
  if ( (unsigned __int64)a2 >= *((_QWORD *)this + 14) && (unsigned __int64)a2 <= *((_QWORD *)this + 15) )
  {
    v10 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v11 = *((_QWORD *)this + 17);
    v12 = *((_QWORD *)this + 18);
    if ( v11 != v12 )
    {
      v13 = v19;
      do
      {
        if ( a2 == *(struct tagCOMPOSITION_FRAME_STATS **)v11 )
        {
          v10 = 1;
          *(_OWORD *)v13 = *(_OWORD *)(v11 + 8);
          *((_QWORD *)v13 + 2) = *(_QWORD *)(v11 + 24);
          if ( a4 && (unsigned __int8)tagCOMPOSITION_TARGET_ID::operator==(a4, v11 + 32) )
          {
            if ( a5 )
            {
              *(_OWORD *)a5 = *(_OWORD *)(v11 + 64);
              *((_OWORD *)a5 + 1) = *(_OWORD *)(v11 + 80);
              *((_OWORD *)a5 + 2) = *(_OWORD *)(v11 + 96);
              *((_OWORD *)a5 + 3) = *(_OWORD *)(v11 + 112);
              *((_QWORD *)a5 + 8) = *(_QWORD *)(v11 + 128);
            }
            v6 = 1;
          }
        }
        else if ( (unsigned __int64)a2 < *(_QWORD *)v11 )
        {
          break;
        }
        v11 += 136;
      }
      while ( v11 != v12 );
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    if ( !v10 )
      return 0;
    goto LABEL_9;
  }
  v19 = a2;
  Statistics = NtDCompositionGetStatistics(&v19, a3, 0, 0, 0);
  if ( (int)DirectComposition::CDevice::HRESULTFromNTSTATUS(Statistics) < 0 )
    return 0;
  if ( !a4 || (memset_0(v20, 0, 0x48u), (int)DCompositionGetTargetStatistics(a2, a4, v20) < 0) )
  {
LABEL_9:
    if ( v6 )
      return v9;
    return 0;
  }
  if ( a5 )
  {
    v16 = v20[1];
    *(_OWORD *)a5 = v20[0];
    v17 = v20[2];
    *((_OWORD *)a5 + 1) = v16;
    v18 = v20[3];
    *((_OWORD *)a5 + 2) = v17;
    *(_QWORD *)&v17 = v21;
    *((_OWORD *)a5 + 3) = v18;
    *((_QWORD *)a5 + 8) = v17;
  }
  return v9;
}

```

## disassembly

```asm
0x1800820c0  push    rbx
0x1800820c2  push    rbp
0x1800820c3  push    rsi
0x1800820c4  push    rdi
0x1800820c5  push    r12
0x1800820c7  push    r13
0x1800820c9  push    r14
0x1800820cb  push    r15
0x1800820cd  sub     rsp, 0A8h
0x1800820d4  mov     rax, cs:__security_cookie
0x1800820db  xor     rax, rsp
0x1800820de  mov     [rsp+0E8h+var_58], rax
0x1800820e6  mov     rdi, [rsp+0E8h+arg_20]
0x1800820ee  test    r9, r9
0x1800820f1  mov     rax, r8
0x1800820f4  mov     r15, r9
0x1800820f7  setz    bl
0x1800820fa  mov     [rsp+0E8h+var_B8], rax
0x1800820ff  mov     rbp, rdx
0x180082102  mov     rsi, rcx
0x180082105  mov     r14b, 1
0x180082108  cmp     rdx, [rcx+70h]
0x18008210c  jb      loc_180082201
0x180082112  cmp     rdx, [rcx+78h]
0x180082116  ja      loc_180082201
0x18008211c  add     rcx, 48h ; 'H'; lpCriticalSection
0x180082120  xor     r12b, r12b
0x180082123  call    cs:__imp_EnterCriticalSection
0x180082129  mov     r8, [rsi+88h]
0x180082130  mov     r9, [rsi+90h]
0x180082137  cmp     r8, r9
0x18008213a  jz      short loc_180082154
0x18008213c  mov     r10, [rsp+0E8h+var_B8]
0x180082141  cmp     rbp, [r8]
0x180082144  jz      short loc_180082196
0x180082146  jb      short loc_180082154
0x180082148  add     r8, 88h
0x18008214f  cmp     r8, r9
0x180082152  jnz     short loc_180082141
0x180082154  lea     rcx, [rsi+48h]; lpCriticalSection
0x180082158  call    cs:__imp_LeaveCriticalSection
0x18008215e  test    r12b, r12b
0x180082161  jz      loc_180082232
0x180082167  test    bl, bl
0x180082169  jz      loc_180082232
0x18008216f  mov     al, r14b
0x180082172  mov     rcx, [rsp+0E8h+var_58]
0x18008217a  xor     rcx, rsp; StackCookie
0x18008217d  call    __security_check_cookie
0x180082182  add     rsp, 0A8h
0x180082189  pop     r15
0x18008218b  pop     r14
0x18008218d  pop     r13
0x18008218f  pop     r12
0x180082191  pop     rdi
0x180082192  pop     rsi
0x180082193  pop     rbp
0x180082194  pop     rbx
0x180082195  retn
0x180082196  mov     r12b, r14b
0x180082199  movups  xmm0, xmmword ptr [r8+8]
0x18008219e  movups  xmmword ptr [r10], xmm0
0x1800821a2  movsd   xmm1, qword ptr [r8+18h]
0x1800821a8  movsd   qword ptr [r10+10h], xmm1
0x1800821ae  test    r15, r15
0x1800821b1  jz      short loc_180082148
0x1800821b3  lea     rdx, [r8+20h]
0x1800821b7  mov     rcx, r15
0x1800821ba  call    ??8tagCOMPOSITION_TARGET_ID@@QEBA_NAEBU0@@Z; tagCOMPOSITION_TARGET_ID::operator==(tagCOMPOSITION_TARGET_ID const &)
0x1800821bf  test    al, al
0x1800821c1  jz      short loc_180082148
0x1800821c3  test    rdi, rdi
0x1800821c6  jz      short loc_1800821F9
0x1800821c8  movups  xmm0, xmmword ptr [r8+40h]
0x1800821cd  movups  xmmword ptr [rdi], xmm0
0x1800821d0  movups  xmm1, xmmword ptr [r8+50h]
0x1800821d5  movups  xmmword ptr [rdi+10h], xmm1
0x1800821d9  movups  xmm0, xmmword ptr [r8+60h]
0x1800821de  movups  xmmword ptr [rdi+20h], xmm0
0x1800821e2  movups  xmm1, xmmword ptr [r8+70h]
0x1800821e7  movups  xmmword ptr [rdi+30h], xmm1
0x1800821eb  movsd   xmm0, qword ptr [r8+80h]
0x1800821f4  movsd   qword ptr [rdi+40h], xmm0
0x1800821f9  mov     bl, r14b
0x1800821fc  jmp     loc_180082148
0x180082201  xor     r9d, r9d
0x180082204  mov     [rsp+0E8h+var_B8], rbp
0x180082209  xor     r8d, r8d
0x18008220c  mov     [rsp+0E8h+var_C8], 0
0x180082215  mov     rdx, rax
0x180082218  lea     rcx, [rsp+0E8h+var_B8]
0x18008221d  call    cs:__imp_NtDCompositionGetStatistics
0x180082223  mov     ecx, eax; int
0x180082225  call    ?HRESULTFromNTSTATUS@CDevice@DirectComposition@@SAJJ@Z; DirectComposition::CDevice::HRESULTFromNTSTATUS(long)
0x18008222a  test    eax, eax
0x18008222c  jns     loc_18017FADA
0x180082232  xor     r14b, r14b
0x180082235  jmp     loc_18008216F
0x18017fada  test    r15, r15
0x18017fadd  jz      loc_180082167
0x18017fae3  xor     edx, edx; Val
0x18017fae5  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18017faea  lea     r8d, [rdx+48h]; Size
0x18017faee  call    memset_0
0x18017faf3  lea     r8, [rsp+0E8h+var_A8]
0x18017faf8  mov     rdx, r15
0x18017fafb  mov     rcx, rbp
0x18017fafe  call    DCompositionGetTargetStatistics
0x18017fb03  test    eax, eax
0x18017fb05  js      loc_180082167
0x18017fb0b  test    rdi, rdi
0x18017fb0e  jz      loc_18008216F
0x18017fb14  movaps  xmm0, [rsp+0E8h+var_A8]
0x18017fb19  movaps  xmm1, [rsp+0E8h+var_98]
0x18017fb1e  movups  xmmword ptr [rdi], xmm0
0x18017fb21  movaps  xmm0, [rsp+0E8h+var_88]
0x18017fb26  movups  xmmword ptr [rdi+10h], xmm1
0x18017fb2a  movaps  xmm1, [rsp+0E8h+var_78]
0x18017fb2f  movups  xmmword ptr [rdi+20h], xmm0
0x18017fb33  movsd   xmm0, [rsp+0E8h+var_68]
0x18017fb3c  movups  xmmword ptr [rdi+30h], xmm1
0x18017fb40  movsd   qword ptr [rdi+40h], xmm0
0x18017fb45  jmp     loc_18008216F
```
