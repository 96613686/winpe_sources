# CreateTimer

- ea: `0x180003800`
- end: `0x180003ab2`
- name: `CreateTimer`
- size: `690`
- prototype: `__int64 __fastcall(_QWORD *, void *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180003800`
- `0x180004390`
- `0x180004b80`
- `0x180008ff0`
- `0x180009130`
- `0x18000b6f4`
- `0x18000b734`
- `0x18000c2d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a28`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180003921`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180003921`

## string_xrefs

- `0x18000386b`: `CreateTimer`
- `0x1800038d7`: `CreateTimer`

## pseudocode

```c
__int64 __fastcall CreateTimer(_QWORD *a1, void *a2, __int64 a3, __int64 a4, __int64 a5)
{
  PVOID *v9; // rcx
  unsigned int v10; // esi
  __int64 v11; // r12
  unsigned int LastError; // eax
  _QWORD *v13; // rbx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  PVOID Parameter; // [rsp+78h] [rbp+10h] BYREF

  Parameter = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 || !a1 || (v11 = a5) == 0 || !a3 )
  {
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
      WPP_SF_(v9[2], 21, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids);
    goto LABEL_4;
  }
  *a1 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, a3, a4, v11, a2);
  LastError = AllocateMemory(0x40u, &Parameter, (int)"CreateTimer", 126);
  v10 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_4;
    v16 = 23;
    goto LABEL_26;
  }
  v13 = Parameter;
  if ( !CreateTimerQueueTimer((PHANDLE)Parameter + 6, a2, TimerTimeout, Parameter, 0x7CFFF060u, 0x7FFFFFFFu, 0) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_4;
      v16 = 24;
LABEL_26:
      WPP_SF_d(v15[2], v16, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, LastError);
LABEL_4:
      FreeMemory(&Parameter, "CreateTimer", 161);
      goto LABEL_17;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v13);
  *v13 = a2;
  v13[2] = a3;
  v13[3] = a4;
  v13[4] = v11;
  *((_DWORD *)v13 + 2) = 1;
  v13[5] = 0;
  *((_DWORD *)v13 + 14) = 2097148000;
  *a1 = v13;
  if ( v10 )
    goto LABEL_4;
LABEL_17:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180003800  mov     r11, rsp
0x180003803  sub     rsp, 68h
0x180003807  mov     [r11+18h], rbp
0x18000380b  xor     eax, eax
0x18000380d  mov     [r11-8], rdi
0x180003811  mov     rbp, r8
0x180003814  mov     [r11-18h], r13
0x180003818  mov     rdi, rdx
0x18000381b  mov     [r11-20h], r14
0x18000381f  mov     r14, rcx
0x180003822  mov     [r11-28h], r15
0x180003826  mov     r15, r9
0x180003829  mov     [r11+10h], rax
0x18000382d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003834  lea     r13, WPP_GLOBAL_Control
0x18000383b  cmp     rcx, r13
0x18000383e  jnz     short loc_180003881
0x180003840  mov     [rsp+68h+arg_0], rbx
0x180003845  mov     [rsp+68h+arg_18], rsi
0x18000384d  mov     [rsp+68h+var_10], r12
0x180003852  test    rdi, rdi
0x180003855  jnz     short loc_1800038A7
0x180003857  mov     esi, 57h ; 'W'
0x18000385c  cmp     rcx, r13
0x18000385f  jnz     loc_180003A71
0x180003865  mov     r8d, 0A1h
0x18000386b  lea     rdx, aCreatetimer_0; "CreateTimer"
0x180003872  lea     rcx, [rsp+68h+Parameter]
0x180003877  call    FreeMemory
0x18000387c  jmp     loc_180003975
0x180003881  test    byte ptr [rcx+1Ch], 8
0x180003885  jz      short loc_180003840
0x180003887  mov     rcx, [rcx+10h]
0x18000388b  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003892  mov     edx, 14h
0x180003897  call    WPP_SF_
0x18000389c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038a3  xor     eax, eax
0x1800038a5  jmp     short loc_180003840
0x1800038a7  test    r14, r14
0x1800038aa  jz      short loc_180003857
0x1800038ac  mov     r12, [rsp+68h+arg_20]
0x1800038b4  test    r12, r12
0x1800038b7  jz      short loc_180003857
0x1800038b9  test    rbp, rbp
0x1800038bc  jz      short loc_180003857
0x1800038be  mov     [r14], rax
0x1800038c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038c8  cmp     rcx, r13
0x1800038cb  jnz     loc_1800039C0
0x1800038d1  mov     r9d, 7Eh ; '~'
0x1800038d7  lea     r8, aCreatetimer_0; "CreateTimer"
0x1800038de  lea     rdx, [rsp+68h+Parameter]
0x1800038e3  mov     ecx, 40h ; '@'; dwBytes
0x1800038e8  call    AllocateMemory
0x1800038ed  mov     esi, eax
0x1800038ef  test    eax, eax
0x1800038f1  jnz     loc_1800039EA
0x1800038f7  mov     rbx, [rsp+68h+Parameter]
0x1800038fc  lea     r8, TimerTimeout; Callback
0x180003903  mov     [rsp+68h+Flags], eax; Flags
0x180003907  mov     r9, rbx; Parameter
0x18000390a  mov     [rsp+68h+Period], 7FFFFFFFh; Period
0x180003912  mov     rdx, rdi; TimerQueue
0x180003915  mov     [rsp+68h+DueTime], 7CFFF060h; DueTime
0x18000391d  lea     rcx, [rbx+30h]; phNewTimer
0x180003921  call    cs:__imp_CreateTimerQueueTimer
0x180003927  test    eax, eax
0x180003929  jz      loc_180003A28
0x18000392f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003936  cmp     rcx, r13
0x180003939  jz      short loc_180003945
0x18000393b  test    byte ptr [rcx+1Ch], 2
0x18000393f  jnz     loc_180003A54
0x180003945  mov     [rbx], rdi
0x180003948  mov     [rbx+10h], rbp
0x18000394c  mov     [rbx+18h], r15
0x180003950  mov     [rbx+20h], r12
0x180003954  mov     dword ptr [rbx+8], 1
0x18000395b  mov     qword ptr [rbx+28h], 0
0x180003963  mov     dword ptr [rbx+38h], 7CFFF060h
0x18000396a  mov     [r14], rbx
0x18000396d  test    esi, esi
0x18000396f  jnz     loc_180003865
0x180003975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000397c  mov     r15, [rsp+68h+var_28]
0x180003981  cmp     rcx, r13
0x180003984  mov     r13, [rsp+68h+var_18]
0x180003989  mov     r14, [rsp+68h+var_20]
0x18000398e  mov     r12, [rsp+68h+var_10]
0x180003993  mov     rdi, [rsp+68h+var_8]
0x180003998  mov     rbp, [rsp+68h+arg_10]
0x1800039a0  mov     rbx, [rsp+68h+arg_0]
0x1800039a5  jz      short loc_1800039B1
0x1800039a7  test    byte ptr [rcx+1Ch], 8
0x1800039ab  jnz     loc_180003A95
0x1800039b1  mov     eax, esi
0x1800039b3  mov     rsi, [rsp+68h+arg_18]
0x1800039bb  add     rsp, 68h
0x1800039bf  retn
0x1800039c0  test    byte ptr [rcx+1Ch], 2
0x1800039c4  jz      loc_1800038D1
0x1800039ca  mov     rcx, [rcx+10h]
0x1800039ce  mov     edx, 16h
0x1800039d3  mov     qword ptr [rsp+68h+Period], rdi
0x1800039d8  mov     r9, r15
0x1800039db  mov     qword ptr [rsp+68h+DueTime], r12
0x1800039e0  call    WPP_SF_qqq
0x1800039e5  jmp     loc_1800038D1
0x1800039ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039f1  cmp     rcx, r13
0x1800039f4  jz      loc_180003865
0x1800039fa  test    byte ptr [rcx+1Ch], 4
0x1800039fe  jz      loc_180003865
0x180003a04  mov     edx, 17h
0x180003a09  jmp     short loc_180003A10
0x180003a0b  mov     edx, 18h
0x180003a10  mov     rcx, [rcx+10h]
0x180003a14  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003a1b  mov     r9d, eax
0x180003a1e  call    WPP_SF_d
0x180003a23  jmp     loc_180003865
0x180003a28  call    cs:__imp_GetLastError
0x180003a2e  mov     esi, eax
0x180003a30  test    eax, eax
0x180003a32  jz      loc_18000392F
0x180003a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a3f  cmp     rcx, r13
0x180003a42  jz      loc_180003865
0x180003a48  test    byte ptr [rcx+1Ch], 4
0x180003a4c  jz      loc_180003865
0x180003a52  jmp     short loc_180003A0B
0x180003a54  mov     rcx, [rcx+10h]
0x180003a58  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003a5f  mov     edx, 19h
0x180003a64  mov     r9, rbx
0x180003a67  call    WPP_SF_q
0x180003a6c  jmp     loc_180003945
0x180003a71  test    byte ptr [rcx+1Ch], 4
0x180003a75  jz      loc_180003865
0x180003a7b  mov     rcx, [rcx+10h]
0x180003a7f  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003a86  mov     edx, 15h
0x180003a8b  call    WPP_SF_
0x180003a90  jmp     loc_180003865
0x180003a95  mov     rcx, [rcx+10h]
0x180003a99  lea     r8, WPP_9599c4091a3a35745e1933e7342d0fa7_Traceguids
0x180003aa0  mov     edx, 1Ah
0x180003aa5  mov     r9d, esi
0x180003aa8  call    WPP_SF_L
0x180003aad  jmp     loc_1800039B1
```
