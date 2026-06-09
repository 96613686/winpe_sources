# BfpCreateTargetEntry

- ea: `0x14001caf8`
- end: `0x14001cd7c`
- name: `BfpCreateTargetEntry`
- size: `644`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140019c44`

## callees

- `0x140001348`
- `0x140003f70`
- `0x140004cc0`
- `0x14001caf8`
- `0x14001d130`
- `0x14001ea10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001cb27`
- `ntoskrnl!ExAllocatePool2` at `0x14001cb27`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ccf7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001ccf7`
- `FLTMGR!FltReferenceContext` at `0x14001cb5b`
- `FLTMGR!FltReferenceContext` at `0x14001cb5b`
- `FLTMGR!FltObjectReference` at `0x14001cb42`
- `FLTMGR!FltObjectReference` at `0x14001cb42`

## pseudocode

```c
__int64 __fastcall BfpCreateTargetEntry(PVOID *Context, _WORD *a2, __int64 *a3)
{
  __int64 Pool2; // rbx
  int v6; // edx
  NTSTATUS UnicodeString; // edi
  __int16 v8; // r12
  _WORD *v9; // r15
  unsigned __int16 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // rcx
  size_t v13; // r8
  int v14; // r9d
  __int64 v15; // rdx
  unsigned int v16; // r8d
  unsigned __int64 v17; // rax
  int v19; // r9d
  int v20; // ecx
  char v21; // [rsp+30h] [rbp-48h]
  NTSTATUS v22; // [rsp+38h] [rbp-40h]

  Pool2 = ExAllocatePool2(256, 56, 1886209602);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  UnicodeString = FltObjectReference(*Context);
  if ( UnicodeString < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_16;
    v19 = 15;
    v22 = UnicodeString;
    v21 = -65;
    goto LABEL_21;
  }
  FltReferenceContext(Context);
  *(_QWORD *)(Pool2 + 16) = Context;
  v8 = a2[3];
  v9 = (_WORD *)(Pool2 + 24);
  v10 = a2[1];
  v11 = (unsigned __int16)a2[2];
  if ( v8 != 92 )
  {
    v10 += 8;
    LOWORD(v11) = v11 + 8;
  }
  UnicodeString = BfAllocateUnicodeString(v11, Pool2 + 24);
  if ( UnicodeString < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_16:
      BfpDeleteTargetEntry((PVOID)Pool2);
      return (unsigned int)UnicodeString;
    }
    v22 = UnicodeString;
    v19 = 16;
    v21 = -40;
LABEL_21:
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      8,
      v19,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v21,
      v22);
    goto LABEL_16;
  }
  if ( v8 != 92 )
    RtlAppendUnicodeStringToString((PUNICODE_STRING)(Pool2 + 24), &g_ntNamePrefix);
  *v9 += a2[2];
  *(_WORD *)(Pool2 + 26) += a2[2];
  v12 = *(_QWORD *)(Pool2 + 32);
  v13 = (unsigned __int16)a2[2];
  if ( v8 == 92 )
  {
    memmove((void *)v12, a2 + 3, v13);
    if ( a2[4] == 92 && a2[5] == 63 )
      *(_WORD *)(*(_QWORD *)(Pool2 + 32) + 2LL) = 63;
  }
  else
  {
    memmove((void *)(v12 + 8), a2 + 3, v13);
  }
  v15 = *(_QWORD *)(Pool2 + 32) + v10;
  v16 = (unsigned __int16)(*v9 - v10);
  v17 = (unsigned __int16)(*v9 - v10);
  *(_WORD *)(Pool2 + 40) = v16;
  *(_WORD *)(Pool2 + 42) = v16;
  *(_QWORD *)(Pool2 + 48) = v15;
  if ( *(_WORD *)(v15 + 2 * (v17 >> 1) - 2) != 92 )
    goto LABEL_13;
  v20 = *((_DWORD *)Context + 6);
  if ( v20 == 6 || v20 == 13 )
  {
    if ( v16 > 2 )
      *(_WORD *)(Pool2 + 40) = v16 - 2;
  }
  else if ( v16 > 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sDL(WPP_GLOBAL_Control->DeviceExtension, v15, v16, v14);
    UnicodeString = -1073741811;
    goto LABEL_16;
  }
LABEL_13:
  UnicodeString = 0;
  *a3 = Pool2;
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x14001caf8  mov     [rsp+arg_0], rbx
0x14001cafd  mov     [rsp+arg_10], r8
0x14001cb02  push    rbp
0x14001cb03  push    rsi
0x14001cb04  push    rdi
0x14001cb05  push    r12
0x14001cb07  push    r13
0x14001cb09  push    r14
0x14001cb0b  push    r15
0x14001cb0d  sub     rsp, 40h
0x14001cb11  mov     rsi, rdx
0x14001cb14  mov     r14, rcx
0x14001cb17  mov     edx, 38h ; '8'
0x14001cb1c  mov     ecx, 100h
0x14001cb21  mov     r8d, 706D4642h
0x14001cb27  call    cs:__imp_ExAllocatePool2
0x14001cb2e  nop     dword ptr [rax+rax+00h]
0x14001cb33  mov     rbx, rax
0x14001cb36  test    rax, rax
0x14001cb39  jz      loc_14001CC7D
0x14001cb3f  mov     rcx, [r14]; FltObject
0x14001cb42  call    cs:__imp_FltObjectReference
0x14001cb49  nop     dword ptr [rax+rax+00h]
0x14001cb4e  mov     edi, eax
0x14001cb50  test    eax, eax
0x14001cb52  js      loc_14001CC84
0x14001cb58  mov     rcx, r14; Context
0x14001cb5b  call    cs:__imp_FltReferenceContext
0x14001cb62  nop     dword ptr [rax+rax+00h]
0x14001cb67  lea     rax, [rsi+6]
0x14001cb6b  mov     [rbx+10h], r14
0x14001cb6f  movzx   r12d, word ptr [rax]
0x14001cb73  lea     r15, [rbx+18h]
0x14001cb77  movzx   r13d, word ptr [rsi+2]
0x14001cb7c  mov     ebp, 8
0x14001cb81  movzx   ecx, word ptr [rsi+4]
0x14001cb85  mov     rdx, r15
0x14001cb88  mov     [rsp+78h+Src], rax
0x14001cb90  mov     eax, ebp
0x14001cb92  add     eax, r13d
0x14001cb95  cmp     r12w, 5Ch ; '\'
0x14001cb9a  cmovnz  r13w, ax
0x14001cb9f  lea     eax, [rcx+rbp]
0x14001cba2  cmovnz  cx, ax
0x14001cba6  call    BfAllocateUnicodeString
0x14001cbab  mov     edi, eax
0x14001cbad  test    eax, eax
0x14001cbaf  js      loc_14001CC63
0x14001cbb5  mov     di, 5Ch ; '\'
0x14001cbb9  cmp     r12w, di
0x14001cbbd  jnz     loc_14001CCED
0x14001cbc3  movzx   eax, word ptr [rsi+4]
0x14001cbc7  add     [r15], ax
0x14001cbcb  movzx   eax, word ptr [rsi+4]
0x14001cbcf  add     [rbx+1Ah], ax
0x14001cbd3  mov     rcx, [rbx+20h]; void *
0x14001cbd7  movzx   r8d, word ptr [rsi+4]; Size
0x14001cbdc  cmp     r12w, di
0x14001cbe0  jnz     loc_14001CD08
0x14001cbe6  lea     rdx, [rsi+6]; Src
0x14001cbea  call    memmove
0x14001cbef  cmp     [rsi+8], di
0x14001cbf3  jnz     short loc_14001CC08
0x14001cbf5  mov     ecx, 3Fh ; '?'
0x14001cbfa  cmp     [rsi+0Ah], cx
0x14001cbfe  jnz     short loc_14001CC08
0x14001cc00  mov     rax, [rbx+20h]
0x14001cc04  mov     [rax+2], cx
0x14001cc08  movzx   eax, word ptr [r15]
0x14001cc0c  sub     ax, r13w
0x14001cc10  movzx   edx, r13w
0x14001cc14  add     rdx, [rbx+20h]
0x14001cc18  movzx   r8d, ax
0x14001cc1c  mov     eax, r8d
0x14001cc1f  mov     [rbx+28h], r8w
0x14001cc24  shr     rax, 1
0x14001cc27  mov     [rbx+2Ah], r8w
0x14001cc2c  mov     [rbx+30h], rdx
0x14001cc30  cmp     [rdx+rax*2-2], di
0x14001cc35  jz      loc_14001CD1D
0x14001cc3b  mov     rax, [rsp+78h+arg_10]
0x14001cc43  xor     edi, edi
0x14001cc45  mov     [rax], rbx
0x14001cc48  mov     rbx, [rsp+78h+arg_0]
0x14001cc50  mov     eax, edi
0x14001cc52  add     rsp, 40h
0x14001cc56  pop     r15
0x14001cc58  pop     r14
0x14001cc5a  pop     r13
0x14001cc5c  pop     r12
0x14001cc5e  pop     rdi
0x14001cc5f  pop     rsi
0x14001cc60  pop     rbp
0x14001cc61  retn
0x14001cc63  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cc6a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cc71  jnz     short loc_14001CCAC
0x14001cc73  mov     rcx, rbx; P
0x14001cc76  call    BfpDeleteTargetEntry
0x14001cc7b  jmp     short loc_14001CC48
0x14001cc7d  mov     edi, 0C000009Ah
0x14001cc82  jmp     short loc_14001CC48
0x14001cc84  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cc8b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cc92  jz      short loc_14001CC73
0x14001cc94  mov     r9d, 0Fh
0x14001cc9a  mov     [rsp+78h+var_40], edi
0x14001cc9e  mov     dword ptr [rsp+78h+var_48], 2BFh
0x14001cca6  lea     r8d, [r9-7]
0x14001ccaa  jmp     short loc_14001CCC1
0x14001ccac  mov     [rsp+78h+var_40], edi
0x14001ccb0  mov     r9d, 10h
0x14001ccb6  mov     dword ptr [rsp+78h+var_48], 2D8h
0x14001ccbe  mov     r8d, ebp
0x14001ccc1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ccc8  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001cccf  mov     [rsp+78h+var_50], rax
0x14001ccd4  mov     dl, 2
0x14001ccd6  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001ccdd  mov     [rsp+78h+var_58], rax
0x14001cce2  mov     rcx, [rcx+40h]
0x14001cce6  call    WPP_RECORDER_SF_sDd
0x14001cceb  jmp     short loc_14001CC73
0x14001cced  lea     rdx, g_ntNamePrefix; Source
0x14001ccf4  mov     rcx, r15; Destination
0x14001ccf7  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001ccfe  nop     dword ptr [rax+rax+00h]
0x14001cd03  jmp     loc_14001CBC3
0x14001cd08  mov     rdx, [rsp+78h+Src]; Src
0x14001cd10  add     rcx, rbp; void *
0x14001cd13  call    memmove
0x14001cd18  jmp     loc_14001CC08
0x14001cd1d  mov     ecx, [r14+18h]
0x14001cd21  cmp     ecx, 6
0x14001cd24  jz      short loc_14001CD63
0x14001cd26  cmp     ecx, 0Dh
0x14001cd29  jz      short loc_14001CD63
0x14001cd2b  cmp     r8d, 2
0x14001cd2f  jbe     loc_14001CC3B
0x14001cd35  lea     rax, WPP_RECORDER_INITIALIZED
0x14001cd3c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001cd43  jz      short loc_14001CD59
0x14001cd45  mov     [rsp+78h+var_40], ecx
0x14001cd49  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd50  mov     rcx, [rcx+40h]
0x14001cd54  call    WPP_RECORDER_SF_sDL
0x14001cd59  mov     edi, 0C000000Dh
0x14001cd5e  jmp     loc_14001CC73
0x14001cd63  cmp     r8d, 2
0x14001cd67  jbe     loc_14001CC3B
0x14001cd6d  sub     r8w, 2
0x14001cd72  mov     [rbx+28h], r8w
0x14001cd77  jmp     loc_14001CC3B
```
