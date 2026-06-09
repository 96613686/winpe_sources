# CDsmCore::_SetTimer(uint)

- ea: `0x18000e290`
- end: `0x18000e335`
- name: `?_SetTimer@CDsmCore@@AEAAXI@Z`
- size: `165`
- prototype: `void __fastcall(CDsmCore *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f2bc`

## callees

- `0x18000e290`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e2d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e2d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e311`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e311`

## pseudocode

```c
void __fastcall CDsmCore::_SetTimer(CDsmCore *this, unsigned int a2)
{
  struct _TP_TIMER *v4; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 20);
  if ( v4 )
  {
    v5 = -10000000LL * a2;
    SetThreadpoolTimer(v4, (PFILETIME)&v5, 0, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids, a2);
    GetSystemTimeAsFileTime((LPFILETIME)this + 23);
    *((_QWORD *)this + 23) += 10000000LL * a2;
  }
}

```

## disassembly

```asm
0x18000e290  mov     r11, rsp
0x18000e293  mov     [r11+10h], rbx
0x18000e297  mov     [r11+18h], rsi
0x18000e29b  push    rdi
0x18000e29c  sub     rsp, 20h
0x18000e2a0  mov     rbx, rcx
0x18000e2a3  mov     edi, edx
0x18000e2a5  mov     rcx, [rcx+0A0h]; pti
0x18000e2ac  test    rcx, rcx
0x18000e2af  jz      short loc_18000E325
0x18000e2b1  imul    rax, rdi, 0FFFFFFFFFF676980h
0x18000e2b8  xor     r9d, r9d; msWindowLength
0x18000e2bb  lea     rdx, [r11+8]; pftDueTime
0x18000e2bf  mov     r8, rax
0x18000e2c2  mov     esi, edi
0x18000e2c4  shr     r8, 20h
0x18000e2c8  mov     [r11+0Ch], r8d
0x18000e2cc  xor     r8d, r8d; msPeriod
0x18000e2cf  mov     dword ptr [rsp+28h+arg_0], eax
0x18000e2d3  call    cs:__imp_SetThreadpoolTimer
0x18000e2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2e0  lea     rax, WPP_GLOBAL_Control
0x18000e2e7  cmp     rcx, rax
0x18000e2ea  jz      short loc_18000E30A
0x18000e2ec  test    byte ptr [rcx+1Ch], 1
0x18000e2f0  jz      short loc_18000E30A
0x18000e2f2  mov     rcx, [rcx+10h]
0x18000e2f6  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x18000e2fd  mov     edx, 19h
0x18000e302  mov     r9d, edi
0x18000e305  call    WPP_SF_d
0x18000e30a  lea     rcx, [rbx+0B8h]; lpSystemTimeAsFileTime
0x18000e311  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e317  imul    rax, rsi, 989680h
0x18000e31e  add     [rbx+0B8h], rax
0x18000e325  mov     rbx, [rsp+28h+arg_8]
0x18000e32a  mov     rsi, [rsp+28h+arg_10]
0x18000e32f  add     rsp, 20h
0x18000e333  pop     rdi
0x18000e334  retn
```
