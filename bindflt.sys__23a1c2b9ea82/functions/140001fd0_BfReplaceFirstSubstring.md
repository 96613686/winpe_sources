# BfReplaceFirstSubstring

- ea: `0x140001fd0`
- end: `0x140002391`
- name: `BfReplaceFirstSubstring`
- size: `961`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140001dd0`
- `0x1400152f0`
- `0x1400157a0`
- `0x140023330`

## callees

- `0x140001348`
- `0x140001fd0`
- `0x140003304`
- `0x1400172f0`
- `0x14001d130`
- `0x14001ef20`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400020f9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002174`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400022f8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400020f9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002174`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400022f8`

## pseudocode

```c
NTSTATUS __fastcall BfReplaceFirstSubstring(
        unsigned __int16 *a1,
        __int16 *a2,
        const UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  __int16 v6; // cx
  char v9; // r12
  int v10; // edx
  const WCHAR *UnicodeSubstring; // rbp
  unsigned __int16 v12; // cx
  int Length; // r8d
  int v14; // eax
  NTSTATUS UnicodeString; // ebx
  int v16; // r9d
  __int64 v17; // r13
  __int64 v18; // rcx
  __int64 v19; // rbp
  unsigned __int16 v20; // cx
  __int64 v21; // rdx
  __int16 v22; // ax
  USHORT v23; // cx
  __int64 v24; // rax
  NTSTATUS result; // eax
  char v26; // [rsp+30h] [rbp-58h]
  int v27; // [rsp+38h] [rbp-50h]
  UNICODE_STRING Source; // [rsp+40h] [rbp-48h] BYREF
  UNICODE_STRING v29; // [rsp+50h] [rbp-38h] BYREF
  int v30; // [rsp+98h] [rbp+10h] BYREF

  *(_QWORD *)&v29.Length = 262146;
  a4->Buffer = 0;
  v6 = *a2;
  v30 = 92;
  v29.Buffer = (PWSTR)&v30;
  if ( v6 == 2 && **((_WORD **)a2 + 1) == 92 && *a1 > 2u || (v9 = 0, !a3->Length) && *a1 && *a1 == v6 )
    v9 = 1;
  UnicodeSubstring = RtlFindUnicodeSubstring(a1, (PCWCH *)a2, 1u);
  if ( !UnicodeSubstring )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        8,
        21,
        (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
        25);
    }
    UnicodeString = -1073741275;
    goto LABEL_21;
  }
  v12 = *a2;
  Length = a3->Length;
  v14 = *a1;
  if ( (_WORD)Length == *a2 )
  {
    v10 = (unsigned __int16)v14;
  }
  else
  {
    if ( (unsigned __int16)v14 < v12 )
    {
      UnicodeString = -1073741675;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = -1073741675;
        v16 = 22;
        v26 = 56;
        goto LABEL_41;
      }
      goto LABEL_21;
    }
    LOWORD(v14) = v14 - v12;
    v10 = Length + v14;
    if ( (unsigned __int16)(Length + v14) < (unsigned __int16)v14 )
    {
      UnicodeString = -1073741675;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = -1073741675;
        v16 = 23;
        v26 = 65;
LABEL_41:
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          8,
          v16,
          (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
          v26,
          v27);
        goto LABEL_21;
      }
      goto LABEL_21;
    }
  }
  v17 = *((_QWORD *)a1 + 1);
  v18 = (unsigned int)(v10 + 2);
  if ( !v9 )
    LOWORD(v18) = v10;
  UnicodeString = BfAllocateUnicodeString(v18, a4);
  if ( UnicodeString < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = UnicodeString;
      v16 = 24;
      v26 = 88;
      goto LABEL_41;
    }
    goto LABEL_21;
  }
  Source = 0;
  v19 = ((__int64)UnicodeSubstring - v17) >> 1;
  Source.MaximumLength = 2 * v19;
  Source.Length = 2 * v19;
  Source.Buffer = (PWSTR)*((_QWORD *)a1 + 1);
  UnicodeString = RtlAppendUnicodeStringToString(a4, &Source);
  if ( UnicodeString < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = UnicodeString;
      v16 = 25;
      v26 = 107;
      goto LABEL_41;
    }
LABEL_21:
    BfFreeUnicodeString(a4);
    return UnicodeString;
  }
  UnicodeString = RtlAppendUnicodeStringToString(a4, a3);
  if ( UnicodeString < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = UnicodeString;
      v16 = 26;
      v26 = 120;
      goto LABEL_41;
    }
    goto LABEL_21;
  }
  if ( v9 )
  {
    UnicodeString = RtlAppendUnicodeStringToString(a4, &v29);
    if ( UnicodeString < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = UnicodeString;
        v16 = 27;
        v26 = -122;
        goto LABEL_41;
      }
      goto LABEL_21;
    }
  }
  v20 = *a1;
  v21 = (unsigned __int16)(v19 + ((unsigned __int16)*a2 >> 1));
  v22 = v19 + ((unsigned __int16)*a2 >> 1);
  Source = 0;
  v23 = v20 - 2 * v22;
  v24 = *((_QWORD *)a1 + 1);
  Source.MaximumLength = v23;
  Source.Length = v23;
  Source.Buffer = (PWSTR)(v24 + 2 * v21);
  result = RtlAppendUnicodeStringToString(a4, &Source);
  UnicodeString = result;
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v27 = result;
      v16 = 28;
      v26 = -102;
      goto LABEL_41;
    }
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x140001fd0  mov     rax, rsp
0x140001fd3  mov     [rax+20h], rbp
0x140001fd7  push    rsi
0x140001fd8  push    rdi
0x140001fd9  push    r12
0x140001fdb  push    r14
0x140001fdd  push    r15
0x140001fdf  sub     rsp, 60h
0x140001fe3  mov     qword ptr [rax-38h], 40002h
0x140001feb  mov     rdi, rcx
0x140001fee  mov     qword ptr [r9+8], 0
0x140001ff6  mov     rsi, r9
0x140001ff9  movzx   ecx, word ptr [rdx]
0x140001ffc  mov     r15, r8
0x140001fff  mov     dword ptr [rax+10h], 5Ch ; '\'
0x140002006  lea     rax, [rax+10h]
0x14000200a  mov     [rsp+88h+var_38.Buffer], rax
0x14000200f  mov     r14, rdx
0x140002012  cmp     cx, 2
0x140002016  jz      loc_14000224F
0x14000201c  xor     r12b, r12b
0x14000201f  cmp     word ptr [r8], 0
0x140002024  jz      loc_140002268
0x14000202a  mov     [rsp+88h+arg_0], rbx
0x140002032  mov     r8b, 1
0x140002035  mov     rcx, rdi
0x140002038  mov     [rsp+88h+arg_10], r13
0x140002040  call    RtlFindUnicodeSubstring
0x140002045  mov     rbp, rax
0x140002048  test    rax, rax
0x14000204b  jz      loc_1400021B0
0x140002051  movzx   ecx, word ptr [r14]
0x140002055  movzx   r8d, word ptr [r15]
0x140002059  movzx   eax, word ptr [rdi]
0x14000205c  cmp     r8w, cx
0x140002060  jz      short loc_1400020A7
0x140002062  cmp     ax, cx
0x140002065  jb      loc_1400021FC
0x14000206b  sub     ax, cx
0x14000206e  lea     edx, [r8+rax]
0x140002072  cmp     dx, ax
0x140002075  jnb     short loc_1400020AA
0x140002077  mov     ebx, 0C0000095h
0x14000207c  lea     rax, WPP_RECORDER_INITIALIZED
0x140002083  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000208a  jz      loc_1400021C9
0x140002090  mov     [rsp+88h+var_50], ebx
0x140002094  mov     r9d, 17h
0x14000209a  mov     dword ptr [rsp+88h+var_58], 541h
0x1400020a2  jmp     loc_14000235C
0x1400020a7  movzx   edx, ax
0x1400020aa  mov     r13, [rdi+8]
0x1400020ae  lea     ecx, [rdx+2]
0x1400020b1  test    r12b, r12b
0x1400020b4  cmovz   cx, dx
0x1400020b8  mov     rdx, rsi
0x1400020bb  call    BfAllocateUnicodeString
0x1400020c0  mov     ebx, eax
0x1400020c2  test    eax, eax
0x1400020c4  js      loc_140002228
0x1400020ca  xorps   xmm0, xmm0
0x1400020cd  lea     rdx, [rsp+88h+Source]; Source
0x1400020d2  movups  xmmword ptr [rsp+88h+Source.Length], xmm0
0x1400020d7  sub     rbp, r13
0x1400020da  mov     rcx, rsi; Destination
0x1400020dd  sar     rbp, 1
0x1400020e0  movzx   eax, bp
0x1400020e3  add     ax, ax
0x1400020e6  mov     [rsp+88h+Source.MaximumLength], ax
0x1400020eb  mov     [rsp+88h+Source.Length], ax
0x1400020f0  mov     rax, [rdi+8]
0x1400020f4  mov     [rsp+88h+Source.Buffer], rax
0x1400020f9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140002100  nop     dword ptr [rax+rax+00h]
0x140002105  mov     ebx, eax
0x140002107  test    eax, eax
0x140002109  js      loc_1400021D5
0x14000210f  mov     rdx, r15; Source
0x140002112  mov     rcx, rsi; Destination
0x140002115  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000211c  nop     dword ptr [rax+rax+00h]
0x140002121  mov     ebx, eax
0x140002123  test    eax, eax
0x140002125  js      loc_1400022C8
0x14000212b  test    r12b, r12b
0x14000212e  jnz     loc_1400022F0
0x140002134  movzx   eax, word ptr [r14]
0x140002138  xorps   xmm0, xmm0
0x14000213b  movzx   ecx, word ptr [rdi]
0x14000213e  shr     ax, 1
0x140002141  add     ax, bp
0x140002144  movzx   edx, ax
0x140002147  movzx   eax, dx
0x14000214a  movups  xmmword ptr [rsp+88h+Source.Length], xmm0
0x14000214f  add     ax, ax
0x140002152  sub     cx, ax
0x140002155  mov     rax, [rdi+8]
0x140002159  mov     [rsp+88h+Source.MaximumLength], cx
0x14000215e  mov     [rsp+88h+Source.Length], cx
0x140002163  lea     rcx, [rax+rdx*2]
0x140002167  mov     [rsp+88h+Source.Buffer], rcx
0x14000216c  lea     rdx, [rsp+88h+Source]; Source
0x140002171  mov     rcx, rsi; Destination
0x140002174  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000217b  nop     dword ptr [rax+rax+00h]
0x140002180  mov     ebx, eax
0x140002182  test    eax, eax
0x140002184  js      loc_140002336
0x14000218a  mov     r13, [rsp+88h+arg_10]
0x140002192  mov     rbx, [rsp+88h+arg_0]
0x14000219a  mov     rbp, [rsp+88h+arg_18]
0x1400021a2  add     rsp, 60h
0x1400021a6  pop     r15
0x1400021a8  pop     r14
0x1400021aa  pop     r12
0x1400021ac  pop     rdi
0x1400021ad  pop     rsi
0x1400021ae  retn
0x1400021b0  lea     rax, WPP_RECORDER_INITIALIZED
0x1400021b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400021be  jnz     loc_140002285
0x1400021c4  mov     ebx, 0C0000225h
0x1400021c9  mov     rcx, rsi
0x1400021cc  call    BfFreeUnicodeString
0x1400021d1  mov     eax, ebx
0x1400021d3  jmp     short loc_14000218A
0x1400021d5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400021dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400021e3  jz      short loc_1400021C9
0x1400021e5  mov     [rsp+88h+var_50], ebx
0x1400021e9  mov     r9d, 19h
0x1400021ef  mov     dword ptr [rsp+88h+var_58], 56Bh
0x1400021f7  jmp     loc_14000235C
0x1400021fc  mov     ebx, 0C0000095h
0x140002201  lea     rax, WPP_RECORDER_INITIALIZED
0x140002208  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000220f  jz      short loc_1400021C9
0x140002211  mov     [rsp+88h+var_50], ebx
0x140002215  mov     r9d, 16h
0x14000221b  mov     dword ptr [rsp+88h+var_58], 538h
0x140002223  jmp     loc_14000235C
0x140002228  lea     rax, WPP_RECORDER_INITIALIZED
0x14000222f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002236  jz      short loc_1400021C9
0x140002238  mov     [rsp+88h+var_50], ebx
0x14000223c  mov     r9d, 18h
0x140002242  mov     dword ptr [rsp+88h+var_58], 558h
0x14000224a  jmp     loc_14000235C
0x14000224f  mov     rax, [rdx+8]
0x140002253  cmp     word ptr [rax], 5Ch ; '\'
0x140002257  jnz     loc_14000201C
0x14000225d  cmp     word ptr [rdi], 2
0x140002261  ja      short loc_14000227D
0x140002263  jmp     loc_14000201C
0x140002268  movzx   eax, word ptr [rdi]
0x14000226b  test    ax, ax
0x14000226e  jz      loc_14000202A
0x140002274  cmp     ax, cx
0x140002277  jnz     loc_14000202A
0x14000227d  mov     r12b, 1
0x140002280  jmp     loc_14000202A
0x140002285  mov     rcx, cs:WPP_GLOBAL_Control
0x14000228c  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140002293  mov     dword ptr [rsp+88h+var_58], 519h
0x14000229b  mov     r9d, 15h
0x1400022a1  mov     [rsp+88h+var_60], rax
0x1400022a6  mov     r8d, 8
0x1400022ac  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x1400022b3  mov     dl, 2
0x1400022b5  mov     rcx, [rcx+40h]
0x1400022b9  mov     [rsp+88h+var_68], rax
0x1400022be  call    WPP_RECORDER_SF_sD
0x1400022c3  jmp     loc_1400021C4
0x1400022c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400022cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400022d6  jz      loc_1400021C9
0x1400022dc  mov     [rsp+88h+var_50], ebx
0x1400022e0  mov     r9d, 1Ah
0x1400022e6  mov     dword ptr [rsp+88h+var_58], 578h
0x1400022ee  jmp     short loc_14000235C
0x1400022f0  lea     rdx, [rsp+88h+var_38]; Source
0x1400022f5  mov     rcx, rsi; Destination
0x1400022f8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400022ff  nop     dword ptr [rax+rax+00h]
0x140002304  mov     ebx, eax
0x140002306  test    eax, eax
0x140002308  jns     loc_140002134
0x14000230e  lea     rax, WPP_RECORDER_INITIALIZED
0x140002315  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000231c  jz      loc_1400021C9
0x140002322  mov     [rsp+88h+var_50], ebx
0x140002326  mov     r9d, 1Bh
0x14000232c  mov     dword ptr [rsp+88h+var_58], 586h
0x140002334  jmp     short loc_14000235C
0x140002336  lea     rax, WPP_RECORDER_INITIALIZED
0x14000233d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002344  jz      loc_1400021C9
0x14000234a  mov     [rsp+88h+var_50], ebx
0x14000234e  mov     r9d, 1Ch
0x140002354  mov     dword ptr [rsp+88h+var_58], 59Ah
0x14000235c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002363  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000236a  mov     [rsp+88h+var_60], rax
0x14000236f  mov     r8d, 8
0x140002375  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x14000237c  mov     dl, 2
0x14000237e  mov     [rsp+88h+var_68], rax
0x140002383  mov     rcx, [rcx+40h]
0x140002387  call    WPP_RECORDER_SF_sDd
0x14000238c  jmp     loc_1400021C9
```
