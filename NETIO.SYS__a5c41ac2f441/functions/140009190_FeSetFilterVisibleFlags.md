# FeSetFilterVisibleFlags

- ea: `0x140009190`
- end: `0x14000936f`
- name: `FeSetFilterVisibleFlags`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14001b820`
- `0x140047dc0`
- `0x1400617e8`

## callees

- `0x140004970`
- `0x140009190`
- `0x140009520`
- `0x140009770`
- `0x14000c210`
- `0x140038dc8`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400092f5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400092f5`

## string_xrefs

- `0x1400092b2`: `GetLayerFromIdRead`
- `0x14000934e`: `GetLayerFromIdRead`

## pseudocode

```c
__int64 __fastcall FeSetFilterVisibleFlags(unsigned __int16 a1, struct _LIST_ENTRY *a2, int a3)
{
  __int64 IntFilter; // rdi
  volatile signed __int64 *v5; // rbx
  bool v6; // dl
  signed __int64 v7; // rcx
  PVOID P; // [rsp+58h] [rbp+20h] BYREF

  P = 0;
  if ( a1 >= *((_WORD *)&gWfpGlobal[3].L.SingleListHead + 4) )
  {
    IntFilter = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"GetLayerFromIdRead",
        13);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"GetLayerFromIdRead",
        13);
    }
    goto LABEL_15;
  }
  IntFilter = FindIntFilter(a1, a2, (ULONG_PTR *)&P);
  if ( IntFilter )
  {
LABEL_15:
    WfpReportError(IntFilter, "FeSetFilterVisibleFlags");
    return IntFilter;
  }
  v5 = (volatile signed __int64 *)P;
  *((_DWORD *)P + 13) = a3 | *((_DWORD *)P + 13) & 1;
  v6 = 0;
  _InterlockedIncrement64(v5 + 2);
  v7 = _InterlockedExchangeAdd64(v5 + 2, 0xFFFFFFFFFFFFFFFFuLL) - 2;
  if ( (_DWORD)v7 == HIDWORD(v7) )
  {
    _m_prefetchw((char *)v5 + 52);
    v6 = (_InterlockedOr((volatile signed __int32 *)v5 + 13, 0x10u) & 0x10) == 0;
  }
  if ( (*(_DWORD *)(*((_QWORD *)v5 + 3) + 40LL) & 0x4000) == 0 || !v6 )
  {
LABEL_7:
    if ( _InterlockedExchangeAdd64(v5 + 2, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    {
      FreeWFPFilter(v5);
      return 0;
    }
    return IntFilter;
  }
  if ( !KeGetCurrentIrql() )
  {
    FeNotifyIntFilterDelete(v5);
    goto LABEL_7;
  }
  NetioInsertWorkQueue(&gWfpGlobal[10].L.FreeEx);
  return 0;
}

```

## disassembly

```asm
0x140009190  mov     [rsp+arg_0], rbx
0x140009195  mov     [rsp+arg_8], rsi
0x14000919a  push    rdi
0x14000919b  sub     rsp, 30h
0x14000919f  mov     rax, cs:gWfpGlobal
0x1400091a6  mov     esi, r8d
0x1400091a9  mov     [rsp+38h+P], 0
0x1400091b2  cmp     cx, [rax+188h]
0x1400091b9  jnb     loc_14000924C
0x1400091bf  lea     r8, [rsp+38h+P]
0x1400091c4  call    FindIntFilter
0x1400091c9  mov     rdi, rax
0x1400091cc  test    rax, rax
0x1400091cf  jnz     loc_14000928B
0x1400091d5  mov     rbx, [rsp+38h+P]
0x1400091da  mov     ecx, [rbx+34h]
0x1400091dd  and     ecx, 1
0x1400091e0  or      ecx, esi
0x1400091e2  mov     [rbx+34h], ecx
0x1400091e5  xor     dl, dl
0x1400091e7  lock inc qword ptr [rbx+10h]
0x1400091ec  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1400091f3  mov     rcx, rsi
0x1400091f6  lock xadd [rbx+10h], rcx
0x1400091fc  sub     rcx, 2
0x140009200  mov     rax, rcx
0x140009203  shr     rax, 20h
0x140009207  cmp     ecx, eax
0x140009209  jz      loc_1400092D0
0x14000920f  mov     rax, [rbx+18h]
0x140009213  test    dword ptr [rax+28h], 4000h
0x14000921a  jz      short loc_140009224
0x14000921c  test    dl, dl
0x14000921e  jnz     loc_1400092F5
0x140009224  lock xadd [rbx+10h], rsi
0x14000922a  cmp     rsi, 1
0x14000922e  jnz     short loc_14000929A
0x140009230  mov     rcx, rbx; P
0x140009233  call    FreeWFPFilter
0x140009238  mov     rax, rdi
0x14000923b  mov     rbx, [rsp+38h+arg_0]
0x140009240  mov     rsi, [rsp+38h+arg_8]
0x140009245  add     rsp, 30h
0x140009249  pop     rdi
0x14000924a  retn
0x14000924c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009253  lea     rbx, WPP_GLOBAL_Control
0x14000925a  mov     rdi, 0FFFFFFFFC000000Dh
0x140009261  cmp     rcx, rbx
0x140009264  jz      short loc_140009270
0x140009266  cmp     byte ptr [rcx+29h], 2
0x14000926a  jnb     loc_14000933D
0x140009270  mov     rcx, cs:WPP_GLOBAL_Control
0x140009277  cmp     rcx, rbx
0x14000927a  jz      short loc_14000928B
0x14000927c  cmp     byte ptr [rcx+29h], 2
0x140009280  jb      short loc_14000928B
0x140009282  test    dword ptr [rcx+2Ch], 1000h
0x140009289  jnz     short loc_1400092AE
0x14000928b  lea     rdx, aFesetfiltervis; "FeSetFilterVisibleFlags"
0x140009292  mov     rcx, rdi
0x140009295  call    WfpReportError
0x14000929a  mov     rax, rdi
0x14000929d  mov     rbx, [rsp+38h+arg_0]
0x1400092a2  mov     rsi, [rsp+38h+arg_8]
0x1400092a7  add     rsp, 30h
0x1400092ab  pop     rdi
0x1400092ac  retn
0x1400092ae  mov     rcx, [rcx+18h]
0x1400092b2  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x1400092b9  mov     edx, 0Fh
0x1400092be  mov     [rsp+38h+var_18], edi
0x1400092c2  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400092c9  call    WPP_SF_sd
0x1400092ce  jmp     short loc_14000928B
0x1400092d0  prefetchw byte ptr [rbx+34h]
0x1400092d4  mov     eax, [rbx+34h]
0x1400092d7  mov     ecx, eax
0x1400092d9  or      ecx, 10h
0x1400092dc  lock cmpxchg [rbx+34h], ecx
0x1400092e1  jnz     short loc_1400092D7
0x1400092e3  test    al, 10h
0x1400092e5  movzx   edx, dl
0x1400092e8  mov     eax, 1
0x1400092ed  cmovz   edx, eax
0x1400092f0  jmp     loc_14000920F
0x1400092f5  call    cs:__imp_KeGetCurrentIrql
0x1400092fc  nop     dword ptr [rax+rax+00h]
0x140009301  test    al, al
0x140009303  jnz     short loc_140009312
0x140009305  mov     rcx, rbx
0x140009308  call    FeNotifyIntFilterDelete
0x14000930d  jmp     loc_140009224
0x140009312  mov     rcx, cs:gWfpGlobal
0x140009319  lea     rdx, [rbx+28h]
0x14000931d  add     rcx, 538h; Context
0x140009324  call    NetioInsertWorkQueue
0x140009329  mov     rbx, [rsp+38h+arg_0]
0x14000932e  mov     rax, rdi
0x140009331  mov     rsi, [rsp+38h+arg_8]
0x140009336  add     rsp, 30h
0x14000933a  pop     rdi
0x14000933b  retn
0x14000933d  test    dword ptr [rcx+2Ch], 1000h
0x140009344  jz      loc_140009270
0x14000934a  mov     rcx, [rcx+18h]
0x14000934e  lea     r9, aGetlayerfromid_0; "GetLayerFromIdRead"
0x140009355  mov     edx, 0Ah
0x14000935a  mov     [rsp+38h+var_18], edi
0x14000935e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140009365  call    WPP_SF_sd
0x14000936a  jmp     loc_140009270
```
