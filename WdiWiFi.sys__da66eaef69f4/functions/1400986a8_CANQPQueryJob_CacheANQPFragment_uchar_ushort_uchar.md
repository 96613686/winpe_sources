# CANQPQueryJob::CacheANQPFragment(uchar,ushort,uchar *)

- ea: `0x1400986a8`
- end: `0x1400989ff`
- name: `?CacheANQPFragment@CANQPQueryJob@@AEAAHEGPEAE@Z`
- size: `855`
- prototype: `__int64 __fastcall(CANQPQueryJob *this, unsigned __int8, unsigned __int16, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x140098d10`

## callees

- `0x140010730`
- `0x1400122e0`
- `0x140023ae0`
- `0x1400297a0`
- `0x14002aa28`
- `0x14002ed64`
- `0x140061328`
- `0x1400986a8`
- `0x140099cd0`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140098825`
- `ntoskrnl!ExAllocatePool2` at `0x140098825`

## pseudocode

```c
__int64 __fastcall CANQPQueryJob::CacheANQPFragment(
        CANQPQueryJob *this,
        unsigned __int8 a2,
        unsigned __int16 a3,
        unsigned __int8 *a4)
{
  size_t v4; // rbp
  unsigned int v8; // esi
  int v9; // edx
  int v10; // r8d
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  USHORT v15; // di
  __int64 Pool2; // rax
  _QWORD *v17; // rdi
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  char v24; // [rsp+40h] [rbp-68h]
  char v25; // [rsp+48h] [rbp-60h]
  USHORT v26[44]; // [rsp+50h] [rbp-58h] BYREF
  USHORT pusResult; // [rsp+C0h] [rbp+18h] BYREF

  v4 = a3;
  pusResult = 0;
  v26[0] = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      52,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( !(_WORD)v4 )
  {
    v8 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_qDL(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        a3,
        53,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        a2);
      goto LABEL_34;
    }
    return v8;
  }
  v11 = RtlUShortAdd(0x18u, v4, &pusResult);
  v8 = v11;
  if ( v11 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v8;
    v25 = v4;
    v14 = 54;
    v24 = 24;
LABEL_11:
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qDDDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      v14,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v11,
      v24,
      v25);
    goto LABEL_34;
  }
  v15 = *((_WORD *)this + 332);
  v11 = RtlUShortAdd(v15, v4, v26);
  v8 = v11;
  if ( v11 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return v8;
    v25 = v4;
    v14 = 55;
    v24 = v15;
    goto LABEL_11;
  }
  Pool2 = ExAllocatePool2(64, pusResult, 1198089303);
  v17 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_qDDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        56,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        154,
        pusResult);
    }
    *((_DWORD *)this + 157) = 3;
LABEL_34:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        v10,
        59,
        (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v8);
    }
    return v8;
  }
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  *(_BYTE *)(Pool2 + 18) = a2;
  *(_WORD *)(Pool2 + 16) = v4;
  memmove((void *)(Pool2 + 19), a4, v4);
  v20 = *((_QWORD *)this + 82);
  v21 = (char *)this + 648;
  while ( 1 )
  {
    if ( (char *)v20 == v21 )
    {
      v22 = *(_QWORD *)v21;
      if ( *(char **)(*(_QWORD *)v21 + 8LL) != v21 )
        __fastfail(3u);
      *v17 = v22;
      v17[1] = v21;
      *(_QWORD *)(v22 + 8) = v17;
      *(_QWORD *)v21 = v17;
      goto LABEL_31;
    }
    if ( *(_BYTE *)(v20 + 18) <= a2 )
      break;
    v20 = *(_QWORD *)(v20 + 8);
  }
  if ( *(_BYTE *)(v20 + 18) != a2 )
  {
    *v17 = *(_QWORD *)v20;
    v17[1] = v20;
    *(_QWORD *)(*(_QWORD *)v20 + 8LL) = v17;
    *(_QWORD *)v20 = v17;
LABEL_31:
    *((_WORD *)this + 332) = v26[0];
    goto LABEL_32;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_qDDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      v19,
      57,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      0,
      a2);
  }
  operator delete(v17);
LABEL_32:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = 4;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      v19,
      58,
      (__int64)WPP_22e887a171e833efff7758db291c5810_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      a2,
      v4);
    goto LABEL_34;
  }
  return v8;
}

```

## disassembly

```asm
0x1400986a8  mov     rax, rsp
0x1400986ab  push    rbx
0x1400986ac  push    rbp
0x1400986ad  push    rsi
0x1400986ae  push    rdi
0x1400986af  push    r12
0x1400986b1  push    r13
0x1400986b3  push    r14
0x1400986b5  push    r15
0x1400986b7  sub     rsp, 68h
0x1400986bb  xor     r12d, r12d
0x1400986be  movzx   ebp, r8w
0x1400986c2  mov     [rax+18h], r12w
0x1400986c7  mov     r15, r9
0x1400986ca  mov     [rax-58h], r12w
0x1400986cf  mov     rbx, rcx
0x1400986d2  movzx   r14d, dl
0x1400986d6  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400986dd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400986e4  lea     rdi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x1400986eb  jz      short loc_140098723
0x1400986ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400986f4  cmp     byte ptr [rcx+29h], 5
0x1400986f8  jnb     short loc_140098701
0x1400986fa  cmp     [rcx+48h], r12w
0x1400986ff  jz      short loc_140098723
0x140098701  mov     eax, [rbx+10h]
0x140098704  mov     r9d, 34h ; '4'
0x14009870a  mov     rcx, [rcx+40h]
0x14009870e  mov     dl, 5
0x140098710  mov     [rsp+0A8h+var_78], eax
0x140098714  mov     [rsp+0A8h+var_80], rbx
0x140098719  mov     [rsp+0A8h+var_88], rdi
0x14009871e  call    WPP_RECORDER_SF_qD
0x140098723  test    bp, bp
0x140098726  jnz     short loc_14009876B
0x140098728  mov     esi, r12d
0x14009872b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098732  jz      loc_1400989EB
0x140098738  mov     rcx, cs:WPP_GLOBAL_Control
0x14009873f  mov     r9d, 35h ; '5'
0x140098745  mov     eax, [rbx+10h]
0x140098748  mov     dl, 4
0x14009874a  mov     [rsp+0A8h+var_70], r14d
0x14009874f  mov     [rsp+0A8h+var_78], eax
0x140098753  mov     rcx, [rcx+40h]
0x140098757  mov     [rsp+0A8h+var_80], rbx
0x14009875c  mov     [rsp+0A8h+var_88], rdi
0x140098761  call    WPP_RECORDER_SF_qDL
0x140098766  jmp     loc_1400989A8
0x14009876b  mov     ecx, 18h; usAugend
0x140098770  lea     r8, [rsp+0A8h+pusResult]; pusResult
0x140098778  movzx   edx, bp; usAddend
0x14009877b  call    RtlUShortAdd
0x140098780  mov     esi, eax
0x140098782  test    eax, eax
0x140098784  jz      short loc_1400987D1
0x140098786  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14009878d  jz      loc_1400989EB
0x140098793  mov     dword ptr [rsp+0A8h+var_60], ebp
0x140098797  mov     r9d, 36h ; '6'
0x14009879d  mov     dword ptr [rsp+0A8h+var_68], 18h
0x1400987a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400987ac  mov     dl, 2
0x1400987ae  mov     [rsp+0A8h+var_70], eax
0x1400987b2  mov     eax, [rbx+10h]
0x1400987b5  mov     [rsp+0A8h+var_78], eax
0x1400987b9  mov     rcx, [rcx+40h]
0x1400987bd  mov     [rsp+0A8h+var_80], rbx
0x1400987c2  mov     [rsp+0A8h+var_88], rdi
0x1400987c7  call    WPP_RECORDER_SF_qDDDD
0x1400987cc  jmp     loc_1400989A8
0x1400987d1  movzx   edi, word ptr [rbx+298h]
0x1400987d8  lea     r8, [rsp+0A8h+var_58]; pusResult
0x1400987dd  movzx   ecx, di; usAugend
0x1400987e0  movzx   edx, bp; usAddend
0x1400987e3  call    RtlUShortAdd
0x1400987e8  mov     esi, eax
0x1400987ea  test    eax, eax
0x1400987ec  jz      short loc_140098812
0x1400987ee  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400987f5  jz      loc_1400989EB
0x1400987fb  mov     dword ptr [rsp+0A8h+var_60], ebp
0x1400987ff  mov     r9d, 37h ; '7'
0x140098805  mov     dword ptr [rsp+0A8h+var_68], edi
0x140098809  lea     rdi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098810  jmp     short loc_1400987A5
0x140098812  movzx   edx, [rsp+0A8h+pusResult]
0x14009881a  mov     ecx, 40h ; '@'
0x14009881f  mov     r8d, 47696457h
0x140098825  call    cs:__imp_ExAllocatePool2
0x14009882c  nop     dword ptr [rax+rax+00h]
0x140098831  mov     rdi, rax
0x140098834  test    rax, rax
0x140098837  jnz     short loc_14009889A
0x140098839  mov     esi, 0C000009Ah
0x14009883e  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140098845  lea     rdi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x14009884c  jz      short loc_14009888B
0x14009884e  movzx   eax, [rsp+0A8h+pusResult]
0x140098856  mov     r9d, 38h ; '8'
0x14009885c  mov     rcx, cs:WPP_GLOBAL_Control
0x140098863  mov     dl, 2
0x140098865  mov     dword ptr [rsp+0A8h+var_68], eax
0x140098869  mov     eax, [rbx+10h]
0x14009886c  mov     [rsp+0A8h+var_70], 0C000009Ah
0x140098874  mov     rcx, [rcx+40h]
0x140098878  mov     [rsp+0A8h+var_78], eax
0x14009887c  mov     [rsp+0A8h+var_80], rbx
0x140098881  mov     [rsp+0A8h+var_88], rdi
0x140098886  call    WPP_RECORDER_SF_qDDd
0x14009888b  mov     dword ptr [rbx+274h], 3
0x140098895  jmp     loc_1400989A8
0x14009889a  mov     [rax+8], rdi
0x14009889e  lea     rcx, [rax+13h]; void *
0x1400988a2  mov     [rax], rdi
0x1400988a5  mov     r8, rbp; Size
0x1400988a8  mov     rdx, r15; Src
0x1400988ab  mov     [rax+12h], r14b
0x1400988af  mov     [rax+10h], bp
0x1400988b3  call    memmove
0x1400988b8  mov     rcx, [rbx+290h]
0x1400988bf  lea     rax, [rbx+288h]
0x1400988c6  cmp     rcx, rax
0x1400988c9  jz      short loc_14009893C
0x1400988cb  cmp     [rcx+12h], r14b
0x1400988cf  jbe     short loc_1400988D7
0x1400988d1  mov     rcx, [rcx+8]
0x1400988d5  jmp     short loc_1400988C6
0x1400988d7  jnz     short loc_140098926
0x1400988d9  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400988e0  jz      short loc_14009891C
0x1400988e2  mov     eax, [rbx+10h]
0x1400988e5  mov     r9d, 39h ; '9'
0x1400988eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400988f2  mov     dl, 2
0x1400988f4  mov     dword ptr [rsp+0A8h+var_68], r14d
0x1400988f9  mov     [rsp+0A8h+var_70], r12d
0x1400988fe  mov     [rsp+0A8h+var_78], eax
0x140098902  lea     rax, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x140098909  mov     rcx, [rcx+40h]
0x14009890d  mov     [rsp+0A8h+var_80], rbx
0x140098912  mov     [rsp+0A8h+var_88], rax
0x140098917  call    WPP_RECORDER_SF_qDDd
0x14009891c  mov     rcx, rdi; void *
0x14009891f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140098924  jmp     short loc_140098966
0x140098926  mov     rax, [rcx]
0x140098929  mov     [rdi], rax
0x14009892c  mov     [rdi+8], rcx
0x140098930  mov     rax, [rcx]
0x140098933  mov     [rax+8], rdi
0x140098937  mov     [rcx], rdi
0x14009893a  jmp     short loc_14009895A
0x14009893c  mov     rcx, [rax]
0x14009893f  cmp     [rcx+8], rax
0x140098943  jz      short loc_14009894C
0x140098945  mov     ecx, 3
0x14009894a  int     29h; Win8: RtlFailFast(ecx)
0x14009894c  mov     [rdi], rcx
0x14009894f  mov     [rdi+8], rax
0x140098953  mov     [rcx+8], rdi
0x140098957  mov     [rax], rdi
0x14009895a  movzx   eax, [rsp+0A8h+var_58]
0x14009895f  mov     [rbx+298h], ax
0x140098966  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14009896d  jz      short loc_1400989EB
0x14009896f  mov     rcx, cs:WPP_GLOBAL_Control
0x140098976  lea     rdi, WPP_22e887a171e833efff7758db291c5810_Traceguids
0x14009897d  mov     eax, [rbx+10h]
0x140098980  mov     r9d, 3Ah ; ':'
0x140098986  mov     dword ptr [rsp+0A8h+var_68], ebp
0x14009898a  mov     dl, 4
0x14009898c  mov     [rsp+0A8h+var_70], r14d
0x140098991  mov     rcx, [rcx+40h]
0x140098995  mov     [rsp+0A8h+var_78], eax
0x140098999  mov     [rsp+0A8h+var_80], rbx
0x14009899e  mov     [rsp+0A8h+var_88], rdi
0x1400989a3  call    WPP_RECORDER_SF_qDdd
0x1400989a8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400989af  jz      short loc_1400989EB
0x1400989b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400989b8  cmp     byte ptr [rcx+29h], 5
0x1400989bc  jnb     short loc_1400989C5
0x1400989be  cmp     [rcx+48h], r12w
0x1400989c3  jz      short loc_1400989EB
0x1400989c5  mov     eax, [rbx+10h]
0x1400989c8  mov     r9d, 3Bh ; ';'
0x1400989ce  mov     rcx, [rcx+40h]
0x1400989d2  mov     dl, 5
0x1400989d4  mov     [rsp+0A8h+var_70], esi
0x1400989d8  mov     [rsp+0A8h+var_78], eax
0x1400989dc  mov     [rsp+0A8h+var_80], rbx
0x1400989e1  mov     [rsp+0A8h+var_88], rdi
0x1400989e6  call    WPP_RECORDER_SF_qDD
0x1400989eb  mov     eax, esi
0x1400989ed  add     rsp, 68h
0x1400989f1  pop     r15
0x1400989f3  pop     r14
0x1400989f5  pop     r13
0x1400989f7  pop     r12
0x1400989f9  pop     rdi
0x1400989fa  pop     rsi
0x1400989fb  pop     rbp
0x1400989fc  pop     rbx
0x1400989fd  retn
```
