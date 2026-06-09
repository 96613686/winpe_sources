# CTieredVolume::Initialize(CTieringEngineLib *,_GUID const *,ulong,void *)

- ea: `0x1400104f4`
- end: `0x1400106d1`
- name: `?Initialize@CTieredVolume@@QEAAJPEAVCTieringEngineLib@@PEBU_GUID@@KPEAX@Z`
- size: `477`
- prototype: `__int64 __fastcall(char *pv, struct CTieringEngineLib *, const struct _GUID *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000761c`

## callees

- `0x140002323`
- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x1400104f4`
- `0x140017b68`
- `0x140017bbc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400106aa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400106aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010648`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010648`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400105fc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1400105fc`

## pseudocode

```c
__int64 __fastcall CTieredVolume::Initialize(
        char *pv,
        struct CTieringEngineLib *a2,
        const struct _GUID *a3,
        unsigned int a4,
        void *a5)
{
  __int128 v9; // xmm0
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  _BYTE v16[8]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+80h] [rbp+8h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::Initialize";
  CHResultImp::CHResultImp((CHResultImp *)v16);
  memset_0(pv + 208, 0, 0x170u);
  *((_DWORD *)pv + 244) |= 1u;
  *((_DWORD *)pv + 79) = 4096;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DqD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  *((_QWORD *)pv + 95) = a5;
  v9 = (__int128)*a3;
  *((_QWORD *)pv + 94) = a2;
  *((_WORD *)pv + 80) = 0;
  *((_OWORD *)pv + 49) = v9;
  *((_DWORD *)pv + 32) = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 20);
  }
  ThreadpoolWork = CreateThreadpoolWork(CTieredVolume::DumpTimerCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 920));
  v11 = v17;
  *((_QWORD *)pv + 113) = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(CTieredVolume::DumpTimerCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 920));
    *((_QWORD *)pv + 114) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      pftDueTime = 0;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x186A0u);
      v17 = 0;
      v11 = 0;
      goto LABEL_21;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 22;
      goto LABEL_19;
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 21;
LABEL_19:
      WPP_SF_Dd(v12[2], v13, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, a4, v11);
    }
  }
LABEL_21:
  CHResultImp::~CHResultImp((CHResultImp *)v16);
  return v11;
}

```

## disassembly

```asm
0x1400104f4  push    rbx
0x1400104f6  push    rbp
0x1400104f7  push    rsi
0x1400104f8  push    rdi
0x1400104f9  push    r14
0x1400104fb  push    r15
0x1400104fd  sub     rsp, 48h
0x140010501  mov     rax, gs:58h
0x14001050a  mov     rbx, rcx
0x14001050d  mov     ecx, 8
0x140010512  mov     esi, r9d
0x140010515  mov     rdi, r8
0x140010518  mov     r14, rdx
0x14001051b  mov     r10, [rax]
0x14001051e  lea     rax, aCtieredvolumeI_3; "CTieredVolume::Initialize"
0x140010525  mov     [rcx+r10], rax
0x140010529  lea     rcx, [rsp+78h+var_48]; this
0x14001052e  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140010533  lea     rcx, [rbx+0D0h]; void *
0x14001053a  xor     edx, edx; Val
0x14001053c  mov     r8d, 170h; Size
0x140010542  call    memset_0
0x140010547  lea     rbp, [rbx+398h]
0x14001054e  mov     r9d, 1000h
0x140010554  or      dword ptr [rbp+38h], 1
0x140010558  mov     [rbx+13Ch], r9d
0x14001055f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010566  lea     r15, WPP_GLOBAL_Control
0x14001056d  cmp     rcx, r15
0x140010570  jz      short loc_140010590
0x140010572  test    byte ptr [rcx+1Ch], 1
0x140010576  jz      short loc_140010590
0x140010578  cmp     byte ptr [rcx+19h], 4
0x14001057c  jb      short loc_140010590
0x14001057e  mov     rcx, [rcx+10h]
0x140010582  mov     [rsp+78h+var_50], esi
0x140010586  mov     [rsp+78h+var_58], rbx
0x14001058b  call    WPP_SF_DqD
0x140010590  mov     rax, [rsp+78h+arg_20]
0x140010598  mov     [rbx+2F8h], rax
0x14001059f  movups  xmm0, xmmword ptr [rdi]
0x1400105a2  mov     [rbx+2F0h], r14
0x1400105a9  xor     r14d, r14d
0x1400105ac  mov     [rbx+0A0h], r14w
0x1400105b4  movdqu  xmmword ptr [rbx+310h], xmm0
0x1400105bc  mov     [rbx+80h], esi
0x1400105c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105c9  cmp     rcx, r15
0x1400105cc  jz      short loc_1400105EF
0x1400105ce  test    byte ptr [rcx+1Ch], 1
0x1400105d2  jz      short loc_1400105EF
0x1400105d4  cmp     byte ptr [rcx+19h], 4
0x1400105d8  jb      short loc_1400105EF
0x1400105da  mov     rcx, [rcx+10h]
0x1400105de  lea     edx, [r14+14h]
0x1400105e2  mov     r9d, esi
0x1400105e5  mov     [rsp+78h+var_58], rbx
0x1400105ea  call    WPP_SF_Dq
0x1400105ef  mov     r8, rbp; pcbe
0x1400105f2  lea     rcx, ?DumpTimerCallback@CTieredVolume@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnwk
0x1400105f9  mov     rdx, rbx; pv
0x1400105fc  call    cs:__imp_CreateThreadpoolWork
0x140010602  mov     edi, [rsp+78h+var_40]
0x140010606  mov     [rbx+388h], rax
0x14001060d  test    rax, rax
0x140010610  jnz     short loc_14001063B
0x140010612  mov     rcx, cs:WPP_GLOBAL_Control
0x140010619  cmp     rcx, r15
0x14001061c  jz      loc_1400106B8
0x140010622  test    byte ptr [rcx+1Ch], 1
0x140010626  jz      loc_1400106B8
0x14001062c  cmp     byte ptr [rcx+19h], 2
0x140010630  jb      loc_1400106B8
0x140010636  lea     edx, [rax+15h]
0x140010639  jmp     short loc_140010675
0x14001063b  mov     r8, rbp; pcbe
0x14001063e  lea     rcx, ?DumpTimerCallback@CTieredVolume@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140010645  mov     rdx, rbx; pv
0x140010648  call    cs:__imp_CreateThreadpoolTimer
0x14001064e  mov     [rbx+390h], rax
0x140010655  test    rax, rax
0x140010658  jnz     short loc_14001068E
0x14001065a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010661  cmp     rcx, r15
0x140010664  jz      short loc_1400106B8
0x140010666  test    byte ptr [rcx+1Ch], 1
0x14001066a  jz      short loc_1400106B8
0x14001066c  cmp     byte ptr [rcx+19h], 2
0x140010670  jb      short loc_1400106B8
0x140010672  lea     edx, [rax+16h]
0x140010675  mov     rcx, [rcx+10h]
0x140010679  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010680  mov     r9d, esi
0x140010683  mov     dword ptr [rsp+78h+var_58], edi
0x140010687  call    WPP_SF_Dd
0x14001068c  jmp     short loc_1400106B8
0x14001068e  mov     r9d, 186A0h; msWindowLength
0x140010694  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], r14
0x14001069c  xor     r8d, r8d; msPeriod
0x14001069f  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1400106a7  mov     rcx, rax; pti
0x1400106aa  call    cs:__imp_SetThreadpoolTimer
0x1400106b0  mov     [rsp+78h+var_40], r14d
0x1400106b5  mov     edi, r14d
0x1400106b8  lea     rcx, [rsp+78h+var_48]; this
0x1400106bd  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400106c2  mov     eax, edi
0x1400106c4  add     rsp, 48h
0x1400106c8  pop     r15
0x1400106ca  pop     r14
0x1400106cc  pop     rdi
0x1400106cd  pop     rsi
0x1400106ce  pop     rbp
0x1400106cf  pop     rbx
0x1400106d0  retn
```
