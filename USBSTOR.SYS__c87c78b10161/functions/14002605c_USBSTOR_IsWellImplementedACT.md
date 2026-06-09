# USBSTOR_IsWellImplementedACT

- ea: `0x14002605c`
- end: `0x14002639c`
- name: `USBSTOR_IsWellImplementedACT`
- size: `832`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140025738`
- `0x140025d60`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x14002605c`
- `0x1400266ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400260c3`
- `ntoskrnl!ExAllocatePool2` at `0x140026199`
- `ntoskrnl!ExAllocatePool2` at `0x1400260c3`
- `ntoskrnl!ExAllocatePool2` at `0x140026199`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026362`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026378`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026362`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026378`

## pseudocode

```c
bool __fastcall USBSTOR_IsWellImplementedACT(
        PDEVICE_OBJECT DeviceObject,
        char a2,
        _BYTE *a3,
        _BYTE *a4,
        __int64 a5,
        unsigned int a6)
{
  _WORD *v10; // rbp
  unsigned __int8 *Pool2; // rax
  __int64 v12; // r8
  unsigned __int8 *v13; // rdi
  PDEVICE_OBJECT v14; // rcx
  unsigned __int16 v15; // dx
  int v16; // ebx
  unsigned int v17; // ebx
  _WORD *v18; // rax
  __int64 v19; // r8
  _WORD *v20; // r8
  unsigned __int8 v21; // r10
  unsigned int v22; // r14d
  __int64 i; // r9
  __int64 v25; // [rsp+40h] [rbp-58h] BYREF
  _OWORD Src[5]; // [rsp+48h] [rbp-50h] BYREF

  LODWORD(v25) = 36;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x13u,
      (__int64)WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
  }
  Pool2 = (unsigned __int8 *)ExAllocatePool2(64, 36, 1396788565);
  v13 = Pool2;
  if ( !Pool2 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_11;
    }
    v15 = 20;
LABEL_10:
    WPP_SF_((__int64)v14->AttachedDevice, v15, (__int64)WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
LABEL_11:
    v16 = -1073741670;
    goto LABEL_49;
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  Src[0] = 0;
  LOBYTE(Src[0]) = 18;
  BYTE4(Src[0]) = 36;
  v16 = USBSTOR_IssueInternalCdbToLun(DeviceObject, a2, v12, Pool2, (ULONG *)&v25, Src, 6u, 20);
  if ( v16 >= 0 )
  {
    v17 = v13[4] + 5;
    if ( v17 > 0x24 && (v17 & 3) == 0 )
    {
      LODWORD(v25) = v13[4] + 5;
      v18 = (_WORD *)ExAllocatePool2(64, v17, 1396788565);
      v10 = v18;
      if ( !v18 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_11;
        }
        v15 = 21;
        goto LABEL_10;
      }
      LOBYTE(Src[0]) = 18;
      BYTE4(Src[0]) = v17;
      v16 = USBSTOR_IssueInternalCdbToLun(DeviceObject, a2, v19, v18, (ULONG *)&v25, Src, 6u, 20);
      if ( v16 < 0 )
        goto LABEL_49;
      if ( (unsigned int)v13[4] + 5 >= 0x3B )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x16u,
            (__int64)WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
        }
        if ( a3 )
          *a3 = 1;
        v20 = v10 + 29;
        if ( v10 + 29 <= v10 + 37 )
        {
          v21 = 58;
          v22 = v13[4] + 5;
          do
          {
            if ( (unsigned int)v21 + 1 >= v22 )
              break;
            for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
            {
              if ( (HIBYTE(*v20) | ((unsigned __int8)*v20 << 8)) == *(unsigned __int16 *)(a5 + 2 * i) )
              {
                if ( a3 )
                  *a4 = 1;
                v16 = 0;
                break;
              }
            }
            v21 += 2;
            ++v20;
          }
          while ( v20 <= v10 + 37 );
        }
        goto LABEL_49;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x17u,
          (__int64)WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids);
      }
    }
    v16 = -1073741823;
  }
LABEL_49:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x18u,
      (__int64)WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids,
      v16);
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  return v16 >= 0;
}

```

## disassembly

```asm
0x14002605c  push    rbx
0x14002605e  push    rbp
0x14002605f  push    rsi
0x140026060  push    rdi
0x140026061  push    r12
0x140026063  push    r14
0x140026065  push    r15
0x140026067  sub     rsp, 60h
0x14002606b  mov     ebx, 24h ; '$'
0x140026070  mov     r12, r9
0x140026073  mov     dword ptr [rsp+98h+var_58], ebx
0x140026077  mov     rsi, r8
0x14002607a  mov     r14b, dl
0x14002607d  mov     r15, rcx
0x140026080  xor     ebp, ebp
0x140026082  mov     rcx, cs:WPP_GLOBAL_Control
0x140026089  lea     rax, WPP_GLOBAL_Control
0x140026090  cmp     rcx, rax
0x140026093  jz      short loc_1400260B5
0x140026095  mov     eax, [rcx+2Ch]
0x140026098  test    al, 1
0x14002609a  jz      short loc_1400260B5
0x14002609c  cmp     byte ptr [rcx+29h], 4
0x1400260a0  jb      short loc_1400260B5
0x1400260a2  mov     rcx, [rcx+18h]
0x1400260a6  lea     edx, [rbx-11h]
0x1400260a9  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x1400260b0  call    WPP_SF_
0x1400260b5  mov     r8d, 53414D55h
0x1400260bb  mov     rdx, rbx
0x1400260be  mov     ecx, 40h ; '@'
0x1400260c3  call    cs:__imp_ExAllocatePool2
0x1400260ca  nop     dword ptr [rax+rax+00h]
0x1400260cf  mov     rdi, rax
0x1400260d2  test    rax, rax
0x1400260d5  jnz     short loc_140026114
0x1400260d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400260de  lea     rax, WPP_GLOBAL_Control
0x1400260e5  cmp     rcx, rax
0x1400260e8  jz      short loc_14002610A
0x1400260ea  mov     eax, [rcx+2Ch]
0x1400260ed  test    al, 1
0x1400260ef  jz      short loc_14002610A
0x1400260f1  cmp     byte ptr [rcx+29h], 2
0x1400260f5  jb      short loc_14002610A
0x1400260f7  lea     edx, [rdi+14h]
0x1400260fa  mov     rcx, [rcx+18h]
0x1400260fe  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x140026105  call    WPP_SF_
0x14002610a  mov     ebx, 0C000009Ah
0x14002610f  jmp     loc_140026320
0x140026114  test    rsi, rsi
0x140026117  jz      short loc_14002611C
0x140026119  mov     [rsi], bpl
0x14002611c  test    r12, r12
0x14002611f  jz      short loc_140026125
0x140026121  mov     [r12], bpl
0x140026125  mov     [rsp+98h+var_60], 14h; int
0x14002612d  lea     rax, [rsp+98h+var_50]
0x140026132  mov     [rsp+98h+var_68], 6; char
0x140026137  xorps   xmm0, xmm0
0x14002613a  mov     [rsp+98h+Src], rax; Src
0x14002613f  mov     r9, rdi
0x140026142  movups  [rsp+98h+var_50], xmm0
0x140026147  lea     rax, [rsp+98h+var_58]
0x14002614c  mov     byte ptr [rsp+98h+var_50], 12h
0x140026151  mov     dl, r14b
0x140026154  mov     [rsp+98h+var_78], rax; __int64
0x140026159  mov     rcx, r15; DeviceObject
0x14002615c  mov     byte ptr [rsp+98h+var_50+4], bl
0x140026160  call    USBSTOR_IssueInternalCdbToLun
0x140026165  mov     ebx, eax
0x140026167  test    eax, eax
0x140026169  js      loc_140026320
0x14002616f  movzx   ebx, byte ptr [rdi+4]
0x140026173  add     ebx, 5
0x140026176  cmp     ebx, 24h ; '$'
0x140026179  jbe     loc_14002631B
0x14002617f  test    bl, 3
0x140026182  jnz     loc_14002631B
0x140026188  mov     edx, ebx
0x14002618a  mov     ecx, 40h ; '@'
0x14002618f  mov     r8d, 53414D55h
0x140026195  mov     dword ptr [rsp+98h+var_58], ebx
0x140026199  call    cs:__imp_ExAllocatePool2
0x1400261a0  nop     dword ptr [rax+rax+00h]
0x1400261a5  mov     rbp, rax
0x1400261a8  test    rax, rax
0x1400261ab  jnz     short loc_1400261E2
0x1400261ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261b4  lea     rax, WPP_GLOBAL_Control
0x1400261bb  cmp     rcx, rax
0x1400261be  jz      loc_14002610A
0x1400261c4  mov     edx, [rcx+2Ch]
0x1400261c7  test    dl, 1
0x1400261ca  jz      loc_14002610A
0x1400261d0  cmp     byte ptr [rcx+29h], 2
0x1400261d4  jb      loc_14002610A
0x1400261da  lea     edx, [rbp+15h]
0x1400261dd  jmp     loc_1400260FA
0x1400261e2  mov     [rsp+98h+var_60], 14h; int
0x1400261ea  lea     rax, [rsp+98h+var_50]
0x1400261ef  mov     [rsp+98h+var_68], 6; char
0x1400261f4  mov     r9, rbp
0x1400261f7  mov     [rsp+98h+Src], rax; Src
0x1400261fc  mov     dl, r14b
0x1400261ff  lea     rax, [rsp+98h+var_58]
0x140026204  mov     byte ptr [rsp+98h+var_50], 12h
0x140026209  mov     rcx, r15; DeviceObject
0x14002620c  mov     [rsp+98h+var_78], rax; __int64
0x140026211  mov     byte ptr [rsp+98h+var_50+4], bl
0x140026215  call    USBSTOR_IssueInternalCdbToLun
0x14002621a  mov     ebx, eax
0x14002621c  test    eax, eax
0x14002621e  js      loc_140026320
0x140026224  movzx   eax, byte ptr [rdi+4]
0x140026228  add     eax, 5
0x14002622b  cmp     eax, 3Bh ; ';'
0x14002622e  jb      loc_1400262E6
0x140026234  mov     rcx, cs:WPP_GLOBAL_Control
0x14002623b  lea     rax, WPP_GLOBAL_Control
0x140026242  cmp     rcx, rax
0x140026245  jz      short loc_140026269
0x140026247  mov     eax, [rcx+2Ch]
0x14002624a  test    al, 1
0x14002624c  jz      short loc_140026269
0x14002624e  cmp     byte ptr [rcx+29h], 4
0x140026252  jb      short loc_140026269
0x140026254  mov     rcx, [rcx+18h]
0x140026258  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x14002625f  mov     edx, 16h
0x140026264  call    WPP_SF_
0x140026269  test    rsi, rsi
0x14002626c  jz      short loc_140026271
0x14002626e  mov     byte ptr [rsi], 1
0x140026271  lea     r8, [rbp+3Ah]
0x140026275  lea     r11, [rbp+4Ah]
0x140026279  cmp     r8, r11
0x14002627c  ja      loc_140026320
0x140026282  movzx   r14d, byte ptr [rdi+4]
0x140026287  mov     r10b, 3Ah ; ':'
0x14002628a  mov     r15, [rsp+98h+arg_20]
0x140026292  add     r14d, 5
0x140026296  movzx   eax, r10b
0x14002629a  inc     eax
0x14002629c  cmp     eax, r14d
0x14002629f  jnb     short loc_140026320
0x1400262a1  xor     r9d, r9d
0x1400262a4  cmp     r9d, [rsp+98h+arg_28]
0x1400262ac  jnb     short loc_1400262D7
0x1400262ae  movzx   eax, word ptr [r8]
0x1400262b2  movzx   ecx, word ptr [r15+r9*2]
0x1400262b7  movzx   edx, al
0x1400262ba  shl     edx, 8
0x1400262bd  shr     eax, 8
0x1400262c0  or      edx, eax
0x1400262c2  cmp     edx, ecx
0x1400262c4  jz      short loc_1400262CB
0x1400262c6  inc     r9d
0x1400262c9  jmp     short loc_1400262A4
0x1400262cb  test    rsi, rsi
0x1400262ce  jz      short loc_1400262D5
0x1400262d0  mov     byte ptr [r12], 1
0x1400262d5  xor     ebx, ebx
0x1400262d7  add     r10b, 2
0x1400262db  add     r8, 2
0x1400262df  cmp     r8, r11
0x1400262e2  jbe     short loc_140026296
0x1400262e4  jmp     short loc_140026320
0x1400262e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262ed  lea     rax, WPP_GLOBAL_Control
0x1400262f4  cmp     rcx, rax
0x1400262f7  jz      short loc_14002631B
0x1400262f9  mov     eax, [rcx+2Ch]
0x1400262fc  test    al, 1
0x1400262fe  jz      short loc_14002631B
0x140026300  cmp     byte ptr [rcx+29h], 4
0x140026304  jb      short loc_14002631B
0x140026306  mov     rcx, [rcx+18h]
0x14002630a  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x140026311  mov     edx, 17h
0x140026316  call    WPP_SF_
0x14002631b  mov     ebx, 0C0000001h
0x140026320  mov     rcx, cs:WPP_GLOBAL_Control
0x140026327  lea     rax, WPP_GLOBAL_Control
0x14002632e  cmp     rcx, rax
0x140026331  jz      short loc_140026358
0x140026333  mov     eax, [rcx+2Ch]
0x140026336  test    al, 1
0x140026338  jz      short loc_140026358
0x14002633a  cmp     byte ptr [rcx+29h], 4
0x14002633e  jb      short loc_140026358
0x140026340  mov     rcx, [rcx+18h]
0x140026344  lea     r8, WPP_35468b3e39b339d6e005ca64578ada2f_Traceguids
0x14002634b  mov     edx, 18h
0x140026350  mov     r9d, ebx
0x140026353  call    WPP_SF_d
0x140026358  test    rbp, rbp
0x14002635b  jz      short loc_14002636E
0x14002635d  xor     edx, edx; Tag
0x14002635f  mov     rcx, rbp; P
0x140026362  call    cs:__imp_ExFreePoolWithTag
0x140026369  nop     dword ptr [rax+rax+00h]
0x14002636e  test    rdi, rdi
0x140026371  jz      short loc_140026384
0x140026373  xor     edx, edx; Tag
0x140026375  mov     rcx, rdi; P
0x140026378  call    cs:__imp_ExFreePoolWithTag
0x14002637f  nop     dword ptr [rax+rax+00h]
0x140026384  shr     ebx, 1Fh
0x140026387  xor     bl, 1
0x14002638a  mov     al, bl
0x14002638c  add     rsp, 60h
0x140026390  pop     r15
0x140026392  pop     r14
0x140026394  pop     r12
0x140026396  pop     rdi
0x140026397  pop     rsi
0x140026398  pop     rbp
0x140026399  pop     rbx
0x14002639a  retn
```
