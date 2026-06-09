# UbpmpRepetitionsStopped

- ea: `0x1800293d0`
- end: `0x180029586`
- name: `UbpmpRepetitionsStopped`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008720`
- `0x180008920`
- `0x18000a940`
- `0x18001af64`
- `0x1800293d0`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800294d2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800294d2`
- `ntdll!RtlAcquireSRWLockShared` at `0x180029414`
- `ntdll!RtlAcquireSRWLockShared` at `0x180029414`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800294a8`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800294a8`

## pseudocode

```c
__int64 __fastcall UbpmpRepetitionsStopped(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // r8
  unsigned __int16 v8; // dx
  unsigned int v9; // r9d
  unsigned int v10; // esi
  unsigned int i; // edi
  __int64 v12; // r14
  __int64 Source1; // [rsp+30h] [rbp-38h] BYREF

  Source1 = a2;
  result = UbpmConsumerIncPendingActions(a3);
  if ( !(_DWORD)result )
  {
    RtlAcquireSRWLockShared(a3 + 48);
    if ( (*(_BYTE *)(a3 + 41) & 1) != 0 )
    {
      v6 = *(_QWORD **)(a3 + 240);
      if ( v6 != (_QWORD *)(a3 + 240) )
      {
        do
        {
          v7 = v6;
          if ( v6[7] == a1 )
            break;
          if ( v6[5] == a1 )
            break;
          v6 = (_QWORD *)*v6;
          v7 = 0;
        }
        while ( v6 != (_QWORD *)(a3 + 240) );
        if ( v7 )
        {
          v8 = 0;
          v9 = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 20LL);
          if ( v9 )
          {
            do
            {
              if ( *(_QWORD *)(*(_QWORD *)(a3 + 32) + 40LL * v8) == v7[4] )
                break;
              ++v8;
            }
            while ( v8 < v9 );
          }
          v10 = v8;
          if ( v8 == v9 )
            __fastfail(0x8000FFFF);
          for ( i = 0; i < 5; ++i )
          {
            v12 = 28LL * i;
            if ( RtlCompareMemory(&Source1, (char *)&g_CSebConditions + v12 + 20, 8u) == 8 )
            {
              UbpmpActionTerminatesOnConstraint(
                (struct _UBPM_TRIGGER_CONSUMER_BLOCK *)a3,
                v10,
                *(_DWORD *)((char *)&g_CSebConditions + v12 + 16));
              break;
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8LL),
        199);
    }
    RtlReleaseSRWLockShared(a3 + 48);
    return UbpmConsumerDecPendingActions(a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800293d0  mov     [rsp+arg_0], rbx
0x1800293d5  mov     [rsp+arg_18], rbp
0x1800293da  push    rsi
0x1800293db  push    rdi
0x1800293dc  push    r12
0x1800293de  push    r14
0x1800293e0  push    r15
0x1800293e2  sub     rsp, 40h
0x1800293e6  mov     rax, cs:__security_cookie
0x1800293ed  xor     rax, rsp
0x1800293f0  mov     [rsp+68h+var_30], rax
0x1800293f5  mov     rdi, rcx
0x1800293f8  mov     [rsp+68h+Source1], rdx
0x1800293fd  mov     rcx, r8
0x180029400  mov     rbx, r8
0x180029403  call    UbpmConsumerIncPendingActions
0x180029408  test    eax, eax
0x18002940a  jnz     loc_1800294E6
0x180029410  lea     rcx, [rbx+30h]
0x180029414  call    cs:__imp_RtlAcquireSRWLockShared
0x18002941b  nop     dword ptr [rax+rax+00h]
0x180029420  mov     r15d, 1
0x180029426  test    [rbx+29h], r15b
0x18002942a  jz      loc_180029538
0x180029430  lea     rcx, [rbx+0F0h]
0x180029437  mov     rax, [rcx]
0x18002943a  cmp     rax, rcx
0x18002943d  jz      loc_1800294CE
0x180029443  mov     r8, rax
0x180029446  cmp     [rax+38h], rdi
0x18002944a  jz      short loc_18002945D
0x18002944c  cmp     [rax+28h], rdi
0x180029450  jz      short loc_18002945D
0x180029452  mov     rax, [rax]
0x180029455  xor     r8d, r8d
0x180029458  cmp     rax, rcx
0x18002945b  jnz     short loc_180029443
0x18002945d  test    r8, r8
0x180029460  jz      short loc_1800294CE
0x180029462  mov     rax, [rbx+18h]
0x180029466  xor     edx, edx
0x180029468  mov     r9d, [rax+14h]
0x18002946c  test    r9d, r9d
0x18002946f  jnz     loc_18002950D
0x180029475  movzx   esi, dx
0x180029478  cmp     esi, r9d
0x18002947b  jz      loc_18002957F
0x180029481  xor     edi, edi
0x180029483  lea     r12, ?g_CSebConditions@@3PAU_UBPM_GLOBAL_STATE_CONDITIONS@@A; _UBPM_GLOBAL_STATE_CONDITIONS near * g_CSebConditions
0x18002948a  cmp     edi, 5
0x18002948d  jnb     short loc_1800294CE
0x18002948f  mov     eax, edi
0x180029491  lea     rdx, [r12+14h]
0x180029496  imul    r14, rax, 1Ch
0x18002949a  mov     r8d, 8; Length
0x1800294a0  lea     rcx, [rsp+68h+Source1]; Source1
0x1800294a5  add     rdx, r14; Source2
0x1800294a8  call    cs:__imp_RtlCompareMemory
0x1800294af  nop     dword ptr [rax+rax+00h]
0x1800294b4  cmp     rax, 8
0x1800294b8  jz      short loc_1800294BF
0x1800294ba  add     edi, r15d
0x1800294bd  jmp     short loc_18002948A
0x1800294bf  mov     r8d, [r14+r12+10h]; unsigned int
0x1800294c4  mov     edx, esi; unsigned int
0x1800294c6  mov     rcx, rbx; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x1800294c9  call    UbpmpActionTerminatesOnConstraint
0x1800294ce  lea     rcx, [rbx+30h]
0x1800294d2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800294d9  nop     dword ptr [rax+rax+00h]
0x1800294de  mov     rcx, rbx
0x1800294e1  call    UbpmConsumerDecPendingActions
0x1800294e6  mov     rcx, [rsp+68h+var_30]
0x1800294eb  xor     rcx, rsp; StackCookie
0x1800294ee  call    __security_check_cookie
0x1800294f3  lea     r11, [rsp+68h+var_28]
0x1800294f8  mov     rbx, [r11+30h]
0x1800294fc  mov     rbp, [r11+48h]
0x180029500  mov     rsp, r11
0x180029503  pop     r15
0x180029505  pop     r14
0x180029507  pop     r12
0x180029509  pop     rdi
0x18002950a  pop     rsi
0x18002950b  retn
0x18002950d  mov     r10, [r8+20h]
0x180029511  mov     r8, [rbx+20h]
0x180029515  movzx   eax, dx
0x180029518  lea     rcx, [rax+rax*4]
0x18002951c  cmp     [r8+rcx*8], r10
0x180029520  jz      loc_180029475
0x180029526  add     dx, r15w
0x18002952a  movzx   eax, dx
0x18002952d  cmp     eax, r9d
0x180029530  jnb     loc_180029475
0x180029536  jmp     short loc_180029515
0x180029538  mov     rcx, cs:WPP_GLOBAL_Control
0x18002953f  lea     rax, WPP_GLOBAL_Control
0x180029546  cmp     rcx, rax
0x180029549  jz      short loc_1800294CE
0x18002954b  test    [rcx+1Ch], r15b
0x18002954f  jz      loc_1800294CE
0x180029555  mov     r9, [rbx+18h]
0x180029559  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x180029560  mov     rcx, [rcx+10h]
0x180029564  mov     edx, 3Ch ; '<'
0x180029569  mov     [rsp+68h+var_48], 4C7h
0x180029571  mov     r9, [r9+8]
0x180029575  call    WPP_SF_Sd
0x18002957a  jmp     loc_1800294CE
0x18002957f  mov     ecx, 8000FFFFh
0x180029584  int     29h; Win8: RtlFailFast(ecx)
```
