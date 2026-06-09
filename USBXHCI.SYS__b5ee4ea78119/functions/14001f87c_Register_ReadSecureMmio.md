# Register_ReadSecureMmio

- ea: `0x14001f87c`
- end: `0x14001fb27`
- name: `Register_ReadSecureMmio`
- size: `683`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14001ac04`
- `0x14001f830`
- `0x1400371c0`
- `0x140049f98`
- `0x140049ffc`

## callees

- `0x14001ad0c`
- `0x14001c178`
- `0x14001d02c`
- `0x14001f87c`
- `0x140059970`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb16`
- `ntoskrnl!ExAllocatePool2` at `0x14001fa74`
- `ntoskrnl!ExAllocatePool2` at `0x14001fa74`

## pseudocode

```c
void __fastcall Register_ReadSecureMmio(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, void *a5)
{
  __int64 v7; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // esi
  unsigned __int64 v14; // rbx
  int *p_P; // rdi
  int v16; // edx
  int v17; // edx
  __int64 v19; // [rsp+38h] [rbp-49h]
  GUID v20[2]; // [rsp+40h] [rbp-41h] BYREF
  __int128 v21; // [rsp+60h] [rbp-21h]
  unsigned __int64 v22; // [rsp+70h] [rbp-11h]
  __int64 P; // [rsp+78h] [rbp-9h] BYREF
  int v24; // [rsp+80h] [rbp-1h]

  v24 = 0;
  P = 0;
  v22 = 0;
  v7 = *(_QWORD *)(a1 + 8);
  v9 = 8;
  memset(v20, 0, sizeof(v20));
  v21 = 0;
  v19 = *(_QWORD *)(v7 + 112);
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1u:
        v10 = 2;
        break;
      case 2u:
        v10 = 4;
        break;
      case 3u:
        v10 = 8;
        break;
      default:
        v11 = a4;
LABEL_6:
        v13 = 0;
        goto LABEL_7;
    }
  }
  else
  {
    v10 = 1;
  }
  v11 = a4;
  v12 = v10 * a4;
  if ( v10 * (unsigned __int64)a4 > 0xFFFFFFFF )
    goto LABEL_6;
  if ( !v12 )
    goto LABEL_6;
  v13 = v12 + 8;
  if ( v12 + 8 < v12 )
    goto LABEL_6;
  if ( v13 < 0x10 )
    v13 = 16;
LABEL_7:
  switch ( a3 )
  {
    case 0u:
      v9 = 1;
      goto LABEL_11;
    case 1u:
      v9 = 2;
      goto LABEL_11;
    case 2u:
      v9 = 4;
      goto LABEL_11;
    case 3u:
LABEL_11:
      v14 = v9 * v11;
      if ( v14 <= 0xFFFFFFFF )
        goto LABEL_13;
      break;
  }
  LODWORD(v14) = 0;
LABEL_13:
  if ( v13 <= 0x10 )
  {
    p_P = (int *)&P;
    v13 = 16;
LABEL_15:
    *(_QWORD *)v20[1].Data4 = *(_QWORD *)(a1 + 128);
    *((_QWORD *)&v21 + 1) = a2;
    memset(v20, 0, 24);
    *(_QWORD *)&v21 = 10;
    v22 = __PAIR64__(a4, a3);
    if ( (int)SecureChannel_SendRequestSynchronously(v19, v20, 56, (__int64)p_P, v13) >= 0 )
    {
      v16 = *p_P;
      if ( *p_P < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
            v16,
            6,
            78,
            (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
            *p_P);
        }
      }
      else
      {
        memmove(a5, p_P + 2, (unsigned int)v14);
      }
    }
    if ( p_P )
    {
      if ( p_P != (int *)&P )
        ExFreePoolWithTag(p_P, 0x49434858u);
    }
    return;
  }
  p_P = (int *)ExAllocatePool2(64, v13, 1229146200);
  if ( p_P )
    goto LABEL_15;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_D(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
      v17,
      6,
      77,
      (__int64)WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids,
      v13);
  }
}

```

## disassembly

```asm
0x14001f87c  push    rbp
0x14001f87e  push    rbx
0x14001f87f  push    rsi
0x14001f880  push    rdi
0x14001f881  push    r12
0x14001f883  push    r13
0x14001f885  push    r14
0x14001f887  push    r15
0x14001f889  lea     rbp, [rsp-17h]
0x14001f88e  sub     rsp, 98h
0x14001f895  mov     rax, cs:__security_cookie
0x14001f89c  xor     rax, rsp
0x14001f89f  mov     [rbp+4Fh+var_48], rax
0x14001f8a3  mov     r13, [rbp+4Fh+arg_20]
0x14001f8a7  xor     eax, eax
0x14001f8a9  mov     qword ptr [rbp+4Fh+var_54], rax
0x14001f8ad  xorps   xmm0, xmm0
0x14001f8b0  mov     [rbp-9], rax
0x14001f8b4  mov     r14, rcx
0x14001f8b7  mov     [rbp+4Fh+var_60], rax
0x14001f8bb  mov     r15d, r8d
0x14001f8be  mov     rax, [rcx+8]
0x14001f8c2  mov     edi, 0FFFFFFFFh
0x14001f8c7  mov     ecx, r8d
0x14001f8ca  mov     [rbp+4Fh+var_A0], rdx
0x14001f8ce  mov     r12d, r9d
0x14001f8d1  mov     edx, 8
0x14001f8d6  movups  [rbp+4Fh+var_90], xmm0
0x14001f8da  movups  [rbp+4Fh+var_80], xmm0
0x14001f8de  lea     r9d, [rdx+8]
0x14001f8e2  lea     r11d, [rdx-4]
0x14001f8e6  lea     r8d, [rdx-6]
0x14001f8ea  lea     r10d, [rdx-7]
0x14001f8ee  movups  [rbp+4Fh+var_70], xmm0
0x14001f8f2  mov     rax, [rax+70h]
0x14001f8f6  mov     [rbp+4Fh+var_98], rax
0x14001f8fa  test    ecx, ecx
0x14001f8fc  jz      loc_14001FA4F
0x14001f902  sub     ecx, r10d
0x14001f905  jz      loc_14001FA47
0x14001f90b  sub     ecx, r10d
0x14001f90e  jnz     loc_14001FA05
0x14001f914  mov     ecx, r11d
0x14001f917  mov     rax, r12
0x14001f91a  mov     rbx, r12
0x14001f91d  imul    rax, rcx
0x14001f921  cmp     rax, rdi
0x14001f924  jbe     loc_14001FA20
0x14001f92a  xor     esi, esi
0x14001f92c  mov     ecx, r15d
0x14001f92f  test    r15d, r15d
0x14001f932  jz      loc_14001FA5F
0x14001f938  sub     ecx, r10d
0x14001f93b  jz      loc_14001FA57
0x14001f941  sub     ecx, r10d
0x14001f944  jnz     loc_14001FA12
0x14001f94a  mov     rdx, r11
0x14001f94d  imul    rbx, rdx
0x14001f951  cmp     rbx, rdi
0x14001f954  jbe     short loc_14001F958
0x14001f956  xor     ebx, ebx
0x14001f958  cmp     esi, r9d
0x14001f95b  ja      loc_14001FA67
0x14001f961  lea     rdi, [rbp+4Fh+P]
0x14001f965  mov     esi, r9d
0x14001f968  mov     rax, [r14+80h]
0x14001f96f  lea     rdx, [rbp+4Fh+var_90]
0x14001f973  mov     rcx, [rbp+4Fh+var_98]
0x14001f977  xorps   xmm0, xmm0
0x14001f97a  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x14001f97e  mov     r9, rdi
0x14001f981  mov     rax, [rbp+4Fh+var_A0]
0x14001f985  mov     r8d, 38h ; '8'
0x14001f98b  mov     qword ptr [rbp+4Fh+var_70+8], rax
0x14001f98f  mov     qword ptr [rbp+4Fh+var_90], 0
0x14001f997  movdqu  [rbp+4Fh+var_90+8], xmm0
0x14001f99c  mov     qword ptr [rbp+4Fh+var_70], 0Ah
0x14001f9a4  mov     dword ptr [rbp+4Fh+var_60], r15d
0x14001f9a8  mov     dword ptr [rbp+4Fh+var_60+4], r12d
0x14001f9ac  mov     dword ptr [rsp+0D0h+var_B0], esi
0x14001f9b0  call    SecureChannel_SendRequestSynchronously
0x14001f9b5  test    eax, eax
0x14001f9b7  js      short loc_14001F9D2
0x14001f9b9  mov     edx, [rdi]
0x14001f9bb  test    edx, edx
0x14001f9bd  js      loc_14001FACC
0x14001f9c3  mov     r8d, ebx; Size
0x14001f9c6  lea     rdx, [rdi+8]; Src
0x14001f9ca  mov     rcx, r13; void *
0x14001f9cd  call    memmove
0x14001f9d2  test    rdi, rdi
0x14001f9d5  jz      short loc_14001F9E4
0x14001f9d7  lea     rax, [rbp+4Fh+P]
0x14001f9db  cmp     rdi, rax
0x14001f9de  jnz     loc_14001FB0E
0x14001f9e4  mov     rcx, [rbp+4Fh+var_48]
0x14001f9e8  xor     rcx, rsp; StackCookie
0x14001f9eb  call    __security_check_cookie
0x14001f9f0  add     rsp, 98h
0x14001f9f7  pop     r15
0x14001f9f9  pop     r14
0x14001f9fb  pop     r13
0x14001f9fd  pop     r12
0x14001f9ff  pop     rdi
0x14001fa00  pop     rsi
0x14001fa01  pop     rbx
0x14001fa02  pop     rbp
0x14001fa03  retn
0x14001fa05  cmp     ecx, r10d
0x14001fa08  jz      short loc_14001FA3F
0x14001fa0a  mov     rbx, r12
0x14001fa0d  jmp     loc_14001F92A
0x14001fa12  cmp     ecx, r10d
0x14001fa15  jnz     loc_14001F956
0x14001fa1b  jmp     loc_14001F94D
0x14001fa20  test    eax, eax
0x14001fa22  jz      loc_14001F92A
0x14001fa28  lea     esi, [rax+8]
0x14001fa2b  cmp     esi, eax
0x14001fa2d  jb      loc_14001F92A
0x14001fa33  cmp     esi, r9d
0x14001fa36  cmovb   esi, r9d
0x14001fa3a  jmp     loc_14001F92C
0x14001fa3f  mov     rcx, rdx
0x14001fa42  jmp     loc_14001F917
0x14001fa47  mov     rcx, r8
0x14001fa4a  jmp     loc_14001F917
0x14001fa4f  mov     rcx, r10
0x14001fa52  jmp     loc_14001F917
0x14001fa57  mov     rdx, r8
0x14001fa5a  jmp     loc_14001F94D
0x14001fa5f  mov     rdx, r10
0x14001fa62  jmp     loc_14001F94D
0x14001fa67  mov     edx, esi
0x14001fa69  mov     ecx, 40h ; '@'
0x14001fa6e  mov     r8d, 49434858h
0x14001fa74  call    cs:__imp_ExAllocatePool2
0x14001fa7b  nop     dword ptr [rax+rax+00h]
0x14001fa80  mov     rdi, rax
0x14001fa83  test    rax, rax
0x14001fa86  jnz     loc_14001F968
0x14001fa8c  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001fa93  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fa9a  jz      loc_14001F9E4
0x14001faa0  mov     rcx, [r14+8]
0x14001faa4  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001faab  lea     r9d, [rdi+4Dh]
0x14001faaf  mov     [rsp+0D0h+var_A8], esi
0x14001fab3  lea     r8d, [rdi+6]
0x14001fab7  mov     [rsp+0D0h+var_B0], rax
0x14001fabc  mov     dl, 2
0x14001fabe  mov     rcx, [rcx+48h]
0x14001fac2  call    WPP_RECORDER_SF_D
0x14001fac7  jmp     loc_14001F9E4
0x14001facc  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001fad3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fada  jz      loc_14001F9D2
0x14001fae0  mov     rcx, [r14+8]
0x14001fae4  lea     rax, WPP_2d3ac5afa9ff3cee117362f2154ae4bf_Traceguids
0x14001faeb  mov     [rsp+0D0h+var_A8], edx
0x14001faef  mov     r9d, 4Eh ; 'N'
0x14001faf5  mov     dl, 2
0x14001faf7  mov     [rsp+0D0h+var_B0], rax
0x14001fafc  mov     rcx, [rcx+48h]
0x14001fb00  lea     r8d, [r9-48h]
0x14001fb04  call    WPP_RECORDER_SF_d
0x14001fb09  jmp     loc_14001F9D2
0x14001fb0e  mov     edx, 49434858h; Tag
0x14001fb13  mov     rcx, rdi; P
0x14001fb16  call    cs:__imp_ExFreePoolWithTag
0x14001fb1d  nop     dword ptr [rax+rax+00h]
0x14001fb22  jmp     loc_14001F9E4
```
