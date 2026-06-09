# sub_18019ACAC

- ea: `0x18019acac`
- end: `0x18019b2a3`
- name: `sub_18019ACAC`
- size: `1527`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180014e30`

## callees

- `0x18000f230`
- `0x1800130bc`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180043c4c`
- `0x180045d1c`
- `0x180050d6c`
- `0x18008b3a0`
- `0x1800ec0e0`
- `0x1800f0fa4`
- `0x1801164e4`
- `0x18019acac`
- `0x180208e70`
- `0x18023c888`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ad6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ae48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019af3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019afff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019b0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019b1bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ad6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019ae48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019af3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019afff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019b0b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18019b1bc`

## string_xrefs

- `0x18019ad35`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019adca`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019aea6`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019af9d`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019b05d`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019b110`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019b18e`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`
- `0x18019b21a`: `CMPMFTNodeInfoAsync::OnMFTDrainComplete`

## pseudocode

```c
__int64 __fastcall sub_18019ACAC(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  unsigned int v5; // r12d
  int v6; // ebx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  int v29; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v30[3]; // [rsp+38h] [rbp-18h] BYREF
  char v31; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v32; // [rsp+90h] [rbp+40h] BYREF
  char v33; // [rsp+98h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 824);
  v30[1] = v30;
  v30[2] = v2;
  v30[0] = v30;
  v5 = 0;
  v29 = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 56) + 56LL))(*(_QWORD *)(v2 + 56), 0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 64) + 56LL))(*(_QWORD *)(v2 + 64), 0);
  sub_180045D1C(&v33, *(_QWORD *)(a1 + 808));
  v32 = 0;
  LODWORD(a2) = sub_18008B3A0(a2, qword_180377D30, 0);
  sub_18002FEE0(&v31, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 974);
  v6 = sub_1801164E4(a1 + 112, (unsigned int)a2, &v32);
  if ( v6 < 0 )
  {
    v7 = (__int64 *)qword_1803CEF18;
    if ( !qword_1803CEF18 )
    {
      v8 = MFGetCallStackTracingWeakReference(0);
      qword_1803CEF18 = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v7 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = sub_1800402C0(v7);
      if ( *(_DWORD *)(v9 + 1996) != v6 )
        sub_1800EC0E0(v9, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 974, (unsigned int)v6);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_13;
    v10 = 85;
LABEL_12:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v10, &stru_180364420, a1, v6);
LABEL_13:
    sub_18003ECB0(&v31);
    sub_18000F230(&v33);
    goto LABEL_75;
  }
  v11 = v32;
  v12 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL * v32);
  if ( !v12 )
  {
    v13 = (__int64 *)qword_1803CEF18;
    v6 = -2147418113;
    if ( !qword_1803CEF18 )
    {
      v14 = MFGetCallStackTracingWeakReference(0);
      qword_1803CEF18 = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v13 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = sub_1800402C0(v13);
      if ( *(_DWORD *)(v15 + 1996) != -2147418113 )
        sub_1800EC0E0(v15, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 977, 2147549183LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_13;
    v10 = 86;
    goto LABEL_12;
  }
  *(_DWORD *)(v12 + 432) = 1;
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    sub_180050D6C(*((_QWORD *)RequestContext + 7), 87, &stru_180364420, a1, v11);
  if ( *(_DWORD *)(a1 + 752) == 1 )
  {
    v6 = sub_180208E70(a1, &v29, *(_QWORD *)(a1 + 816));
    if ( v6 < 0 )
    {
      v16 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v17 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v16 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = sub_1800402C0(v16);
        if ( *(_DWORD *)(v18 + 1996) != v6 )
          sub_1800EC0E0(v18, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 993, (unsigned int)v6);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_13;
      v10 = 88;
      goto LABEL_12;
    }
  }
  else if ( *(_DWORD *)(a1 + 764) == 1 )
  {
    v6 = sub_18023C888(a1, &v29, *(_QWORD *)(a1 + 816));
    if ( v6 < 0 )
    {
      v19 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v20 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v19 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = sub_1800402C0(v19);
        if ( *(_DWORD *)(v21 + 1996) != v6 )
          sub_1800EC0E0(v21, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 1001, (unsigned int)v6);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_13;
      v10 = 89;
      goto LABEL_12;
    }
  }
  v6 = sub_1800130BC(v2, *(_QWORD *)(a1 + 816), &v29);
  if ( v6 < 0 )
  {
    v22 = (__int64 *)qword_1803CEF18;
    if ( !qword_1803CEF18 )
    {
      v23 = MFGetCallStackTracingWeakReference(0);
      qword_1803CEF18 = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v22 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = sub_1800402C0(v22);
      if ( *(_DWORD *)(v24 + 1996) != v6 )
        sub_1800EC0E0(v24, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 1023, (unsigned int)v6);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_13;
    v10 = 90;
    goto LABEL_12;
  }
  sub_18003ECB0(&v31);
  sub_18000F230(&v33);
  if ( *(_DWORD *)(v2 + 1008) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 64) + 64LL))(*(_QWORD *)(v2 + 64), 0);
    v5 = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v2 + 64) + 56LL))(*(_QWORD *)(v2 + 64), 1);
    sub_18002FEE0(&v31, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 1036);
    v6 = sub_180043C4C(v2);
    if ( v6 < 0 )
    {
      v25 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v26 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v25 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = sub_1800402C0(v25);
        if ( *(_DWORD *)(v27 + 1996) != v6 )
          sub_1800EC0E0(v27, "CMPMFTNodeInfoAsync::OnMFTDrainComplete", 1036, (unsigned int)v6);
      }
      if ( byte_1803CECE8 )
        sub_180050D6C(*((_QWORD *)RequestContext + 2), 91, &stru_180364420, a1, v6);
    }
    sub_18003ECB0(&v31);
  }
LABEL_75:
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 64) + 64LL))(*(_QWORD *)(v2 + 64), v5);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v2 + 56) + 64LL))(*(_QWORD *)(v2 + 56), 0);
  sub_1800F0FA4(&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18019acac  push    rbp
0x18019acae  push    rbx
0x18019acaf  push    rdi
0x18019acb0  push    r12
0x18019acb2  push    r15
0x18019acb4  mov     rbp, rsp
0x18019acb7  sub     rsp, 50h
0x18019acbb  mov     r15, [rcx+338h]
0x18019acc2  lea     rax, [rbp+var_18]
0x18019acc6  mov     [rbp+var_10], rax
0x18019acca  mov     rdi, rcx
0x18019accd  mov     [rbp+var_8], r15
0x18019acd1  lea     rax, [rbp+var_18]
0x18019acd5  mov     [rbp+var_18], rax
0x18019acd9  mov     rbx, rdx
0x18019acdc  xor     r12d, r12d
0x18019acdf  xor     edx, edx
0x18019ace1  mov     [rbp+var_20], r12d
0x18019ace5  mov     rcx, [r15+38h]
0x18019ace9  mov     rax, [rcx]
0x18019acec  mov     rax, [rax+38h]
0x18019acf0  call    cs:__guard_dispatch_icall_fptr
0x18019acf6  mov     rcx, [r15+40h]
0x18019acfa  xor     edx, edx
0x18019acfc  mov     rax, [rcx]
0x18019acff  mov     rax, [rax+38h]
0x18019ad03  call    cs:__guard_dispatch_icall_fptr
0x18019ad09  mov     rdx, [rdi+328h]
0x18019ad10  lea     rcx, [rbp+arg_18]
0x18019ad14  call    sub_180045D1C
0x18019ad19  xor     r8d, r8d
0x18019ad1c  mov     [rbp+arg_10], r12d
0x18019ad20  lea     rdx, qword_180377D30
0x18019ad27  mov     rcx, rbx
0x18019ad2a  call    sub_18008B3A0
0x18019ad2f  mov     r8d, 3CEh
0x18019ad35  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019ad3c  lea     rcx, [rbp+arg_0]
0x18019ad40  mov     ebx, eax
0x18019ad42  call    sub_18002FEE0
0x18019ad47  lea     rcx, [rdi+70h]
0x18019ad4b  mov     edx, ebx
0x18019ad4d  lea     r8, [rbp+arg_10]
0x18019ad51  call    sub_1801164E4
0x18019ad56  mov     ebx, eax
0x18019ad58  test    eax, eax
0x18019ad5a  jns     loc_18019AE22
0x18019ad60  mov     rcx, cs:qword_1803CEF18
0x18019ad67  test    rcx, rcx
0x18019ad6a  jnz     short loc_18019ADB4
0x18019ad6c  call    cs:MFGetCallStackTracingWeakReference
0x18019ad73  nop     dword ptr [rax+rax+00h]
0x18019ad78  mov     cs:qword_1803CEF18, rax
0x18019ad7f  mov     rcx, rax
0x18019ad82  test    rax, rax
0x18019ad85  jz      short loc_18019ADA6
0x18019ad87  mov     rax, [rax]
0x18019ad8a  mov     edx, 7F0h
0x18019ad8f  mov     rax, [rax+8]
0x18019ad93  call    cs:__guard_dispatch_icall_fptr
0x18019ad99  test    eax, eax
0x18019ad9b  jz      short loc_18019ADA6
0x18019ad9d  mov     rcx, cs:qword_1803CEF18
0x18019ada4  jmp     short loc_18019ADB4
0x18019ada6  lea     rcx, qword_1803CE250
0x18019adad  mov     cs:qword_1803CEF18, rcx
0x18019adb4  cmp     [rcx+8], r12b
0x18019adb8  jz      short loc_18019ADDF
0x18019adba  call    sub_1800402C0
0x18019adbf  cmp     [rax+7CCh], ebx
0x18019adc5  jz      short loc_18019ADDF
0x18019adc7  mov     r9d, ebx
0x18019adca  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019add1  mov     r8d, 3CEh
0x18019add7  mov     rcx, rax
0x18019adda  call    sub_1800EC0E0
0x18019addf  cmp     cs:byte_1803CECE8, 1
0x18019ade6  jb      short loc_18019AE0B
0x18019ade8  mov     edx, 55h ; 'U'
0x18019aded  mov     rcx, cs:RequestContext
0x18019adf4  lea     r8, stru_180364420
0x18019adfb  mov     r9, rdi
0x18019adfe  mov     [rsp+50h+var_30], ebx
0x18019ae02  mov     rcx, [rcx+10h]
0x18019ae06  call    sub_180050D6C
0x18019ae0b  lea     rcx, [rbp+arg_0]
0x18019ae0f  call    sub_18003ECB0
0x18019ae14  lea     rcx, [rbp+arg_18]
0x18019ae18  call    sub_18000F230
0x18019ae1d  jmp     loc_18019B264
0x18019ae22  mov     r8d, [rbp+arg_10]
0x18019ae26  mov     rax, [rdi+18h]
0x18019ae2a  mov     rdx, [rax+r8*8]
0x18019ae2e  test    rdx, rdx
0x18019ae31  jnz     loc_18019AED2
0x18019ae37  mov     rcx, cs:qword_1803CEF18
0x18019ae3e  mov     ebx, 8000FFFFh
0x18019ae43  test    rcx, rcx
0x18019ae46  jnz     short loc_18019AE90
0x18019ae48  call    cs:MFGetCallStackTracingWeakReference
0x18019ae4f  nop     dword ptr [rax+rax+00h]
0x18019ae54  mov     cs:qword_1803CEF18, rax
0x18019ae5b  mov     rcx, rax
0x18019ae5e  test    rax, rax
0x18019ae61  jz      short loc_18019AE82
0x18019ae63  mov     rax, [rax]
0x18019ae66  mov     edx, 7F0h
0x18019ae6b  mov     rax, [rax+8]
0x18019ae6f  call    cs:__guard_dispatch_icall_fptr
0x18019ae75  test    eax, eax
0x18019ae77  jz      short loc_18019AE82
0x18019ae79  mov     rcx, cs:qword_1803CEF18
0x18019ae80  jmp     short loc_18019AE90
0x18019ae82  lea     rcx, qword_1803CE250
0x18019ae89  mov     cs:qword_1803CEF18, rcx
0x18019ae90  cmp     [rcx+8], r12b
0x18019ae94  jz      short loc_18019AEBB
0x18019ae96  call    sub_1800402C0
0x18019ae9b  cmp     [rax+7CCh], ebx
0x18019aea1  jz      short loc_18019AEBB
0x18019aea3  mov     r9d, ebx
0x18019aea6  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019aead  mov     r8d, 3D1h
0x18019aeb3  mov     rcx, rax
0x18019aeb6  call    sub_1800EC0E0
0x18019aebb  cmp     cs:byte_1803CECE8, 1
0x18019aec2  jb      loc_18019AE0B
0x18019aec8  mov     edx, 56h ; 'V'
0x18019aecd  jmp     loc_18019ADED
0x18019aed2  mov     dword ptr [rdx+1B0h], 1
0x18019aedc  cmp     cs:byte_1803CECE9, 8
0x18019aee3  jb      short loc_18019AF09
0x18019aee5  mov     rcx, cs:RequestContext
0x18019aeec  mov     edx, 57h ; 'W'
0x18019aef1  mov     [rsp+50h+var_30], r8d
0x18019aef6  mov     r9, rdi
0x18019aef9  lea     r8, stru_180364420
0x18019af00  mov     rcx, [rcx+38h]
0x18019af04  call    sub_180050D6C
0x18019af09  cmp     dword ptr [rdi+2F0h], 1
0x18019af10  jnz     loc_18019AFC9
0x18019af16  mov     r8, [rdi+330h]
0x18019af1d  lea     rdx, [rbp+var_20]
0x18019af21  mov     rcx, rdi
0x18019af24  call    sub_180208E70
0x18019af29  mov     ebx, eax
0x18019af2b  test    eax, eax
0x18019af2d  jns     loc_18019B089
0x18019af33  mov     rcx, cs:qword_1803CEF18
0x18019af3a  test    rcx, rcx
0x18019af3d  jnz     short loc_18019AF87
0x18019af3f  call    cs:MFGetCallStackTracingWeakReference
0x18019af46  nop     dword ptr [rax+rax+00h]
0x18019af4b  mov     cs:qword_1803CEF18, rax
0x18019af52  mov     rcx, rax
0x18019af55  test    rax, rax
0x18019af58  jz      short loc_18019AF79
0x18019af5a  mov     rax, [rax]
0x18019af5d  mov     edx, 7F0h
0x18019af62  mov     rax, [rax+8]
0x18019af66  call    cs:__guard_dispatch_icall_fptr
0x18019af6c  test    eax, eax
0x18019af6e  jz      short loc_18019AF79
0x18019af70  mov     rcx, cs:qword_1803CEF18
0x18019af77  jmp     short loc_18019AF87
0x18019af79  lea     rcx, qword_1803CE250
0x18019af80  mov     cs:qword_1803CEF18, rcx
0x18019af87  cmp     [rcx+8], r12b
0x18019af8b  jz      short loc_18019AFB2
0x18019af8d  call    sub_1800402C0
0x18019af92  cmp     [rax+7CCh], ebx
0x18019af98  jz      short loc_18019AFB2
0x18019af9a  mov     r9d, ebx
0x18019af9d  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019afa4  mov     r8d, 3E1h
0x18019afaa  mov     rcx, rax
0x18019afad  call    sub_1800EC0E0
0x18019afb2  cmp     cs:byte_1803CECE8, 1
0x18019afb9  jb      loc_18019AE0B
0x18019afbf  mov     edx, 58h ; 'X'
0x18019afc4  jmp     loc_18019ADED
0x18019afc9  cmp     dword ptr [rdi+2FCh], 1
0x18019afd0  jnz     loc_18019B089
0x18019afd6  mov     r8, [rdi+330h]
0x18019afdd  lea     rdx, [rbp+var_20]
0x18019afe1  mov     rcx, rdi
0x18019afe4  call    sub_18023C888
0x18019afe9  mov     ebx, eax
0x18019afeb  test    eax, eax
0x18019afed  jns     loc_18019B089
0x18019aff3  mov     rcx, cs:qword_1803CEF18
0x18019affa  test    rcx, rcx
0x18019affd  jnz     short loc_18019B047
0x18019afff  call    cs:MFGetCallStackTracingWeakReference
0x18019b006  nop     dword ptr [rax+rax+00h]
0x18019b00b  mov     cs:qword_1803CEF18, rax
0x18019b012  mov     rcx, rax
0x18019b015  test    rax, rax
0x18019b018  jz      short loc_18019B039
0x18019b01a  mov     rax, [rax]
0x18019b01d  mov     edx, 7F0h
0x18019b022  mov     rax, [rax+8]
0x18019b026  call    cs:__guard_dispatch_icall_fptr
0x18019b02c  test    eax, eax
0x18019b02e  jz      short loc_18019B039
0x18019b030  mov     rcx, cs:qword_1803CEF18
0x18019b037  jmp     short loc_18019B047
0x18019b039  lea     rcx, qword_1803CE250
0x18019b040  mov     cs:qword_1803CEF18, rcx
0x18019b047  cmp     [rcx+8], r12b
0x18019b04b  jz      short loc_18019B072
0x18019b04d  call    sub_1800402C0
0x18019b052  cmp     [rax+7CCh], ebx
0x18019b058  jz      short loc_18019B072
0x18019b05a  mov     r9d, ebx
0x18019b05d  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019b064  mov     r8d, 3E9h
0x18019b06a  mov     rcx, rax
0x18019b06d  call    sub_1800EC0E0
0x18019b072  cmp     cs:byte_1803CECE8, 1
0x18019b079  jb      loc_18019AE0B
0x18019b07f  mov     edx, 59h ; 'Y'
0x18019b084  jmp     loc_18019ADED
0x18019b089  mov     rdx, [rdi+330h]
0x18019b090  lea     r8, [rbp+var_20]
0x18019b094  mov     rcx, r15
0x18019b097  call    sub_1800130BC
0x18019b09c  mov     ebx, eax
0x18019b09e  test    eax, eax
0x18019b0a0  jns     loc_18019B13C
0x18019b0a6  mov     rcx, cs:qword_1803CEF18
0x18019b0ad  test    rcx, rcx
0x18019b0b0  jnz     short loc_18019B0FA
0x18019b0b2  call    cs:MFGetCallStackTracingWeakReference
0x18019b0b9  nop     dword ptr [rax+rax+00h]
0x18019b0be  mov     cs:qword_1803CEF18, rax
0x18019b0c5  mov     rcx, rax
0x18019b0c8  test    rax, rax
0x18019b0cb  jz      short loc_18019B0EC
0x18019b0cd  mov     rax, [rax]
0x18019b0d0  mov     edx, 7F0h
0x18019b0d5  mov     rax, [rax+8]
0x18019b0d9  call    cs:__guard_dispatch_icall_fptr
0x18019b0df  test    eax, eax
0x18019b0e1  jz      short loc_18019B0EC
0x18019b0e3  mov     rcx, cs:qword_1803CEF18
0x18019b0ea  jmp     short loc_18019B0FA
0x18019b0ec  lea     rcx, qword_1803CE250
0x18019b0f3  mov     cs:qword_1803CEF18, rcx
0x18019b0fa  cmp     [rcx+8], r12b
0x18019b0fe  jz      short loc_18019B125
0x18019b100  call    sub_1800402C0
0x18019b105  cmp     [rax+7CCh], ebx
0x18019b10b  jz      short loc_18019B125
0x18019b10d  mov     r9d, ebx
0x18019b110  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019b117  mov     r8d, 3FFh
0x18019b11d  mov     rcx, rax
0x18019b120  call    sub_1800EC0E0
0x18019b125  cmp     cs:byte_1803CECE8, 1
0x18019b12c  jb      loc_18019AE0B
0x18019b132  mov     edx, 5Ah ; 'Z'
0x18019b137  jmp     loc_18019ADED
0x18019b13c  lea     rcx, [rbp+arg_0]
0x18019b140  call    sub_18003ECB0
0x18019b145  lea     rcx, [rbp+arg_18]
0x18019b149  call    sub_18000F230
0x18019b14e  cmp     [r15+3F0h], r12d
0x18019b155  jz      loc_18019B264
0x18019b15b  mov     rcx, [r15+40h]
0x18019b15f  xor     edx, edx
0x18019b161  mov     rax, [rcx]
0x18019b164  mov     rax, [rax+40h]
0x18019b168  call    cs:__guard_dispatch_icall_fptr
0x18019b16e  mov     rcx, [r15+40h]
0x18019b172  mov     r12d, 1
0x18019b178  mov     edx, r12d
0x18019b17b  mov     rax, [rcx]
0x18019b17e  mov     rax, [rax+38h]
0x18019b182  call    cs:__guard_dispatch_icall_fptr
0x18019b188  mov     r8d, 40Ch
0x18019b18e  lea     rdx, aCmpmftnodeinfo_60; "CMPMFTNodeInfoAsync::OnMFTDrainComplete"
0x18019b195  lea     rcx, [rbp+arg_0]
0x18019b199  call    sub_18002FEE0
0x18019b19e  mov     rcx, r15
0x18019b1a1  call    sub_180043C4C
0x18019b1a6  mov     ebx, eax
0x18019b1a8  test    eax, eax
0x18019b1aa  jns     loc_18019B25B
0x18019b1b0  mov     rcx, cs:qword_1803CEF18
0x18019b1b7  test    rcx, rcx
0x18019b1ba  jnz     short loc_18019B204
0x18019b1bc  call    cs:MFGetCallStackTracingWeakReference
0x18019b1c3  nop     dword ptr [rax+rax+00h]
0x18019b1c8  mov     cs:qword_1803CEF18, rax
0x18019b1cf  mov     rcx, rax
0x18019b1d2  test    rax, rax
0x18019b1d5  jz      short loc_18019B1F6
0x18019b1d7  mov     rax, [rax]
0x18019b1da  mov     edx, 7F0h
  ... truncated ...
```
