# File::PossiblyScheduleTimer(void)

- ea: `0x180033034`
- end: `0x1800330b2`
- name: `?PossiblyScheduleTimer@File@@AEAAXXZ`
- size: `126`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003409c`

## callees

- `0x180033034`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180033056`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180033056`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003309f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003309f`

## pseudocode

```c
void __fastcall File::PossiblyScheduleTimer(_QWORD *pv)
{
  struct _TP_TIMER *v2; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _TP_TIMER *)pv[82];
  if ( v2
    || (ThreadpoolTimer = CreateThreadpoolTimer(File::FlushTimerCallback, pv, 0),
        pv[82] = ThreadpoolTimer,
        (v2 = ThreadpoolTimer) != 0) )
  {
    if ( !*((_BYTE *)pv + 837) )
    {
      pftDueTime = (struct _FILETIME)((-(__int64)(*((_BYTE *)pv + 831) != 0) & 0xFFFFFFFFEE1E5D00uLL) - 300000000);
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0x1Eu);
      *((_BYTE *)pv + 837) = 1;
    }
  }
}

```

## disassembly

```asm
0x180033034  push    rbx
0x180033036  sub     rsp, 20h
0x18003303a  mov     rbx, rcx
0x18003303d  mov     rcx, [rcx+290h]
0x180033044  test    rcx, rcx
0x180033047  jnz     short loc_18003306B
0x180033049  xor     r8d, r8d; pcbe
0x18003304c  lea     rcx, ?FlushTimerCallback@File@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180033053  mov     rdx, rbx; pv
0x180033056  call    cs:__imp_CreateThreadpoolTimer
0x18003305c  mov     [rbx+290h], rax
0x180033063  mov     rcx, rax; pti
0x180033066  test    rax, rax
0x180033069  jz      short loc_1800330AC
0x18003306b  cmp     byte ptr [rbx+345h], 0
0x180033072  jnz     short loc_1800330AC
0x180033074  mov     al, [rbx+33Fh]
0x18003307a  mov     r9d, 1Eh; msWindowLength
0x180033080  neg     al
0x180033082  mov     rax, 0FFFFFFFFEE1E5D00h
0x180033089  sbb     rdx, rdx
0x18003308c  xor     r8d, r8d; msPeriod
0x18003308f  and     rdx, rax
0x180033092  add     rdx, rax
0x180033095  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rdx
0x18003309a  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18003309f  call    cs:__imp_SetThreadpoolTimer
0x1800330a5  mov     byte ptr [rbx+345h], 1
0x1800330ac  add     rsp, 20h
0x1800330b0  pop     rbx
0x1800330b1  retn
```
