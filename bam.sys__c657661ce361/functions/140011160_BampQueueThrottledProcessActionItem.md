# BampQueueThrottledProcessActionItem

- ea: `0x140011160`
- end: `0x14001139a`
- name: `BampQueueThrottledProcessActionItem`
- size: `570`
- prototype: `NTSTATUS __fastcall(__int64, int, unsigned int, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c990`
- `0x1400100b0`
- `0x140010308`
- `0x140010990`
- `0x140011660`
- `0x14001474c`
- `0x1400153a0`

## callees

- `0x1400026d0`
- `0x140011160`
- `0x140011430`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001135e`
- `ntoskrnl!EtwWriteTransfer` at `0x14001135e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400111a5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400111a5`

## pseudocode

```c
NTSTATUS __fastcall BampQueueThrottledProcessActionItem(__int64 a1, int a2, unsigned int a3, int a4)
{
  __int64 v5; // r15
  unsigned __int64 v8; // rax
  char v9; // bl
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  char v12; // r8
  __int64 v13; // rdx
  _QWORD *v14; // r8
  NTSTATUS result; // eax
  __int64 v16; // rax
  int v17; // ecx
  char v18; // [rsp+30h] [rbp-89h] BYREF
  char v19; // [rsp+31h] [rbp-88h] BYREF
  int v20; // [rsp+34h] [rbp-85h] BYREF
  int v21; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v22; // [rsp+3Ch] [rbp-7Dh] BYREF
  _DWORD v23[2]; // [rsp+40h] [rbp-79h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-59h] BYREF
  void *v26; // [rsp+70h] [rbp-49h]
  int v27; // [rsp+78h] [rbp-41h]
  int v28; // [rsp+7Ch] [rbp-3Dh]
  int *v29; // [rsp+80h] [rbp-39h]
  __int64 v30; // [rsp+88h] [rbp-31h]
  int *v31; // [rsp+90h] [rbp-29h]
  __int64 v32; // [rsp+98h] [rbp-21h]
  int *v33; // [rsp+A0h] [rbp-19h]
  __int64 v34; // [rsp+A8h] [rbp-11h]
  _DWORD *v35; // [rsp+B0h] [rbp-9h]
  __int64 v36; // [rsp+B8h] [rbp-1h]
  char *v37; // [rsp+C0h] [rbp+7h]
  __int64 v38; // [rsp+C8h] [rbp+Fh]
  char *v39; // [rsp+D0h] [rbp+17h]
  __int64 v40; // [rsp+D8h] [rbp+1Fh]

  v5 = a2;
  if ( a3 )
    v8 = 10000LL * a3 + KeQueryUnbiasedInterruptTime();
  else
    v8 = 0;
  v9 = 0;
  v10 = (_QWORD *)(a1 + 32 * v5 + 168);
  v11 = v10[2];
  if ( (v11 & 1) != 0 )
  {
    if ( (a4 & 1) == 0 )
    {
      v12 = 0;
      if ( (a4 & 2) == 0 || v8 >= (v11 & 0xFFFFFFFFFFFFFFFEuLL) )
        goto LABEL_14;
    }
    v13 = *v10;
    v9 = 1;
    if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v14 = (_QWORD *)v10[1], (_QWORD *)*v14 != v10) )
      __fastfail(3u);
    *v14 = v13;
    *(_QWORD *)(v13 + 8) = v14;
    *(_OWORD *)v10 = 0;
  }
  v10[2] = v8 & 0xFFFFFFFFFFFFFFFEuLL;
  BampInsertThrottlingActionItem();
  v12 = 1;
  if ( !v9 && _InterlockedIncrement64((volatile signed __int64 *)(a1 + 264)) <= 1 )
    __fastfail(0xEu);
LABEL_14:
  result = dword_140007010;
  if ( (unsigned int)dword_140007010 > 5 )
  {
    v16 = *(_QWORD *)(a1 + 8);
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    v17 = *(_DWORD *)(v16 + 464);
    v29 = &v20;
    v31 = &v21;
    v33 = (int *)&v22;
    v35 = v23;
    v37 = &v18;
    v39 = &v19;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_140007018;
    v20 = v17;
    v18 = v12;
    v30 = 4;
    v21 = v5;
    v32 = 4;
    v22 = a3;
    v34 = 4;
    v23[0] = a4;
    v36 = 4;
    v38 = 1;
    v19 = v9;
    v40 = 1;
    UserData.Size = *(unsigned __int16 *)off_140007018;
    v26 = &unk_140005448;
    UserData.Reserved = 2;
    v27 = 88;
    v28 = 1;
    v23[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x140011160  mov     [rsp-8+arg_10], rbx
0x140011165  mov     [rsp-8+arg_18], rsi
0x14001116a  push    rbp
0x14001116b  push    rdi
0x14001116c  push    r12
0x14001116e  push    r14
0x140011170  push    r15
0x140011172  lea     rbp, [rsp-37h]
0x140011177  sub     rsp, 0F0h
0x14001117e  mov     rax, cs:__security_cookie
0x140011185  xor     rax, rsp
0x140011188  mov     [rbp+57h+var_30], rax
0x14001118c  xor     r12d, r12d
0x14001118f  mov     esi, r8d
0x140011192  movsxd  r15, edx
0x140011195  mov     r14d, r9d
0x140011198  mov     rdi, rcx
0x14001119b  test    r8d, r8d
0x14001119e  jnz     short loc_1400111A5
0x1400111a0  mov     eax, r12d
0x1400111a3  jmp     short loc_1400111BB
0x1400111a5  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400111ac  nop     dword ptr [rax+rax+00h]
0x1400111b1  imul    rdx, rsi, 2710h
0x1400111b8  add     rax, rdx
0x1400111bb  mov     rcx, r15
0x1400111be  xor     bl, bl
0x1400111c0  shl     rcx, 5
0x1400111c4  add     rcx, 0A8h
0x1400111cb  add     rcx, rdi
0x1400111ce  mov     rdx, [rcx+10h]
0x1400111d2  test    dl, 1
0x1400111d5  jz      short loc_140011218
0x1400111d7  test    r14b, 1
0x1400111db  jnz     short loc_1400111EF
0x1400111dd  xor     r8b, r8b
0x1400111e0  test    r14b, 2
0x1400111e4  jz      short loc_14001124A
0x1400111e6  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1400111ea  cmp     rax, rdx
0x1400111ed  jnb     short loc_14001124A
0x1400111ef  mov     rdx, [rcx]
0x1400111f2  mov     bl, 1
0x1400111f4  cmp     [rdx+8], rcx
0x1400111f8  jnz     loc_140011393
0x1400111fe  mov     r8, [rcx+8]
0x140011202  cmp     [r8], rcx
0x140011205  jnz     loc_140011393
0x14001120b  mov     [r8], rdx
0x14001120e  xorps   xmm0, xmm0
0x140011211  mov     [rdx+8], r8
0x140011215  movups  xmmword ptr [rcx], xmm0
0x140011218  and     rax, 0FFFFFFFFFFFFFFFEh
0x14001121c  mov     [rcx+10h], rax
0x140011220  call    BampInsertThrottlingActionItem
0x140011225  mov     r8b, 1
0x140011228  test    bl, bl
0x14001122a  jnz     short loc_14001124A
0x14001122c  mov     eax, 1
0x140011231  lock xadd [rdi+108h], rax
0x14001123a  inc     rax
0x14001123d  cmp     rax, 1
0x140011241  jg      short loc_14001124A
0x140011243  mov     ecx, 0Eh
0x140011248  int     29h; Win8: RtlFailFast(ecx)
0x14001124a  mov     eax, cs:dword_140007010
0x140011250  cmp     eax, 5
0x140011253  jbe     loc_14001136A
0x140011259  mov     rax, [rdi+8]
0x14001125d  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140011261  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140011268  xor     r9d, r9d; RelatedActivityId
0x14001126b  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x14001126f  mov     ecx, [rax+1D0h]
0x140011275  lea     rax, [rsp+110h+var_DC]
0x14001127a  mov     [rbp+57h+var_90], rax
0x14001127e  lea     rax, [rsp+110h+var_D8]
0x140011283  mov     [rbp+57h+var_80], rax
0x140011287  lea     rax, [rbp+57h+var_D4]
0x14001128b  mov     [rbp+57h+var_70], rax
0x14001128f  lea     rax, [rbp+57h+var_D0]
0x140011293  mov     [rbp+57h+var_60], rax
0x140011297  lea     rax, [rsp+110h+var_E0]
0x14001129c  mov     [rbp+57h+var_50], rax
0x1400112a0  lea     rax, [rsp+110h+var_DF]
0x1400112a5  mov     [rbp+57h+var_40], rax
0x1400112a9  movzx   eax, cs:word_14000543E
0x1400112b0  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1400112b3  mov     rax, cs:off_140007018
0x1400112ba  mov     [rbp+57h+var_B0.Ptr], rax
0x1400112be  mov     [rsp+110h+var_DC], ecx
0x1400112c2  lea     rcx, _TraceLoggingMetadata
0x1400112c9  mov     [rsp+110h+var_E0], r8b
0x1400112ce  xor     r8d, r8d; ActivityId
0x1400112d1  mov     [rbp+57h+var_88], 4
0x1400112d9  mov     [rsp+110h+var_D8], r15d
0x1400112de  mov     [rbp+57h+var_78], 4
0x1400112e6  mov     [rbp+57h+var_D4], esi
0x1400112e9  mov     [rbp+57h+var_68], 4
0x1400112f1  mov     [rbp+57h+var_D0], r14d
0x1400112f5  mov     [rbp+57h+var_58], 4
0x1400112fd  mov     [rbp+57h+var_48], 1
0x140011305  mov     [rsp+110h+var_DF], bl
0x140011309  mov     [rbp+57h+var_38], 1
0x140011311  movzx   eax, word ptr [rax]
0x140011314  mov     [rbp+57h+var_B0.Size], eax
0x140011317  lea     rax, unk_140005448
0x14001131e  mov     [rbp+57h+var_A0], rax
0x140011322  lea     rax, _TraceLoggingMetadataEnd
0x140011329  sub     eax, ecx
0x14001132b  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140011332  mov     [rbp+57h+var_98], 58h ; 'X'
0x140011339  mov     [rbp+57h+var_94], 1
0x140011340  mov     [rbp+57h+var_CC], eax
0x140011343  mov     eax, [rbp+57h+var_CC]
0x140011346  mov     rcx, cs:RegHandle; RegHandle
0x14001134d  lea     rax, [rbp+57h+var_B0]
0x140011351  mov     [rsp+110h+UserData], rax; UserData
0x140011356  mov     [rsp+110h+UserDataCount], 8; UserDataCount
0x14001135e  call    cs:__imp_EtwWriteTransfer
0x140011365  nop     dword ptr [rax+rax+00h]
0x14001136a  mov     rcx, [rbp+57h+var_30]
0x14001136e  xor     rcx, rsp; StackCookie
0x140011371  call    __security_check_cookie
0x140011376  lea     r11, [rsp+110h+var_20]
0x14001137e  mov     rbx, [r11+40h]
0x140011382  mov     rsi, [r11+48h]
0x140011386  mov     rsp, r11
0x140011389  pop     r15
0x14001138b  pop     r14
0x14001138d  pop     r12
0x14001138f  pop     rdi
0x140011390  pop     rbp
0x140011391  retn
0x140011393  mov     ecx, 3
0x140011398  int     29h; Win8: RtlFailFast(ecx)
```
