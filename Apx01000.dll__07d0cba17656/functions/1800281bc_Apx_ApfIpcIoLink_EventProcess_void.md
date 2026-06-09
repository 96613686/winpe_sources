# Apx::ApfIpcIoLink::EventProcess(void)

- ea: `0x1800281bc`
- end: `0x18002836f`
- name: `?EventProcess@ApfIpcIoLink@Apx@@QEAAXXZ`
- size: `435`
- prototype: `void __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800287c0`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000ba84`
- `0x180011e6c`
- `0x180027754`
- `0x18002812c`
- `0x1800281bc`
- `0x180029118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800282a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002826c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002826c`

## string_xrefs

- `0x1800282fc`: `event operation completed`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::EventProcess(unsigned __int64 this)
{
  _QWORD *v2; // rcx
  _DWORD **v3; // r14
  _DWORD *v4; // rdi
  __int64 v5; // rax
  int v6; // eax
  const struct std::nothrow_t *v7; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  if ( Apx::ApfIpcIoLink::StartOperation((Apx::ApfIpcIoLink *)this) )
  {
    v3 = (_DWORD **)(this + 400);
    do
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
      v4 = *v3;
      if ( *v3 == (_DWORD *)v3 )
      {
        v4 = 0;
      }
      else
      {
        if ( *((_DWORD ***)v4 + 1) != v3 || (v5 = *(_QWORD *)v4, *(_DWORD **)(*(_QWORD *)v4 + 8LL) != v4) )
          __fastfail(3u);
        *v3 = (_DWORD *)v5;
        *(_QWORD *)(v5 + 8) = v3;
        *((_QWORD *)v4 + 1) = v4;
        *(_QWORD *)v4 = v4;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
      if ( !v4 )
        break;
      v6 = Apx::ApfHelper::SyncIoctl(
             *(void **)(this + 112),
             0,
             0x1DC040u,
             v4 + 4,
             v4[4] + v4[11],
             0,
             0,
             0,
             *(void **)(this + 416));
      Apx::ApfIpcIoLink::ApfLogEventResult(
        (Apx::ApfIpcIoLink *)this,
        (struct APF_MESSAGE_EVENT *)(v4 + 4),
        v6,
        "event operation completed");
      operator delete(v4, v7);
    }
    while ( !*(_BYTE *)(this + 432) );
    Apx::ApfIpcIoLink::EndOperation((Apx::ApfIpcIoLink *)this);
    goto LABEL_19;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
      ~this,
      *(_QWORD *)(this + 64),
      -2147467260);
LABEL_19:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 49, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
}

```

## disassembly

```asm
0x1800281bc  push    rbx
0x1800281be  push    rbp
0x1800281bf  push    rsi
0x1800281c0  push    rdi
0x1800281c1  push    r12
0x1800281c3  push    r14
0x1800281c5  sub     rsp, 58h
0x1800281c9  mov     rsi, rcx
0x1800281cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281d3  lea     r12, WPP_GLOBAL_Control
0x1800281da  cmp     rcx, r12
0x1800281dd  jz      short loc_180028200
0x1800281df  test    byte ptr [rcx+1Ch], 1
0x1800281e3  jz      short loc_180028200
0x1800281e5  cmp     byte ptr [rcx+19h], 5
0x1800281e9  jb      short loc_180028200
0x1800281eb  mov     rcx, [rcx+10h]
0x1800281ef  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800281f6  mov     edx, 2Fh ; '/'
0x1800281fb  call    WPP_SF_
0x180028200  mov     rcx, rsi; this
0x180028203  call    ?StartOperation@ApfIpcIoLink@Apx@@AEAA_NXZ; Apx::ApfIpcIoLink::StartOperation(void)
0x180028208  test    al, al
0x18002820a  jnz     short loc_180028261
0x18002820c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028213  cmp     rcx, r12
0x180028216  jz      loc_18002835B
0x18002821c  test    byte ptr [rcx+1Ch], 80h
0x180028220  jz      loc_180028335
0x180028226  cmp     byte ptr [rcx+19h], 4
0x18002822a  jb      loc_180028335
0x180028230  mov     rax, [rsi+40h]
0x180028234  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x18002823b  mov     rcx, [rcx+10h]
0x18002823f  mov     r9, rsi
0x180028242  not     r9
0x180028245  mov     dword ptr [rsp+88h+var_60], 80004004h
0x18002824d  mov     edx, 30h ; '0'
0x180028252  mov     qword ptr [rsp+88h+nInBufferSize], rax
0x180028257  call    WPP_SF_qqd
0x18002825c  jmp     loc_18002832E
0x180028261  lea     r14, [rsi+190h]
0x180028268  lea     rcx, [rsi+10h]; lpCriticalSection
0x18002826c  call    cs:__imp_EnterCriticalSection
0x180028272  mov     rdi, [r14]
0x180028275  cmp     rdi, r14
0x180028278  jnz     short loc_18002827E
0x18002827a  xor     edi, edi
0x18002827c  jmp     short loc_1800282A3
0x18002827e  cmp     [rdi+8], r14
0x180028282  jnz     loc_180028368
0x180028288  mov     rax, [rdi]
0x18002828b  cmp     [rax+8], rdi
0x18002828f  jnz     loc_180028368
0x180028295  mov     [r14], rax
0x180028298  mov     [rax+8], r14
0x18002829c  mov     [rdi+8], rdi
0x1800282a0  mov     [rdi], rdi
0x1800282a3  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800282a7  call    cs:__imp_LeaveCriticalSection
0x1800282ad  test    rdi, rdi
0x1800282b0  jz      short loc_180028326
0x1800282b2  mov     rax, [rsi+1A0h]
0x1800282b9  lea     rbx, [rdi+10h]
0x1800282bd  mov     r8d, [rdi+2Ch]
0x1800282c1  mov     r9, rbx; void *
0x1800282c4  add     r8d, [rbx]
0x1800282c7  xor     edx, edx; unsigned int
0x1800282c9  mov     rcx, [rsi+70h]; void *
0x1800282cd  mov     [rsp+88h+var_48], rax; void *
0x1800282d2  mov     [rsp+88h+lpNumberOfBytesTransferred], 0; lpNumberOfBytesTransferred
0x1800282db  mov     [rsp+88h+var_58], 0; DWORD
0x1800282e3  mov     [rsp+88h+var_60], 0; void *
0x1800282ec  mov     [rsp+88h+nInBufferSize], r8d; nInBufferSize
0x1800282f1  mov     r8d, 1DC040h; unsigned int
0x1800282f7  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x1800282fc  lea     r9, aEventOperation; "event operation completed"
0x180028303  mov     r8d, eax; int
0x180028306  mov     rdx, rbx; struct APF_MESSAGE_EVENT *
0x180028309  mov     rcx, rsi; this
0x18002830c  call    ?ApfLogEventResult@ApfIpcIoLink@Apx@@AEAAXPEAUAPF_MESSAGE_EVENT@@JPEBD@Z; Apx::ApfIpcIoLink::ApfLogEventResult(APF_MESSAGE_EVENT *,long,char const *)
0x180028311  mov     rcx, rdi; void *
0x180028314  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028319  cmp     byte ptr [rsi+1B0h], 0
0x180028320  jz      loc_180028268
0x180028326  mov     rcx, rsi; this
0x180028329  call    ?EndOperation@ApfIpcIoLink@Apx@@AEAAXXZ; Apx::ApfIpcIoLink::EndOperation(void)
0x18002832e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028335  cmp     rcx, r12
0x180028338  jz      short loc_18002835B
0x18002833a  test    byte ptr [rcx+1Ch], 1
0x18002833e  jz      short loc_18002835B
0x180028340  cmp     byte ptr [rcx+19h], 5
0x180028344  jb      short loc_18002835B
0x180028346  mov     rcx, [rcx+10h]
0x18002834a  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028351  mov     edx, 31h ; '1'
0x180028356  call    WPP_SF_
0x18002835b  add     rsp, 58h
0x18002835f  pop     r14
0x180028361  pop     r12
0x180028363  pop     rdi
0x180028364  pop     rsi
0x180028365  pop     rbp
0x180028366  pop     rbx
0x180028367  retn
0x180028368  mov     ecx, 3
0x18002836d  int     29h; Win8: RtlFailFast(ecx)
```
