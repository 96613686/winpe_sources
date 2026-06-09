# CPMKIDCacheHelpers::SetPMKIDsForBSSEntries(CPort *,ulong,ulong,ulong *,CBSSEntry * *,uchar (* *)[16])

- ea: `0x1400b37f8`
- end: `0x1400b3cc6`
- name: `?SetPMKIDsForBSSEntries@CPMKIDCacheHelpers@@SAHPEAVCPort@@KKPEAKPEAPEAVCBSSEntry@@PEAPEAY0BA@E@Z`
- size: `1230`
- prototype: `__int64 __fastcall(struct CPort *, unsigned int, unsigned int, unsigned int *, struct CBSSEntry **, unsigned __int8 (**)[16])`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a5b1c`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x14001a630`
- `0x140024a20`
- `0x14005ab30`
- `0x14009a8c0`
- `0x1400b37f8`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b395f`
- `ntoskrnl!RtlCompareMemory` at `0x1400b395f`

## pseudocode

```c
__int64 __fastcall CPMKIDCacheHelpers::SetPMKIDsForBSSEntries(
        struct CPort *a1,
        unsigned int a2,
        int a3,
        unsigned int *a4,
        struct CBSSEntry **a5,
        unsigned __int8 (**a6)[16])
{
  unsigned __int16 v6; // bp
  struct CPort *v8; // rax
  unsigned int v9; // ebx
  int v10; // edx
  __int64 v11; // r8
  unsigned int PropertyBuffer; // r15d
  unsigned __int8 *v13; // rsi
  int v14; // edx
  __int64 v15; // rax
  unsigned int j; // edi
  __int64 v17; // r14
  __int64 v18; // r12
  unsigned __int8 (**v19)[16]; // r12
  struct CBSSEntry **v20; // rbp
  unsigned int v21; // eax
  struct CBSSEntry *v22; // r10
  __int64 v23; // r9
  unsigned __int8 *v24; // r11
  char v25; // r14
  char v26; // r13
  unsigned __int8 PropertyBooleanOrDefault; // al
  int v28; // edx
  int v29; // r8d
  char v30; // r12
  unsigned int v31; // ebp
  unsigned __int16 v32; // di
  unsigned __int8 (**v33)[16]; // r15
  struct CBSSEntry **v34; // r12
  __int64 v35; // r14
  __int64 v36; // rax
  char i; // [rsp+50h] [rbp-68h]
  char v39; // [rsp+54h] [rbp-64h]
  unsigned __int8 *v40; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v42; // [rsp+C8h] [rbp+10h]
  unsigned int v43; // [rsp+D0h] [rbp+18h] BYREF
  unsigned int *v44; // [rsp+D8h] [rbp+20h]

  v44 = a4;
  v42 = a2;
  v6 = 0;
  v40 = 0;
  v43 = 0;
  v8 = a1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      71,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    v8 = a1;
  }
  if ( !a4 )
  {
    LOBYTE(v9) = 0;
LABEL_51:
    PropertyBuffer = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBuffer;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      a3,
      72,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      v9,
      40);
    goto LABEL_53;
  }
  v9 = *a4;
  if ( !v9 || v9 > 0x28 )
    goto LABEL_51;
  PropertyBuffer = CPropertyCache::GetPropertyBuffer((struct CPort *)((char *)v8 + 480), 0x2Cu, &v43, &v40);
  if ( PropertyBuffer || v43 < 0xC )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBuffer;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      73,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      PropertyBuffer);
  }
  else
  {
    v13 = v40;
    v39 = 0;
    v14 = 0;
    for ( i = 0; (unsigned int)(unsigned __int16)v14 < *((_DWORD *)v13 + 1); *(_DWORD *)&v13[28 * v15 + 36] = 0 )
    {
      v15 = (unsigned __int16)v14;
      LOWORD(v14) = v14 + 1;
    }
    v43 = v9;
    for ( j = 0; j < v9; ++j )
    {
      v17 = j;
      while ( (unsigned int)v6 < *((_DWORD *)v13 + 1) )
      {
        v17 = j;
        v18 = 28LL * v6;
        if ( RtlCompareMemory((char *)a5[v17] + 32, &v13[v18 + 12], 6u) == 6 )
        {
          ++v39;
          a6[v17] = (unsigned __int8 (*)[16])&v13[v18 + 18];
          *(_DWORD *)&v13[v18 + 36] = 1;
          break;
        }
        ++v6;
      }
      v19 = a6;
      v6 = 0;
      if ( !a6[v17] && v42 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v20 = a5;
        }
        else
        {
          v20 = a5;
          WPP_RECORDER_SF_d_MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            v11,
            74,
            (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
            j,
            (__int64)a5[v17] + 32);
        }
        v21 = j;
        v22 = v20[v17];
        v23 = v43 - 1;
        v24 = (unsigned __int8 *)v19[v17];
        if ( j < (unsigned int)v23 )
        {
          do
          {
            v11 = v21 + 1;
            v20[v21] = v20[v11];
            v19[v21++] = v19[v11];
          }
          while ( (unsigned int)v11 < (unsigned int)v23 );
        }
        v20[v23] = v22;
        --v9;
        v19[v23] = (unsigned __int8 (*)[16])v24;
        --j;
        v6 = 0;
      }
    }
    PropertyBuffer = 0;
    v25 = v42;
    v26 = 0;
    PropertyBooleanOrDefault = CPropertyCache::GetPropertyBooleanOrDefault((struct CPort *)((char *)a1 + 480), 0x2Fu, 0);
    LOBYTE(v43) = PropertyBooleanOrDefault;
    v30 = PropertyBooleanOrDefault;
    if ( v42 && !PropertyBooleanOrDefault && v9 < 0x28 )
    {
      v31 = v42;
      if ( *((_DWORD *)v13 + 1) < v42 )
        v31 = *((_DWORD *)v13 + 1);
      v32 = 0;
      if ( v31 )
      {
        v33 = a6;
        v34 = a5;
        do
        {
          v35 = 28LL * v32;
          if ( !*(_DWORD *)&v13[v35 + 36] )
          {
            v36 = (**(__int64 (__fastcall ***)(__int64, __int64))(*((_QWORD *)a1 + 17) + 1336LL))(
                    *((_QWORD *)a1 + 17) + 1336LL,
                    (__int64)&v13[v35 + 12]);
            if ( !v36 || *(_BYTE *)(v36 + 947) )
            {
              v26 = i;
            }
            else
            {
              v34[v9] = (struct CBSSEntry *)v36;
              v33[v9++] = (unsigned __int8 (*)[16])&v13[v35 + 18];
              *(_DWORD *)&v13[v35 + 36] = 1;
              v26 = ++i;
              if ( v9 >= 0x28 )
                break;
            }
          }
          ++v32;
        }
        while ( v32 < v31 );
        PropertyBuffer = 0;
        v30 = v43;
        v25 = v42;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v28) = 4;
      WPP_RECORDER_SF_ddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v28,
        v29,
        75,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        v25,
        v9,
        v39,
        v26,
        v30);
    }
    if ( v9 )
      *v44 = v9;
  }
LABEL_53:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v28) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v28,
      1,
      76,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      PropertyBuffer);
  }
  return PropertyBuffer;
}

```

## disassembly

```asm
0x1400b37f8  mov     r11, rsp
0x1400b37fb  mov     [r11+20h], r9
0x1400b37ff  mov     [r11+18h], r8d
0x1400b3803  mov     [rsp+arg_8], edx
0x1400b3807  mov     [r11+8], rcx
0x1400b380b  push    rbx
0x1400b380c  push    rbp
0x1400b380d  push    rsi
0x1400b380e  push    rdi
0x1400b380f  push    r12
0x1400b3811  push    r13
0x1400b3813  push    r14
0x1400b3815  push    r15
0x1400b3817  sub     rsp, 78h
0x1400b381b  xor     ebp, ebp
0x1400b381d  mov     rbx, r9
0x1400b3820  mov     [r11-58h], rbp
0x1400b3824  mov     r14d, edx
0x1400b3827  mov     [r11+18h], ebp
0x1400b382b  mov     rax, rcx
0x1400b382e  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b3835  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b383c  lea     rsi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b3843  lea     edi, [rbp+1]
0x1400b3846  jz      short loc_1400B3883
0x1400b3848  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b384f  cmp     byte ptr [rcx+29h], 5
0x1400b3853  jnb     short loc_1400B385B
0x1400b3855  cmp     [rcx+48h], bp
0x1400b3859  jz      short loc_1400B387C
0x1400b385b  mov     rcx, [rcx+40h]
0x1400b385f  mov     r9d, 47h ; 'G'
0x1400b3865  mov     r8d, edi
0x1400b3868  mov     [rsp+0B8h+var_98], rsi
0x1400b386d  mov     dl, 5
0x1400b386f  call    WPP_RECORDER_SF_
0x1400b3874  mov     rax, [rsp+0B8h+arg_0]
0x1400b387c  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b3883  test    rbx, rbx
0x1400b3886  jz      loc_1400B3C39
0x1400b388c  mov     ebx, [rbx]
0x1400b388e  test    ebx, ebx
0x1400b3890  jz      loc_1400B3C3B
0x1400b3896  cmp     ebx, 28h ; '('
0x1400b3899  ja      loc_1400B3C3B
0x1400b389f  lea     rcx, [rax+1E0h]; this
0x1400b38a6  mov     edx, 2Ch ; ','; unsigned int
0x1400b38ab  lea     r9, [rsp+0B8h+var_58]; unsigned __int8 **
0x1400b38b0  lea     r8, [rsp+0B8h+arg_10]; unsigned int *
0x1400b38b8  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400b38bd  mov     [rsp+0B8h+var_60], eax
0x1400b38c1  mov     r15d, eax
0x1400b38c4  test    eax, eax
0x1400b38c6  jnz     loc_1400B3BFE
0x1400b38cc  cmp     [rsp+0B8h+arg_10], 0Ch
0x1400b38d4  jb      loc_1400B3BFE
0x1400b38da  mov     rsi, [rsp+0B8h+var_58]
0x1400b38df  mov     r13d, ebp
0x1400b38e2  mov     [rsp+0B8h+var_64], ebp
0x1400b38e6  mov     edx, ebp
0x1400b38e8  mov     [rsp+0B8h+var_68], ebp
0x1400b38ec  cmp     [rsi+4], ebp
0x1400b38ef  jbe     short loc_1400B3907
0x1400b38f1  movzx   eax, dx
0x1400b38f4  add     dx, di
0x1400b38f7  imul    rcx, rax, 1Ch
0x1400b38fb  movzx   eax, dx
0x1400b38fe  mov     [rcx+rsi+24h], ebp
0x1400b3902  cmp     eax, [rsi+4]
0x1400b3905  jb      short loc_1400B38F1
0x1400b3907  mov     [rsp+0B8h+arg_10], ebx
0x1400b390e  mov     edi, ebp
0x1400b3910  test    ebx, ebx
0x1400b3912  jz      loc_1400B3A88
0x1400b3918  mov     r15d, [rsp+0B8h+arg_8]
0x1400b3920  mov     r13d, edi
0x1400b3923  lea     r14, ds:0[r13*8]
0x1400b392b  movzx   eax, bp
0x1400b392e  cmp     eax, [rsi+4]
0x1400b3931  jnb     short loc_1400B399B
0x1400b3933  movzx   eax, bp
0x1400b3936  lea     r14, ds:0[r13*8]
0x1400b393e  imul    r12, rax, 1Ch
0x1400b3942  mov     rax, [rsp+0B8h+arg_20]
0x1400b394a  lea     rdx, [rsi+0Ch]
0x1400b394e  add     rdx, r12; Source2
0x1400b3951  mov     r8d, 6; Length
0x1400b3957  mov     rcx, [r14+rax]
0x1400b395b  add     rcx, 20h ; ' '; Source1
0x1400b395f  call    cs:__imp_RtlCompareMemory
0x1400b3966  nop     dword ptr [rax+rax+00h]
0x1400b396b  cmp     rax, 6
0x1400b396f  jz      short loc_1400B3976
0x1400b3971  inc     bp
0x1400b3974  jmp     short loc_1400B392B
0x1400b3976  mov     rcx, [rsp+0B8h+arg_28]
0x1400b397e  lea     rax, [rsi+12h]
0x1400b3982  add     rax, r12
0x1400b3985  mov     r13d, 1
0x1400b398b  add     [rsp+0B8h+var_64], r13d
0x1400b3990  mov     [r14+rcx], rax
0x1400b3994  mov     [r12+rsi+24h], r13d
0x1400b3999  jmp     short loc_1400B39A1
0x1400b399b  mov     r13d, 1
0x1400b39a1  mov     r12, [rsp+0B8h+arg_28]
0x1400b39a9  xor     ebp, ebp
0x1400b39ab  cmp     [r14+r12], rbp
0x1400b39af  jnz     loc_1400B3A6B
0x1400b39b5  test    r15d, r15d
0x1400b39b8  jz      loc_1400B3A6B
0x1400b39be  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b39c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b39cc  jz      short loc_1400B3A17
0x1400b39ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b39d5  cmp     byte ptr [rcx+29h], 5
0x1400b39d9  jnb     short loc_1400B39E1
0x1400b39db  cmp     [rcx+48h], bp
0x1400b39df  jz      short loc_1400B3A17
0x1400b39e1  mov     rbp, [rsp+0B8h+arg_20]
0x1400b39e9  mov     r9d, 4Ah ; 'J'
0x1400b39ef  mov     rcx, [rcx+40h]
0x1400b39f3  mov     rax, [r14+rbp]
0x1400b39f7  add     rax, 20h ; ' '
0x1400b39fb  mov     [rsp+0B8h+var_88], rax
0x1400b3a00  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b3a07  mov     [rsp+0B8h+var_90], edi
0x1400b3a0b  mov     [rsp+0B8h+var_98], rax
0x1400b3a10  call    WPP_RECORDER_SF_d_MAC_
0x1400b3a15  jmp     short loc_1400B3A1F
0x1400b3a17  mov     rbp, [rsp+0B8h+arg_20]
0x1400b3a1f  mov     r9d, [rsp+0B8h+arg_10]
0x1400b3a27  mov     eax, edi
0x1400b3a29  mov     r10, [r14+rbp]
0x1400b3a2d  dec     r9d
0x1400b3a30  mov     r11, [r14+r12]
0x1400b3a34  cmp     edi, r9d
0x1400b3a37  jnb     short loc_1400B3A59
0x1400b3a39  mov     ecx, eax
0x1400b3a3b  lea     r8d, [rax+1]
0x1400b3a3f  mov     rax, [rbp+r8*8+0]
0x1400b3a44  mov     [rbp+rcx*8+0], rax
0x1400b3a49  mov     rax, [r12+r8*8]
0x1400b3a4d  mov     [r12+rcx*8], rax
0x1400b3a51  mov     eax, r8d
0x1400b3a54  cmp     r8d, r9d
0x1400b3a57  jb      short loc_1400B3A39
0x1400b3a59  or      eax, 0FFFFFFFFh
0x1400b3a5c  mov     [rbp+r9*8+0], r10
0x1400b3a61  add     ebx, eax
0x1400b3a63  mov     [r12+r9*8], r11
0x1400b3a67  add     edi, eax
0x1400b3a69  xor     ebp, ebp
0x1400b3a6b  add     edi, r13d
0x1400b3a6e  cmp     edi, ebx
0x1400b3a70  jb      loc_1400B3920
0x1400b3a76  mov     r15d, [rsp+0B8h+var_60]
0x1400b3a7b  mov     r14d, [rsp+0B8h+arg_8]
0x1400b3a83  mov     r13d, [rsp+0B8h+var_68]
0x1400b3a88  mov     rcx, [rsp+0B8h+arg_0]
0x1400b3a90  xor     r8d, r8d; unsigned __int8
0x1400b3a93  add     rcx, 1E0h; this
0x1400b3a9a  lea     edx, [r8+2Fh]; unsigned int
0x1400b3a9e  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400b3aa3  mov     byte ptr [rsp+0B8h+arg_10], al
0x1400b3aaa  mov     r12b, al
0x1400b3aad  test    r14d, r14d
0x1400b3ab0  jz      loc_1400B3B97
0x1400b3ab6  test    al, al
0x1400b3ab8  jnz     loc_1400B3B97
0x1400b3abe  cmp     ebx, 28h ; '('
0x1400b3ac1  jnb     loc_1400B3B97
0x1400b3ac7  mov     ecx, [rsi+4]
0x1400b3aca  mov     ebp, r14d
0x1400b3acd  cmp     ecx, r14d
0x1400b3ad0  cmovb   ebp, ecx
0x1400b3ad3  xor     edi, edi
0x1400b3ad5  test    ebp, ebp
0x1400b3ad7  jz      loc_1400B3B95
0x1400b3add  mov     r15, [rsp+0B8h+arg_28]
0x1400b3ae5  mov     r12, [rsp+0B8h+arg_20]
0x1400b3aed  movzx   eax, di
0x1400b3af0  imul    r14, rax, 1Ch
0x1400b3af4  cmp     dword ptr [r14+rsi+24h], 0
0x1400b3afa  jnz     short loc_1400B3B6D
0x1400b3afc  mov     rax, [rsp+0B8h+arg_0]
0x1400b3b04  lea     r13, [r14+rsi]
0x1400b3b08  lea     rdx, [r13+0Ch]
0x1400b3b0c  mov     rcx, [rax+88h]
0x1400b3b13  add     rcx, 538h
0x1400b3b1a  mov     rax, [rcx]
0x1400b3b1d  mov     rax, [rax]
0x1400b3b20  call    _guard_dispatch_icall
0x1400b3b25  test    rax, rax
0x1400b3b28  jz      short loc_1400B3B68
0x1400b3b2a  cmp     byte ptr [rax+3B3h], 0
0x1400b3b31  jnz     short loc_1400B3B68
0x1400b3b33  mov     ecx, ebx
0x1400b3b35  mov     [r12+rcx*8], rax
0x1400b3b39  lea     rax, [r13+12h]
0x1400b3b3d  mov     r13d, 1
0x1400b3b43  mov     [r15+rcx*8], rax
0x1400b3b47  add     ebx, r13d
0x1400b3b4a  mov     [r14+rsi+24h], r13d
0x1400b3b4f  mov     r13d, [rsp+0B8h+var_68]
0x1400b3b54  mov     eax, 1
0x1400b3b59  add     r13d, eax
0x1400b3b5c  mov     [rsp+0B8h+var_68], r13d
0x1400b3b61  cmp     ebx, 28h ; '('
0x1400b3b64  jnb     short loc_1400B3B80
0x1400b3b66  jmp     short loc_1400B3B72
0x1400b3b68  mov     r13d, [rsp+0B8h+var_68]
0x1400b3b6d  mov     eax, 1
0x1400b3b72  add     di, ax
0x1400b3b75  movzx   eax, di
0x1400b3b78  cmp     eax, ebp
0x1400b3b7a  jb      loc_1400B3AED
0x1400b3b80  mov     r15d, [rsp+0B8h+var_60]
0x1400b3b85  mov     r12b, byte ptr [rsp+0B8h+arg_10]
0x1400b3b8d  mov     r14d, [rsp+0B8h+arg_8]
0x1400b3b95  xor     ebp, ebp
0x1400b3b97  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b3b9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3ba5  lea     rsi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b3bac  jz      short loc_1400B3BE9
0x1400b3bae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3bb5  mov     r9d, 4Bh ; 'K'
0x1400b3bbb  movzx   eax, r12b
0x1400b3bbf  mov     dl, 4
0x1400b3bc1  mov     [rsp+0B8h+var_70], eax
0x1400b3bc5  mov     eax, [rsp+0B8h+var_64]
0x1400b3bc9  mov     rcx, [rcx+40h]
0x1400b3bcd  mov     [rsp+0B8h+var_78], r13d
0x1400b3bd2  mov     [rsp+0B8h+var_80], eax
0x1400b3bd6  mov     dword ptr [rsp+0B8h+var_88], ebx
0x1400b3bda  mov     [rsp+0B8h+var_90], r14d
0x1400b3bdf  mov     [rsp+0B8h+var_98], rsi
0x1400b3be4  call    WPP_RECORDER_SF_ddddd
0x1400b3be9  mov     edi, 1
0x1400b3bee  test    ebx, ebx
0x1400b3bf0  jz      short loc_1400B3C70
0x1400b3bf2  mov     rax, [rsp+0B8h+arg_18]
0x1400b3bfa  mov     [rax], ebx
0x1400b3bfc  jmp     short loc_1400B3C70
0x1400b3bfe  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b3c05  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3c0c  jz      loc_1400B3CB1
0x1400b3c12  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c19  mov     r9d, 49h ; 'I'
0x1400b3c1f  mov     [rsp+0B8h+var_90], r15d
0x1400b3c24  mov     r8d, edi
0x1400b3c27  mov     dl, 2
0x1400b3c29  mov     [rsp+0B8h+var_98], rsi
0x1400b3c2e  mov     rcx, [rcx+40h]
0x1400b3c32  call    WPP_RECORDER_SF_d
0x1400b3c37  jmp     short loc_1400B3C70
0x1400b3c39  mov     ebx, ebp
0x1400b3c3b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b3c42  mov     r15d, ebp
0x1400b3c45  jz      short loc_1400B3CB1
0x1400b3c47  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c4e  mov     r9d, 48h ; 'H'
0x1400b3c54  mov     dword ptr [rsp+0B8h+var_88], 28h ; '('
0x1400b3c5c  mov     dl, 2
0x1400b3c5e  mov     [rsp+0B8h+var_90], ebx
0x1400b3c62  mov     [rsp+0B8h+var_98], rsi
0x1400b3c67  mov     rcx, [rcx+40h]
0x1400b3c6b  call    WPP_RECORDER_SF_Ld
0x1400b3c70  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b3c77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b3c7e  jz      short loc_1400B3CB1
0x1400b3c80  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c87  cmp     byte ptr [rcx+29h], 5
0x1400b3c8b  jnb     short loc_1400B3C93
0x1400b3c8d  cmp     [rcx+48h], bp
0x1400b3c91  jz      short loc_1400B3CB1
0x1400b3c93  mov     rcx, [rcx+40h]
0x1400b3c97  mov     r9d, 4Ch ; 'L'
0x1400b3c9d  mov     [rsp+0B8h+var_90], r15d
0x1400b3ca2  mov     r8d, edi
0x1400b3ca5  mov     dl, 5
0x1400b3ca7  mov     [rsp+0B8h+var_98], rsi
0x1400b3cac  call    WPP_RECORDER_SF_d
0x1400b3cb1  mov     eax, r15d
0x1400b3cb4  add     rsp, 78h
0x1400b3cb8  pop     r15
0x1400b3cba  pop     r14
0x1400b3cbc  pop     r13
0x1400b3cbe  pop     r12
0x1400b3cc0  pop     rdi
0x1400b3cc1  pop     rsi
0x1400b3cc2  pop     rbp
0x1400b3cc3  pop     rbx
0x1400b3cc4  retn
```
